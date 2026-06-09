# ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)

- ea: `0x180079628`
- end: `0x180079674`
- name: `?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z`
- size: `76`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, PHANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180079314`

## callees

- `0x180079628`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079658`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079658`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007964e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007964e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180079638`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180079638`

## pseudocode

```c

```
