# HCI_DeleteStoredLinkKeyCallback(DEVICE_EXTENSION *,void *,_HCI_CALLBACK_DATA *)

- ea: `0x1400a5610`
- end: `0x1400a58ac`
- name: `?HCI_DeleteStoredLinkKeyCallback@@YAXPEAUDEVICE_EXTENSION@@PEAXPEAU_HCI_CALLBACK_DATA@@@Z`
- size: `668`
- prototype: `void(struct DEVICE_EXTENSION *, void *, struct _HCI_CALLBACK_DATA *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x140005c04`
- `0x1400278d8`
- `0x14005d8b0`
- `0x1400a5610`
- `0x1400a629c`
- `0x1400a652c`
- `0x140161d7c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400a5801`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a5801`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400a57ad`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400a57ad`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400a57de`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400a57de`

## pseudocode

```c

```
