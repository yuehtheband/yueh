# YuëH Band Website

Hugo static site for the band **YuëH** (yuehtheband.com) — a post-hardcore trio from Paris ("SchrodingerMusclorPop").

## Stack

- **Generator**: Hugo (extended) with the Ananke theme (git submodule at `themes/ananke/`)
- **Hosting**: GitHub Pages, auto-deployed on push to `main` via `.github/workflows/hugo.yaml`
- **Config**: `config/_default/config.toml` (site settings) and `config/_default/params.toml`

## Local dev

```bash
# Pull theme submodule first
git submodule update --init

# Run dev server
hugo server --configDir ./config --cleanDestinationDir --gc
```

## Content structure

All content lives under `content/en/` (French is commented out):

| Section | File | Notes |
|---|---|---|
| Home | `content/en/_index.md` | Hero/landing |
| Bio | `content/en/bio/index.md` | Band description |
| Music | `content/en/music/index.md` | Discography (Bandcamp links) |
| Upcoming concerts | `content/en/concerts/index.md` | Future gig list |
| Past concerts | `content/en/concerts-past/index.md` | Archive with photos |
| Videos | `content/en/videos/` | |
| News | `content/en/news/` | |
| Contact | `content/en/contact/` | |

## Images

Static images live in `static/images/`:
- `band/` — band photos
- `concerts/` — one photo per concert gig
- `cover/` — album artwork
- `logo/` — band logo variants

Resize scripts are in `scripts/` (`script_resize.sh`, `script_resize_spread.sh`).

## Common tasks

**Add a past concert**: edit `content/en/concerts-past/index.md`, add a new entry at the top (most recent first), copy the concert photo to `static/images/concerts/`.

**Add an upcoming concert**: edit `content/en/concerts/index.md` similarly.

**Concert image naming convention**: `YYYYMMDD-venue-city.jpg` for dated entries (e.g. `20260425-auberge-artistes-paris.jpg`).

## Social links

Configured in `config/_default/config.toml` under `[params.ananke.social.*]`: Instagram, Facebook, YouTube, Bandcamp, Soundcloud, Spotify, Deezer.
