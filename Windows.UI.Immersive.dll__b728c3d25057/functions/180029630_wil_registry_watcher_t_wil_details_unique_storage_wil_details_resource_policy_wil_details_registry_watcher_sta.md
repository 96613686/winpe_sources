# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::callback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x180029630`
- end: `0x180029750`
- name: `?callback@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `288`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180008000`
- `0x180029630`
- `0x18002aab8`
- `0x180043d5c`
- `0x180068da8`
- `0x18006b9b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029729`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029729`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800296d5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800296d5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180029702`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180029702`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180029672`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180029672`

## string_xrefs

- `0x1800296a8`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`

## pseudocode

```c

```
