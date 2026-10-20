# Repolex Knowledge Graph of simonw/datasette-cors

RDF knowledge graph data for [simonw/datasette-cors](https://github.com/simonw/datasette-cors), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/datasette-cors
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f22b38ff3c50cd395b95968960ef9a5bb49c5465
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── f22b38ff3c50cd395b95968960ef9a5bb49c5465
│           └── chunk-001.nq.gz
├── blob
│   ├── 1f12dfc68debf9a70e62722c5e1cc9bac95e0ea5.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 4e8f5979e33c473fd7ca50cd08c42e40360f1f46.nq.gz
│   ├── 6ddd2cd1ba6ace773d865fa122008bf176ccffc5.nq.gz
│   ├── 99b7012ab0fde92292d328bd6d6a81d9c4021359.nq.gz
│   ├── af7c122cca11c576857eebc8a31a623d43182de9.nq.gz
│   ├── c8b1f19dc749a2848231d75a2a29f460efb20e78.nq.gz
│   └── cebc018ec7aad2ac16ff3dbdaffdc1a4e2f5ebe5.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── f22b38ff3c50cd395b95968960ef9a5bb49c5465.nq.gz
├── issue
│   └── issue.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 15 files
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

[simonw/datasette-cors](https://github.com/simonw/datasette-cors)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
