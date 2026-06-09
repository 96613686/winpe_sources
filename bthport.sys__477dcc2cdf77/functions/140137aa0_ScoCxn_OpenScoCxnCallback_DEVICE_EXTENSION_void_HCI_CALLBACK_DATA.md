# ScoCxn_OpenScoCxnCallback(DEVICE_EXTENSION *,void *,_HCI_CALLBACK_DATA *)

- ea: `0x140137aa0`
- end: `0x140137e16`
- name: `?ScoCxn_OpenScoCxnCallback@@YAXPEAUDEVICE_EXTENSION@@PEAXPEAU_HCI_CALLBACK_DATA@@@Z`
- size: `886`
- prototype: `void(struct DEVICE_EXTENSION *, void *, struct _HCI_CALLBACK_DATA *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting`

## callees

- `0x14000113c`
- `0x14000376c`
- `0x140005608`
- `0x140005b4c`
- `0x140005c04`
- `0x1400071c4`
- `0x140137aa0`
- `0x140138b08`
- `0x140139c94`
- `0x140161d7c`
- `0x1401630a8`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x140137b5d`
- `ntoskrnl!EtwActivityIdControl` at `0x140137b5d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140137c32`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140137cb6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140137c32`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140137cb6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140137c52`
- `ntoskrnl!KeReleaseSpinLock` at `0x140137cf8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140137c52`
- `ntoskrnl!KeReleaseSpinLock` at `0x140137cf8`

## pseudocode

```c

```
