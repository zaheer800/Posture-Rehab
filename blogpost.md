# How I Deployed a Website Without Touching My Laptop — Using Claude Code

*Published March 15, 2026*

---

I hurt my leg. Nothing dramatic — just the kind of nagging pain that builds up when you spend too much time sitting at a desk and not enough time moving. The physio gave me a 5-day recovery plan with a list of exercises, stretches, and rest rules. I had a printed sheet of paper. I wanted something better.

So I decided to build a proper recovery tracker — a clean, interactive web page I could actually use on my phone. The catch? I didn't want to open my laptop. My leg hurt, I was on the couch, and I had my phone.

That's when I reached for **Claude Code on the web**.

---

## Starting From Zero, On My Phone

I opened a browser, started a Claude Code session, and described what I wanted:

> *"Build me a 5-day leg recovery routine as a web page with exercises, timers, and a way to track progress."*

No terminal. No VS Code. No file explorer. Just a conversation.

Claude Code got to work. It created `index.html` — a fully self-contained page with:

- A **day-by-day exercise plan** with sets, reps, and rest periods
- **Inline SVG illustrations** for each exercise (so no broken image links)
- **YouTube tutorial links** for every move, right there in the card
- **Checkboxes** to tick off exercises as I completed them, with strikethrough styling
- A **built-in countdown timer** so I didn't have to switch apps
- A **day selector** with visual progress — buttons turned green as I marked days done
- Local storage so my progress **persisted between sessions**

It even added a big red reset button for when I wanted to start fresh. The whole thing looked polished — cards, shadows, a clean blue-and-white design, mobile-friendly layout.

I reviewed it in the chat. It looked exactly right.

---

## From Conversation to Live Website

Here's the part that genuinely surprised me.

Claude Code didn't just write the code. It:

1. **Created a GitHub Actions workflow** that automatically deploys to GitHub Pages whenever a push is made to the branch
2. **Pushed everything to a feature branch** on my GitHub repo
3. The workflow ran, the `gh-pages` branch was updated, and GitHub Pages served the site

I asked: *"Is the updated page published?"*

Claude Code checked the GitHub Actions run status via the API and confirmed:

> *"Yes — the updated page is published. Both the deploy job and the Pages build completed successfully."*

The whole thing — from idea to live URL — happened while I was sitting on the couch, phone in hand, leg elevated.

**I never opened my laptop. I never typed a terminal command. I never touched a file.**

---

## What Made This Work

A few things stood out about the experience:

**Claude Code understood context, not just commands.** I didn't have to specify file names or directory structures. I described what I wanted and it made reasonable decisions — a single `index.html` with embedded CSS and JS, no build step needed, no dependencies.

**It handled real-world problems on its own.** When external image URLs broke, it switched to inline SVGs without me asking. When the initial deployment config didn't work correctly, it fixed the GitHub Actions YAML and pushed again.

**The feedback loop was instant.** Every change went straight to the repo and triggered the deployment pipeline. There was no "let me set up my environment" friction.

**It was genuinely autonomous.** Not autocomplete. Not a code suggestion. It planned, wrote, iterated, committed, and deployed — all from a conversation.

---

## The Result

A clean, mobile-first **5 Day Leg Recovery Tracker** live on GitHub Pages. I've been using it every morning. The timer keeps me honest. The checkboxes feel satisfying to tick. The progress buttons turning green is weirdly motivating.

I built it from my phone, on my couch, with a sore leg.

That's the part I keep thinking about. The barrier to going from *"I have an idea"* to *"this is live on the internet"* is now just... a conversation.

---

*Built with Claude Code. Deployed to GitHub Pages. Couch-tested.*
