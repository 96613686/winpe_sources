# DrawTextInLine(HDC__ *,wchar_t const *,tagRECT const *,bool,int,int)

- ea: `0x1809721b0`
- end: `0x18097262b`
- name: `?DrawTextInLine@@YAXPEAUHDC__@@PEB_WPEBUtagRECT@@_NHH@Z`
- size: `1147`
- prototype: `void __usercall(HDC@<rcx>, const wchar_t *Source@<rdx>, const struct tagRECT *@<r8>, bool@<r9b>, int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180972120`
- `0x1812199a0`

## callees

- `0x18001aea0`
- `0x18016eca0`
- `0x1801f87ec`
- `0x1809721b0`
- `0x180bf9d90`

## import_xrefs

- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x180972411`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x1809724ad`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x18097259d`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x180972411`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x1809724ad`
- `Mso98Win32Client!__imp_MsoGetTextExtentPointW` at `0x18097259d`
- `Mso98Win32Client!__imp_MsoDrawTextW` at `0x180972485`
- `Mso98Win32Client!__imp_MsoDrawTextW` at `0x180972485`
- `Mso98Win32Client!__imp_?GetHFontBoldSdmTaskpane@@YAPEAUHFONT__@@XZ` at `0x180972240`
- `Mso98Win32Client!__imp_?GetHFontBoldSdmTaskpane@@YAPEAUHFONT__@@XZ` at `0x180972611`
- `Mso98Win32Client!__imp_?GetHFontBoldSdmTaskpane@@YAPEAUHFONT__@@XZ` at `0x180972240`
- `Mso98Win32Client!__imp_?GetHFontBoldSdmTaskpane@@YAPEAUHFONT__@@XZ` at `0x180972611`
- `mso40uiWin32Client!__imp_?MsoDrawThemeGroupLine@@YAXPEAUHDC__@@PEAUtagRECT@@@Z` at `0x1809722da`
- `mso40uiWin32Client!__imp_?MsoDrawThemeGroupLine@@YAXPEAUHDC__@@PEAUtagRECT@@@Z` at `0x1809722da`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x18097225b`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x180972271`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1809725ee`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x18097225b`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x180972271`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1809725ee`
- `mso40uiWin32Client!__imp_?MsoThemeGetHTheme@@YAPEAXW4ENUM_MSOHTHEMES@@@Z` at `0x1809724cf`
- `mso40uiWin32Client!__imp_?MsoThemeGetHTheme@@YAPEAXW4ENUM_MSOHTHEMES@@@Z` at `0x1809724cf`
- `mso40uiWin32Client!__imp_?CbvFillRect@@YAXPEAUHDC__@@PEBUtagRECT@@K@Z` at `0x1809725fe`
- `mso40uiWin32Client!__imp_?CbvFillRect@@YAXPEAUHDC__@@PEBUtagRECT@@K@Z` at `0x1809725fe`
- `mso40uiWin32Client!__imp_?Settings@UIColor@Mso@@YAPEAUMSOSG@@XZ` at `0x180972311`
- `mso40uiWin32Client!__imp_?Settings@UIColor@Mso@@YAPEAUMSOSG@@XZ` at `0x180972354`
- `mso40uiWin32Client!__imp_?Settings@UIColor@Mso@@YAPEAUMSOSG@@XZ` at `0x180972311`
- `mso40uiWin32Client!__imp_?Settings@UIColor@Mso@@YAPEAUMSOSG@@XZ` at `0x180972354`
- `mso40uiWin32Client!__imp_?MsoGetThemeColor@@YAJPEAXHHHPEAK@Z` at `0x1809724f0`
- `mso40uiWin32Client!__imp_?MsoGetThemeColor@@YAJPEAXHHHPEAK@Z` at `0x1809724f0`
- `mso40uiWin32Client!__imp_?MsoThemeFActive@@YAHXZ` at `0x1809722bd`
- `mso40uiWin32Client!__imp_?MsoThemeFActive@@YAHXZ` at `0x1809724bd`
- `mso40uiWin32Client!__imp_?MsoThemeFActive@@YAHXZ` at `0x1809722bd`
- `mso40uiWin32Client!__imp_?MsoThemeFActive@@YAHXZ` at `0x1809724bd`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x180972430`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x180972462`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x180972430`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x180972462`
- `Mso30Win32Client!__imp_?MsoPwchStripAmpersandsWtz@@YAPEA_WPEA_W@Z` at `0x1809723fc`
- `Mso30Win32Client!__imp_?MsoPwchStripAmpersandsWtz@@YAPEA_WPEA_W@Z` at `0x1809723fc`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1809723d7`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1809723d7`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18097241a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18097261f`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18097241a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18097261f`
- `Mso20Win32Client!__imp_?MsoWzToWtz@@YAHPEB_WPEA_WH@Z` at `0x1809723f3`
- `Mso20Win32Client!__imp_?MsoWzToWtz@@YAHPEB_WPEA_WH@Z` at `0x1809723f3`
- `USER32!OffsetRect` at `0x180972370`
- `USER32!OffsetRect` at `0x180972370`
- `GDI32!SetBkMode` at `0x180972459`
- `GDI32!SetBkMode` at `0x180972491`
- `GDI32!SetBkMode` at `0x180972459`
- `GDI32!SetBkMode` at `0x180972491`
- `GDI32!SetTextColor` at `0x18097227c`
- `GDI32!SetTextColor` at `0x1809722cd`
- `GDI32!SetTextColor` at `0x1809724fc`
- `GDI32!SetTextColor` at `0x1809725e3`
- `GDI32!SetTextColor` at `0x18097227c`
- `GDI32!SetTextColor` at `0x1809722cd`
- `GDI32!SetTextColor` at `0x1809724fc`
- `GDI32!SetTextColor` at `0x1809725e3`
- `GDI32!SetBkColor` at `0x180972266`
- `GDI32!SetBkColor` at `0x18097231d`
- `GDI32!SetBkColor` at `0x180972360`
- `GDI32!SetBkColor` at `0x1809723a4`
- `GDI32!SetBkColor` at `0x180972266`
- `GDI32!SetBkColor` at `0x18097231d`
- `GDI32!SetBkColor` at `0x180972360`
- `GDI32!SetBkColor` at `0x1809723a4`
- `GDI32!ExtTextOutW` at `0x18097234e`
- `GDI32!ExtTextOutW` at `0x180972399`
- `GDI32!ExtTextOutW` at `0x18097234e`
- `GDI32!ExtTextOutW` at `0x180972399`
- `GDI32!SelectObject` at `0x18097224c`
- `GDI32!SelectObject` at `0x18097260b`
- `GDI32!SelectObject` at `0x18097224c`
- `GDI32!SelectObject` at `0x18097260b`

## pseudocode

```c

```
