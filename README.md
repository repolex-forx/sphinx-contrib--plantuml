# Repolex Knowledge Graph of sphinx-contrib/plantuml

RDF knowledge graph data for [sphinx-contrib/plantuml](https://github.com/sphinx-contrib/plantuml), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/plantuml
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 42bf035f32438b97942368c2e19af6f13aaa58ca
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 42bf035f32438b97942368c2e19af6f13aaa58ca
│           └── chunk-001.nq.gz
├── blob
│   ├── 158e895f6f6ad70627331655169bc629ac3f42cf.nq.gz
│   ├── 170e0a1ffdf5a04c1f4988cd7009915fd9c1f662.nq.gz
│   ├── 23826ac409391c37c5f76974baa7ad9ce6f0c421.nq.gz
│   ├── 35d34fc53bde73a52472b7e1cfce9b183d7aaa66.nq.gz
│   ├── 38d9925e3badf2b6abc03d8d81c0fb37c9abd530.nq.gz
│   ├── 45dd5f5b51e10661a6b6699e050c4ab23d721804.nq.gz
│   ├── 7433e9ee03f22fc5355e08a2c173310adee42148.nq.gz
│   ├── 7a0c222b1ea10f486e8d562f2a3ed8ff115ef38b.nq.gz
│   ├── 7bd89d418fd6e9aa467217d46fd371e859146d70.nq.gz
│   ├── 820684d3cd5f7b01369aad1e8edf41b8a068ba68.nq.gz
│   ├── 8efc240a7366301a4d8f36a6a23ee7bd494ab09a.nq.gz
│   ├── 94a57a3e1cc7255a9d7d96c17d2ad0ebeb996c11.nq.gz
│   ├── 952cf5402ecd86e8083cbdeba2093b426b8a4729.nq.gz
│   ├── 9a0f8ba059065a676f89757d857eda48e5cbd293.nq.gz
│   ├── a25901f9303559368f84122b38ed8a45104d2293.nq.gz
│   ├── a5316d49a0550888902b341fbbe393d43651799a.nq.gz
│   ├── b24802d202ce53bf9ee8fd6dee5cca2928c79854.nq.gz
│   ├── d92be46593b46eb0a92561aeb6cf74a16bebfcec.nq.gz
│   ├── dd084de2eb7d56e3606063879b9257bb54cb28b7.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ff3268e6f00a3aac3e25ca5284cdba8ca6075fe0.nq.gz
│   └── ffa15da65ec7ec989bcb07d0f26c93fabd320f3a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 42bf035f32438b97942368c2e19af6f13aaa58ca.nq.gz
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

[sphinx-contrib/plantuml](https://github.com/sphinx-contrib/plantuml)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
