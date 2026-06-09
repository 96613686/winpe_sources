# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x14000c51c`
- end: `0x14000c581`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `101`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x14000c9b8`

## callees

- `0x14000c51c`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000c560`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000c560`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000c549`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000c549`

## string_xrefs

- `0x14000c542`: `ntdll.dll`
- `0x14000c556`: `RtlUnregisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
