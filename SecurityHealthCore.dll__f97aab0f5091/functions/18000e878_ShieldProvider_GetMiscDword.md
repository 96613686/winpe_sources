# ShieldProvider::GetMiscDword

- ea: `0x18000e878`
- end: `0x18000e986`
- name: `ShieldProvider::GetMiscDword`
- size: `270`
- prototype: `__int64 __fastcall(HKEY)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000e98c`

## callees

- `0x18000a7ec`
- `0x18000e878`
- `0x1800cf6f8`
- `0x1800dd908`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e90a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e956`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e96e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e90a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e956`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e96e`

## string_xrefs

- `0x18000e89b`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\service\config.cpp`
- `0x18000e8ec`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\service\config.cpp`
- `0x18000e93a`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\service\config.cpp`
- `0x18000e8c6`: `SOFTWARE\Microsoft\Windows Security Health\Miscellaneous`

## pseudocode

```c

```
