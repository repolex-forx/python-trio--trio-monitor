# Repolex Knowledge Graph of python-trio/trio-monitor

RDF knowledge graph data for [python-trio/trio-monitor](https://github.com/python-trio/trio-monitor), parsed by [repolex](https://repolex.ai).

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
rlex download python-trio/trio-monitor
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 1fc9766a18f81983e4999061f30ec53329d7259d
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 1fc9766a18f81983e4999061f30ec53329d7259d
│           └── chunk-001.nq.gz
├── blob
│   ├── 06fd51f12eae02662780444feff431f5fb7a03d1.nq.gz
│   ├── 0dd63e7f40f365abc7e64f842f8cc113ceac93d1.nq.gz
│   ├── 104c402ebf17ef55f9cdca2114f0a4449f6dd039.nq.gz
│   ├── 20a7c8176e2ebb0af95c8aac0d6c0654a69918cf.nq.gz
│   ├── 291bfeaa3b207e4173c50080f22cfb473363ee5a.nq.gz
│   ├── 3096fe49854d19a802d3ef35a44cdcefac425dc6.nq.gz
│   ├── 45681f715c81c579d5ad89e6d9c477c4e19c8079.nq.gz
│   ├── 51f3442917839f8e0f0cccb52b3c10968ad0779e.nq.gz
│   ├── 67898ba6f5cffa770a3110d8c996c8203cbbdc26.nq.gz
│   ├── 687ec1717655ffa9eacffafe04f56a53fc359555.nq.gz
│   ├── 6ed1b6035b1f7dd0b44bc7eab5bbe2c06b647099.nq.gz
│   ├── a9719aec7626c8b5843a22308a704a969fa3d9d0.nq.gz
│   ├── afdfef3b06fe1d54e39083d712ff964d36c44f28.nq.gz
│   ├── b8bb97185926d7daed314609753173945ed4ff1a.nq.gz
│   ├── bd0ac7354ccfd90b1be49cfdab99260fba3abb75.nq.gz
│   ├── c88c131759171c5052f4a054f43bddf6f7a50579.nq.gz
│   ├── cd6c20838a33daabd844252c4ad3f3ee548572c6.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   ├── da6abdf2ce977fc22ed876f6b16a95a7fa4341da.nq.gz
│   ├── dfd005ec041432431cf2cd0564fa57584f5c1822.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ea582df848f9f808b9e200078f422c7b89c83a26.nq.gz
│   ├── ee1ac5ad8b98ac29e0c49297a535141ed99d9bf8.nq.gz
│   └── fe87c35f7786a833d93aad59c617777ddc9cf9e7.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 1fc9766a18f81983e4999061f30ec53329d7259d.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 32 files
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

[python-trio/trio-monitor](https://github.com/python-trio/trio-monitor)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
