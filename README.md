# Market Pulse — Sector Breadth Dashboard

A Stockbee-style market breadth dashboard with live TradingView charts, sector breadth (% above MA5/20/50/100/200), index breadth, 52-week highs/lows, and a quarterly Market Monitor.

**Live site:** https://xdeerizx.github.io/market-pulse-dashboard/

## How it updates

Data refreshes 3x per trading day from a Perplexity Computer scheduled task:

- **9:30 AM EDT** — morning refresh (pre-open snapshot)
- **12:00 PM EDT** — midday update
- **4:15 PM EDT** — close update

Each run computes fresh breadth values, writes `index.html` (data embedded inline), commits, and pushes. GitHub Pages auto-rebuilds (~30 sec).

## Data sources

- **Breadth & history:** `finance_analyst` parquet pulls (sector/index constituents, OHLC)
- **Live perf (client-side):** TradingView scanner API — called directly from the browser for per-ticker returns
- **Charts:** TradingView advanced chart, embedded via `s.tradingview.com/widgetembed/`

## Local dev

```
open index.html
```

That's it — it's a single-file app. No build, no backend required for viewing.
