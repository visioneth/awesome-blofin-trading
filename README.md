# Awesome BloFin Trading

A curated list of resources, tools, strategies, and edges for trading perpetual futures on BloFin.

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![X Follow](https://img.shields.io/twitter/follow/Vision33X?style=social)](https://x.com/Vision33X)

---

## Contents

- [Official Resources](#official-resources)
- [Copy Trading](#copy-trading)
- [Proven Edges](#proven-edges)
- [API and Tools](#api-and-tools)
- [Fee Structure](#fee-structure)
- [Community](#community)

---

## Official Resources

- [BloFin Exchange](https://blofin.com) - Main exchange
- [BloFin API Documentation](https://docs.blofin.com) - Full REST and WebSocket API reference
- [BloFin Python SDK](https://github.com/blofin/blofin-sdk-python) - Official Python client

---

## Copy Trading

BloFin copy trading lets you follow lead traders automatically. Your account mirrors their positions in real time.

**Vision33X** - Current record: 88% win rate, 25 trades. Strategy: RSI extremes at institutional kill zones. SHORT bias. No overnight holds. Tight ATR-based stops on every trade.

Use code **Vision33X** when signing up on BloFin for VIP fee discounts.

---

## Proven Edges

These are the edges that have survived real trading, not just backtests.

**Kill Zones** - Recurring time windows where institutional flow creates predictable direction bias. 20:00 UTC SHORT has produced 98.4% win rate across 65 trades. Full data: [crypto-kill-zones repo](https://github.com/visioneth/crypto-kill-zones)

**RSI Extremes** - Mean reversion works at genuine extremes, not moderate levels.
- SOL RSI below 10: LONG, 67.6% win rate
- BTC RSI above 90: SHORT, 66.7% win rate
- DOGE RSI above 90: SHORT, 65.6% win rate
- SOL RSI fades below 30: 50% win rate, avoid this

**Funding Rate Edge** - When funding is deeply negative, the market is paying you to hold shorts. Current March 2026 environment: deeply negative across the board.

**What Does Not Work** - SOL intraday RSI fades: 50% WR. XRP any direction: 37.6% WR. High leverage with fixed percentage stops: gets eaten by candle noise every time.

---

## API and Tools

- [claude-crypto-prompts](https://github.com/visioneth/claude-crypto-prompts) - The exact Claude prompts used for live trade decisions
- [crypto-kill-zones](https://github.com/visioneth/crypto-kill-zones) - Kill zone analysis with full backtested data
- [V33X-RSI-Scanner](https://github.com/visioneth/V33X-RSI-Scanner) - Real-time RSI extreme scanner across 360+ pairs
- [V33X-Whale-Shield](https://github.com/visioneth/V33X-Whale-Shield) - Multi-chain whale movement tracker
- [V33X-Pine-Scripts](https://github.com/visioneth/V33X-Pine-Scripts) - Free TradingView strategies (RSI Extreme, EDGE, Webhook)

**Contract sizes on BloFin (common mistake area):**
BTC = 0.001 per contract. ETH = 0.01. SOL = 1. XRP = 100. DOGE = 1000. Using wrong sizes is how people accidentally size 100x larger than intended.

**API notes for builders:**
Copy trading endpoints live at /api/v1/copytrading/ which is a completely separate path from main account endpoints at /api/v1/trade/. They use the same auth format but different base paths. Most unofficial wrappers only cover the main account.

---

## Fee Structure

BloFin VIP tiers change the math on every trade.

VIP0: Maker 0.02% / Taker 0.06%
VIP5: Maker 0.00% / Taker 0.035%

At 25x leverage, the difference between maker and taker fees is whether a strategy is profitable or not. At VIP5 maker, you pay nothing to enter. At VIP0 taker, you pay 0.12% round trip. On a 1% TP that is 12% of your profit gone to fees.

---

## Community

- [@Vision33X on X](https://x.com/Vision33X) - Daily market reads, kill zone alerts, trade setups
- [BloFin Official X](https://x.com/BloFin_Official) - Exchange announcements and updates

---

---

## March 3, 2026 — New: Funding Farm Signals

Added to the Beast Pack today: automatic funding rate extreme detection.

When funding exceeds 10 percent per 8h on BloFin perpetuals, the system auto-generates FIRE signals:
- LONG signal when funding is negative (shorts paying longs)
- SHORT signal when funding is positive (longs paying shorts)
- Score 7.0 to 9.5 based on rate magnitude
- Deduped daily, logged to signal history

Today live: POWER -47 percent funding per 8h. Executor in signal-only mode.

Resources:
- BloFin funding rates: app.blofin.com
- CoinGlass funding data: coinglass.com
- BloFin copy trading: partner.blofin.com/d/Vision33X



Star this if it helped. Contributions welcome via PR.
