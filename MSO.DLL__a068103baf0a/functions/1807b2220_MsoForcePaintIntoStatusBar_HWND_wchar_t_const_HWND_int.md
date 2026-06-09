# MsoForcePaintIntoStatusBar(HWND__ *,wchar_t const *,HWND__ * *,int)

- ea: `0x1807b2220`
- end: `0x1807b2979`
- name: `?MsoForcePaintIntoStatusBar@@YAHPEAUHWND__@@PEB_WPEAPEAU1@H@Z`
- size: `1881`
- prototype: `__int64 __fastcall(HWND, const wchar_t *, HWND *, int)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x1800f3198`
- `0x1807b2108`

## callees

- `0x1800372c0`
- `0x180045260`
- `0x1800a2bbc`
- `0x1800c79c0`
- `0x1800f2c9c`
- `0x18018b0b8`
- `0x1801a9930`
- `0x180239aa0`
- `0x18023c2e0`
- `0x18023e8d0`
- `0x1807b2220`

## import_xrefs

- `Mso98Win32Client!__imp_?MsoGomDrawTextExW@@YAHPEAVCGomDC@@PEB_WHPEAUtagRECT@@KPEAUtagDRAWTEXTPARAMS@@@Z` at `0x1807b2958`
- `Mso98Win32Client!__imp_?MsoGomDrawTextExW@@YAHPEAVCGomDC@@PEB_WHPEAUtagRECT@@KPEAUtagDRAWTEXTPARAMS@@@Z` at `0x1807b2958`
- `Mso98Win32Client!__imp_?Release@CMsoStatusDataSet@@UEAAKXZ` at `0x1807b2767`
- `Mso98Win32Client!__imp_?Release@CMsoStatusDataSet@@UEAAKXZ` at `0x1807b2882`
- `Mso98Win32Client!__imp_?Release@CMsoStatusDataSet@@UEAAKXZ` at `0x1807b2767`
- `Mso98Win32Client!__imp_?Release@CMsoStatusDataSet@@UEAAKXZ` at `0x1807b2882`
- `Mso98Win32Client!__imp_?SetHwndFakePaint@CMsoStatusDataSet@@QEAAXPEAUHWND__@@@Z` at `0x1807b2868`
- `Mso98Win32Client!__imp_?SetHwndFakePaint@CMsoStatusDataSet@@QEAAXPEAUHWND__@@@Z` at `0x1807b28bb`
- `Mso98Win32Client!__imp_?SetHwndFakePaint@CMsoStatusDataSet@@QEAAXPEAUHWND__@@@Z` at `0x1807b2868`
- `Mso98Win32Client!__imp_?SetHwndFakePaint@CMsoStatusDataSet@@QEAAXPEAUHWND__@@@Z` at `0x1807b28bb`
- `Mso98Win32Client!__imp_?GetStaticClassInfo@NetPane@@SAPEAUIClassInfo@NetUI@@XZ` at `0x1807b24fb`
- `Mso98Win32Client!__imp_?GetStaticClassInfo@NetPane@@SAPEAUIClassInfo@NetUI@@XZ` at `0x1807b24fb`
- `Mso98Win32Client!__imp_?GetHwndFakePaint@CMsoStatusDataSet@@QEBAPEAUHWND__@@XZ` at `0x1807b2476`
- `Mso98Win32Client!__imp_?GetHwndFakePaint@CMsoStatusDataSet@@QEBAPEAUHWND__@@XZ` at `0x1807b2476`
- `mso40uiWin32Client!__imp_?MsoFPitbsFromHwnd@@YA_NPEAUHWND__@@PEAPEAUIMsoToolbarSet@@@Z` at `0x1807b226f`
- `mso40uiWin32Client!__imp_?MsoFPitbsFromHwnd@@YA_NPEAUHWND__@@PEAPEAUIMsoToolbarSet@@@Z` at `0x1807b226f`
- `mso40uiWin32Client!__imp_?GetLikelyBackgroundColor@Element@NetUI@@QEBA?AV?$optional@K@std@@XZ` at `0x1807b2526`
- `mso40uiWin32Client!__imp_?GetLikelyBackgroundColor@Element@NetUI@@QEBA?AV?$optional@K@std@@XZ` at `0x1807b2526`
- `mso40uiWin32Client!__imp_?GetFontCache@NetUI@@YAPEAVFontCache@1@XZ` at `0x1807b26b1`
- `mso40uiWin32Client!__imp_?GetFontCache@NetUI@@YAPEAVFontCache@1@XZ` at `0x1807b26b1`
- `mso40uiWin32Client!__imp_?NetUIGomGetCache@NetUI@@YAPEAVCGomCache@@XZ` at `0x1807b26a8`
- `mso40uiWin32Client!__imp_?NetUIGomGetCache@NetUI@@YAPEAVCGomCache@@XZ` at `0x1807b26a8`
- `mso40uiWin32Client!__imp_?GetStaticClassInfo@HWNDElement@NetUI@@SAPEAUIClassInfo@2@XZ` at `0x1807b23b5`
- `mso40uiWin32Client!__imp_?GetStaticClassInfo@HWNDElement@NetUI@@SAPEAUIClassInfo@2@XZ` at `0x1807b23b5`
- `mso40uiWin32Client!__imp_?GetFontPropertiesImpl@Element@NetUI@@QEBAXPEA_WHAEAV?$variant@V?$TUnits@MUPoints@Math@@@Math@@V?$TUnits@MUDevicePixels@Math@@@2@V?$TUnits@MUDeviceIndependentPixels@Math@@@2@@std@@AEAH2PEAKQEBUPropertyInfo@2@@Z` at `0x1807b267c`
- `mso40uiWin32Client!__imp_?GetFontPropertiesImpl@Element@NetUI@@QEBAXPEA_WHAEAV?$variant@V?$TUnits@MUPoints@Math@@@Math@@V?$TUnits@MUDevicePixels@Math@@@2@V?$TUnits@MUDeviceIndependentPixels@Math@@@2@@std@@AEAH2PEAKQEBUPropertyInfo@2@@Z` at `0x1807b267c`
- `mso40uiWin32Client!__imp_?CheckOutGomFont@FontCache@NetUI@@QEAAPEAVCGomFont@@PEB_WV?$TUnits@HUDevicePixels@Math@@@Math@@HH@Z` at `0x1807b26cf`
- `mso40uiWin32Client!__imp_?CheckOutGomFont@FontCache@NetUI@@QEAAPEAVCGomFont@@PEB_WV?$TUnits@HUDevicePixels@Math@@@Math@@HH@Z` at `0x1807b26cf`
- `mso40uiWin32Client!__imp_?FindDescendent@Element@NetUI@@QEBAPEAV12@PEBUIClassInfo@2@@Z` at `0x1807b2507`
- `mso40uiWin32Client!__imp_?FindDescendent@Element@NetUI@@QEBAPEAV12@PEBUIClassInfo@2@@Z` at `0x1807b2507`
- `mso40uiWin32Client!__imp_?GetRootElement@NUIDocument@NetUI@@QEBAPEAVElement@2@XZ` at `0x1807b23ac`
- `mso40uiWin32Client!__imp_?GetRootElement@NUIDocument@NetUI@@QEBAPEAVElement@2@XZ` at `0x1807b23ac`
- `mso40uiWin32Client!__imp_MsoCbvFillRectFast` at `0x1807b254f`
- `mso40uiWin32Client!__imp_MsoCbvFillRectFast` at `0x1807b254f`
- `mso40uiWin32Client!__imp_?GetHWND@HWNDElement@NetUI@@QEBAPEAUHWND__@@XZ` at `0x1807b23f3`
- `mso40uiWin32Client!__imp_?GetHWND@HWNDElement@NetUI@@QEBAPEAUHWND__@@XZ` at `0x1807b23f3`
- `mso40uiWin32Client!__imp_?FontSizeToPxI@Element@NetUI@@QEBA?AV?$TUnits@HUDevicePixels@Math@@@Math@@AEBV?$variant@V?$TUnits@MUPoints@Math@@@Math@@V?$TUnits@MUDevicePixels@Math@@@2@V?$TUnits@MUDeviceIndependentPixels@Math@@@2@@std@@@Z` at `0x1807b2696`
- `mso40uiWin32Client!__imp_?FontSizeToPxI@Element@NetUI@@QEBA?AV?$TUnits@HUDevicePixels@Math@@@Math@@AEBV?$variant@V?$TUnits@MUPoints@Math@@@Math@@V?$TUnits@MUDevicePixels@Math@@@2@V?$TUnits@MUDeviceIndependentPixels@Math@@@2@@std@@@Z` at `0x1807b2696`
- `mso40uiWin32Client!__imp_?MsoSetWindowPos@@YAHPEAUHWND__@@0HHHHI@Z` at `0x1807b28e3`
- `mso40uiWin32Client!__imp_?MsoSetWindowPos@@YAHPEAUHWND__@@0HHHHI@Z` at `0x1807b290f`
- `mso40uiWin32Client!__imp_?MsoSetWindowPos@@YAHPEAUHWND__@@0HHHHI@Z` at `0x1807b28e3`
- `mso40uiWin32Client!__imp_?MsoSetWindowPos@@YAHPEAUHWND__@@0HHHHI@Z` at `0x1807b290f`
- `mso40uiWin32Client!__imp_?ForegroundPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ` at `0x1807b2642`
- `mso40uiWin32Client!__imp_?ForegroundPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ` at `0x1807b2642`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1807b2620`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1807b2777`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1807b27bf`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1807b2620`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1807b2777`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1807b27bf`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1807b275b`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1807b27d1`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1807b2894`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1807b275b`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1807b27d1`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1807b2894`
- `USER32!DefWindowProcW` at `0x1807b27e7`
- `USER32!GetClientRect` at `0x1807b2496`
- `USER32!GetClientRect` at `0x1807b24b3`
- `USER32!GetClientRect` at `0x1807b2496`
- `USER32!GetClientRect` at `0x1807b24b3`
- `USER32!IsWindow` at `0x1807b2735`
- `USER32!IsWindow` at `0x1807b2735`
- `USER32!GetAncestor` at `0x1807b2339`
- `USER32!GetAncestor` at `0x1807b2339`
- `USER32!GetDC` at `0x1807b24e9`
- `USER32!GetDC` at `0x1807b24e9`
- `USER32!ReleaseDC` at `0x1807b2581`
- `USER32!ReleaseDC` at `0x1807b2581`
- `USER32!ShowWindow` at `0x1807b24e0`
- `USER32!ShowWindow` at `0x1807b24e0`
- `USER32!EqualRect` at `0x1807b24c1`
- `USER32!EqualRect` at `0x1807b24c1`
- `USER32!GetWindow` at `0x1807b2322`
- `USER32!GetWindow` at `0x1807b2322`
- `USER32!SetTimer` at `0x1807b25a0`
- `USER32!SetTimer` at `0x1807b25a0`
- `GDI32!SetTextColor` at `0x1807b26a2`
- `GDI32!SetTextColor` at `0x1807b26a2`

## pseudocode

```c

```
