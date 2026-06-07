# 🔐 Password Strength Lab

> See exactly how strong a password is — and **why** — the way an attacker *and* a defender would measure it.

![Type](https://img.shields.io/badge/type-defensive_security-3fe08f)
![Stack](https://img.shields.io/badge/built_with-vanilla_JS-46d3ff)
![Privacy](https://img.shields.io/badge/privacy-100%25_client--side-7c8bff)
![License](https://img.shields.io/badge/license-MIT-lightgrey)

A single-file, fully client-side web app that scores password strength using real entropy math and the same heuristics password-cracking tools use — then teaches the concepts behind the score.

**🔗 Live demo:** `https://staticish.github.io/password-strength-lab/` *(enable GitHub Pages, see below)*

---

## ✨ Features

- **Effective entropy in bits** — `length × log₂(charset)`, then penalised for predictable patterns.
- **Crack-time estimates** at four real attacker speeds: throttled login (10/s) → leaked-DB GPU (10 B/s) → nation-state (100 T/s).
- **Pattern cracking logic** — detects breached words (even leet-spelled: `P@ssw0rd` → `password`), keyboard walks (`qwerty`), sequences, repeats, year suffixes, and the “Word + numbers + symbol” shape crackers try first.
- **Live strength meter** with verdict (Very weak → Excellent).
- **Secure passphrase generator** using `crypto.getRandomValues` (a CSPRNG) — 4 random words + a number.
- **100% private** — the password never leaves your browser.

## 🧠 How it works

Naïve strength meters only count character classes. This one models how cracking actually happens:

1. Compute raw entropy from length and character pool.
2. Run the candidate through dictionary / leetspeak / keyboard-walk / date checks.
3. **Subtract an entropy penalty** for each match — mirroring how `hashcat`/`John` shortcut the search with rules and wordlists.
4. Map the *effective* entropy to crack-time at several guessing rates.

The result demotes things like `Summer2024!` (looks complex, cracks fast) and rewards long passphrases.

## 🎓 What it demonstrates

Applied **authentication security**, **entropy/probability**, threat-actor cracking techniques, and secure RNG usage — and translating a technical concept into something non-technical users understand.

## ▶️ Run locally

Just open `index.html` in any browser. No build, no dependencies, works offline.

## 🚀 Deploy as a live demo (GitHub Pages)

Repo **Settings → Pages → Source: `main` / root → Save**. Your demo goes live at the link above.

## 📜 License

MIT © 2026 Ismail Olanrewaju
