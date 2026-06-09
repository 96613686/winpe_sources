# AfdFinishSuperAccept

- ea: `0x140018bb4`
- end: `0x140018d2d`
- name: `AfdFinishSuperAccept`
- size: `377`
- prototype: `void __fastcall(PIRP Irp, __int64, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140018b90`
- `0x140044a00`

## callees

- `0x140013030`
- `0x140018bb4`
- `0x140019190`
- `0x1400191f0`
- `0x14001c708`
- `0x140072980`
- `0x140093008`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140018d15`
- `ntoskrnl!IofCompleteRequest` at `0x140018d15`
- `ntoskrnl!ObfDereferenceObject` at `0x140018cc7`
- `ntoskrnl!ObfDereferenceObject` at `0x140018cda`
- `ntoskrnl!ObfDereferenceObject` at `0x140018cc7`
- `ntoskrnl!ObfDereferenceObject` at `0x140018cda`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018cac`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018cac`

## pseudocode

```c

```
