# Csl::OpenRegistryKey(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,Csl::RegistryKey &)

- ea: `0x1800343f0`
- end: `0x180034520`
- name: `?OpenRegistryKey@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@AEAVRegistryKey@1@@Z`
- size: `304`
- prototype: `int __high(HKEY, const unsigned __int16 *, enum Csl::RegistryKeyAccess, struct Csl::RegistryKey *)`
- caller_count: `47`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002c1f4`
- `0x180034364`
- `0x180068f7c`
- `0x18006e0e8`
- `0x18006f4c8`
- `0x18006f6b8`
- `0x18006f7bc`
- `0x18006fc28`
- `0x180070698`
- `0x18007095c`
- `0x180071674`
- `0x1800810f4`
- `0x1800812c8`
- `0x180083ea0`
- `0x180085d60`
- `0x180085edc`
- `0x180087344`
- `0x180087b80`
- `0x180087dfc`
- `0x180087f4c`
- `0x18008a840`
- `0x18008aaa4`
- `0x18008ab5c`
- `0x1800c20bc`
- `0x1800c44ac`
- `0x1800c5b18`
- `0x1800cb858`
- `0x1800cc330`
- `0x1800cc4ec`
- `0x1800cc648`
- `0x1800cc798`
- `0x1800d9f2c`
- `0x1800de860`
- `0x1800df82c`
- `0x1800e1200`
- `0x1800e1f94`
- `0x1800eb644`
- `0x1800ebd18`
- `0x1800ee910`
- `0x1800eeea0`
- `0x1800ef0a4`
- `0x1800fa1cc`
- `0x1800fa4d8`
- `0x1800fb5b0`
- `0x1800fea78`
- `0x180198f7c`
- `0x1801993b8`

## callees

- `0x180032344`
- `0x1800343f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034498`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034498`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800344b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800344b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034467`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800344a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800344d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800344eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034505`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034467`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800344a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800344d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800344eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034505`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034418`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034418`

## string_xrefs

- `0x180034442`: `onecore\base\gendrv\silos\csl\lib\cslregistry.cpp`
- `0x180034436`: `Failed to open registry key with name '%ws'`

## pseudocode

```c

```
