# AfdWaitForListen

- ea: `0x14002f800`
- end: `0x14002fadc`
- name: `AfdWaitForListen`
- size: `732`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14001ef30`
- `0x14002e9c0`

## callees

- `0x1400049b0`
- `0x140004c10`
- `0x14002f800`
- `0x14002fd20`
- `0x140036dac`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002f919`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002fa90`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002f919`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002fa90`
- `ntoskrnl!IofCompleteRequest` at `0x14002fabf`
- `ntoskrnl!IofCompleteRequest` at `0x14002fabf`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14002f90a`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14002fa81`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14002f90a`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14002fa81`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002f86a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002f8b0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002f94a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002fa07`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002fa67`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002f86a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002f8b0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002f94a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002fa07`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002fa67`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002f853`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002f853`

## pseudocode

```c

```
