# Repolex Knowledge Graph of astral-sh/ty-pre-commit

RDF knowledge graph data for [astral-sh/ty-pre-commit](https://github.com/astral-sh/ty-pre-commit), parsed by [repolex](https://repolex.ai).

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
rlex download astral-sh/ty-pre-commit
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ded8634232ffc633dc66d44f1b0dfe2bdf766542
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ded8634232ffc633dc66d44f1b0dfe2bdf766542
│           └── chunk-001.nq.gz
├── blob
│   ├── 1a0062569d1d0268fba61cf4a7a885b64521ac1b.nq.gz
│   ├── 1febb9f87852428471ec13a4cdb408996116bf21.nq.gz
│   ├── 23b2203df3cf8a2c5206343b40511b5e182cd8b2.nq.gz
│   ├── 309de5763b135a2f879391d9c899e95ca488798b.nq.gz
│   ├── 543902914efcc5562aa023691347836e9ed4cccb.nq.gz
│   ├── 9b37f144aa1c5aae80dfe0c1b5301b6520ba4e26.nq.gz
│   ├── a75c39950d64468efe139133db45120fb5cf0932.nq.gz
│   ├── ad45eb8b5db71785f2e518db460e27b01204fe94.nq.gz
│   ├── b0a477a71ad1ded7b57c42738b717bc8c3b87f6a.nq.gz
│   ├── c16d8bb1db2621505a8bdd37d260d6f312b049ad.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   └── f8980229a290a76f4fffdf0594d8663dc52435c3.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ded8634232ffc633dc66d44f1b0dfe2bdf766542.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 20 files
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

[astral-sh/ty-pre-commit](https://github.com/astral-sh/ty-pre-commit)

---
*Parsed on 2026-10-10 by [repolex](https://repolex.ai)*
