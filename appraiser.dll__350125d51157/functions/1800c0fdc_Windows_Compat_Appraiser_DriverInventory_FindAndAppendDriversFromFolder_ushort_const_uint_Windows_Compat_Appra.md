# Windows::Compat::Appraiser::DriverInventory::FindAndAppendDriversFromFolder(ushort const *,uint,Windows::Compat::Appraiser::IAssetAppender *)

- ea: `0x1800c0fdc`
- end: `0x1800c1382`
- name: `?FindAndAppendDriversFromFolder@DriverInventory@Appraiser@Compat@Windows@@CAJPEBGIPEAVIAssetAppender@234@@Z`
- size: `934`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, struct Windows::Compat::Appraiser::IAssetAppender *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800c0fdc`
- `0x1800c1390`

## callees

- `0x180008570`
- `0x1800092dc`
- `0x18002ebb8`
- `0x1800301d0`
- `0x18008e988`
- `0x1800c0fdc`
- `0x1800c1f08`
- `0x1801ac054`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800c121b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800c121b`
- `KERNEL32!FindClose` at `0x1800c1350`
- `KERNEL32!FindClose` at `0x1800c1350`
- `KERNEL32!FindNextFileW` at `0x1800c127f`
- `KERNEL32!FindNextFileW` at `0x1800c127f`
- `KERNEL32!FindFirstFileW` at `0x1800c10f3`
- `KERNEL32!FindFirstFileW` at `0x1800c10f3`
- `KERNEL32!GetLastError` at `0x1800c1102`
- `KERNEL32!GetLastError` at `0x1800c1114`
- `KERNEL32!GetLastError` at `0x1800c1133`
- `KERNEL32!GetLastError` at `0x1800c128d`
- `KERNEL32!GetLastError` at `0x1800c129c`
- `KERNEL32!GetLastError` at `0x1800c12bb`
- `KERNEL32!GetLastError` at `0x1800c1102`
- `KERNEL32!GetLastError` at `0x1800c1114`
- `KERNEL32!GetLastError` at `0x1800c1133`
- `KERNEL32!GetLastError` at `0x1800c128d`
- `KERNEL32!GetLastError` at `0x1800c129c`
- `KERNEL32!GetLastError` at `0x1800c12bb`
- `SHLWAPI!PathFindExtensionW` at `0x1800c120b`
- `SHLWAPI!PathFindExtensionW` at `0x1800c120b`

## string_xrefs

- `0x1800c1092`: `onecore\base\appcompat\appraiser\inventory\driverinventory.cpp`
- `0x1800c10c3`: `onecore\base\appcompat\appraiser\inventory\driverinventory.cpp`
- `0x1800c11fd`: `Error appending in subdirectory %ls: [0x%x].`
- `0x1800c12ed`: `Error appending in subdirectory %ls: [0x%x].`
- `0x1800c1148`: `Error finding files in directory %ls: [%d].`
- `0x1800c1086`: `Windows::Compat::Appraiser::DriverInventory::FindAndAppendDriversFromFolder`
- `0x1800c10b7`: `Windows::Compat::Appraiser::DriverInventory::FindAndAppendDriversFromFolder`
- `0x1800c1075`: `Error combining path: [0x%x].`

## pseudocode

```c

```
