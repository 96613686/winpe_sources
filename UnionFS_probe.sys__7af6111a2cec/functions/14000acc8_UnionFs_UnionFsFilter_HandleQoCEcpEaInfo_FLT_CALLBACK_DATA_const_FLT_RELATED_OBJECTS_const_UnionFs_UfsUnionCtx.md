# UnionFs::UnionFsFilter::HandleQoCEcpEaInfo(_FLT_CALLBACK_DATA const &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsUnionCtx &,_QUERY_ON_CREATE_ECP_CONTEXT *,UnionFs::StackEventTracer &)

- ea: `0x14000acc8`
- end: `0x14000afe4`
- name: `?HandleQoCEcpEaInfo@UnionFsFilter@UnionFs@@AEAAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAVUfsUnionCtx@2@PEAU_QUERY_ON_CREATE_ECP_CONTEXT@@AEAVStackEventTracer@2@@Z`
- size: `796`
- prototype: `__int64 __fastcall(UnionFs::UnionFsFilter *__hidden this, const struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, struct UnionFs::UfsUnionCtx *, struct _QUERY_ON_CREATE_ECP_CONTEXT *, struct UnionFs::StackEventTracer *)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x14000a7c8`
- `0x140013bb0`
- `0x1400156a8`

## callees

- `0x14000acc8`
- `0x14000f7fc`
- `0x140021f80`
- `0x140023970`
- `0x140056ac4`
- `0x140056afc`
- `0x14006e1a4`
- `0x14007af90`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000af4c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000af4c`
- `ntoskrnl!ExAllocatePool2` at `0x14000aebb`
- `ntoskrnl!ExAllocatePool2` at `0x14000aebb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000adde`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000ae54`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000af9f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000adde`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000ae54`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000af9f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000adea`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ae60`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000afab`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000adea`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ae60`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000afab`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000ad50`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000ae86`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000afd1`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000ad50`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000ae86`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000afd1`

## pseudocode

```c

```
