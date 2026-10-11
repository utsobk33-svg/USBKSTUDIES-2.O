# USBKSTUDIES-2.O
AI Powered learning system

USBKStudies V20.2 — Utsab AI Learning System
Files
index.html: single-page responsive frontend, served by Express
server.js: API, auth, data persistence, AI provider gateway, study endpoints
package.json: Node dependencies
.env.example: variable names only; no secrets
.gitignore: excludes secrets and dependencies
render.yaml: Render deployment blueprint
Deploy
Create a PostgreSQL database in Render.
Create a Web Service connected to this repository.
Build command: npm install; Start command: npm start.
Set DATABASE_URL using the database's Internal Database URL (same Render region).
Ensure JWT_SECRET is a long random value (Render may generate one).
Configure Grow AI only using its current official documentation: GROW_API_KEY, GROW_API_BASE_URL, GROW_API_ENDPOINT, and GROW_API_MODEL. Do not guess provider URLs/models.
Deploy and open /api/health.
Included modules
Student/Teacher auth; notes; flashcards; library; chat history; study planner; revision tasks; knowledge concepts; exam/mistake log; AI chat; study-pack generation; practice-question generation; optional web-search gateway; voice input/output via browser support; camera/gallery/image and file picker; PDF selectable-text extraction; chat-history search; local question bank; calculator; focus timer; print-to-PDF; dashboard; settings; founder project log.
Important boundaries
AI endpoints require a compatible provider configured in Render and may incur charges.
Search is only live when a documented search provider is configured in WEB_SEARCH_*; otherwise the UI clearly says it is not connected.
File selection is local and text extraction is limited in the browser; image analysis requires a Grow-compatible vision model; selectable-text PDF extraction uses PDF.js loaded from a CDN, scanned PDFs may need OCR, and DOC/DOCX extraction is not built in.
Password-reset email/SMS delivery requires a mail/SMS provider. This starter exposes no fake reset delivery.
Browser speech recognition, text-to-speech, printing and notifications depend on browser/device support.
This is a substantial starter project, not a promise that every feature is production-ready without testing. Review security, backups, provider terms, privacy, and costs before public launch.
Feature coverage note
This package includes the previously discussed module structure except AI video generation. Some integrations require the matching provider: Grow AI model compatibility, vision support for image analysis, a live-search API, and a verified email/SMS service for password-reset delivery. The Question Bank and Founder Dashboard currently use browser local storage, not shared PostgreSQL persistence.