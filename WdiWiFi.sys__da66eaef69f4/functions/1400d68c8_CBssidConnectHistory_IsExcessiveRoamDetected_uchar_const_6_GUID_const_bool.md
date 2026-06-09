# CBssidConnectHistory::IsExcessiveRoamDetected(uchar (* const)[6],_GUID const &,bool)

- ea: `0x1400d68c8`
- end: `0x1400d6af5`
- name: `?IsExcessiveRoamDetected@CBssidConnectHistory@@QEAA_NQEAY05EAEBU_GUID@@_N@Z`
- size: `557`
- prototype: `bool __fastcall(CBssidConnectHistory *__hidden this, unsigned __int8 (*const)[6], const struct _GUID *, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400143d8`

## callees

- `0x140001970`
- `0x1400175f8`
- `0x14007e5dc`
- `0x1400d68c8`
- `0x1400da740`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400d6aca`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d6aca`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d6923`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d6923`

## pseudocode

```c

```
