# CbsRegQueryDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong *)

- ea: `0x1800443e4`
- end: `0x1800447f7`
- name: `?CbsRegQueryDWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEAK@Z`
- size: `1043`
- prototype: `int(HKEY, const wchar_t *, unsigned int, const wchar_t *, unsigned int *)`
- caller_count: `5`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800375fc`
- `0x1800465b8`
- `0x180046680`
- `0x180070418`
- `0x1801adee8`

## callees

- `0x1800031d0`
- `0x18000ba40`
- `0x18000f614`
- `0x18000f874`
- `0x18001a810`
- `0x1800296a4`
- `0x180044170`
- `0x1800443e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044561`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044696`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800447c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044561`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044696`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800447c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004454d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044686`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800447b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004454d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044686`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800447b2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180044658`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180044658`

## string_xrefs

- `0x180044594`: `Failed to open the registry root: n/a, key: {}.`
- `0x1800446c8`: `Failed to query registry value: {}`
- `0x18004473b`: `Registry value is not a DWORD type.`

## pseudocode

```c

```
