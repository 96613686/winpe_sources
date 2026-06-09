# AfdSetQos

- ea: `0x14004fde0`
- end: `0x14004feea`
- name: `AfdSetQos`
- size: `266`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14001ef30`

## callees

- `0x14000f450`
- `0x1400137a0`
- `0x14004fde0`
- `0x14004fef0`
- `0x1400731a0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14004fed0`
- `ntoskrnl!IofCompleteRequest` at `0x14004fed0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004feb0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004feb0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004fe60`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004fe60`
- `ntoskrnl!IoIs32bitProcess` at `0x14004fdf1`
- `ntoskrnl!IoIs32bitProcess` at `0x14004fdf1`

## pseudocode

```c

```
