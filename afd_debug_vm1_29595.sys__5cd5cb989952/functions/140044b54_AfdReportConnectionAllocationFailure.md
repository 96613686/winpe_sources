# AfdReportConnectionAllocationFailure

- ea: `0x140044b54`
- end: `0x140044cbb`
- name: `AfdReportConnectionAllocationFailure`
- size: `359`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14002e9c0`
- `0x140044980`

## callees

- `0x140004848`
- `0x1400049b0`
- `0x140044b54`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140044c3d`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140044c3d`
- `ntoskrnl!IofCompleteRequest` at `0x140044c84`
- `ntoskrnl!IofCompleteRequest` at `0x140044c84`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140044c2d`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140044c2d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140044c0d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140044c9e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140044c0d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140044c9e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140044b7f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140044b7f`

## pseudocode

```c

```
