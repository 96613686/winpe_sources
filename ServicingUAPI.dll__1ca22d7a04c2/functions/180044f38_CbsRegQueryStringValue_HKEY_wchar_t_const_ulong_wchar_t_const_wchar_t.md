# CbsRegQueryStringValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,wchar_t * *)

- ea: `0x180044f38`
- end: `0x18004553c`
- name: `?CbsRegQueryStringValue@@YAJPEAUHKEY__@@PEB_WK1PEAPEA_W@Z`
- size: `1540`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, const wchar_t *@<rdx>, unsigned int@<r8d>, const wchar_t *@<r9>, wchar_t **)`
- caller_count: `4`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180037570`
- `0x1800375fc`
- `0x180069378`
- `0x1801adee8`

## callees

- `0x1800031d0`
- `0x18000ba40`
- `0x18000f614`
- `0x18000f874`
- `0x18001a810`
- `0x1800296a4`
- `0x18003cbbc`
- `0x18003efe0`
- `0x180044170`
- `0x180044f38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045053`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045316`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045411`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045508`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045053`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045316`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045411`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045508`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045043`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045306`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045401`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800454f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045043`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045306`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045401`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800454f8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800451a2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800452d8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004544a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800451a2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800452d8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004544a`

## string_xrefs

- `0x180045086`: `Failed to open the registry root: n/a, key: {}.`
- `0x18004534e`: `Failed to query value to get type and size of registry root: n/a, value: {}`
- `0x1800451d6`: `Registry value is not a string type.`
- `0x180045261`: `Failed initial query of value to get type, size, and value of registry value: {}`
- `0x18004546f`: `Failed to query registry value: {}`

## pseudocode

```c

```
