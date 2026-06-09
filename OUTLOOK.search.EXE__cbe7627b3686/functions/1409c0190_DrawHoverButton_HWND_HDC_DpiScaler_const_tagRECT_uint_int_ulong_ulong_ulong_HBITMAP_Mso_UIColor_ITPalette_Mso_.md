# DrawHoverButton(HWND__ *,HDC__ *,DpiScaler const &,tagRECT,uint,int,ulong,ulong,ulong,HBITMAP__ *,Mso::UIColor::ITPalette<Mso::UIColor::Swatch> *)

- ea: `0x1409c0190`
- end: `0x1409c11f9`
- name: `?DrawHoverButton@@YAHPEAUHWND__@@PEAUHDC__@@AEBVDpiScaler@@UtagRECT@@IHKKKPEAUHBITMAP__@@PEAU?$ITPalette@W4Swatch@UIColor@Mso@@@UIColor@Mso@@@Z`
- size: `4201`
- prototype: `__int64 __usercall@<rax>(HWND hWnd@<rcx>, unsigned int, int, unsigned int, COLORREF color, unsigned int, __int64, __int64)`
- caller_count: `10`
- callee_count: `25`
- tags: `broker_com_uri`

## callers

- `0x140805640`
- `0x1408ed84c`
- `0x1409bfea0`
- `0x1409c1dc0`
- `0x140b9dfd0`
- `0x140bf5690`
- `0x1411a80c0`
- `0x14131bdf0`
- `0x141321d50`
- `0x14164b294`

## callees

- `0x14011e0a8`
- `0x14011fc6c`
- `0x140124ddc`
- `0x1401723e8`
- `0x140244860`
- `0x140257140`
- `0x1402d2980`
- `0x1405049f0`
- `0x1405e27b8`
- `0x1405e2c94`
- `0x1405e2d20`
- `0x1407b0828`
- `0x1409c0190`
- `0x1409c12a8`
- `0x1409c229c`
- `0x140a68600`
- `0x140a687b4`
- `0x140ae77e4`
- `0x140c43210`
- `0x140c43290`
- `0x140c5c1c0`
- `0x140cbc440`
- `0x140e80a98`
- `0x141171134`
- `0x141196e08`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1409c05de`
- `KERNEL32!LeaveCriticalSection` at `0x1409c05de`
- `GDI32!CreateSolidBrush` at `0x1409c06df`
- `GDI32!CreateSolidBrush` at `0x1409c06df`
- `GDI32!SelectObject` at `0x1409c0797`
- `GDI32!SelectObject` at `0x1409c0dc9`
- `GDI32!SelectObject` at `0x1409c0e39`
- `GDI32!SelectObject` at `0x1409c0e6d`
- `GDI32!SelectObject` at `0x1409c0e8c`
- `GDI32!SelectObject` at `0x1409c11ed`
- `GDI32!SelectObject` at `0x1409c0797`
- `GDI32!SelectObject` at `0x1409c0dc9`
- `GDI32!SelectObject` at `0x1409c0e39`
- `GDI32!SelectObject` at `0x1409c0e6d`
- `GDI32!SelectObject` at `0x1409c0e8c`
- `GDI32!SelectObject` at `0x1409c11ed`
- `GDI32!SetBkColor` at `0x1409c044d`
- `GDI32!SetBkColor` at `0x1409c04aa`
- `GDI32!SetBkColor` at `0x1409c0726`
- `GDI32!SetBkColor` at `0x1409c075d`
- `GDI32!SetBkColor` at `0x1409c044d`
- `GDI32!SetBkColor` at `0x1409c04aa`
- `GDI32!SetBkColor` at `0x1409c0726`
- `GDI32!SetBkColor` at `0x1409c075d`
- `GDI32!ExtTextOutA` at `0x1409c0475`
- `GDI32!ExtTextOutA` at `0x1409c0751`
- `GDI32!ExtTextOutA` at `0x1409c0475`
- `GDI32!ExtTextOutA` at `0x1409c0751`
- `GDI32!StretchBlt` at `0x1409c0e21`
- `GDI32!StretchBlt` at `0x1409c0e21`
- `GDI32!SetStretchBltMode` at `0x1409c0ddb`
- `GDI32!SetStretchBltMode` at `0x1409c0e2d`
- `GDI32!SetStretchBltMode` at `0x1409c0ddb`
- `GDI32!SetStretchBltMode` at `0x1409c0e2d`
- `GDI32!GetPixel` at `0x1409c0e7e`
- `GDI32!GetPixel` at `0x1409c0e7e`
- `GDI32!CreateCompatibleDC` at `0x1409c0db9`
- `GDI32!CreateCompatibleDC` at `0x1409c0e58`
- `GDI32!CreateCompatibleDC` at `0x1409c0db9`
- `GDI32!CreateCompatibleDC` at `0x1409c0e58`
- `GDI32!DeleteDC` at `0x1409c0e42`
- `GDI32!DeleteDC` at `0x1409c0e95`
- `GDI32!DeleteDC` at `0x1409c0e42`
- `GDI32!DeleteDC` at `0x1409c0e95`
- `GDI32!BitBlt` at `0x1409c0584`
- `GDI32!BitBlt` at `0x1409c0584`
- `GDI32!GetObjectA` at `0x1409c0c1d`
- `GDI32!GetObjectA` at `0x1409c0c1d`
- `GDI32!DeleteObject` at `0x1409c06fb`
- `GDI32!DeleteObject` at `0x1409c0ec7`
- `GDI32!DeleteObject` at `0x1409c06fb`
- `GDI32!DeleteObject` at `0x1409c0ec7`
- `GDI32!SetTextColor` at `0x1409c04f3`
- `GDI32!SetTextColor` at `0x1409c0537`
- `GDI32!SetTextColor` at `0x1409c11df`
- `GDI32!SetTextColor` at `0x1409c04f3`
- `GDI32!SetTextColor` at `0x1409c0537`
- `GDI32!SetTextColor` at `0x1409c11df`
- `GDI32!SetBkMode` at `0x1409c028a`
- `GDI32!SetBkMode` at `0x1409c05f7`
- `GDI32!SetBkMode` at `0x1409c1063`
- `GDI32!SetBkMode` at `0x1409c028a`
- `GDI32!SetBkMode` at `0x1409c05f7`
- `GDI32!SetBkMode` at `0x1409c1063`
- `USER32!GetWindowLongPtrA` at `0x1409c0394`
- `USER32!GetWindowLongPtrA` at `0x1409c0394`
- `USER32!OffsetRect` at `0x1409c1194`
- `USER32!OffsetRect` at `0x1409c1194`
- `USER32!InflateRect` at `0x1409c049e`
- `USER32!InflateRect` at `0x1409c0719`
- `USER32!InflateRect` at `0x1409c049e`
- `USER32!InflateRect` at `0x1409c0719`
- `USER32!CopyRect` at `0x1409c03d7`
- `USER32!CopyRect` at `0x1409c0faa`
- `USER32!CopyRect` at `0x1409c03d7`
- `USER32!CopyRect` at `0x1409c0faa`
- `USER32!FrameRect` at `0x1409c06f2`
- `USER32!FrameRect` at `0x1409c06f2`
- `USER32!SendMessageA` at `0x1409c078a`
- `USER32!SendMessageA` at `0x1409c078a`
- `MSO!__imp_MsoDrawTextW` at `0x1409c0851`
- `MSO!__imp_MsoDrawTextW` at `0x1409c116e`
- `MSO!__imp_MsoDrawTextW` at `0x1409c11d2`
- `MSO!__imp_MsoDrawTextW` at `0x1409c0851`
- `MSO!__imp_MsoDrawTextW` at `0x1409c116e`
- `MSO!__imp_MsoDrawTextW` at `0x1409c11d2`
- `mso40uiWin32Client!__imp_?RenderSmartBitmap@NetUI@@YAXPEAUHDC__@@HHHHHHE_N@Z` at `0x1409c0f49`
- `mso40uiWin32Client!__imp_?RenderSmartBitmap@NetUI@@YAXPEAUHDC__@@HHHHHHE_N@Z` at `0x1409c0f49`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1409c0616`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1409c0abf`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1409c0bb9`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1409c0f13`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1409c0616`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1409c0abf`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1409c0bb9`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1409c0f13`
- `mso40uiWin32Client!__imp_?GetSmartBitmapSize@NetUI@@YA?AUtagSIZE@@H@Z` at `0x1409c088f`
- `mso40uiWin32Client!__imp_?GetSmartBitmapSize@NetUI@@YA?AUtagSIZE@@H@Z` at `0x1409c088f`
- `mso40uiWin32Client!__imp_?MsoFCbvHighContrast@@YAHXZ` at `0x1409c03b1`
- `mso40uiWin32Client!__imp_?MsoFCbvHighContrast@@YAHXZ` at `0x1409c0ba1`
- `mso40uiWin32Client!__imp_?MsoFCbvHighContrast@@YAHXZ` at `0x1409c03b1`
- `mso40uiWin32Client!__imp_?MsoFCbvHighContrast@@YAHXZ` at `0x1409c0ba1`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x1409c03e6`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x1409c0b34`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x1409c03e6`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x1409c0b34`
- `Mso30Win32Client!__imp_?MsoLoadBitmapW@@YAPEAUHBITMAP__@@PEAUHINSTANCE__@@PEB_W@Z` at `0x1409c0be5`
- `Mso30Win32Client!__imp_?MsoLoadBitmapW@@YAPEAUHBITMAP__@@PEAUHINSTANCE__@@PEB_W@Z` at `0x1409c0be5`

## pseudocode

```c

```
