# UnionFs::UfsPathCache::AddToCacheListAfterInsertion(UnionFs::UfsPathCachePayload &,_FLT_INSTANCE const &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &&,UnionFs::StackEventTracer &)

- ea: `0x14003c0ec`
- end: `0x14003c246`
- name: `?AddToCacheListAfterInsertion@UfsPathCache@UnionFs@@AEAAJAEAVUfsPathCachePayload@2@AEBU_FLT_INSTANCE@@$$QEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `346`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14003c734`

## callees

- `0x14003c0ec`
- `0x140041308`
- `0x140056afc`
- `0x1400799a4`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14003c203`
- `ntoskrnl!ExReleaseFastMutex` at `0x14003c203`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003c1e1`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003c222`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003c1e1`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003c222`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003c1ed`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003c22e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003c1ed`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003c22e`

## string_xrefs

- `0x14003c119`: `PUSH: Allocating cache control`
- `0x14003c12a`: `UnionFs::UfsPathCache::AddToCacheListAfterInsertion`

## pseudocode

```c

```
