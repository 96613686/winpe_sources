# Jot::CWin32EmptyView::RenderCanvas(HDC__ *,Ofc::CRect const &)

- ea: `0x1803d0bf4`
- end: `0x1803d13e5`
- name: `?RenderCanvas@CWin32EmptyView@Jot@@AEAAXPEAUHDC__@@AEBVCRect@Ofc@@@Z`
- size: `2033`
- prototype: `void __fastcall(Jot::CWin32EmptyView *__hidden this, HDC, RECT *lprect)`
- caller_count: `3`
- callee_count: `11`
- tags: ``

## callers

- `0x1803d0050`
- `0x1806ff1a0`
- `0x180822de0`

## callees

- `0x180031420`
- `0x1801232d8`
- `0x1801a3758`
- `0x1802e2251`
- `0x1802e5170`
- `0x1802e5190`
- `0x1803d0bf4`
- `0x1803d13e8`
- `0x1803d1ec4`
- `0x1803d1f58`
- `0x180883b94`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x1803d0ee4`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x1803d1173`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x1803d0ee4`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x1803d1173`
- `GDI32!SetBkColor` at `0x1803d0cd6`
- `GDI32!SetBkColor` at `0x1803d0d27`
- `GDI32!SetBkColor` at `0x1803d0f59`
- `GDI32!SetBkColor` at `0x1803d0cd6`
- `GDI32!SetBkColor` at `0x1803d0d27`
- `GDI32!SetBkColor` at `0x1803d0f59`
- `GDI32!ExtTextOutW` at `0x1803d0d56`
- `GDI32!ExtTextOutW` at `0x1803d0d56`
- `GDI32!SetTextColor` at `0x1803d0caf`
- `GDI32!SetTextColor` at `0x1803d0d0a`
- `GDI32!SetTextColor` at `0x1803d0f4d`
- `GDI32!SetTextColor` at `0x1803d0caf`
- `GDI32!SetTextColor` at `0x1803d0d0a`
- `GDI32!SetTextColor` at `0x1803d0f4d`
- `gdiplus!GdipDrawImage` at `0x1803d1097`
- `gdiplus!GdipDrawImage` at `0x1803d1097`
- `gdiplus!GdipDeleteGraphics` at `0x1803d10a0`
- `gdiplus!GdipDeleteGraphics` at `0x1803d10a0`
- `gdiplus!GdipCreateFromHDC` at `0x1803d1061`
- `gdiplus!GdipCreateFromHDC` at `0x1803d1061`
- `USER32!SetRect` at `0x1803d0dc8`
- `USER32!SetRect` at `0x1803d130a`
- `USER32!SetRect` at `0x1803d0dc8`
- `USER32!SetRect` at `0x1803d130a`
- `USER32!SetWindowTextW` at `0x1803d0e1a`
- `USER32!SetWindowTextW` at `0x1803d1266`
- `USER32!SetWindowTextW` at `0x1803d0e1a`
- `USER32!SetWindowTextW` at `0x1803d1266`
- `MSO!__imp_MsoDrawTextW` at `0x1803d0f2a`
- `MSO!__imp_MsoDrawTextW` at `0x1803d11bd`
- `MSO!__imp_MsoDrawTextW` at `0x1803d11f1`
- `MSO!__imp_MsoDrawTextW` at `0x1803d0f2a`
- `MSO!__imp_MsoDrawTextW` at `0x1803d11bd`
- `MSO!__imp_MsoDrawTextW` at `0x1803d11f1`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1803d0cff`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1803d0d1c`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1803d0cff`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1803d0d1c`
- `mso40uiWin32Client!__imp_?GetApplicationWindowColors@VisualVersion@@YA?AUApplicationWindowColors@1@XZ` at `0x1803d0c61`
- `mso40uiWin32Client!__imp_?GetApplicationWindowColors@VisualVersion@@YA?AUApplicationWindowColors@1@XZ` at `0x1803d0c61`
- `mso40uiWin32Client!__imp_?MsoGetTextStyle@TextStyles@Mso@@YA?AV?$TCntPtr@$$CBUITextStyle@TextStyles@Mso@@@2@H@Z` at `0x1803d0c31`
- `mso40uiWin32Client!__imp_?MsoGetTextStyle@TextStyles@Mso@@YA?AV?$TCntPtr@$$CBUITextStyle@TextStyles@Mso@@@2@H@Z` at `0x1803d10c0`
- `mso40uiWin32Client!__imp_?MsoGetTextStyle@TextStyles@Mso@@YA?AV?$TCntPtr@$$CBUITextStyle@TextStyles@Mso@@@2@H@Z` at `0x1803d0c31`
- `mso40uiWin32Client!__imp_?MsoGetTextStyle@TextStyles@Mso@@YA?AV?$TCntPtr@$$CBUITextStyle@TextStyles@Mso@@@2@H@Z` at `0x1803d10c0`
- `mso40uiWin32Client!__imp_?GetVisualStyle@VisualVersion@@YA?AW4VisualStyle@1@XZ` at `0x1803d0c4d`
- `mso40uiWin32Client!__imp_?GetVisualStyle@VisualVersion@@YA?AW4VisualStyle@1@XZ` at `0x1803d0c4d`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1803d1276`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1803d1276`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1803d0fb1`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1803d0fbf`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1803d0fcd`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1803d1238`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1803d1246`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1803d1254`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1803d0fb1`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1803d0fbf`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1803d0fcd`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1803d1238`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1803d1246`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1803d1254`

## pseudocode

```c

```
