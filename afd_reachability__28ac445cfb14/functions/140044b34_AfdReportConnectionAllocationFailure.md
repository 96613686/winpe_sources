# AfdReportConnectionAllocationFailure

- ea: `0x140044b34`
- end: `0x140044c9b`
- name: `AfdReportConnectionAllocationFailure`
- size: `359`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14002e9c0`
- `0x140044960`

## callees

- `0x140004848`
- `0x1400049b0`
- `0x140044b34`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140044c1d`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140044c1d`
- `ntoskrnl!IofCompleteRequest` at `0x140044c64`
- `ntoskrnl!IofCompleteRequest` at `0x140044c64`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140044c0d`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140044c0d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140044bed`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140044c7e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140044bed`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140044c7e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140044b5f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140044b5f`

## pseudocode

```c

```
