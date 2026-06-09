# AfdNotifySockIndicateEventsUnlock

- ea: `0x14001b800`
- end: `0x14001b8da`
- name: `AfdNotifySockIndicateEventsUnlock`
- size: `218`
- prototype: `void __fastcall(struct _EX_RUNDOWN_REF *, struct _KLOCK_QUEUE_HANDLE *, char)`
- caller_count: `36`
- callee_count: `2`
- tags: ``

## callers

- `0x140008210`
- `0x14000c0d0`
- `0x14000d7f0`
- `0x14000de50`
- `0x14000ea50`
- `0x140012338`
- `0x140012a88`
- `0x140013590`
- `0x140019364`
- `0x14001a030`
- `0x14001af00`
- `0x14001b938`
- `0x14001bb20`
- `0x14001d524`
- `0x14001f120`
- `0x1400277f0`
- `0x14002b8b0`
- `0x14002cb90`
- `0x14002d8d0`
- `0x14002e9c0`
- `0x140030a48`
- `0x14003604c`
- `0x14003a910`
- `0x140041018`
- `0x1400446e0`
- `0x140048560`
- `0x14004c6d0`
- `0x14004d510`
- `0x140052da0`
- `0x140052fc0`
- `0x1400531c0`
- `0x140053710`
- `0x140054ae0`
- `0x140059910`
- `0x14005ad90`
- `0x14005b110`

## callees

- `0x14001b800`
- `0x140050be4`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001b878`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001b878`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14001b89b`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14001b89b`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14001b8c9`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14001b8c9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001b886`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14001b886`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001b83c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001b83c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001b86a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001b86a`

## pseudocode

```c

```
