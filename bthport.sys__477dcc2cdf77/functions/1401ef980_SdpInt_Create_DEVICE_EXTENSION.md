# SdpInt_Create(DEVICE_EXTENSION *)

- ea: `0x1401ef980`
- end: `0x1401efa20`
- name: `?SdpInt_Create@@YAPEAU_SDP_INTERFACE@@PEAUDEVICE_EXTENSION@@@Z`
- size: `160`
- prototype: `struct _SDP_INTERFACE *__fastcall(struct DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14002a5b8`

## callees

- `0x14014ac78`
- `0x140165940`
- `0x1401ef980`

## import_xrefs

- `ntoskrnl!ExInitializeResourceLite` at `0x1401efa02`
- `ntoskrnl!ExInitializeResourceLite` at `0x1401efa02`
- `ntoskrnl!ExAllocatePool2` at `0x1401ef99d`
- `ntoskrnl!ExAllocatePool2` at `0x1401ef99d`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401ef9f2`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401ef9f2`

## pseudocode

```c

```
