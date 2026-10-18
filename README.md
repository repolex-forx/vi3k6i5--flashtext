# Repolex Knowledge Graph of vi3k6i5/flashtext

RDF knowledge graph data for [vi3k6i5/flashtext](https://github.com/vi3k6i5/flashtext), parsed by [repolex](https://repolex.ai).

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
rlex download vi3k6i5/flashtext
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f49274459bc9879789c6e6bb64bf05af755de0b3
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── f49274459bc9879789c6e6bb64bf05af755de0b3
│           └── chunk-001.nq.gz
├── blob
│   ├── 014d2c7533af976a249d26e428295e1b4554a35f.nq.gz
│   ├── 01d1ac75fe5c070a94cc73ab4a76c2f38c427f3f.nq.gz
│   ├── 09f8910af0aabcb6885564777bad044c382d6b2e.nq.gz
│   ├── 0d1486dc7ec3853544ea0b021e00c7d4fdc1f7bb.nq.gz
│   ├── 0d477bbb9470dc8e2fc0b8242fd611bd03bd72d2.nq.gz
│   ├── 17b6a16f4e8d18e1b05cbd3deb1757828d832383.nq.gz
│   ├── 19ac2825d0e12fa42632f9d82359109cbef74a87.nq.gz
│   ├── 1ec3fc5d5f939d151442d414b85353a5c20008a0.nq.gz
│   ├── 2b9f7a4834e0effac6138158b0957dc03a062059.nq.gz
│   ├── 2cce873c04e06e9580d1d593e07faacef84f0966.nq.gz
│   ├── 32e51532cb66e70e680814e0b2183d0f9f5fa1d3.nq.gz
│   ├── 352be1d153249f05b33a52ac07a3f1f1c4c19e92.nq.gz
│   ├── 3c0ebff838ca596a7d99ce2b97b448a7c6955745.nq.gz
│   ├── 417c6e48c63b179248f97b202b49aeeced0cc573.nq.gz
│   ├── 459d2d051f40485496bef20559510a85e6d4708e.nq.gz
│   ├── 4735a5197d294804f5a11eda610e9bbd2f303598.nq.gz
│   ├── 4b965763a0b61b24fc76c82839e8c5528f6f6f70.nq.gz
│   ├── 4bbdedf8d1219ad07f09b0c3b277980913838743.nq.gz
│   ├── 5a849ef870827c84f70374f426ae97a6ea0c1f6b.nq.gz
│   ├── 6263dc7a04dca494c0d233ba04943ba23a2e6977.nq.gz
│   ├── 62807715c969ecc492a679e40c87d059826e83df.nq.gz
│   ├── 67348234b3953318ed5564d44fd6e886e4a71255.nq.gz
│   ├── 6d33d73635c3221e2534509cae2c5cc205fc079b.nq.gz
│   ├── 7c2b2874c477c0a0d7ee2245b5d776da35f61de1.nq.gz
│   ├── 8e1ae056aa5869523ecfe9f626a75379d990072d.nq.gz
│   ├── ac02e84e1b3ea4fd1e2b4c74ba1a696dcc9ec1ac.nq.gz
│   ├── b5cb1d1abd0e891166b2a82f9884cec6f6601831.nq.gz
│   ├── bd0d4585f08fdf433e3001c8a2eb5717266b0c73.nq.gz
│   ├── ccbf4e387f8ae35099cda244cea22d9289d1b11b.nq.gz
│   ├── ce52638e9c1971eff0bea699fdf4350e0f75f71e.nq.gz
│   ├── d63679bbce150e460b5084b74ecf479dc857b17a.nq.gz
│   ├── e5f6daa26cd4dfffb265efc177e313bb14d12b91.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f49c004c0a1bfc8f4fd9061893025ba93e22ddc3.nq.gz
│   ├── f96cca8a8632d9e520651e8c1c38326115a7c2cd.nq.gz
│   └── fc376cb4a75ec056642db330ee2df6e6b541450d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── f49274459bc9879789c6e6bb64bf05af755de0b3.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 44 files
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

[vi3k6i5/flashtext](https://github.com/vi3k6i5/flashtext)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
