# UnionFs::Utils::MarkFileAsDeleteCandidateIfInLayer(_FLT_CALLBACK_DATA const &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsStreamHandleCtx const &,UnionFs::UfsFileCtx &,UnionFs::StackEventTracer &)

- ea: `0x14007078c`
- end: `0x140070a28`
- name: `?MarkFileAsDeleteCandidateIfInLayer@Utils@UnionFs@@YAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEBVUfsStreamHandleCtx@2@AEAVUfsFileCtx@2@AEAVStackEventTracer@2@@Z`
- size: `668`
- prototype: `__int64 __fastcall(struct _FLT_CALLBACK_DATA *this, const struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, const struct UnionFs::UfsStreamHandleCtx *, struct UnionFs::UfsFileCtx *)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x140031a5c`
- `0x140074d3c`

## callees

- `0x14000f81c`
- `0x140010ba8`
- `0x14002ad6c`
- `0x140056c44`
- `0x140056c7c`
- `0x140061210`
- `0x14006e394`
- `0x1400705e0`
- `0x14007078c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14007091e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007099f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007091e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007099f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140070937`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400709b8`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140070a01`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140070937`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400709b8`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140070a01`

## string_xrefs

- `0x1400707f9`: `UnionFs::Utils::MarkFileAsDeleteCandidateIfInLayer`
- `0x1400708f0`: `UnionFs::Utils::MarkFileAsDeleteCandidateIfInLayer`
- `0x1400709db`: `UnionFs::Utils::MarkFileAsDeleteCandidateIfInLayer`
- `0x140070971`: `PUSH: PrepareForDelete`

## pseudocode

```c

```
