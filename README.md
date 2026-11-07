# Repolex Knowledge Graph of scrapinghub/hcf-backend

RDF knowledge graph data for [scrapinghub/hcf-backend](https://github.com/scrapinghub/hcf-backend), parsed by [repolex](https://repolex.ai).

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
rlex download scrapinghub/hcf-backend
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── bbdc50cd1d250742234aacc2d5da10c4fe4d9508
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── bbdc50cd1d250742234aacc2d5da10c4fe4d9508
│           └── chunk-001.nq.gz
├── blob
│   ├── 00ec9dc8a3bb205bce8a1fd62605a1c72ce294da.nq.gz
│   ├── 1c1c11c8985b7f73f0ed761fb87f4c3cb799006d.nq.gz
│   ├── 1d3e495f722c54c90865bfb5c7d6f5a2b0994345.nq.gz
│   ├── 25083b571d1b3e71ae564293f0ddd45d08145010.nq.gz
│   ├── 29cfe4c4e944fac7c18e6861f4f58282f14a4310.nq.gz
│   ├── 3a0e63bfd89a957adde1191ca0d33b25cc092513.nq.gz
│   ├── 3a934c612f0f8541a8c3ea43b212d119eb7dc7c8.nq.gz
│   ├── 3f7e53796c82edb14fac794427bf9dfdb9278176.nq.gz
│   ├── 52422e928ea3e3c2b98f5e14081977914952ec50.nq.gz
│   ├── 55b24d8cfdeefc2080a32c1fd72890776da6914b.nq.gz
│   ├── 5ed000352c8e7491a33a79e5cba1ed7c09f95ac2.nq.gz
│   ├── 6037d01940bc17a3cf4d2a4ebeece3938c1f6c07.nq.gz
│   ├── 676446558ce58915cf7067927a93e6b5d740eddc.nq.gz
│   ├── 6deafc261704e20369c0983af88042e502ae4880.nq.gz
│   ├── 816c45e62bc3c05880df5933e31ef0d56f617a7c.nq.gz
│   ├── 8950e594cdbbe714abcf79c4190dbe8a879c498e.nq.gz
│   ├── 95d5d93774260cda4351e8095af3a925c4528882.nq.gz
│   ├── a5da1d4230c22515a3b62411c3c333eac45b4ba2.nq.gz
│   └── f553996f857532a5c407157e3093ecc2c02bd44d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── bbdc50cd1d250742234aacc2d5da10c4fe4d9508.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 27 files
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

[scrapinghub/hcf-backend](https://github.com/scrapinghub/hcf-backend)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
