# 🚨 Breaking Down a Job Scam: An OSINT Investigation into Ascenno HR

## 📌 Introduction
In this investigation, I analyze a fraudulent job offer from **Ascenno HR**, a fake company attempting to scam job seekers. Using **OSINT (Open Source Intelligence)**, I uncover multiple red flags proving this operation is deceptive. This report is meant to educate others on how to spot and handle job scams.

---

## 🔍 Step 1: How the Scam Works
I received an unsolicited email from "Michael" at Ascenno HR, claiming I had applied for a Virtual Assistant position on LinkedIn via Zoho Recruit. However, I never applied for such a position, indicating this was an attempt to **phish for personal information**.

### 🚩 Red Flags in the Email:
- ❌ No interview process before offering the job.
- ❌ Vague recruiter identity (no last name, generic greeting).
- ❌ False claim that I applied through Zoho Recruit.
- ❌ Generic, templated language, likely **AI-generated**.

📸 *[Fake Acceptance Email](https://drive.google.com/file/d/1cTe8rF4AOpqDtRmj3KpZrf05Qvexxyhu/view?usp=sharing)*

---

## 🌐 Step 2: Domain & Website Analysis
A **WHOIS lookup** of the domain **ascenno.com** revealed critical inconsistencies:
- 📅 **Registered on:** January 1, 2025 (Yet claims to be in business for 2+ years).
- 🏢 **Hosting Provider:** IONOS SE, Germany.
- 🔒 **TLS Certificate:** Issued on January 2, 2025.

📸 **[WHOIS Lookup](https://drive.google.com/file/d/15Dyai66-netjfScMJd9TxkBvk6WLUf6Z/view?usp=drive_link)**

A **BuiltWith analysis** shows the site is built using a basic **WordPress template** with common plugins, often seen in scam websites trying to appear legitimate.

📸 **[BuiltWith Analysis](https://drive.google.com/file/d/1xPHy72ixahmgSWGJIbDlPAqfc-94O7ta/view?usp=drive_link)**

A scan via **URLScan.io** shows minimal external links, reinforcing that this is a hastily built scam website.

📸 **[URLScan.io Results](https://drive.google.com/file/d/1OgeYeskLQZnwJaEyhbi9eeV1KTszsRj8/view?usp=drive_link)**

---

## 🕵️ Step 3: Network & DNS Investigation
A **DNS lookup** using MXToolbox confirmed:
- 🌍 **IP Address:** 212.227.172.254 (IONOS SE, Germany).
- ❌ No legitimate business registration linked to the domain.
- 🔗 **Connected domains** indicate potential links to other fraudulent operations.

📸 **[MXToolBox Results](https://drive.google.com/file/d/17p7Q0cepyIqHoIDJeBevb0cfdn3wiukc/view?usp=drive_link)**

---

## 🔐 Step 4: Legal Vulnerability Scanning & Security Posture Analysis
To further analyze the security of the scam website, I conducted **passive OSINT-based vulnerability scanning** using legal and ethical methods.

### 🛠️ Tools Used:
- **Shodan.io** → Checked for open ports, services, and misconfigurations.
- **Censys.io** → Analyzed certificates and exposed endpoints.
- **SecurityTrails.com** → Retrieved historical DNS and subdomain data.
- **Nikto** → Scanned for outdated software and misconfigurations.
  ```bash
  nikto -h www.ascenno.com
  ```
- **WhatWeb** → Identified technologies used and potential vulnerabilities.
  ```bash
  whatweb www.ascenno.com
  ```
- **Google Dorking** → Checked for exposed admin panels and sensitive files.
  ```plaintext
  site:ascenno.com intitle:"Admin Login"
  site:ascenno.com filetype:txt OR filetype:log
  ```
- **Nmap** → Scanned for open ports (without exploitation).
  ```bash
  nmap -Pn -sV -p- www.ascenno.com
  ```

### 🚨 Key Findings:
- ❗ **Outdated WordPress plugins**, posing known security risks.
- ❗ **Multiple open ports**, indicating **weak security configurations**.
- ❗ No **Web Application Firewall (WAF)** detected, making it vulnerable.
- ❗ **Exposed admin login panels**, which could be targeted by brute-force attacks.

---

## 🚨 Step 5: Reporting & Awareness
If you come across scams like this, report them to prevent others from being targeted:
- 🔗 **[Google Safe Browsing: Report a Phishing Site](https://safebrowsing.google.com/safebrowsing/report_phish/)**
- 🔗 **[FTC (USA): Report Fraud](https://reportfraud.ftc.gov/)**
- 🔗 **[IC3 (FBI Internet Crime Center): Report Cybercrime](https://www.ic3.gov/)**
- 🔗 **[IONOS (Domain Registrar): Report Abuse](https://www.ionos.com/terms-gtc/complaints)**

---

## 📚 Lessons Learned: How to Spot Job Scams
✅ **Verify domain registration history (WHOIS).**  
✅ **Check for inconsistencies in job offers.**  
✅ **Use OSINT tools (Nmap, BuiltWith, Shodan).**  
✅ **Be cautious of unsolicited job offers requiring no interview.**  
✅ **Use legal vulnerability assessment tools to evaluate security risks.**

---

## 🎯 Conclusion
This investigation highlights the importance of **OSINT in cybersecurity and job scam prevention**. By staying informed and using verification tools, we can better protect ourselves and others from fraudulent schemes.
