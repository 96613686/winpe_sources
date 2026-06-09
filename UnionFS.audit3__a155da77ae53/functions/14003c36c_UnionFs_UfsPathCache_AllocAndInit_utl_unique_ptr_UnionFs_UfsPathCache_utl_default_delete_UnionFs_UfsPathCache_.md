# UnionFs::UfsPathCache::AllocAndInit(utl::unique_ptr<UnionFs::UfsPathCache,utl::default_delete<UnionFs::UfsPathCache>> &,UnionFs::StackEventTracer &)

- ea: `0x14003c36c`
- end: `0x14003c503`
- name: `?AllocAndInit@UfsPathCache@UnionFs@@SAJAEAV?$unique_ptr@VUfsPathCache@UnionFs@@U?$default_delete@VUfsPathCache@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `407`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x14005a87c`
- `0x14005f38c`

## callees

- `0x140023060`
- `0x14003b7f4`
- `0x14003c36c`
- `0x140047fdc`
- `0x140056c44`
- `0x140056c7c`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14003c442`
- `ntoskrnl!KeInitializeEvent` at `0x14003c442`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c493`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c4bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c493`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c4bb`
- `ntoskrnl!ExAllocatePool2` at `0x14003c38b`
- `ntoskrnl!ExAllocatePool2` at `0x14003c38b`

## string_xrefs

- `0x14003c4cb`: `ORIGIN: Allocating path cache table`
- `0x14003c470`: `UnionFs::UfsPathCache::AllocAndInit`
- `0x14003c4de`: `UnionFs::UfsPathCache::AllocAndInit`

## pseudocode

```c

```
