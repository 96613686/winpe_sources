# ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)

- ea: `0x1800a0790`
- end: `0x1800a07dc`
- name: `?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z`
- size: `76`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, PHANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800a04b0`

## callees

- `0x1800a0790`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a07c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a07c0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a07b6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a07b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a07a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a07a0`

## pseudocode

```c

```
