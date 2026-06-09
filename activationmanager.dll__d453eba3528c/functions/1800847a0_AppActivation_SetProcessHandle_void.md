# AppActivation::SetProcessHandle(void *)

- ea: `0x1800847a0`
- end: `0x180084849`
- name: `?SetProcessHandle@AppActivation@@UEAAJPEAX@Z`
- size: `169`
- prototype: `int(AppActivation *__hidden this, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x18003f63c`
- `0x180044408`
- `0x1800847a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800847d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800847e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800847d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800847e2`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800847b3`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800847b3`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18008480e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18008480e`

## pseudocode

```c

```
