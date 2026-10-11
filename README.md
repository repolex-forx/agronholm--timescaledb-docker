# Repolex Knowledge Graph of agronholm/timescaledb-docker

RDF knowledge graph data for [agronholm/timescaledb-docker](https://github.com/agronholm/timescaledb-docker), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download agronholm/timescaledb-docker
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 62dc5d41b9b3e26e9cf8bbf682103fecef184d33
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 62dc5d41b9b3e26e9cf8bbf682103fecef184d33
│           └── chunk-001.nq.gz
├── blob
│   ├── 139bdc745791b70a05095eb65ef783cbd2ae8a10.nq.gz
│   ├── 1db607f1b0912e1503061b2f69527f964e4ebab0.nq.gz
│   ├── 3132f2e99604c4351c6aeb6d1c8051d98b8ae814.nq.gz
│   ├── 39521b726d754885c5d7c21307d7c93c88d771f1.nq.gz
│   ├── 51987ac390a0ef8f05fd5a7a792ce49db756abb8.nq.gz
│   ├── 6d9d67c4a094d460f318a761c72343ce8ba40b57.nq.gz
│   ├── 8b06b8ad0b4573bcda94863472bda1551b248eee.nq.gz
│   ├── 948c76ba4aee9c9ea7541ebfbf1d4ca7e8944cd3.nq.gz
│   ├── ae3a81db8e0b4bf49b350f25a5e9bd801ce15560.nq.gz
│   ├── b7614a3bb7a1dc27657c0be46c0f82f85294ac69.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   ├── ef0ae0fbdb0e5f4911ce1b25732fece495c4862c.nq.gz
│   ├── f2affdd92b415e52a3035b6414df1816395a1e3e.nq.gz
│   └── f2be5c36cdd7126c749b8deacf57d07b1108eddb.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 62dc5d41b9b3e26e9cf8bbf682103fecef184d33.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 20 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[agronholm/timescaledb-docker](https://github.com/agronholm/timescaledb-docker)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
