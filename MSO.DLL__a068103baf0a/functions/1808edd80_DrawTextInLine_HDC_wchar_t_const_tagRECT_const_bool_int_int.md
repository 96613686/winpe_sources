# DrawTextInLine(HDC__ *,wchar_t const *,tagRECT const *,bool,int,int)

- ea: `0x1808edd80`
- end: `0x1808ee1fb`
- name: `?DrawTextInLine@@YAXPEAUHDC__@@PEB_WPEBUtagRECT@@_NHH@Z`
- size: `1147`
- prototype: `void __usercall(HDC@<rcx>, const wchar_t *Source@<rdx>, const struct tagRECT *@<r8>, bool@<r9b>, int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1808edcf0`
- `0x18125e4d0`

## callees

- `0x18009781c`
- `0x1801255bc`
- `0x18023c2e0`
- `0x18081ebd0`
- `0x1808edd80`

## import_xrefs

- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x1808edfe1`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x1808ee07d`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x1808ee16d`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x1808edfe1`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x1808ee07d`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x1808ee16d`
- `Mso98Win32Client!__imp_MsoDrawTextW` at `0x1808ee055`
- `Mso98Win32Client!__imp_MsoDrawTextW` at `0x1808ee055`
- `Mso98Win32Client!__imp_?GetHFontBoldSdmTaskpane@@YAPEAUHFONT__@@XZ` at `0x1808ede10`
- `Mso98Win32Client!__imp_?GetHFontBoldSdmTaskpane@@YAPEAUHFONT__@@XZ` at `0x1808ee1e1`
- `Mso98Win32Client!__imp_?GetHFontBoldSdmTaskpane@@YAPEAUHFONT__@@XZ` at `0x1808ede10`
- `Mso98Win32Client!__imp_?GetHFontBoldSdmTaskpane@@YAPEAUHFONT__@@XZ` at `0x1808ee1e1`
- `mso40uiWin32Client!__imp_?MsoDrawThemeGroupLine@@YAXPEAUHDC__@@PEAUtagRECT@@@Z` at `0x1808edeaa`
- `mso40uiWin32Client!__imp_?MsoDrawThemeGroupLine@@YAXPEAUHDC__@@PEAUtagRECT@@@Z` at `0x1808edeaa`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1808ede2b`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1808ede41`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1808ee1be`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1808ede2b`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1808ede41`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1808ee1be`
- `mso40uiWin32Client!__imp_?MsoThemeGetHTheme@@YAPEAXW4ENUM_MSOHTHEMES@@@Z` at `0x1808ee09f`
- `mso40uiWin32Client!__imp_?MsoThemeGetHTheme@@YAPEAXW4ENUM_MSOHTHEMES@@@Z` at `0x1808ee09f`
- `mso40uiWin32Client!__imp_?CbvFillRect@@YAXPEAUHDC__@@PEBUtagRECT@@K@Z` at `0x1808ee1ce`
- `mso40uiWin32Client!__imp_?CbvFillRect@@YAXPEAUHDC__@@PEBUtagRECT@@K@Z` at `0x1808ee1ce`
- `mso40uiWin32Client!__imp_?Settings@UIColor@Mso@@YAPEAUMSOSG@@XZ` at `0x1808edee1`
- `mso40uiWin32Client!__imp_?Settings@UIColor@Mso@@YAPEAUMSOSG@@XZ` at `0x1808edf24`
- `mso40uiWin32Client!__imp_?Settings@UIColor@Mso@@YAPEAUMSOSG@@XZ` at `0x1808edee1`
- `mso40uiWin32Client!__imp_?Settings@UIColor@Mso@@YAPEAUMSOSG@@XZ` at `0x1808edf24`
- `mso40uiWin32Client!__imp_?MsoGetThemeColor@@YAJPEAXHHHPEAK@Z` at `0x1808ee0c0`
- `mso40uiWin32Client!__imp_?MsoGetThemeColor@@YAJPEAXHHHPEAK@Z` at `0x1808ee0c0`
- `mso40uiWin32Client!__imp_?MsoThemeFActive@@YAHXZ` at `0x1808ede8d`
- `mso40uiWin32Client!__imp_?MsoThemeFActive@@YAHXZ` at `0x1808ee08d`
- `mso40uiWin32Client!__imp_?MsoThemeFActive@@YAHXZ` at `0x1808ede8d`
- `mso40uiWin32Client!__imp_?MsoThemeFActive@@YAHXZ` at `0x1808ee08d`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x1808ee000`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x1808ee032`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x1808ee000`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x1808ee032`
- `Mso30Win32Client!__imp_?MsoPwchStripAmpersandsWtz@@YAPEA_WPEA_W@Z` at `0x1808edfcc`
- `Mso30Win32Client!__imp_?MsoPwchStripAmpersandsWtz@@YAPEA_WPEA_W@Z` at `0x1808edfcc`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1808edfa7`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1808edfa7`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1808edfea`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1808ee1ef`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1808edfea`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1808ee1ef`
- `Mso20Win32Client!__imp_?MsoWzToWtz@@YAHPEB_WPEA_WH@Z` at `0x1808edfc3`
- `Mso20Win32Client!__imp_?MsoWzToWtz@@YAHPEB_WPEA_WH@Z` at `0x1808edfc3`
- `USER32!OffsetRect` at `0x1808edf40`
- `USER32!OffsetRect` at `0x1808edf40`
- `GDI32!SetBkMode` at `0x1808ee029`
- `GDI32!SetBkMode` at `0x1808ee061`
- `GDI32!SetBkMode` at `0x1808ee029`
- `GDI32!SetBkMode` at `0x1808ee061`
- `GDI32!SetTextColor` at `0x1808ede4c`
- `GDI32!SetTextColor` at `0x1808ede9d`
- `GDI32!SetTextColor` at `0x1808ee0cc`
- `GDI32!SetTextColor` at `0x1808ee1b3`
- `GDI32!SetTextColor` at `0x1808ede4c`
- `GDI32!SetTextColor` at `0x1808ede9d`
- `GDI32!SetTextColor` at `0x1808ee0cc`
- `GDI32!SetTextColor` at `0x1808ee1b3`
- `GDI32!SetBkColor` at `0x1808ede36`
- `GDI32!SetBkColor` at `0x1808edeed`
- `GDI32!SetBkColor` at `0x1808edf30`
- `GDI32!SetBkColor` at `0x1808edf74`
- `GDI32!SetBkColor` at `0x1808ede36`
- `GDI32!SetBkColor` at `0x1808edeed`
- `GDI32!SetBkColor` at `0x1808edf30`
- `GDI32!SetBkColor` at `0x1808edf74`
- `GDI32!ExtTextOutW` at `0x1808edf1e`
- `GDI32!ExtTextOutW` at `0x1808edf69`
- `GDI32!ExtTextOutW` at `0x1808edf1e`
- `GDI32!ExtTextOutW` at `0x1808edf69`
- `GDI32!SelectObject` at `0x1808ede1c`
- `GDI32!SelectObject` at `0x1808ee1db`
- `GDI32!SelectObject` at `0x1808ede1c`
- `GDI32!SelectObject` at `0x1808ee1db`

## pseudocode

```c

```
