# ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z

- ea: `0x18001b330`
- end: `0x18001b389`
- name: `?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z`
- size: `89`
- prototype: `wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::ReleaseMutex,wistd::integral_constant<unsigned __int64,2>,void *,void *,0,std::nullptr_t> > > *__fastcall(wil::mutex_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::CloseHandle,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> >,wil::err_returncode_policy> *this, wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::ReleaseMutex,wistd::integral_constant<unsigned __int64,2>,void *,void *,0,std::nullptr_t> > > *result, unsigned int *pStatus, unsigned int dwMilliseconds)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001ace8`
- `0x1800300c8`
- `0x1800329f0`

## callees

- `0x18001b330`
- `0x180028ce8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001b349`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001b349`

## string_xrefs

- `0x18001b377`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c

```
