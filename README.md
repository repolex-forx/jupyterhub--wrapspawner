# Repolex Knowledge Graph of jupyterhub/wrapspawner

RDF knowledge graph data for [jupyterhub/wrapspawner](https://github.com/jupyterhub/wrapspawner), parsed by [repolex](https://repolex.ai).

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
rlex download jupyterhub/wrapspawner
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── cb74046aa0217cf48c76944fae2d8c0cbae2a701
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── cb74046aa0217cf48c76944fae2d8c0cbae2a701
│           └── chunk-001.nq.gz
├── blob
│   ├── 293d9460dd8dcea9a8302484ebab3fff1ae8de40.nq.gz
│   ├── 29a1df669473fe87f214356b03c38477ec5977ec.nq.gz
│   ├── 2afaa9d72128b1841b4deee028bd41d8027d9002.nq.gz
│   ├── 3730402c03084dc9916e1276feaca43280278633.nq.gz
│   ├── 3a5b89776d25b41282bd635cd85645404ebd1ac7.nq.gz
│   ├── 4325113b825a9cefed4ac49604e1edf44683e2b8.nq.gz
│   ├── 66f8edacec934885cd72cde6b4092a3007b9d1e3.nq.gz
│   ├── 72364f99fe4bf8d5262df3b19b33102aeaa791e5.nq.gz
│   ├── 815a9af14e2dd40f998a82afe49089c84b973810.nq.gz
│   ├── 9eb375cc44c2174e3f657f41e0c578e092689e28.nq.gz
│   ├── ada8b301610919e6108904256a39d6f9b526dda2.nq.gz
│   ├── be86e844c1298db605cb0fb74282e9809a24557d.nq.gz
│   └── cc682dd0dcc5190eea67050ef665193a24726fef.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── cb74046aa0217cf48c76944fae2d8c0cbae2a701.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 21 files
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

[jupyterhub/wrapspawner](https://github.com/jupyterhub/wrapspawner)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
