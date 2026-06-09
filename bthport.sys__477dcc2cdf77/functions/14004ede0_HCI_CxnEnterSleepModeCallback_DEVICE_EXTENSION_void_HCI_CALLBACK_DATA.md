# HCI_CxnEnterSleepModeCallback(DEVICE_EXTENSION *,void *,_HCI_CALLBACK_DATA *)

- ea: `0x14004ede0`
- end: `0x14004f0d5`
- name: `?HCI_CxnEnterSleepModeCallback@@YAXPEAUDEVICE_EXTENSION@@PEAXPEAU_HCI_CALLBACK_DATA@@@Z`
- size: `757`
- prototype: `void(struct DEVICE_EXTENSION *, void *, struct _HCI_CALLBACK_DATA *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x140005608`
- `0x140030f20`
- `0x140040834`
- `0x14004ede0`
- `0x140050680`
- `0x1400507b0`
- `0x1400ba080`
- `0x140161d7c`
- `0x14016241c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004ee84`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004efa7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004ee84`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004efa7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004ef4f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004f015`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004ef4f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004f015`

## pseudocode

```c

```
