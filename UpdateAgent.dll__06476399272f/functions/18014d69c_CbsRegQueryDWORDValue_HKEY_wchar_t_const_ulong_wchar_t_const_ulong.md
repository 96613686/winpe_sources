# CbsRegQueryDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong *)

- ea: `0x18014d69c`
- end: `0x18014db98`
- name: `?CbsRegQueryDWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEAK@Z`
- size: `1276`
- prototype: `int(HKEY, const wchar_t *, unsigned int, const wchar_t *, unsigned int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800c7778`
- `0x18026a53c`

## callees

- `0x1800059d0`
- `0x18000a0e8`
- `0x18000b508`
- `0x18000c4c4`
- `0x18008b38c`
- `0x18008b3ec`
- `0x18014d3d4`
- `0x18014d69c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014d807`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014d8d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014d96d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014da3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014dafb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014db4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014d807`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014d8d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014d96d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014da3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014dafb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014db4b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014d93f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014d93f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014d817`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014d8e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014d97d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014da4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014db0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014db5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014d817`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014d8e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014d97d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014da4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014db0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014db5b`

## string_xrefs

- `0x18014d854`: `Failed to open the registry root: n/a, key: {}.`
- `0x18014d9bd`: `Failed to query registry value: {}`
- `0x18014da8d`: `Registry value is not a DWORD type.`

## pseudocode

```c

```
