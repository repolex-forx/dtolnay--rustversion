# Repolex Knowledge Graph of dtolnay/rustversion

RDF knowledge graph data for [dtolnay/rustversion](https://github.com/dtolnay/rustversion), parsed by [repolex](https://repolex.ai).

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
rlex download dtolnay/rustversion
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 9e86f839b6a34a7d9398f243d88bf400b7fa1f7c
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 9e86f839b6a34a7d9398f243d88bf400b7fa1f7c.nq.gz
│   └── repolex
│       └── 9e86f839b6a34a7d9398f243d88bf400b7fa1f7c
│           └── chunk-001.nq.gz
├── blob
│   ├── 058f340f690cd73cee864761fdcbd7fe5f280d26.nq.gz
│   ├── 09846254b04c29bc032a2988b835fadedf6506b8.nq.gz
│   ├── 0d0c7b853cb758aac727d5acd9d43604acac5dbe.nq.gz
│   ├── 0e50c0396996c3146edad14b55f966fe4decb043.nq.gz
│   ├── 102c80bcfce3d9694d533f0a3ba8dd0c66e9e628.nq.gz
│   ├── 1b5ec8b78e237b5c3b3d812a7c0a6589d0f7161d.nq.gz
│   ├── 1fe8dba166ec057c284382cdf2745a2ae098610e.nq.gz
│   ├── 215df7d7d00d01900ca5dc3361f8a2564e099dae.nq.gz
│   ├── 23a6a065ec960a031726c8c26222b0405d4f5851.nq.gz
│   ├── 2a964061777a34ae366f04812d147ac679b0d111.nq.gz
│   ├── 2b0c699332b70307a0d09833d948af7b0b19655c.nq.gz
│   ├── 31aa79387f27e730e33d871925e152e35e428031.nq.gz
│   ├── 45ed7d2156226c9da45be5522380849726be4bb6.nq.gz
│   ├── 559e463575e4ec65a43a39b8f6fd85b1cc4ea3a4.nq.gz
│   ├── 576292abb6d549de3ded5aa063e9eaf6d642378d.nq.gz
│   ├── 6023d1eaf12fbc0bb6eacdd2a1a1a284b532a97a.nq.gz
│   ├── 64c61ca2182114e2cc4e42fee68ac9fbb12e1438.nq.gz
│   ├── 66c22df110e8ee491424dd5a905f741cd639189d.nq.gz
│   ├── 722013c7d6c05f6fd481f05f48317b7962f7a2a0.nq.gz
│   ├── 750707701cdae985156601cc906195021ba6a6e5.nq.gz
│   ├── 826725825d258f6cf69a28d07c8e362386286bd1.nq.gz
│   ├── 9a43a654ab4e88b0176bf9402f764c64518398e3.nq.gz
│   ├── 9b1db03c359622eef83a5a24629433ce69a4d9dc.nq.gz
│   ├── a99625b4aabf101204ac75b49951cae0ee919572.nq.gz
│   ├── aa4e71018014b0aed5a8a14a193999af062da188.nq.gz
│   ├── add8792eb116f88c8cf53f0c6475f418b9055df3.nq.gz
│   ├── bf3f144b153712179d180c063507f58d4fedddb4.nq.gz
│   ├── c044e8599f52a5e337a338bcc2bfa63588319d5d.nq.gz
│   ├── c8c021921df9b3319869b4c09bb69858254b9546.nq.gz
│   ├── ce70f2e4d68f9130cc43a21278e66a412d97470d.nq.gz
│   ├── d009641653a6e04900fc6cd17eb96f90d7c294a9.nq.gz
│   ├── d3cb4aa678099b37068fea5138462ecd8d6e1983.nq.gz
│   ├── d9b0eb673860cce211051fc634b15be30409904a.nq.gz
│   ├── e9e21997b1aca0707f8749ea13c09aec66c899d2.nq.gz
│   ├── ebb6f1c012a453acd99899cc94490fb8f7529bdc.nq.gz
│   └── f4a69f51855b6d1fb4d6961b088ea9aa650c2e80.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 9e86f839b6a34a7d9398f243d88bf400b7fa1f7c.nq.gz
├── filetree
│   └── 9e86f839b6a34a7d9398f243d88bf400b7fa1f7c.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 46 files
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

[dtolnay/rustversion](https://github.com/dtolnay/rustversion)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
