# DrawHoverButton(HWND__ *,HDC__ *,DpiScaler const &,tagRECT,uint,int,ulong,ulong,ulong,HBITMAP__ *,Mso::UIColor::ITPalette<Mso::UIColor::Swatch> *)

- ea: `0x1409c0040`
- end: `0x1409c10a9`
- name: `?DrawHoverButton@@YAHPEAUHWND__@@PEAUHDC__@@AEBVDpiScaler@@UtagRECT@@IHKKKPEAUHBITMAP__@@PEAU?$ITPalette@W4Swatch@UIColor@Mso@@@UIColor@Mso@@@Z`
- size: `4201`
- prototype: `__int64 __usercall@<rax>(HWND hWnd@<rcx>, unsigned int, int, unsigned int, COLORREF color, unsigned int, __int64, __int64)`
- caller_count: `10`
- callee_count: `25`
- tags: `broker_com_uri`

## callers

- `0x1408056a0`
- `0x1408ed85c`
- `0x1409bfd50`
- `0x1409c1c70`
- `0x140b9df10`
- `0x140bf55d0`
- `0x1411a8000`
- `0x14131bd30`
- `0x141321c90`
- `0x14164b1d4`

## callees

- `0x14011e018`
- `0x14011fbdc`
- `0x140124d9c`
- `0x1401723a8`
- `0x140244080`
- `0x140256930`
- `0x1402d2100`
- `0x140503f00`
- `0x1405e5950`
- `0x1405e6d50`
- `0x1405e6dd0`
- `0x1407b5848`
- `0x1409c0040`
- `0x1409c1158`
- `0x1409c214c`
- `0x140a684d0`
- `0x140a68684`
- `0x140ae76c4`
- `0x140c43160`
- `0x140c431e0`
- `0x140c5c110`
- `0x140cbc390`
- `0x140e809e8`
- `0x141171074`
- `0x141196d48`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1409c048e`
- `KERNEL32!LeaveCriticalSection` at `0x1409c048e`
- `GDI32!CreateSolidBrush` at `0x1409c058f`
- `GDI32!CreateSolidBrush` at `0x1409c058f`
- `GDI32!SelectObject` at `0x1409c0647`
- `GDI32!SelectObject` at `0x1409c0c79`
- `GDI32!SelectObject` at `0x1409c0ce9`
- `GDI32!SelectObject` at `0x1409c0d1d`
- `GDI32!SelectObject` at `0x1409c0d3c`
- `GDI32!SelectObject` at `0x1409c109d`
- `GDI32!SelectObject` at `0x1409c0647`
- `GDI32!SelectObject` at `0x1409c0c79`
- `GDI32!SelectObject` at `0x1409c0ce9`
- `GDI32!SelectObject` at `0x1409c0d1d`
- `GDI32!SelectObject` at `0x1409c0d3c`
- `GDI32!SelectObject` at `0x1409c109d`
- `GDI32!SetBkColor` at `0x1409c02fd`
- `GDI32!SetBkColor` at `0x1409c035a`
- `GDI32!SetBkColor` at `0x1409c05d6`
- `GDI32!SetBkColor` at `0x1409c060d`
- `GDI32!SetBkColor` at `0x1409c02fd`
- `GDI32!SetBkColor` at `0x1409c035a`
- `GDI32!SetBkColor` at `0x1409c05d6`
- `GDI32!SetBkColor` at `0x1409c060d`
- `GDI32!ExtTextOutA` at `0x1409c0325`
- `GDI32!ExtTextOutA` at `0x1409c0601`
- `GDI32!ExtTextOutA` at `0x1409c0325`
- `GDI32!ExtTextOutA` at `0x1409c0601`
- `GDI32!StretchBlt` at `0x1409c0cd1`
- `GDI32!StretchBlt` at `0x1409c0cd1`
- `GDI32!SetStretchBltMode` at `0x1409c0c8b`
- `GDI32!SetStretchBltMode` at `0x1409c0cdd`
- `GDI32!SetStretchBltMode` at `0x1409c0c8b`
- `GDI32!SetStretchBltMode` at `0x1409c0cdd`
- `GDI32!GetPixel` at `0x1409c0d2e`
- `GDI32!GetPixel` at `0x1409c0d2e`
- `GDI32!CreateCompatibleDC` at `0x1409c0c69`
- `GDI32!CreateCompatibleDC` at `0x1409c0d08`
- `GDI32!CreateCompatibleDC` at `0x1409c0c69`
- `GDI32!CreateCompatibleDC` at `0x1409c0d08`
- `GDI32!DeleteDC` at `0x1409c0cf2`
- `GDI32!DeleteDC` at `0x1409c0d45`
- `GDI32!DeleteDC` at `0x1409c0cf2`
- `GDI32!DeleteDC` at `0x1409c0d45`
- `GDI32!BitBlt` at `0x1409c0434`
- `GDI32!BitBlt` at `0x1409c0434`
- `GDI32!GetObjectA` at `0x1409c0acd`
- `GDI32!GetObjectA` at `0x1409c0acd`
- `GDI32!DeleteObject` at `0x1409c05ab`
- `GDI32!DeleteObject` at `0x1409c0d77`
- `GDI32!DeleteObject` at `0x1409c05ab`
- `GDI32!DeleteObject` at `0x1409c0d77`
- `GDI32!SetTextColor` at `0x1409c03a3`
- `GDI32!SetTextColor` at `0x1409c03e7`
- `GDI32!SetTextColor` at `0x1409c108f`
- `GDI32!SetTextColor` at `0x1409c03a3`
- `GDI32!SetTextColor` at `0x1409c03e7`
- `GDI32!SetTextColor` at `0x1409c108f`
- `GDI32!SetBkMode` at `0x1409c013a`
- `GDI32!SetBkMode` at `0x1409c04a7`
- `GDI32!SetBkMode` at `0x1409c0f13`
- `GDI32!SetBkMode` at `0x1409c013a`
- `GDI32!SetBkMode` at `0x1409c04a7`
- `GDI32!SetBkMode` at `0x1409c0f13`
- `USER32!GetWindowLongPtrA` at `0x1409c0244`
- `USER32!GetWindowLongPtrA` at `0x1409c0244`
- `USER32!OffsetRect` at `0x1409c1044`
- `USER32!OffsetRect` at `0x1409c1044`
- `USER32!InflateRect` at `0x1409c034e`
- `USER32!InflateRect` at `0x1409c05c9`
- `USER32!InflateRect` at `0x1409c034e`
- `USER32!InflateRect` at `0x1409c05c9`
- `USER32!CopyRect` at `0x1409c0287`
- `USER32!CopyRect` at `0x1409c0e5a`
- `USER32!CopyRect` at `0x1409c0287`
- `USER32!CopyRect` at `0x1409c0e5a`
- `USER32!FrameRect` at `0x1409c05a2`
- `USER32!FrameRect` at `0x1409c05a2`
- `USER32!SendMessageA` at `0x1409c063a`
- `USER32!SendMessageA` at `0x1409c063a`
- `MSO!__imp_MsoDrawTextW` at `0x1409c0701`
- `MSO!__imp_MsoDrawTextW` at `0x1409c101e`
- `MSO!__imp_MsoDrawTextW` at `0x1409c1082`
- `MSO!__imp_MsoDrawTextW` at `0x1409c0701`
- `MSO!__imp_MsoDrawTextW` at `0x1409c101e`
- `MSO!__imp_MsoDrawTextW` at `0x1409c1082`
- `mso40uiWin32Client!__imp_?RenderSmartBitmap@NetUI@@YAXPEAUHDC__@@HHHHHHE_N@Z` at `0x1409c0df9`
- `mso40uiWin32Client!__imp_?RenderSmartBitmap@NetUI@@YAXPEAUHDC__@@HHHHHHE_N@Z` at `0x1409c0df9`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1409c04c6`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1409c096f`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1409c0a69`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1409c0dc3`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1409c04c6`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1409c096f`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1409c0a69`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1409c0dc3`
- `mso40uiWin32Client!__imp_?GetSmartBitmapSize@NetUI@@YA?AUtagSIZE@@H@Z` at `0x1409c073f`
- `mso40uiWin32Client!__imp_?GetSmartBitmapSize@NetUI@@YA?AUtagSIZE@@H@Z` at `0x1409c073f`
- `mso40uiWin32Client!__imp_?MsoFCbvHighContrast@@YAHXZ` at `0x1409c0261`
- `mso40uiWin32Client!__imp_?MsoFCbvHighContrast@@YAHXZ` at `0x1409c0a51`
- `mso40uiWin32Client!__imp_?MsoFCbvHighContrast@@YAHXZ` at `0x1409c0261`
- `mso40uiWin32Client!__imp_?MsoFCbvHighContrast@@YAHXZ` at `0x1409c0a51`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x1409c0296`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x1409c09e4`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x1409c0296`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x1409c09e4`
- `Mso30Win32Client!__imp_?MsoLoadBitmapW@@YAPEAUHBITMAP__@@PEAUHINSTANCE__@@PEB_W@Z` at `0x1409c0a95`
- `Mso30Win32Client!__imp_?MsoLoadBitmapW@@YAPEAUHBITMAP__@@PEAUHINSTANCE__@@PEB_W@Z` at `0x1409c0a95`

## pseudocode

```c

```
