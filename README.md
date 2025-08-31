# Kill Chain and MITRE ATT&CK 

1. Summary of Hutchins et al. (2011)
   - The article explains the idea of the Intrusion Kill Chain, which shows the steps attackers usually take in a cyberattack.
   - The kill chain has seven stages:
     a. Reconnaissance- collecting information about the target.
     
     b. Weaponisation- creating malicious file or tool.
     
     c. Delivery- sending the file, e.g. through email or website.
     
     d. Exploitation- running the malicious code on the victim's system.

     e. Installation- installing malware or backdoors to stay in the system.

     f. Command and Control- connecting back to the attacker's server.

     g. Actions on Objectives- stealing data damaging systems, etc.
     
   - The key idea is that defenders can stop the attack at any of these steps, not only at the end.
 
   - The paper also highlights that attackers often work in longer campaigns, not just single actions.

My thought: If defenders only focus on one step (like blocking delivery), attackers may put more effort into earlier stages, such as better reconnaissance. Defence should cover all steps, not just one.

3. Tactics, Tools and Procedures
     - Tactic: the goal of the attacker at a certain step. Example: Credential Access (trying to steal usernames and passwords).
       
     - Technique: the method used to achieve goal. Example: Brute Force (repeatedly trying different passswords).
    
     - Subtechnique: a more detailed version of a technique. Example: Password Guessing (T1110.001) guessing common passwords.
    
     - Procedure: how it looks in real life. Example: Running the Hydra tool with a password list to break into an SSH account.

This framework helps turn abstract ideas about attacks into clear, real examples that defenders can spot and block.

4. Short Attack Story
   - Reconnaissance: The attacker scans for open SSH ports with nmap.

     Defence: IDS alerts the admin about scanning.
     
   - Initial Access: They try to brute-force weak SSH passwords.

     Defence: Account lockout stops them after multiple wrong tries.

   - Execution: They upload and run a malicious shell script.

     Defence: Endpoint monitoring blocks suspicious outbond traffic.

   - Persistence: They add their SSH key to stay inside the system.

     Defence: Security team notices an unknown key.

   - Exfiltration: They attempt to copy stolen files out with SCP.
  
     Defence: Firewall blocks traffic to an untrusted server.

  Result: The attack was detected and blocked before data was lost.

## References

Hutchins, E., Cloppert, M. & Amin, R. (2011). Intelligence-Driven Computer Network Defense Informed by Analysis of Adversary Campaigns and Intrusion Kill Chains. Lockheed Martin. Available at: https://www.lockheedmartin.com/content/dam/lockheed-martin/rms/documents/cyber/LM-White-Paper-Intel-Driven-Defense.pdf

MITRE ATT&CK (2025). MITRE ATT&CK® FAQ – General. Available at: https://attack.mitre.org/resources/faq/

   
   
