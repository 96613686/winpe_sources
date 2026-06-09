# CBssidConnectHistory::IsExcessiveRoamDetected(uchar (* const)[6],_GUID const &,bool)

- ea: `0x1400bcec8`
- end: `0x1400bd0ff`
- name: `?IsExcessiveRoamDetected@CBssidConnectHistory@@QEAA_NQEAY05EAEBU_GUID@@_N@Z`
- size: `567`
- prototype: `bool __fastcall(CBssidConnectHistory *__hidden this, unsigned __int8 (*const)[6], const struct _GUID *, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x1400a77e8`

## callees

- `0x140001008`
- `0x140001b6c`
- `0x14000cf40`
- `0x14002ed50`
- `0x14006b8ac`
- `0x1400bcec8`
- `0x1400bd108`
- `0x1400e0100`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400bd0cb`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bd0cb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bcf2c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bcf2c`

## pseudocode

```c

```
