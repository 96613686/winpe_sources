# TBCDD::DrawDropItem(HDC__ *,tagRECT *,int,int,int,int)

- ea: `0x1809c9290`
- end: `0x1809ca43e`
- name: `?DrawDropItem@TBCDD@@MEAAXPEAUHDC__@@PEAUtagRECT@@HHHH@Z`
- size: `4526`
- prototype: `void __usercall(TBCDD *__hidden this@<rcx>, HDC hdc@<rdx>, struct tagRECT *@<r8>, int@<r9d>, int, int, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180a34ce0`

## callees

- `0x18001d310`
- `0x180029700`
- `0x18016eca0`
- `0x1804860a0`
- `0x1809c9290`
- `0x1809ca440`
- `0x1809ca89c`
- `0x1809ca8c8`
- `0x1809ca8f8`
- `0x18169afb0`

## import_xrefs

- `KERNEL32!MulDiv` at `0x1809c9870`
- `KERNEL32!MulDiv` at `0x1809c9d2b`
- `KERNEL32!MulDiv` at `0x1809c9870`
- `KERNEL32!MulDiv` at `0x1809c9d2b`
- `Mso98Win32Client!__imp_?FBadFontName@@YAHPEAUtagLOGFONTA@@@Z` at `0x1809c95ac`
- `Mso98Win32Client!__imp_?FBadFontName@@YAHPEAUtagLOGFONTA@@@Z` at `0x1809c95ac`
- `Mso98Win32Client!__imp_?FGetFontSampleHculture@@YA_NPEAUHDC__@@PEAUtagLOGFONTA@@PEAPEAX@Z` at `0x1809c98de`
- `Mso98Win32Client!__imp_?FGetFontSampleHculture@@YA_NPEAUHDC__@@PEAUtagLOGFONTA@@PEAPEAX@Z` at `0x1809c98de`
- `Mso98Win32Client!__imp_?Release@_FBC@@QEAAXXZ` at `0x1809c994a`
- `Mso98Win32Client!__imp_?Release@_FBC@@QEAAXXZ` at `0x1809ca40d`
- `Mso98Win32Client!__imp_?Release@_FBC@@QEAAXXZ` at `0x1809c994a`
- `Mso98Win32Client!__imp_?Release@_FBC@@QEAAXXZ` at `0x1809ca40d`
- `Mso98Win32Client!__imp_?Pfbc@_FBC@@SAPEAV1@H@Z` at `0x1809c95da`
- `Mso98Win32Client!__imp_?Pfbc@_FBC@@SAPEAV1@H@Z` at `0x1809c9953`
- `Mso98Win32Client!__imp_?Pfbc@_FBC@@SAPEAV1@H@Z` at `0x1809c95da`
- `Mso98Win32Client!__imp_?Pfbc@_FBC@@SAPEAV1@H@Z` at `0x1809c9953`
- `Mso98Win32Client!__imp_?FDrawAndCacheFontDropDownBitmap@@YAHPEAV_FBC@@PEAUtagLOGFONTA@@PEAXPEAUHDC__@@3PEAUtagRECT@@PEAUHBITMAP__@@@Z` at `0x1809c9c5b`
- `Mso98Win32Client!__imp_?FDrawAndCacheFontDropDownBitmap@@YAHPEAV_FBC@@PEAUtagLOGFONTA@@PEAXPEAUHDC__@@3PEAUtagRECT@@PEAUHBITMAP__@@@Z` at `0x1809c9ff9`
- `Mso98Win32Client!__imp_?FDrawAndCacheFontDropDownBitmap@@YAHPEAV_FBC@@PEAUtagLOGFONTA@@PEAXPEAUHDC__@@3PEAUtagRECT@@PEAUHBITMAP__@@@Z` at `0x1809c9c5b`
- `Mso98Win32Client!__imp_?FDrawAndCacheFontDropDownBitmap@@YAHPEAV_FBC@@PEAUtagLOGFONTA@@PEAXPEAUHDC__@@3PEAUtagRECT@@PEAUHBITMAP__@@@Z` at `0x1809c9ff9`
- `Mso98Win32Client!__imp_?InvalidatePfbc@@YAXPEAV_FBC@@@Z` at `0x1809c9941`
- `Mso98Win32Client!__imp_?InvalidatePfbc@@YAXPEAV_FBC@@@Z` at `0x1809c9941`
- `Mso98Win32Client!__imp_?InitKbOleoInfo@@YAXXZ` at `0x1809c98cd`
- `Mso98Win32Client!__imp_?InitKbOleoInfo@@YAXXZ` at `0x1809c98cd`
- `Mso98Win32Client!__imp_?GetKoi@@YAPEAU_Kb_Oleo_Info_@@XZ` at `0x1809c98bc`
- `Mso98Win32Client!__imp_?GetKoi@@YAPEAU_Kb_Oleo_Info_@@XZ` at `0x1809c98bc`
- `Mso98Win32Client!__imp_?GetWtz255@@YAXPEB_WPEA_W@Z` at `0x1809c94c4`
- `Mso98Win32Client!__imp_?GetWtz255@@YAXPEB_WPEA_W@Z` at `0x1809c94c4`
- `Mso98Win32Client!__imp_?MsoFGetTextExtentPointW@@YAHPEAUHDC__@@PEB_WHPEAUtagSIZE@@@Z` at `0x1809c9b92`
- `Mso98Win32Client!__imp_?MsoFGetTextExtentPointW@@YAHPEAUHDC__@@PEB_WHPEAUtagSIZE@@@Z` at `0x1809c9e27`
- `Mso98Win32Client!__imp_?MsoFGetTextExtentPointW@@YAHPEAUHDC__@@PEB_WHPEAUtagSIZE@@@Z` at `0x1809c9b92`
- `Mso98Win32Client!__imp_?MsoFGetTextExtentPointW@@YAHPEAUHDC__@@PEB_WHPEAUtagSIZE@@@Z` at `0x1809c9e27`
- `Mso98Win32Client!__imp_?HbmpFromLogFontHculture@_FBC@@QEAAPEAUHBITMAP__@@PEAUtagLOGFONTA@@PEAXPEAUtagSIZE@@K@Z` at `0x1809c9906`
- `Mso98Win32Client!__imp_?HbmpFromLogFontHculture@_FBC@@QEAAPEAUHBITMAP__@@PEAUtagLOGFONTA@@PEAXPEAUtagSIZE@@K@Z` at `0x1809c9906`
- `Mso98Win32Client!__imp_MsoExtTextOutW` at `0x1809c9c0d`
- `Mso98Win32Client!__imp_MsoExtTextOutW` at `0x1809c9daa`
- `Mso98Win32Client!__imp_MsoExtTextOutW` at `0x1809c9fc2`
- `Mso98Win32Client!__imp_MsoExtTextOutW` at `0x1809ca0b8`
- `Mso98Win32Client!__imp_MsoExtTextOutW` at `0x1809c9c0d`
- `Mso98Win32Client!__imp_MsoExtTextOutW` at `0x1809c9daa`
- `Mso98Win32Client!__imp_MsoExtTextOutW` at `0x1809c9fc2`
- `Mso98Win32Client!__imp_MsoExtTextOutW` at `0x1809ca0b8`
- `Mso98Win32Client!__imp_?FGetFontSampleStrFromHculture@@YA_NPEAXPEA_WIPEAU_FontSampleMulDiv_@@@Z` at `0x1809c9cec`
- `Mso98Win32Client!__imp_?FGetFontSampleStrFromHculture@@YA_NPEAXPEA_WIPEAU_FontSampleMulDiv_@@@Z` at `0x1809c9cec`
- `mso40uiWin32Client!__imp_?GetAPI@CommandBarVisuals@ToolBar@Mso@@YAAEAUIMsoToolBarCommandBarVisualsApi@123@XZ` at `0x1809ca1fb`
- `mso40uiWin32Client!__imp_?GetAPI@CommandBarVisuals@ToolBar@Mso@@YAAEAUIMsoToolBarCommandBarVisualsApi@123@XZ` at `0x1809ca1fb`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1809c94f5`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1809c94f5`
- `mso40uiWin32Client!__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ` at `0x1809c9458`
- `mso40uiWin32Client!__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ` at `0x1809c9662`
- `mso40uiWin32Client!__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ` at `0x1809c9683`
- `mso40uiWin32Client!__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ` at `0x1809c96ab`
- `mso40uiWin32Client!__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ` at `0x1809c96c9`
- `mso40uiWin32Client!__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ` at `0x1809c973c`
- `mso40uiWin32Client!__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ` at `0x1809c9458`
- `mso40uiWin32Client!__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ` at `0x1809c9662`
- `mso40uiWin32Client!__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ` at `0x1809c9683`
- `mso40uiWin32Client!__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ` at `0x1809c96ab`
- `mso40uiWin32Client!__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ` at `0x1809c96c9`
- `mso40uiWin32Client!__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ` at `0x1809c973c`
- `mso40uiWin32Client!__imp_??0PaintContext@@QEAA@PEAUHDC__@@PEAUtagRGBQUAD@@HH@Z` at `0x1809ca234`
- `mso40uiWin32Client!__imp_??0PaintContext@@QEAA@PEAUHDC__@@PEAUtagRGBQUAD@@HH@Z` at `0x1809ca234`
- `mso40uiWin32Client!__imp_?HobjSelectUI@@YAPEAXPEAUHDC__@@PEAX@Z` at `0x1809c9a18`
- `mso40uiWin32Client!__imp_?HobjSelectUI@@YAPEAXPEAUHDC__@@PEAX@Z` at `0x1809c9b70`
- `mso40uiWin32Client!__imp_?HobjSelectUI@@YAPEAXPEAUHDC__@@PEAX@Z` at `0x1809ca34b`
- `mso40uiWin32Client!__imp_?HobjSelectUI@@YAPEAXPEAUHDC__@@PEAX@Z` at `0x1809ca370`
- `mso40uiWin32Client!__imp_?HobjSelectUI@@YAPEAXPEAUHDC__@@PEAX@Z` at `0x1809ca3aa`
- `mso40uiWin32Client!__imp_?HobjSelectUI@@YAPEAXPEAUHDC__@@PEAX@Z` at `0x1809ca3d7`
- `mso40uiWin32Client!__imp_?HobjSelectUI@@YAPEAXPEAUHDC__@@PEAX@Z` at `0x1809c9a18`
- `mso40uiWin32Client!__imp_?HobjSelectUI@@YAPEAXPEAUHDC__@@PEAX@Z` at `0x1809c9b70`
- `mso40uiWin32Client!__imp_?HobjSelectUI@@YAPEAXPEAUHDC__@@PEAX@Z` at `0x1809ca34b`
- `mso40uiWin32Client!__imp_?HobjSelectUI@@YAPEAXPEAUHDC__@@PEAX@Z` at `0x1809ca370`
- `mso40uiWin32Client!__imp_?HobjSelectUI@@YAPEAXPEAUHDC__@@PEAX@Z` at `0x1809ca3aa`
- `mso40uiWin32Client!__imp_?HobjSelectUI@@YAPEAXPEAUHDC__@@PEAX@Z` at `0x1809ca3d7`
- `mso40uiWin32Client!__imp_?Settings@UIColor@Mso@@YAPEAUMSOSG@@XZ` at `0x1809c94d1`
- `mso40uiWin32Client!__imp_?Settings@UIColor@Mso@@YAPEAUMSOSG@@XZ` at `0x1809c94e0`
- `mso40uiWin32Client!__imp_?Settings@UIColor@Mso@@YAPEAUMSOSG@@XZ` at `0x1809c94fd`
- `mso40uiWin32Client!__imp_?Settings@UIColor@Mso@@YAPEAUMSOSG@@XZ` at `0x1809c951e`
- `mso40uiWin32Client!__imp_?Settings@UIColor@Mso@@YAPEAUMSOSG@@XZ` at `0x1809c952d`
- `mso40uiWin32Client!__imp_?Settings@UIColor@Mso@@YAPEAUMSOSG@@XZ` at `0x1809ca33b`
- `mso40uiWin32Client!__imp_?Settings@UIColor@Mso@@YAPEAUMSOSG@@XZ` at `0x1809ca360`
- `mso40uiWin32Client!__imp_?Settings@UIColor@Mso@@YAPEAUMSOSG@@XZ` at `0x1809c94d1`
- `mso40uiWin32Client!__imp_?Settings@UIColor@Mso@@YAPEAUMSOSG@@XZ` at `0x1809c94e0`
- `mso40uiWin32Client!__imp_?Settings@UIColor@Mso@@YAPEAUMSOSG@@XZ` at `0x1809c94fd`
- `mso40uiWin32Client!__imp_?Settings@UIColor@Mso@@YAPEAUMSOSG@@XZ` at `0x1809c951e`
- `mso40uiWin32Client!__imp_?Settings@UIColor@Mso@@YAPEAUMSOSG@@XZ` at `0x1809c952d`
- `mso40uiWin32Client!__imp_?Settings@UIColor@Mso@@YAPEAUMSOSG@@XZ` at `0x1809ca33b`
- `mso40uiWin32Client!__imp_?Settings@UIColor@Mso@@YAPEAUMSOSG@@XZ` at `0x1809ca360`
- `mso40uiWin32Client!__imp_?MsoAlphaBlend@@YAHPEAUHDC__@@HHHH0HHHHU_BLENDFUNCTION@@@Z` at `0x1809ca2ed`
- `mso40uiWin32Client!__imp_?MsoAlphaBlend@@YAHPEAUHDC__@@HHHH0HHHHU_BLENDFUNCTION@@@Z` at `0x1809ca2ed`
- `Mso30Win32Client!__imp_?FBidiContext@StringIntlUtil@Mso@@YA_NPEB_W_K_N@Z` at `0x1809c9a85`
- `Mso30Win32Client!__imp_?FBidiContext@StringIntlUtil@Mso@@YA_NPEB_W_K_N@Z` at `0x1809c9a85`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x1809c9a4a`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x1809c9db9`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x1809ca289`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x1809c9a4a`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x1809c9db9`
- `Mso30Win32Client!__imp_?MsoFRtlUI@@YAHXZ` at `0x1809ca289`
- `Mso30Win32Client!__imp_?MsoGetTextMetricsA@@YAHPEAUHDC__@@PEAUtagTEXTMETRICA@@@Z` at `0x1809c9843`
- `Mso30Win32Client!__imp_?MsoGetTextMetricsA@@YAHPEAUHDC__@@PEAUtagTEXTMETRICA@@@Z` at `0x1809c9853`
- `Mso30Win32Client!__imp_?MsoGetTextMetricsA@@YAHPEAUHDC__@@PEAUtagTEXTMETRICA@@@Z` at `0x1809c9e7f`
- `Mso30Win32Client!__imp_?MsoGetTextMetricsA@@YAHPEAUHDC__@@PEAUtagTEXTMETRICA@@@Z` at `0x1809c9843`
- `Mso30Win32Client!__imp_?MsoGetTextMetricsA@@YAHPEAUHDC__@@PEAUtagTEXTMETRICA@@@Z` at `0x1809c9853`
- `Mso30Win32Client!__imp_?MsoGetTextMetricsA@@YAHPEAUHDC__@@PEAUtagTEXTMETRICA@@@Z` at `0x1809c9e7f`
- `Mso30Win32Client!__imp_MsoFLoadWtz` at `0x1809c9ed1`
- `Mso30Win32Client!__imp_MsoFLoadWtz` at `0x1809c9ed1`
- `Mso30Win32Client!__imp_?MsoFGlyphAvailable@@YAHPEAUHDC__@@PEB_WH@Z` at `0x1809c9b30`
- `Mso30Win32Client!__imp_?MsoFGlyphAvailable@@YAHPEAUHDC__@@PEB_WH@Z` at `0x1809c9b30`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x1809c9eb6`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x1809c9eb6`
- `Mso20Win32Client!__imp_?MsoGetSystemMetricsForDPI@Mso@@YAHHV?$TUnits@MU?$TUnitsRatioTag@UDevicePixels@Math@@UInches@2@@Math@@@Math@@@Z` at `0x1809c93b8`
- `Mso20Win32Client!__imp_?MsoGetSystemMetricsForDPI@Mso@@YAHHV?$TUnits@MU?$TUnitsRatioTag@UDevicePixels@Math@@UInches@2@@Math@@@Math@@@Z` at `0x1809c93b8`
- `Mso20Win32Client!__imp_?MsoCpSzToWzCore@@YAHIPEBDPEA_WHPEAUIMsoMemHeap@@@Z` at `0x1809c964a`
- `Mso20Win32Client!__imp_?MsoCpSzToWzCore@@YAHIPEBDPEA_WHPEAUIMsoMemHeap@@@Z` at `0x1809c964a`
- `Mso20Win32Client!__imp_?MsoGetPixelsPerInchForScaleFactor@Mso@@YA?AV?$TUnits@MU?$TUnitsRatioTag@UDevicePixels@Math@@UInches@2@@Math@@@Math@@V?$TUnits@MU?$TUnitsRatioTag@UDevicePixels@Math@@UDeviceIndependentPixels@2@@Math@@@3@@Z` at `0x1809c93ab`
- `Mso20Win32Client!__imp_?MsoGetPixelsPerInchForScaleFactor@Mso@@YA?AV?$TUnits@MU?$TUnitsRatioTag@UDevicePixels@Math@@UInches@2@@Math@@@Math@@V?$TUnits@MU?$TUnitsRatioTag@UDevicePixels@Math@@UDeviceIndependentPixels@2@@Math@@@3@@Z` at `0x1809c93ab`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x1809c9770`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x1809c9770`
- `USER32!InflateRect` at `0x1809ca168`
- `USER32!InflateRect` at `0x1809ca168`
- `GDI32!PatBlt` at `0x1809c9b02`
- `GDI32!PatBlt` at `0x1809ca39e`
- `GDI32!PatBlt` at `0x1809c9b02`
- `GDI32!PatBlt` at `0x1809ca39e`
- `GDI32!CreateFontIndirectA` at `0x1809c9798`
- `GDI32!CreateFontIndirectA` at `0x1809c981b`
- `GDI32!CreateFontIndirectA` at `0x1809c987d`
- `GDI32!CreateFontIndirectA` at `0x1809c9d38`
- `GDI32!CreateFontIndirectA` at `0x1809c9798`
- `GDI32!CreateFontIndirectA` at `0x1809c981b`
- `GDI32!CreateFontIndirectA` at `0x1809c987d`
- `GDI32!CreateFontIndirectA` at `0x1809c9d38`
- `GDI32!BitBlt` at `0x1809ca113`
- `GDI32!BitBlt` at `0x1809ca113`
- `GDI32!CreateDIBSection` at `0x1809ca1d6`
- `GDI32!CreateDIBSection` at `0x1809ca1d6`
- `GDI32!GetTextAlign` at `0x1809c9a57`
- `GDI32!GetTextAlign` at `0x1809c9f22`
- `GDI32!GetTextAlign` at `0x1809ca030`
- `GDI32!GetTextAlign` at `0x1809c9a57`
- `GDI32!GetTextAlign` at `0x1809c9f22`
- `GDI32!GetTextAlign` at `0x1809ca030`
- `GDI32!SetTextColor` at `0x1809c950e`
- `GDI32!SetTextColor` at `0x1809ca3c2`
- `GDI32!SetTextColor` at `0x1809c950e`
- `GDI32!SetTextColor` at `0x1809ca3c2`
- `GDI32!SetBkColor` at `0x1809c9542`
- `GDI32!SetBkColor` at `0x1809ca3b6`
- `GDI32!SetBkColor` at `0x1809c9542`
- `GDI32!SetBkColor` at `0x1809ca3b6`
- `GDI32!SetTextAlign` at `0x1809c9a99`
- `GDI32!SetTextAlign` at `0x1809c9dcc`
- `GDI32!SetTextAlign` at `0x1809c9f47`
- `GDI32!SetTextAlign` at `0x1809c9f7b`
- `GDI32!SetTextAlign` at `0x1809c9fcd`
- `GDI32!SetTextAlign` at `0x1809ca04a`
- `GDI32!SetTextAlign` at `0x1809ca071`
- `GDI32!SetTextAlign` at `0x1809ca0c3`
- `GDI32!SetTextAlign` at `0x1809c9a99`
- `GDI32!SetTextAlign` at `0x1809c9dcc`
- `GDI32!SetTextAlign` at `0x1809c9f47`
- `GDI32!SetTextAlign` at `0x1809c9f7b`
- `GDI32!SetTextAlign` at `0x1809c9fcd`
- `GDI32!SetTextAlign` at `0x1809ca04a`
- `GDI32!SetTextAlign` at `0x1809ca071`
- `GDI32!SetTextAlign` at `0x1809ca0c3`
- `GDI32!CreateCompatibleDC` at `0x1809c95ec`
- `GDI32!CreateCompatibleDC` at `0x1809ca187`
- `GDI32!CreateCompatibleDC` at `0x1809c95ec`
- `GDI32!CreateCompatibleDC` at `0x1809ca187`
- `GDI32!SelectObject` at `0x1809c97b4`
- `GDI32!SelectObject` at `0x1809c9833`
- `GDI32!SelectObject` at `0x1809c9891`
- `GDI32!SelectObject` at `0x1809c98ab`
- `GDI32!SelectObject` at `0x1809c99ac`
- `GDI32!SelectObject` at `0x1809c9c7c`
- `GDI32!SelectObject` at `0x1809c9e4e`
- `GDI32!SelectObject` at `0x1809ca120`
- `GDI32!SelectObject` at `0x1809ca1f1`
- `GDI32!SelectObject` at `0x1809ca2f9`
- `GDI32!SelectObject` at `0x1809c97b4`
- `GDI32!SelectObject` at `0x1809c9833`
- `GDI32!SelectObject` at `0x1809c9891`
- `GDI32!SelectObject` at `0x1809c98ab`
- `GDI32!SelectObject` at `0x1809c99ac`
- `GDI32!SelectObject` at `0x1809c9c7c`
- `GDI32!SelectObject` at `0x1809c9e4e`
- `GDI32!SelectObject` at `0x1809ca120`
- `GDI32!SelectObject` at `0x1809ca1f1`
- `GDI32!SelectObject` at `0x1809ca2f9`
- `GDI32!DeleteDC` at `0x1809c9979`
- `GDI32!DeleteDC` at `0x1809c9c94`
- `GDI32!DeleteDC` at `0x1809ca0d7`
- `GDI32!DeleteDC` at `0x1809ca129`
- `GDI32!DeleteDC` at `0x1809ca317`
- `GDI32!DeleteDC` at `0x1809c9979`
- `GDI32!DeleteDC` at `0x1809c9c94`
- `GDI32!DeleteDC` at `0x1809ca0d7`
- `GDI32!DeleteDC` at `0x1809ca129`
- `GDI32!DeleteDC` at `0x1809ca317`

## pseudocode

```c
void __fastcall TBCDD::DrawDropItem(TBCDD *this, HDC hdc, struct tagRECT *a3, int a4, int a5, int a6, int a7)
{
  struct tagRECT *v7; // r12
  HDC v8; // r14
  char v10; // si
  HDC v11; // rdi
  int v12; // r15d
  unsigned int *PixelsPerInchForScaleFactor; // rax
  Mso::GDIAssistant *v14; // rcx
  __int64 v15; // rdx
  struct Mso::GDIAssistant::IGDIAssistant *GDIAssistant; // rax
  wchar_t *v17; // rcx
  COLORREF v18; // eax
  COLORREF v19; // eax
  Mso::UIColor *v20; // rcx
  bool v21; // zf
  HGDIOBJ v22; // rsi
  COLORREF v23; // edx
  struct MSOSG *v24; // rax
  HDC CompatibleDC; // rax
  Mso::GDIAssistant *v26; // rcx
  struct Mso::GDIAssistant::IGDIAssistant *v27; // rax
  Mso::GDIAssistant *v28; // rcx
  struct Mso::GDIAssistant::IGDIAssistant *v29; // rax
  Mso::GDIAssistant *v30; // rcx
  struct Mso::GDIAssistant::IGDIAssistant *v31; // rax
  Mso::GDIAssistant *v32; // rcx
  struct Mso::GDIAssistant::IGDIAssistant *v33; // rax
  Mso::GDIAssistant *v34; // rcx
  struct Mso::GDIAssistant::IGDIAssistant *v35; // rax
  const wchar_t *p_Source; // r8
  HFONT v37; // rax
  HFONT v38; // rax
  HFONT v39; // rbx
  HFONT v40; // rax
  HFONT v41; // rsi
  struct _FBC *v42; // rbx
  HBITMAP v43; // rsi
  int v44; // edx
  HBITMAP Bitmap; // rax
  __int64 v46; // rcx
  int v47; // ebx
  __int64 v48; // rcx
  int v49; // ebx
  void *v50; // rax
  LONG v51; // ecx
  int v52; // esi
  LONG v53; // eax
  unsigned int v54; // r15d
  UINT TextAlign; // eax
  bool v56; // r9
  unsigned int v57; // r8d
  UINT v58; // ebx
  unsigned __int64 v59; // r8
  bool v60; // al
  unsigned int v61; // ebx
  void *v62; // rax
  unsigned int v63; // ebx
  char v64; // bl
  HFONT v65; // rax
  LONG right; // r15d
  struct tagRECT v67; // xmm0
  HGDIOBJ v68; // rdx
  LONG bottom; // r9d
  LONG top; // r10d
  __int64 v71; // rdx
  int v72; // r15d
  wchar_t *v73; // rbx
  __int64 HinstIntl; // rax
  int v75; // edx
  int v76; // r8d
  UINT v77; // eax
  UINT v78; // esi
  __int64 v79; // rcx
  LONG v80; // r8d
  __int64 v81; // rdx
  UINT v82; // eax
  UINT v83; // esi
  __int64 v84; // rcx
  __int64 v85; // rdx
  int v86; // ecx
  HDC v87; // rbx
  HDC v88; // rbx
  HBITMAP v89; // rax
  HBITMAP v90; // rdi
  Mso::ToolBar::CommandBarVisuals *v91; // rcx
  struct Mso::ToolBar::CommandBarVisuals::IMsoToolBarCommandBarVisualsApi *API; // rax
  int v93; // r9d
  struct Mso::ToolBar::CommandBarVisuals::IMsoToolBarCommandBarVisualsApi *v94; // r15
  int v95; // xmm6_4
  void (__fastcall **v96)(struct Mso::ToolBar::CommandBarVisuals::IMsoToolBarCommandBarVisualsApi *, PaintContext *, _QWORD, struct tagRECT *, int, int, COLORREF *, int, _DWORD, HGDIOBJ *); // rcx
  unsigned int v97; // esi
  void (__fastcall *v98)(struct Mso::ToolBar::CommandBarVisuals::IMsoToolBarCommandBarVisualsApi *, PaintContext *, _QWORD, struct tagRECT *, int, int, COLORREF *, int, _DWORD, HGDIOBJ *); // r14
  PaintContext *v99; // rax
  int v100; // r9d
  LONG left; // edx
  Mso::UIColor *v102; // rcx
  struct MSOSG *v103; // rax
  void *v104; // rax
  int v105; // r8d
  struct MSOSG *v106; // rax
  void *v107; // rbx
  int lpBits; // [rsp+28h] [rbp-E0h]
  int rop; // [rsp+30h] [rbp-D8h]
  char v110; // [rsp+68h] [rbp-A0h]
  char v111; // [rsp+69h] [rbp-9Fh]
  bool v112; // [rsp+6Ah] [rbp-9Eh]
  char v113; // [rsp+6Bh] [rbp-9Dh]
  int v114; // [rsp+6Ch] [rbp-9Ch]
  __int16 v115; // [rsp+70h] [rbp-98h]
  __int64 v116; // [rsp+78h] [rbp-90h] BYREF
  int SystemMetricsForDPI; // [rsp+80h] [rbp-88h]
  int v118; // [rsp+84h] [rbp-84h] BYREF
  HDC hdca; // [rsp+88h] [rbp-80h]
  HGDIOBJ v120; // [rsp+90h] [rbp-78h] BYREF
  HGDIOBJ ho; // [rsp+98h] [rbp-70h]
  int v122; // [rsp+A0h] [rbp-68h]
  HGDIOBJ v123; // [rsp+A8h] [rbp-60h]
  HGDIOBJ h; // [rsp+B0h] [rbp-58h] BYREF
  _FBC *v125; // [rsp+B8h] [rbp-50h]
  int cy[2]; // [rsp+C0h] [rbp-48h] BYREF
  UINT align; // [rsp+C8h] [rbp-40h]
  __int64 v128; // [rsp+D0h] [rbp-38h] BYREF
  COLORREF v129; // [rsp+D8h] [rbp-30h] BYREF
  void *ppvBits; // [rsp+E0h] [rbp-28h] BYREF
  int v131[2]; // [rsp+E8h] [rbp-20h] BYREF
  COLORREF v132; // [rsp+F0h] [rbp-18h] BYREF
  COLORREF color; // [rsp+F4h] [rbp-14h]
  HGDIOBJ v134; // [rsp+F8h] [rbp-10h]
  HGDIOBJ v135; // [rsp+100h] [rbp-8h]
  HDC v136; // [rsp+108h] [rbp+0h]
  struct tagRECT v137; // [rsp+110h] [rbp+8h] BYREF
  struct tagRECT rc; // [rsp+120h] [rbp+18h] BYREF
  BITMAPINFO Source; // [rsp+130h] [rbp+28h] BYREF
  LOGFONTA v140; // [rsp+160h] [rbp+58h] BYREF
  struct tagRECT v141; // [rsp+1A0h] [rbp+98h] BYREF
  struct tagTEXTMETRICA v142; // [rsp+1B0h] [rbp+A8h] BYREF
  struct tagTEXTMETRICA nDenominator; // [rsp+1E8h] [rbp+E0h] BYREF
  struct tagTEXTMETRICA nNumerator; // [rsp+220h] [rbp+118h] BYREF
  LOGFONTW lf; // [rsp+258h] [rbp+150h] BYREF
  _WORD v146[8]; // [rsp+2B8h] [rbp+1B0h] BYREF
  int v147; // [rsp+2C8h] [rbp+1C0h] BYREF
  __int16 v148; // [rsp+2CCh] [rbp+1C4h]
  __int16 v149; // [rsp+2CEh] [rbp+1C6h]
  wchar_t v150[64]; // [rsp+4D8h] [rbp+3D0h] BYREF

  v122 = a4;
  v136 = hdc;
  v135 = 0;
  LODWORD(v116) = 0;
  v118 = 0;
  v7 = a3;
  v112 = 0;
  v8 = hdc;
  v10 = 0;
  v125 = 0;
  v11 = hdc;
  *(_QWORD *)cy = 0;
  v123 = 0;
  hdca = 0;
  v110 = 0;
  v115 = 256;
  h = 0;
  ho = 0;
  v134 = 0;
  v150[0] = 0;
  v113 = 0;
  v128 = -1;
  v111 = 0;
  v141 = 0;
  memset(&v140, 0, sizeof(v140));
  if ( a4 < 0 && !a6 )
    return;
  if ( !a3 )
  {
    if ( a4 < *((_DWORD *)this + 28) || a4 >= *((_DWORD *)this + 28) + *((__int16 *)this + 75) )
      return;
    TBCDD::GetItemRect(this, a4, 0, &v141);
    v7 = &v141;
  }
  v12 = 0;
  v114 = 0;
  PixelsPerInchForScaleFactor = (unsigned int *)Mso::MsoGetPixelsPerInchForScaleFactor(
                                                  &v129,
                                                  *((unsigned int *)this + 6));
  SystemMetricsForDPI = Mso::MsoGetSystemMetricsForDPI(2, *PixelsPerInchForScaleFactor);
  if ( !a6 || (*((_BYTE *)this + 72) & 1) != 0 || a5 )
  {
    if ( *((__int16 *)this + 74) <= 0 || v122 < 0 )
    {
      v147 = 0;
    }
    else
    {
      (*(void (__fastcall **)(_QWORD, TBCDD *, char *, int *, int, int *))(**((_QWORD **)this + 8) + 120LL))(
        *((_QWORD *)this + 8),
        this,
        (char *)this + 8,
        &v147,
        v122,
        &v118);
      if ( v118 == 112 )
        v118 = 746;
    }
    GDIAssistant = Mso::GDIAssistant::GetGDIAssistant(v14);
    LOBYTE(v15) = (*(__int64 (__fastcall **)(struct Mso::GDIAssistant::IGDIAssistant *, char *))(*(_QWORD *)GDIAssistant
                                                                                               + 56LL))(
                    GDIAssistant,
                    (char *)&v147 + 2);
    v111 = v15;
    v118 = (_BYTE)v15 != 0 ? 0x7F6B : 0;
    if ( (_BYTE)v15 )
    {
      v12 = *((__int16 *)this + 73) + 1;
      v114 = v12;
    }
    else
    {
      v114 = 0;
    }
  }
  else
  {
    (*(void (__fastcall **)(_QWORD, TBCDD *, char *, int *))(**((_QWORD **)this + 8) + 112LL))(
      *((_QWORD *)this + 8),
      this,
      (char *)this + 8,
      &v147);
  }
  v17 = (wchar_t *)*((_QWORD *)this + 21);
  if ( v17 && !(_WORD)v147 )
  {
    v10 = 1;
    GetWtz255(v17, (wchar_t *)&v147);
  }
  if ( (*((_BYTE *)this + 30) & 0x10) != 0 )
  {
    if ( a5 )
    {
      v18 = *((_DWORD *)Mso::UIColor::Settings((Mso::UIColor *)v17) + 8);
    }
    else if ( v10 )
    {
      MsoCrCbvGet(16, v15);
    }
    else
    {
      v18 = *((_DWORD *)Mso::UIColor::Settings((Mso::UIColor *)v17) + 18);
    }
  }
  else
  {
    v18 = *((_DWORD *)Mso::UIColor::Settings((Mso::UIColor *)v17) + 6);
  }
  v132 = v18;
  v19 = SetTextColor(v8, v18);
  v21 = (*((_BYTE *)this + 30) & 0x10) == 0;
  v129 = v19;
  if ( v21 )
  {
    v22 = 0;
    v23 = *((_DWORD *)Mso::UIColor::Settings(v20) + 1);
  }
  else
  {
    v22 = 0;
    v24 = Mso::UIColor::Settings(v20);
    if ( a5 )
      v23 = *((_DWORD *)v24 + 7);
    else
      v23 = *((_DWORD *)v24 + 16);
  }
  color = SetBkColor(v8, v23);
  if ( a6
    || !(unsigned int)TBCDD::FIsWysiwygFont(this)
    || !(*(unsigned int (__fastcall **)(_QWORD, TBCDD *, char *, _QWORD, int, LOGFONTA *))(**((_QWORD **)this + 8)
                                                                                         + 200LL))(
          *((_QWORD *)this + 8),
          this,
          (char *)this + 8,
          (unsigned int)v122,
          v7->bottom - v7->top,
          &v140)
    || FBadFontName(&v140) )
  {
    goto LABEL_74;
  }
  v112 = v140.lfCharSet == 2;
  if ( *((_WORD *)this + 14) == 1728
    && (v125 = _FBC::Pfbc(1)) != 0
    && (CompatibleDC = CreateCompatibleDC(v8), (hdca = CompatibleDC) != 0) )
  {
    v110 = 1;
    v11 = CompatibleDC;
  }
  else
  {
    v110 = 0;
  }
  if ( v140.lfHeight < 0 )
    v140.lfHeight = -v140.lfHeight;
  if ( v111 )
  {
    memset_0(&lf, 0, sizeof(lf));
    MsoCpSzToWzCore(0, v140.lfFaceName, lf.lfFaceName, 32, 0);
    lf.lfWeight = v140.lfWeight;
    lf.lfItalic = v140.lfItalic;
    v27 = Mso::GDIAssistant::GetGDIAssistant(v26);
    HIBYTE(v115) = (*(__int64 (__fastcall **)(struct Mso::GDIAssistant::IGDIAssistant *, LOGFONTW *))(*(_QWORD *)v27 + 104LL))(
                     v27,
                     &lf);
    v29 = Mso::GDIAssistant::GetGDIAssistant(v28);
    if ( (*(unsigned __int8 (__fastcall **)(struct Mso::GDIAssistant::IGDIAssistant *, char *))(*(_QWORD *)v29 + 160LL))(
           v29,
           (char *)&v147 + 2) )
    {
      v31 = Mso::GDIAssistant::GetGDIAssistant(v30);
      if ( (*(unsigned __int8 (__fastcall **)(struct Mso::GDIAssistant::IGDIAssistant *))(*(_QWORD *)v31 + 88LL))(v31) )
      {
        v33 = Mso::GDIAssistant::GetGDIAssistant(v32);
        if ( (*(unsigned __int8 (__fastcall **)(struct Mso::GDIAssistant::IGDIAssistant *, char *, _WORD *))(*(_QWORD *)v33 + 64LL))(
               v33,
               (char *)&v147 + 2,
               v146) )
        {
          LOWORD(v147) = 2;
          HIWORD(v147) = v146[0];
          *(_OWORD *)&Source.bmiHeader.biSize = 0;
          v148 = v146[1];
          v149 = 0;
          *(__m128i *)&Source.bmiHeader.biCompression = _mm_load_si128((const __m128i *)&_xmm);
          LOWORD(Source.bmiHeader.biSize) = 0;
          v35 = Mso::GDIAssistant::GetGDIAssistant(v34);
          (*(void (__fastcall **)(struct Mso::GDIAssistant::IGDIAssistant *, BITMAPINFO *))(*(_QWORD *)v35 + 120LL))(
            v35,
            &Source);
          p_Source = (const wchar_t *)&Source;
          if ( *(_QWORD *)&Source.bmiHeader.biXPelsPerMeter > 7u )
            p_Source = *(const wchar_t **)&Source.bmiHeader.biSize;
          wcscpy_s(lf.lfFaceName, 0x20u, p_Source);
          lf.lfCharSet = 1;
          std::basic_string<char16_t>::~basic_string<char16_t>(&Source);
        }
      }
    }
    v37 = CreateFontIndirectW(&lf);
  }
  else
  {
    v37 = CreateFontIndirectA(&v140);
  }
  v22 = v37;
  ho = v37;
  if ( !v37 )
    goto LABEL_74;
  v135 = SelectObject(v11, v37);
  v22 = 0;
  if ( (unsigned __int8)sub_1809CA8F8(v11) )
  {
    v140.lfHeight = -2048;
    memset(&nNumerator, 0, sizeof(nNumerator));
    memset(&nDenominator, 0, sizeof(nDenominator));
    v38 = CreateFontIndirectA(&v140);
    v39 = v38;
    if ( v38 )
    {
      SelectObject(v11, v38);
      MsoGetTextMetricsA(v11, &nNumerator);
      MsoGetTextMetricsA(v11, &nDenominator);
      v140.lfHeight = MulDiv(v7->bottom - v7->top, nNumerator.tmHeight, nDenominator.tmHeight);
      v40 = CreateFontIndirectA(&v140);
      v41 = v40;
      if ( v40 )
      {
        SelectObject(v11, v40);
        DeleteObject(ho);
        ho = v41;
      }
      else
      {
        SelectObject(v11, ho);
      }
      DeleteObject(v39);
      v22 = 0;
    }
  }
  if ( (*(_BYTE *)GetKoi() & 1) == 0 )
    InitKbOleoInfo();
  FGetFontSampleHculture(v11, &v140, (void **)&v128);
  if ( v110 )
  {
    v42 = v125;
    v43 = _FBC::HbmpFromLogFontHculture(v125, &v140, (void *)v128, (struct tagSIZE *)cy, 0);
    v44 = v7->bottom - v7->top;
    v123 = v43;
    if ( v43 )
    {
      if ( v44 == cy[1] && v7->right - v7->left == cy[0] )
      {
        LOBYTE(v115) = 1;
LABEL_73:
        h = SelectObject(hdca, v43);
        v22 = 0;
        goto LABEL_106;
      }
      InvalidatePfbc(v42);
      _FBC::Release(v42);
      v22 = 0;
      v125 = _FBC::Pfbc(1);
      if ( !v125 )
      {
        DeleteDC(hdca);
        goto LABEL_105;
      }
      Bitmap = CreateBitmap(v7->right - v7->left, v7->bottom - v7->top, 1u, 1u, 0);
    }
    else
    {
      Bitmap = CreateBitmap(v7->right - v7->left, v44, 1u, 1u, 0);
    }
    v123 = Bitmap;
    v43 = Bitmap;
    goto LABEL_73;
  }
  while ( 1 )
  {
LABEL_106:
    v12 = v114;
    v49 = v116;
    if ( !(_BYTE)v115 )
    {
      if ( v112 )
      {
LABEL_74:
        v46 = *((_QWORD *)this + 2);
        v120 = v22;
        (*(void (__fastcall **)(__int64, HGDIOBJ *))(*(_QWORD *)v46 + 16LL))(v46, &v120);
        v47 = v7->bottom - v7->top;
        v48 = (unsigned int)v120 >> 13;
        LOBYTE(v48) = ((unsigned __int16)v120 & 0x2000) != 0;
        v49 = (int)(v47 - GetDropdownFontHeight(v48, *((unsigned int *)this + 6))) / 2;
        v50 = (void *)sub_1809CA8C8(((unsigned int)v120 >> 13) & 1, *((unsigned int *)this + 6));
        HobjSelectUI(v11, v50);
      }
      else
      {
        *(_QWORD *)v131 = 0;
        if ( v128 == -1 || !FGetFontSampleStrFromHculture((void *)v128, v150, 0x40u, (struct _FontSampleMulDiv_ *)v131) )
        {
          v113 = 0;
        }
        else
        {
          v113 = 1;
          if ( v131[0] && v131[1] && (v131[0] != 1 || v131[1] != 1) )
          {
            v140.lfHeight = MulDiv(v140.lfHeight, v131[0], v131[1]);
            v65 = CreateFontIndirectA(&v140);
            v12 = v114;
            v49 = v116;
            v134 = v65;
          }
        }
      }
    }
    v51 = (int)v22;
    v52 = v12 + 1;
    if ( v49 >= 0 )
      v51 = v49;
    align = 0;
    if ( !a7 )
      v52 = v12;
    v53 = v51 - 1;
    if ( !a7 )
      v53 = v51;
    LODWORD(v116) = v53;
    v54 = v53;
    LODWORD(v120) = v53;
    if ( MsoFRtlUI() )
    {
      TextAlign = GetTextAlign(v11);
      v57 = *((_DWORD *)this + 18);
      v58 = TextAlign;
      align = TextAlign;
      v59 = v57 >> 26;
      if ( (v59 & 1) != 0 )
      {
        LOBYTE(v59) = v59 & 1;
        v60 = Mso::StringIntlUtil::FBidiContext(
                (Mso::StringIntlUtil *)((char *)&v147 + 2),
                (const wchar_t *)(unsigned __int16)v147,
                v59,
                v56);
        SetTextAlign(v11, v58 | (v60 << 8) | 2);
      }
      v61 = (*((_DWORD *)this + 18) & 0x4000000) != 0 ? v7->right - 1 : v7->left + 1;
    }
    else
    {
      v61 = v7->left + 1;
    }
    if ( (_BYTE)v115 )
      break;
    if ( v110 )
    {
      v114 = v52;
      if ( !PatBlt(v11, 0, 0, v7->right - v7->left, v7->bottom - v7->top, 0xFF0062u) )
        goto LABEL_103;
    }
    if ( !v111 && !v112 && !MsoFGlyphAvailable(v11, (const wchar_t *)&v147 + 1, (unsigned __int16)v147) )
    {
      v116 = 0;
      (*(void (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 2) + 16LL))(*((_QWORD *)this + 2), &v116);
      v62 = (void *)sub_1809CA8C8(((unsigned int)v116 >> 13) & 1, *((unsigned int *)this + 6));
      HobjSelectUI(v11, v62);
    }
    ppvBits = 0;
    MsoFGetTextExtentPointW(v11, (const wchar_t *)&v147 + 1, (unsigned __int16)v147, (struct tagSIZE *)&ppvBits);
    if ( v110 && ho )
    {
      v63 = v61 - v7->left;
      Source.bmiHeader.biHeight = v7->right - v7->left;
      *(_DWORD *)&Source.bmiHeader.biPlanes = v7->bottom - v7->top;
      *(_QWORD *)&Source.bmiHeader.biSize = 0;
      LODWORD(v116) = v54;
      v114 = v52;
      if ( !(unsigned int)MsoExtTextOutW(v11, v63, v54, 6, &Source, (char *)&v147 + 2, (unsigned __int16)v147, 0) )
        goto LABEL_103;
      v64 = v111;
      if ( (v111 || !v112 && !v113)
        && !FDrawAndCacheFontDropDownBitmap(v125, &v140, (void *)v128, v8, hdca, v7, (HBITMAP)h) )
      {
        LODWORD(v116) = v54;
        v114 = v52;
LABEL_103:
        v22 = 0;
        goto LABEL_104;
      }
    }
    else
    {
      right = v7->right;
      if ( v111 && (int)ppvBits > right - v52 - SystemMetricsForDPI - v7->left )
        v7->right = right - v52 - SystemMetricsForDPI;
      MsoExtTextOutW(
        v11,
        v61,
        (unsigned int)(v7->top + (_DWORD)v120),
        6,
        v7,
        (char *)&v147 + 2,
        (unsigned __int16)v147,
        0);
      v64 = v111;
      v7->right = right;
    }
    if ( MsoFRtlUI() )
      SetTextAlign(v11, align);
    v114 = v52;
    if ( a7 )
      v114 = v52 - 1;
    if ( !v112 && !v113 || v64 )
      goto LABEL_154;
    v67 = *v7;
    v120 = 0;
    v137 = v67;
    MsoFGetTextExtentPointW(v11, (const wchar_t *)&v147 + 1, (unsigned __int16)v147, (struct tagSIZE *)&v120);
    v137.left += 6 + (_DWORD)v120;
    v68 = v134;
    if ( !v134 )
      v68 = ho;
    SelectObject(v11, v68);
    memset(&v142, 0, sizeof(v142));
    MsoGetTextMetricsA(v11, &v142);
    bottom = v137.bottom;
    top = v137.top;
    v71 = (unsigned int)((v137.bottom - v142.tmHeight - v137.top) >> 31);
    LODWORD(v116) = (v137.bottom - v142.tmHeight - v137.top) / 2;
    v72 = v116;
    if ( v113 )
    {
      v73 = v150;
    }
    else
    {
      LODWORD(v71) = (v137.bottom - v142.tmHeight - v137.top) % 2;
      HinstIntl = MsoGetHinstIntl(2, v71);
      MsoFLoadWtz(HinstIntl, 137537228, &v147, 257);
      bottom = v137.bottom;
      v73 = (wchar_t *)&v147 + 1;
      top = v137.top;
    }
    v22 = 0;
    if ( !v110 )
    {
      if ( (int)v120 < v137.right && *v73 )
      {
        v82 = GetTextAlign(v11);
        v83 = v82;
        if ( (*((_DWORD *)this + 18) & 0x4000000) != 0 )
        {
          SetTextAlign(v11, v82 & 0xFFFFFFFD);
          v84 = -1;
          do
            ++v84;
          while ( v73[v84] );
          v85 = (unsigned int)(v137.left + 1 + SystemMetricsForDPI);
        }
        else
        {
          SetTextAlign(v11, v82 | 2);
          v84 = -1;
          do
            ++v84;
          while ( v73[v84] );
          v85 = (unsigned int)(v137.right - SystemMetricsForDPI - 1);
        }
        MsoExtTextOutW(v11, v85, (unsigned int)(v72 + v137.top), 536870918, &v137, v73, v84, 0);
        SetTextAlign(v11, v83);
LABEL_154:
        v22 = 0;
      }
LABEL_155:
      if ( hdca )
        DeleteDC(hdca);
      v86 = v114;
      goto LABEL_161;
    }
    v75 = -v7->left;
    v76 = -v7->top;
    rc.left = v137.left - v7->left;
    rc.right = v75 + v137.right;
    rc.top = top + v76;
    rc.bottom = bottom + v76;
    v77 = GetTextAlign(v11);
    v78 = v77;
    if ( *v73 )
    {
      if ( (*((_DWORD *)this + 18) & 0x4000000) != 0 )
      {
        SetTextAlign(v11, v77 & 0xFFFFFFFD);
        v79 = -1;
        do
          ++v79;
        while ( v73[v79] );
        v80 = v137.top - v7->top;
        v81 = (unsigned int)(v137.left - v7->left + SystemMetricsForDPI + 1);
      }
      else
      {
        SetTextAlign(v11, v77 | 2);
        v79 = -1;
        do
          ++v79;
        while ( v73[v79] );
        v80 = rc.top;
        v81 = (unsigned int)(rc.right - SystemMetricsForDPI - 1);
      }
      MsoExtTextOutW(v11, v81, (unsigned int)(v72 + v80), 536870918, &rc, v73, v79, 0);
      SetTextAlign(v11, v78);
    }
    v22 = 0;
    if ( FDrawAndCacheFontDropDownBitmap(v125, &v140, (void *)v128, v8, hdca, v7, (HBITMAP)h) )
      goto LABEL_155;
LABEL_104:
    SelectObject(hdca, h);
    DeleteObject(v123);
    v123 = 0;
    DeleteDC(hdca);
    v11 = v8;
LABEL_105:
    v110 = 0;
    hdca = 0;
  }
  v87 = hdca;
  BitBlt(v8, v7->left, v7->top, cy[0], cy[1], hdca, 0, 0, 0xCC0020u);
  SelectObject(v87, h);
  DeleteDC(v87);
  v86 = v52;
  if ( a7 )
    v86 = v52 - 1;
  v22 = 0;
LABEL_161:
  if ( v86 > 0 && !HIBYTE(v115) )
  {
    rc = *v7;
    InflateRect(&rc, -1, -1);
    rc.right = *((__int16 *)this + 73);
    rc.bottom = rc.right;
    *(_QWORD *)&rc.left = 0;
    v88 = CreateCompatibleDC(v8);
    ppvBits = 0;
    Source.bmiHeader.biWidth = *((__int16 *)this + 73);
    Source.bmiHeader.biHeight = -Source.bmiHeader.biWidth;
    Source.bmiHeader.biSize = 40;
    memset(&Source.bmiHeader.biSizeImage, 0, 24);
    *(_QWORD *)&Source.bmiHeader.biPlanes = 2097153;
    v89 = CreateDIBSection(v88, &Source, 0, &ppvBits, 0, 0);
    v90 = v89;
    if ( v89 )
    {
      v123 = SelectObject(v88, v89);
      API = Mso::ToolBar::CommandBarVisuals::GetAPI(v91);
      v93 = *((__int16 *)this + 73);
      v94 = API;
      v95 = *((_DWORD *)this + 6);
      v96 = *(void (__fastcall ***)(struct Mso::ToolBar::CommandBarVisuals::IMsoToolBarCommandBarVisualsApi *, PaintContext *, _QWORD, struct tagRECT *, int, int, COLORREF *, int, _DWORD, HGDIOBJ *))API;
      v97 = v118;
      BYTE4(h) = 0;
      v98 = *v96;
      v99 = PaintContext::PaintContext((PaintContext *)&v142, v88, (struct tagRGBQUAD *)ppvBits, v93, v93);
      LOBYTE(rop) = 0;
      LOBYTE(lpBits) = 0;
      v98(v94, v99, v97, &rc, lpBits, rop, &v132, v95, 0, &h);
      v8 = v136;
      v22 = v123;
    }
    LODWORD(v116) = 33488896;
    if ( MsoFRtlUI() && (*((_DWORD *)this + 18) & 0x4000000) != 0 )
    {
      v100 = *((__int16 *)this + 73);
      left = v7->left;
    }
    else
    {
      v100 = *((__int16 *)this + 73);
      left = v7->right - v100 - SystemMetricsForDPI;
    }
    MsoAlphaBlend(v8, left, v7->top, v100, v100, v88, 0, 0, v100, v100, (struct _BLENDFUNCTION)v116);
    SelectObject(v88, v22);
    if ( v90 )
      DeleteObject(v90);
    if ( v88 )
      DeleteDC(v88);
  }
  if ( !a6 )
  {
    v102 = (Mso::UIColor *)(unsigned int)*((__int16 *)this + 76);
    if ( (_DWORD)v102 - 1 == v122 )
    {
      v103 = Mso::UIColor::Settings(v102);
      v104 = HobjSelectUI(v8, *((void **)v103 + 17));
      v105 = v7->bottom - 2;
      goto LABEL_178;
    }
    if ( (_DWORD)v102 == v122 )
    {
      v106 = Mso::UIColor::Settings(v102);
      v104 = HobjSelectUI(v8, *((void **)v106 + 17));
      v105 = v7->top;
LABEL_178:
      v107 = v104;
      PatBlt(v8, v7->left, v105, v7->right - v7->left, 1, 0xF00021u);
      HobjSelectUI(v8, v107);
    }
  }
  SetBkColor(v8, color);
  SetTextColor(v8, v129);
  if ( v135 )
    HobjSelectUI(v8, v135);
  if ( v134 )
    DeleteObject(v134);
  if ( ho )
    DeleteObject(ho);
  if ( v125 )
    _FBC::Release(v125);
}

```

## disassembly

```asm
0x1809c9290  mov     rax, rsp
0x1809c9293  push    rbp
0x1809c9294  push    rbx
0x1809c9295  push    rsi
0x1809c9296  push    rdi
0x1809c9297  push    r12
0x1809c9299  push    r13
0x1809c929b  push    r14
0x1809c929d  push    r15
0x1809c929f  lea     rbp, [rax-4B8h]
0x1809c92a6  sub     rsp, 578h
0x1809c92ad  movaps  xmmword ptr [rax-58h], xmm6
0x1809c92b1  mov     rax, cs:__security_cookie
0x1809c92b8  xor     rax, rsp
0x1809c92bb  mov     [rbp+4B0h+var_60], rax
0x1809c92c2  xor     ebx, ebx
0x1809c92c4  mov     [rbp+4B0h+var_518], r9d
0x1809c92c8  xorps   xmm0, xmm0
0x1809c92cb  mov     [rbp+4B0h+var_4B0], rdx
0x1809c92cf  xor     eax, eax
0x1809c92d1  mov     [rbp+4B0h+var_4B8], rbx
0x1809c92d5  mov     [rsp+5B0h+var_540], ebx
0x1809c92d9  mov     r10d, r9d
0x1809c92dc  mov     [rsp+5B0h+var_534], ebx
0x1809c92e0  mov     r12, r8
0x1809c92e3  mov     [rsp+62h], bl
0x1809c92e7  mov     r14, rdx
0x1809c92ea  mov     qword ptr [rbp+4B0h+var_458.lfFaceName+14h], rax
0x1809c92f1  mov     r13, rcx
0x1809c92f4  mov     dword ptr [rbp+4B0h+var_458.lfFaceName+1Ch], eax
0x1809c92fa  mov     sil, bl
0x1809c92fd  mov     [rbp+4B0h+var_500], rbx
0x1809c9301  mov     rdi, rdx
0x1809c9304  mov     qword ptr [rbp+4B0h+cy], rbx
0x1809c9308  mov     [rbp+4B0h+var_510], rbx
0x1809c930c  mov     [rbp+4B0h+hdc], rbx
0x1809c9310  mov     [rsp+5B0h+var_550], bl
0x1809c9314  mov     byte ptr [rsp+5B0h+var_548], bl
0x1809c9318  mov     [rbp+4B0h+h], rbx
0x1809c931c  mov     [rbp+4B0h+ho], rbx
0x1809c9320  mov     [rbp+4B0h+var_4C0], rbx
0x1809c9324  mov     [rbp+4B0h+var_E0], bx
0x1809c932b  mov     [rsp+63h], bl
0x1809c932f  mov     [rbp+4B0h+var_4E8], 0FFFFFFFFFFFFFFFFh
0x1809c9337  mov     [rsp+5B0h+var_54F], bl
0x1809c933b  mov     byte ptr [rsp+5B0h+var_548+1], 1
0x1809c9340  movups  xmmword ptr [rbp+4B0h+var_418.left], xmm0
0x1809c9347  movups  xmmword ptr [rbp+4B0h+var_458.lfHeight], xmm0
0x1809c934b  movups  xmmword ptr [rbp+4B0h+var_458.lfWeight], xmm0
0x1809c934f  movups  xmmword ptr [rbp+4B0h+var_458.lfFaceName+4], xmm0
0x1809c9353  test    r9d, r9d
0x1809c9356  jns     short loc_1809C9364
0x1809c9358  cmp     [rbp+4B0h+arg_28], ebx
0x1809c935e  jz      loc_1809CA413
0x1809c9364  test    r8, r8
0x1809c9367  jnz     short loc_1809C939C
0x1809c9369  cmp     r10d, [rcx+70h]
0x1809c936d  jl      loc_1809CA413
0x1809c9373  movsx   eax, word ptr [rcx+96h]
0x1809c937a  add     eax, [rcx+70h]
0x1809c937d  cmp     r10d, eax
0x1809c9380  jge     loc_1809CA413
0x1809c9386  lea     r9, [rbp+4B0h+var_418]; struct tagRECT *
0x1809c938d  mov     edx, r10d; int
0x1809c9390  call    ?GetItemRect@TBCDD@@QEAAXHHPEAUtagRECT@@@Z; TBCDD::GetItemRect(int,int,tagRECT *)
0x1809c9395  lea     r12, [rbp+4B0h+var_418]
0x1809c939c  mov     edx, [r13+18h]
0x1809c93a0  lea     rcx, [rbp+4B0h+var_4E0]
0x1809c93a4  mov     r15d, ebx
0x1809c93a7  mov     [rsp+64h], ebx
0x1809c93ab  call    cs:__imp_?MsoGetPixelsPerInchForScaleFactor@Mso@@YA?AV?$TUnits@MU?$TUnitsRatioTag@UDevicePixels@Math@@UInches@2@@Math@@@Math@@V?$TUnits@MU?$TUnitsRatioTag@UDevicePixels@Math@@UDeviceIndependentPixels@2@@Math@@@3@@Z; Mso::MsoGetPixelsPerInchForScaleFactor(Math::TUnits<float,Math::TUnitsRatioTag<Math::DevicePixels,Math::DeviceIndependentPixels>>)
0x1809c93b1  mov     ecx, 2
0x1809c93b6  mov     edx, [rax]
0x1809c93b8  call    cs:__imp_?MsoGetSystemMetricsForDPI@Mso@@YAHHV?$TUnits@MU?$TUnitsRatioTag@UDevicePixels@Math@@UInches@2@@Math@@@Math@@@Z; Mso::MsoGetSystemMetricsForDPI(int,Math::TUnits<float,Math::TUnitsRatioTag<Math::DevicePixels,Math::Inches>>)
0x1809c93be  mov     ebx, [rbp+4B0h+arg_20]
0x1809c93c4  mov     [rsp+5B0h+var_538], eax
0x1809c93c8  xor     eax, eax
0x1809c93ca  cmp     [rbp+4B0h+arg_28], eax
0x1809c93d0  jz      short loc_1809C9403
0x1809c93d2  test    byte ptr [r13+48h], 1
0x1809c93d7  jnz     short loc_1809C9403
0x1809c93d9  test    ebx, ebx
0x1809c93db  jnz     short loc_1809C9403
0x1809c93dd  mov     rcx, [r13+40h]
0x1809c93e1  lea     r8, [r13+8]
0x1809c93e5  lea     r9, [rbp+4B0h+var_2F0]
0x1809c93ec  mov     rdx, r13
0x1809c93ef  mov     rax, [rcx]
0x1809c93f2  mov     rax, [rax+70h]
0x1809c93f6  call    cs:__guard_dispatch_icall_fptr
0x1809c93fc  xor     eax, eax
0x1809c93fe  jmp     loc_1809C94A5
0x1809c9403  cmp     [r13+94h], ax
0x1809c940b  jle     short loc_1809C9452
0x1809c940d  mov     edx, [rbp+4B0h+var_518]
0x1809c9410  test    edx, edx
0x1809c9412  js      short loc_1809C9452
0x1809c9414  mov     rcx, [r13+40h]
0x1809c9418  lea     r9, [rsp+5B0h+var_534]
0x1809c941d  mov     qword ptr [rsp+5B0h+rop], r9
0x1809c9422  lea     r8, [r13+8]
0x1809c9426  mov     dword ptr [rsp+5B0h+lpBits], edx
0x1809c942a  lea     r9, [rbp+4B0h+var_2F0]
0x1809c9431  mov     rdx, r13
0x1809c9434  mov     rax, [rcx]
0x1809c9437  mov     rax, [rax+78h]
0x1809c943b  call    cs:__guard_dispatch_icall_fptr
0x1809c9441  cmp     [rsp+5B0h+var_534], 70h ; 'p'
0x1809c9446  jnz     short loc_1809C9458
0x1809c9448  mov     [rsp+5B0h+var_534], 2EAh
0x1809c9450  jmp     short loc_1809C9458
0x1809c9452  mov     [rbp+4B0h+var_2F0], eax
0x1809c9458  call    cs:__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ; Mso::GDIAssistant::GetGDIAssistant(void)
0x1809c945e  mov     rcx, rax
0x1809c9461  lea     rdx, [rbp+4B0h+var_2F0+2]
0x1809c9468  mov     rax, [rax]
0x1809c946b  mov     rax, [rax+38h]
0x1809c946f  call    cs:__guard_dispatch_icall_fptr
0x1809c9475  mov     dl, al
0x1809c9477  mov     [rsp+5B0h+var_54F], al
0x1809c947b  neg     al
0x1809c947d  sbb     ecx, ecx
0x1809c947f  xor     eax, eax
0x1809c9481  and     ecx, 7F6Bh
0x1809c9487  mov     [rsp+5B0h+var_534], ecx
0x1809c948b  test    dl, dl
0x1809c948d  jnz     short loc_1809C9495
0x1809c948f  mov     [rsp+64h], eax
0x1809c9493  jmp     short loc_1809C94A5
0x1809c9495  movsx   r15d, word ptr [r13+92h]
0x1809c949d  inc     r15d
0x1809c94a0  mov     [rsp+64h], r15d
0x1809c94a5  mov     rcx, [r13+0A8h]
0x1809c94ac  test    rcx, rcx
0x1809c94af  jz      short loc_1809C94CA
0x1809c94b1  cmp     word ptr [rbp+4B0h+var_2F0], ax
0x1809c94b8  jnz     short loc_1809C94CA
0x1809c94ba  lea     rdx, [rbp+4B0h+var_2F0]
0x1809c94c1  mov     sil, 1
0x1809c94c4  call    cs:__imp_?GetWtz255@@YAXPEB_WPEA_W@Z; GetWtz255(wchar_t const *,wchar_t *)
0x1809c94ca  test    byte ptr [r13+1Eh], 10h
0x1809c94cf  jnz     short loc_1809C94DC
0x1809c94d1  call    cs:__imp_?Settings@UIColor@Mso@@YAPEAUMSOSG@@XZ; Mso::UIColor::Settings(void)
0x1809c94d7  mov     eax, [rax+18h]
0x1809c94da  jmp     short loc_1809C9506
0x1809c94dc  test    ebx, ebx
0x1809c94de  jz      short loc_1809C94EB
0x1809c94e0  call    cs:__imp_?Settings@UIColor@Mso@@YAPEAUMSOSG@@XZ; Mso::UIColor::Settings(void)
0x1809c94e6  mov     eax, [rax+20h]
0x1809c94e9  jmp     short loc_1809C9506
0x1809c94eb  test    sil, sil
0x1809c94ee  jz      short loc_1809C94FD
0x1809c94f0  mov     ecx, 10h
0x1809c94f5  call    cs:__imp_MsoCrCbvGet
0x1809c94fb  jmp     short loc_1809C9506
0x1809c94fd  call    cs:__imp_?Settings@UIColor@Mso@@YAPEAUMSOSG@@XZ; Mso::UIColor::Settings(void)
0x1809c9503  mov     eax, [rax+48h]
0x1809c9506  mov     edx, eax; color
0x1809c9508  mov     [rbp+4B0h+var_4C8], eax
0x1809c950b  mov     rcx, r14; hdc
0x1809c950e  call    cs:__imp_SetTextColor
0x1809c9514  test    byte ptr [r13+1Eh], 10h
0x1809c9519  mov     [rbp+4B0h+var_4E0], eax
0x1809c951c  jnz     short loc_1809C952B
0x1809c951e  call    cs:__imp_?Settings@UIColor@Mso@@YAPEAUMSOSG@@XZ; Mso::UIColor::Settings(void)
0x1809c9524  xor     esi, esi
0x1809c9526  mov     edx, [rax+4]
0x1809c9529  jmp     short loc_1809C953F
0x1809c952b  xor     esi, esi
0x1809c952d  call    cs:__imp_?Settings@UIColor@Mso@@YAPEAUMSOSG@@XZ; Mso::UIColor::Settings(void)
0x1809c9533  test    ebx, ebx
0x1809c9535  jz      short loc_1809C953C
0x1809c9537  mov     edx, [rax+1Ch]
0x1809c953a  jmp     short loc_1809C953F
0x1809c953c  mov     edx, [rax+40h]; color
0x1809c953f  mov     rcx, r14; hdc
0x1809c9542  call    cs:__imp_SetBkColor
0x1809c9548  mov     [rbp+4B0h+color], eax
0x1809c954b  cmp     [rbp+4B0h+arg_28], esi
0x1809c9551  jnz     loc_1809C99BD
0x1809c9557  mov     rcx, r13; this
0x1809c955a  call    ?FIsWysiwygFont@TBCDD@@IEAAHXZ; TBCDD::FIsWysiwygFont(void)
0x1809c955f  test    eax, eax
0x1809c9561  jz      loc_1809C99BD
0x1809c9567  mov     rcx, [r13+40h]
0x1809c956b  lea     rdx, [rbp+4B0h+var_458]
0x1809c956f  mov     r9d, [rbp+4B0h+var_518]
0x1809c9573  lea     r8, [r13+8]
0x1809c9577  mov     qword ptr [rsp+5B0h+rop], rdx
0x1809c957c  mov     rdx, r13
0x1809c957f  mov     rax, [rcx]
0x1809c9582  mov     r10, [rax+0C8h]
0x1809c9589  mov     eax, [r12+0Ch]
0x1809c958e  sub     eax, [r12+4]
0x1809c9593  mov     dword ptr [rsp+5B0h+lpBits], eax
0x1809c9597  mov     rax, r10
0x1809c959a  call    cs:__guard_dispatch_icall_fptr
0x1809c95a0  test    eax, eax
0x1809c95a2  jz      loc_1809C99BD
0x1809c95a8  lea     rcx, [rbp+4B0h+var_458]
0x1809c95ac  call    cs:__imp_?FBadFontName@@YAHPEAUtagLOGFONTA@@@Z; FBadFontName(tagLOGFONTA *)
0x1809c95b2  test    eax, eax
0x1809c95b4  jnz     loc_1809C99BD
0x1809c95ba  mov     eax, 2
0x1809c95bf  mov     ebx, 1
0x1809c95c4  cmp     [rbp+4B0h+var_458.lfCharSet], al
0x1809c95c7  mov     eax, 6C0h
0x1809c95cc  setz    byte ptr [rsp+62h]
0x1809c95d1  cmp     [r13+1Ch], ax
0x1809c95d6  jnz     short loc_1809C9604
0x1809c95d8  mov     ecx, ebx
0x1809c95da  call    cs:__imp_?Pfbc@_FBC@@SAPEAV1@H@Z; _FBC::Pfbc(int)
0x1809c95e0  mov     [rbp+4B0h+var_500], rax
0x1809c95e4  test    rax, rax
0x1809c95e7  jz      short loc_1809C9604
0x1809c95e9  mov     rcx, r14; hdc
0x1809c95ec  call    cs:__imp_CreateCompatibleDC
0x1809c95f2  mov     [rbp+4B0h+hdc], rax
0x1809c95f6  test    rax, rax
0x1809c95f9  jz      short loc_1809C9604
0x1809c95fb  mov     [rsp+5B0h+var_550], bl
0x1809c95ff  mov     rdi, rax
0x1809c9602  jmp     short loc_1809C9609
0x1809c9604  mov     [rsp+5B0h+var_550], sil
0x1809c9609  mov     eax, [rbp+4B0h+var_458.lfHeight]
0x1809c960c  test    eax, eax
0x1809c960e  jns     short loc_1809C9615
0x1809c9610  neg     eax
0x1809c9612  mov     [rbp+4B0h+var_458.lfHeight], eax
0x1809c9615  cmp     [rsp+5B0h+var_54F], sil
0x1809c961a  jz      loc_1809C9794
0x1809c9620  xor     edx, edx; Val
0x1809c9622  lea     rcx, [rbp+4B0h+lf]; void *
0x1809c9629  lea     r8d, [rdx+5Ch]; Size
0x1809c962d  call    memset_0
0x1809c9632  mov     r9d, 20h ; ' '
0x1809c9638  mov     [rsp+5B0h+lpBits], rsi
0x1809c963d  lea     r8, [rbp+4B0h+lf.lfFaceName]
0x1809c9644  xor     ecx, ecx
0x1809c9646  lea     rdx, [rbp+4B0h+var_458.lfFaceName]
0x1809c964a  call    cs:__imp_?MsoCpSzToWzCore@@YAHIPEBDPEA_WHPEAUIMsoMemHeap@@@Z; MsoCpSzToWzCore(uint,char const *,wchar_t *,int,IMsoMemHeap *)
0x1809c9650  mov     eax, [rbp+4B0h+var_458.lfWeight]
0x1809c9653  mov     [rbp+4B0h+lf.lfWeight], eax
0x1809c9659  mov     al, [rbp+4B0h+var_458.lfItalic]
0x1809c965c  mov     [rbp+4B0h+lf.lfItalic], al
0x1809c9662  call    cs:__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ; Mso::GDIAssistant::GetGDIAssistant(void)
0x1809c9668  mov     rcx, rax
0x1809c966b  lea     rdx, [rbp+4B0h+lf]
0x1809c9672  mov     rax, [rax]
0x1809c9675  mov     rax, [rax+68h]
0x1809c9679  call    cs:__guard_dispatch_icall_fptr
0x1809c967f  mov     byte ptr [rsp+5B0h+var_548+1], al
0x1809c9683  call    cs:__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ; Mso::GDIAssistant::GetGDIAssistant(void)
0x1809c9689  mov     rcx, rax
0x1809c968c  lea     rdx, [rbp+4B0h+var_2F0+2]
0x1809c9693  mov     rax, [rax]
0x1809c9696  mov     rax, [rax+0A0h]
0x1809c969d  call    cs:__guard_dispatch_icall_fptr
0x1809c96a3  test    al, al
0x1809c96a5  jz      loc_1809C9785
0x1809c96ab  call    cs:__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ; Mso::GDIAssistant::GetGDIAssistant(void)
0x1809c96b1  mov     rcx, rax
0x1809c96b4  mov     rax, [rax]
0x1809c96b7  mov     rax, [rax+58h]
0x1809c96bb  call    cs:__guard_dispatch_icall_fptr
0x1809c96c1  test    al, al
0x1809c96c3  jz      loc_1809C9785
0x1809c96c9  call    cs:__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ; Mso::GDIAssistant::GetGDIAssistant(void)
0x1809c96cf  mov     rcx, rax
0x1809c96d2  lea     r8, [rbp+4B0h+var_300]
0x1809c96d9  lea     rdx, [rbp+4B0h+var_2F0+2]
0x1809c96e0  mov     rax, [rax]
0x1809c96e3  mov     rax, [rax+40h]
0x1809c96e7  call    cs:__guard_dispatch_icall_fptr
0x1809c96ed  test    al, al
0x1809c96ef  jz      loc_1809C9785
0x1809c96f5  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1809c96fd  mov     eax, 2
0x1809c9702  mov     word ptr [rbp+4B0h+var_2F0], ax
0x1809c9709  xorps   xmm0, xmm0
0x1809c970c  movzx   eax, [rbp+4B0h+var_300]
0x1809c9713  mov     word ptr [rbp+4B0h+var_2F0+2], ax
0x1809c971a  movzx   eax, [rbp+4B0h+var_2FE]
0x1809c9721  movups  xmmword ptr [rbp+4B0h+Source], xmm0
0x1809c9725  mov     [rbp+4B0h+var_2EC], ax
0x1809c972c  mov     [rbp+4B0h+var_2EA], si
0x1809c9733  movdqu  [rbp+4B0h+var_478], xmm1
0x1809c9738  mov     word ptr [rbp+4B0h+Source], si
0x1809c973c  call    cs:__imp_?GetGDIAssistant@GDIAssistant@Mso@@YAAEAUIGDIAssistant@12@XZ; Mso::GDIAssistant::GetGDIAssistant(void)
0x1809c9742  mov     rcx, rax
0x1809c9745  lea     rdx, [rbp+4B0h+Source]
0x1809c9749  mov     rax, [rax]
0x1809c974c  mov     rax, [rax+78h]
0x1809c9750  call    cs:__guard_dispatch_icall_fptr
0x1809c9756  cmp     qword ptr [rbp+4B0h+var_478+8], 7
0x1809c975b  lea     r8, [rbp+4B0h+Source]
0x1809c975f  mov     edx, 20h ; ' '; SizeInWords
0x1809c9764  lea     rcx, [rbp+4B0h+lf.lfFaceName]; Destination
0x1809c976b  cmova   r8, [rbp+4B0h+Source]; Source
0x1809c9770  call    cs:__imp_wcscpy_s
  ... truncated ...
```
