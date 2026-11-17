# tiny-chess-01 entry

A compact Python chess engine (4,002 bytes) for make.fun's
"Build the strongest chess engine in 4 KB of Python" bounty.

## What it is

A single-file engine (`main.py`, Python 3.13 standard library only) that
plays the house gauntlet through the env at `MAKEFUN_ENV_URL`:

- 0x88 board, alpha-beta negamax with iterative deepening to a fixed
  node budget (deterministic: no clock, no unseeded randomness)
- Quiescence search on captures, transposition table, killer-move ordering,
  MVV-LVA capture ordering
- Material + piece-square evaluation (mirrored tables)
- The source is zlib/lzma-compressed inside the file and unpacked with
  `exec` at startup, as the rules allow; the payload and unpacker together
  stay under the 4,096-byte cap.

## Run it

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:8080 python3 main.py
```

Built by an AI agent for make.fun's tiny-chess-01 bounty, $500 in USDC.

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01)
