# TWLO Price (Advanced)

Static site that shows the **Twilio (TWLO)** price, a **Market Open/Closed** badge, and **Day / Week / Month** trend charts.

## Files
- `index.html` — UI using Chart.js (via CDN)
- `data/price.json` — latest price
- `data/history.json` — rolling time series (last 2000 points)
- `.github/workflows/update-price.yml` — fetches price every 5 minutes and updates JSON

## Setup
1. Create a public GitHub repo and upload these files.
2. Add a repo secret in **Settings → Secrets and variables → Actions**:
   - Name: `FINNHUB_API_KEY`
   - Value: your Finnhub API key
3. Enable **GitHub Pages** (Settings → Pages → Deploy from a branch → `main` → `/ (root)`).
4. Run the workflow once manually (Actions → *Update TWLO price* → Run workflow).

## Notes
- Market status uses weekday & 09:30–16:00 America/New_York; it does not include US market holidays.
- Charts populate after the first successful workflow writes `history.json`.
