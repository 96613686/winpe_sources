# RefsAddToWorkqueInternal(_IRP_CONTEXT *,_IRP *,uchar,uchar)

- ea: `0x14000a650`
- end: `0x14000ace7`
- name: `?RefsAddToWorkqueInternal@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@EE@Z`
- size: `1687`
- prototype: `void(struct _IRP_CONTEXT *, struct _IRP *, unsigned __int8, unsigned __int8)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a630`
- `0x14000c180`
- `0x1400b6650`
- `0x1402ed9c0`

## callees

- `0x14000a650`
- `0x14000e0e0`
- `0x1400d0fd8`

## import_xrefs

- `ntoskrnl!IoGetActivityIdThread` at `0x14000ac98`
- `ntoskrnl!IoGetActivityIdThread` at `0x14000ac98`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14000a974`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14000ac84`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14000a974`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14000ac84`
- `ntoskrnl!IoGetCurrentProcess` at `0x14000aafb`
- `ntoskrnl!IoGetCurrentProcess` at `0x14000ab15`
- `ntoskrnl!IoGetCurrentProcess` at `0x14000aafb`
- `ntoskrnl!IoGetCurrentProcess` at `0x14000ab15`
- `ntoskrnl!ExQueueWorkItem` at `0x14000acc2`
- `ntoskrnl!ExQueueWorkItem` at `0x14000acc2`
- `ntoskrnl!KeSetEvent` at `0x14000a908`
- `ntoskrnl!KeSetEvent` at `0x14000abc3`
- `ntoskrnl!KeSetEvent` at `0x14000a908`
- `ntoskrnl!KeSetEvent` at `0x14000abc3`
- `ntoskrnl!DbgPrintEx` at `0x14000aa94`
- `ntoskrnl!DbgPrintEx` at `0x14000aa94`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x14000aac1`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x14000aac1`
- `ntoskrnl!_strnicmp` at `0x14000ab40`
- `ntoskrnl!_strnicmp` at `0x14000ab40`
- `ntoskrnl!PsGetProcessImageFileName` at `0x14000ab24`
- `ntoskrnl!PsGetProcessImageFileName` at `0x14000ab24`
- `ntoskrnl!IoGetIoPriorityHint` at `0x14000a69e`
- `ntoskrnl!IoGetIoPriorityHint` at `0x14000a69e`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000a841`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000a841`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a75d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a89d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a75d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a89d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a7d7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a940`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000aba5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ac0f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a7d7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a940`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000aba5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ac0f`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14000a9a0`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14000a9a0`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000a9c9`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000aa00`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000a9c9`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000aa00`
- `ntoskrnl!ExTryQueueWorkItem` at `0x14000a7fe`
- `ntoskrnl!ExTryQueueWorkItem` at `0x14000a7fe`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000a882`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000ac45`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000a882`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000ac45`

## pseudocode

```c

```
