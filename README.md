# MTA-STS Policy for svailsa.com

This repository hosts the **MTA-STS (Mail Transfer Agent Strict Transport Security)** policy for `svailsa.com`.

## 📌 Purpose

MTA-STS helps secure email transport by enforcing **TLS encryption** for SMTP connections. This prevents attackers from intercepting or downgrading email security.

## 📁 Hosted Policy Location

The MTA-STS policy must be accessible at:

```
https://mta-sts.svailsa.com/.well-known/mta-sts.txt
```

## 🚀 Deployment Instructions

1. Clone this repository:
   ```sh
   git clone https://github.com/YOUR_USERNAME/mta-sts-svailsa.git
   ```
2. Navigate into the directory:
   ```sh
   cd mta-sts-svailsa
   ```
3. Ensure the `.well-known/` folder exists:
   ```sh
   mkdir -p .well-known
   ```
4. Add or update the `mta-sts.txt` policy file inside `.well-known/`:
   ```plaintext
   version: STSv1
   mode: enforce
   max_age: 604800
   mx: svailsa.com
   ```
5. Commit and push the changes:
   ```sh
   git add .
   git commit -m "Updated MTA-STS policy"
   git push origin main
   ```
6. Verify the file is accessible:
   ```sh
   curl -I https://mta-sts.svailsa.com/.well-known/mta-sts.txt
   ```
   Expected response:
   ```http
   HTTP/2 200
   ```
