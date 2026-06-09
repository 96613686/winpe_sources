# Memory::VirtualAllocWrapper::AllocPages(void *,unsigned __int64,ulong,ulong,bool)

- ea: `0x1801d0a50`
- end: `0x1801d0ce7`
- name: `?AllocPages@VirtualAllocWrapper@Memory@@QEAAPEAXPEAX_KKK_N@Z`
- size: `663`
- prototype: `void *__fastcall(Memory::VirtualAllocWrapper *__hidden this, void *, unsigned __int64, unsigned int, unsigned int, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1801d0cf0`

## callees

- `0x1801d084c`
- `0x1801d0a50`
- `0x18108a7b8`
- `0x18108e998`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x1801d0bf8`
- `KERNEL32!GetCurrentThread` at `0x1801d0c31`
- `KERNEL32!GetCurrentThread` at `0x1801d0cc4`
- `KERNEL32!GetCurrentThread` at `0x1801d0bf8`
- `KERNEL32!GetCurrentThread` at `0x1801d0c31`
- `KERNEL32!GetCurrentThread` at `0x1801d0cc4`
- `KERNEL32!GetProcAddress` at `0x1801d0b41`
- `KERNEL32!GetProcAddress` at `0x1801d0b54`
- `KERNEL32!GetProcAddress` at `0x1801d0b6b`
- `KERNEL32!GetProcAddress` at `0x1801d0b41`
- `KERNEL32!GetProcAddress` at `0x1801d0b54`
- `KERNEL32!GetProcAddress` at `0x1801d0b6b`
- `KERNEL32!GetModuleHandleW` at `0x1801d0b29`
- `KERNEL32!GetModuleHandleW` at `0x1801d0b29`
- `KERNEL32!LeaveCriticalSection` at `0x1801d0bb6`
- `KERNEL32!LeaveCriticalSection` at `0x1801d0bb6`
- `KERNEL32!EnterCriticalSection` at `0x1801d0b0d`
- `KERNEL32!EnterCriticalSection` at `0x1801d0b0d`
- `KERNEL32!GetCurrentProcess` at `0x1801d0b7d`
- `KERNEL32!GetCurrentProcess` at `0x1801d0b7d`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1801d0ab8`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1801d0c5e`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1801d0ab8`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1801d0c5e`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1801d0c9a`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x1801d0c9a`

## string_xrefs

- `0x1801d0b22`: `api-ms-win-core-processthreads-l1-1-3.dll`
- `0x1801d0b4a`: `SetThreadInformation`
- `0x1801d0b61`: `GetThreadInformation`

## pseudocode

```c

```
