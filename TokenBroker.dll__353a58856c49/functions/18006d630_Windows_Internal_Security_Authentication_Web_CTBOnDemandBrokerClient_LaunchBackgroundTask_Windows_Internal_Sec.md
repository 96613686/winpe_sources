# Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient::LaunchBackgroundTask(Windows::Internal::Security::Authentication::Web::CallerContext *,ushort const *,ushort const *,_GUID *,uchar *,ulong,void *,bool)

- ea: `0x18006d630`
- end: `0x18006da07`
- name: `?LaunchBackgroundTask@CTBOnDemandBrokerClient@Web@Authentication@Security@Internal@Windows@@QEAAJPEAVCallerContext@23456@PEBG1PEAU_GUID@@PEAEKPEAX_N@Z`
- size: `983`
- prototype: `int(Windows::Internal::Security::Authentication::Web::CTBOnDemandBrokerClient *__hidden this, struct Windows::Internal::Security::Authentication::Web::CallerContext *, const unsigned __int16 *, const unsigned __int16 *, struct _GUID *, unsigned __int8 *, unsigned int, void *, bool)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180066608`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x180030adc`
- `0x18003c5e8`
- `0x18003c6f4`
- `0x180040790`
- `0x180040880`
- `0x180041084`
- `0x18004a544`
- `0x180057e10`
- `0x18006d454`
- `0x18006d630`
- `0x18008e690`
- `0x18008e6cc`
- `0x1800da250`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006d851`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006d851`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006d882`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006d882`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006d8fb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006d8fb`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18006d973`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18006d973`
- `ntdll!RtlQueryWnfStateData` at `0x18006d9ab`
- `ntdll!RtlQueryWnfStateData` at `0x18006d9ab`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtQueryWorkItemStatusStateName` at `0x18006d91f`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtQueryWorkItemStatusStateName` at `0x18006d91f`

## string_xrefs

- `0x18006d6c7`: `onecore\ds\security\tokenbroker\broker\lib\tbodbclient.cpp`
- `0x18006d743`: `onecore\ds\security\tokenbroker\broker\lib\tbodbclient.cpp`
- `0x18006d79a`: `onecore\ds\security\tokenbroker\broker\lib\tbodbclient.cpp`

## pseudocode

```c

```
