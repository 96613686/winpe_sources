# CreateObjectDescriptor(_GUID,ulong,tagSIZE const *,_POINTL const *,ulong,ushort *,ushort *)

- ea: `0x180084a38`
- end: `0x180084b97`
- name: `?CreateObjectDescriptor@@YAPEAXU_GUID@@KPEBUtagSIZE@@PEBU_POINTL@@KPEAG3@Z`
- size: `351`
- prototype: `void *__fastcall(_GUID clsid, unsigned int psizel, const tagSIZE *ppointl, const _POINTL *lpszFullUserTypeName, unsigned int lpszSrcOfCopy, wchar_t *clsid, wchar_t *dwAspect)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180091294`

## callees

- `0x180009374`
- `0x180084a38`
- `0x1800c4651`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x180084ab7`
- `KERNELBASE!GlobalAlloc` at `0x180084ab7`
- `KERNELBASE!GlobalFree` at `0x180084ae2`
- `KERNELBASE!GlobalFree` at `0x180084ae2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180084ad9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180084b89`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180084ad9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180084b89`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180084ac8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180084ac8`

## pseudocode

```c

```
