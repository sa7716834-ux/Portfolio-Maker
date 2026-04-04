# PortfolioForge

> **AI-powered portfolio builder for developers** — Fill a form, generate a polished HTML portfolio, download in seconds.

---

## Overview

PortfolioForge is a fully client-side, zero-dependency web application that lets developers build and download a complete personal portfolio website in minutes. No backend required. No frameworks. Just open the file and start building.

Users fill out a guided 5-step form, optionally enhance their content with AI writing tools, choose from 3 professional templates, and download a clean, self-contained HTML file ready to deploy anywhere.

---

## Features

- **Guided 5-Step Builder** — Structured flow: Personal Info → Skills → Projects → Template → Generate
- **AI Writing Assistant** — Auto-generate your bio, suggest relevant skills, and improve project descriptions using AI
- **3 Professional Templates** — Midnight (dark minimal), Terminal (hacker CLI), and Gradient Pro (vibrant modern)
- **Live Dashboard** — Manage multiple portfolios per account, re-download at any time
- **Client-Side Auth** — Local account system with sign up / log in (data stored in `localStorage`)
- **One-Click Download** — Generates a clean, portable `index.html` with zero external dependencies
- **Animated Canvas Background** — Particle network animation rendered on `<canvas>` for visual depth
- **Fully Responsive** — Works on desktop, tablet, and mobile
- **No Build Step** — Pure HTML, CSS, and vanilla JavaScript. Open and run instantly

---

## Demo

Click **"View Demo"** on the landing page to preview a pre-filled portfolio rendered with the Midnight template — no account needed.

---

## Getting Started

PortfolioForge requires no installation, no npm, no build tools.

**Option 1 — Open directly in browser**
```bash
# Just open the file
open index.html
```

**Option 2 — Serve locally (recommended for development)**
```bash
# Python
python -m http.server 8000

# Node.js
npx serve .

# VS Code
# Use the Live Server extension
```

Then visit `http://localhost:8000` in your browser.

---

## How It Works

```
User fills form  →  AI enhances content  →  Template applied  →  HTML generated  →  Download
```

1. **Sign up** with a name, email, and password (stored locally in your browser)
2. **Fill the builder** across 5 steps — personal details, skills, projects, and template selection
3. **Use AI tools** to auto-generate your bio, suggest skills based on your job title, or improve project descriptions
4. **Generate** — the app assembles your portfolio into a complete HTML document in ~3 seconds
5. **Download** — save the `.html` file and deploy it anywhere

---

## Templates

| Template | Style | Font | Color Scheme |
|---|---|---|---|
| **Midnight** | Dark · Minimal | Segoe UI / system-ui | GitHub dark palette — `#58a6ff` accent |
| **Terminal** | Hacker · CLI | Courier New / Fira Code | Black background, `#00ff41` green |
| **Gradient Pro** | Vibrant · Modern | Inter / Helvetica Neue | Indigo-to-cyan gradient, deep purple base |

All generated portfolios include a sticky nav, hero section, skills display, project cards with GitHub/live demo links, education block, contact section, and footer.

---

## Project Structure

```
portfolioforge/
└── index.html          # Entire application — UI, logic, and HTML generator
```

PortfolioForge is intentionally a single-file application. All CSS, JavaScript, and markup live in `index.html` for maximum portability.

---

## AI Features

The AI tools run in **demo mode** by default — responses are locally simulated with realistic delays and pre-written variations. No API key is required to use them.

| Tool | Trigger | What It Does |
|---|---|---|
| **AI Generate Bio** | Step 1 — About Me | Writes a professional bio based on your name, title, and experience |
| **AI Suggest Skills** | Step 2 — Skills | Suggests relevant tech skills based on your job title |
| **AI Improve Description** | Step 3 — Projects | Rewrites a project description to be more professional and impactful |

To connect a real LLM, replace the `delay()` + static response logic in the `aiGenerateBio()`, `aiSuggestSkills()`, and `aiImproveDesc()` functions with your API calls.

---

## Data & Privacy

All data is stored exclusively in your browser's `localStorage`. Nothing is sent to any server. Clearing your browser storage will erase all accounts and portfolios.

| Storage Key | Contents |
|---|---|
| `pf_users` | Registered user accounts (name, email, hashed-equivalent password) |
| `pf_current` | Currently logged-in user session |
| `pf_portfolios_<email>` | All portfolios for a given user |

> **Note:** This is a demo-grade auth system. Do not store sensitive passwords. For production use, replace `localStorage` auth with a proper backend.

---

## Deploying Your Generated Portfolio

Once you download your `.html` portfolio file, you can deploy it for free on any of these platforms:

**GitHub Pages**
```bash
git init && git add . && git commit -m "Portfolio"
git remote add origin https://github.com/yourusername/yourrepo
git push -u origin main
# Enable Pages in repo Settings → Pages → Deploy from branch
```

**Netlify**
Drag and drop your file (or folder) at [netlify.com/drop](https://netlify.com/drop) — live in seconds.

**Vercel**
```bash
vercel deploy
```

**Any web host** — Upload the `.html` file to any static hosting provider. It has zero dependencies.

---

## Customization

To extend or modify PortfolioForge, all logic is in clearly commented sections within `index.html`:

| Section | What to Edit |
|---|---|
| `themes` object in `generateHTML()` | Add or modify template color schemes |
| `generateHTML()` function | Change the structure of the generated portfolio |
| `aiGenerateBio()` etc. | Swap demo mode for real AI API calls |
| `:root` CSS variables | Modify the builder app's own design system |
| `templates-grid` HTML | Add new template cards to the UI |

---

## Browser Support

| Browser | Support |
|---|---|
| Chrome 90+ | ✅ Full |
| Firefox 88+ | ✅ Full |
| Safari 14+ | ✅ Full |
| Edge 90+ | ✅ Full |

Requires `localStorage`, `Canvas API`, `CSS custom properties`, and `Blob` / `URL.createObjectURL` — all available in all modern browsers.

---

## Roadmap

- [ ] Connect real AI API (OpenAI / Claude) for live bio and description generation
- [ ] Add image/screenshot upload for project cards
- [ ] Export as `.zip` with separate `index.html`, `style.css`, and `assets/` folder
- [ ] Additional templates (Glassmorphism, Brutalist, Resume-style)
- [ ] Custom color/font picker per template
- [ ] PDF export of portfolio
- [ ] Backend sync for cross-device access

---

## Contributing

Contributions are welcome! To get started:

1. Fork the repository
2. Make your changes in `index.html`
3. Test across major browsers
4. Open a pull request with a clear description of your changes

Please keep the zero-dependency, single-file architecture unless proposing a major structural change via an issue first.

---

## License

MIT License — free to use, modify, and distribute. See [`LICENSE`](./LICENSE) for details.

---

## Acknowledgments

- Fonts: [Syne](https://fonts.google.com/specimen/Syne), [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono), [DM Sans](https://fonts.google.com/specimen/DM+Sans) via Google Fonts
- Inspiration: GitHub's dark theme, Linear's design system, Vercel's dashboard aesthetic

---

<div align="center">
  Built with PortfolioForge · Made for developers, by developers
</div>
