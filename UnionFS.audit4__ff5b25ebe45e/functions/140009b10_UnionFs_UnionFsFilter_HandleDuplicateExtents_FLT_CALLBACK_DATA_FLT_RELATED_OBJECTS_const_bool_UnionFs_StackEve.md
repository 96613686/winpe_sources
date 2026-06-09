# UnionFs::UnionFsFilter::HandleDuplicateExtents(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,bool *,UnionFs::StackEventTracer &,UnionFs::UfsStreamHandleCtx const *)

- ea: `0x140009b10`
- end: `0x14000a360`
- name: `?HandleDuplicateExtents@UnionFsFilter@UnionFs@@QEAAJPEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEA_NAEAVStackEventTracer@2@PEBVUfsStreamHandleCtx@2@@Z`
- size: `2128`
- prototype: `__int64 __fastcall(UnionFs::UnionFsFilter *__hidden this, struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, bool *, struct UnionFs::StackEventTracer *, const struct UnionFs::UfsStreamHandleCtx *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x14000ccb0`

## callees

- `0x140001008`
- `0x140005ff8`
- `0x140009b10`
- `0x14000bfd8`
- `0x140027a9c`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x14006ed2c`
- `0x14007b2b0`
- `0x14007baf0`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000a225`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a225`
- `ntoskrnl!ExAllocatePool2` at `0x14000a13a`
- `ntoskrnl!ExAllocatePool2` at `0x14000a13a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140009c4a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140009c4a`
- `ntoskrnl!IoFileObjectType` at `0x140009c12`
- `ntoskrnl!ObfDereferenceObject` at `0x140009c74`
- `ntoskrnl!ObfDereferenceObject` at `0x140009cbe`
- `ntoskrnl!ObfDereferenceObject` at `0x140009e9d`
- `ntoskrnl!ObfDereferenceObject` at `0x140009f28`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a04a`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a119`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a26c`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a32a`
- `ntoskrnl!ObfDereferenceObject` at `0x140009c74`
- `ntoskrnl!ObfDereferenceObject` at `0x140009cbe`
- `ntoskrnl!ObfDereferenceObject` at `0x140009e9d`
- `ntoskrnl!ObfDereferenceObject` at `0x140009f28`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a04a`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a119`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a26c`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a32a`
- `FLTMGR!FltFsControlFile` at `0x14000a1e0`
- `FLTMGR!FltFsControlFile` at `0x14000a1e0`
- `FLTMGR!FltReleaseContext` at `0x140009e61`
- `FLTMGR!FltReleaseContext` at `0x140009eec`
- `FLTMGR!FltReleaseContext` at `0x14000a012`
- `FLTMGR!FltReleaseContext` at `0x14000a0dd`
- `FLTMGR!FltReleaseContext` at `0x14000a234`
- `FLTMGR!FltReleaseContext` at `0x14000a2af`
- `FLTMGR!FltReleaseContext` at `0x14000a2ee`
- `FLTMGR!FltReleaseContext` at `0x140009e61`
- `FLTMGR!FltReleaseContext` at `0x140009eec`
- `FLTMGR!FltReleaseContext` at `0x14000a012`
- `FLTMGR!FltReleaseContext` at `0x14000a0dd`
- `FLTMGR!FltReleaseContext` at `0x14000a234`
- `FLTMGR!FltReleaseContext` at `0x14000a2af`
- `FLTMGR!FltReleaseContext` at `0x14000a2ee`
- `FLTMGR!FltObjectDereference` at `0x140009d1d`
- `FLTMGR!FltObjectDereference` at `0x140009db0`
- `FLTMGR!FltObjectDereference` at `0x140009e7e`
- `FLTMGR!FltObjectDereference` at `0x140009f09`
- `FLTMGR!FltObjectDereference` at `0x14000a02f`
- `FLTMGR!FltObjectDereference` at `0x14000a0fa`
- `FLTMGR!FltObjectDereference` at `0x14000a251`
- `FLTMGR!FltObjectDereference` at `0x14000a2cc`
- `FLTMGR!FltObjectDereference` at `0x14000a30b`
- `FLTMGR!FltObjectDereference` at `0x140009d1d`
- `FLTMGR!FltObjectDereference` at `0x140009db0`
- `FLTMGR!FltObjectDereference` at `0x140009e7e`
- `FLTMGR!FltObjectDereference` at `0x140009f09`
- `FLTMGR!FltObjectDereference` at `0x14000a02f`
- `FLTMGR!FltObjectDereference` at `0x14000a0fa`
- `FLTMGR!FltObjectDereference` at `0x14000a251`
- `FLTMGR!FltObjectDereference` at `0x14000a2cc`
- `FLTMGR!FltObjectDereference` at `0x14000a30b`

## string_xrefs

- `0x140009b61`: `Write Operation on SFO`
- `0x140009b6d`: `ORIGIN: Write operation on SFO`

## pseudocode

```c

```
