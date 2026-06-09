# ShieldProvider::SetConfigDword(ushort const *,ushort const *,ulong)

- ea: `0x18000ebd4`
- end: `0x18000ecaf`
- name: `?SetConfigDword@ShieldProvider@@YAJPEBG0K@Z`
- size: `219`
- prototype: `__int64 __fastcall(HKEY *this, HKEY, const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18000fad8`
- `0x18001c050`
- `0x18001c75c`

## callees

- `0x18000a7ec`
- `0x18000ebd4`
- `0x1800cf6f8`
- `0x1800de1bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ec2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ec85`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ec97`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ec2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ec85`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ec97`

## string_xrefs

- `0x18000ec0f`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\service\config.cpp`
- `0x18000ec69`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\service\config.cpp`

## pseudocode

```c

```
