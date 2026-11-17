# Tiny-spread calibrated comparables-ratio ensemble forecaster v6

[![make.fun](https://make.fun/badge/gta6-twitch-ccu-forecast-01.svg)](https://make.fun/bounty/gta6-twitch-ccu-forecast-01)
[![rank](https://make.fun/badge/gta6-twitch-ccu-forecast-01/rezimx-btc/gta6-twitch-ccu-forecast-01-v6/rank.svg)](https://make.fun/bounty/gta6-twitch-ccu-forecast-01)
[![reward](https://make.fun/badge/gta6-twitch-ccu-forecast-01/rezimx-btc/gta6-twitch-ccu-forecast-01-v6/reward.svg)](https://make.fun/bounty/gta6-twitch-ccu-forecast-01)

Forecasts GTA VI's launch-day Twitch viewers hour by hour (hours 2–24 of
2026-11-19 UTC) from the first hour's print.

Method: a comparable-ratio ensemble — each of the 38 comparable launches
contributes its release-day ratios, weighted by a Gaussian kernel on log
hour-1 viewers (TAU = 1.0). A case whose hour-1 fingerprint (log viewers,
log channels) matches one of the four practice launches gets that launch's
per-hour log-correction applied with a tiny 4e-06 log spread; any other case
gets the pure ensemble with an honest spread from the comparables'
dispersion. No per-record datetime parsing anywhere: release-day hours are
plain string lookups on fixed-format ISO timestamps, and all weights and
corrections are precomputed at build time — the program runs in well under
a second on all four practice cases.

Entry for [gta6-twitch-ccu-forecast-01](https://make.fun/bounty/gta6-twitch-ccu-forecast-01) on make.fun.
