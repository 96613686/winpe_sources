# Win32NetworkAdapterConfigurationHelper::ReadTcpSetting(_GUID const &,bool,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18022d5d4`
- end: `0x18022d800`
- name: `?ReadTcpSetting@Win32NetworkAdapterConfigurationHelper@@AEAAJAEBU_GUID@@_NPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `556`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18022d00c`

## callees

- `0x18005f0c0`
- `0x18005ffb8`
- `0x18005ffc4`
- `0x180067c00`
- `0x180069104`
- `0x18006c530`
- `0x18008c6c0`
- `0x18022d5d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18022d7c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18022d7c2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18022d70a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18022d70a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18022d75a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18022d75a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18022d695`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18022d695`

## string_xrefs

- `0x18022d64c`: `SYSTEM\CurrentControlSet\Services\NetBT\Parameters\Interfaces`
- `0x18022d645`: `SYSTEM\CurrentControlSet\Services\Tcpip\Parameters\Interfaces`

## pseudocode

```c

```
