# Repolex Knowledge Graph of click-contrib/click-didyoumean

RDF knowledge graph data for [click-contrib/click-didyoumean](https://github.com/click-contrib/click-didyoumean), parsed by [repolex](https://repolex.ai).

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
rlex download click-contrib/click-didyoumean
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d8a5eb9f826556cda173b00d63056460d555e361
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── d8a5eb9f826556cda173b00d63056460d555e361
│           └── chunk-001.nq.gz
├── blob
│   ├── 3694d8ff85c56ec4e316846b94807ae05147ee57.nq.gz
│   ├── 77fff8cd8b57465702ab0c9531ac9cd82c5fd414.nq.gz
│   ├── ae57c793bc0b1fae453e5232c54bda759ae4687d.nq.gz
│   ├── c2b94194f19b74e63eaa775deb39b37866930e98.nq.gz
│   ├── ce9541a7ff57d2a71223df052dfe28bd591a3aa7.nq.gz
│   ├── cf6a4cf5c17e9aa6d00d516875f954d691cbf289.nq.gz
│   ├── db1213f0b64c7dcfc11440d931a596691c430748.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── efeaa6bc8459bd325147b483a078f07e473f685e.nq.gz
│   └── f736a5953d3d2c69f53555e284af9728ced6d20e.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d8a5eb9f826556cda173b00d63056460d555e361.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 18 files
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

[click-contrib/click-didyoumean](https://github.com/click-contrib/click-didyoumean)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
