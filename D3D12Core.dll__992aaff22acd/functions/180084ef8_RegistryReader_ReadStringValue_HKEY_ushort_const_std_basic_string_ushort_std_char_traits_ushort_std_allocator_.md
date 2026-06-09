# RegistryReader::ReadStringValue(HKEY__ *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180084ef8`
- end: `0x180084f9b`
- name: `?ReadStringValue@RegistryReader@@SAJPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `163`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, LPBYTE lpData)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180084938`
- `0x180129ca8`
- `0x180129eec`
- `0x18012a490`
- `0x18012ae60`
- `0x18012ca1c`

## callees

- `0x180084ef8`
- `0x180085cc0`
- `0x180085d84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180084f2b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180084f86`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180084f2b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180084f86`

## pseudocode

```c

```
