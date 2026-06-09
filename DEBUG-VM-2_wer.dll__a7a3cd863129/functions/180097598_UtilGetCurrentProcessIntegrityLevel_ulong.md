# UtilGetCurrentProcessIntegrityLevel(ulong *)

- ea: `0x180097598`
- end: `0x180097676`
- name: `?UtilGetCurrentProcessIntegrityLevel@@YAJPEAK@Z`
- size: `222`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003daec`

## callees

- `0x18000716c`
- `0x180007e10`
- `0x18001fe24`
- `0x18002c570`
- `0x180049310`
- `0x18004acbc`
- `0x180097598`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800975c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800975c5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800975d6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800975d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800975ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800975ec`

## pseudocode

```c

```
