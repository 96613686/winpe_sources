# UnionFs::UfsPathCache::AddToCacheListAfterInsertion(UnionFs::UfsPathCachePayload &,_FLT_INSTANCE const &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &&,UnionFs::StackEventTracer &)

- ea: `0x14003c20c`
- end: `0x14003c366`
- name: `?AddToCacheListAfterInsertion@UfsPathCache@UnionFs@@AEAAJAEAVUfsPathCachePayload@2@AEBU_FLT_INSTANCE@@$$QEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `346`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14003c854`

## callees

- `0x14003c20c`
- `0x140041490`
- `0x140056c7c`
- `0x140079cc4`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14003c323`
- `ntoskrnl!ExReleaseFastMutex` at `0x14003c323`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003c301`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003c342`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003c301`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003c342`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003c30d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003c34e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003c30d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003c34e`

## string_xrefs

- `0x14003c239`: `PUSH: Allocating cache control`
- `0x14003c24a`: `UnionFs::UfsPathCache::AddToCacheListAfterInsertion`

## pseudocode

```c

```
