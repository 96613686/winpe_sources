# UnionFs::UnionFsFilter::QueryBackingEAsForQoC(_FLT_INSTANCE const &,_FILE_OBJECT const &,_QUERY_ON_CREATE_ECP_CONTEXT *,UnionFs::StackEventTracer &)

- ea: `0x14000ed24`
- end: `0x14000eef8`
- name: `?QueryBackingEAsForQoC@UnionFsFilter@UnionFs@@AEAAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@PEAU_QUERY_ON_CREATE_ECP_CONTEXT@@AEAVStackEventTracer@2@@Z`
- size: `468`
- prototype: `__int64 __fastcall(UnionFs::UnionFsFilter *this, const struct _FLT_INSTANCE *, struct _FILE_OBJECT *, struct _QUERY_ON_CREATE_ECP_CONTEXT *, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000a798`

## callees

- `0x14000ed24`
- `0x140056bd0`
- `0x140056c44`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000ee91`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ee91`
- `ntoskrnl!ExAllocatePool2` at `0x14000ede2`
- `ntoskrnl!ExAllocatePool2` at `0x14000ede2`
- `FLTMGR!FltQueryInformationFile` at `0x14000ed66`
- `FLTMGR!FltQueryInformationFile` at `0x14000ed66`
- `FLTMGR!FltQueryEaFile` at `0x14000ee4e`
- `FLTMGR!FltQueryEaFile` at `0x14000ee4e`

## pseudocode

```c

```
