
<h1>Microsoft Sentinel SIEM Lab</h1>

 

<h2>Description</h2>
My goal was to learn how to take raw data from the Event Viewer in my VM and create a visual representation of that information so that it is easier to view the brute force attacks occuring on my machine.
<br />


<h2>Technologies Used</h2>

- <b>PowerShell</b> 
- <b>Azure Log Analytics Workspace</b>
- <b>Microsoft Sentinel</b>



<h2>Program walk-through:</h2>

<p align="center">
Create the Resources in Azure Portal. Add a rule to allow any traffic to the VM: <br/>
<img src="https://imgur.com/ncN7v5I.png" height="80%" width="80%" alt="Microsoft Sentinel SIEM Lab"/>
<br />
<br />
Turn off the firewall in the VM:  <br/>
<img src="https://imgur.com/B3e4bvM.png" height="80%" width="80%" alt="Microsoft Sentinel SIEM Lab"/>
<br />
<br />
I used a powershell script from Josh Madakor's tutorial and added my own API code to his script: <br/>
<img src="https://imgur.com/Th1gy1A.png" height="80%" width="80%" alt="Microsoft Sentinel SIEM Lab"/>
<br />
<br />
Run the script to see the failed logins grabbed from the Security Events. I failed 3 logins with a vfailtest user to test the script:  <br/>
<img src="https://imgur.com/L6OBaiE.png" height="80%" width="80%" alt="Microsoft Sentinel SIEM Lab"/>
<br />
<br />
The script automatically created a Failed file log:  <br/>
<img src="https://imgur.com/c9Dubra.png" height="80%" width="80%" alt="Microsoft Sentinel SIEM Lab"/>
<br />
<br />
Add a custom log to the Log Analytics Workspace in the Azure Portal. Add the path to the failed file log after adding the sample log:  <br/>
<img src="https://imgur.com/C4RlSKZ.png" height="80%" width="80%" alt="Microsoft Sentinel SIEM Lab"/>
<br />
<br />
Run a query with the failed logins file path created in the last step:  <br/>
<img src="https://imgur.com/eH2b9gO.png" height="80%" width="80%" alt="Microsoft Sentinel SIEM Lab"/>
<br />
Extract fields from the raw data (latitude, longitude, country, etc.). Tune the extraction if necessary, and then save: <br/>
<img src="https://imgur.com/SzNyVqZ.png" height="80%" width="80%" alt="Microsoft Sentinel SIEM Lab"/>
<br />
<br />
Create a workbook in Azure Sentinel. Add a query with the source host and edit the map settings:  <br/>
<img src="https://imgur.com/PLnDIHk.png" height="80%" width="80%" alt="Microsoft Sentinel SIEM Lab"/>
<br />
Edit the map settings:  <br/>
<img src="https://imgur.com/DuBaKlG.png" height="80%" width="80%" alt="Microsoft Sentinel SIEM Lab"/>
<br /> 
Apply the map settings and verify that the locations are accurate:  <br/>
<img src="https://imgur.com/ioZqrqv.png" height="80%" width="80%" alt="Microsoft Sentinel SIEM Lab"/>
<br /> 
<br />
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
