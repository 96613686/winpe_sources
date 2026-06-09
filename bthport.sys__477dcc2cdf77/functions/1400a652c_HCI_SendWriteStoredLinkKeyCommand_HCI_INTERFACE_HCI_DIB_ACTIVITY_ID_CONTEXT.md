# HCI_SendWriteStoredLinkKeyCommand(HCI_INTERFACE *,_HCI_DIB_ACTIVITY_ID_CONTEXT *)

- ea: `0x1400a652c`
- end: `0x1400a6822`
- name: `?HCI_SendWriteStoredLinkKeyCommand@@YAJPEAUHCI_INTERFACE@@PEAU_HCI_DIB_ACTIVITY_ID_CONTEXT@@@Z`
- size: `758`
- prototype: `int(struct HCI_INTERFACE *, struct _HCI_DIB_ACTIVITY_ID_CONTEXT *)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400a5610`
- `0x1400a58e8`
- `0x1400a6ca0`
- `0x1400a7680`

## callees

- `0x140005b4c`
- `0x140005c04`
- `0x14000bdb8`
- `0x1400a652c`
- `0x1400a7830`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400a673e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a673e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400a65d2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400a65d2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400a6716`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400a6716`

## pseudocode

```c

```
