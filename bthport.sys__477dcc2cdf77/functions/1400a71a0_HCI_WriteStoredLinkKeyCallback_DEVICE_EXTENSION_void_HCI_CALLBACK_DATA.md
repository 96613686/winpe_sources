# HCI_WriteStoredLinkKeyCallback(DEVICE_EXTENSION *,void *,_HCI_CALLBACK_DATA *)

- ea: `0x1400a71a0`
- end: `0x1400a766d`
- name: `?HCI_WriteStoredLinkKeyCallback@@YAXPEAUDEVICE_EXTENSION@@PEAXPEAU_HCI_CALLBACK_DATA@@@Z`
- size: `1229`
- prototype: `void __fastcall(struct DEVICE_EXTENSION *, PVOID P, struct _HCI_CALLBACK_DATA *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x140005608`
- `0x140005b4c`
- `0x140005c04`
- `0x1400278d8`
- `0x14005e140`
- `0x1400a629c`
- `0x1400a71a0`
- `0x1400a7830`
- `0x140161d7c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400a75d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a75d3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400a7343`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400a7343`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400a7473`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400a7473`

## pseudocode

```c

```
