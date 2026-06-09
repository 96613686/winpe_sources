# HCI_pSendWriteStoredLinkKey(HCI_INTERFACE *,_HCI_DIB_ACTIVITY_ID_CONTEXT *)

- ea: `0x1400a7830`
- end: `0x1400a7cbf`
- name: `?HCI_pSendWriteStoredLinkKey@@YAJPEAUHCI_INTERFACE@@PEAU_HCI_DIB_ACTIVITY_ID_CONTEXT@@@Z`
- size: `1167`
- prototype: `__int64 __fastcall(struct HCI_INTERFACE *, struct _HCI_DIB_ACTIVITY_ID_CONTEXT *)`
- caller_count: `3`
- callee_count: `13`
- tags: ``

## callers

- `0x1400a652c`
- `0x1400a71a0`
- `0x1400a7cd0`

## callees

- `0x140005608`
- `0x140005a64`
- `0x140005b4c`
- `0x140005c04`
- `0x14000abf4`
- `0x14000bdb8`
- `0x1400272a4`
- `0x1400350f0`
- `0x1400a629c`
- `0x1400a7830`
- `0x140161a44`
- `0x140165540`
- `0x1401f2528`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x1400a796a`
- `ntoskrnl!IoFreeWorkItem` at `0x1400a796a`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400a7927`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400a7927`
- `ntoskrnl!IoQueueWorkItem` at `0x1400a7a03`
- `ntoskrnl!IoQueueWorkItem` at `0x1400a7a03`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a7a14`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a7b43`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a7a14`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a7b43`
- `ntoskrnl!ExAllocatePool2` at `0x1400a7953`
- `ntoskrnl!ExAllocatePool2` at `0x1400a7953`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400a78f4`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400a78f4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400a7b05`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400a7b05`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400a7b32`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400a7b32`

## pseudocode

```c

```
