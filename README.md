# @tummycrypt/tinyland-analytics-data (retired)

> **Retired 2026-10-09.** This package was merged into
> [xoxd-ai/tinyland-otel](https://github.com/xoxd-ai/tinyland-otel) as the
> `./analytics-data` subpath export, shipped in `tummycrypt_tinyland_otel`
> 1.1.0 and later. This repository is archived and gets no further changes.

## Migration

- Bazel: remove `bazel_dep(name = "tummycrypt_tinyland_analytics_data", ...)` and
  depend on `bazel_dep(name = "tummycrypt_tinyland_otel", version = "1.1.0")`
  (or later) from [xoxd-ai/bazel-registry](https://github.com/xoxd-ai/bazel-registry).
- Imports: change `@tummycrypt/tinyland-analytics-data` to
  `@tummycrypt/tinyland-otel/analytics-data`. The API is the same
  (`configure`, `getConfig`, `resetConfig`, `parseTimeRange`,
  `AnalyticsDataService`, `analyticsDataService`, `createAnalyticsDataService`,
  and the types `PageView`, `AnalyticsMetrics`, `AnalyticsDataConfig`, `Logger`,
  `FetchResponse`).
- The otel root also re-exports it under non-clashing names
  (`configureAnalyticsData`, `AnalyticsDataService`, `analyticsDataService`, ...).

## Distribution

Bazel is the only distribution path for in-house packages. Nothing is published
to npm from this repository any more, and the publish workflow has been removed.
The Bazel module `tummycrypt_tinyland_analytics_data` (0.2.2, 0.2.3) is marked
deprecated in the registry but stays resolvable; nothing is yanked. Earlier npm
releases of `@tummycrypt/tinyland-analytics-data` remain on the npm registry.

## What it was

A Loki-backed reader for page view and session metrics: page views, top pages,
unique visitors, active users, average session duration, bounce rate and
traffic sources, read through a caller-supplied `fetchLoki` function.
