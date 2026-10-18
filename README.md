# Repolex Knowledge Graph of thombashi/mbstrdecoder

RDF knowledge graph data for [thombashi/mbstrdecoder](https://github.com/thombashi/mbstrdecoder), parsed by [repolex](https://repolex.ai).

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
rlex download thombashi/mbstrdecoder
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d44737c4e817d6d39cce03f966005f319d6e0a3e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── d44737c4e817d6d39cce03f966005f319d6e0a3e
│           └── chunk-001.nq.gz
├── blob
│   ├── 041147b33e32d1dd1516c2c411743954f86b7776.nq.gz
│   ├── 07e1dadba18dbc8b48b6c0c072fef0c8cb315ff4.nq.gz
│   ├── 1862de44521a83ca1462578766d0700b12ffe2b1.nq.gz
│   ├── 35e3314155d1c6d96f93346ae54841398d02f46a.nq.gz
│   ├── 3c9e5640a303929e06cfb9a249dfced8011112d3.nq.gz
│   ├── 41cbe1a4dbfd3af577fef078705a1bbc630b19d9.nq.gz
│   ├── 4e4f84b6c29037306cdb56e03e6c0172ed95719c.nq.gz
│   ├── 5c3607f7333ad6ab5251846de7650bb7aa13b59d.nq.gz
│   ├── 677b883c7ff1db53859a2424e4f5d490a7da5919.nq.gz
│   ├── 755a14092dd64f47dcd1f8573bcbdc57cbcd2392.nq.gz
│   ├── 76b91aa97916096d0c34b87ad6c00ed7a116c186.nq.gz
│   ├── 7f49682d341006caccc5a703cb836ff149c6f1b7.nq.gz
│   ├── 86493d4be7df342883d62f5387882acf2150f58c.nq.gz
│   ├── 8863ef18168973fad1271c1c9a069a433957734a.nq.gz
│   ├── 9395622535fd9d4d781785c7e33860aa35f7fe91.nq.gz
│   ├── 9555a7c14f2f77bf6bab7519c83f597160c77edb.nq.gz
│   ├── a03153f060410688d94dbbab7c998f8da27432c9.nq.gz
│   ├── c0e31dbecbd167e1426a7b73aaa91a0c63722878.nq.gz
│   ├── c1d9971674ca4115870c75bfffcde95dad6ee2fb.nq.gz
│   ├── cbac6e0785586aa0ff39e8452ce9ca2570d307ed.nq.gz
│   ├── e38a6ea6e8f998e4b20351520bed3486af4788dc.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ed1efe2c9f1715517f0d3977b65596f9bb81f211.nq.gz
│   └── ed3b9c2d182dff638e989a1121be4e1668b1dc9a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d44737c4e817d6d39cce03f966005f319d6e0a3e.nq.gz
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

[thombashi/mbstrdecoder](https://github.com/thombashi/mbstrdecoder)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
