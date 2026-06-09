# CbsRegSetStringValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,wchar_t const * const)

- ea: `0x180045908`
- end: `0x180045bf4`
- name: `?CbsRegSetStringValue@@YAJPEAUHKEY__@@PEB_WK1QEB_W@Z`
- size: `748`
- prototype: `__int64 __fastcall(HKEY, const wchar_t *, unsigned int, const wchar_t *, const wchar_t *const)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180069378`

## callees

- `0x1800031d0`
- `0x18000ba40`
- `0x18000f614`
- `0x18000f874`
- `0x18001a810`
- `0x1800296a4`
- `0x180043c70`
- `0x180045908`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045b67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045bc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045b67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045bc6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045b57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045bb6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045b57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045bb6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180045ab9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180045ab9`

## string_xrefs

- `0x1800459f6`: `Failed to create key: {}`
- `0x180045ae8`: `Failed to set registry value: {}`

## pseudocode

```c

```
