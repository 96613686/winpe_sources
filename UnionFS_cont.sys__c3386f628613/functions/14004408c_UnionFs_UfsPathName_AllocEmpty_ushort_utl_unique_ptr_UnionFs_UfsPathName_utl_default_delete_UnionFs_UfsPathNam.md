# UnionFs::UfsPathName::AllocEmpty(ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)

- ea: `0x14004408c`
- end: `0x1400441ab`
- name: `?AllocEmpty@UfsPathName@UnionFs@@SAJGAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `287`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x14001c15c`
- `0x14003b798`
- `0x140043a88`
- `0x140043bdc`
- `0x14004c74c`

## callees

- `0x140043858`
- `0x14004408c`
- `0x140056ac4`
- `0x140079c48`
- `0x140079d0c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400440c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044159`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400440c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140044159`
- `ntoskrnl!ExAllocatePool2` at `0x14004410f`
- `ntoskrnl!ExAllocatePool2` at `0x14004410f`

## string_xrefs

- `0x1400440ef`: `ORIGIN: Allocating path string`
- `0x140044169`: `ORIGIN: Allocating UfsPathName`
- `0x140044186`: `UnionFs::UfsPathName::AllocEmpty`

## pseudocode

```c

```
