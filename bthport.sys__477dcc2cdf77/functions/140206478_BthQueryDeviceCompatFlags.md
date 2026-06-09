# BthQueryDeviceCompatFlags

- ea: `0x140206478`
- end: `0x140206641`
- name: `BthQueryDeviceCompatFlags`
- size: `457`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400515b0`
- `0x140065b9c`
- `0x1400683f0`
- `0x140068440`
- `0x140092a60`
- `0x1401518a0`
- `0x1401bdd60`
- `0x1401fa610`
- `0x1401faa54`

## callees

- `0x140206478`
- `0x140206710`
- `0x140206a04`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140206622`
- `ntoskrnl!ObfDereferenceObject` at `0x140206622`
- `ntoskrnl!ExFreePoolWithTag` at `0x14020660c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14020660c`
- `ntoskrnl!ExAllocatePool2` at `0x1402065c2`
- `ntoskrnl!ExAllocatePool2` at `0x1402065c2`
- `ntoskrnl!KseQueryDeviceFlags` at `0x1402065f8`
- `ntoskrnl!KseQueryDeviceFlags` at `0x1402065f8`

## string_xrefs

- `0x1402064fc`: `BthCodService`

## pseudocode

```c

```
