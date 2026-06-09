# FSPrivilegedAction::InitializeParameters(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &)

- ea: `0x1800a95d0`
- end: `0x1800a9709`
- name: `?InitializeParameters@FSPrivilegedAction@@MEAAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z`
- size: `313`
- prototype: `__int64 __fastcall(__int64, struct Windows::Data::Json::IJsonObject **)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180004b80`
- `0x18000cc8c`
- `0x180010fe0`
- `0x1800168c8`
- `0x18001ec78`
- `0x180022a58`
- `0x180087a1c`
- `0x1800a95d0`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a9667`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a9667`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a967b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a967b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a96a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a96a5`

## string_xrefs

- `0x1800a96c8`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsprivilegedaction.cpp`

## pseudocode

```c

```
