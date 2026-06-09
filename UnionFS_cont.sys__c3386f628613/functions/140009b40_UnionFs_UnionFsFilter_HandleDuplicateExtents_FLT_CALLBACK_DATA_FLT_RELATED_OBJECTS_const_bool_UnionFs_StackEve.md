# UnionFs::UnionFsFilter::HandleDuplicateExtents(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,bool *,UnionFs::StackEventTracer &,UnionFs::UfsStreamHandleCtx const *)

- ea: `0x140009b40`
- end: `0x14000a390`
- name: `?HandleDuplicateExtents@UnionFsFilter@UnionFs@@QEAAJPEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEA_NAEAVStackEventTracer@2@PEBVUfsStreamHandleCtx@2@@Z`
- size: `2128`
- prototype: `__int64 __fastcall(UnionFs::UnionFsFilter *__hidden this, struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, bool *, struct UnionFs::StackEventTracer *, const struct UnionFs::UfsStreamHandleCtx *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x14000cce0`

## callees

- `0x140001008`
- `0x140005ff8`
- `0x140009b40`
- `0x14000c008`
- `0x1400279fc`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x14006eb3c`
- `0x14007af90`
- `0x14007b7d0`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000a255`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a255`
- `ntoskrnl!ExAllocatePool2` at `0x14000a16a`
- `ntoskrnl!ExAllocatePool2` at `0x14000a16a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140009c7a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140009c7a`
- `ntoskrnl!IoFileObjectType` at `0x140009c42`
- `ntoskrnl!ObfDereferenceObject` at `0x140009ca4`
- `ntoskrnl!ObfDereferenceObject` at `0x140009cee`
- `ntoskrnl!ObfDereferenceObject` at `0x140009ecd`
- `ntoskrnl!ObfDereferenceObject` at `0x140009f58`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a07a`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a149`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a29c`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a35a`
- `ntoskrnl!ObfDereferenceObject` at `0x140009ca4`
- `ntoskrnl!ObfDereferenceObject` at `0x140009cee`
- `ntoskrnl!ObfDereferenceObject` at `0x140009ecd`
- `ntoskrnl!ObfDereferenceObject` at `0x140009f58`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a07a`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a149`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a29c`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a35a`
- `FLTMGR!FltFsControlFile` at `0x14000a210`
- `FLTMGR!FltFsControlFile` at `0x14000a210`
- `FLTMGR!FltReleaseContext` at `0x140009e91`
- `FLTMGR!FltReleaseContext` at `0x140009f1c`
- `FLTMGR!FltReleaseContext` at `0x14000a042`
- `FLTMGR!FltReleaseContext` at `0x14000a10d`
- `FLTMGR!FltReleaseContext` at `0x14000a264`
- `FLTMGR!FltReleaseContext` at `0x14000a2df`
- `FLTMGR!FltReleaseContext` at `0x14000a31e`
- `FLTMGR!FltReleaseContext` at `0x140009e91`
- `FLTMGR!FltReleaseContext` at `0x140009f1c`
- `FLTMGR!FltReleaseContext` at `0x14000a042`
- `FLTMGR!FltReleaseContext` at `0x14000a10d`
- `FLTMGR!FltReleaseContext` at `0x14000a264`
- `FLTMGR!FltReleaseContext` at `0x14000a2df`
- `FLTMGR!FltReleaseContext` at `0x14000a31e`
- `FLTMGR!FltObjectDereference` at `0x140009d4d`
- `FLTMGR!FltObjectDereference` at `0x140009de0`
- `FLTMGR!FltObjectDereference` at `0x140009eae`
- `FLTMGR!FltObjectDereference` at `0x140009f39`
- `FLTMGR!FltObjectDereference` at `0x14000a05f`
- `FLTMGR!FltObjectDereference` at `0x14000a12a`
- `FLTMGR!FltObjectDereference` at `0x14000a281`
- `FLTMGR!FltObjectDereference` at `0x14000a2fc`
- `FLTMGR!FltObjectDereference` at `0x14000a33b`
- `FLTMGR!FltObjectDereference` at `0x140009d4d`
- `FLTMGR!FltObjectDereference` at `0x140009de0`
- `FLTMGR!FltObjectDereference` at `0x140009eae`
- `FLTMGR!FltObjectDereference` at `0x140009f39`
- `FLTMGR!FltObjectDereference` at `0x14000a05f`
- `FLTMGR!FltObjectDereference` at `0x14000a12a`
- `FLTMGR!FltObjectDereference` at `0x14000a281`
- `FLTMGR!FltObjectDereference` at `0x14000a2fc`
- `FLTMGR!FltObjectDereference` at `0x14000a33b`

## string_xrefs

- `0x140009b91`: `Write Operation on SFO`
- `0x140009b9d`: `ORIGIN: Write operation on SFO`

## pseudocode

```c

```
