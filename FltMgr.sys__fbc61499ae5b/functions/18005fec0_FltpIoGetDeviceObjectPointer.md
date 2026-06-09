# FltpIoGetDeviceObjectPointer

- ea: `0x18005fec0`
- end: `0x18005fffd`
- name: `FltpIoGetDeviceObjectPointer`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18005fe20`

## callees

- `0x180009f20`
- `0x18005fec0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x18005ffc9`
- `ntoskrnl!ObfDereferenceObject` at `0x18005ffc9`
- `ntoskrnl!ObfReferenceObject` at `0x18005ffb5`
- `ntoskrnl!ObfReferenceObject` at `0x18005ffb5`
- `ntoskrnl!ZwClose` at `0x18005ffdd`
- `ntoskrnl!ZwClose` at `0x18005ffdd`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18005ff72`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18005ff72`
- `ntoskrnl!ZwCreateFile` at `0x18005ff35`
- `ntoskrnl!ZwCreateFile` at `0x18005ff35`
- `ntoskrnl!IoFileObjectType` at `0x18005ff49`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x18005ffa3`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x18005ffa3`

## pseudocode

```c

```
