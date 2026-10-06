# Dynasty Trade Calculator

A one-page dynasty trade calculator that averages values from several free sites, with Sleeper roster fit and trade grades.

## How the pieces fit

- **GitHub** stores the files and runs `update_values.py` every morning. The script pulls fresh numbers from KeepTradeCut, FantasyCalc, RotoWire and the FantasyPros trade value chart, then saves them to `values.json`.
- **Netlify** hosts the app. The page reads `values.json` straight from GitHub each time it opens, so the daily updates show up without Netlify redeploying anything.
- Netlify redeploys only when the app itself changes. That keeps you inside the free plan, which allows about 20 deploys a month before it pauses the site.

## Files

- `index.html`: the app.
- `values.json`: the latest values from each site.
- `update_values.py` and `.github/workflows/update-values.yml`: the daily updater that runs on GitHub.
- `netlify_build.py` and `netlify.toml`: tell Netlify where to find the daily values, and to skip deploys when only the values changed.
