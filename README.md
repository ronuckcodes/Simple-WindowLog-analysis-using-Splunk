Windows Log Analysis with Splunk  
A beginner-friendly Splunk project analyzing Windows Event Logs (Security, System, Application) to detect anomalies like failed logins and suspicious activity.

 Key Features  
- Queries: Tracked failed (`EventCode=4625`) and successful (`EventCode=4624`) logons.  
- Alerts: Configured email alerts for multiple failed login attempts.  
- Observations:  
  - Detected brute-force attempts (Status `0xC000006D`).  
  - Recommended account lockout policies and PowerShell restrictions.  

 Setup  
1. Splunk Forwarding: Enable `WinEventLog://Security`, `System`, `Application`.  
2. Run Queries:  
   index=main sourcetype=WinEventLog:Security EventCode=4624
   index=main sourcetype=WinEventLog:Security EventCode=4625
