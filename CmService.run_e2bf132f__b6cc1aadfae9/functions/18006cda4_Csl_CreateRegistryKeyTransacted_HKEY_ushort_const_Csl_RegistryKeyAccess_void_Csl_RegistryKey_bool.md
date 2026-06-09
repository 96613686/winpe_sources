# Csl::CreateRegistryKeyTransacted(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,void *,Csl::RegistryKey &,bool &)

- ea: `0x18006cda4`
- end: `0x18006cf06`
- name: `?CreateRegistryKeyTransacted@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@PEAXAEAVRegistryKey@1@AEA_N@Z`
- size: `354`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180068f7c`
- `0x1800812c8`
- `0x180083ea0`
- `0x1800bf75c`
- `0x1800c20bc`
- `0x1800de860`
- `0x1800df82c`
- `0x1800ebd18`

## callees

- `0x180032344`
- `0x18006cda4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ce84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ce84`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006cea3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006cea3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ce4d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ce95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cec1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ceec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ce4d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ce95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cec1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ceec`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x18006ce00`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x18006ce00`

## string_xrefs

- `0x18006ce18`: `Failed to create registry key transacted with name '%ws'`
- `0x18006ce24`: `onecore\base\gendrv\silos\csl\lib\cslregistry.cpp`

## pseudocode

```c

```
