# GetCurrentUserContext(unsigned __int64 *)

- ea: `0x1800c1dd8`
- end: `0x1800c1ed8`
- name: `?GetCurrentUserContext@@YAJPEA_K@Z`
- size: `256`
- prototype: `int(unsigned __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1801545c4`

## callees

- `0x18006cb78`
- `0x180098bf4`
- `0x1800a021c`
- `0x1800baaac`
- `0x1800c1dd8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1e13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1e13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c1e5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c1e5f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800c1e72`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800c1e72`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c1e05`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c1e05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c1dee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c1dee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c1eb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c1eb7`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800c1e9c`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800c1e9c`

## pseudocode

```c

```
