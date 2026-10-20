# Repolex Knowledge Graph of jaraco/singledispatch

RDF knowledge graph data for [jaraco/singledispatch](https://github.com/jaraco/singledispatch), parsed by [repolex](https://repolex.ai).

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
rlex download jaraco/singledispatch
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 8dab473b3f7e81bcf87165e640b9f0ec3e18d5c3
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 8dab473b3f7e81bcf87165e640b9f0ec3e18d5c3
│           └── chunk-001.nq.gz
├── blob
│   ├── 0000f0c92bd5c643b04d770c32b64cd0f82fcd56.nq.gz
│   ├── 10d412f406891b9683f832fcbc134c9bdf4f916e.nq.gz
│   ├── 1f2aa7533b0423a8eb943f6f4ec02498e39581a0.nq.gz
│   ├── 2e3f4dd791a6372b427d618eb0baa8c4dc58e5f0.nq.gz
│   ├── 304196f81e11a168c9894f966e4a617ebf4ed53c.nq.gz
│   ├── 31124d11ae2cec27a68077e71ab52326b144ade6.nq.gz
│   ├── 54c9000ec94341dd65c2053251b85b124017b9b5.nq.gz
│   ├── 54cc8303b22089e12053e552d4e6cb852a865b8a.nq.gz
│   ├── 577e87a793a20e413f7321f4f17ec1eba2ea1962.nq.gz
│   ├── 5bdc232005af9be104a00437ae9bc64417a4c1cc.nq.gz
│   ├── 62bf03d0cd3b0b0e60d9a8c0c3b8c042fa80b2cd.nq.gz
│   ├── 700235be57c1b2872455c0be5333f59cf568e252.nq.gz
│   ├── 724370638fc188317bbc7dc868f1a571995fd796.nq.gz
│   ├── 9a0f3bce1395ae3819030b822e5d9076c85068ea.nq.gz
│   ├── a8d81dff8f99bb56f3fbd9e20095e1976ad1433b.nq.gz
│   ├── a991639f7d14e866b4a7cb6dc6e83f70f326af61.nq.gz
│   ├── b5d4157558444a4daf78ed1a7a760b970c91f076.nq.gz
│   ├── c8a479e4f9da112496418949ca66d22f938d4897.nq.gz
│   ├── ceb26d55c4816256e7a425b219c637677b8bc37c.nq.gz
│   ├── d521ae7efcdd2ec48bf72b5710692aff8f0fb5d5.nq.gz
│   ├── d755c8576d7e4c1ab2b650e0999cb6257305684f.nq.gz
│   └── e05a3d4a2ab888e32952006d8cd380864368db5f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 8dab473b3f7e81bcf87165e640b9f0ec3e18d5c3.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 30 files
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

[jaraco/singledispatch](https://github.com/jaraco/singledispatch)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
