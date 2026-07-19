# Uzum Market Seller Manual — Markdown Mirror

An unofficial, **auto-updated Markdown mirror** of the official **Uzum Market seller manual**
(<https://seller.uzum.uz/manual/>), in **every available language** — Russian and Uzbek.

## Why this repo exists

The official manual is excellent content, but it is hard to actually *use* as data:

- **You can't download it.** It's a client-rendered VuePress single-page app sitting **behind
  Yandex SmartCaptcha**. A normal `curl` / `wget` / crawler is redirected to a `showcaptchafast`
  verification page, so the text is unreachable to scripts, search engines, LLMs and RAG pipelines.
- **There is no public source.** The docs' original repository is private or deleted. (We actually
  went looking — the trail started from a warehouse render hosted on
  `user-images.githubusercontent.com` embedded in section 1.2 — but nothing behind it is public.)
- **It changes silently.** Tariffs, requirements and deadlines get edited over time with **no
  changelog**, so there's no way to see *what* changed or *when*.

This repository fixes all three by keeping a clean, **diff-able, versioned, plain-Markdown** copy of
every page, in every language, refreshed **every hour**. That makes the manual easy to:

- read offline or in your editor,
- feed to LLMs / RAG / full-text search,
- **track over time** — every content change becomes a single git commit you can diff.

## Structure

```
ru/   Russian manual   — 15 sections (01_… … 15_…)
uz/   Uzbek (Oʻzbekcha) — 15 sections (01_… … 15_…)
```

Files are named in the manual's own section order. Images point at their original
`https://seller.uzum.uz/...` URLs, so they render without any extra hosting.

## How it stays up to date

An **n8n workflow runs once an hour**. Because of the SmartCaptcha, it renders each page in a
**headless browser (Puppeteer)** rather than a plain HTTP request, converts the resulting HTML to
Markdown, compares it against what's already in this repo, and **commits only the files that actually
changed** — with a commit message listing which sections were updated. Hours with no changes produce
no commit.

## Source & attribution

- **Source:** <https://seller.uzum.uz/manual/>
- All manual content is **© Uzum Market**. This is an **unofficial community mirror** created purely
  for readability and change-tracking. It is **not affiliated with, nor endorsed by, Uzum**. If you
  represent Uzum and would like changes or removal, please open an issue.

---

_Initial snapshot generated 2026-07-19. Languages: RU, UZ. Sections per language: 15._
