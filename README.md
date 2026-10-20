# Repolex Knowledge Graph of klen/muffin-peewee

RDF knowledge graph data for [klen/muffin-peewee](https://github.com/klen/muffin-peewee), parsed by [repolex](https://repolex.ai).

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
rlex download klen/muffin-peewee
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── cf338708b459a963e23e7239058fc3aa9226b2a8
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── cf338708b459a963e23e7239058fc3aa9226b2a8
│           └── chunk-001.nq.gz
├── blob
│   ├── 09e6f05caffeab803b1a305779acd056bbece71d.nq.gz
│   ├── 0a6ee958310ca78a98bf4803c291d5898c7fd5b4.nq.gz
│   ├── 0b2e907c89333ea1b1c45cf476f5afdd63c69c08.nq.gz
│   ├── 0bff1d00cb28163968ca17515b90d711fb537385.nq.gz
│   ├── 12166ed838d0dc4f07089db3df3a7b608797390f.nq.gz
│   ├── 20bbf93a14c72d3c952b0b4ff07ccdd9e1cf18ea.nq.gz
│   ├── 23c5c150f58bdd129447223d88288e859f8cccb1.nq.gz
│   ├── 2ddfb30d221818828f720d5e3fc3ebbd5e3cfcd0.nq.gz
│   ├── 3c80bffce68b8b1a71e093dbac5855a43f0cd83a.nq.gz
│   ├── 402de5133a6f8c7f1137ad67a4ec7de583661d8b.nq.gz
│   ├── 5541b072c386d7e7552f3162ba02027f2ce5429b.nq.gz
│   ├── 559db0bb9fdc71a8fe1a4e7149fcd150745b030a.nq.gz
│   ├── 5702157bde0cb72013c05c7e479d978b0fe2520f.nq.gz
│   ├── 5f1d5686f3dc12105665875988bbe0b90d32c2bc.nq.gz
│   ├── 5f386c8458de822cef576b7fde89bfd05fc56f52.nq.gz
│   ├── 666ce2a519fd8f0c3599a11f968422b82612ca92.nq.gz
│   ├── 6e01047c068eda4b69abe103ae8da636731f8ab9.nq.gz
│   ├── 7886a32406bcd30ba2f3ae990572fec279b39222.nq.gz
│   ├── 78df056a6afd6b2f7c5a8695635380a19f30acd9.nq.gz
│   ├── 78f3fb8d5b56eabe24f3167625c38783a565d33c.nq.gz
│   ├── 7a3f07ab83552f47a8705fa5d22729a324a2f71a.nq.gz
│   ├── 7bacd3cc2f2745f2ddf8a5f6273395388d9e6c78.nq.gz
│   ├── 9475d4c130bb855735b9bae80939af3ed02e7231.nq.gz
│   ├── c3e2bbeb4ffb903215c764f6838d342c45baacae.nq.gz
│   ├── ce48f87110f5a00c4f3320f9ed0c8e630cb23daf.nq.gz
│   ├── df7604696c0854a1ed10dd2d4e05276a44cfb669.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e728d03676c20ba87a39556e60b642f5df17ebde.nq.gz
│   └── f04208224b00b9f929e70c36506a4e18acfe02a5.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── cf338708b459a963e23e7239058fc3aa9226b2a8.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 37 files
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

[klen/muffin-peewee](https://github.com/klen/muffin-peewee)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
