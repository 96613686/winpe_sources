# FrameExtTextOutBackgroundW(HDC__ *,int,int,uint,tagRECT *,wchar_t const *,uint,int const *,CCTEXTURE *,tagRECT *,int,int,int)

- ea: `0x1409caa60`
- end: `0x1409cafda`
- name: `?FrameExtTextOutBackgroundW@@YAHPEAUHDC__@@HHIPEAUtagRECT@@PEB_WIPEBHPEAUCCTEXTURE@@1HHH@Z`
- size: `1402`
- prototype: `__int64 __usercall@<rax>(HDC@<rcx>, int@<edx>, int@<r8d>, unsigned int@<r9d>, struct tagRECT *, const wchar_t *, unsigned int, const int *, struct CCTEXTURE *, struct tagRECT *, int, int, int)`
- caller_count: `10`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1409c94f8`
- `0x140a4b370`
- `0x140a4b7bc`
- `0x140a4b9f0`
- `0x140a4bd60`
- `0x140ac4928`
- `0x140d1a624`
- `0x141a72ab0`
- `0x141a73890`
- `0x141a86fa0`

## callees

- `0x140122864`
- `0x140257218`
- `0x1405049f0`
- `0x1409caa60`
- `0x140cd0c7c`

## import_xrefs

- `GDI32!SelectObject` at `0x1409cac3f`
- `GDI32!SelectObject` at `0x1409cac5c`
- `GDI32!SelectObject` at `0x1409cadab`
- `GDI32!SelectObject` at `0x1409cac3f`
- `GDI32!SelectObject` at `0x1409cac5c`
- `GDI32!SelectObject` at `0x1409cadab`
- `GDI32!SetBkColor` at `0x1409cacfc`
- `GDI32!SetBkColor` at `0x1409cae1f`
- `GDI32!SetBkColor` at `0x1409caf12`
- `GDI32!SetBkColor` at `0x1409cafce`
- `GDI32!SetBkColor` at `0x1409cacfc`
- `GDI32!SetBkColor` at `0x1409cae1f`
- `GDI32!SetBkColor` at `0x1409caf12`
- `GDI32!SetBkColor` at `0x1409cafce`
- `GDI32!GetTextAlign` at `0x1409cab84`
- `GDI32!GetTextAlign` at `0x1409cac65`
- `GDI32!GetTextAlign` at `0x1409cae80`
- `GDI32!GetTextAlign` at `0x1409cab84`
- `GDI32!GetTextAlign` at `0x1409cac65`
- `GDI32!GetTextAlign` at `0x1409cae80`
- `GDI32!GetBkColor` at `0x1409caf8a`
- `GDI32!GetBkColor` at `0x1409caf8a`
- `GDI32!CreateCompatibleBitmap` at `0x1409cac22`
- `GDI32!CreateCompatibleBitmap` at `0x1409cac22`
- `GDI32!CreateCompatibleDC` at `0x1409cac0d`
- `GDI32!CreateCompatibleDC` at `0x1409cac0d`
- `GDI32!DeleteDC` at `0x1409cac2f`
- `GDI32!DeleteDC` at `0x1409cadbb`
- `GDI32!DeleteDC` at `0x1409cac2f`
- `GDI32!DeleteDC` at `0x1409cadbb`
- `GDI32!BitBlt` at `0x1409cad9f`
- `GDI32!BitBlt` at `0x1409cad9f`
- `GDI32!GetCurrentObject` at `0x1409cac51`
- `GDI32!GetCurrentObject` at `0x1409cac51`
- `GDI32!GetTextColor` at `0x1409cacbd`
- `GDI32!GetTextColor` at `0x1409cacbd`
- `GDI32!DeleteObject` at `0x1409cadb3`
- `GDI32!DeleteObject` at `0x1409cadb3`
- `GDI32!SetTextColor` at `0x1409cacb2`
- `GDI32!SetTextColor` at `0x1409cacc7`
- `GDI32!SetTextColor` at `0x1409cae5a`
- `GDI32!SetTextColor` at `0x1409caf1e`
- `GDI32!SetTextColor` at `0x1409caf4d`
- `GDI32!SetTextColor` at `0x1409cacb2`
- `GDI32!SetTextColor` at `0x1409cacc7`
- `GDI32!SetTextColor` at `0x1409cae5a`
- `GDI32!SetTextColor` at `0x1409caf1e`
- `GDI32!SetTextColor` at `0x1409caf4d`
- `GDI32!SetTextAlign` at `0x1409cab95`
- `GDI32!SetTextAlign` at `0x1409cabd0`
- `GDI32!SetTextAlign` at `0x1409cac6f`
- `GDI32!SetTextAlign` at `0x1409cae91`
- `GDI32!SetTextAlign` at `0x1409caed0`
- `GDI32!SetTextAlign` at `0x1409cab95`
- `GDI32!SetTextAlign` at `0x1409cabd0`
- `GDI32!SetTextAlign` at `0x1409cac6f`
- `GDI32!SetTextAlign` at `0x1409cae91`
- `GDI32!SetTextAlign` at `0x1409caed0`
- `GDI32!SetBkMode` at `0x1409cad3c`
- `GDI32!SetBkMode` at `0x1409cad3c`
- `USER32!OffsetRect` at `0x1409cad1f`
- `USER32!OffsetRect` at `0x1409cad1f`
- `USER32!GetSysColor` at `0x1409caca0`
- `USER32!GetSysColor` at `0x1409cacea`
- `USER32!GetSysColor` at `0x1409cae0b`
- `USER32!GetSysColor` at `0x1409cae47`
- `USER32!GetSysColor` at `0x1409caf39`
- `USER32!GetSysColor` at `0x1409caf77`
- `USER32!GetSysColor` at `0x1409cafbb`
- `USER32!GetSysColor` at `0x1409caca0`
- `USER32!GetSysColor` at `0x1409cacea`
- `USER32!GetSysColor` at `0x1409cae0b`
- `USER32!GetSysColor` at `0x1409cae47`
- `USER32!GetSysColor` at `0x1409caf39`
- `USER32!GetSysColor` at `0x1409caf77`
- `USER32!GetSysColor` at `0x1409cafbb`
- `USER32!CopyRect` at `0x1409cad0a`
- `USER32!CopyRect` at `0x1409cad0a`
- `Mso98Win32Client!__imp_MsoExtTextOutWEx` at `0x1409cab44`
- `Mso98Win32Client!__imp_MsoExtTextOutWEx` at `0x1409cab44`
- `Mso98Win32Client!__imp_MsoExtTextOutW` at `0x1409cabc2`
- `Mso98Win32Client!__imp_MsoExtTextOutW` at `0x1409cad6e`
- `Mso98Win32Client!__imp_MsoExtTextOutW` at `0x1409caec2`
- `Mso98Win32Client!__imp_MsoExtTextOutW` at `0x1409caf03`
- `Mso98Win32Client!__imp_MsoExtTextOutW` at `0x1409cabc2`
- `Mso98Win32Client!__imp_MsoExtTextOutW` at `0x1409cad6e`
- `Mso98Win32Client!__imp_MsoExtTextOutW` at `0x1409caec2`
- `Mso98Win32Client!__imp_MsoExtTextOutW` at `0x1409caf03`

## pseudocode

```c

```
