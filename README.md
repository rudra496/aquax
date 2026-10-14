# AquaX — AI Water-Loss Intelligence for Bangladeshi Utilities

**Find every lost litre before it becomes lost revenue.**

AquaX helps water utilities in Bangladesh detect and act on Non-Revenue Water (NRW) —
water that is treated and pumped but never paid for. Built by **Team AquaX (SUST, Bangladesh)
for GP FutureMakers 2026, Round 2**.

- Landing site: [`index.html`](index.html)
- Demo application: [`app/index.html`](app/index.html) — one self-contained HTML file
  (no frameworks, no CDNs, no build step). Works offline from `file://` and on GitHub Pages.

## What it does

| Layer | Capability | Status |
|-------|------------|--------|
| 1 | **Billing anomaly detection** — risk-scores every connection from billing/consumption history, ranks flags by litres & revenue recoverable, explains each flag in plain language with a recommended field action | Working MVP (this repo) |
| 2 | **DMA flow & pressure anomaly detection** — night-flow analysis and pressure-drop signatures on district-metered-area SCADA streams | Year-2 design prototype (simulated demo in app) |
| 3 | **Sentinel-1 SAR leak mapping** — soil-moisture change detection along buried mains using free ESA Copernicus radar | Year 2–3 concept visualisation |

## Features in the demo app (`app/`)

- **Dashboard** — 200 deterministically generated accounts (seeded PRNG, identical on every
  load), KPI cards, ranked flag table with zone/status filters, per-account drawer with a
  6-month consumption sparkline, model stats and an "AI analyst assessment" generated from
  the account's actual numbers (with copy-to-clipboard).
- **Droplet AI assistant** — rule-based chat that answers **only** from the dataset
  (zone rankings, sudden-drop commercial accounts, revenue recovery at a user-set tariff,
  per-account summaries). It never invents numbers.
- **DMA Zone Monitor** — 12 simulated zones with 48-hour flow/pressure series and one marked
  night-flow anomaly (Layer-2 concept prototype).
- **Satellite SAR** — stylised city-grid map with three soil-moisture hotspots, confidence
  sizing, Sentinel-1 pass dates and inspect priority (Layer-3 concept).
- **What-If Recovery Simulator** — illustrative estimator: NRW %, detection coverage,
  verified recovery rate, production volume, tariff, AquaX share and household-equivalent
  output, plus a 36-month cumulative recovery-vs-cost chart with break-even marker.
- **Reports** — client-side CSV export of all flagged accounts and an A4 print summary.

## Honest disclaimer

> **Demonstration build.** The Layer-1 analysis engine, ranking logic, assessment generator
> and assistant are real and run entirely in your browser — but the dataset is **synthetic**,
> generated from a fixed seed for demonstration. KPI figures (200 accounts, 8 high-risk,
> 320,982 L/month, ৳4,813/month at ৳15/kl) are demo numbers carried over from the Round-1
> video for continuity. Layer 2 and Layer 3 are **design prototypes** on simulated data, not
> connected to any SCADA or satellite pipeline.

## Data sources cited on the landing page

- Dhaka WASA NRW 22%, Chattogram 31–35% — TBS News, Apr 2024
- Rajshahi WASA ~30% NRW — The Observer BD, Nov 2024
- Dhaka aquifer decline 2–3 m/yr — The Daily Star
- 2 billion people without safely managed drinking water — UNESCO/UN-Water, WWDR 2023
- DMA rollout context — UNB News
- Satellite leak-detection context — ASTERRA via Kurrant News, 2025

## Links

- Live demo (GitHub Pages): https://rudra496.github.io/aquax/
- Live demo (Lovable build, Round 1): https://aqua-x.lovable.app/
- Round-1 pitch video: _to be added before submission_
- GP FutureMakers 2026 — Round 2 Concept Pitch entry
- Contact: Team AquaX — SUST (rudrasarker125@gmail.com)

## Running locally

No build step. Either open `index.html` directly, or serve the folder:

```bash
python -m http.server 8080
# then visit http://localhost:8080 (app at /app/)
```

## License

MIT — see below.

```
MIT License

Copyright (c) 2026 Team AquaX — SUST, Bangladesh

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
