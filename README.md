Cyber Security Internship – Task 1: Local Network Port Scanning

## Objective:
Learn to discover open ports on devices in your local network using **Nmap**, understand which services are exposed, and identify potential security risks.

---

## Tools Used:
- **Nmap v7.97**
- Terminal (macOS)
- Local network: `192.168.1.0/24`

---

## Steps Performed:

### 1. Installed Nmap
Installed Nmap using Homebrew: `brew install nmap`
Verified installation with: `nmap --version`

### 2. Found Local IP Address
Used the command: `ipconfig getifaddr en0`
Got output: 192.168.1.6 → So network range was considered as 192.168.1.0/24.

###  3. Host Discovery
Command: `nmap -sn 192.168.1.0/24`

### 4. Service Scan on a Specific Host
Command: `nmap -sV 192.168.1.5`

### 5. Full Output Scan
Command:`nmap -sT 192.168.1.0/24 -oN ~/Desktop/scan_results.txt`
Scanned full network and saved result to a file.

| File               | Description                         |
| ------------------ | ----------------------------------- |
| `scan_results.txt` | Full TCP scan output on the network |
| `screenshots/`     | Step-by-step terminal screenshots   |
| `README.md`        | Complete explanation of the task    |


###Key Observations:
IP: 192.168.1.1
Open Ports: 21 (FTP), 22 (SSH), 23 (filtered Telnet), 53 (DNS), 80 (HTTP), 443 (HTTPS)

Risk: FTP and Telnet are outdated and insecure protocols. Their presence can pose vulnerabilities.

IP: 192.168.1.3
Status: All scanned ports closed

IP: 192.168.1.5
Filtered Port: 1272 (cspmlockmgr)

Note: Port is filtered — not enough info about running service.

IP: 192.168.1.6 (My System)
Open Ports: 88 (Kerberos), 445 (SMB), 5000 (UPnP), 7000 (AFS)

Security Insight:

SMB (port 445) and UPnP (port 5000) are known attack targets.

If unused, these services should be firewalled or disabled.


###Key Concepts Learned:
How to scan a network using nmap -sS and nmap -sT
What open ports reveal about devices/services
How to find your local IP and subnet range
Basic network reconnaissance and risk analysis
Saving scan output to .txt using -oN

###Outcome:
Developed foundational cybersecurity skills including network mapping, port scanning, and threat awareness, crucial for ethical hacking and security auditing.




