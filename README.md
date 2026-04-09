# cache-proxy

[![Build Status](https://img.shields.io/github/actions/workflow/status/user/cache-proxy/ci.yml?branch=main)]()
[![Go Version](https://img.shields.io/badge/go-1.22+-blue.svg)]()
[![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

> Transparent caching reverse proxy with configurable TTL and invalidation

A Go project focused on solving real-world engineering problems.

## Features

- **High Performance** — Optimized for low-latency, high-throughput workloads
- **Structured Logging** — Built-in structured logging with slog compatibility
- **Zero Dependencies** — No external packages required for core functionality
- **Context Support** — Full context.Context propagation for cancellation and deadlines

## Installation

```bash
go get github.com/user/cache-proxy@latest
```

## Usage

```go
package main

import (
	"fmt"
	"github.com/user/cache-proxy"
)

func main() {
	client := cacheproxy.New(
		cacheproxy.WithTimeout(30 * time.Second),
	)

	result, err := client.Run(context.Background())
	if err != nil {
		log.Fatal(err)
	}

	fmt.Println(result)
}
```

## Configuration

Configuration can be provided via environment variables, a config file, or programmatically.

| Variable | Description | Default |
|----------|-------------|--------|
| `CACHE_PROXY_TIMEOUT` | Request timeout in seconds | `30` |
| `CACHE_PROXY_RETRIES` | Number of retry attempts | `3` |
| `CACHE_PROXY_LOG_LEVEL` | Log verbosity (debug, info, warn, error) | `info` |

## License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.
