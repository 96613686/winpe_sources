# SetRectForBubble(CThreadData *,HWND__ *,tagRECT *,char *,tagRECT *)

- ea: `0x1800024c0`
- end: `0x1800026ba`
- name: `?SetRectForBubble@@YAXPEAVCThreadData@@PEAUHWND__@@PEAUtagRECT@@PEAD2@Z`
- size: `506`
- prototype: `void __fastcall(struct CThreadData *, HWND, struct tagRECT *, char *, LPPOINT lpPoint)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180001d04`

## callees

- `0x1800022f8`
- `0x1800024c0`
- `0x1800187f0`
- `0x1800189c0`
- `0x180028b60`
- `0x18002b344`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x18000258d`
- `KERNEL32!lstrlenA` at `0x18000258d`
- `USER32!GetDC` at `0x180002551`
- `USER32!GetDC` at `0x180002551`
- `USER32!ReleaseDC` at `0x1800025bd`
- `USER32!ReleaseDC` at `0x1800025bd`
- `USER32!GetCursorPos` at `0x1800025f8`
- `USER32!GetCursorPos` at `0x1800025f8`
- `USER32!GetCursor` at `0x1800025fe`
- `USER32!GetCursor` at `0x1800025fe`
- `USER32!MapWindowPoints` at `0x1800025ef`
- `USER32!MapWindowPoints` at `0x1800025ef`
- `USER32!OffsetRect` at `0x18000266c`
- `USER32!OffsetRect` at `0x180002694`
- `USER32!OffsetRect` at `0x18000266c`
- `USER32!OffsetRect` at `0x180002694`
- `GDI32!SelectObject` at `0x180002580`
- `GDI32!SelectObject` at `0x180002580`
- `GDI32!GetTextExtentPointA` at `0x1800025a2`
- `GDI32!GetTextExtentPointA` at `0x1800025a2`

## pseudocode

```c

```
