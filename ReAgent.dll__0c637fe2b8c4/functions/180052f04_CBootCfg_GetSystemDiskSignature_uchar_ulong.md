# CBootCfg::_GetSystemDiskSignature(uchar *,ulong)

- ea: `0x180052f04`
- end: `0x18005310c`
- name: `?_GetSystemDiskSignature@CBootCfg@@AEAAKPEAEK@Z`
- size: `520`
- prototype: `__int64 __fastcall(CBootCfg *this, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180051e68`

## callees

- `0x180001f94`
- `0x18004f8d0`
- `0x18005281c`
- `0x180052f04`
- `0x18005cf30`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180052f90`
- `ntdll!RtlNtStatusToDosError` at `0x180052f90`
- `bcd!BcdCloseObject` at `0x1800530df`
- `bcd!BcdCloseObject` at `0x1800530df`
- `bcd!BcdOpenObject` at `0x180052f51`
- `bcd!BcdOpenObject` at `0x180052f51`

## pseudocode

```c

```
