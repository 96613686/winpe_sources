# Windows::Internal::Security::Authentication::TokenBroker::GetCallingProcessHandle(IUnknown *,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)

- ea: `0x18003dc90`
- end: `0x18003df23`
- name: `?GetCallingProcessHandle@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUnknown@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
- size: `659`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000d2b0`

## callees

- `0x18000bd40`
- `0x18003dc90`
- `0x180041050`
- `0x1800565a0`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003dd12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003dd12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003deda`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003deda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003dd80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003de1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003de6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003dd80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003de1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003de6c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003deea`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003deea`
- `combase!__imp_CoGetCallContextOfObject` at `0x18003dcf5`
- `combase!__imp_CoGetCallContextOfObject` at `0x18003dcf5`
- `combase!__imp_CoGetCallLocality` at `0x18003dcc4`
- `combase!__imp_CoGetCallLocality` at `0x18003dcc4`

## string_xrefs

- `0x18003de04`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18003de3a`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18003de52`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18003debf`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`

## pseudocode

```c

```
