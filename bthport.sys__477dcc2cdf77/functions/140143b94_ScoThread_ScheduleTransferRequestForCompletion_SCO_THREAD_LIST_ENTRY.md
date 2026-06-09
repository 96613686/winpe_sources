# ScoThread_ScheduleTransferRequestForCompletion(_SCO_THREAD *,_LIST_ENTRY *)

- ea: `0x140143b94`
- end: `0x140143c27`
- name: `?ScoThread_ScheduleTransferRequestForCompletion@@YAXPEAU_SCO_THREAD@@PEAU_LIST_ENTRY@@@Z`
- size: `147`
- prototype: `void __fastcall(PKSPIN_LOCK SpinLock, struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140144c4c`

## callees

- `0x140143b94`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140143c0f`
- `ntoskrnl!KeSetEvent` at `0x140143c0f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140143ba4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140143ba4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140143bf7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140143bf7`

## pseudocode

```c

```
