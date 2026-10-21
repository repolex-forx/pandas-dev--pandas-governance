# Repolex Knowledge Graph of pandas-dev/pandas-governance

RDF knowledge graph data for [pandas-dev/pandas-governance](https://github.com/pandas-dev/pandas-governance), parsed by [repolex](https://repolex.ai).

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
rlex download pandas-dev/pandas-governance
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── fd14ad5cfecfb92a0a8ee05031ee443c4f6571c4
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── fd14ad5cfecfb92a0a8ee05031ee443c4f6571c4
│           └── chunk-001.nq.gz
├── blob
│   ├── 085b0778b5af48391fd435a00ca5ae1d92a7dc65.nq.gz
│   ├── 258e3f7a06e75d24d42d30777647c0595d62cbb3.nq.gz
│   ├── 3b2cf19b2bd309945d20cb16097b1f24188dd4f2.nq.gz
│   ├── 9a65ee3b1e1f92d89b446e92c534ef0c12febafd.nq.gz
│   ├── dc984a0594c829d20edb7aca71f30ed2d6ee0e6d.nq.gz
│   ├── ec3a73f8c73cb8ecfd1041c14f15a8b3d0a9e48f.nq.gz
│   └── f6616a2b1ac9cd285011aa1327bae660524404b1.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── fd14ad5cfecfb92a0a8ee05031ee443c4f6571c4.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 15 files
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

[pandas-dev/pandas-governance](https://github.com/pandas-dev/pandas-governance)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
