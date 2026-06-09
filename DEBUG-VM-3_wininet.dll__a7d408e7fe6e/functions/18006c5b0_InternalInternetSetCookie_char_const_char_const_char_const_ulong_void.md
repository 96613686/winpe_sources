# InternalInternetSetCookie(char const *,char const *,char const *,ulong,void *)

- ea: `0x18006c5b0`
- end: `0x18006cfb9`
- name: `?InternalInternetSetCookie@@YAHPEBD00KPEAX@Z`
- size: `2569`
- prototype: `int(const char *, const char *, const char *, unsigned int, void *)`
- caller_count: `4`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800c6dd0`
- `0x180165220`
- `0x180180bd0`
- `0x180180c00`

## callees

- `0x1800174f8`
- `0x18003759c`
- `0x18006a6b0`
- `0x18006c5b0`
- `0x18006cfc0`
- `0x18006dd10`
- `0x1800701d0`
- `0x1800c2d90`
- `0x1800c60c8`
- `0x18014a7a0`
- `0x180154882`
- `0x1801c9c31`
- `0x1801d6494`
- `0x1801e1790`
- `0x1801e285c`
- `0x1801e3714`
- `0x1801e41b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006cae7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006cb05`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006cae7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006cb05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ca8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ca8b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006c89d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006c951`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006c89d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006c951`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006ca36`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006ca4d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006ca6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006ca85`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006ca36`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006ca4d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006ca6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006ca85`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006ccd7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006ccd7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006c782`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006c782`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006c78a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006c78a`
- `ntdll!EtwEventActivityIdControl` at `0x18006c74b`
- `ntdll!EtwEventActivityIdControl` at `0x18006c7a9`
- `ntdll!EtwEventActivityIdControl` at `0x18006cacb`
- `ntdll!EtwEventActivityIdControl` at `0x18006c74b`
- `ntdll!EtwEventActivityIdControl` at `0x18006c7a9`
- `ntdll!EtwEventActivityIdControl` at `0x18006cacb`
- `ntdll!RtlGetLastNtStatus` at `0x18006cce8`
- `ntdll!RtlGetLastNtStatus` at `0x18006cce8`

## pseudocode

```c

```
