# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x1800083b8`
- end: `0x18000841d`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `101`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800086a4`

## callees

- `0x1800083b8`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800083fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800083fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800083e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800083e5`

## string_xrefs

- `0x1800083de`: `ntdll.dll`
- `0x1800083f2`: `RtlUnregisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
