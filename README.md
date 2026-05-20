# YART-Tent (yart-tent.onrender.com)

## About

YART-Tent is a single-page editorial site for a workshop that has been building and repairing truck tarps, sliding curtain systems, steel frames and PVC products in Krasnodar & Rostov-on-Don since 2014

The layout leans on a workshop-blueprint aesthetic — caution stripes, monospaced metadata captions, a navy/safety-yellow palette and oversized display type — instead of the usual round-corner SaaS look that every tarp shop on the south coast already uses

---

<img width="1902" height="992" alt="image" src="https://github.com/user-attachments/assets/58fa3bd8-3e9e-489c-8833-2ae1d28aab31" />

---

## Tech stack

- **HTML5** — semantic sectioning, one file
- **CSS3** — custom properties, `clamp()` fluid type, CSS grid, scroll-triggered classes
- **Vanilla JS** — sticky header shadow + `IntersectionObserver` reveal, no framework, no bundler
- **Google Fonts** — Unbounded (display), Onest (body), JetBrains Mono (captions)
- **Yandex Maps Constructor** — external map embed, no API key needed

No npm, no build, no preprocessor — just open `index.html`

---

## Run locally

Clone the repo and open the file — there is no install step

```bash
git clone https://github.com/vgartg/YART-Tent.git
cd YART-Tent
```

Then either:

- double-click `index.html`, or
- serve the folder with any static server, e.g.

```bash
python -m http.server 8080
# then visit http://localhost:8080
```

---

## Demo watermark

The repo currently ships with a diagonal `vgartg.ru` watermark used to protect the demo build from being copied 1:1 before client delivery

It lives in two places — a CSS block at the bottom of [assets/css/style.css](assets/css/style.css) and a watchdog script [assets/js/demo-guard.js](assets/js/demo-guard.js) that re-injects the styles if anyone tries to disable them via DevTools

To ship the site to the client, remove:

1. the `DEMO WATERMARK` block at the end of `assets/css/style.css`
2. the file `assets/js/demo-guard.js`
3. the `<script src="assets/js/demo-guard.js" defer></script>` line from `index.html`
