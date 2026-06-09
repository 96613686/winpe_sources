# ShieldProvider::SetConfigString(ushort const *,ushort const *,ushort const *)

- ea: `0x18000eda4`
- end: `0x18000ee73`
- name: `?SetConfigString@ShieldProvider@@YAJPEBG00@Z`
- size: `207`
- prototype: `__int64 __fastcall(ShieldProvider *this, unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001a324`
- `0x18001bc88`

## callees

- `0x18000a7ec`
- `0x18000eda4`
- `0x1800cf6f8`
- `0x1800de258`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ee05`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ee49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ee5b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ee05`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ee49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ee5b`

## string_xrefs

- `0x18000ede7`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\service\config.cpp`
- `0x18000ee2d`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\service\config.cpp`
- `0x18000edd0`: `SOFTWARE\Microsoft\Windows Security Health\Platform`

## pseudocode

```c

```
