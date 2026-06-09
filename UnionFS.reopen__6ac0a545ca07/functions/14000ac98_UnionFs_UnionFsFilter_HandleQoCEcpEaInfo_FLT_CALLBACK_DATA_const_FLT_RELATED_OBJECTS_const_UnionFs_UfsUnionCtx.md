# UnionFs::UnionFsFilter::HandleQoCEcpEaInfo(_FLT_CALLBACK_DATA const &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsUnionCtx &,_QUERY_ON_CREATE_ECP_CONTEXT *,UnionFs::StackEventTracer &)

- ea: `0x14000ac98`
- end: `0x14000afb4`
- name: `?HandleQoCEcpEaInfo@UnionFsFilter@UnionFs@@AEAAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAVUfsUnionCtx@2@PEAU_QUERY_ON_CREATE_ECP_CONTEXT@@AEAVStackEventTracer@2@@Z`
- size: `796`
- prototype: `__int64 __fastcall(UnionFs::UnionFsFilter *__hidden this, const struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, struct UnionFs::UfsUnionCtx *, struct _QUERY_ON_CREATE_ECP_CONTEXT *, struct UnionFs::StackEventTracer *)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x14000a798`
- `0x140013b60`
- `0x14001568c`

## callees

- `0x14000ac98`
- `0x14000f81c`
- `0x140022020`
- `0x140023a10`
- `0x140056c44`
- `0x140056c7c`
- `0x14006e394`
- `0x14007b2b0`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000af1c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000af1c`
- `ntoskrnl!ExAllocatePool2` at `0x14000ae8b`
- `ntoskrnl!ExAllocatePool2` at `0x14000ae8b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000adae`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000ae24`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000af6f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000adae`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000ae24`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000af6f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000adba`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ae30`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000af7b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000adba`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ae30`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000af7b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000ad20`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000ae56`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000afa1`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000ad20`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000ae56`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000afa1`

## pseudocode

```c

```
