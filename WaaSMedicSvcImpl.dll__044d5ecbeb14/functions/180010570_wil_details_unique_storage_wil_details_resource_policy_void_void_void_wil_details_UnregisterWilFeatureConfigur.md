# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x180010570`
- end: `0x1800105d5`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180010968`

## callees

- `0x180010570`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800105b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800105b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001059d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001059d`

## string_xrefs

- `0x180010596`: `ntdll.dll`
- `0x1800105aa`: `RtlUnregisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
