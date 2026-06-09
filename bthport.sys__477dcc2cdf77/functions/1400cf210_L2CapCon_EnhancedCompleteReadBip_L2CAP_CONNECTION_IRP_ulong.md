# L2CapCon_EnhancedCompleteReadBip(L2CAP_CONNECTION *,_IRP *,ulong)

- ea: `0x1400cf210`
- end: `0x1400cf991`
- name: `?L2CapCon_EnhancedCompleteReadBip@@YAJPEAUL2CAP_CONNECTION@@PEAU_IRP@@K@Z`
- size: `1921`
- prototype: `__int64 __fastcall(struct L2CAP_CONNECTION *, struct _IRP *, unsigned int)`
- caller_count: `3`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1400bae70`
- `0x1400d1368`
- `0x1400e4814`

## callees

- `0x140005748`
- `0x140005ce8`
- `0x14000764c`
- `0x1400ba420`
- `0x1400ccb3c`
- `0x1400ccbc4`
- `0x1400cf210`
- `0x1400d54b4`
- `0x14016241c`
- `0x140162670`
- `0x140165540`
- `0x140165580`
- `0x140165940`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400cf549`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cf80b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cf549`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cf80b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400cf30e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400cf30e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cf83c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cf83c`

## pseudocode

```c

```
