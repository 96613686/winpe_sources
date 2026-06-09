# CBootCfg::_GetOsInfoForBootEntry(_GUID const *,_SRT_OS_INFO * *)

- ea: `0x1800529a8`
- end: `0x180052b24`
- name: `?_GetOsInfoForBootEntry@CBootCfg@@AEAAKPEBU_GUID@@PEAPEAU_SRT_OS_INFO@@@Z`
- size: `380`
- prototype: `__int64 __fastcall(CBootCfg *this, const struct _GUID *, struct _SRT_OS_INFO **)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180051dc8`

## callees

- `0x180001f54`
- `0x180001f94`
- `0x18004f8a8`
- `0x18004f8d0`
- `0x1800529a8`
- `0x1800536ec`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180052a8b`
- `ntdll!RtlNtStatusToDosError` at `0x180052a8b`
- `bcd!BcdCloseObject` at `0x180052af2`
- `bcd!BcdCloseObject` at `0x180052af2`
- `bcd!BcdOpenObject` at `0x180052a4b`
- `bcd!BcdOpenObject` at `0x180052a4b`

## pseudocode

```c

```
