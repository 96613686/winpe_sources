# AslLogpWriteLog(_ASL_LOG *,char const *,unsigned __int64)

- ea: `0x18000818c`
- end: `0x180008388`
- name: `?AslLogpWriteLog@@YAXPEAU_ASL_LOG@@PEBD_K@Z`
- size: `508`
- prototype: `void(struct _ASL_LOG *, const char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800080e0`
- `0x1800282b4`

## callees

- `0x18000818c`
- `0x18002ee20`
- `0x180039b18`
- `0x180039b54`
- `0x18005841c`
- `0x18005915d`
- `0x180059175`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800082c0`
- `ntdll!RtlLeaveCriticalSection` at `0x180008371`
- `ntdll!RtlLeaveCriticalSection` at `0x1800082c0`
- `ntdll!RtlLeaveCriticalSection` at `0x180008371`
- `ntdll!RtlEnterCriticalSection` at `0x1800081bb`
- `ntdll!RtlEnterCriticalSection` at `0x18000833b`
- `ntdll!RtlEnterCriticalSection` at `0x1800081bb`
- `ntdll!RtlEnterCriticalSection` at `0x18000833b`
- `ntdll!RtlReAllocateHeap` at `0x180008266`
- `ntdll!RtlReAllocateHeap` at `0x180008266`
- `ntdll!RtlAllocateHeap` at `0x180008246`
- `ntdll!RtlAllocateHeap` at `0x180008246`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x180008305`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x180008305`

## pseudocode

```c

```
