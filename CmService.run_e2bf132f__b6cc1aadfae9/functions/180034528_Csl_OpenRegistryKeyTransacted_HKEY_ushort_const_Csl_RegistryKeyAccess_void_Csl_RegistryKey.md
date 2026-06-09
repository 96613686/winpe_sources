# Csl::OpenRegistryKeyTransacted(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,void *,Csl::RegistryKey &)

- ea: `0x180034528`
- end: `0x18003466b`
- name: `?OpenRegistryKeyTransacted@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@PEAXAEAVRegistryKey@1@@Z`
- size: `323`
- prototype: `int __high(HKEY, const unsigned __int16 *, enum Csl::RegistryKeyAccess, void *, struct Csl::RegistryKey *)`
- caller_count: `20`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800532d4`
- `0x18006c2b4`
- `0x180070524`
- `0x180070698`
- `0x18007095c`
- `0x180071464`
- `0x1800810f4`
- `0x180085e1c`
- `0x180087b80`
- `0x180087f4c`
- `0x1800cb858`
- `0x1800cc330`
- `0x1800cc4ec`
- `0x1800cc648`
- `0x1800cc798`
- `0x1800cc950`
- `0x1800e17ac`
- `0x1800e1f94`
- `0x1800eeea0`
- `0x1800ef0a4`

## callees

- `0x180032344`
- `0x180034528`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800345e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800345e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034602`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034602`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800345aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800345f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034620`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034636`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034650`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800345aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800345f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034620`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034636`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034650`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x18003455b`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x18003455b`

## string_xrefs

- `0x180034585`: `onecore\base\gendrv\silos\csl\lib\cslregistry.cpp`
- `0x180034579`: `Failed to open registry key transacted with name '%ws'`

## pseudocode

```c

```
