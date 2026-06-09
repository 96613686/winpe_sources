# BthUnregisterPsmForPdo(DEVICE_EXTENSION *,PDO_EXTENSION *,ushort)

- ea: `0x14002863c`
- end: `0x140028931`
- name: `?BthUnregisterPsmForPdo@@YAJPEAUDEVICE_EXTENSION@@PEAUPDO_EXTENSION@@G@Z`
- size: `757`
- prototype: `__int64 __fastcall(struct DEVICE_EXTENSION *, struct PDO_EXTENSION *, unsigned __int16)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1401bb0a0`

## callees

- `0x140005690`
- `0x140005c04`
- `0x14002863c`
- `0x140028938`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140028865`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028865`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400286da`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400286da`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002884d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002884d`

## pseudocode

```c

```
