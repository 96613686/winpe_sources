# CMsoPolicyLabel::HrCreateImage(int,int,wchar_t *,int)

- ea: `0x1815c9ec0`
- end: `0x1815caa91`
- name: `?HrCreateImage@CMsoPolicyLabel@@UEAAJHHPEA_WH@Z`
- size: `3025`
- prototype: `__int64 __usercall@<rax>(CMsoPolicyLabel *__hidden this@<rcx>, int@<edx>, int@<r8d>, wchar_t *@<r9>, int)`
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18001d310`
- `0x18002c370`
- `0x1800916f4`
- `0x1800f7a9c`
- `0x1802144d8`
- `0x180371700`
- `0x180386740`
- `0x1803901bc`
- `0x180485240`
- `0x180485dd0`
- `0x180a029d0`
- `0x180a5e550`
- `0x180b35cc4`
- `0x180c92860`
- `0x1815c8e74`
- `0x1815c9a64`
- `0x1815c9ec0`
- `0x1815cad10`
- `0x1815cb784`
- `0x1815cbff4`

## import_xrefs

- `KERNEL32!MulDiv` at `0x1815ca1e6`
- `KERNEL32!MulDiv` at `0x1815ca1e6`
- `KERNEL32!WriteFile` at `0x1815ca943`
- `KERNEL32!WriteFile` at `0x1815ca967`
- `KERNEL32!WriteFile` at `0x1815ca943`
- `KERNEL32!WriteFile` at `0x1815ca967`
- `KERNEL32!CloseHandle` at `0x1815ca97a`
- `KERNEL32!CloseHandle` at `0x1815ca97a`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x1815ca2ee`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x1815ca50c`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x1815ca65b`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x1815ca68b`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x1815ca2ee`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x1815ca50c`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x1815ca65b`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x1815ca68b`
- `Mso98Win32Client!__imp_?MsoTextOutW@@YAHPEAUHDC__@@HHPEB_WH@Z` at `0x1815ca58f`
- `Mso98Win32Client!__imp_?MsoTextOutW@@YAHPEAUHDC__@@HHPEB_WH@Z` at `0x1815ca58f`
- `mso40uiWin32Client!__imp_MsoDialogFontNameLid` at `0x1815ca14e`
- `mso40uiWin32Client!__imp_MsoDialogFontNameLid` at `0x1815ca14e`
- `mso40uiWin32Client!__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z` at `0x1815ca0b8`
- `mso40uiWin32Client!__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z` at `0x1815ca3af`
- `mso40uiWin32Client!__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z` at `0x1815ca0b8`
- `mso40uiWin32Client!__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z` at `0x1815ca3af`
- `Mso30Win32Client!__imp_MsoChsFromLid` at `0x1815ca1a1`
- `Mso30Win32Client!__imp_MsoChsFromLid` at `0x1815ca1a1`
- `Mso20Win32Client!__imp_?MsoEmptyPx@@YAXPEAX@Z` at `0x1815caa1f`
- `Mso20Win32Client!__imp_?MsoEmptyPx@@YAXPEAX@Z` at `0x1815caa1f`
- `Mso20Win32Client!__imp_?TryReallocateRawBytes@Memory@Mso@@YA_NAEAPEAX_K@Z` at `0x1815ca6c5`
- `Mso20Win32Client!__imp_?TryReallocateRawBytes@Memory@Mso@@YA_NAEAPEAX_K@Z` at `0x1815ca6c5`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1815ca81a`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1815ca840`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1815ca81a`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1815ca840`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1815ca768`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1815ca98c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1815ca9a0`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1815caa28`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1815ca768`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1815ca98c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1815ca9a0`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1815caa28`
- `Mso20Win32Client!__imp_?SendErrorTag@Diagnostics@Mso@@YAXKW4Category@Logging@2@@Z` at `0x1815c9fb1`
- `Mso20Win32Client!__imp_?SendErrorTag@Diagnostics@Mso@@YAXKW4Category@Logging@2@@Z` at `0x1815c9fb1`
- `USER32!GetDC` at `0x1815ca06c`
- `USER32!GetDC` at `0x1815ca06c`
- `USER32!ReleaseDC` at `0x1815ca9cb`
- `USER32!ReleaseDC` at `0x1815ca9cb`
- `GDI32!PatBlt` at `0x1815ca4ab`
- `GDI32!PatBlt` at `0x1815ca4ab`
- `GDI32!SetBkMode` at `0x1815ca4b7`
- `GDI32!SetBkMode` at `0x1815ca4b7`
- `GDI32!Polyline` at `0x1815ca73f`
- `GDI32!Polyline` at `0x1815ca73f`
- `GDI32!SetDCPenColor` at `0x1815ca5f4`
- `GDI32!SetDCPenColor` at `0x1815ca5f4`
- `GDI32!SetTextAlign` at `0x1815ca3f4`
- `GDI32!SetTextAlign` at `0x1815ca3f4`
- `GDI32!CreateCompatibleDC` at `0x1815ca08d`
- `GDI32!CreateCompatibleDC` at `0x1815ca08d`
- `GDI32!SelectObject` at `0x1815ca0d9`
- `GDI32!SelectObject` at `0x1815ca393`
- `GDI32!SelectObject` at `0x1815ca3d0`
- `GDI32!SelectObject` at `0x1815ca3e9`
- `GDI32!SelectObject` at `0x1815ca40b`
- `GDI32!SelectObject` at `0x1815ca5e6`
- `GDI32!SelectObject` at `0x1815ca7c5`
- `GDI32!SelectObject` at `0x1815ca0d9`
- `GDI32!SelectObject` at `0x1815ca393`
- `GDI32!SelectObject` at `0x1815ca3d0`
- `GDI32!SelectObject` at `0x1815ca3e9`
- `GDI32!SelectObject` at `0x1815ca40b`
- `GDI32!SelectObject` at `0x1815ca5e6`
- `GDI32!SelectObject` at `0x1815ca7c5`
- `GDI32!DeleteDC` at `0x1815ca9b7`
- `GDI32!DeleteDC` at `0x1815ca9b7`
- `GDI32!DeleteObject` at `0x1815ca39d`
- `GDI32!DeleteObject` at `0x1815ca7b3`
- `GDI32!DeleteObject` at `0x1815ca9dd`
- `GDI32!DeleteObject` at `0x1815ca39d`
- `GDI32!DeleteObject` at `0x1815ca7b3`
- `GDI32!DeleteObject` at `0x1815ca9dd`
- `GDI32!SetMapMode` at `0x1815ca0a7`
- `GDI32!SetMapMode` at `0x1815ca0a7`
- `GDI32!GetStockObject` at `0x1815ca3ff`
- `GDI32!GetStockObject` at `0x1815ca5da`
- `GDI32!GetStockObject` at `0x1815ca3ff`
- `GDI32!GetStockObject` at `0x1815ca5da`
- `GDI32!CreateFontW` at `0x1815ca22a`
- `GDI32!CreateFontW` at `0x1815ca22a`
- `GDI32!GetDIBits` at `0x1815ca8b5`
- `GDI32!GetDIBits` at `0x1815ca8b5`

## pseudocode

```c

```
