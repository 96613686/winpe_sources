# GetExecutablePathFromProcessHandle(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x18000e840`
- end: `0x18000e950`
- name: `?GetExecutablePathFromProcessHandle@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `272`
- prototype: `__int64 __fastcall(HANDLE hProcess)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180027d78`

## callees

- `0x180007c78`
- `0x18000e840`
- `0x180018400`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e86c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e89e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e86c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e89e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e8bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e8bd`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18000e8e2`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18000e8e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e8af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e8af`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e887`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e887`

## string_xrefs

- `0x18000e8fe`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18000e91a`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

## pseudocode

```c

```
