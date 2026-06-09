# UnionFs::Utils::MarkFileAsDeleteCandidateIfInLayer(_FLT_CALLBACK_DATA const &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsStreamHandleCtx const &,UnionFs::UfsFileCtx &,UnionFs::StackEventTracer &)

- ea: `0x14007059c`
- end: `0x140070838`
- name: `?MarkFileAsDeleteCandidateIfInLayer@Utils@UnionFs@@YAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEBVUfsStreamHandleCtx@2@AEAVUfsFileCtx@2@AEAVStackEventTracer@2@@Z`
- size: `668`
- prototype: `__int64 __usercall@<rax>(struct _FLT_CALLBACK_DATA *this@<rcx>, const struct _FLT_CALLBACK_DATA *@<rdx>, const struct _FLT_RELATED_OBJECTS *@<r8>, const struct UnionFs::UfsStreamHandleCtx *@<r9>, struct UnionFs::UfsFileCtx *, struct UnionFs::StackEventTracer *)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x1400319bc`
- `0x140074b3c`

## callees

- `0x14000f7fc`
- `0x140010b88`
- `0x14002accc`
- `0x140056ac4`
- `0x140056afc`
- `0x140061090`
- `0x14006e1a4`
- `0x1400703f0`
- `0x14007059c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14007072e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400707af`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007072e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400707af`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140070747`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400707c8`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140070811`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140070747`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400707c8`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140070811`

## string_xrefs

- `0x140070609`: `UnionFs::Utils::MarkFileAsDeleteCandidateIfInLayer`
- `0x140070700`: `UnionFs::Utils::MarkFileAsDeleteCandidateIfInLayer`
- `0x1400707eb`: `UnionFs::Utils::MarkFileAsDeleteCandidateIfInLayer`
- `0x140070781`: `PUSH: PrepareForDelete`

## pseudocode

```c

```
