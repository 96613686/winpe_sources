# SettingsCopier::SetRegKeyValue(HKEY__ *,ushort const *,ushort const *,ulong,uchar const *,ulong)

- ea: `0x18039fd58`
- end: `0x18039feec`
- name: `?SetRegKeyValue@SettingsCopier@@CAJPEAUHKEY__@@PEBG1KPEBEK@Z`
- size: `404`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValueName, DWORD dwType, BYTE *lpData, DWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, registry_config`

## callers

- `0x18039f0ec`

## callees

- `0x18039fd58`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18039fe4a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18039fe4a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18039febc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18039febc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18039fdc8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18039fdc8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18039fdef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18039fe65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18039fe8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18039fece`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18039fdef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18039fe65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18039fe8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18039fece`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18039fe16`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18039fe16`

## string_xrefs

- `0x18039fe43`: `SymbolicLinkValue`

## pseudocode

```c

```
