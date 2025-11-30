# Task 4 — Firewall Configuration on Kali Linux (UFW)

This repository contains my work for Task 4 of my internship:  
Managing and testing firewall rules on my Kali Linux PC using **UFW (Uncomplicated Firewall)**.

---

## 🖥 System Info
- OS: Kali Linux (Debian based)
- Firewall Tool: UFW
- Terminal used for all commands

---

## 🔧 Steps Performed 

### 1️⃣ Checked UFW Installation & Enabled Firewall
```bash
sudo apt install ufw
sudo ufw enable

Output confirmed: Firewall is active.

2️⃣  Listed Current Firewall Rules 
sudo ufw status numbered


This showed existing allow/deny policies (mostly default).

3️⃣ Blocked Inbound Traffic on Telnet Port 23
sudo ufw deny 23


This rule prevents Telnet attacks and unauthorized access attempts.

4️⃣ Tested the Rule
telnet localhost 23


Result:
⚠️ Connection refused → Rule successfully blocking port 23

5️⃣ Allowed SSH (Port 22)

(SSH is important for remote access)

sudo ufw allow 22/tcp


This ensures SSH remains working and not blocked.

6️⃣ Checked UFW Installation & Enabled Firewall

sudo ufw delete deny 23


Now Telnet port access is back to normal (not that I need Telnet 😅)

📌 Final UFW Status

(Screenshot is included inside screenshots/ folder in this repository)

Command used:

sudo ufw status verbose
