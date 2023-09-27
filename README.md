<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-Premises Active Directory Implemented in the Cloud (Azure)</h1>
This guide details the deployment of on-premises Active Directory on Azure Virtual Machines.<br />




<h2>Utilized Environments and Technologies</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>Key Deployment and Configuration Steps</h2>

- Step 1- Creating virtual machine
- Step 2- Ping DC-1's IP address
- Step 3- Enabling imbound rules via DC-1
- Step 4- Configuring users and allowing to logon to Client-1's OS
- Step 5- Restting a password

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/f7mtfnc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To kickstart the lab, the first step involves creating a virtual machine, specifically using the Windows Server 2022 image. Additionally, I have set up another virtual machine named "Client-1," utilizing a Windows 10 image, with the intention of connecting it to the domain controller in a subsequent step of this lab.
</p>
<br />

<p>
<img src="https://i.imgur.com/u6W5FSw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
As shown above, I attempted to ping the IP address of my DC-1 from my Client-1's operating system using the command prompt. However, it resulted in a timeout, and I did not receive any response. I will proceed with further configuration to determine if I can successfully ping DC-1 in the future.
</p>
<br />

<p>
<img src="https://i.imgur.com/zHHNMQG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The ping to DC-1's IP address has now started successfully. This was made possible by enabling two rules on DC-1 through the Microsoft firewall, specifically the ICMPv4 echo rules. After enabling these rules, the requests began to arrive, and the ping operation was accomplished without any issues.
</p>
<br />

<p>
<img src="https://i.imgur.com/qjNtZmt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here, I'm remotely connecting to an account that I created by configuring several domain users, granting them remote access to Client-1's virtual machine. Essentially, "bac.dap" has been added to the domain, enabling not only "bac.dap" but all other users to log in to Client-1's OS, even if it's their first time doing so.
</p>
<br />

<p>
<img src="https://i.imgur.com/XO9ksrz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
I intentionally attempted to lock out an account as part of my practice to reset the password and unlock the user's account within Active Directory.
</p>
<br />
