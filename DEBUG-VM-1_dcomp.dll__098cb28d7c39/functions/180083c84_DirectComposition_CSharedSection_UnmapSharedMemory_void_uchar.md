# DirectComposition::CSharedSection::UnmapSharedMemory(void *,uchar *)

- ea: `0x180083c84`
- end: `0x180083cb6`
- name: `?UnmapSharedMemory@CSharedSection@DirectComposition@@CAXPEAXPEAE@Z`
- size: `50`
- prototype: `void __fastcall(void *, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180083bf8`
- `0x180083cbc`

## callees

- `0x180083c84`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180083c9e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180083c9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180083c8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180083c8d`
- `ntdll!NtUnmapViewOfSection` at `0x180083caf`

## pseudocode

```c

```
