# CMsoPolicyLabel::HrCreateImage(int,int,wchar_t *,int)

- ea: `0x1815ca460`
- end: `0x1815cb031`
- name: `?HrCreateImage@CMsoPolicyLabel@@UEAAJHHPEA_WH@Z`
- size: `3025`
- prototype: `__int64 __usercall@<rax>(CMsoPolicyLabel *__hidden this@<rcx>, int@<edx>, int@<r8d>, wchar_t *@<r9>, int)`
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18001d310`
- `0x18002c370`
- `0x1800968d0`
- `0x1800f5a08`
- `0x18016eca0`
- `0x180214f58`
- `0x180373590`
- `0x180391d00`
- `0x1803d16ac`
- `0x1804860a0`
- `0x180a07af0`
- `0x180a64170`
- `0x180b3b394`
- `0x180c93f40`
- `0x1815c9414`
- `0x1815ca004`
- `0x1815ca460`
- `0x1815cb2b0`
- `0x1815cbd24`
- `0x1815cc594`

## import_xrefs

- `KERNEL32!MulDiv` at `0x1815ca786`
- `KERNEL32!MulDiv` at `0x1815ca786`
- `KERNEL32!WriteFile` at `0x1815caee3`
- `KERNEL32!WriteFile` at `0x1815caf07`
- `KERNEL32!WriteFile` at `0x1815caee3`
- `KERNEL32!WriteFile` at `0x1815caf07`
- `KERNEL32!CloseHandle` at `0x1815caf1a`
- `KERNEL32!CloseHandle` at `0x1815caf1a`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x1815ca88e`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x1815caaac`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x1815cabfb`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x1815cac2b`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x1815ca88e`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x1815caaac`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x1815cabfb`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x1815cac2b`
- `Mso98Win32Client!__imp_?MsoTextOutW@@YAHPEAUHDC__@@HHPEB_WH@Z` at `0x1815cab2f`
- `Mso98Win32Client!__imp_?MsoTextOutW@@YAHPEAUHDC__@@HHPEB_WH@Z` at `0x1815cab2f`
- `mso40uiWin32Client!__imp_MsoDialogFontNameLid` at `0x1815ca6ee`
- `mso40uiWin32Client!__imp_MsoDialogFontNameLid` at `0x1815ca6ee`
- `mso40uiWin32Client!__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z` at `0x1815ca658`
- `mso40uiWin32Client!__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z` at `0x1815ca94f`
- `mso40uiWin32Client!__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z` at `0x1815ca658`
- `mso40uiWin32Client!__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z` at `0x1815ca94f`
- `Mso30Win32Client!__imp_MsoChsFromLid` at `0x1815ca741`
- `Mso30Win32Client!__imp_MsoChsFromLid` at `0x1815ca741`
- `Mso20Win32Client!__imp_?MsoEmptyPx@@YAXPEAX@Z` at `0x1815cafbf`
- `Mso20Win32Client!__imp_?MsoEmptyPx@@YAXPEAX@Z` at `0x1815cafbf`
- `Mso20Win32Client!__imp_?TryReallocateRawBytes@Memory@Mso@@YA_NAEAPEAX_K@Z` at `0x1815cac65`
- `Mso20Win32Client!__imp_?TryReallocateRawBytes@Memory@Mso@@YA_NAEAPEAX_K@Z` at `0x1815cac65`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1815cadba`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1815cade0`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1815cadba`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1815cade0`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1815cad08`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1815caf2c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1815caf40`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1815cafc8`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1815cad08`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1815caf2c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1815caf40`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1815cafc8`
- `Mso20Win32Client!__imp_?SendErrorTag@Diagnostics@Mso@@YAXKW4Category@Logging@2@@Z` at `0x1815ca551`
- `Mso20Win32Client!__imp_?SendErrorTag@Diagnostics@Mso@@YAXKW4Category@Logging@2@@Z` at `0x1815ca551`
- `USER32!GetDC` at `0x1815ca60c`
- `USER32!GetDC` at `0x1815ca60c`
- `USER32!ReleaseDC` at `0x1815caf6b`
- `USER32!ReleaseDC` at `0x1815caf6b`
- `GDI32!PatBlt` at `0x1815caa4b`
- `GDI32!PatBlt` at `0x1815caa4b`
- `GDI32!SetBkMode` at `0x1815caa57`
- `GDI32!SetBkMode` at `0x1815caa57`
- `GDI32!Polyline` at `0x1815cacdf`
- `GDI32!Polyline` at `0x1815cacdf`
- `GDI32!SetDCPenColor` at `0x1815cab94`
- `GDI32!SetDCPenColor` at `0x1815cab94`
- `GDI32!SetTextAlign` at `0x1815ca994`
- `GDI32!SetTextAlign` at `0x1815ca994`
- `GDI32!CreateCompatibleDC` at `0x1815ca62d`
- `GDI32!CreateCompatibleDC` at `0x1815ca62d`
- `GDI32!SelectObject` at `0x1815ca679`
- `GDI32!SelectObject` at `0x1815ca933`
- `GDI32!SelectObject` at `0x1815ca970`
- `GDI32!SelectObject` at `0x1815ca989`
- `GDI32!SelectObject` at `0x1815ca9ab`
- `GDI32!SelectObject` at `0x1815cab86`
- `GDI32!SelectObject` at `0x1815cad65`
- `GDI32!SelectObject` at `0x1815ca679`
- `GDI32!SelectObject` at `0x1815ca933`
- `GDI32!SelectObject` at `0x1815ca970`
- `GDI32!SelectObject` at `0x1815ca989`
- `GDI32!SelectObject` at `0x1815ca9ab`
- `GDI32!SelectObject` at `0x1815cab86`
- `GDI32!SelectObject` at `0x1815cad65`
- `GDI32!DeleteDC` at `0x1815caf57`
- `GDI32!DeleteDC` at `0x1815caf57`
- `GDI32!DeleteObject` at `0x1815ca93d`
- `GDI32!DeleteObject` at `0x1815cad53`
- `GDI32!DeleteObject` at `0x1815caf7d`
- `GDI32!DeleteObject` at `0x1815ca93d`
- `GDI32!DeleteObject` at `0x1815cad53`
- `GDI32!DeleteObject` at `0x1815caf7d`
- `GDI32!SetMapMode` at `0x1815ca647`
- `GDI32!SetMapMode` at `0x1815ca647`
- `GDI32!GetStockObject` at `0x1815ca99f`
- `GDI32!GetStockObject` at `0x1815cab7a`
- `GDI32!GetStockObject` at `0x1815ca99f`
- `GDI32!GetStockObject` at `0x1815cab7a`
- `GDI32!CreateFontW` at `0x1815ca7ca`
- `GDI32!CreateFontW` at `0x1815ca7ca`
- `GDI32!GetDIBits` at `0x1815cae55`
- `GDI32!GetDIBits` at `0x1815cae55`

## pseudocode

```c

```
