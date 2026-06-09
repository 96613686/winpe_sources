# BthCompleteAuthenticateRequest(_DEVICE_OBJECT *,_IRP *,long)

- ea: `0x14001cce0`
- end: `0x14001d1b7`
- name: `?BthCompleteAuthenticateRequest@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@J@Z`
- size: `1239`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *, int)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x140005b4c`
- `0x140005c04`
- `0x140005ce8`
- `0x140006f50`
- `0x140006ff0`
- `0x14000764c`
- `0x14001c578`
- `0x14001c638`
- `0x14001cce0`
- `0x1400202d8`
- `0x14002a354`
- `0x14003af88`
- `0x140041474`
- `0x1400b9d78`
- `0x140162008`
- `0x140165540`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14001d104`
- `ntoskrnl!ObfDereferenceObject` at `0x14001d104`
- `ntoskrnl!KeSetEvent` at `0x14001d0f5`
- `ntoskrnl!KeSetEvent` at `0x14001d0f5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001cdbb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001cfe4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001cdbb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001cfe4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001cee2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001d000`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001cee2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001d000`

## pseudocode

```c

```
