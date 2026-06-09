# CEcsReadOpLock::GetFileHandle(EcsUniqueHandle<void *,Win32HandleDeleter,-1> &)

- ea: `0x1800d168c`
- end: `0x1800d182d`
- name: `?GetFileHandle@CEcsReadOpLock@@QEAAXAEAV?$EcsUniqueHandle@PEAXUWin32HandleDeleter@@$0?0@@@Z`
- size: `417`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800d1364`
- `0x1800d22d0`

## callees

- `0x180003604`
- `0x180007b9c`
- `0x180007e10`
- `0x180008b60`
- `0x180011314`
- `0x1800d168c`
- `0x1800d25e0`

## import_xrefs

- `KERNEL32!DuplicateHandle` at `0x1800d17b8`
- `KERNEL32!DuplicateHandle` at `0x1800d17b8`
- `KERNEL32!GetCurrentProcess` at `0x1800d1780`
- `KERNEL32!GetCurrentProcess` at `0x1800d178d`
- `KERNEL32!GetCurrentProcess` at `0x1800d1780`
- `KERNEL32!GetCurrentProcess` at `0x1800d178d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d180e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d180e`

## string_xrefs

- `0x1800d1701`: `CEcsReadOpLock::GetFileHandle`

## pseudocode

```c

```
