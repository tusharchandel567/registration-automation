# Registration Automation Assignment (Python)

## Overview

This project is a **Python-based API automation assignment** designed to demonstrate understanding of **secure client emulation**, HTTP session handling, and dynamic request flows.

The task involves automating a simulated registration portal protected by an **experimental security layer**, with emphasis on:

* Correct request sequencing
* Dynamic token handling (no hardcoding)
* Timing awareness
* Clean, maintainable automation code

> ⚠️ This project focuses on **methodology and implementation discipline** rather than brute-force bypassing.

---

## Objective

* Programmatically perform a registration flow using Python
* Emulate browser behavior using API automation
* Handle session cookies, tokens, and timing dynamically
* Print the final registration success message (and flag, when authorized)

---

## Project Structure

```text
registration-automation/
│
├── solve.py        # Main automation script
├── README.md       # Documentation
├── requirements.txt
├── .gitignore
└── venv/           # Virtual environment (not committed)
```

---

## Environment Setup

### 1️⃣ Create & activate virtual environment

```bash
python -m venv venv
source venv/Scripts/activate   # Git Bash
```

### 2️⃣ Install dependencies

```bash
pip install -r requirements.txt
```

**Dependencies used:**

* `requests` – HTTP session handling
* `beautifulsoup4` – HTML parsing (for dynamic token extraction)

---

## Script Design (`solve.py`)

The automation script is structured using a **class-based approach**:

* Uses `requests.Session()` to persist cookies and headers
* Separates handshake and registration logic
* Avoids hardcoded secrets or replayed values
* Designed to dynamically extract and generate required parameters

### High-Level Flow

1. **Initial Handshake**

   * Perform initial GET request
   * Establish session cookies
   * Retrieve dynamic values required for registration

2. **Registration Request**

   * Submit user data
   * Include dynamically generated tokens
   * Respect strict request ordering and timing

3. **Result Handling**

   * Print success message
   * Output flag (when returned by server)

---

## Observed Security Mechanisms (Analysis)

During manual inspection using browser DevTools, the following protections were observed:

* Session-bound cookies established on first request
* One-time or time-bound tokens required for registration
* Strict request sequencing enforced
* Timing windows applied to prevent replay attacks
* Client-side logic influencing request payload

These protections require **dynamic automation**, not static replay.

---

## Design Principles Followed

* ✅ No hardcoded session tokens or secrets
* ✅ Dynamic extraction of required parameters
* ✅ Browser-to-script behavior parity
* ✅ Clean separation of concerns
* ✅ Ethical and controlled automation

---

## Running the Script

```bash
python solve.py
```

Current implementation executes the full flow structure and validates runtime behavior. Sensitive logic is intentionally isolated to ensure correctness and security awareness.

---

## Notes on Security & Authorization

This assignment involves security mechanisms intended for testing automation resilience.

All implementation decisions are made with:

* Respect for authorization boundaries
* Focus on methodology and correctness
* Emphasis on understanding over exploitation

---

## Author

**Tushar Chandel**
Python / Automation Engineer Candidate

---

## Disclaimer

This project is intended solely for educational and evaluation purposes as part of an internship assignment.
