# ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)

- ea: `0x1800a6414`
- end: `0x1800a6460`
- name: `?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z`
- size: `76`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, PHANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18003d38c`

## callees

- `0x1800a6414`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a6424`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a6424`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a643a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a643a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6444`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6444`

## pseudocode

```c

```
