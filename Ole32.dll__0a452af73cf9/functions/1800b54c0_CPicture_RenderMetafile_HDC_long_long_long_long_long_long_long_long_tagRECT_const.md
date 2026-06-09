# CPicture::RenderMetafile(HDC__ *,long,long,long,long,long,long,long,long,tagRECT const *)

- ea: `0x1800b54c0`
- end: `0x1800b580b`
- name: `?RenderMetafile@CPicture@@QEAAJPEAUHDC__@@JJJJJJJJPEBUtagRECT@@@Z`
- size: `843`
- prototype: `HRESULT __fastcall(CPicture *this, HDC__ *hdc, int x, int y, int cx, int cy, int xSrc, int ySrc, int cxSrc, int cySrc, const tagRECT *prcWBounds)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800b5100`

## callees

- `0x1800276c4`
- `0x180052390`
- `0x180052760`
- `0x1800b54c0`
- `0x1800b62b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b567d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b567d`
- `GDI32!OffsetViewportOrgEx` at `0x1800b562d`
- `GDI32!OffsetViewportOrgEx` at `0x1800b562d`
- `GDI32!GetWindowOrgEx` at `0x1800b5586`
- `GDI32!GetWindowOrgEx` at `0x1800b5586`
- `GDI32!DeleteMetaFile` at `0x1800b5773`
- `GDI32!DeleteMetaFile` at `0x1800b5773`
- `GDI32!SetMapMode` at `0x1800b5578`
- `GDI32!SetMapMode` at `0x1800b5578`
- `GDI32!GetDeviceCaps` at `0x1800b5524`
- `GDI32!GetDeviceCaps` at `0x1800b5524`
- `GDI32!SaveDC` at `0x1800b5506`
- `GDI32!SaveDC` at `0x1800b5506`
- `GDI32!IntersectClipRect` at `0x1800b555d`
- `GDI32!IntersectClipRect` at `0x1800b555d`
- `GDI32!PlayEnhMetaFile` at `0x1800b573e`
- `GDI32!PlayEnhMetaFile` at `0x1800b573e`
- `GDI32!SetViewportExtEx` at `0x1800b5643`
- `GDI32!SetViewportExtEx` at `0x1800b5643`
- `GDI32!EnumMetaFile` at `0x1800b576a`
- `GDI32!EnumMetaFile` at `0x1800b5788`
- `GDI32!EnumMetaFile` at `0x1800b576a`
- `GDI32!EnumMetaFile` at `0x1800b5788`
- `GDI32!RestoreDC` at `0x1800b57e1`
- `GDI32!RestoreDC` at `0x1800b57e1`

## pseudocode

```c

```
