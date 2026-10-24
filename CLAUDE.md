# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

A single-page personal site for "Вовчик", written in plain HTML and CSS: `index.html` + `style.css`, with no JavaScript, build step, package manager, linter or tests. All visible text and code comments are in Ukrainian (`lang="uk"`), so new content and comments should be in Ukrainian too.

## Running

Open `index.html` directly in a browser, or serve the folder with `python3 -m http.server` and visit http://localhost:8000.

## Structure

- Every section of the page is an anchor target (`#about`, `#tennis`, `#cube`, `#projects`, `#contacts`) linked from the sticky header nav. A new section needs an `id`, a nav link and a numbered `.section-title` (`<span class="num">05</span> …`) to match the others.
- `html { scroll-padding-top }` makes room for the sticky header (80px, or 100px under 640px where the nav wraps). Adjust it if the header height changes.
- The look comes from CSS custom properties on `:root`: the violet→blue gradient `--grad`, the glass card colors `--glass` and `--border`, and the fonts `--head` (Unbounded) and `--body` (Inter, loaded from Google Fonts). Reuse these instead of hard-coding colors. `.grad` applies the gradient to text.
- Building blocks: `.card` (glass panel with hover lift), `.grid` / `.grid-2` (auto-fit columns), `.btn-primary` / `.btn-ghost`.
- The starry background is the fixed `.sky` div, drawn entirely with CSS gradients on `::before`/`::after`. There are no image assets for it.
- Responsive rules live in one `@media (max-width: 640px)` block at the end of `style.css`, followed by a `prefers-reduced-motion` block that turns off the animations.

## Placeholder content

The markup contains `<!-- ЗАМІНИ: … -->` comments marking content that still needs filling in: tournament years/names, the project descriptions and the `href="#"` links. The tennis gallery uses `div.photo-slot` placeholders. To add a photo, put the file in `img/` (currently empty) and replace the slot with `<figure class="photo"><img src="img/….jpg" alt="…" loading="lazy"></figure>`.

## Мої правила

- Завжди відповідай мені українською.
- Перед великими змінами спочатку показуй план.
- Після змін коротко пиши, що змінив.
