# Repolex Knowledge Graph of pydantic/pydantic-media-kit

RDF knowledge graph data for [pydantic/pydantic-media-kit](https://github.com/pydantic/pydantic-media-kit), parsed by [repolex](https://repolex.ai).

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
rlex download pydantic/pydantic-media-kit
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e84e2728e15a5433f8c53c0063b026a5c7056424
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── e84e2728e15a5433f8c53c0063b026a5c7056424
│           └── chunk-001.nq.gz
├── blob
│   ├── 68d9040927a3597179e1fc2d59d88847fe73c8fc.nq.gz
│   ├── b6bd70ceb66eb4b309d197bb35199d559cc60521.nq.gz
│   ├── d6f8aa7dc92b01498e33fd16e43e27d0f8941d64.nq.gz
│   ├── eb1ad2a23df0e202602825f8f2b057a02dfc501b.nq.gz
│   ├── ec25b43f7012c055f9b13349a8168a9c551378ca.nq.gz
│   └── fec8886a91ee7cfee70e81e73f6cc4b831417b38.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── e84e2728e15a5433f8c53c0063b026a5c7056424.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 12 files
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

[pydantic/pydantic-media-kit](https://github.com/pydantic/pydantic-media-kit)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
