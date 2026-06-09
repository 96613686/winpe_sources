# UnionFs::UfsEaPayload::AllocAndRestoreShared(utl::shared_ptr<UnionFs::UfsUnionCtx>,utl::vector<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>,utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>,gsl::span<gsl::byte,-1> &,utl::shared_ptr<UnionFs::UfsEaPayload> &,UnionFs::StackEventTracer &)

- ea: `0x140021c14`
- end: `0x140021f79`
- name: `?AllocAndRestoreShared@UfsEaPayload@UnionFs@@SAJV?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@V?$vector@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@2@@4@AEAV?$span@W4byte@gsl@@$0?0@gsl@@AEAV?$shared_ptr@VUfsEaPayload@UnionFs@@@4@AEAVStackEventTracer@2@@Z`
- size: `869`
- prototype: `__int64 __fastcall(int, int, int, int, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14001fbb0`

## callees

- `0x14000f7fc`
- `0x14001c780`
- `0x140021470`
- `0x140021550`
- `0x1400218ac`
- `0x140021c14`
- `0x140022850`
- `0x140056ac4`
- `0x140056afc`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140021da9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021ed0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021f51`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021da9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021ed0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021f51`
- `ntoskrnl!ExAllocatePool2` at `0x140021c70`
- `ntoskrnl!ExAllocatePool2` at `0x140021c70`
- `ntoskrnl!ExReleaseResourceLite` at `0x140021d4d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140021e38`
- `ntoskrnl!ExReleaseResourceLite` at `0x140021e75`
- `ntoskrnl!ExReleaseResourceLite` at `0x140021d4d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140021e38`
- `ntoskrnl!ExReleaseResourceLite` at `0x140021e75`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140021d59`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140021e44`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140021e81`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140021d59`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140021e44`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140021e81`

## string_xrefs

- `0x140021d18`: `PUSH: Adding scratch path to EA payload`

## pseudocode

```c

```
