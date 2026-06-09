# CbsRegSetStringValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,wchar_t const * const)

- ea: `0x18014ed44`
- end: `0x18014f0c1`
- name: `?CbsRegSetStringValue@@YAJPEAUHKEY__@@PEB_WK1QEB_W@Z`
- size: `893`
- prototype: `__int64 __fastcall(HKEY, const wchar_t *, unsigned int, const wchar_t *, const wchar_t *const)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800c02fc`

## callees

- `0x1800059d0`
- `0x18000a0e8`
- `0x18000b508`
- `0x18000c4c4`
- `0x18008b38c`
- `0x18008b3ec`
- `0x18014ced0`
- `0x18014ed44`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014eeb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014efd4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014f01b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014f07f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014eeb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014efd4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014f01b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014f07f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18014ef22`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18014ef22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014eec9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014efe4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014f02b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014f08f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014eec9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014efe4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014f02b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014f08f`

## string_xrefs

- `0x18014ee32`: `Failed to create key: {}`
- `0x18014ef4d`: `Failed to set registry value: {}`

## pseudocode

```c

```
