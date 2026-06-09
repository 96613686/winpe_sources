# IPHelper::CreateRuntimePortReservation(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>> &,ushort &,ushort,INET_PORT_RESERVATION_TOKEN *)

- ea: `0x180089d24`
- end: `0x180089e3a`
- name: `?CreateRuntimePortReservation@IPHelper@@SAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?closesocket@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0_K@details@wil@@@details@wil@@@wil@@AEAGGPEAUINET_PORT_RESERVATION_TOKEN@@@Z`
- size: `278`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801c4f5c`
- `0x1801c5438`
- `0x1801c5c9c`

## callees

- `0x18005f0c0`
- `0x180087cc0`
- `0x180089d24`

## import_xrefs

- `WS2_32!WSAIoctl` at `0x180089db6`
- `WS2_32!WSAIoctl` at `0x180089db6`
- `WS2_32!__imp_htons` at `0x180089d5d`
- `WS2_32!__imp_htons` at `0x180089d5d`
- `WS2_32!__imp_ntohs` at `0x180089e1a`
- `WS2_32!__imp_ntohs` at `0x180089e1a`
- `WS2_32!__imp_WSAGetLastError` at `0x180089dbe`
- `WS2_32!__imp_WSAGetLastError` at `0x180089dcb`
- `WS2_32!__imp_WSAGetLastError` at `0x180089dbe`
- `WS2_32!__imp_WSAGetLastError` at `0x180089dcb`

## string_xrefs

- `0x180089df0`: `onecore\vm\dv\net\hns\service\common\helperlib\src\iphelper.cpp`

## pseudocode

```c

```
