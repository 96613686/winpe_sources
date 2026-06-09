# CbsRegQueryMultiStringValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,CCbsStringArray *)

- ea: `0x180044800`
- end: `0x180044f2f`
- name: `?CbsRegQueryMultiStringValue@@YAJPEAUHKEY__@@PEB_WK1PEAVCCbsStringArray@@@Z`
- size: `1839`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, const wchar_t *@<rdx>, unsigned int@<r8d>, const wchar_t *@<r9>, struct CCbsStringArray *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1800e3550`
- `0x1800e3ad4`

## callees

- `0x1800031d0`
- `0x1800062b8`
- `0x18000ba40`
- `0x18000f614`
- `0x18000f874`
- `0x18001a810`
- `0x1800296a4`
- `0x18003cbbc`
- `0x180044170`
- `0x180044800`
- `0x180045bfc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044982`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044ac8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044bfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044cf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044dd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044eb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044f00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044982`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044ac8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044bfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044cf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044dd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044eb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044f00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004496e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044ab4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044bea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044ce3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044dc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044ea1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044ef0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004496e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044ab4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044bea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044ce3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044dc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044ea1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044ef0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180044a7e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180044ca6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180044a7e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180044ca6`

## string_xrefs

- `0x1800449b5`: `Failed to open the registry root: n/a, key: {}.`
- `0x180044af3`: `Failed to query value to get type and size of registry root: n/a, value: {}`
- `0x180044b66`: `Registry value is not a multi-string type.`
- `0x180044d2a`: `Failed to query registry value: {}`

## pseudocode

```c

```
