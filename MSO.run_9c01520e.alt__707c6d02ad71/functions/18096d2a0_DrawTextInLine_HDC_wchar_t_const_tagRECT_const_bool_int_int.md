# DrawTextInLine(HDC__ *,wchar_t const *,tagRECT const *,bool,int,int)

- ea: `0x18096d2a0`
- end: `0x18096d71b`
- name: `?DrawTextInLine@@YAXPEAUHDC__@@PEB_WPEBUtagRECT@@_NHH@Z`
- size: `1147`
- prototype: `void __usercall(HDC@<rcx>, const wchar_t *Source@<rdx>, const struct tagRECT *@<r8>, bool@<r9b>, int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18096d210`
- `0x1812193e0`

## callees

- `0x18001aeb0`
- `0x180214004`
- `0x180485240`
- `0x18096d2a0`
- `0x180bf5320`

## import_xrefs

- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x18096d501`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x18096d59d`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x18096d68d`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x18096d501`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x18096d59d`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x18096d68d`
- `Mso98Win32Client!__imp_MsoDrawTextW` at `0x18096d575`
- `Mso98Win32Client!__imp_MsoDrawTextW` at `0x18096d575`
- `Mso98Win32Client!__imp_?GetHFontBoldSdmTaskpane@@YAPEAUHFONT__@@XZ` at `0x18096d330`
- `Mso98Win32Client!__imp_?GetHFontBoldSdmTaskpane@@YAPEAUHFONT__@@XZ` at `0x18096d701`
- `Mso98Win32Client!__imp_?GetHFontBoldSdmTaskpane@@YAPEAUHFONT__@@XZ` at `0x18096d330`
- `Mso98Win32Client!__imp_?GetHFontBoldSdmTaskpane@@YAPEAUHFONT__@@XZ` at `0x18096d701`
- `mso40uiWin32Client!__imp_?MsoDrawThemeGroupLine@@YAXPEAUHDC__@@PEAUtagRECT@@@Z` at `0x18096d3ca`
- `mso40uiWin32Client!__imp_?MsoDrawThemeGroupLine@@YAXPEAUHDC__@@PEAUtagRECT@@@Z` at `0x18096d3ca`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x18096d34b`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x18096d361`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x18096d6de`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x18096d34b`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x18096d361`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x18096d6de`
- `mso40uiWin32Client!__imp_?MsoThemeGetHTheme@@YAPEAXW4ENUM_MSOHTHEMES@@@Z` at `0x18096d5bf`
- `mso40uiWin32Client!__imp_?MsoThemeGetHTheme@@YAPEAXW4ENUM_MSOHTHEMES@@@Z` at `0x18096d5bf`
- `mso40uiWin32Client!__imp_?CbvFillRect@@YAXPEAUHDC__@@PEBUtagRECT@@K@Z` at `0x18096d6ee`
- `mso40uiWin32Client!__imp_?CbvFillRect@@YAXPEAUHDC__@@PEBUtagRECT@@K@Z` at `0x18096d6ee`
- `mso40uiWin32Client!__imp_?Settings@UIColor@Mso@@YAPEAUMSOSG@@XZ` at `0x18096d401`
- `mso40uiWin32Client!__imp_?Settings@UIColor@Mso@@YAPEAUMSOSG@@XZ` at `0x18096d444`
- `mso40uiWin32Client!__imp_?Settings@UIColor@Mso@@YAPEAUMSOSG@@XZ` at `0x18096d401`
- `mso40uiWin32Client!__imp_?Settings@UIColor@Mso@@YAPEAUMSOSG@@XZ` at `0x18096d444`
- `mso40uiWin32Client!__imp_?MsoGetThemeColor@@YAJPEAXHHHPEAK@Z` at `0x18096d5e0`
- `mso40uiWin32Client!__imp_?MsoGetThemeColor@@YAJPEAXHHHPEAK@Z` at `0x18096d5e0`
- `mso40uiWin32Client!__imp_?MsoThemeFActive@@YAHXZ` at `0x18096d3ad`
- `mso40uiWin32Client!__imp_?MsoThemeFActive@@YAHXZ` at `0x18096d5ad`
- `mso40uiWin32Client!__imp_?MsoThemeFActive@@YAHXZ` at `0x18096d3ad`
- `mso40uiWin32Client!__imp_?MsoThemeFActive@@YAHXZ` at `0x18096d5ad`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x18096d520`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x18096d552`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x18096d520`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x18096d552`
- `Mso30Win32Client!__imp_?MsoPwchStripAmpersandsWtz@@YAPEA_WPEA_W@Z` at `0x18096d4ec`
- `Mso30Win32Client!__imp_?MsoPwchStripAmpersandsWtz@@YAPEA_WPEA_W@Z` at `0x18096d4ec`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18096d4c7`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18096d4c7`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18096d50a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18096d70f`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18096d50a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18096d70f`
- `Mso20Win32Client!__imp_?MsoWzToWtz@@YAHPEB_WPEA_WH@Z` at `0x18096d4e3`
- `Mso20Win32Client!__imp_?MsoWzToWtz@@YAHPEB_WPEA_WH@Z` at `0x18096d4e3`
- `USER32!OffsetRect` at `0x18096d460`
- `USER32!OffsetRect` at `0x18096d460`
- `GDI32!SetBkMode` at `0x18096d549`
- `GDI32!SetBkMode` at `0x18096d581`
- `GDI32!SetBkMode` at `0x18096d549`
- `GDI32!SetBkMode` at `0x18096d581`
- `GDI32!SetTextColor` at `0x18096d36c`
- `GDI32!SetTextColor` at `0x18096d3bd`
- `GDI32!SetTextColor` at `0x18096d5ec`
- `GDI32!SetTextColor` at `0x18096d6d3`
- `GDI32!SetTextColor` at `0x18096d36c`
- `GDI32!SetTextColor` at `0x18096d3bd`
- `GDI32!SetTextColor` at `0x18096d5ec`
- `GDI32!SetTextColor` at `0x18096d6d3`
- `GDI32!SetBkColor` at `0x18096d356`
- `GDI32!SetBkColor` at `0x18096d40d`
- `GDI32!SetBkColor` at `0x18096d450`
- `GDI32!SetBkColor` at `0x18096d494`
- `GDI32!SetBkColor` at `0x18096d356`
- `GDI32!SetBkColor` at `0x18096d40d`
- `GDI32!SetBkColor` at `0x18096d450`
- `GDI32!SetBkColor` at `0x18096d494`
- `GDI32!ExtTextOutW` at `0x18096d43e`
- `GDI32!ExtTextOutW` at `0x18096d489`
- `GDI32!ExtTextOutW` at `0x18096d43e`
- `GDI32!ExtTextOutW` at `0x18096d489`
- `GDI32!SelectObject` at `0x18096d33c`
- `GDI32!SelectObject` at `0x18096d6fb`
- `GDI32!SelectObject` at `0x18096d33c`
- `GDI32!SelectObject` at `0x18096d6fb`

## pseudocode

```c

```
