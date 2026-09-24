# Tally

Setup journal for the DRC indicator. Log every setup it prints (taken or not), mark how it resolved, and see the real hit rate by model, grade, hour, draw and version.

Single-file vanilla JS PWA. Data in localStorage, screenshots in IndexedDB (per device), optional encrypted Gist sync. Same family as Tape / Ledger / HQ.

## Deploy
1. New repo under ventra-ai-hub, e.g. `tally`. Push these files to `main`.
2. Settings > Pages > Deploy from branch > `main` / root.
3. Opens at ventra-ai-hub.github.io/tally. Add to Home Screen on the phone.

## Sync
Settings > paste a GitHub token with `gist` scope + a passphrase > Save & sync. It creates a secret gist and shows the ID. On the next device paste the same token, passphrase and that gist ID.

## Logging flow
- `+` (or `n` on desktop) opens the logger. Date, market, model, version and mode stick from the last one, so a replay day is fast.
- Entry / stop / TP → direction and planned R work themselves out.
- Leave outcome on Pending, then hit TP / SL / BE / No fill on the card when it resolves.
- Max R reached (MFE) is optional but it's the data that tells you whether TPs are too close or too far.

## Maths
- TP = planned R, SL = -1, BE = 0, No fill = excluded from win rate, counted in fill rate.
- R override replaces the result for partials or moved targets.
- "You vs the indicator" compares your actual R against the same setups at planned R (execution) and against every setup (selection).

## Export
Settings > Export CSV. That's the file to drop into Claude for analysis.
