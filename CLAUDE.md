# Lyka's Birthday Website — Dev Notes

## Branch policy
**Always commit and push directly to `main`.** Do not use feature branches. The live site deploys from `main`.

## Project overview
Single-file static site (`index.html`) with all CSS, HTML, and JS inline. Supporting pages: `globe.html`, `voice-note.html`, `birthday-voice-note.html`, `card.html`, `newspaper.html`, `excuses.html`, `upload.html`.

## Design tokens
- Fonts: Cormorant Garamond (serif/headings), Inter (sans-serif/body)
- `--rose: #c4727f` · `--rose-light: #e8a0aa` · `--rose-pale: #f5dde0`
- `--sage: #8a9a7b` · `--gold: #d4a574` · `--cream: #faf8f5`

## Key sections in index.html (approximate line order)
1. Gate / Scavenger Hunt (CSS ~1756, HTML ~1908, JS ~3062) — sequential 4-step unlock
2. Music Player (CSS ~1519, HTML ~5143, JS ~4288) — Supabase Storage sync
3. Photo Gallery (CSS ~1519, HTML after Wishes section) — 30-slot 4:3 grid
4. Bible Verses (CSS ~1519, HTML after Photos section) — 38 dated verse cards

## Supabase
- Bucket: `music`
- Constants at top of music player JS: `SUPABASE_URL`, `SUPABASE_KEY`, `BUCKET`

## Gate codes (STEPS config in gate JS)
- Key 1: `ILOVEYOU` (physical letter)
- Key 2: `Happy Birthday` (iMessage auto-reply)
- Key 3: `My Dearest Lyka` (iMessage auto-reply)
- Key 4 (multi): `Him` / `letter` / `too` (Valentine's website last words)
- All comparisons are case-insensitive (.toUpperCase())
