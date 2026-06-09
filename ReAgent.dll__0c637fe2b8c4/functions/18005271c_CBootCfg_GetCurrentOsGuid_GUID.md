# CBootCfg::_GetCurrentOsGuid(_GUID *)

- ea: `0x18005271c`
- end: `0x180052816`
- name: `?_GetCurrentOsGuid@CBootCfg@@AEAAKPEAU_GUID@@@Z`
- size: `250`
- prototype: `__int64 __fastcall(CBootCfg *this, struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180051d24`

## callees

- `0x18004f8d0`
- `0x18005271c`
- `0x18005cf30`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800527df`
- `ntdll!RtlNtStatusToDosError` at `0x1800527df`
- `bcd!BcdCloseObject` at `0x1800527f6`
- `bcd!BcdCloseObject` at `0x1800527f6`
- `bcd!BcdQueryObject` at `0x1800527a0`
- `bcd!BcdQueryObject` at `0x1800527a0`
- `bcd!BcdOpenObject` at `0x180052750`
- `bcd!BcdOpenObject` at `0x180052750`

## pseudocode

```c

```
