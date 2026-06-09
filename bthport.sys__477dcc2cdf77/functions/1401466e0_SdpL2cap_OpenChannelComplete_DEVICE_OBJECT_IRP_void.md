# SdpL2cap_OpenChannelComplete(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x1401466e0`
- end: `0x140146cf9`
- name: `?SdpL2cap_OpenChannelComplete@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `1561`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x140005608`
- `0x140005690`
- `0x140005b4c`
- `0x14000764c`
- `0x1401466e0`
- `0x140146d00`
- `0x140146ed8`
- `0x1401472f0`
- `0x140147934`
- `0x1401480a0`
- `0x140161a44`
- `0x140161d7c`
- `0x140162538`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140146a54`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140146a54`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140146864`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140146864`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14014684a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14014684a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140146b0a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140146b0a`

## pseudocode

```c

```
