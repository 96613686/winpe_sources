# AfdValidateGroup

- ea: `0x140050550`
- end: `0x1400507df`
- name: `AfdValidateGroup`
- size: `655`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14001ef30`

## callees

- `0x14001c708`
- `0x140049960`
- `0x140049a48`
- `0x14004dd9c`
- `0x140050550`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x140050603`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x140050603`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140050782`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140050782`
- `ntoskrnl!IofCompleteRequest` at `0x1400507b8`
- `ntoskrnl!IofCompleteRequest` at `0x1400507b8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140050680`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005070f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005074d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140050680`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005070f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005074d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005064e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005069a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005064e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005069a`

## pseudocode

```c

```
