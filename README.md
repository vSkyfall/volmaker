# volmaker

A personal research project for building and evaluating an automated trading system on a perpetual futures market.

The system runs in **paper (demo) mode only**. It reads public market data, simulates fills, fees and funding on its own, and never sends real orders to an exchange.

## What it includes

- **Signal engine:** An incremental engine that processes closed one-minute candles and produces trade setups.
- **Demo broker:** Simulates limit and market fills, stop and target exits, exchange fees, funding payments and position sizing, so results are as realistic as possible without risking money.
- **Restart-safe design:** Market data is stored on disk and replayed on startup. If the machine is off for a while, the missed period is downloaded and processed when it comes back.
- **Local dashboard:** A browser panel that shows the chart, open position, demo balance, closed trades with profit and loss, and a progress counter for the ongoing paper test.
- **Research tooling:** A backtest simulator, data quality checks and a statistics module used to evaluate ideas before they reach the bot.

## How the research is done

Every idea is treated as a hypothesis:

1. It is written down with its exact rules and pass criteria before any result is seen.
2. It is tested once, on data that was not used to design it.
3. If it fails, it is closed. Variants are not tried until something passes.

All experiments are recorded in an append-only log, so the full history, including failures, stays visible.

## Safety

- No live order code and no exchange API keys.
- Dashboard is reachable only from the local machine.
- A test period of market data is kept locked and is not used for research.

## Status

Under active research. No configuration has been shown to be profitable yet, so the project is not used with real money.

## Tech

Python 3.12, NumPy, pandas, aiohttp. Runs on macOS and Windows.

## Notice

This repository is for personal research and is not financial advice. Usage details, strategy rules and settings are not shared.

All rights reserved.
