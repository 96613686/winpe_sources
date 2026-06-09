# WfpAcquireSpinLock

- ea: `0x140014b90`
- end: `0x140014c1c`
- name: `WfpAcquireSpinLock`
- size: `140`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock, PKLOCK_QUEUE_HANDLE LockHandle)`
- caller_count: `25`
- callee_count: `1`
- tags: ``

## callers

- `0x14000cf4c`
- `0x1400119a4`
- `0x140011a64`
- `0x140011b70`
- `0x140011ca0`
- `0x1400121e0`
- `0x140013024`
- `0x140013180`
- `0x140013638`
- `0x140014600`
- `0x140015a80`
- `0x140041240`
- `0x1400439e4`
- `0x14004b200`
- `0x14004d8b4`
- `0x1400509ac`
- `0x1400518c0`
- `0x1400646d0`
- `0x140064790`
- `0x140064b50`
- `0x140065a50`
- `0x140066b40`
- `0x140066c10`
- `0x14006e304`
- `0x14006e6a8`

## callees

- `0x140014b90`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140014bd7`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140014bd7`
- `ntoskrnl!KeGetCurrentIrql` at `0x140014ba5`
- `ntoskrnl!KeGetCurrentIrql` at `0x140014ba5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140014bba`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140014bba`

## pseudocode

```c

```
