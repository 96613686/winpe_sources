# FDICreate

- ea: `0x1800cc284`
- end: `0x1800cc3c8`
- name: `FDICreate`
- size: `324`
- prototype: `HFDI __cdecl(PFNALLOC pfnalloc, PFNFREE pfnfree, PFNOPEN pfnopen, PFNREAD pfnread, PFNWRITE pfnwrite, PFNCLOSE pfnclose, PFNSEEK pfnseek, int cpuType, PERF perf)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800b6540`

## callees

- `0x1800cc284`
- `0x18011c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800cc3a8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800cc3ba`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800cc3a8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800cc3ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cc2b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cc2cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cc2e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cc302`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cc2b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cc2cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cc2e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cc302`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x1800cc291`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x1800cc291`

## string_xrefs

- `0x1800cc2a7`: `FDICreate`
- `0x1800cc2be`: `FDICopy`

## pseudocode

```c

```
