# UnionFs::UfsEaPayload::AllocAndRestoreShared(utl::shared_ptr<UnionFs::UfsUnionCtx>,utl::vector<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>,utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>,gsl::span<gsl::byte,-1> &,utl::shared_ptr<UnionFs::UfsEaPayload> &,UnionFs::StackEventTracer &)

- ea: `0x140021cb4`
- end: `0x140022019`
- name: `?AllocAndRestoreShared@UfsEaPayload@UnionFs@@SAJV?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@V?$vector@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@2@@4@AEAV?$span@W4byte@gsl@@$0?0@gsl@@AEAV?$shared_ptr@VUfsEaPayload@UnionFs@@@4@AEAVStackEventTracer@2@@Z`
- size: `869`
- prototype: `__int64 __fastcall(int, int, int, int, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14001fc50`

## callees

- `0x14000f81c`
- `0x14001c820`
- `0x140021510`
- `0x1400215f0`
- `0x14002194c`
- `0x140021cb4`
- `0x1400228f0`
- `0x140056c44`
- `0x140056c7c`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140021e49`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021f70`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021ff1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021e49`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021f70`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021ff1`
- `ntoskrnl!ExAllocatePool2` at `0x140021d10`
- `ntoskrnl!ExAllocatePool2` at `0x140021d10`
- `ntoskrnl!ExReleaseResourceLite` at `0x140021ded`
- `ntoskrnl!ExReleaseResourceLite` at `0x140021ed8`
- `ntoskrnl!ExReleaseResourceLite` at `0x140021f15`
- `ntoskrnl!ExReleaseResourceLite` at `0x140021ded`
- `ntoskrnl!ExReleaseResourceLite` at `0x140021ed8`
- `ntoskrnl!ExReleaseResourceLite` at `0x140021f15`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140021df9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140021ee4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140021f21`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140021df9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140021ee4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140021f21`

## string_xrefs

- `0x140021db8`: `PUSH: Adding scratch path to EA payload`

## pseudocode

```c

```
