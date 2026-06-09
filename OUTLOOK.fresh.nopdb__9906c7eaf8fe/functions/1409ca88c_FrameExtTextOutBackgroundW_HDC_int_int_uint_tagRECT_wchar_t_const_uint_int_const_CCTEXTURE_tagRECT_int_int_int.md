# FrameExtTextOutBackgroundW(HDC__ *,int,int,uint,tagRECT *,wchar_t const *,uint,int const *,CCTEXTURE *,tagRECT *,int,int,int)

- ea: `0x1409ca88c`
- end: `0x1409cae06`
- name: `?FrameExtTextOutBackgroundW@@YAHPEAUHDC__@@HHIPEAUtagRECT@@PEB_WIPEBHPEAUCCTEXTURE@@1HHH@Z`
- size: `1402`
- prototype: `__int64 __usercall@<rax>(HDC@<rcx>, int@<edx>, int@<r8d>, unsigned int@<r9d>, struct tagRECT *, const wchar_t *, unsigned int, const int *, struct CCTEXTURE *, struct tagRECT *, int, int, int)`
- caller_count: `10`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1409c9324`
- `0x140a4b240`
- `0x140a4b68c`
- `0x140a4b8c0`
- `0x140a4bc30`
- `0x140ac4808`
- `0x140d1a574`
- `0x141a729f0`
- `0x141a737d0`
- `0x141a86ee0`

## callees

- `0x140122824`
- `0x140256a08`
- `0x140503f00`
- `0x1409ca88c`
- `0x140cd0bcc`

## import_xrefs

- `GDI32!SelectObject` at `0x1409caa6b`
- `GDI32!SelectObject` at `0x1409caa88`
- `GDI32!SelectObject` at `0x1409cabd7`
- `GDI32!SelectObject` at `0x1409caa6b`
- `GDI32!SelectObject` at `0x1409caa88`
- `GDI32!SelectObject` at `0x1409cabd7`
- `GDI32!SetBkColor` at `0x1409cab28`
- `GDI32!SetBkColor` at `0x1409cac4b`
- `GDI32!SetBkColor` at `0x1409cad3e`
- `GDI32!SetBkColor` at `0x1409cadfa`
- `GDI32!SetBkColor` at `0x1409cab28`
- `GDI32!SetBkColor` at `0x1409cac4b`
- `GDI32!SetBkColor` at `0x1409cad3e`
- `GDI32!SetBkColor` at `0x1409cadfa`
- `GDI32!GetTextAlign` at `0x1409ca9b0`
- `GDI32!GetTextAlign` at `0x1409caa91`
- `GDI32!GetTextAlign` at `0x1409cacac`
- `GDI32!GetTextAlign` at `0x1409ca9b0`
- `GDI32!GetTextAlign` at `0x1409caa91`
- `GDI32!GetTextAlign` at `0x1409cacac`
- `GDI32!GetBkColor` at `0x1409cadb6`
- `GDI32!GetBkColor` at `0x1409cadb6`
- `GDI32!CreateCompatibleBitmap` at `0x1409caa4e`
- `GDI32!CreateCompatibleBitmap` at `0x1409caa4e`
- `GDI32!CreateCompatibleDC` at `0x1409caa39`
- `GDI32!CreateCompatibleDC` at `0x1409caa39`
- `GDI32!DeleteDC` at `0x1409caa5b`
- `GDI32!DeleteDC` at `0x1409cabe7`
- `GDI32!DeleteDC` at `0x1409caa5b`
- `GDI32!DeleteDC` at `0x1409cabe7`
- `GDI32!BitBlt` at `0x1409cabcb`
- `GDI32!BitBlt` at `0x1409cabcb`
- `GDI32!GetCurrentObject` at `0x1409caa7d`
- `GDI32!GetCurrentObject` at `0x1409caa7d`
- `GDI32!GetTextColor` at `0x1409caae9`
- `GDI32!GetTextColor` at `0x1409caae9`
- `GDI32!DeleteObject` at `0x1409cabdf`
- `GDI32!DeleteObject` at `0x1409cabdf`
- `GDI32!SetTextColor` at `0x1409caade`
- `GDI32!SetTextColor` at `0x1409caaf3`
- `GDI32!SetTextColor` at `0x1409cac86`
- `GDI32!SetTextColor` at `0x1409cad4a`
- `GDI32!SetTextColor` at `0x1409cad79`
- `GDI32!SetTextColor` at `0x1409caade`
- `GDI32!SetTextColor` at `0x1409caaf3`
- `GDI32!SetTextColor` at `0x1409cac86`
- `GDI32!SetTextColor` at `0x1409cad4a`
- `GDI32!SetTextColor` at `0x1409cad79`
- `GDI32!SetTextAlign` at `0x1409ca9c1`
- `GDI32!SetTextAlign` at `0x1409ca9fc`
- `GDI32!SetTextAlign` at `0x1409caa9b`
- `GDI32!SetTextAlign` at `0x1409cacbd`
- `GDI32!SetTextAlign` at `0x1409cacfc`
- `GDI32!SetTextAlign` at `0x1409ca9c1`
- `GDI32!SetTextAlign` at `0x1409ca9fc`
- `GDI32!SetTextAlign` at `0x1409caa9b`
- `GDI32!SetTextAlign` at `0x1409cacbd`
- `GDI32!SetTextAlign` at `0x1409cacfc`
- `GDI32!SetBkMode` at `0x1409cab68`
- `GDI32!SetBkMode` at `0x1409cab68`
- `USER32!OffsetRect` at `0x1409cab4b`
- `USER32!OffsetRect` at `0x1409cab4b`
- `USER32!GetSysColor` at `0x1409caacc`
- `USER32!GetSysColor` at `0x1409cab16`
- `USER32!GetSysColor` at `0x1409cac37`
- `USER32!GetSysColor` at `0x1409cac73`
- `USER32!GetSysColor` at `0x1409cad65`
- `USER32!GetSysColor` at `0x1409cada3`
- `USER32!GetSysColor` at `0x1409cade7`
- `USER32!GetSysColor` at `0x1409caacc`
- `USER32!GetSysColor` at `0x1409cab16`
- `USER32!GetSysColor` at `0x1409cac37`
- `USER32!GetSysColor` at `0x1409cac73`
- `USER32!GetSysColor` at `0x1409cad65`
- `USER32!GetSysColor` at `0x1409cada3`
- `USER32!GetSysColor` at `0x1409cade7`
- `USER32!CopyRect` at `0x1409cab36`
- `USER32!CopyRect` at `0x1409cab36`
- `Mso98Win32Client!__imp_MsoExtTextOutWEx` at `0x1409ca970`
- `Mso98Win32Client!__imp_MsoExtTextOutWEx` at `0x1409ca970`
- `Mso98Win32Client!__imp_MsoExtTextOutW` at `0x1409ca9ee`
- `Mso98Win32Client!__imp_MsoExtTextOutW` at `0x1409cab9a`
- `Mso98Win32Client!__imp_MsoExtTextOutW` at `0x1409cacee`
- `Mso98Win32Client!__imp_MsoExtTextOutW` at `0x1409cad2f`
- `Mso98Win32Client!__imp_MsoExtTextOutW` at `0x1409ca9ee`
- `Mso98Win32Client!__imp_MsoExtTextOutW` at `0x1409cab9a`
- `Mso98Win32Client!__imp_MsoExtTextOutW` at `0x1409cacee`
- `Mso98Win32Client!__imp_MsoExtTextOutW` at `0x1409cad2f`

## pseudocode

```c

```
