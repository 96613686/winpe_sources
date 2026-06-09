# Windows::Internal::AssignedAccess::MsGraphHelper::BuildHttpRequest(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,Windows::Web::Http::IHttpRequestMessage * *)

- ea: `0x18008b90c`
- end: `0x18008be83`
- name: `?BuildHttpRequest@MsGraphHelper@AssignedAccess@Internal@Windows@@AEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0PEAPEAUIHttpRequestMessage@Http@Web@4@@Z`
- size: `1399`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18008be8c`

## callees

- `0x180006640`
- `0x18000b6b4`
- `0x18000cfe4`
- `0x180010590`
- `0x180010c98`
- `0x1800116bc`
- `0x180013fac`
- `0x180016c24`
- `0x18001f2b0`
- `0x18002001c`
- `0x18002074c`
- `0x1800221e0`
- `0x180022930`
- `0x18008b53c`
- `0x18008b90c`
- `0x18008cd30`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18008b9c4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18008ba22`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18008baf5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18008bc73`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18008b9c4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18008ba22`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18008baf5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18008bc73`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18008b95f`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18008b95f`

## string_xrefs

- `0x18008bad5`: `Windows.Foundation.Uri`
- `0x18008bb4d`: `https://graph.microsoft.com/v1.0/me/memberOf?$top=999&$select=odata.type,id`
- `0x18008bb44`: `https://graph.microsoft.com/v1.0/me/transitiveMemberOf?$top=999&$select=odata.type,id`

## pseudocode

```c

```
