# Heroku artwork

Optional custom pictures used by the userbot. The code resolves them through
`heroku.utils.assets`, which looks in `assets/heroku/<name>` first and then in
the legacy `assets/<name>` location. **If a file is missing the media step is
simply skipped** – the text/action is still performed, nothing crashes.

All files must be placed **flat** in this folder (`assets/heroku/*.png`) –
`.gitignore` only whitelists this exact level.

## Expected files

| File                      | Used for                                                        | Status |
|---------------------------|-----------------------------------------------------------------|--------|
| `heroku.png`              | content channel avatar (falls back to `assets/heroku.png`)      | ✅ present (colour logo, 1000×1000) |
| `heroku-ava.png`          | inline bot profile photo                                        | ✅ present (recovered original, 1000×1000) |
| `updated.png`             | update notification                                             | ✅ present (recovered, 1150×500) |
| `unit_alpha.png`          | autoupdate / backup setup prompts                               | ✅ present (recovered, 3400×2000) |
| `heroku_started.png`      | startup badge posted to the logs chat                           | ⬜ missing |
| `presets_cmd.png`         | `/presets` menu                                                 | ⬜ missing |
| `start_cmd.png`           | bot `/start` and `/profile` replies                             | ⬜ missing |
| `heroku_cmd.png`          | heroku module info / help media (sent as a file)                | ⬜ missing |
| `heroku_installation.png` | installation guide (sent as a file)                             | ⬜ missing |
| `join_request.png`        | "join request" prompt sent by the bot                           | ⬜ missing |
| `declined_jr.png`         | "declined join request" inline message                          | ⬜ missing |
| `joined_jr.png`           | "joined channel" inline message                                 | ⬜ missing |

## Recovered originals (not wired to code)

Recovered from the deleted upstream repos and kept here as drawing references:

| File                | Original purpose                         | Size |
|---------------------|------------------------------------------|------|
| `heroku-assets.png` | assets/content channel avatar            | 1000×1000 |
| `heroku-backups.png`| backups channel avatar                   | 1000×1000 |
| `heroku-logs.png`   | logs channel avatar                      | 1000×1000 |

## Specs

- Bot profile photo (`heroku-ava.png`): square PNG, at least 160×160
  (Telegram rejects smaller avatars).
- Message banners: any aspect ratio; wide images (e.g. 1150×500) look best.
- Files sent as documents (`heroku_cmd.png`, `heroku_installation.png`) can be
  larger; keep them reasonably sized to avoid slow uploads.
- If an asset is missing, the corresponding media step is skipped and only the
  text is sent.
