<p align="center">
<img src="https://imgur.com/jgPG99G.png" alt="Traffic Examination"/>
</p>

<h1>Assigning File Permissions in Azure Virtual Machines</h1>
In this tutorial, we will practice setting up different file permissions and access (on a domain) to different users within different groups. This is all done within Active Directory on our CLient Virtual Machine in Azure. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory
- File Permissions
- Security Groups

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Step 1: Login to both VMs
- Step 2: Create 4 Shared Folders & Set Permissions
- Step 3: Test Permissions
- Step 4: Create Security Group & Grant Additional Permissions
- Step 5: Test Security Group Members' Access

<h2>Actions and Observations</h2>

<p>
<img src="https://imgur.com/OBFtOuo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 1: Remote Desktop into both VMs that were used in the previous lab (DC-1 & Client-1). These are the subject VMs that will be used again for this lab with DC-1 being the Domain Controller once again. 
</p>
<br />

<p>
<img src="https://imgur.com/smc3Ano.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/Ar3Paox.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 2: Create four folders on DC-1's C: drive all with different access permissions: "read-access" - permission: read, "write-access" - permission read/write", "no-access" - permission none, "accounting" - permission read/write.
</p>
<br />

<p>
<img src="https://imgur.com/y5byjxa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 3: Log into a random employee account on Client-1 to test the newly added permissions/access created in step #2. Type "\\dc-1" into file explorer to show all shared folders created on the domain in step #2. Next, click any of the created shared folders and try to perfrom an action that does not align with the permissions used for said folder. You should not be allowed to open the folder titled "no-access" or write in the folder titled "read-access", etc.
</p>
<br />

<p>
<img src="https://imgur.com/xSXLxLo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 4: Create an "Organizational Unit" (OU) in Active Directory on DC-1 titled "Security Group". Next, create a new group within the OU titled "Accountants". Add Client-1's account to the list of "Accountant" members in the group (this will give the client-1 account access to the shared accountant folder created earlier).
</p>
<br />

<p>
<img src="https://imgur.com/FLEB0F4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 5: Restart Client-1 to allow the new permission settings to enable. Next access the shared "accountant" folder in \\dc-1  to verify access was successfully set up and granted for this user/employee. This is the conclusion of the lab.
</p>
<br />
