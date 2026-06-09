# UnionFs::UfsInstanceTierNode::AllocAndInit(_FLT_INSTANCE const &,utl::unique_ptr<UnionFs::UfsInstanceTierNode,utl::default_delete<UnionFs::UfsInstanceTierNode>> &,UnionFs::StackEventTracer &)

- ea: `0x140035b64`
- end: `0x140035d9f`
- name: `?AllocAndInit@UfsInstanceTierNode@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEAV?$unique_ptr@VUfsInstanceTierNode@UnionFs@@U?$default_delete@VUfsInstanceTierNode@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `571`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140048244`

## callees

- `0x140005d9c`
- `0x140027764`
- `0x140035b64`
- `0x140045218`
- `0x140056c44`
- `0x140056c7c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140035bb8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035cf3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035d37`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035bb8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035cf3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035d37`
- `ntoskrnl!ExAllocatePool2` at `0x140035c21`
- `ntoskrnl!ExAllocatePool2` at `0x140035c21`
- `FLTMGR!FltReleaseContext` at `0x140035b9f`
- `FLTMGR!FltReleaseContext` at `0x140035cda`
- `FLTMGR!FltReleaseContext` at `0x140035d1e`
- `FLTMGR!FltReleaseContext` at `0x140035d7d`
- `FLTMGR!FltReleaseContext` at `0x140035b9f`
- `FLTMGR!FltReleaseContext` at `0x140035cda`
- `FLTMGR!FltReleaseContext` at `0x140035d1e`
- `FLTMGR!FltReleaseContext` at `0x140035d7d`

## string_xrefs

- `0x140035c90`: `UnionFs::UfsInstanceTierNode::SetEmptyRootNode`

## pseudocode

```c

```
