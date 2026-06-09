# AfdValidateGroup

- ea: `0x1400505f0`
- end: `0x14005087f`
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
- `0x140049a00`
- `0x140049ae8`
- `0x14004de3c`
- `0x1400505f0`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x1400506a3`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x1400506a3`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140050822`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140050822`
- `ntoskrnl!IofCompleteRequest` at `0x140050858`
- `ntoskrnl!IofCompleteRequest` at `0x140050858`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140050720`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400507af`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400507ed`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140050720`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400507af`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400507ed`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400506ee`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005073a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400506ee`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005073a`

## pseudocode

```c

```
