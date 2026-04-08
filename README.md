# UX Analyzer

> AI-powered usability feedback tool. Describe any UI and instantly receive structured UX analysis grounded in psychology principles.

---

## Demo

![UX Analyzer Screenshot](./docs/screenshot.png)

> _Add a screenshot to `docs/screenshot.png` to display it here._

---

## Product Requirements Document (PRD)

### Overview

**Product Name:** UX Analyzer  
**Type:** Standalone web application  
**Stack:** HTML, CSS, Vanilla JavaScript  
**AI Provider:** OpenAI (GPT-4o Mini)  
**Status:** v1.0 — MVP

### Problem Statement

Designers, developers, and product managers often lack fast, accessible feedback on usability issues during ideation or early prototyping. Hiring a UX researcher is expensive and slow. UX Analyzer fills this gap by providing instant, psychology-backed usability analysis through a simple browser interface.

### Goals

- Enable any user to get structured UX feedback in under 30 seconds
- Make usability principles accessible to non-specialists
- Require zero setup — no build tools, no server, no accounts beyond an OpenAI API key

### Non-Goals

- Image or screenshot upload (future scope)
- Saving/exporting results (future scope)
- Multi-user accounts or persistent history

### Success Metrics

- User submits a UI description and receives a valid structured response
- Response is organized into three distinct, readable sections
- App functions entirely in the browser with no backend

---

## Epic

**"Instant UX Feedback for Everyone"**

Enable any person — regardless of UX expertise — to describe a user interface in plain language and receive actionable, psychology-backed usability analysis in seconds, directly in the browser.

---

## Description

UX Analyzer is a lightweight, no-install web app that acts as an on-demand UX researcher. A user describes a UI in plain text (e.g., *"a login page with small error messages and no password visibility toggle"*), clicks **Analyze UX**, and the app calls the OpenAI API with a structured prompt instructing it to:

1. Identify usability issues
2. Explain each issue using cognitive/psychological principles
3. Suggest concrete improvements

Results are rendered in three clearly labeled sections with visual hierarchy and iconography, making the output easy to scan and act on.

---

## Features

| # | Feature | Description |
|---|---------|-------------|
| 1 | **UI Description Input** | A resizable textarea for describing any interface in plain language |
| 2 | **API Key Field** | Secure password input for the user's OpenAI key — never stored or transmitted beyond the API call |
| 3 | **Analyze UX Button** | Primary CTA with visual weight; disabled and relabeled during loading |
| 4 | **Loading State** | Animated spinner with contextual text while awaiting the AI response |
| 5 | **Error Handling** | Inline error messages for empty input, missing API key, or API failures |
| 6 | **Issues Section** | Bulleted list of identified usability problems |
| 7 | **Psychology Explanation Section** | Each issue tied to a cognitive or UX psychology principle |
| 8 | **Improvements Section** | Concrete, actionable suggestions for resolving each issue |
| 9 | **Zero-dependency** | Runs directly in any modern browser — no build step, no server required |

---

## User Stories

### Epic: Instant UX Feedback for Everyone

---

**US-01 — Describe a UI**  
_As a_ designer or developer,  
_I want to_ describe a UI in plain text,  
_So that_ I can get feedback without uploading images or prototypes.

**Acceptance Criteria:**
- A textarea is present and focused on page load
- Placeholder text provides a helpful example
- Text is required before the analysis can be triggered

---

**US-02 — Authenticate with OpenAI**  
_As a_ user,  
_I want to_ enter my own OpenAI API key,  
_So that_ the app can call the AI on my behalf without needing a backend or account.

**Acceptance Criteria:**
- Input is a password field (key is masked)
- Key is only used in the request header and never stored
- An error is shown if the field is blank when the button is clicked

---

**US-03 — Trigger Analysis**  
_As a_ user,  
_I want to_ click a clearly labeled button to start the analysis,  
_So that_ I know exactly how to initiate the process.

**Acceptance Criteria:**
- Button reads "Analyze UX" by default
- Button changes to "Analyzing…" and becomes disabled while the request is in flight
- Button returns to its default state after the response is received

---

**US-04 — See a Loading State**  
_As a_ user,  
_I want to_ see a loading indicator while I wait for the AI response,  
_So that_ I know the app is working and haven't lost my input.

**Acceptance Criteria:**
- An animated spinner with the label "Analyzing your UI…" is shown during the request
- The spinner disappears once results or an error are displayed

---

**US-05 — View Structured Results**  
_As a_ user,  
_I want to_ see the AI's feedback organized into clear sections,  
_So that_ I can quickly understand the issues, their causes, and how to fix them.

**Acceptance Criteria:**
- Results are split into three sections: Usability Issues, Psychology Explanation, Suggested Improvements
- Each section has a distinct icon, title, and styled container
- Each section renders as a bulleted list

---

**US-06 — Handle Errors Gracefully**  
_As a_ user,  
_I want to_ see a clear error message if something goes wrong,  
_So that_ I know what happened and what to do next.

**Acceptance Criteria:**
- Empty description or API key shows an inline validation message
- API errors (bad key, rate limit, network failure) display the error message in a styled error box
- No raw JSON or stack traces are ever shown to the user

---

## Getting Started

1. Clone or download this repo
2. Open `index.html` in any modern browser
3. Describe a UI in the textarea
4. Paste your [OpenAI API key](https://platform.openai.com/api-keys)
5. Click **Analyze UX**

No installation. No build step. No account required beyond an OpenAI API key.

---

## Project Structure

```
ux-analyzer/
├── index.html       # Single-file app (HTML + CSS + JS)
├── docs/
│   └── screenshot.png  # Demo screenshot (add your own)
└── README.md
```

---

## License

MIT
