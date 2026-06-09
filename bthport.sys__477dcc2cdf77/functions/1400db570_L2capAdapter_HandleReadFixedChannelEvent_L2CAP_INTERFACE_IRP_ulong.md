# L2capAdapter_HandleReadFixedChannelEvent(L2CAP_INTERFACE *,_IRP *,ulong *)

- ea: `0x1400db570`
- end: `0x1400db784`
- name: `?L2capAdapter_HandleReadFixedChannelEvent@@YAJPEAUL2CAP_INTERFACE@@PEAU_IRP@@PEAK@Z`
- size: `532`
- prototype: `__int64 __fastcall(struct L2CAP_INTERFACE *, struct _IRP *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x14001e010`

## callees

- `0x140005690`
- `0x1400db2c8`
- `0x1400db570`
- `0x1400dbef0`
- `0x140161a44`
- `0x140161d7c`
- `0x140162174`
- `0x140165940`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400db663`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400db663`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400db593`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400db593`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400db6f6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400db6f6`

## pseudocode

```c

```
