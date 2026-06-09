# UnionFs::UfsPathName::AllocEmpty(ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)

- ea: `0x14004420c`
- end: `0x14004432b`
- name: `?AllocEmpty@UfsPathName@UnionFs@@SAJGAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `287`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x14001c1fc`
- `0x14003b8b8`
- `0x140043c08`
- `0x140043d5c`
- `0x14004c8cc`

## callees

- `0x1400439d8`
- `0x14004420c`
- `0x140056c44`
- `0x140079f68`
- `0x14007a02c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140044246`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400442d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044246`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400442d9`
- `ntoskrnl!ExAllocatePool2` at `0x14004428f`
- `ntoskrnl!ExAllocatePool2` at `0x14004428f`

## string_xrefs

- `0x14004426f`: `ORIGIN: Allocating path string`
- `0x1400442e9`: `ORIGIN: Allocating UfsPathName`
- `0x140044306`: `UnionFs::UfsPathName::AllocEmpty`

## pseudocode

```c

```
