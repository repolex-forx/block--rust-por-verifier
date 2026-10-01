# Repolex Knowledge Graph of block/rust-por-verifier

RDF knowledge graph data for [block/rust-por-verifier](https://github.com/block/rust-por-verifier), parsed by [repolex](https://repolex.ai).

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
rlex download block/rust-por-verifier
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 580e1f366bfcee0a11890ee16d2ce1fbef0cebf9
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 580e1f366bfcee0a11890ee16d2ce1fbef0cebf9.nq.gz
│   └── repolex
│       └── 580e1f366bfcee0a11890ee16d2ce1fbef0cebf9
│           └── chunk-001.nq.gz
├── blob
│   ├── 05fbc36ba35ee9e70782dd214456139ef2403479.nq.gz
│   ├── 0ba9db25329d0b336e39ca8cde8470c5b7bc45eb.nq.gz
│   ├── 12cc251960a095779ec6d03d69e09819ca15d877.nq.gz
│   ├── 21ecf13a6fc9700d6494b5a930d156bd547e15c7.nq.gz
│   ├── 25f0bc5ed80683a81f46e6bfd1cf8ea0b56c6807.nq.gz
│   ├── 39ee2986eb5b5d98b1f5c4d090e848053f01d81c.nq.gz
│   ├── 6bccf43368fd7c96d9c659562a5142b8b8cb98a1.nq.gz
│   ├── 6e84586771ca14c396c35e69739d0873007f9f0c.nq.gz
│   ├── 78a19cfbe0773f7f931b8af5e0c907131e678add.nq.gz
│   ├── 9303e473b5a5eb44158ea4a4e6b9d97ec7520289.nq.gz
│   ├── 9582fc588754f78d9875691a3bd5e674295436b3.nq.gz
│   ├── a758a3128452eadc31e06e7ec837f5c2a78039b3.nq.gz
│   ├── ae4b1853e04abdd6c98554b38c659b93293ffdff.nq.gz
│   ├── bb812584887aa1ad54adf104d03e57b073e331e5.nq.gz
│   ├── c45f2e5f2979ea9a632b12d4206e152320d4dd01.nq.gz
│   └── ed6736ca348115b62e448d20e4cf7ce02ec9c6ee.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 580e1f366bfcee0a11890ee16d2ce1fbef0cebf9.nq.gz
├── filetree
│   └── 580e1f366bfcee0a11890ee16d2ce1fbef0cebf9.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 26 files
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

[block/rust-por-verifier](https://github.com/block/rust-por-verifier)

---
*Parsed on 2026-10-01 by [repolex](https://repolex.ai)*
