[![NEXUS COSMOS Banner](https://github.com/sahil-gaund03/cosmos/raw/main/public/images/hero-earth.png)](https://github.com/sahil-gaund03/cosmos/blob/main/public/images/hero-earth.png)

# ✦ NEXUS COSMOS

### *AI-Powered Space Intelligence Operating System*
> *The universe, decoded.*

[![Next.js](https://img.shields.io/badge/Next.js_16-000000?style=for-the-badge&logo=nextdotjs&logoColor=white)](https://nextjs.org/)
[![React](https://img.shields.io/badge/React_19-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://reactjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS_4-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)](https://tailwindcss.com/)
[![Three.js](https://img.shields.io/badge/Three.js-000000?style=for-the-badge&logo=threedotjs&logoColor=white)](https://threejs.org/)
[![Gemini AI](https://img.shields.io/badge/Gemini_API-8E75B2?style=for-the-badge&logo=google&logoColor=white)](https://deepmind.google/technologies/gemini/)
[![NASA API](https://img.shields.io/badge/NASA_API-0B3D91?style=for-the-badge&logo=nasa&logoColor=white)](https://api.nasa.gov/)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)
[![GitHub Stars](https://img.shields.io/github/stars/sahil-gaund03/cosmos?style=flat-square&color=gold)](https://github.com/sahil-gaund03/cosmos/stargazers)
[![GitHub Forks](https://img.shields.io/github/forks/sahil-gaund03/cosmos?style=flat-square&color=blue)](https://github.com/sahil-gaund03/cosmos/forks)

**[🚀 Live Demo](https://nexus-cosmos.vercel.app/)** · **[📸 Screenshots](#-screenshots--gallery)** · **[📖 Docs](#-installation)** · **[🤝 Contribute](#-contributing)**

---

## 🌌 What is NEXUS COSMOS?

**NEXUS COSMOS** is a full-stack space intelligence platform that fuses real-time NASA data streams, Gemini AI, and immersive 3D graphics into a single interface. It tracks the International Space Station in real time, renders the solar system in interactive 3D, retrieves live NASA imagery and space-weather data, and runs a Gemini-powered AI astronomy assistant — all in one cohesive UI.

Built on **Next.js 16**, **React 19**, **Three.js**, and **Framer Motion**.

---

## ⚡ Feature Showcase

**🤖 AI Astronomy Assistant**
- Powered by Google Gemini (`@google/genai`), streamed Markdown responses via `react-markdown` + `remark-gfm`
- JWT-secured API layer (`jose`) with input validation via `zod`
- Custom system prompt tuned for space-science context

**🪐 Interactive 3D Solar System**
- Full `Three.js` scene via `@react-three/fiber` + `@react-three/drei`
- Real planetary textures for all 8 planets, the Sun, and Saturn's rings
- Post-processing bloom/lens effects via `@react-three/postprocessing`
- Per-planet dossier HUD with orbital data

**🛰️ Real-Time ISS Tracker**
- Live ISS position, altitude, and orbital velocity telemetry
- Interactive map via `Leaflet` + `react-leaflet`
- Radar HUD overlay with animated telemetry readouts

**🌠 NASA Media Gallery**
- APOD (Astronomy Picture of the Day) hero display
- Searchable gallery with HUD-style filters and full-screen lightbox

**🚀 Launch Intelligence**
- Upcoming/past launch tracking for SpaceX, NASA, ISRO, and more, with countdown timers and launch-pad mapping

**🌩️ Space Weather Dashboard**
- Solar flare classification (X/M/C class), geomagnetic storm indices, aurora forecast data

**👩‍🚀 Astronaut Intelligence & 📅 Space Timeline**
- Current ISS crew manifest and mission histories
- Scrollable timeline of space milestones from Sputnik to Artemis

**🎨 Design System**
- Custom glass-morphism components (`GlassPanel`, `Badge`, `Button`, `TelemetryCard`)
- Fully responsive, mobile-optimized navigation
- Consistent design language across 9 platform modules

---

## 🛠️ Tech Stack

**Frontend:** Next.js 16 · React 19 · TypeScript
**3D/Graphics:** Three.js · @react-three/fiber · @react-three/drei · @react-three/postprocessing
**APIs & Data:** Gemini API (`@google/genai`) · NASA APIs · Open Launch API · Where the ISS At
**Styling/Animation:** Tailwind CSS 4 · Framer Motion 12 · clsx
**Maps & Markdown:** Leaflet + react-leaflet · react-markdown + remark-gfm
**Security:** jose (JWT) · zod (runtime validation)

---

## 🗂️ Project Architecture

```
cosmos/
├── public/
│   ├── images/          # Planet and nebula reference images
│   └── textures/planets/# Three.js UV texture maps
├── scripts/
│   └── download_textures.js
└── src/
    ├── app/              # Next.js App Router pages (home, ai-assistant,
    │                     # solar-system, iss-tracker, nasa-gallery,
    │                     # launches, space-weather, astronauts, timeline)
    │   └── api/          # chat (Gemini proxy, JWT-secured) + auth routes
    ├── components/       # ai, effects, gallery, home, launches, layout,
    │                     # solar, tracking, ui, weather
    ├── lib/
    │   ├── security/     # jwt.ts, validation.ts
    │   └── services/     # nasaService, solarService, launchService,
    │                     # astronautService, spaceWeatherService, timelineService
    └── middleware.ts     # Edge auth middleware
```

---

## 🚀 Installation

### Prerequisites
- Node.js ≥ 18.17, npm ≥ 9 (or pnpm/yarn)
- A NASA API key (free at [api.nasa.gov](https://api.nasa.gov))
- A Gemini API key (free at [aistudio.google.com](https://aistudio.google.com))

```bash
git clone https://github.com/sahil-gaund03/cosmos.git
cd cosmos
npm install
cp .env.example .env.local   # fill in your keys — see below
npm run dev
```

Open **http://localhost:3000**.

```bash
npm run build   # production build
npm start
```

---

## 🔐 Environment Variables

Create `.env.local` (never commit this file):

```
GEMINI_API_KEY=       # https://aistudio.google.com
NASA_API_KEY=         # https://api.nasa.gov (DEMO_KEY works, rate-limited)
JWT_SECRET=           # openssl rand -base64 32
API_PASSWORD=         # used by the login route to issue JWT tokens
```

> All keys are consumed server-side only via Next.js API routes/middleware and never shipped to the browser. The Gemini chat endpoint is JWT-protected.

---

## 📸 Screenshots & Gallery

> _Add real screenshots here (e.g. `public/images/` or a `docs/screenshots/` folder) once captured from a live deployment — hero, AI assistant, solar system, ISS tracker, and NASA gallery views all make good candidates._

---

## 🗺️ Roadmap

- [ ] Real-time 3D ISS orbit on the solar-system globe
- [ ] Voice-enabled AI assistant
- [ ] WebXR/VR solar system walkthrough
- [ ] Deep-space object catalog (exoplanets, nebulae, star clusters)
- [ ] Eclipse & transit predictor
- [ ] Mission builder for custom interplanetary trajectories
- [ ] Internationalization
- [ ] Personal space dashboard (favorites, launch alerts)
- [ ] PWA support

---

## 🤝 Contributing

```bash
git checkout -b feature/AmazingFeature
git commit -m "feat: add real-time ISS 3D orbit overlay"
git push origin feature/AmazingFeature
# then open a Pull Request
```

Follow the existing TypeScript-strict / Tailwind-utility style, keep components focused, and test both desktop and mobile viewports.

---

## 📄 License

MIT © 2026 Sahil Gaund — see [`LICENSE`](https://github.com/sahil-gaund03/cosmos/blob/main/LICENSE).

---

## 👨‍💻 Author

**Sahil Gaund** — *Full-Stack Engineer · AI/ML Engineer in training*

[![GitHub](https://img.shields.io/badge/GitHub-sahil--gaund03-181717?style=for-the-badge&logo=github)](https://github.com/sahil-gaund03)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-sahilgaund03-0A66C2?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/sahilgaund03)
[![Portfolio](https://img.shields.io/badge/Portfolio-sahilgaund0310.netlify.app-black?style=for-the-badge&logo=vercel)](https://sahilgaund0310.netlify.app)

---

### ✦ ALL SYSTEMS NOMINAL.
*Built for explorers of the universe.*

*© 2026 Sahil Gaund · MIT License*
