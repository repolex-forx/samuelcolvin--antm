# Repolex Knowledge Graph of samuelcolvin/antm

RDF knowledge graph data for [samuelcolvin/antm](https://github.com/samuelcolvin/antm), parsed by [repolex](https://repolex.ai).

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
rlex download samuelcolvin/antm
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 922d2902b14a99afe58d7ff90dfbbd4f37d8165c
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 922d2902b14a99afe58d7ff90dfbbd4f37d8165c
│           └── chunk-001.nq.gz
├── blob
│   ├── 05d6c8065d95b92ac3d9cddd454041d14f17f4bb.nq.gz
│   ├── 1daeb45d2ce2efc2b38abdc7d4f99f638777fb13.nq.gz
│   ├── 24ee5b1be9961e38a503c8e764b7385dbb6ba124.nq.gz
│   ├── 255859003a4bc40ee744ae7894f0612486c78416.nq.gz
│   ├── 2b676f48cca267fbecc8a29640a18999866eadca.nq.gz
│   ├── 2d5cee8f3f7a2c9c77d9b8806e4a225807d06d39.nq.gz
│   ├── 4581e3262c5789530ff96186e873f57a52ce07b0.nq.gz
│   ├── 48d4f28beed53e02c3c755547f1db4d3d06f684b.nq.gz
│   ├── 556c582c7e861f8b942b946359b0c2b0b534aa92.nq.gz
│   ├── 5f4bb43888853db29cc76b7ee1ef0d73f5860904.nq.gz
│   ├── 67c4b80384a37366d1bfad8cfb0419f94b13bf8e.nq.gz
│   ├── 8206e03882b2bf467be8e975f9b455d075367a81.nq.gz
│   ├── 946040a871df326dc9a852164d03db6f5545c2a0.nq.gz
│   ├── aa1db276e047d38b6d1c147e6930f83ffe4a5f3c.nq.gz
│   ├── b6a3e92fa04268a55d7c3a9c7a054ce39472f6d8.nq.gz
│   ├── c52062028703f698b521b9de767233a53d918f27.nq.gz
│   ├── cc5f45bc0a46d20642ad016df03a5f6a42f992c9.nq.gz
│   ├── d9994e81788288cf101a7d83c26c67a6bdf42dab.nq.gz
│   ├── dc0907e30c601b41f0ae19a37dc4613b9a041077.nq.gz
│   ├── eaa2598afd16a915a3ec2838e652ca6778de7e9d.nq.gz
│   ├── f2ab2a215aa609de71b65778bf18bf97fbf64ea0.nq.gz
│   └── f6a72dad03f56fa4e3a3424226f9951cfd9b04d9.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 922d2902b14a99afe58d7ff90dfbbd4f37d8165c.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 28 files
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

[samuelcolvin/antm](https://github.com/samuelcolvin/antm)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
