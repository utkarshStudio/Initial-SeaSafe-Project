# 🌊 SeaSafe — Captain's Copilot

**Decision support at the helm.** A local-first, AI-powered maritime route intelligence console built for **Buildathon 2026** by **Team TryHard**.

🔗 **Live demo:** [seasafe-three.vercel.app](https://seasafe-three.vercel.app)
📦 **Repo:** [github.com/utkarshStudio/-SeaSafe](https://github.com/utkarshStudio/-SeaSafe)

---

## The Problem

95% of India's trade moves by sea — roughly **$1T** in value and **915 million tonnes** of cargo every year. Yet a single disruption can be catastrophic: the Red Sea crisis cut import/export volume by **75%**, and Panama Canal draft restrictions slashed throughput by **50%**, adding 36+ hours of transit per vessel.

India sits at the crossroads of four of the world's most fragile chokepoints — **Strait of Hormuz, Bab-el-Mandeb/Red Sea, Malacca/Singapore, and Panama** — and today, a captain's reroute decision is stitched together from scattered email advisories, broker calls, weather PDFs, and gut instinct.

## The Solution

SeaSafe puts real-time route intelligence directly on the bridge — one pane combining a live map, an AI orchestrator, a quantified decision card, a five-axis trade-off radar, and a compliance HUD. **No paid LLM. No API key. No setup.**

## Core Features

| Feature | Description |
|---|---|
| **5 Built-in Scenarios** | Red Sea, Hormuz, Panama, Malacca, Cyclone — replayable and demo-deterministic |
| **Custom Scenario Builder** | Vessel + ports + severity → a full live voyage synthesized in under 30 seconds |
| **AI Orchestrator** | Streamed tool calling across 5 tools (chokepoint status, weather hazards, route metrics, route comparison, port congestion) — every step shown with arguments and latency |
| **Decision Card** | Recommended route + 2 alternatives, each with quantified deltas: ±hours ETA, ±USD cost, ±tonnes CO₂ |
| **Factors Radar** | Five-axis trade-off view — Risk, Cost, Carbon, Speed, Reliability — overlaid on one chart |
| **Compliance Mode** | Jurisdiction-aware, forward-only display masking across 4 regimes — India DPDP, EU GDPR, UAE FDPL, IMO/SOLAS — auto-rebinding at every zone transition |

## Why It's Different

- **Show your work, not magic.** Every AI recommendation streams its tool calls in real time, so the captain sees the *why*, not just the *what*. A deterministic fallback keeps the app usable even if the local model goes offline.
- **Decide on data, not gut.** Every route comes with quantified deltas vs. the current course. Captains can override the AI — every override is logged as an auditable **Captain's Call**.
- **Compliance as a legal moat.** Vessel position is treated as personal data. SeaSafe enforces a forward-only legal display window (100–200 nm look-ahead, 0–48h disposal) driven by the jurisdiction the vessel currently sits in.

## Tech Stack

- **Framework:** Next.js 16, React 19, TypeScript
- **Mapping:** MapLibre GL, deck.gl, react-map-gl
- **Routing:** searoute-js (real sea-lane geometry, not straight-line)
- **State:** Zustand
- **AI:** OpenAI-compatible tool-calling orchestrator with local/deterministic fallback
- **UI:** Tailwind CSS v4, shadcn/ui, Base UI

## Getting Started

```bash
git clone https://github.com/utkarshStudio/-SeaSafe.git
cd BlockSeBlock_codex_Hackathon
npm install
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) — no environment variables or API keys required.

## Project Structure

```
app/              Next.js app router pages & API routes
components/       UI, map, and bridge console components
lib/
  scenarios/      Built-in crisis scenario JSON (Red Sea, Hormuz, Panama, Malacca, Cyclone)
  compliance/     Jurisdiction masking engine, zones, vessel clock
  weather/        Hazard detection & reroute logic
  radar/          Five-axis trade-off scoring
  tools/          AI orchestrator tool definitions
  seaRoute.ts      Real sea-lane route generation (searoute-js)
```

## Team

**TryHard** — Buildathon 2026.

---

*Bring data to the bridge.*
