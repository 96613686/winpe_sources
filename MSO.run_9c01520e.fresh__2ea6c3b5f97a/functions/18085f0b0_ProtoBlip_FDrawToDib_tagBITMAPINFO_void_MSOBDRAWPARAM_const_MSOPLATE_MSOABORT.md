# ProtoBlip::FDrawToDib(tagBITMAPINFO *,void *,MSOBDRAWPARAM const *,MSOPLATE,MSOABORT *)

- ea: `0x18085f0b0`
- end: `0x18085f9cf`
- name: `?FDrawToDib@ProtoBlip@@UEBAHPEAUtagBITMAPINFO@@PEAXPEBUMSOBDRAWPARAM@@W4MSOPLATE@@PEAUMSOABORT@@@Z`
- size: `2335`
- prototype: `int __high(struct tagBITMAPINFO *, void *, const struct MSOBDRAWPARAM *, enum MSOPLATE, struct MSOABORT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x181250830`

## callees

- `0x18001d310`
- `0x18014cd50`
- `0x18016eca0`
- `0x1802419f0`
- `0x180246060`
- `0x1802e2720`
- `0x180422820`
- `0x1804860a0`
- `0x18085f0b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18085f31b`
- `KERNEL32!GetLastError` at `0x18085f65f`
- `KERNEL32!GetLastError` at `0x18085f74b`
- `KERNEL32!GetLastError` at `0x18085f825`
- `KERNEL32!GetLastError` at `0x18085f881`
- `KERNEL32!GetLastError` at `0x18085f928`
- `KERNEL32!GetLastError` at `0x18085f31b`
- `KERNEL32!GetLastError` at `0x18085f65f`
- `KERNEL32!GetLastError` at `0x18085f74b`
- `KERNEL32!GetLastError` at `0x18085f825`
- `KERNEL32!GetLastError` at `0x18085f881`
- `KERNEL32!GetLastError` at `0x18085f928`
- `KERNEL32!SetLastError` at `0x18085f985`
- `KERNEL32!SetLastError` at `0x18085f9a4`
- `KERNEL32!SetLastError` at `0x18085f985`
- `KERNEL32!SetLastError` at `0x18085f9a4`
- `KERNEL32!MulDiv` at `0x18085f1ca`
- `KERNEL32!MulDiv` at `0x18085f1f0`
- `KERNEL32!MulDiv` at `0x18085f1ca`
- `KERNEL32!MulDiv` at `0x18085f1f0`
- `mso40uiWin32Client!__imp_?MsoFIsHpalHalftone@@YAHPEAUHPALETTE__@@@Z` at `0x18085f96c`
- `mso40uiWin32Client!__imp_?MsoFIsHpalHalftone@@YAHPEAUHPALETTE__@@@Z` at `0x18085f96c`
- `mso40uiWin32Client!__imp_?MsoHbrCreateBrush@@YAPEAUHBRUSH__@@KK@Z` at `0x18085f57a`
- `mso40uiWin32Client!__imp_?MsoHbrCreateBrush@@YAPEAUHBRUSH__@@KK@Z` at `0x18085f57a`
- `mso40uiWin32Client!__imp_??0MSODC@@QEAA@XZ` at `0x18085f4ec`
- `mso40uiWin32Client!__imp_??0MSODC@@QEAA@XZ` at `0x18085f4ec`
- `mso40uiWin32Client!__imp_?Destroy@MSODC@@QEAAXXZ` at `0x18085f66e`
- `mso40uiWin32Client!__imp_?Destroy@MSODC@@QEAAXXZ` at `0x18085f834`
- `mso40uiWin32Client!__imp_?Destroy@MSODC@@QEAAXXZ` at `0x18085f890`
- `mso40uiWin32Client!__imp_?Destroy@MSODC@@QEAAXXZ` at `0x18085f66e`
- `mso40uiWin32Client!__imp_?Destroy@MSODC@@QEAAXXZ` at `0x18085f834`
- `mso40uiWin32Client!__imp_?Destroy@MSODC@@QEAAXXZ` at `0x18085f890`
- `mso40uiWin32Client!__imp_??1MSODC@@QEAA@XZ` at `0x18085f8ad`
- `mso40uiWin32Client!__imp_??1MSODC@@QEAA@XZ` at `0x18085f8ad`
- `mso40uiWin32Client!__imp_?MsoFillDc@@YAXPEAUMSODC@@PEAUHDC__@@W4MSOGELDCINFO@@PEAUHPALETTE__@@KP6AHPEAX@Z4@Z` at `0x18085f51f`
- `mso40uiWin32Client!__imp_?MsoFillDc@@YAXPEAUMSODC@@PEAUHDC__@@W4MSOGELDCINFO@@PEAUHPALETTE__@@KP6AHPEAX@Z4@Z` at `0x18085f79c`
- `mso40uiWin32Client!__imp_?MsoFillDc@@YAXPEAUMSODC@@PEAUHDC__@@W4MSOGELDCINFO@@PEAUHPALETTE__@@KP6AHPEAX@Z4@Z` at `0x18085f51f`
- `mso40uiWin32Client!__imp_?MsoFillDc@@YAXPEAUMSODC@@PEAUHDC__@@W4MSOGELDCINFO@@PEAUHPALETTE__@@KP6AHPEAX@Z4@Z` at `0x18085f79c`
- `mso40uiWin32Client!__imp_?FPaletteMatchesHalftone@@YAHPEBUtagRGBQUAD@@H@Z` at `0x18085f533`
- `mso40uiWin32Client!__imp_?FPaletteMatchesHalftone@@YAHPEBUtagRGBQUAD@@H@Z` at `0x18085f533`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18085f439`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18085f439`
- `Mso20Win32Client!__imp_?MsoAbortCallback@@YAHPEAX@Z` at `0x18085f506`
- `Mso20Win32Client!__imp_?MsoAbortCallback@@YAHPEAX@Z` at `0x18085f764`
- `USER32!GetDC` at `0x18085f30c`
- `USER32!GetDC` at `0x18085f30c`
- `USER32!ReleaseDC` at `0x18085f936`
- `USER32!ReleaseDC` at `0x18085f936`
- `USER32!FillRect` at `0x18085f594`
- `USER32!FillRect` at `0x18085f594`
- `GDI32!CreateDIBSection` at `0x18085f36b`
- `GDI32!CreateDIBSection` at `0x18085f732`
- `GDI32!CreateDIBSection` at `0x18085f36b`
- `GDI32!CreateDIBSection` at `0x18085f732`
- `GDI32!SelectPalette` at `0x18085f4c8`
- `GDI32!SelectPalette` at `0x18085f4c8`
- `GDI32!CreatePalette` at `0x18085f4ad`
- `GDI32!CreatePalette` at `0x18085f4ad`
- `GDI32!CreateCompatibleDC` at `0x18085f333`
- `GDI32!CreateCompatibleDC` at `0x18085f333`
- `GDI32!SelectObject` at `0x18085f3bc`
- `GDI32!SelectObject` at `0x18085f75e`
- `GDI32!SelectObject` at `0x18085f841`
- `GDI32!SelectObject` at `0x18085f8bf`
- `GDI32!SelectObject` at `0x18085f3bc`
- `GDI32!SelectObject` at `0x18085f75e`
- `GDI32!SelectObject` at `0x18085f841`
- `GDI32!SelectObject` at `0x18085f8bf`
- `GDI32!DeleteDC` at `0x18085f93f`
- `GDI32!DeleteDC` at `0x18085f93f`
- `GDI32!DeleteObject` at `0x18085f59f`
- `GDI32!DeleteObject` at `0x18085f899`
- `GDI32!DeleteObject` at `0x18085f952`
- `GDI32!DeleteObject` at `0x18085f979`
- `GDI32!DeleteObject` at `0x18085f59f`
- `GDI32!DeleteObject` at `0x18085f899`
- `GDI32!DeleteObject` at `0x18085f952`
- `GDI32!DeleteObject` at `0x18085f979`
- `GDI32!RealizePalette` at `0x18085f4da`
- `GDI32!RealizePalette` at `0x18085f4da`
- `GDI32!GetDIBits` at `0x18085f86f`
- `GDI32!GetDIBits` at `0x18085f8e9`
- `GDI32!GetDIBits` at `0x18085f917`
- `GDI32!GetDIBits` at `0x18085f86f`
- `GDI32!GetDIBits` at `0x18085f8e9`
- `GDI32!GetDIBits` at `0x18085f917`

## pseudocode

```c

```
