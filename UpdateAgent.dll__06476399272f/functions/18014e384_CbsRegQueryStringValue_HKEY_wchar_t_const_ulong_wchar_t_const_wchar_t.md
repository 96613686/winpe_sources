# CbsRegQueryStringValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,wchar_t * *)

- ea: `0x18014e384`
- end: `0x18014ebc7`
- name: `?CbsRegQueryStringValue@@YAJPEAUHKEY__@@PEB_WK1PEAPEA_W@Z`
- size: `2115`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, const wchar_t *@<rdx>, unsigned int@<r8d>, const wchar_t *@<r9>, wchar_t **)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1800c02fc`
- `0x18026a53c`

## callees

- `0x1800059d0`
- `0x18000a0e8`
- `0x18000b508`
- `0x18000c4c4`
- `0x18008b38c`
- `0x18008b3ec`
- `0x180149b54`
- `0x18014c364`
- `0x18014d3d4`
- `0x18014e384`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014e49e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014e569`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014e5fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014e719`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014e781`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014e85a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014e8cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014e99f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014ea23`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014eb1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014eb76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014e49e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014e569`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014e5fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014e719`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014e781`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014e85a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014e8cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014e99f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014ea23`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014eb1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014eb76`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014e66c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014e8a1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014ea70`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014e66c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014e8a1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014ea70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014e4ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014e579`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014e60e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014e729`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014e791`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014e86a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014e8df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014e9af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014ea33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014eb2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014eb86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014e4ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014e579`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014e60e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014e729`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014e791`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014e86a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014e8df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014e9af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014ea33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014eb2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014eb86`

## string_xrefs

- `0x18014e4e7`: `Failed to open the registry root: n/a, key: {}.`
- `0x18014e91d`: `Failed to query value to get type and size of registry root: n/a, value: {}`
- `0x18014e6a0`: `Registry value is not a string type.`
- `0x18014e7d8`: `Failed initial query of value to get type, size, and value of registry value: {}`
- `0x18014ea9b`: `Failed to query registry value: {}`

## pseudocode

```c

```
