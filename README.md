# 🔐 The Cipher Bureau — Caesar Cipher Encryptor / Decryptor

An interactive Caesar cipher tool that goes beyond basic encrypt/decrypt — it also **cracks ciphertext without a key** using letter-frequency analysis, and visualizes the shift on a live cipher wheel.

![status](https://img.shields.io/badge/status-complete-brightgreen) ![type](https://img.shields.io/badge/type-single--file%20HTML-blue) ![license](https://img.shields.io/badge/license-MIT-lightgrey)

## 🎯 Why this project

Most Caesar cipher demos stop at "shift the letters." This one demonstrates *why* the cipher is considered insecure — by breaking it live, in the browser, with no key provided.

## ✨ Features

| Feature | What it shows |
|---|---|
| **Encrypt / Decrypt** | Classic shift cipher (1–25), preserves case, leaves punctuation/numbers/spaces untouched |
| **Live Cipher Wheel** | SVG visual that rotates to show the letter mapping for the current shift key |
| **Crack Without a Key** | Runs all 25 possible shifts and ranks them using chi-squared scoring against standard English letter frequency — no key required |
| **Session Log** | Tracks every encode/decode performed in the session |
| **Field Notes** | Explains the cryptography concepts behind each part of the tool |

## 🧠 How the auto-crack works

English text has a predictable letter distribution (E, T, A, O, N appear most often). The tool:
1. Decrypts the ciphertext under all 25 possible shift values
2. Scores each result against expected English letter frequencies (chi-squared test)
3. Ranks shifts by how closely the output resembles real English
4. The lowest-scoring (best-matching) shift is almost always the correct key

This is a live demonstration of why single-alphabet substitution ciphers like Caesar's are considered cryptographically weak — the tiny key space (only 25 options) makes brute-force + frequency analysis trivial.

## 🛠️ Tech stack

Pure HTML, CSS, and vanilla JavaScript — no frameworks, no build step, no dependencies. Open `index.html` in any browser.

## 🚀 Run it

```bash
git clone https://github.com/<your-username>/cipher-bureau.git
cd cipher-bureau
open index.html   # or just double-click the file
```

## 📁 Project structure

```
cipher-bureau/
├── index.html      # everything: markup, styling, cipher + crack logic
└── README.md
```

## 📚 Key concepts demonstrated

- Encryption/decryption logic (modular arithmetic on the alphabet)
- Handling edge cases (case sensitivity, non-letter characters)
- Basic cryptanalysis (frequency analysis, chi-squared scoring)
- Why key-space size determines cipher strength

## 📄 License

MIT — free to use, modify, and learn from.

---
*Part of a personal cybersecurity fundamentals series.*
