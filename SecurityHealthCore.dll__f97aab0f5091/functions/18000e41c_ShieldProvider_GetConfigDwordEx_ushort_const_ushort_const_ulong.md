# ShieldProvider::GetConfigDwordEx(ushort const *,ushort const *,ulong *)

- ea: `0x18000e41c`
- end: `0x18000e4fa`
- name: `?GetConfigDwordEx@ShieldProvider@@YAJPEBG0PEAK@Z`
- size: `222`
- prototype: `__int64 __fastcall(HKEY *this, HKEY, const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18000e3ec`
- `0x18001c050`

## callees

- `0x18000a7ec`
- `0x18000e41c`
- `0x1800cf6f8`
- `0x1800dd908`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e47c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e4ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e4e2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e47c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e4ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e4e2`

## string_xrefs

- `0x18000e45e`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\service\config.cpp`
- `0x18000e4ae`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\service\config.cpp`

## pseudocode

```c

```
