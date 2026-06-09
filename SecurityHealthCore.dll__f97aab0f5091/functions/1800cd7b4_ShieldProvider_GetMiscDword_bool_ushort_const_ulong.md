# ShieldProvider::GetMiscDword(bool,ushort const *,ulong *)

- ea: `0x1800cd7b4`
- end: `0x1800cd8c4`
- name: `?GetMiscDword@ShieldProvider@@YAJ_NPEBGPEAK@Z`
- size: `272`
- prototype: `int(ShieldProvider *__hidden this, bool, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800cd8cc`

## callees

- `0x18000a7ec`
- `0x1800cd7b4`
- `0x1800cf6f8`
- `0x1800dd908`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cd844`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cd894`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cd8ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cd844`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cd894`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cd8ac`

## string_xrefs

- `0x1800cd7fb`: `SOFTWARE\Microsoft\Windows Security Health\Miscellaneous`
- `0x1800cd7d4`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\shieldutil\shieldproviderutil.cpp`
- `0x1800cd826`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\shieldutil\shieldproviderutil.cpp`
- `0x1800cd878`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\shieldutil\shieldproviderutil.cpp`

## pseudocode

```c

```
