# HR KPI Dashboard · Panel de KPIs de RR. HH.

**Live:** https://sops-hr-kpis.vercel.app

A single-page dashboard for tracking monthly People / HR KPIs against targets. English and Spanish, no login, no database.

*Panel de una sola página para seguir mensualmente los indicadores de RR. HH. frente a sus objetivos. En inglés y español, sin registro y sin base de datos.*

## What it tracks

| KPI | How it's calculated |
|---|---|
| Headcount | Headcount at end of month |
| Turnover rate | Total leavers ÷ average headcount × 100 |
| Voluntary turnover | Voluntary leavers ÷ average headcount × 100 |
| Time to hire | Average days from vacancy opened to offer accepted (entered directly) |
| Absenteeism rate | Hours absent ÷ hours scheduled × 100 |
| eNPS | % promoters (9–10) − % detractors (0–6) |
| Training hours / employee | Total training hours ÷ average headcount |

Average headcount = (start of month + end of month) ÷ 2. Month-on-month changes in rates are shown in **percentage points (pp)**, not percent.

## How to use it

1. Open the live link and click **Load sample data** to see it working, or go straight to **Add a month**.
2. Enter the raw monthly totals. The dashboard calculates the rates.
3. Under **Targets**, set a goal per KPI. Cards show ✓ / ✗ against it, and the trend chart draws it as a dashed line.
   - Turnover, time to hire and absenteeism targets are **maximums**. eNPS and training hours targets are **minimums**. Headcount is a **plan**, so the gap is shown without judging it good or bad.
4. Switch language with **EN / ES** in the top-right corner.

## Where the data lives

Everything you enter is stored in **your own browser** (`localStorage`). Nothing is sent to a server.

- Someone else opening the link sees an empty dashboard, not your numbers.
- Clearing your browser data, or using a private window, loses it. Use **Export data (.json)** regularly as a backup, and **Import data** to restore it or move it to another computer.

## Data protection

Enter **aggregated figures only**, never names or individual records. In small teams, even totals can identify a person (for example, one leaver in a team of four), so think about that before sharing screenshots or exports (GDPR / LOPDGDD).

When calculating absenteeism, decide once which absences count and stay consistent. A common approach is to include temporary incapacity (sick leave) and exclude holidays and paid statutory leave such as birth leave (art. 37 Estatuto de los Trabajadores).

## Tech

A single static `index.html` (HTML, CSS and vanilla JS) with no build step and no dependencies apart from the Inter font from Google Fonts. It's deployed on Vercel, and every push to `main` redeploys automatically.

To run it locally, open `index.html` in a browser.
