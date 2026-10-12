# Repolex Knowledge Graph of spec-first/swagger_ui_bundle

RDF knowledge graph data for [spec-first/swagger_ui_bundle](https://github.com/spec-first/swagger_ui_bundle), parsed by [repolex](https://repolex.ai).

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
rlex download spec-first/swagger_ui_bundle
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 77ce9d279b3b0699511e3b2900477db47374e593
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 77ce9d279b3b0699511e3b2900477db47374e593
│           └── chunk-001.nq.gz
├── blob
│   ├── 11a19be97c813628678fcf253b6aa8d878229afc.nq.gz
│   ├── 185a2add3b911754681b854e09ff1d485a4c3f6f.nq.gz
│   ├── 77dfede7bb557cc4d9af2e9532e1ad3fb884071a.nq.gz
│   ├── 7a4a3ea2424c09fbe48d455aed1eaa94d9124835.nq.gz
│   ├── b525fe213221e2dd68f34f5972fdab58b66d7ca4.nq.gz
│   ├── e1736e0de9cbe58a8d4bd87246c52eb38947a269.nq.gz
│   ├── e18c0766ef686c60cd6f0793643f4df906359f80.nq.gz
│   ├── e78040f380f13f3e2fa58d69fbd99e31c50a0511.nq.gz
│   └── f60709e810a9b42ccdfad6559630468952aa079b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 77ce9d279b3b0699511e3b2900477db47374e593.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 17 files
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

[spec-first/swagger_ui_bundle](https://github.com/spec-first/swagger_ui_bundle)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
