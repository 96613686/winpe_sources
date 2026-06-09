# ProtoBlip::FDrawToDib(tagBITMAPINFO *,void *,MSOBDRAWPARAM const *,MSOPLATE,MSOABORT *)

- ea: `0x180855c20`
- end: `0x18085653f`
- name: `?FDrawToDib@ProtoBlip@@UEBAHPEAUtagBITMAPINFO@@PEAXPEBUMSOBDRAWPARAM@@W4MSOPLATE@@PEAUMSOABORT@@@Z`
- size: `2335`
- prototype: `int __high(struct tagBITMAPINFO *, void *, const struct MSOBDRAWPARAM *, enum MSOPLATE, struct MSOABORT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x181250270`

## callees

- `0x18001d310`
- `0x18014f180`
- `0x180242ec0`
- `0x180243ba0`
- `0x1802e3980`
- `0x180420880`
- `0x180485240`
- `0x180485dd0`
- `0x180855c20`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180855e8b`
- `KERNEL32!GetLastError` at `0x1808561cf`
- `KERNEL32!GetLastError` at `0x1808562bb`
- `KERNEL32!GetLastError` at `0x180856395`
- `KERNEL32!GetLastError` at `0x1808563f1`
- `KERNEL32!GetLastError` at `0x180856498`
- `KERNEL32!GetLastError` at `0x180855e8b`
- `KERNEL32!GetLastError` at `0x1808561cf`
- `KERNEL32!GetLastError` at `0x1808562bb`
- `KERNEL32!GetLastError` at `0x180856395`
- `KERNEL32!GetLastError` at `0x1808563f1`
- `KERNEL32!GetLastError` at `0x180856498`
- `KERNEL32!SetLastError` at `0x1808564f5`
- `KERNEL32!SetLastError` at `0x180856514`
- `KERNEL32!SetLastError` at `0x1808564f5`
- `KERNEL32!SetLastError` at `0x180856514`
- `KERNEL32!MulDiv` at `0x180855d3a`
- `KERNEL32!MulDiv` at `0x180855d60`
- `KERNEL32!MulDiv` at `0x180855d3a`
- `KERNEL32!MulDiv` at `0x180855d60`
- `mso40uiWin32Client!__imp_?MsoFIsHpalHalftone@@YAHPEAUHPALETTE__@@@Z` at `0x1808564dc`
- `mso40uiWin32Client!__imp_?MsoFIsHpalHalftone@@YAHPEAUHPALETTE__@@@Z` at `0x1808564dc`
- `mso40uiWin32Client!__imp_?MsoHbrCreateBrush@@YAPEAUHBRUSH__@@KK@Z` at `0x1808560ea`
- `mso40uiWin32Client!__imp_?MsoHbrCreateBrush@@YAPEAUHBRUSH__@@KK@Z` at `0x1808560ea`
- `mso40uiWin32Client!__imp_??0MSODC@@QEAA@XZ` at `0x18085605c`
- `mso40uiWin32Client!__imp_??0MSODC@@QEAA@XZ` at `0x18085605c`
- `mso40uiWin32Client!__imp_?Destroy@MSODC@@QEAAXXZ` at `0x1808561de`
- `mso40uiWin32Client!__imp_?Destroy@MSODC@@QEAAXXZ` at `0x1808563a4`
- `mso40uiWin32Client!__imp_?Destroy@MSODC@@QEAAXXZ` at `0x180856400`
- `mso40uiWin32Client!__imp_?Destroy@MSODC@@QEAAXXZ` at `0x1808561de`
- `mso40uiWin32Client!__imp_?Destroy@MSODC@@QEAAXXZ` at `0x1808563a4`
- `mso40uiWin32Client!__imp_?Destroy@MSODC@@QEAAXXZ` at `0x180856400`
- `mso40uiWin32Client!__imp_??1MSODC@@QEAA@XZ` at `0x18085641d`
- `mso40uiWin32Client!__imp_??1MSODC@@QEAA@XZ` at `0x18085641d`
- `mso40uiWin32Client!__imp_?MsoFillDc@@YAXPEAUMSODC@@PEAUHDC__@@W4MSOGELDCINFO@@PEAUHPALETTE__@@KP6AHPEAX@Z4@Z` at `0x18085608f`
- `mso40uiWin32Client!__imp_?MsoFillDc@@YAXPEAUMSODC@@PEAUHDC__@@W4MSOGELDCINFO@@PEAUHPALETTE__@@KP6AHPEAX@Z4@Z` at `0x18085630c`
- `mso40uiWin32Client!__imp_?MsoFillDc@@YAXPEAUMSODC@@PEAUHDC__@@W4MSOGELDCINFO@@PEAUHPALETTE__@@KP6AHPEAX@Z4@Z` at `0x18085608f`
- `mso40uiWin32Client!__imp_?MsoFillDc@@YAXPEAUMSODC@@PEAUHDC__@@W4MSOGELDCINFO@@PEAUHPALETTE__@@KP6AHPEAX@Z4@Z` at `0x18085630c`
- `mso40uiWin32Client!__imp_?FPaletteMatchesHalftone@@YAHPEBUtagRGBQUAD@@H@Z` at `0x1808560a3`
- `mso40uiWin32Client!__imp_?FPaletteMatchesHalftone@@YAHPEBUtagRGBQUAD@@H@Z` at `0x1808560a3`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180855fa9`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180855fa9`
- `Mso20Win32Client!__imp_?MsoAbortCallback@@YAHPEAX@Z` at `0x180856076`
- `Mso20Win32Client!__imp_?MsoAbortCallback@@YAHPEAX@Z` at `0x1808562d4`
- `USER32!GetDC` at `0x180855e7c`
- `USER32!GetDC` at `0x180855e7c`
- `USER32!ReleaseDC` at `0x1808564a6`
- `USER32!ReleaseDC` at `0x1808564a6`
- `USER32!FillRect` at `0x180856104`
- `USER32!FillRect` at `0x180856104`
- `GDI32!CreateDIBSection` at `0x180855edb`
- `GDI32!CreateDIBSection` at `0x1808562a2`
- `GDI32!CreateDIBSection` at `0x180855edb`
- `GDI32!CreateDIBSection` at `0x1808562a2`
- `GDI32!SelectPalette` at `0x180856038`
- `GDI32!SelectPalette` at `0x180856038`
- `GDI32!CreatePalette` at `0x18085601d`
- `GDI32!CreatePalette` at `0x18085601d`
- `GDI32!CreateCompatibleDC` at `0x180855ea3`
- `GDI32!CreateCompatibleDC` at `0x180855ea3`
- `GDI32!SelectObject` at `0x180855f2c`
- `GDI32!SelectObject` at `0x1808562ce`
- `GDI32!SelectObject` at `0x1808563b1`
- `GDI32!SelectObject` at `0x18085642f`
- `GDI32!SelectObject` at `0x180855f2c`
- `GDI32!SelectObject` at `0x1808562ce`
- `GDI32!SelectObject` at `0x1808563b1`
- `GDI32!SelectObject` at `0x18085642f`
- `GDI32!DeleteDC` at `0x1808564af`
- `GDI32!DeleteDC` at `0x1808564af`
- `GDI32!DeleteObject` at `0x18085610f`
- `GDI32!DeleteObject` at `0x180856409`
- `GDI32!DeleteObject` at `0x1808564c2`
- `GDI32!DeleteObject` at `0x1808564e9`
- `GDI32!DeleteObject` at `0x18085610f`
- `GDI32!DeleteObject` at `0x180856409`
- `GDI32!DeleteObject` at `0x1808564c2`
- `GDI32!DeleteObject` at `0x1808564e9`
- `GDI32!RealizePalette` at `0x18085604a`
- `GDI32!RealizePalette` at `0x18085604a`
- `GDI32!GetDIBits` at `0x1808563df`
- `GDI32!GetDIBits` at `0x180856459`
- `GDI32!GetDIBits` at `0x180856487`
- `GDI32!GetDIBits` at `0x1808563df`
- `GDI32!GetDIBits` at `0x180856459`
- `GDI32!GetDIBits` at `0x180856487`

## pseudocode

```c

```
