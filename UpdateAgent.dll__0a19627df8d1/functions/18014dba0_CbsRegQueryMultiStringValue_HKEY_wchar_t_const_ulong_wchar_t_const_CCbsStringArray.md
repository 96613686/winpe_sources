# CbsRegQueryMultiStringValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,CCbsStringArray *)

- ea: `0x18014dba0`
- end: `0x18014e37c`
- name: `?CbsRegQueryMultiStringValue@@YAJPEAUHKEY__@@PEB_WK1PEAVCCbsStringArray@@@Z`
- size: `2012`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, const wchar_t *@<rdx>, unsigned int@<r8d>, const wchar_t *@<r9>, struct CCbsStringArray *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18013957c`
- `0x180139ac0`

## callees

- `0x1800059d0`
- `0x1800059f4`
- `0x18000a0e8`
- `0x18000b508`
- `0x18000c4c4`
- `0x18008b38c`
- `0x18008b3ec`
- `0x180149b54`
- `0x18014d3d4`
- `0x18014dba0`
- `0x18014f0c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014dd17`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014dde5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014de72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014df3c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014dffe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014e08d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014e115`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014e1f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014e2d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014e32d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014dd17`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014dde5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014de72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014df3c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014dffe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014e08d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014e115`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014e1f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014e2d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18014e32d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014de3c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014e0d7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014de3c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18014e0d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014dd27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014ddf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014de86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014df4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014e00e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014e09d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014e125`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014e206`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014e2e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014e33d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014dd27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014ddf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014de86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014df4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014e00e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014e09d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014e125`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014e206`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014e2e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014e33d`

## string_xrefs

- `0x18014dd60`: `Failed to open the registry root: n/a, key: {}.`
- `0x18014deb7`: `Failed to query value to get type and size of registry root: n/a, value: {}`
- `0x18014df82`: `Registry value is not a multi-string type.`
- `0x18014e162`: `Failed to query registry value: {}`

## pseudocode

```c

```
