# CEMfObject::Draw(void *,HDC__ *,HDC__ *,_RECTL const *,_RECTL const *,int (*)(unsigned __int64),unsigned __int64)

- ea: `0x18009d5c0`
- end: `0x18009d75d`
- name: `?Draw@CEMfObject@@UEAAJPEAXPEAUHDC__@@1PEBU_RECTL@@2P6AH_K@Z3@Z`
- size: `413`
- prototype: `HRESULT __fastcall(CEMfObject *this, void *__formal, HDC__ *__formal, HDC__ *hdcDraw, const _RECTL *lprcBounds, const _RECTL *__formal, int (__fastcall *pfnContinue)(unsigned __int64), unsigned __int64 dwContinue)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18009d45c`
- `0x18009d5c0`
- `0x18009dc84`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x18009d664`
- `KERNELBASE!GlobalAlloc` at `0x18009d664`
- `KERNELBASE!GlobalFree` at `0x18009d6f5`
- `KERNELBASE!GlobalFree` at `0x18009d6f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d6cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d706`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d6cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d706`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18009d6ec`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18009d6ec`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18009d679`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18009d679`
- `GDI32!DeleteMetaFile` at `0x18009d6c7`
- `GDI32!DeleteMetaFile` at `0x18009d6c7`
- `GDI32!SaveDC` at `0x18009d602`
- `GDI32!SaveDC` at `0x18009d602`
- `GDI32!EnumMetaFile` at `0x18009d6be`
- `GDI32!EnumMetaFile` at `0x18009d6be`
- `GDI32!RestoreDC` at `0x18009d747`
- `GDI32!RestoreDC` at `0x18009d747`
- `GDI32!GetWinMetaFileBits` at `0x18009d64d`
- `GDI32!GetWinMetaFileBits` at `0x18009d696`
- `GDI32!GetWinMetaFileBits` at `0x18009d64d`
- `GDI32!GetWinMetaFileBits` at `0x18009d696`
- `GDI32!SetMetaFileBitsEx` at `0x18009d6a5`
- `GDI32!SetMetaFileBitsEx` at `0x18009d6a5`
- `GDI32!EnumEnhMetaFile` at `0x18009d73b`
- `GDI32!EnumEnhMetaFile` at `0x18009d73b`

## pseudocode

```c

```
