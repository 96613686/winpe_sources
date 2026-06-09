# ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)

- ea: `0x180095dac`
- end: `0x180095df8`
- name: `?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z`
- size: `76`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, PHANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180095cf4`

## callees

- `0x180095dac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095ddc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095ddc`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180095dd2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180095dd2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180095dbc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180095dbc`

## pseudocode

```c

```
