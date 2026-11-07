# Repolex Knowledge Graph of fastai/ulms

RDF knowledge graph data for [fastai/ulms](https://github.com/fastai/ulms), parsed by [repolex](https://repolex.ai).

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
rlex download fastai/ulms
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d349777284725678de65b81d9fd37eb97a85d957
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── d349777284725678de65b81d9fd37eb97a85d957
│           └── chunk-001.nq.gz
├── blob
│   ├── 00329277a194878e301e1ac62e069ef7aca58737.nq.gz
│   ├── 061f0e647c985b7662bcc59d1a5465c23d51fca8.nq.gz
│   ├── 1671092357f47d08376e01d0c2368a8885bf29ad.nq.gz
│   ├── 1db68b542e6ceb9635a200cdd201c6b5a2cc4497.nq.gz
│   ├── 22b1a1ff7046c565f2bc81350f00d64205919dc2.nq.gz
│   ├── 2d213bdadac9691e86e02d66f491c558ce1c772f.nq.gz
│   ├── 3b80e0f1f87a24651efc3bdc4fa46258d98e09ca.nq.gz
│   ├── 51264c4fda25feadb007e30ab69bf9b0ddfc1cee.nq.gz
│   ├── 51b8d59174d6e88a01a395b1ff17c1b8b146f227.nq.gz
│   ├── 59e7a5d86707fe4023991fcfbfc95a1b1983e6c5.nq.gz
│   ├── 6134b780a578d98cf925ed28ea97fd835c2d7a68.nq.gz
│   ├── 6cfb6647f6bd089275a8fc3c6dbec09d9f839d1f.nq.gz
│   ├── 702d6e78f6a7b7fc12e41c85d2ec1f08a89f2b13.nq.gz
│   ├── 77701959470914384b60c38e84c2a30c0eb06782.nq.gz
│   ├── 7ba6e73d48999a1de3586a4dbe22b250ca9b0558.nq.gz
│   ├── 82a5ed607a157f2c7c81b7f2a18ed5d50df12f8d.nq.gz
│   ├── 842e3a139fa6961146978e41e60747ad1a041d7f.nq.gz
│   ├── 8ad81996ef9e77235081cad58d7c138c320b4487.nq.gz
│   ├── 936945e2bad2b4965817331390ec5db0a4c5264f.nq.gz
│   ├── adc45374d59eeae2c34807bdbc3685c39a1162b0.nq.gz
│   ├── bbe8fb3c3a3fe02ad38d8ce1959eae67d9639298.nq.gz
│   ├── bc59dde14a64905fd145374fda9a89aeb40e75fa.nq.gz
│   ├── d4e42c8966963d9ef35b8947d181c1b7e42e4243.nq.gz
│   ├── d6e721aaef82287c96e52d19866ee0d80c51fccc.nq.gz
│   ├── d98ff6054dee550d713288ed87dc95c9532d0a7f.nq.gz
│   ├── dc30d398c05632fba404ed875fa33ddeb0065c73.nq.gz
│   ├── e39309235189d679c91872805d0b1e0a4f492b3d.nq.gz
│   ├── ee8d253f06461e89e7ce08b4e9ea2bb6402a24fd.nq.gz
│   ├── ef3789b309adb2d20aed19b41b32a8e4722ad194.nq.gz
│   ├── f41b75f1e365704b5fed1b2c0be91c3421e5def5.nq.gz
│   ├── f459be0920f436f1501f152637a7359a138428bc.nq.gz
│   └── fd7fa03e788cf503b6ddb95272218d7e405c361f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d349777284725678de65b81d9fd37eb97a85d957.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 39 files
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

[fastai/ulms](https://github.com/fastai/ulms)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
