# SdpL2cap_CloseChannelComplete(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x140146310`
- end: `0x14014656e`
- name: `?SdpL2cap_CloseChannelComplete@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `606`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140005b4c`
- `0x1400b9d78`
- `0x140146310`
- `0x140147a90`
- `0x140147fe0`
- `0x140161d7c`
- `0x140162538`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140146452`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140146462`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140146452`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140146462`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140146414`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140146434`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140146414`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140146434`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401463a4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401463a4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140146479`
- `ntoskrnl!KeReleaseSpinLock` at `0x140146479`

## pseudocode

```c

```
