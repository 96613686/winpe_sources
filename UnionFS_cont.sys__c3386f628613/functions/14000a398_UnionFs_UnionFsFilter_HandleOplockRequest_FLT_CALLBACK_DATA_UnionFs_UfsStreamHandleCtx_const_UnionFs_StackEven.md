# UnionFs::UnionFsFilter::HandleOplockRequest(_FLT_CALLBACK_DATA &,UnionFs::UfsStreamHandleCtx const &,UnionFs::StackEventTracer &)

- ea: `0x14000a398`
- end: `0x14000a7c0`
- name: `?HandleOplockRequest@UnionFsFilter@UnionFs@@QEAAJAEAU_FLT_CALLBACK_DATA@@AEBVUfsStreamHandleCtx@2@AEAVStackEventTracer@2@@Z`
- size: `1064`
- prototype: `int(UnionFs::UnionFsFilter *__hidden this, struct _FLT_CALLBACK_DATA *, const struct UnionFs::UfsStreamHandleCtx *, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x14000cce0`

## callees

- `0x14000a398`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x140058a30`
- `0x14006ef34`
- `0x1400799a4`
- `0x140079a6c`
- `0x140079ab4`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14000a6d4`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14000a6d4`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000a5dc`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000a68c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000a5dc`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000a68c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000a552`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000a552`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000a55e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000a55e`
- `FLTMGR!FltOplockIsSharedRequest` at `0x14000a3e8`
- `FLTMGR!FltOplockIsSharedRequest` at `0x14000a3e8`
- `FLTMGR!FltOplockFsctrlEx` at `0x14000a738`
- `FLTMGR!FltOplockFsctrlEx` at `0x14000a738`

## string_xrefs

- `0x14000a419`: `ORIGIN: Invalid oplock request on directory.`
- `0x14000a51e`: `ORIGIN: Cannot grant handle oplock on delete-pending file`

## pseudocode

```c

```
