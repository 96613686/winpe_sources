# wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)

- ea: `0x180053378`
- end: `0x18005345d`
- name: `?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z`
- size: `229`
- prototype: `__int64 __fastcall(HANDLE Token)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001d490`

## callees

- `0x18001d4f4`
- `0x180053378`
- `0x18007c220`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180053390`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180053390`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800533c5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800533c5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800533a9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800533a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053440`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053440`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800533b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005342e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800533b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005342e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005344d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053455`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005344d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053455`

## string_xrefs

- `0x1800533d9`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c

```
