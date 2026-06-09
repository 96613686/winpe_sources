# AfdSetQos

- ea: `0x14004fd40`
- end: `0x14004fe4a`
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
- `0x14004fd40`
- `0x14004fe50`
- `0x140073020`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14004fe30`
- `ntoskrnl!IofCompleteRequest` at `0x14004fe30`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004fe10`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004fe10`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004fdc0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004fdc0`
- `ntoskrnl!IoIs32bitProcess` at `0x14004fd51`
- `ntoskrnl!IoIs32bitProcess` at `0x14004fd51`

## pseudocode

```c

```
