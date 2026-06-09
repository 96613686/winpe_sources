# ScreenShooter::_Grab(Geometry::CRect const *,HBITMAP__ * *)

- ea: `0x180160250`
- end: `0x1801603d7`
- name: `?_Grab@ScreenShooter@@CAJPEBUCRect@Geometry@@PEAPEAUHBITMAP__@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(const struct Geometry::CRect *, HBITMAP *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180160f00`

## callees

- `0x18002fc18`
- `0x1800f82ec`
- `0x180160250`

## import_xrefs

- `USER32!GetDC` at `0x180160273`
- `USER32!GetDC` at `0x180160273`
- `USER32!ReleaseDC` at `0x18016039c`
- `USER32!ReleaseDC` at `0x18016039c`
- `GDI32!CreateCompatibleBitmap` at `0x1801602d4`
- `GDI32!CreateCompatibleBitmap` at `0x1801602d4`
- `GDI32!CreateCompatibleDC` at `0x180160299`
- `GDI32!CreateCompatibleDC` at `0x180160299`
- `GDI32!SelectObject` at `0x180160305`
- `GDI32!SelectObject` at `0x18016037e`
- `GDI32!SelectObject` at `0x180160305`
- `GDI32!SelectObject` at `0x18016037e`
- `GDI32!BitBlt` at `0x180160345`
- `GDI32!BitBlt` at `0x180160345`
- `GDI32!DeleteDC` at `0x1801603b0`
- `GDI32!DeleteDC` at `0x1801603b0`

## pseudocode

```c

```
