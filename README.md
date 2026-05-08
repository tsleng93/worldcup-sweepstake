# World Cup 2026 Sweepstake

A fair, self-contained sweepstake draw for the 2026 FIFA World Cup. No server, no dependencies — just a single HTML file you can open in any browser or host anywhere.

## How it works

The draw supports four group sizes:

| Participants | Teams each |
|---|---|
| 6 | 8 |
| 12 | 4 |
| 24 | 2 |
| 48 | 1 |

Fairness is enforced mathematically. For the 12-person draw (the core case): three random offsets `a`, `b`, `c` are drawn from 1–11. Each participant starts at a different group `N`, and their four teams come from groups `N`, `N+a`, `N+b`, `N+c` (mod 12). Because everyone shares the same offsets but starts at a different position, no two participants share a group — and everyone gets exactly one team from each rank tier (1st, 2nd, 3rd, and 4th place in their group). The 6- and 24-person modes are derived from this same logic.

## Prizes

Four prizes are built into the rules:

- 🥇 **Winner's prize** — whoever holds the team that wins the tournament
- 🥈 **2nd team prize** — whose 2nd-ranked team progresses furthest
- 🥉 **3rd team prize** — whose 3rd-ranked team progresses furthest
- 🏅 **4th team prize** — whose 4th-ranked team progresses furthest

Participants can win multiple prizes. Ties are broken by: how far the team progressed → penalties/extra time/normal time elimination → goal difference in that round → goals scored in that round → repeat for the previous round.

## Updating the teams

The default groups are based on odds of winning group as of 08/05/2026, to update these go to `index.html`:

```js
const GROUPS = {
  A: ["1st seed", "2nd seed", "3rd seed", "4th seed"],
  B: [...],
  // etc.
};
```

Or use the in-app editor (the "Edit team rankings" section) to adjust on the fly.

## Usage

Open `index.html` in any browser, or host it as a static site (GitHub Pages, Netlify, etc.).

## Licence

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) — free to use and adapt for your own sweepstake, with attribution.
