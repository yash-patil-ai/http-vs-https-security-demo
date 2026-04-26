# 🔐 HTTP vs HTTPS — Interactive Security Demo Dashboard

> **Mini Project 4** — A fully interactive, single-file web application that visually demonstrates the difference between HTTP and HTTPS security, real-world hacker attacks, cloud data storage, and security headers — with live animations and simulations.

---

## 🚀 Live Demo

Open `http_vs_https_with_cloudstore.html` directly in any browser — **no server, no install, no dependencies.**

---

## 📸 Preview

| Tab | What It Shows |
|-----|--------------|
| 🔴 Live Demo | Type real data → watch HTTP expose it vs HTTPS encrypt it |
| 📋 Overview | Side-by-side HTTP vs HTTPS protocol comparison |
| 💥 Attack Demos | Wireshark sniffing, Burp Suite tampering, Cookie hijacking |
| ☠️ Hacker Attack Types | 8 attack vectors with code examples and defenses |
| ☁️ Cloud Storage | How AWS / GCP / Azure store data securely |
| 🗃️ Cloud Data Store | Interactive DB simulation — store data via HTTP or HTTPS |
| 🛡️ Security Headers | All 7 security headers explained with HTTP vs HTTPS comparison |

---

## ✨ Features

### 🔴 Live Interactive Demo
- Enter your own name, email, password, card number, CVV, and amount
- Watch the **HTTP packet** display your data in plain text — exactly as Wireshark would capture it
- Watch the **HTTPS packet** show only AES-256-GCM encrypted ciphertext
- **Hacker Terminal** reveals what an attacker on the same WiFi network would steal
- **Database Storage** comparison shows plain-text vs hashed/masked storage

### ☁️ Cloud Data Store — Interactive Simulation
- Choose between **Google Firestore**, **AWS DynamoDB**, or **Azure Cosmos DB**
- Click **"Store via HTTP"** → see credentials travel in plain text, stored unhashed
- Click **"Store via HTTPS"** → see TLS handshake, bcrypt hashing, AES-256 at-rest encryption
- Animated step-by-step **data pipeline**: Browser → TLS → Load Balancer → Server → Cloud DB
- Three live panels: **In Transit**, **Server Processing**, **Cloud DB JSON Record**
- **Records Table** tracks all simulated entries with color-coded protocol badges

### ☠️ Hacker Attack Types (8 Attacks Documented)
- Man-in-the-Middle (MITM)
- Credential Sniffing via Wireshark
- Session Cookie Hijacking
- SSL Stripping / Protocol Downgrade
- Parameter Tampering via Burp Suite
- DNS Spoofing + HTTP Hijack
- Cross-Site Scripting (XSS)
- Clickjacking & CSRF

### 🛡️ Security Headers Reference
Complete table of all 7 HTTP security headers with values, HTTP vs HTTPS status, and purpose.

---

## 🗂️ Project Structure

```
http-vs-https-security-demo/
│
├── http_vs_https_with_cloudstore.html   ← The entire project (single file)
└── README.md                            ← This file
```

> The entire project is a **single self-contained HTML file** — all CSS, JavaScript, and content are inline. No frameworks, no build tools, no npm.

---

## 🛠️ Tech Stack

| Technology | Usage |
|-----------|-------|
| **HTML5** | Structure and semantic layout |
| **CSS3** | Custom properties, Grid, Flexbox, animations |
| **Vanilla JavaScript** | All interactivity — zero dependencies |
| **JetBrains Mono** | Monospace font for packet/code displays |
| **Syne** | UI font for headings and labels |

> Both fonts load from Google Fonts CDN. The project works offline except for font rendering (falls back to system monospace/sans-serif).

---

## 🏃 How to Run

### Option 1 — Just open it
```bash
# Clone the repo
git clone https://github.com/YOUR_USERNAME/http-vs-https-security-demo.git

# Open in browser
open http_vs_https_with_cloudstore.html       # macOS
start http_vs_https_with_cloudstore.html      # Windows
xdg-open http_vs_https_with_cloudstore.html  # Linux
```

### Option 2 — Local server (optional)
```bash
# Python
python -m http.server 8080

# Node.js
npx serve .

# Then open: http://localhost:8080
```

---

## 🎯 What You Learn

| Concept | Covered In |
|---------|-----------|
| Why HTTP is dangerous on public WiFi | Live Demo + Attack Demos |
| How TLS 1.3 encrypts data | Live Demo (HTTPS Packet view) |
| What Wireshark actually captures | Hacker Terminal tab |
| How bcrypt password hashing works | Live Demo (DB Storage tab) |
| What cloud data stores are | Cloud Data Store tab |
| How AWS S3, Firestore, Cosmos DB differ | Cloud Storage tab |
| What HSTS, CSP, X-Frame-Options do | Security Headers tab |
| How MITM, SSL Stripping, CSRF attacks work | Hacker Attack Types tab |

---

## 🔒 Security Concepts Demonstrated

```
Browser Input
     │
     ├─── HTTP ──────────────────────────────────────────────────►  ⚠ EXPOSED
     │    Plain text POST body                                        Wireshark sees everything
     │    password=admin123 & card=4111...                           Attacker steals credentials
     │
     └─── HTTPS ─── TLS 1.3 Handshake ─── Encrypted Tunnel ──────►  ✓ PROTECTED
          AES-256-GCM ciphertext                                      Random bytes — unreadable
          a4 f2 9c 3b 8e 1d 7a 52...                                 Math impossible to reverse
                                    │
                                    ▼
                             Server Processing
                             bcrypt(password) → hash
                             mask card → ****1111
                             CVV → never stored
                                    │
                                    ▼
                            Cloud Data Store
                            AES-256 at rest (KMS)
                            Geo-replicated
                            Audit logged
```

---

## 📋 All 7 Security Headers Covered

| Header | Protects Against |
|--------|-----------------|
| `Strict-Transport-Security` | SSL Stripping, Protocol Downgrade |
| `Content-Security-Policy` | XSS, Code Injection |
| `X-Frame-Options` | Clickjacking |
| `X-Content-Type-Options` | MIME Sniffing |
| `X-XSS-Protection` | Reflected XSS |
| `Referrer-Policy` | Information Leakage |
| `Set-Cookie: Secure; HttpOnly; SameSite` | Cookie Theft, CSRF |

---

## ☁️ Cloud Providers Simulated

| Provider | Services Shown |
|----------|---------------|
| 🟠 **AWS** | S3, RDS, DynamoDB, ElastiCache, Glacier |
| 🔵 **GCP** | Firestore, Cloud SQL, BigQuery, GCS, Memorystore |
| 🔷 **Azure** | Cosmos DB, Blob Storage, Azure SQL, Table Storage, Data Lake |

---

## 👨‍💻 Author

**Mini Project 4** — Web Security Concepts  
Built with pure HTML, CSS, and JavaScript — no frameworks needed.

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## ⭐ If this helped you understand web security better, give it a star!

```
git clone https://github.com/YOUR_USERNAME/http-vs-https-security-demo.git
```
