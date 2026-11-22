# Repolex Knowledge Graph of harryfei/which-rs

RDF knowledge graph data for [harryfei/which-rs](https://github.com/harryfei/which-rs), parsed by [repolex](https://repolex.ai).

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
rlex download harryfei/which-rs
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5bb3e82a82a6ef8f56a3a455125680fd6579c7ca
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 5bb3e82a82a6ef8f56a3a455125680fd6579c7ca.nq.gz
│   └── repolex
│       └── 5bb3e82a82a6ef8f56a3a455125680fd6579c7ca
│           └── chunk-001.nq.gz
├── blob
│   ├── 0980eec360d52e7c1a7c6006f19da33cf203277c.nq.gz
│   ├── 369139bbd1ec359fd68f78b81633d77675775279.nq.gz
│   ├── 49bb7ef100f596606e6b52a942cd08a1d00c9b6e.nq.gz
│   ├── 5f399834fca96db925a53a1b4443ddc78d30ae7d.nq.gz
│   ├── 7b4ab8c9af111bd8b01d1d72eccf70c02862e3d5.nq.gz
│   ├── 7fccced1e4fe5be71d86c81c7130aa83269fb9cb.nq.gz
│   ├── 833e3ff112888bca93779a174426a30c4845a834.nq.gz
│   ├── 8886f83b29d2512ad8d33634b51774fafcadf4bc.nq.gz
│   ├── 9e3ed5ff5910384028cf1a8f0e0a0798dc7db5bb.nq.gz
│   ├── a14d04bd9748c0c6a781333fd79eeff206b4c3b2.nq.gz
│   ├── ad2a9dbd33cbd901afe97dc85e4074671bf1816d.nq.gz
│   ├── ae9ccc2f12c8a08aeb996bfd2f9c8e855a4c33cd.nq.gz
│   ├── af6bc4300c4b30ca5e1b7c204894c9c3070c8c40.nq.gz
│   ├── e1391a665bd5bda0102228bf7ab267cd1cdc06c9.nq.gz
│   ├── e3af4170909dd4295d329ded4ca09bc25a9d2009.nq.gz
│   ├── e962e344886dafa23e95fe8676e28176afa1c638.nq.gz
│   ├── fc0a65f161c0d3b11bd23ef79eba2c852adedf8d.nq.gz
│   └── fcebc0dc58b1e8f865b72c3e7cc6da6edc3ad6d5.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 5bb3e82a82a6ef8f56a3a455125680fd6579c7ca.nq.gz
├── filetree
│   └── 5bb3e82a82a6ef8f56a3a455125680fd6579c7ca.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 28 files
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

[harryfei/which-rs](https://github.com/harryfei/which-rs)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
