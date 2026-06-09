# UnionFs::UfsUnionCtx::AddRootNodeToPathCache(UnionFs::StackEventTracer &)

- ea: `0x14005e200`
- end: `0x14005e464`
- name: `?AddRootNodeToPathCache@UfsUnionCtx@UnionFs@@AEAAJAEAVStackEventTracer@2@@Z`
- size: `612`
- prototype: `int(UnionFs::UfsUnionCtx *__hidden this, struct UnionFs::StackEventTracer *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x14005c250`
- `0x140062e54`

## callees

- `0x14000f7fc`
- `0x14003c734`
- `0x140040e6c`
- `0x140056afc`
- `0x14005e200`
- `0x140079a24`
- `0x140079da0`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14005e3d3`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e427`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e3d3`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e427`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e3df`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e433`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e3df`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e433`

## string_xrefs

- `0x14005e23c`: `PUSH: Allocating cache root node`
- `0x14005e386`: `PUSH: Inserting path cache root node`
- `0x14005e24d`: `UnionFs::UfsUnionCtx::AddRootNodeToPathCache`
- `0x14005e397`: `UnionFs::UfsUnionCtx::AddRootNodeToPathCache`

## pseudocode

```c

```
