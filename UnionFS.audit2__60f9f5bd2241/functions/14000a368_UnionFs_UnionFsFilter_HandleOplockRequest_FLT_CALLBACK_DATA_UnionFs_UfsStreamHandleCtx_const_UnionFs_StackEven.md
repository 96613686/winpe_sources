# UnionFs::UnionFsFilter::HandleOplockRequest(_FLT_CALLBACK_DATA &,UnionFs::UfsStreamHandleCtx const &,UnionFs::StackEventTracer &)

- ea: `0x14000a368`
- end: `0x14000a790`
- name: `?HandleOplockRequest@UnionFsFilter@UnionFs@@QEAAJAEAU_FLT_CALLBACK_DATA@@AEBVUfsStreamHandleCtx@2@AEAVStackEventTracer@2@@Z`
- size: `1064`
- prototype: `int(UnionFs::UnionFsFilter *__hidden this, struct _FLT_CALLBACK_DATA *, const struct UnionFs::UfsStreamHandleCtx *, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x14000ccb0`

## callees

- `0x14000a368`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x140058bb0`
- `0x14006f124`
- `0x140079cc4`
- `0x140079d8c`
- `0x140079dd4`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14000a6a4`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14000a6a4`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000a5ac`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000a65c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000a5ac`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000a65c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000a522`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000a522`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000a52e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000a52e`
- `FLTMGR!FltOplockIsSharedRequest` at `0x14000a3b8`
- `FLTMGR!FltOplockIsSharedRequest` at `0x14000a3b8`
- `FLTMGR!FltOplockFsctrlEx` at `0x14000a708`
- `FLTMGR!FltOplockFsctrlEx` at `0x14000a708`

## string_xrefs

- `0x14000a3e9`: `ORIGIN: Invalid oplock request on directory.`
- `0x14000a4ee`: `ORIGIN: Cannot grant handle oplock on delete-pending file`

## pseudocode

```c

```
