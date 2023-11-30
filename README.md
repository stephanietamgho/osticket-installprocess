<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - The Installation Process</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Microsoft Remote Desktop
- Internet Information Services (IIS)
<br />

<h2>Operating Systems Used </h2>

- Windows 10</b> (22H2)
<br />

<h2>List of Prerequisites</h2>

- In Azure: Create a Resource Group & a Windows 10 Virtual Machine with 2-4 CPUs 
- Install & Enable IIS in Windows 
- Download & Install PHP Manager for IIS
- Download & Install URL Rewrite Module
- Download PHP 7.3.8
- Download & Install VCRedist
- Download & Install MySQL 5.5.62
- Download & Install Heidi SQL
- Install osTicket v1.15.8
<br />

<h2>Installation Steps</h2>
<p><h3> 1. CREATE A RESOURCE GROUP AND A VIRTUAL MACHINE IN AZURE </h3></p>

<p><h3> 2. INSTALL / ENABLE IIS IN WINDOWS WITH CGI, COMMON HTTP FEATURES</h3></p>
<p>
<img src="https://i.imgur.com/ejN3TMV.png" height="50%" width="50%" alt="Turn Windows features on/off"/>
</p>
<p>
+ After you created a Resource group and a Windows 10 VM with 2-4 CPUs in Azure, connect to Microsoft Remote Desktop (Mac users) with your Windows 10 VM Public IP & credentials you created during its set up in Azure. </p>
<p>
+ In Windows, go to Control Panel > Programs > Programs & Features, and Turn Windows features on and off. 
</p>
<br />
<br />

<p>
<img src="https://i.imgur.com/KWxqFFv.png" height="40%" width="40%" alt="Enable IIS"/>
</p>
<img src="https://i.imgur.com/qYh2xQJ.png" height="40%" width="40%" alt="Enable IIS"/>
<p>
Before installing osTicket, you need IIS because osTicket is a web-based application. IIS (Internet Information Services) is the needed software that allows your computer to serve and display web pages on the internet.
<p>
Check mark Internet Information Services to enable it. Then, click on Web Management Tools > Application Development Features. Check CGI and Common Features to enable them as well.  
</p>
<br />


<p>
<p><h3>3. INSTALL PHP MANAGER FOR IIS</h3></p>
<p>
<img src="https://i.imgur.com/8xoF95v.png" height="50%" width="50%" alt="Install PHP Manager for IIS"/>
</p>
<p>
+ Download and install PHP Manager for IIS. </p>
 <p>
+ PHP Manager for IIS is a tool that helps Internet Information Services (IIS) work smoothly with PHP. It ensures that IIS can understand and process PHP code, making it compatible with osTicket since it's built using PHP.
</p>
<br />
<br />



<p>
<p><h3>4.INSTALL REWRITE MODULE</h3>
</p>
<p>
<img src="https://i.imgur.com/ETZ51Zc.png" height="50%" width="50%" alt="Install URL Rewrite Module"/>  
</p>
<p>
+ Download and install URL Rewrite Module.
</p>
<br />
<br />


<p>
<p><h3>5. CREATE A PHP FOLDER IN C:\</h3>
</p>
<p>
<img src="https://i.imgur.com/0VuTyZL.png" height="50%" width="50%" alt="PHP Folder on C:\"/>
</p>
<p>
+ On your Windows local disk C:\, create a folder and name it "PHP". 
</p>
<br />
<br />

<p>
<img width="235" alt="image" src="https://github.com/stephanietamgho/osticket-installprocess/assets/151881271/7e62aa36-1044-4776-b636-3fe5cb15a03a">
</p>
<p>
+ Then, download PHP 7.3.8, and unzip its contents, by clicking "Extract all", into C:\PHP folder you've just created.  
</p>
<br />
<br />



<p>
<p><h3>6. INSTALL VCREDIST</h3>
</p>  
<p>
<img src="https://i.imgur.com/fO1yYbA.png" height="50%" width="50%" alt="Visual C++ instal"/>
</p>
<p>
+ Download and install VCRedist. </p>
<p>
+ osTicket is built using certain components or libraries created with Visual C++. VCRedist ensures that your computer has all the right tools so that osTicket can run smoothly without missing anything.
</p>
<br />
<br />



<p>
<p><h3>7. INSTALL MySQL</h3>
</p>
<p>
<img src="https://i.imgur.com/OH31d1N.png" height="50%" width="50%" alt="MySQL instal"/>
</p>
<p>
+ Download and install MySQL. osTicket needs a place to store and organize information. </p>
<p>
+ MySQL is the filing cabinet and management system that helps osTicket keep things in order. Installing MySQL before osTicket ensures that there's an organized place for osTicket to store and retrieve the information it needs to handle support tickets effectively.
 <p>
+ Choose "Typical Setup" and upon installation, choose "Standard Configuration".
 </p> 
</p>
<br />
<br />


<p>
<img src="https://i.imgur.com/VOENr29.png" height="50%" width="50%" alt="MySQL credentials"/>
</p>
<p>
+ The standard configuration sets you up with a "root" username. You may add your own password.
</p>
<br />
<br />


<p>
<p><h3>8. OPEN IIS AND REGISTER PHP WITHIN IIS</h3>
</p>
<p>
<img src="https://i.imgur.com/0gMTZY6.png" height="50%" width="50%" alt="Open IIS as Admin"/>
</p>
<p>
+ Open IIS as an Admin. In the Windows search bar, write "IIS". 
</p>
<br />
<br />


<p>
<img src="https://i.imgur.com/8qMjwAQ.png" height="50%" width="50%" alt="Register PHP within IIS"/>
</p>
<p>
+ In IIS, click on PHP Manager > Register new PHP version.
</p>
<br />
<br />


<p>
<img src="https://i.imgur.com/pg1zuf0.png" height="50%" width="50%" alt="Pull CGI PHP folder"/>
</p>
<p>
+ You will be prompted to add a CGI with .exe extension. </p>
<p>
+ Select C:\PHP and you CGI file will appear. Click on it so IIS can register it.
</p>
<br />
<br />


<p>
<img src="https://i.imgur.com/DuhEkVT.png" height="50%" width="50%" alt="Reload IIS"/>
</p>
<p>
+ It's time to reload IIS with the new additions you've just made. Back to IIS' main page, click "Restart".
</p>
<br />
<br />


<p>
<p><h3>9. INSTALL osTICKET</h3>
</p>

<p>
<img src="https://i.imgur.com/JFUlEzg.png" height="50%" width="50%" alt="Install OsTicket"/>
</p>
<p>
<h4> You are now ready to install osTicket!</h4> 😀 </p>
<p> + Download and install it. Then, move its "Upload" folder to your local disk C:\inetpub\wwwroot.
+ Within C:\inetpub|wwwroot, rename "Uplaod" to "osTicket" (NO SPACE).
</p>
<br />
<br />


<p>
<img src="https://i.imgur.com/DuhEkVT.png" height="50%" width="50%" alt="Reload IIS"/>
</p>
<p>
+ It's time to reload IIS with the new additions you've just made. Back to IIS' main page, click "Restart".
</p>
<br />
<br />

<p>
<img src="https://i.imgur.com/KcYJpeB.png" height="50%" width="50%" alt="Launch osTicket"/>
</p>
<p>
+ It's time to launch osTicket! On IIS, to your left (see arrow), click on sites > Default > osTicket. </p>
<p>
+ Then, to your the right, locate and click "Browse *:80".
</p>
<br />
<br />


<p>
<img src="https://i.imgur.com/m6vwDWe.png" height="50%" width="50%" alt="osTicket missing extensions"/>
</p>
<p>
+ Here you are, in osTicket !!! Note that some extensions are not enabled. So we'll go back to IIS and enable them.
</p>
<br />
<br />


<p>
<img src="https://i.imgur.com/w0irABP.png.png" height="30%" width="30%" alt="Enabling .php extensions"/>
</p>
<p>
+ Back to IIS. Go to sites > Default > osTicket. Then, double-click on PHP Manager. You will see a list of both enabled and disabled .php extensions.
</p>
<p>
+ Enable: php_imap.dll; php_intl.dll; php_opcache.dll. See the "enable" in the example section below.
</p>
<br />
<br />


<p>
<img src="https://i.imgur.com/C10F5ch.png" height="40%" width="40%" alt="Enabling .php extensions"/>
</p>
<p>
+ Once you've enabled the missing extensions, refesh osTicket in your browser. </p>
<p>
+ Observe the changes.
</p>
<br />
<br />


<p>
<p><h3>10. RENAME "OST-SAMPLE CONFIG" FILE AND ASSIGN NEW PERMISSIONS TO "OST-CONFIG" FILE</h3>
</p>
<p>
<img src="https://i.imgur.com/UFYe11S.png" height="40%" width="40%" alt="Rename ost-sampleconfig to ost-config"/>
</p>
<p>
+ Now, it's time to rename your ost-sampleconfig.php file. </p>
<p>
+ In your local disk C:\inetpub\wwwroot\osTicket\includ\ost-sampleconfig.php, right-click on the file and rename it "ost-config".
</p>
<br />
<br />



<p>
<img src="https://i.imgur.com/Wthw0ZH.png" height="40%" width="40%" alt="Assign Permissions of ost-config.php"/>
</p>
<p>
+ At this stage, we can assign new permissions to our ost-config.php file we've just renamed. </p>
<p>
+ Right-click on the file > Properties > Security > Advanced. Then, "disable inheritance" > Remove All Permissions.
</p>
<br />
<br />


<p>
<img src="https://i.imgur.com/ZF0WQAB.png" height="40%" width="40%" alt="Assign Permissioms of ost-config.php"/>
</p>
<p>
+ Once you removed all inheritances, click on "Add" > Select a principal. Write "Everyone", then click on "Check Names". 
</p>
<br />
<br />

<p>
<img src="https://i.imgur.com/vRIITNZ.png" height="40%" width="40%" alt="Give full control to Everyone"/>
</p>
<p>
+ Give full control to the group "Everyone". Now, everyone has access to the file.
</p>
<br />
<br />


<p>
<p><h3>11. CONTINUE SETTING UP osTICKET IN THE BROWSER</h3>
</p>
<p>
<img src="https://i.imgur.com/ipN6Zhr.png" height="40%" width="40%" alt="Setting up osTicket in the browser"/>
</p>
<p>
+ Back to the osTicket page on your browser, click "Continue". You may now fill most information. 
<p>
+ The default email address is the one that receives emails from customers. DO NOT PRESS INSTALL, yet. We need more SQL information before proceeding.
</p>
<br />
<br />


<p>
<p><h3>12. INSTALL HeidiSQL.</h3>
</p>
<p>
<img src="https://i.imgur.com/2rpcY9P.png" height="40%" width="40%" alt="Download and Install Heidi SQL"/>
</p>
<p>
+ Download and install Heidi SQL. It provides a visual interface for managing and manipulating data in the database.
</p>
<br />
<br />


<p>
<p><h3>13. CREATE A NEW SESSION AND DATABASE IN HeidiSQL</h3>
</p>
<p>
<img src="https://i.imgur.com/HDEsVxB.png" height="40%" width="40%" alt="Create a new session Heidi"/>
</p>
<p>
+ Open Heidi SQL and click "New" (bottom left corner) to create a new seesion. Enter your password used for MySQL and connect to the session. 
</p>
<br />
<br />


<p>
<img src="https://i.imgur.com/UN2He83.png" height="40%" width="40%" alt="Create a database in Heidi"/>
</p>
<p>
+ Create a database called "osTicket". For this, right-click on the screen > create new > database. Name it "osTicket".
</p>
<br />
<br />



<p>
<p><h3>14. FINISH SETTIN UP osTICKET IN THE BROWSER</h3>
</p>
<p>
<img src="https://i.imgur.com/HrDrfYT.png" height="40%" width="40%" alt="Continuing osTicket set up"/>
</p>
<p>
+ Back to osTicket in your browser, you may not fill all the remaining SQL section. Then, click "Install Now!"
</p>
<br />
<br />

<p>
<p><h3>STEP 15. CONGRATULATIONS!</h3>
</p>
<p>
<img src="https://i.imgur.com/tvABRAz.png" height="40%" width="40%" alt="Congrats, you're in!"/>
</p>
<p>
<h4>CONGRATULATIONS, YOU MADE IT!</h4> 🥳
</p>
<p>
You can also clean up now by:</p>  
<p>+ 1. Deleting the following file: C:\inetpub\wwwroot\osTicket\setup </p>
<p>
+ 2. Setting new permissions to "Read Only" to your "ost-config.php": C:\inetpub|wwwwroot|osTicket\include\ost-config.php</p>
<br />
<br />


<p>
<img src="https://i.imgur.com/21dOAQT.png" height="50%" width="50%" alt="osTicket help desk page"/>
</p>
<p>
<h4> You may browse to your help desk login page: http://localhost/osTicket/scp/login.php </h4>
</p>
<br />
<br />


<P><H2>VOILÀ! 🤓 </H2></P>
