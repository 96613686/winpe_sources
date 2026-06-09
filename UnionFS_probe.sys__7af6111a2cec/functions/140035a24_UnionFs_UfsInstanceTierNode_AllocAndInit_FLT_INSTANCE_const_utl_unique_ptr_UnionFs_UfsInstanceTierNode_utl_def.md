# UnionFs::UfsInstanceTierNode::AllocAndInit(_FLT_INSTANCE const &,utl::unique_ptr<UnionFs::UfsInstanceTierNode,utl::default_delete<UnionFs::UfsInstanceTierNode>> &,UnionFs::StackEventTracer &)

- ea: `0x140035a24`
- end: `0x140035c5f`
- name: `?AllocAndInit@UfsInstanceTierNode@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEAV?$unique_ptr@VUfsInstanceTierNode@UnionFs@@U?$default_delete@VUfsInstanceTierNode@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `571`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400480c4`

## callees

- `0x140005d9c`
- `0x1400276c4`
- `0x140035a24`
- `0x140045098`
- `0x140056ac4`
- `0x140056afc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140035a78`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035bb3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035bf7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035a78`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035bb3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035bf7`
- `ntoskrnl!ExAllocatePool2` at `0x140035ae1`
- `ntoskrnl!ExAllocatePool2` at `0x140035ae1`
- `FLTMGR!FltReleaseContext` at `0x140035a5f`
- `FLTMGR!FltReleaseContext` at `0x140035b9a`
- `FLTMGR!FltReleaseContext` at `0x140035bde`
- `FLTMGR!FltReleaseContext` at `0x140035c3d`
- `FLTMGR!FltReleaseContext` at `0x140035a5f`
- `FLTMGR!FltReleaseContext` at `0x140035b9a`
- `FLTMGR!FltReleaseContext` at `0x140035bde`
- `FLTMGR!FltReleaseContext` at `0x140035c3d`

## string_xrefs

- `0x140035b50`: `UnionFs::UfsInstanceTierNode::SetEmptyRootNode`

## pseudocode

```c

```
