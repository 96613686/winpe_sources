# Windows::Compat::Appraiser::Utilities::DisableOOBETrigger(int,ushort const *,ushort const *,ushort const *)

- ea: `0x180084eac`
- end: `0x180085134`
- name: `?DisableOOBETrigger@Utilities@Appraiser@Compat@Windows@@SAJHPEBG00@Z`
- size: `648`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004dc14`

## callees

- `0x18002ebb8`
- `0x1800301d0`
- `0x180084eac`
- `0x18008e3a0`
- `0x18008fadc`
- `0x18021f010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180084f66`
- `KERNEL32!LoadLibraryExW` at `0x180084f66`
- `KERNEL32!GetProcAddress` at `0x18008501a`
- `KERNEL32!GetProcAddress` at `0x18008501a`
- `KERNEL32!GetLastError` at `0x180084fa5`
- `KERNEL32!GetLastError` at `0x180085028`
- `KERNEL32!GetLastError` at `0x180085103`
- `KERNEL32!GetLastError` at `0x18008511b`
- `KERNEL32!GetLastError` at `0x180084fa5`
- `KERNEL32!GetLastError` at `0x180085028`
- `KERNEL32!GetLastError` at `0x180085103`
- `KERNEL32!GetLastError` at `0x18008511b`
- `OLE32!CoUninitialize` at `0x1800850d1`
- `OLE32!CoUninitialize` at `0x1800850d1`
- `OLE32!CoInitializeEx` at `0x180084edc`
- `OLE32!CoInitializeEx` at `0x180084edc`

## string_xrefs

- `0x18008507b`: `Microsoft Compatibility Appraiser Exp`
- `0x180084f09`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180084f31`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180084fbb`: `LoadLibrary(dcntel.dll) failed: [0x%x].`
- `0x180084ff7`: `LoadLibrary(dcntel.dll) failed: [0x%x].`
- `0x180084f02`: `Windows::Compat::Appraiser::Utilities::DisableOOBETrigger`
- `0x180084f2a`: `Windows::Compat::Appraiser::Utilities::DisableOOBETrigger`
- `0x180084f5f`: `dcntel.dll`

## pseudocode

```c

```
