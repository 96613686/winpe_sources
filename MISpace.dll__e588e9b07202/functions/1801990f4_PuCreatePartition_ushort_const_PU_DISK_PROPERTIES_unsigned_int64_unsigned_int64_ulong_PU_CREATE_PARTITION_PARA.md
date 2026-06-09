# PuCreatePartition(ushort const *,PU_DISK_PROPERTIES *,unsigned __int64,unsigned __int64,ulong,PU_CREATE_PARTITION_PARAMETERS *,unsigned __int64 *)

- ea: `0x1801990f4`
- end: `0x1801998c9`
- name: `?PuCreatePartition@@YAJPEBGPEAVPU_DISK_PROPERTIES@@_K2KPEAUPU_CREATE_PARTITION_PARAMETERS@@PEA_K@Z`
- size: `2005`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpFileName@<rcx>, struct PU_DISK_PROPERTIES *@<rdx>, unsigned __int64@<r8>, unsigned __int64@<r9>, unsigned int, struct PU_CREATE_PARTITION_PARAMETERS *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `21`
- tags: ``

## callers

- `0x180110ea8`

## callees

- `0x180006290`
- `0x180195a90`
- `0x180195cac`
- `0x180197af0`
- `0x180197ef4`
- `0x180198c5c`
- `0x1801990f4`
- `0x1801998d0`
- `0x18019b994`
- `0x18019bfd8`
- `0x1801a0df0`
- `0x1801a1a48`
- `0x1801a401c`
- `0x1801a422c`
- `0x1801a4520`
- `0x1801a481c`
- `0x1801a4ccc`
- `0x1801a4e88`
- `0x1801a55ec`
- `0x1801a578c`
- `0x1801a59f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180199302`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801996e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180199727`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180199302`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801996e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180199727`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019988f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18019988f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180199877`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180199877`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180199197`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180199750`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180199197`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180199750`

## string_xrefs

- `0x1801994b4`: `DeleteBands`
- `0x1801991e4`: `Disk is read-only`
- `0x1801993f5`: `PuCreateRegions`
- `0x18019973e`: `PuRecreateRegionList`
- `0x180199700`: `PuWriteLayout`
- `0x180199454`: `PuCreatePartLayout`

## pseudocode

```c

```
