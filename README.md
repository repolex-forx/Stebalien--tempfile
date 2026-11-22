# Repolex Knowledge Graph of Stebalien/tempfile

RDF knowledge graph data for [Stebalien/tempfile](https://github.com/Stebalien/tempfile), parsed by [repolex](https://repolex.ai).

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
rlex download Stebalien/tempfile
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5c8fa12eb584931b4f1bccfde87eb72fbfa7dc61
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 5c8fa12eb584931b4f1bccfde87eb72fbfa7dc61.nq.gz
│   └── repolex
│       └── 5c8fa12eb584931b4f1bccfde87eb72fbfa7dc61
│           └── chunk-001.nq.gz
├── blob
│   ├── 08b1606cae7e1888ac7c07cd94aa4db18c806a0c.nq.gz
│   ├── 0c3270fdd1530e101f6cd8f3e9bb28ce2442812d.nq.gz
│   ├── 16fe87b06e802f094b3fbb0894b137bca2b16ef1.nq.gz
│   ├── 21cfeb7ebddb7720ab48f40dbee03de1ddf1e250.nq.gz
│   ├── 26d0a227387e2553000b3562417b43f91ebb7cf2.nq.gz
│   ├── 3ef149d6fba969c516b7d54540214aa69a207d8a.nq.gz
│   ├── 4276b9ad4581f9b9380e85a024f9c3bd2bb6f6c8.nq.gz
│   ├── 47317a8f2088cc0e1c576d79148c2a14de0d0fc0.nq.gz
│   ├── 54f305e984d6c40f61ac4a7153d9db6689f8002b.nq.gz
│   ├── 57ba9bead4fc364df30d888f2de1ab577c6dffd7.nq.gz
│   ├── 5ab5c0a169940b4a83b9e25832aea8aab5ec2d39.nq.gz
│   ├── 5dff328a5398d46d76f7072920cd910596b6e7e6.nq.gz
│   ├── 722b7391f8060a253d5b7b6320d32769208fa700.nq.gz
│   ├── 8737edd27d77c80d9c90d52d15bfde07ffcf3977.nq.gz
│   ├── 8a00f201ecb15504fc2e78bc04e8320047616278.nq.gz
│   ├── 8d245c5fed53a34d84b45f215b5dee957be6a00f.nq.gz
│   ├── 913ff93690c8739b6cac0d76895660ee822cfa74.nq.gz
│   ├── 93a8d7ccb8df70ad910791375ed682425add6d52.nq.gz
│   ├── 987791e1477243b80a8ec766dfef4fb60ed2bf14.nq.gz
│   ├── 98e44ee5f7942cdf11562b935a4e23cb0299880e.nq.gz
│   ├── a9d37c560c6ab8d4afbf47eda643e8c42e857716.nq.gz
│   ├── b210a421a3b2976e05b6054831b01ae754323dbb.nq.gz
│   ├── ba0dd6ecefc91c190cbfd7afa00590b03e740461.nq.gz
│   ├── bba36712a25f9f0fcfa041273b1ec8cc9ecc8fae.nq.gz
│   ├── cccd543d922dda6855480fbc232d8b00045d93fe.nq.gz
│   ├── cfbb4b54f74601205ea5124ccb8e6d9526efec9a.nq.gz
│   ├── d2b5ec2083c2e33b2986fa4ba1776c825907d6bb.nq.gz
│   ├── d913ff68efe5efe183e7e490d69466e5026b0511.nq.gz
│   ├── e938d87c2ad3a27b18fe5cc50977aceaace7785d.nq.gz
│   ├── ed6b6cc8d13236f9e14c59f4539cc0d894cb94b0.nq.gz
│   └── f10c83340c87b567e4ea5cefd2e47fcd9fa0ca36.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 5c8fa12eb584931b4f1bccfde87eb72fbfa7dc61.nq.gz
├── filetree
│   └── 5c8fa12eb584931b4f1bccfde87eb72fbfa7dc61.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 41 files
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

[Stebalien/tempfile](https://github.com/Stebalien/tempfile)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
