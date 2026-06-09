# CDeploymentSession::ExecuteMitigations(void)

- ea: `0x180048f88`
- end: `0x18004961f`
- name: `?ExecuteMitigations@CDeploymentSession@@QEAAJXZ`
- size: `1687`
- prototype: `__int64 __fastcall(CDeploymentSession *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting`

## callers

- `0x180052d40`

## callees

- `0x1800059d0`
- `0x180008fbc`
- `0x18003557c`
- `0x180039f90`
- `0x18003c418`
- `0x1800408d0`
- `0x180048f88`
- `0x180067684`
- `0x180077664`
- `0x180078b9c`
- `0x180091364`
- `0x1800970bc`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180049207`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180049207`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180049328`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180049328`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800492c8`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180049512`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800492c8`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180049512`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800492b1`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800492b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004914c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049524`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049557`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004958a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800495c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004914c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049524`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049557`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004958a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800495c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049161`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049539`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004956c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004959f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800495dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049161`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049539`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004956c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004959f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800495dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800492e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049341`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800492e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049341`

## string_xrefs

- `0x180049014`: `ExecuteMitigations: Mitigations already executed for this scenario.`
- `0x18004902f`: `MitigationPath`
- `0x1800490ac`: `Mitigation.dll`
- `0x18004931e`: `CreateMitigationManager`

## pseudocode

```c

```
