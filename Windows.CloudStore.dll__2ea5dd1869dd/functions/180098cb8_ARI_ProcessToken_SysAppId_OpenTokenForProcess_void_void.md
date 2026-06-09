# ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)

- ea: `0x180098cb8`
- end: `0x180098d04`
- name: `?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z`
- size: `76`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, PHANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1801af740`

## callees

- `0x180098cb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098cfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098cfc`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180098cf2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180098cf2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180098cc8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180098cc8`

## pseudocode

```c

```
