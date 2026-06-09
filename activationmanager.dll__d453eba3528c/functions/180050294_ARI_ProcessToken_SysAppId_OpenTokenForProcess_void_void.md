# ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)

- ea: `0x180050294`
- end: `0x1800502e0`
- name: `?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z`
- size: `76`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, PHANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800995dc`

## callees

- `0x180050294`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800502c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800502c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800502a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800502a4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800502ba`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800502ba`

## pseudocode

```c

```
