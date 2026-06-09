# UnionFs::UfsPathCache::AllocAndInit(utl::unique_ptr<UnionFs::UfsPathCache,utl::default_delete<UnionFs::UfsPathCache>> &,UnionFs::StackEventTracer &)

- ea: `0x14003c24c`
- end: `0x14003c3e3`
- name: `?AllocAndInit@UfsPathCache@UnionFs@@SAJAEAV?$unique_ptr@VUfsPathCache@UnionFs@@U?$default_delete@VUfsPathCache@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `407`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x14005a6fc`
- `0x14005f20c`

## callees

- `0x140022fc0`
- `0x14003b6d4`
- `0x14003c24c`
- `0x140047e5c`
- `0x140056ac4`
- `0x140056afc`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14003c322`
- `ntoskrnl!KeInitializeEvent` at `0x14003c322`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c373`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c39b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c373`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c39b`
- `ntoskrnl!ExAllocatePool2` at `0x14003c26b`
- `ntoskrnl!ExAllocatePool2` at `0x14003c26b`

## string_xrefs

- `0x14003c3ab`: `ORIGIN: Allocating path cache table`
- `0x14003c350`: `UnionFs::UfsPathCache::AllocAndInit`
- `0x14003c3be`: `UnionFs::UfsPathCache::AllocAndInit`

## pseudocode

```c

```
