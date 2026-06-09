# VwaitForMultipleObjects(ulong,void * const *,int,ulong)

- ea: `0x180073710`
- end: `0x1800738a3`
- name: `?VwaitForMultipleObjects@@YAKKPEBQEAXHK@Z`
- size: `403`
- prototype: `unsigned int __fastcall(DWORD nCount, HANDLE *lpHandles, BOOL bWaitAll, DWORD dwMilliseconds)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800db960`
- `0x1800dbda0`

## callees

- `0x180048d40`
- `0x180048db0`
- `0x180073710`
- `0x1800838f0`
- `0x180133d30`
- `0x1801519a0`

## import_xrefs

- `KERNEL32!WaitForMultipleObjects` at `0x18007387f`
- `KERNEL32!WaitForMultipleObjects` at `0x18007387f`
- `KERNEL32!GetProcAddress` at `0x1800737f2`
- `KERNEL32!GetProcAddress` at `0x1800737f2`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800737a9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180073824`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800737a9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180073824`

## string_xrefs

- `0x180073750`: `ole32.dll`

## pseudocode

```c

```
