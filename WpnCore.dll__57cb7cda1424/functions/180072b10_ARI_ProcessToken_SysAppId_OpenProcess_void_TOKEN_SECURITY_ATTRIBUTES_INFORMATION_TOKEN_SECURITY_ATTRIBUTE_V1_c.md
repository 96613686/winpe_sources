# ARI::ProcessToken::SysAppId::OpenProcess(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x180072b10`
- end: `0x180072ba8`
- name: `?OpenProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `152`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180072978`

## callees

- `0x180072b10`
- `0x180072cc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072b57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072b57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180072b35`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180072b35`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180072b4d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180072b4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072b92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072b92`

## pseudocode

```c

```
