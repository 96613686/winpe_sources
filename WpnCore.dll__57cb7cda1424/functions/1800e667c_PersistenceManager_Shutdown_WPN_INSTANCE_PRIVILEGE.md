# PersistenceManager::Shutdown(WPN_INSTANCE_PRIVILEGE)

- ea: `0x1800e667c`
- end: `0x1800e677c`
- name: `?Shutdown@PersistenceManager@@AEAAXW4WPN_INSTANCE_PRIVILEGE@@@Z`
- size: `256`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800e3c6c`
- `0x1800e67f0`

## callees

- `0x1800e667c`
- `0x1800e6784`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e66fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e66fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800e66a6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800e66a6`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800e66e6`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800e66e6`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800e66cf`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800e6756`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800e66cf`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800e6756`

## pseudocode

```c

```
