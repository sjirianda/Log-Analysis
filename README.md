# 🚨 Log Analysis
Threat Hunting with Elastic SIEM 🔍

## 🎯 Objective
Differentiate between true positives and false positives.  
- Decode suspicious powershell script using CyberChef.

### 🧠 Skills Gained
- Understanding of SIEM concepts and practical application.
- Proficiency in analyzing and interpreting network logs.
- Ability to generate and recognize attack signatures and patterns.
- Development of critical thinking and problem-solving skills in cybersecurity.

### 🔧Tools Utilized

- Elastic SIEM: For log ingestion and advanced analysis.
- CyberChef: The ultimate tool for de-obfuscation and decoding.

## 🚀 Step-by-Step Guide
1. The alert occurred on Dec 1st, 2024, between 0900 and 0930. We can set this as our time window by clicking the timeframe settings in the upper-right corner. 
![image](https://github.com/user-attachments/assets/49ef2d9e-d919-4c99-8a5f-1fca321fef2a)

2. Since we are looking for events related to PowerShell, we can customize the fields to see pertinent information.We can see that someone ran the same encoded PowerShell command on multiple machines.
![image](https://github.com/user-attachments/assets/01c519d1-8faa-4a04-ae5a-0f9ec50df3b3)

3. The logs show that someone tried a brute-force attack on December 1st. Once they succeeded with the brute-force attempt because of the successful authentication attempt they quickly ran some PowerShell commands on the affected machines.
![image](https://github.com/user-attachments/assets/5be97473-009d-4d6c-809a-c1936eff56ff)
   
4. Since the powershell command is encoded its important to use a tool like CyberChef to determine its contents. To use this tool type the text to the input and add operations to the recipe to display the output. In this case I used FromBase64 and Decode text.![image](https://github.com/user-attachments/assets/9316c6bd-83f6-4417-95e5-9cc475daad37)

5. Based on these findings it looks like an administrator was trying to login to outdated machines and used a powershell script to update them.

 ## 🔑 Key Takeaways
- Accurate analysis of logs is crucial for distinguishing between benign admin activity and potential malicious actions.  
- Tools like Elastic SIEM and CyberChef empower analysts to uncover hidden insights and validate alerts effectively.  
