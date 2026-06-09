# FSServiceDrivenAction::InitStringFromJson(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &,ushort const *,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)

- ea: `0x1800a596c`
- end: `0x1800a5a74`
- name: `?InitStringFromJson@FSServiceDrivenAction@@KAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z`
- size: `264`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a43c0`
- `0x1800a7ac0`
- `0x1800a81e0`
- `0x1800ab2a0`
- `0x1800ac4d0`

## callees

- `0x180004b80`
- `0x18000cc8c`
- `0x180010fe0`
- `0x1800168c8`
- `0x18001ec78`
- `0x1800a596c`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a59ce`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a59ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a59e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a59e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a5a14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a5a14`

## string_xrefs

- `0x1800a5a34`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsservicedrivenaction.cpp`

## pseudocode

```c

```
