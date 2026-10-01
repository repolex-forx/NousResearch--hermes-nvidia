# Repolex Knowledge Graph of NousResearch/hermes-nvidia

RDF knowledge graph data for [NousResearch/hermes-nvidia](https://github.com/NousResearch/hermes-nvidia), parsed by [repolex](https://repolex.ai).

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
rlex download NousResearch/hermes-nvidia
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e35b7429532c3e3fb7b4d9fea9c18e2c14740afa
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── e35b7429532c3e3fb7b4d9fea9c18e2c14740afa.nq.gz
│   └── repolex
│       └── e35b7429532c3e3fb7b4d9fea9c18e2c14740afa
│           └── chunk-001.nq.gz
├── blob
│   ├── 0bdf659c9460b1101914552be810d95963b1b6fd.nq.gz
│   ├── 0cde0fa3ecd38ea6aea6735277f08483d76f0b43.nq.gz
│   ├── 176c19de13ccff21d905735da957afb191e24ffd.nq.gz
│   ├── 20ed93fbcd49398ab5cd3514323d04fc198ab43f.nq.gz
│   ├── 22ec929aaed16166b31c1980dfe478a785f85031.nq.gz
│   ├── 25db2d730ad6fc21ae01c73f878edb586580e111.nq.gz
│   ├── 2b0b2ef86f24dec989cdd94324b97bada03b4522.nq.gz
│   ├── 32ef1a809f6d0c8e1f3c27d6687446d2d413b23d.nq.gz
│   ├── 3bc2ebc2fcccbf94c4e9457f7ea26044c6f5c1cc.nq.gz
│   ├── 649ddf78924f0c4f236dd3cf1b0a8631ba8b8b0b.nq.gz
│   ├── 95c5afccb3d96d75b7f38c7fcb14813697181779.nq.gz
│   ├── a975f509286590935f0338069ec5d5c8adfbe3fe.nq.gz
│   ├── b3a4a6b159a11a585ca87b213e2bb60abbf300fb.nq.gz
│   ├── bbb249f42944d6b4e53372b22a33041febc774e9.nq.gz
│   ├── d07d1eff9dfad578d2eab76b0e897ac7d30bc24a.nq.gz
│   ├── e1b4150ef71493a0b6d775b35f5f0678a6214dca.nq.gz
│   ├── e9e39697cf0da06fa1b8a312ae3c78de94748e02.nq.gz
│   ├── f055a535c0a266b45004dcf478978456b4b7b050.nq.gz
│   ├── f5b24ec25c6a4493accfddc491b36577609edc69.nq.gz
│   └── f7a83e9d8b97055ceb6e3f09ad083b2a25ff115a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── e35b7429532c3e3fb7b4d9fea9c18e2c14740afa.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 28 files
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

[NousResearch/hermes-nvidia](https://github.com/NousResearch/hermes-nvidia)

---
*Parsed on 2026-10-01 by [repolex](https://repolex.ai)*
