# UnionFs::UnionFsFilter::SetPurgeFailureMode(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,bool *,UnionFs::StackEventTracer &,UnionFs::UfsStreamHandleCtx const *)

- ea: `0x14000f06c`
- end: `0x14000f23a`
- name: `?SetPurgeFailureMode@UnionFsFilter@UnionFs@@QEAAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@PEA_NAEAVStackEventTracer@2@PEBVUfsStreamHandleCtx@2@@Z`
- size: `462`
- prototype: `__int64 __fastcall(UnionFs::UnionFsFilter *__hidden this, struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, bool *, struct UnionFs::StackEventTracer *, const struct UnionFs::UfsStreamHandleCtx *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000cce0`

## callees

- `0x14000f06c`
- `0x140056ac4`
- `0x140079a6c`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14000f16f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000f1d7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000f213`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000f16f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000f1d7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000f213`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f17b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f1e3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f21f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f17b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f1e3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f21f`

## string_xrefs

- `0x14000f0af`: `ORIGIN: SetPurgeFailure on directory`
- `0x14000f187`: `ORIGIN: Purge failure mode enable count already MAXULONG`
- `0x14000f1ef`: `ORIGIN: Purge failure mode enable count alread 0`

## pseudocode

```c

```
