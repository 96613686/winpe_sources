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
- `0x140030a68`
- `0x14003606c`
- `0x14003a930`
- `0x140041038`
- `0x140044700`
- `0x1400485e0`
- `0x14004c770`
- `0x14004d5b0`
- `0x140052e40`
- `0x140053060`
- `0x140053260`
- `0x1400537b0`
- `0x140054b80`
- `0x140059ab0`
- `0x14005af30`
- `0x14005b2b0`

## callees

- `0x14001b800`
- `0x140050c84`

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
