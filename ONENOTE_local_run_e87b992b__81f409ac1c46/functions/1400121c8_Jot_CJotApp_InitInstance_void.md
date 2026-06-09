# Jot::CJotApp::InitInstance(void)

- ea: `0x1400121c8`
- end: `0x140013fc7`
- name: `?InitInstance@CJotApp@Jot@@AEAA_NXZ`
- size: `7679`
- prototype: `char __fastcall(Jot::CJotApp *this)`
- caller_count: `1`
- callee_count: `58`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140017dcc`

## callees

- `0x140001340`
- `0x1400014b0`
- `0x140001a40`
- `0x1400054d0`
- `0x1400056c0`
- `0x140005740`
- `0x1400057a0`
- `0x14000596c`
- `0x140005c00`
- `0x1400062ec`
- `0x1400063ac`
- `0x1400065cc`
- `0x140006770`
- `0x1400067d0`
- `0x140006b34`
- `0x140006d44`
- `0x140006f90`
- `0x140007030`
- `0x140007518`
- `0x1400106c0`
- `0x140011414`
- `0x140011478`
- `0x140012020`
- `0x140012050`
- `0x140012080`
- `0x1400121c8`
- `0x140014010`
- `0x14001446c`
- `0x140017f40`
- `0x14002b860`
- `0x14002b890`
- `0x14002cac0`
- `0x14002d88c`
- `0x14002e840`
- `0x14002f768`
- `0x14003f250`
- `0x14003f348`
- `0x140040888`
- `0x140045a2c`
- `0x1400478e4`
- `0x140047ac8`
- `0x1400488d0`
- `0x140048a58`
- `0x140048b00`
- `0x140056ac0`
- `0x140057398`
- `0x140057580`
- `0x14007dffc`
- `0x140095f1c`
- `0x14009cde0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140012c18`
- `KERNEL32!GetLastError` at `0x140012c18`
- `KERNEL32!GetProcAddress` at `0x140012291`
- `KERNEL32!GetProcAddress` at `0x140012291`
- `KERNEL32!LocalFree` at `0x1400133d6`
- `KERNEL32!LocalFree` at `0x1400133d6`
- `KERNEL32!FreeLibrary` at `0x1400122a7`
- `KERNEL32!FreeLibrary` at `0x1400122a7`
- `KERNEL32!LoadLibraryExW` at `0x140012279`
- `KERNEL32!LoadLibraryExW` at `0x140012279`
- `KERNEL32!AddAtomW` at `0x1400131e3`
- `KERNEL32!AddAtomW` at `0x1400131f0`
- `KERNEL32!AddAtomW` at `0x1400131e3`
- `KERNEL32!AddAtomW` at `0x1400131f0`
- `onmain!?SetEmpty@CWzInBuffer@Jot@@QEAAXXZ` at `0x1400128d3`
- `onmain!?SetEmpty@CWzInBuffer@Jot@@QEAAXXZ` at `0x1400128d3`
- `onmain!?GetNamespace@OneNote@Office@@YAAEBUTelemetryNamespace@Telemetry@Mso@@XZ` at `0x140012788`
- `onmain!?GetNamespace@OneNote@Office@@YAAEBUTelemetryNamespace@Telemetry@Mso@@XZ` at `0x140012788`
- `onmain!?UseCurrentExecutionContext@FastIntegration@Jot@@YAAEAUIExecutionContext@ApplicationModel@Mso@@XZ` at `0x140013e66`
- `onmain!?UseCurrentExecutionContext@FastIntegration@Jot@@YAAEAUIExecutionContext@ApplicationModel@Mso@@XZ` at `0x140013e66`
- `onmain!?IsMemoryWindowAutoRestoreEnabled@Jot@@YA_N_N@Z` at `0x140012929`
- `onmain!?IsMemoryWindowAutoRestoreEnabled@Jot@@YA_N_N@Z` at `0x140013e32`
- `onmain!?IsMemoryWindowAutoRestoreEnabled@Jot@@YA_N_N@Z` at `0x140012929`
- `onmain!?IsMemoryWindowAutoRestoreEnabled@Jot@@YA_N_N@Z` at `0x140013e32`
- `onmain!?GetNamespace@Boot@OneNote@Office@@YAAEBUTelemetryNamespace@Telemetry@Mso@@XZ` at `0x140012318`
- `onmain!?GetNamespace@Boot@OneNote@Office@@YAAEBUTelemetryNamespace@Telemetry@Mso@@XZ` at `0x140012318`
- `onmain!?JotMain_SetMainThreadID@Jot@@YAXXZ` at `0x1400122d0`
- `onmain!?JotMain_SetMainThreadID@Jot@@YAXXZ` at `0x1400122d0`
- `onmain!?RegisterErrorHandler@MsoCF@@YAXPEAUAErrorHandler@1@@Z` at `0x1400122f6`
- `onmain!?RegisterErrorHandler@MsoCF@@YAXPEAUAErrorHandler@1@@Z` at `0x1400122f6`
- `onmain!?Start@PerfMetrics@MsoCF@@YAXH@Z` at `0x1400123a9`
- `onmain!?Start@PerfMetrics@MsoCF@@YAXH@Z` at `0x1400123a9`
- `onmain!?Activate@PerfMetrics@MsoCF@@YAXXZ` at `0x1400123c8`
- `onmain!?Activate@PerfMetrics@MsoCF@@YAXXZ` at `0x1400123c8`
- `onmain!?CreateTheApp@Frame@MsoCF@@YAXAEAUCreateTheAppArgs@12@@Z` at `0x1400124e6`
- `onmain!?CreateTheApp@Frame@MsoCF@@YAXAEAUCreateTheAppArgs@12@@Z` at `0x1400124e6`
- `onmain!?TheApp@Frame@MsoCF@@YAPEAUAFrameApp@2@XZ` at `0x1400124ec`
- `onmain!?TheApp@Frame@MsoCF@@YAPEAUAFrameApp@2@XZ` at `0x140012518`
- `onmain!?TheApp@Frame@MsoCF@@YAPEAUAFrameApp@2@XZ` at `0x140012ae2`
- `onmain!?TheApp@Frame@MsoCF@@YAPEAUAFrameApp@2@XZ` at `0x140012e98`
- `onmain!?TheApp@Frame@MsoCF@@YAPEAUAFrameApp@2@XZ` at `0x1400124ec`
- `onmain!?TheApp@Frame@MsoCF@@YAPEAUAFrameApp@2@XZ` at `0x140012518`
- `onmain!?TheApp@Frame@MsoCF@@YAPEAUAFrameApp@2@XZ` at `0x140012ae2`
- `onmain!?TheApp@Frame@MsoCF@@YAPEAUAFrameApp@2@XZ` at `0x140012e98`
- `onmain!?Start@Frame@MsoCF@@YAXXZ` at `0x140012a04`
- `onmain!?Start@Frame@MsoCF@@YAXXZ` at `0x140012a04`
- `onmain!?IsTellMeMemorySearchInWin32Enabled@Jot@@YA_NXZ` at `0x140012e5b`
- `onmain!?IsTellMeMemorySearchInWin32Enabled@Jot@@YA_NXZ` at `0x140012e5b`
- `onmain!?IsOneNoteSubstrateV2QueryEnabled@Jot@@YAAEBVFeatureGate@Optimized@AB@Mso@@XZ` at `0x140012e6a`
- `onmain!?IsOneNoteSubstrateV2QueryEnabled@Jot@@YAAEBVFeatureGate@Optimized@AB@Mso@@XZ` at `0x140012e6a`
- `onmain!?FGetMyDocumentsFolder@Jot@@YA_NPEAPEAUIFolderProxy@1@@Z` at `0x140012f30`
- `onmain!?FGetMyDocumentsFolder@Jot@@YA_NPEAPEAUIFolderProxy@1@@Z` at `0x140012f30`
- `onmain!?Init@ExeServer@Jot@@YAXPEAVIJotHostComModule@ATLUtils@2@PEAUHINSTANCE__@@@Z` at `0x1400131b8`
- `onmain!?Init@ExeServer@Jot@@YAXPEAVIJotHostComModule@ATLUtils@2@PEAUHINSTANCE__@@@Z` at `0x1400131b8`
- `onmain!?CreateMainApp@Jot@@YAPEAUAMainApp@1@PEAUIActionManager@MsoCF@@PEAUIKeyMapMan@4@PEAUAMainAppUser@1@AEAV?$TOwnerPtrList@UMSOSTARTUPACTION@@@Ofc@@_NAEAVIBootStatus@1@KPEA_N@Z` at `0x14001336f`
- `onmain!?CreateMainApp@Jot@@YAPEAUAMainApp@1@PEAUIActionManager@MsoCF@@PEAUIKeyMapMan@4@PEAUAMainAppUser@1@AEAV?$TOwnerPtrList@UMSOSTARTUPACTION@@@Ofc@@_NAEAVIBootStatus@1@KPEA_N@Z` at `0x14001336f`
- `onmain!?Start@ExeServer@Jot@@YAXXZ` at `0x1400139d0`
- `onmain!?Start@ExeServer@Jot@@YAXXZ` at `0x1400139d0`
- `onmain!?RegisterEDPRevokeEvent@EDP@Jot@@YA?AUEventRegistrationToken@@XZ` at `0x140013dde`
- `onmain!?RegisterEDPRevokeEvent@EDP@Jot@@YA?AUEventRegistrationToken@@XZ` at `0x140013dde`
- `onmain!?UsePremiumFeatureEnablement@PremiumFeatureEnablement@Flighting@OneNote@@YAAEAUAPremiumFeatureEnablement@123@XZ` at `0x140013e05`
- `onmain!?UsePremiumFeatureEnablement@PremiumFeatureEnablement@Flighting@OneNote@@YAAEAUAPremiumFeatureEnablement@123@XZ` at `0x140013e05`
- `onmain!?IsPreventMemoryWindowAutoRestoreOnOneNoteLaunchEnabled@Jot@@YA_NXZ` at `0x140013e47`
- `onmain!?IsPreventMemoryWindowAutoRestoreOnOneNoteLaunchEnabled@Jot@@YA_NXZ` at `0x140013e47`
- `onmain!?RegisterPropertySpace@MsoCF@@YAXPEBUPropertySpaceInfo@1@@Z` at `0x140012e92`
- `onmain!?RegisterPropertySpace@MsoCF@@YAXPEBUPropertySpaceInfo@1@@Z` at `0x140012e92`
- `onmain!?Mark@PerfMetrics@MsoCF@@YAXH@Z` at `0x140013f5a`
- `onmain!?Mark@PerfMetrics@MsoCF@@YAXH@Z` at `0x140013f5a`
- `onmain!?Instance@CLangConfig@MsoCF@@SAPEAV12@XZ` at `0x140013a7f`
- `onmain!?Instance@CLangConfig@MsoCF@@SAPEAV12@XZ` at `0x140013a7f`
- `onmain!?CopyWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z` at `0x1400128cb`
- `onmain!?CopyWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z` at `0x1400128cb`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x14001290a`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x14001290a`
- `onmain!?IsServerSku@System@Jot@@YA_NXZ` at `0x14001296f`
- `onmain!?IsServerSku@System@Jot@@YA_NXZ` at `0x14001296f`
- `MSVCP140!_Xtime_get_ticks` at `0x1400123ce`
- `MSVCP140!_Xtime_get_ticks` at `0x1400123ce`
- `ADVAPI32!RegOpenKeyExW` at `0x14001299f`
- `ADVAPI32!RegOpenKeyExW` at `0x14001299f`
- `ADVAPI32!RegCloseKey` at `0x1400129e7`
- `ADVAPI32!RegCloseKey` at `0x1400129e7`
- `ole32!OleInitialize` at `0x1400123ed`
- `ole32!OleInitialize` at `0x1400123ed`
- `ole32!CoCreateGuid` at `0x140012fce`
- `ole32!CoCreateGuid` at `0x140012fce`
- `USER32!GetAsyncKeyState` at `0x140012259`
- `USER32!GetAsyncKeyState` at `0x140012259`
- `USER32!SendMessageW` at `0x140012b54`
- `USER32!SendMessageW` at `0x140012c09`
- `USER32!SendMessageW` at `0x140012b54`
- `USER32!SendMessageW` at `0x140012c09`
- `USER32!GetDesktopWindow` at `0x140012db8`
- `USER32!GetDesktopWindow` at `0x140012db8`
- `USER32!SetThreadDpiAwarenessContext` at `0x14001223b`
- `USER32!SetThreadDpiAwarenessContext` at `0x14001223b`
- `MSO!__imp_?MsoFShowSplash@@YAHPEBUMsoSplashParams@@@Z` at `0x140012e4d`
- `MSO!__imp_?MsoFShowSplash@@YAHPEBUMsoSplashParams@@@Z` at `0x140012e4d`
- `MSO!__imp_?MsoRegisterAWSUser@@YAXPEAUIMsoAWSUser@@@Z` at `0x14001342e`
- `MSO!__imp_?MsoRegisterAWSUser@@YAXPEAUIMsoAWSUser@@@Z` at `0x14001342e`
- `MSO!__imp_?MsoInitDigSigEx@@YAXPEBUIMsoDigSigUser@@PEBXH_N2@Z` at `0x140013df3`
- `MSO!__imp_?MsoInitDigSigEx@@YAXPEBUIMsoDigSigUser@@PEBXH_N2@Z` at `0x140013df3`
- `MSO!__imp_MsoFForceAcbInit` at `0x140013db8`
- `MSO!__imp_MsoFForceAcbInit` at `0x140013db8`
- `MSO!__imp_?MsoBfileLimit@@YAXH@Z` at `0x140013dc0`
- `MSO!__imp_?MsoBfileLimit@@YAXH@Z` at `0x140013dc0`
- `Mso98Win32Client!__imp_?MsoFInitializeCtxUIManager@@YA_NPEAUIMsoCtxUIUser@@@Z` at `0x140012e55`
- `Mso98Win32Client!__imp_?MsoFInitializeCtxUIManager@@YA_NPEAUIMsoCtxUIUser@@@Z` at `0x140012e55`
- `Mso98Win32Client!__imp_?SetGlobalOption@OLDocApi@Mso@@YAXK@Z` at `0x1400129f2`
- `Mso98Win32Client!__imp_?SetGlobalOption@OLDocApi@Mso@@YAXK@Z` at `0x1400129f2`
- `Mso98Win32Client!__imp_?MsoFFirstRun@@YAHPEAUMSOINST@@@Z` at `0x140012f08`
- `Mso98Win32Client!__imp_?MsoFFirstRun@@YAHPEAUMSOINST@@@Z` at `0x140012f08`
- `Mso98Win32Client!__imp_?MsoInitGimme@@YAXHPEBU_msotcfcf@@PEAUIMsoGimmeUser@@@Z` at `0x140012418`
- `Mso98Win32Client!__imp_?MsoInitGimme@@YAXHPEBU_msotcfcf@@PEAUIMsoGimmeUser@@@Z` at `0x140012418`
- `Mso98Win32Client!__imp_?MsoHrRegisterOfficeCenterUser@@YAJPEAUMSOINST@@PEAUIMsoOfficeCenterUser@@@Z` at `0x140013c8d`
- `Mso98Win32Client!__imp_?MsoHrRegisterOfficeCenterUser@@YAJPEAUMSOINST@@PEAUIMsoOfficeCenterUser@@@Z` at `0x140013c8d`
- `Mso98Win32Client!__imp_?MsoMigrate@@YAHHPEAK@Z` at `0x140012a1e`
- `Mso98Win32Client!__imp_?MsoMigrate@@YAHHPEAK@Z` at `0x140012a1e`
- `mso40uiWin32Client!__imp_?MsoDestroyStartup@@YAXXZ` at `0x140013cb3`
- `mso40uiWin32Client!__imp_?MsoDestroyStartup@@YAXXZ` at `0x140013cb3`
- `mso40uiWin32Client!__imp_?MsoThemeHaveManifest@@YAXH@Z` at `0x140012421`
- `mso40uiWin32Client!__imp_?MsoThemeHaveManifest@@YAXH@Z` at `0x140012421`
- `Mso30Win32Client!__imp_?MsoSetUnhandledExceptionFilter@@YAP6AJPEAU_EXCEPTION_POINTERS@@@ZP6AJ0@Z@Z` at `0x1400122dd`
- `Mso30Win32Client!__imp_?MsoSetUnhandledExceptionFilter@@YAP6AJPEAU_EXCEPTION_POINTERS@@@ZP6AJ0@Z@Z` at `0x1400122dd`
- `Mso30Win32Client!__imp_?MsoAlertIds@@YAHPEAUHINSTANCE__@@HHPEAUHWND__@@@Z` at `0x1400129c5`
- `Mso30Win32Client!__imp_?MsoAlertIds@@YAHPEAUHINSTANCE__@@HHPEAUHWND__@@@Z` at `0x140012cfd`
- `Mso30Win32Client!__imp_?MsoAlertIds@@YAHPEAUHINSTANCE__@@HHPEAUHWND__@@@Z` at `0x1400130f4`
- `Mso30Win32Client!__imp_?MsoAlertIds@@YAHPEAUHINSTANCE__@@HHPEAUHWND__@@@Z` at `0x14001328a`
- `Mso30Win32Client!__imp_?MsoAlertIds@@YAHPEAUHINSTANCE__@@HHPEAUHWND__@@@Z` at `0x1400129c5`
- `Mso30Win32Client!__imp_?MsoAlertIds@@YAHPEAUHINSTANCE__@@HHPEAUHWND__@@@Z` at `0x140012cfd`
- `Mso30Win32Client!__imp_?MsoAlertIds@@YAHPEAUHINSTANCE__@@HHPEAUHWND__@@@Z` at `0x1400130f4`
- `Mso30Win32Client!__imp_?MsoAlertIds@@YAHPEAUHINSTANCE__@@HHPEAUHWND__@@@Z` at `0x14001328a`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x140013452`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x140013468`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x1400134d8`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x1400134f2`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x140013566`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x14001357c`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x1400135ef`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x140013605`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x140013678`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x14001368e`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x140013704`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x14001371a`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x14001378d`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x1400137a3`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x140013814`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x14001382a`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x140013896`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x1400138ac`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x140013452`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x140013468`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x1400134d8`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x1400134f2`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x140013566`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x14001357c`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x1400135ef`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x140013605`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x140013678`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x14001368e`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x140013704`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x14001371a`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x14001378d`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x1400137a3`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x140013814`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x14001382a`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x140013896`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x1400138ac`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x140012856`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x140012875`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x140012898`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x1400128f3`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x14001291d`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x140012856`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x140012875`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x140012898`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x1400128f3`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x14001291d`
- `Mso30Win32Client!__imp_?MsoUIBootCheck@@YAHXZ` at `0x140013246`
- `Mso30Win32Client!__imp_?MsoUIBootCheck@@YAHXZ` at `0x140013246`
- `Mso30Win32Client!__imp_?MsoAddFormatChangeListener@Clipboard@Mso@@YA_NPEAUHWND__@@@Z` at `0x140013cad`
- `Mso30Win32Client!__imp_?MsoAddFormatChangeListener@Clipboard@Mso@@YA_NPEAUHWND__@@@Z` at `0x140013cad`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x140012547`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x140013f91`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x140012547`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x140013f91`
- `Mso20Win32Client!__imp_?GetAPI@Sqm@Mso@@YAAEAUISqmApi@12@XZ` at `0x140012a6c`
- `Mso20Win32Client!__imp_?GetAPI@Sqm@Mso@@YAAEAUISqmApi@12@XZ` at `0x140012a6c`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x140012431`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x140013b18`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x140012431`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x140013b18`
- `Mso20Win32Client!__imp_?MsoDisableSqmThisSession@@YAXXZ` at `0x140012d31`
- `Mso20Win32Client!__imp_?MsoDisableSqmThisSession@@YAXXZ` at `0x140012d31`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x140012a62`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x140012d27`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x140012a62`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x140012d27`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140012353`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140012353`

## string_xrefs

- `0x140012272`: `user32.dll`
- `0x140012574`: `IsDPIAwarenessRegSet`
- `0x140012991`: `CLSID\{937C1A34-151D-4610-9CA6-A8CC9BDB5D83}`
- `0x140012cc4`: `/openro`
- `0x140012302`: `/sidenote`
- `0x1400131fc`: `/sidenote`
- `0x140012371`: `/hyperlink`
- `0x14001284b`: `/hyperlink`
- `0x140012cab`: `/hyperlink`
- `0x140012b99`: ` /createnewpage`

## pseudocode

```c
char __fastcall Jot::CJotApp::InitInstance(Jot::CJotApp *this)
{
  Jot::CJotApp *v1; // r15
  Jot::DPIAwareness *v2; // rcx
  __int64 v3; // rcx
  bool v4; // si
  char v5; // r13
  bool v6; // di
  HMODULE Library; // rax
  HMODULE v8; // rsi
  FARPROC ProcAddress; // rax
  Jot *v10; // rcx
  __int64 v11; // rcx
  Mso::CrashDetails *v12; // rcx
  Mso::CrashDetails *v13; // rcx
  struct MsoCF::AErrorHandler *v14; // rdx
  bool v15; // si
  Office::OneNote::Boot *v16; // rcx
  struct Mso::Telemetry::IDataFieldCollection *v17; // rax
  __int64 v18; // r8
  int v19; // edx
  MsoCF::PerfMetrics *v20; // rcx
  __int64 ticks; // rax
  HRESULT v22; // eax
  struct MsoCF::Frame::CreateTheAppArgs *v23; // rdx
  MsoCF::Frame *v24; // rcx
  struct MsoCF::AFrameApp *v25; // rax
  MsoCF::Frame *v26; // rcx
  struct MsoCF::AFrameApp *v27; // rax
  __int64 v29; // rax
  void **v30; // r14
  const WCHAR *v31; // rcx
  Jot *v32; // rsi
  const WCHAR *v33; // rax
  __int64 v34; // rax
  void **v35; // rdi
  _QWORD *v36; // rcx
  __int64 v37; // rax
  Office::OneNote *v38; // rcx
  Jot::System *v39; // rcx
  int *v40; // r8
  wchar_t **v41; // rax
  int v42; // edi
  __int64 i; // rsi
  __int64 v44; // rax
  bool v45; // dl
  void *v46; // rdx
  Jot *v47; // rcx
  unsigned int v48; // edx
  Jot *v49; // rcx
  int v50; // edx
  Jot::DPIAwareness *v51; // rcx
  bool v52; // dl
  MsoCF::Frame *v53; // rcx
  unsigned __int64 v54; // rdx
  Jot *v55; // rcx
  unsigned int v56; // r8d
  bool v57; // al
  struct Mso::Sqm::ISqmApi *API; // rax
  Jot::CJotSingleApp *v59; // rax
  __int64 v60; // rax
  __int64 v61; // rdi
  MsoCF::Frame *v62; // rcx
  struct MsoCF::AFrameApp *v63; // rax
  __int64 v64; // rax
  __int64 v65; // r8
  int started; // eax
  bool v67; // zf
  bool v68; // sf
  HKEY v69; // rdi
  GUID *p_pguid; // rax
  const wchar_t *v71; // r8
  bool v72; // di
  int v73; // r14d
  __int64 v74; // r13
  int v75; // edx
  bool v76; // al
  bool v77; // si
  __int64 v78; // rcx
  HWND DesktopWindow; // rax
  unsigned __int64 v80; // rdx
  unsigned int v81; // r8d
  void **v82; // rax
  Jot *v83; // rcx
  Jot *v84; // rcx
  Mso::AB::Optimized::FeatureGate *Enabled; // rax
  const struct MsoCF::PropertySpaceInfo *v86; // rdx
  Jot *v87; // rcx
  bool v88; // al
  MsoCF::Frame *v89; // rcx
  struct MsoCF::AFrameApp *v90; // rax
  struct MSOINST *MsoInstance; // rax
  Jot *v92; // rcx
  struct Jot::IFolderProxy **v93; // rdx
  __int64 v94; // rax
  HKEY v95; // rdi
  __int64 (__fastcall *v96)(HKEY, Jot::CJotSingleApp **, void ***, _QWORD, int, int, char, _BYTE, const char **, __int64 *); // r14
  HRESULT v97; // eax
  void ***p_Src; // r8
  char **v99; // rax
  char *v100; // rdi
  HKEY v101; // rcx
  bool v102; // al
  HINSTANCE v103; // r8
  Jot *v104; // rcx
  unsigned __int64 v105; // rdx
  unsigned int v106; // r8d
  Jot::CDialogManager *v107; // rax
  __int64 v108; // rax
  void (*v109)(void); // rax
  Jot::CDialogManager *v110; // rdi
  Jot::CJotApp *v111; // rcx
  unsigned int v112; // esi
  char v113; // r14
  __int64 v114; // rdi
  __int64 v115; // rax
  __int64 v116; // rax
  void (__fastcall ***v117)(_QWORD); // rcx
  void *v118; // rcx
  __int64 Instance; // rax
  __int64 v120; // rdi
  __int64 v121; // rcx
  __int64 v122; // rsi
  void (__fastcall *v123)(__int64, __int64, const struct MsoCF::KeyMapEntry near *const *, __int64, int, __int64, const wchar_t *, int, _DWORD); // r14
  const wchar_t *v124; // rdi
  __int64 v125; // rax
  __int64 v126; // rsi
  __int64 v127; // rsi
  __int64 v128; // rsi
  __int64 v129; // rsi
  __int64 v130; // rsi
  __int64 v131; // rsi
  const wchar_t *v132; // rdi
  __int64 v133; // rax
  __int64 v134; // rsi
  const wchar_t *v135; // rdi
  __int64 v136; // rax
  __int64 v137; // rsi
  void (__fastcall *v138)(__int64, __int64, const char *, __int64, int, __int64, const wchar_t *, int, _DWORD); // r14
  const wchar_t *v139; // rdi
  __int64 v140; // rax
  __int64 v141; // rax
  __int64 v142; // rax
  __int64 v143; // rax
  __int64 v144; // rax
  Jot::ExeServer *v145; // rcx
  unsigned int v146; // r8d
  void *v147; // rax
  __int64 (__fastcall ***v148)(); // rcx
  bool v149; // si
  unsigned int v150; // r14d
  char v151; // di
  unsigned int v152; // eax
  char v153; // cl
  __int64 v154; // r10
  __int64 v155; // r10
  unsigned __int64 v156; // rdx
  unsigned int v157; // r8d
  _QWORD *v158; // rax
  _QWORD *v159; // rdi
  char *v160; // rcx
  __int64 v161; // rcx
  struct IMsoOfficeCenterUser *v162; // rdi
  struct MSOINST *v163; // rax
  Mso::Clipboard *v164; // rax
  HWND v165; // rdx
  __int64 v166; // rdx
  __int64 v167; // r10
  __int64 v168; // rax
  __int64 v169; // r10
  Jot::EDP *v170; // rcx
  OneNote::Flighting::PremiumFeatureEnablement *v171; // rcx
  struct OneNote::Flighting::PremiumFeatureEnablement::APremiumFeatureEnablement *v172; // rax
  bool v173; // dl
  Jot *v174; // rcx
  Jot::FastIntegration *v175; // rcx
  struct Mso::ApplicationModel::IExecutionContext *v176; // rax
  __int64 v177; // rax
  __int64 (__fastcall ***v178)(); // rcx
  void **v179; // rax
  int v180; // edx
  __int64 (__fastcall ***v181)(); // rbx
  const WCHAR *v182; // rbx
  const WCHAR *v183; // rax
  int phkResult; // [rsp+20h] [rbp-698h]
  int v185; // [rsp+28h] [rbp-690h]
  int v186; // [rsp+28h] [rbp-690h]
  int v187; // [rsp+28h] [rbp-690h]
  int v188; // [rsp+28h] [rbp-690h]
  int v189; // [rsp+28h] [rbp-690h]
  int v190; // [rsp+30h] [rbp-688h]
  int v191; // [rsp+30h] [rbp-688h]
  int v192; // [rsp+30h] [rbp-688h]
  int v193; // [rsp+30h] [rbp-688h]
  int v194; // [rsp+38h] [rbp-680h]
  int v195; // [rsp+38h] [rbp-680h]
  int v196; // [rsp+38h] [rbp-680h]
  int v197; // [rsp+38h] [rbp-680h]
  int v198; // [rsp+38h] [rbp-680h]
  int v199; // [rsp+38h] [rbp-680h]
  int v200; // [rsp+38h] [rbp-680h]
  int v201; // [rsp+38h] [rbp-680h]
  int v202; // [rsp+40h] [rbp-678h]
  int v203; // [rsp+40h] [rbp-678h]
  int v204; // [rsp+40h] [rbp-678h]
  bool v205; // [rsp+60h] [rbp-658h] BYREF
  bool v206; // [rsp+64h] [rbp-654h] BYREF
  char v207; // [rsp+65h] [rbp-653h]
  _BYTE v208[2]; // [rsp+68h] [rbp-650h] BYREF
  __int16 v209; // [rsp+6Ah] [rbp-64Eh] BYREF
  char v210; // [rsp+6Ch] [rbp-64Ch] BYREF
  bool v211; // [rsp+6Dh] [rbp-64Bh]
  Jot::CJotSingleApp *v212; // [rsp+70h] [rbp-648h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-640h] BYREF
  unsigned int Dw; // [rsp+80h] [rbp-638h] BYREF
  __int64 (__fastcall ***v215)(); // [rsp+88h] [rbp-630h] BYREF
  _BYTE v216[2]; // [rsp+90h] [rbp-628h] BYREF
  _BYTE v217[2]; // [rsp+92h] [rbp-626h] BYREF
  unsigned int v218; // [rsp+94h] [rbp-624h] BYREF
  __int64 v219; // [rsp+98h] [rbp-620h] BYREF
  const char *v220; // [rsp+A0h] [rbp-618h] BYREF
  char *v221; // [rsp+A8h] [rbp-610h] BYREF
  int v222; // [rsp+B0h] [rbp-608h] BYREF
  _BYTE v223[11]; // [rsp+B8h] [rbp-600h] BYREF
  char v224; // [rsp+C3h] [rbp-5F5h]
  _BYTE v225[16]; // [rsp+C8h] [rbp-5F0h] BYREF
  __int64 v226; // [rsp+D8h] [rbp-5E0h] BYREF
  int v227; // [rsp+E0h] [rbp-5D8h] BYREF
  _QWORD v228[2]; // [rsp+E8h] [rbp-5D0h] BYREF
  _QWORD v229[3]; // [rsp+F8h] [rbp-5C0h] BYREF
  _QWORD v230[6]; // [rsp+110h] [rbp-5A8h] BYREF
  __int16 v231; // [rsp+140h] [rbp-578h]
  __int64 v232; // [rsp+148h] [rbp-570h]
  void *v233; // [rsp+150h] [rbp-568h]
  char v234; // [rsp+158h] [rbp-560h]
  int v235; // [rsp+15Ch] [rbp-55Ch]
  __int16 v236; // [rsp+160h] [rbp-558h]
  int v237; // [rsp+164h] [rbp-554h]
  int v238; // [rsp+168h] [rbp-550h]
  char v239; // [rsp+16Ch] [rbp-54Ch]
  Ofc::CAbortException *v240; // [rsp+170h] [rbp-548h] BYREF
  void **Src; // [rsp+180h] [rbp-538h] BYREF
  void **v242; // [rsp+188h] [rbp-530h]
  __int64 v243; // [rsp+190h] [rbp-528h] BYREF
  unsigned __int64 v244; // [rsp+198h] [rbp-520h]
  _BYTE v245[24]; // [rsp+1A0h] [rbp-518h] BYREF
  __int64 *v246; // [rsp+1C8h] [rbp-4F0h]
  GUID pguid; // [rsp+1D0h] [rbp-4E8h] BYREF
  const WCHAR *v248; // [rsp+1E0h] [rbp-4D8h]
  unsigned __int64 v249; // [rsp+1E8h] [rbp-4D0h]
  bool *v250; // [rsp+1F0h] [rbp-4C8h]
  __int16 v251; // [rsp+1F8h] [rbp-4C0h]
  const WCHAR *v252; // [rsp+200h] [rbp-4B8h] BYREF
  LPARAM lParam[2]; // [rsp+210h] [rbp-4A8h] BYREF
  GUID *v254; // [rsp+220h] [rbp-498h]
  _BYTE v255[32]; // [rsp+230h] [rbp-488h] BYREF
  char v256[40]; // [rsp+250h] [rbp-468h] BYREF
  Mso::Memory *v257; // [rsp+278h] [rbp-440h]
  char v258; // [rsp+290h] [rbp-428h] BYREF
  _BYTE v259[368]; // [rsp+3A0h] [rbp-318h] BYREF
  _BYTE v260[368]; // [rsp+510h] [rbp-1A8h] BYREF

  v1 = this;
  v215 = (__int64 (__fastcall ***)())this;
  Jot::DPIAwareness::GetDPIRegKeySetting(&v206);
  v4 = Jot::DPIAwareness::DisableDDPIBasedOnUserRegkeySetting(v2);
  v5 = v207;
  v6 = v206;
  if ( ((unsigned __int8)-(v207 != 0) & v206) != 0 )
  {
    LOBYTE(v3) = -v207;
    if ( (unsigned __int8)sub_140001A40(v3) )
    {
      if ( !v4 )
      {
        SetThreadDpiAwarenessContext(-4);
        *((_BYTE *)v1 + 320) = 1;
      }
    }
  }
  *((_BYTE *)v1 + 308) = GetAsyncKeyState(17) < 0;
  Library = LoadLibraryExW(L"user32.dll", 0, 0x1000u);
  v8 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "EnableMouseInPointer");
    if ( ProcAddress )
      ((void (__fastcall *)(_QWORD))ProcAddress)(0);
    FreeLibrary(v8);
  }
  if ( !Mso::LoadMso::DllData::Load((Mso::LoadMso::DllData *)&qword_140259EA8, 0) )
  {
    DisplayAppNotConfiguredMsg();
    Ofc::CAbortException::ThrowTag(v11, 42849866);
    __debugbreak();
  }
  Jot::JotMain_SetMainThreadID(v10);
  MsoSetUnhandledExceptionFilter((int (*)(struct _EXCEPTION_POINTERS *))Jot::JotUnhandledExceptionFilter);
  Mso::CrashDetails::EnableCrashRecoveryOnPureCall(v12);
  Mso::CrashDetails::EnableCrashRecoveryOnInvalidParameter(v13);
  MsoCF::RegisterErrorHandler((Jot::CJotApp *)((char *)v1 + 264), v14);
  v15 = Jot::CJotApp::FQueryCommandLineFlag(v1, L"/sidenote", 0, 0);
  v211 = v15;
  v228[0] = Office::OneNote::Boot::GetNamespace(v16);
  v228[1] = "InitInstance";
  Mso::Telemetry::Activity::Activity((Mso::Telemetry::Activity *)v225, (const struct Mso::Telemetry::EventName *)v228);
  v17 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v225);
  LOBYTE(v18) = v15;
  Mso::Telemetry::IDataFieldCollection::Add<bool>(v17, "QuickNote", v18);
  if ( Jot::CJotApp::FQueryCommandLineFlag(v1, L"/hyperlink", 0, 0)
    || Jot::CJotApp::FQueryCommandLineFlag(v1, L"/oneindex", 0, 0) )
  {
    *((_BYTE *)v1 + 308) = 0;
  }
  MsoCF::PerfMetrics::Start((MsoCF::PerfMetrics *)0x14, v19);
  if ( !Jot::CJotApp::FQueryCommandLineFlag(v1, L"/markersoff", 0, 0) )
    MsoCF::PerfMetrics::Activate(v20);
  ticks = _Xtime_get_ticks();
  if ( !*((_BYTE *)v1 + 336) )
    *((_BYTE *)v1 + 336) = 1;
  *((_QWORD *)v1 + 41) = ticks;
  v22 = OleInitialize(0);
  if ( v22 < 0 )
  {
    CrashWithRecoveryHrTag(v22, 0x28DD64Bu);
    __debugbreak();
  }
  MsoInitGimme(851968, (const struct _msotcfcf *)&vfcf, (Jot::CJotApp *)((char *)v1 + 560));
  MsoThemeHaveManifest(1);
  Dw = MsoDwRegGetDw((const struct _msoreg *)&vmsoridOneNoteLastUILang);
  v231 = 0;
  v232 = 0;
  v237 = -2;
  v230[0] = *((_QWORD *)v1 + 34);
  v230[1] = (char *)v1 + 8;
  v230[2] = v1;
  v230[3] = L"Microsoft OneNote";
  v230[4] = L"OneNote";
  v230[5] = &vmsoridCUBrandOneNoteName;
  v233 = &vmsoridOneNoteLastUILang;
  v234 = 1;
  v235 = 12;
  v236 = 256;
  v238 = 1;
  v239 = 1;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    MsoCF::Frame::CreateTheApp((MsoCF::Frame *)v230, v23);
    v25 = MsoCF::Frame::TheApp(v24);
    (*(void (__fastcall **)(struct MsoCF::AFrameApp *, _QWORD *))(*(_QWORD *)v25 + 240LL))(v25, v230);
    Jot::CJotApp::InitPluggableUI(v1);
    v27 = MsoCF::Frame::TheApp(v26);
    (*(void (__fastcall **)(struct MsoCF::AFrameApp *, _QWORD *))(*(_QWORD *)v27 + 248LL))(v27, v230);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &Ofc::CAbortException `RTTI Type Descriptor', &v240) )
    {
      if ( *((_DWORD *)v240 + 2) == 2 )
      {
        MsoShipAssertTagProc(42849868);
        v181 = v215;
        if ( v215[62] )
        {
          Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(
            v260,
            v215[62],
            3560628973LL);
          Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(
            v259,
            v181[62],
            349579406);
          v182 = (const WCHAR *)Jot::CWzInBuffer::operator wchar_t *(v259);
          v183 = (const WCHAR *)Jot::CWzInBuffer::operator wchar_t *(v260);
          MessageBoxW(0, v183, v182, 0);
          Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(v259);
          Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(v260);
        }
        __eh34_try_continuation(0, &Ofc::CAbortException `RTTI Type Descriptor', &loc_14001253F);
        goto LABEL_21;
      }
      v6 = v206;
      v5 = v207;
      v1 = (Jot::CJotApp *)v215;
      __eh34_try_continuation(0, &Ofc::CAbortException `RTTI Type Descriptor', &loc_140012554);
    }
  }
  v206 = v5 != 0;
  v220 = "IsDPIAwarenessRegSet";
  v221 = "";
  v29 = std::make_unique<std::wstring const,char const * &,char const *,0>(&v212, &v220, &v221);
  v30 = (void **)v29;
  v31 = *(const WCHAR **)v29;
  if ( *(_QWORD *)(*(_QWORD *)v29 + 24LL) > 7u )
    v31 = *(const WCHAR **)v31;
  v32 = (Jot *)&psz;
  if ( v31 )
  {
    v248 = v31;
    v249 = -1;
  }
  else
  {
    v248 = &psz;
    v249 = 0;
  }
  v250 = &v206;
  v251 = 4;
  *(_QWORD *)&pguid.Data1 = &Jot::Logging::details::StructuredTraceKeyHolder<Jot::Logging::details::StructuredTraceImplementation<bool>,bool>::`vftable'{for `Mso::Logging::IStructuredTrace'};
  *(_QWORD *)pguid.Data4 = &Jot::Logging::details::StructuredTraceKeyHolder<Jot::Logging::details::StructuredTraceImplementation<bool>,bool>::`vftable'{for `Mso::Telemetry::IDataField'};
  v33 = *(const WCHAR **)v29;
  *v30 = 0;
  v252 = v33;
  if ( *v30 )
    std::wstring::`scalar deleting destructor'(*v30);
  *v30 = (void *)19937;
  v205 = v5 != 0 && v6;
  v220 = "IsDPIAwarenessEnabled";
  v221 = "";
  v34 = std::make_unique<std::wstring const,char const * &,char const *,0>(&v212, &v220, &v221);
  v35 = (void **)v34;
  v36 = *(_QWORD **)v34;
  if ( *(_QWORD *)(*(_QWORD *)v34 + 24LL) > 7u )
    v36 = (_QWORD *)*v36;
  if ( v36 )
  {
    v243 = (__int64)v36;
    v244 = -1;
  }
  else
  {
    v243 = (__int64)&psz;
    v244 = 0;
  }
  *(_QWORD *)v245 = &v205;
  *(_WORD *)&v245[8] = 4;
  Src = &Jot::Logging::details::StructuredTraceKeyHolder<Jot::Logging::details::StructuredTraceImplementation<bool>,bool>::`vftable'{for `Mso::Logging::IStructuredTrace'};
  v242 = &Jot::Logging::details::StructuredTraceKeyHolder<Jot::Logging::details::StructuredTraceImplementation<bool>,bool>::`vftable'{for `Mso::Telemetry::IDataField'};
  v37 = *(_QWORD *)v34;
  *v35 = 0;
  *(_QWORD *)&v245[16] = v37;
  if ( *v35 )
    std::wstring::`scalar deleting destructor'(*v35);
  *v35 = (void *)19937;
  v208[1] = 0;
  LOWORD(hKey) = 2;
  BYTE2(hKey) = 1;
  v216[1] = 0;
  v217[1] = 0;
  v209 = 257;
  Mso::Telemetry::EventFlags::EventFlags(&v226, &v209, v217, v216, &hKey, v208);
  v229[0] = Office::OneNote::GetNamespace(v38);
  v229[1] = "SetAppToDPIAwareState";
  Jot::Logging::SendTelemetryEvent<Jot::Logging::details::StructuredTraceKeyHolder<Jot::Logging::details::StructuredTraceImplementation<bool>,bool>,Jot::Logging::details::StructuredTraceKeyHolder<Jot::Logging::details::StructuredTraceImplementation<bool>,bool>>(
    v229,
    &v226,
    &Src,
    &pguid);
  std::unique_ptr<std::wstring const>::~unique_ptr<std::wstring const,std::default_delete<std::wstring const>>(&v245[16]);
  std::unique_ptr<std::wstring const>::~unique_ptr<std::wstring const,std::default_delete<std::wstring const>>(&v252);
  LOBYTE(v209) = 0;
  Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(v255);
  if ( *((_QWORD *)v1 + 37) )
    goto LABEL_40;
  if ( *((_QWORD *)v1 + 36) )
    v32 = (Jot *)*((_QWORD *)v1 + 36);
  v41 = Jot::CommandLineToArgvW(v32, (const wchar_t *)v1 + 152, v40);
  *((_QWORD *)v1 + 37) = v41;
  if ( v41 )
  {
LABEL_40:
    v42 = 0;
    for ( i = 0; ; i += 8 )
    {
      if ( v42 >= *((_DWORD *)v1 + 76) )
        goto LABEL_56;
      if ( (unsigned int)MsoFWzEqual(*(_QWORD *)(*((_QWORD *)v1 + 37) + i), L"/hyperlink", 1)
        || (unsigned int)MsoFWzEqual(*(_QWORD *)(*((_QWORD *)v1 + 37) + i), L"/oneindex", 1) )
      {
        break;
      }
      if ( (unsigned int)MsoFWzEqual(*(_QWORD *)(*((_QWORD *)v1 + 37) + i), L"/memoryWindow", 1) )
      {
        if ( v42 + 1 >= *((_DWORD *)v1 + 76) )
          Jot::CWzInBuffer::SetEmpty((Jot::CWzInBuffer *)v255);
        else
          Jot::CWzInBuffer::CopyWz((Jot::CWzInBuffer *)v255, *(const wchar_t **)(*((_QWORD *)v1 + 37) + 8LL * v42 + 8));
LABEL_50:
        LOBYTE(v209) = 1;
        v44 = Jot::CWzInBuffer::operator wchar_t *(v255);
        if ( !(unsigned int)MsoFWzEqual(v44, L"autoRestore", 1)
          || Jot::IsMemoryWindowAutoRestoreEnabled(0, v45) && Jot::HasAnyMemoryWindowToRestore(v47) )
        {
          goto LABEL_56;
        }
        if ( v257 != (Mso::Memory *)&v258 )
          Mso::Memory::Free(v257, v46);
        std::wstring::~wstring(v256);
        goto LABEL_21;
      }
      ++v42;
    }
    if ( !(unsigned int)MsoFWzEqual(*(_QWORD *)(*((_QWORD *)v1 + 37) + 8LL * v42), L"/memoryWindow", 1) )
      goto LABEL_56;
    goto LABEL_50;
  }
LABEL_56:
  if ( Jot::System::IsServerSku(v39) )
  {
    hKey = 0;
    if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID\\{937C1A34-151D-4610-9CA6-A8CC9BDB5D83}", 0, 0x20019u, &hKey)
      && !Jot::IsDesktopExperienceInstalled(v49) )
    {
      v50 = -90482553;
LABEL_60:
      MsoAlertIds(*((HINSTANCE *)v1 + 62), v50, 48, 0);
LABEL_61:
      Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(v255);
LABEL_21:
      Mso::Telemetry::Activity::~Activity((Mso::Telemetry::Activity *)v225);
      return 0;
    }
    RegCloseKey(hKey);
  }
  Mso::OLDocApi::SetGlobalOption((Mso::OLDocApi *)0x800, v48);
  LOBYTE(v51) = sub_1400062EC();
  Jot::DPIAwareness::SetDPIRegKeySetting(v51, v52);
  MsoCF::Frame::Start(v53);
  v218 = 0;
  MsoMigrate(12, &v218);
  Jot::BootStatus::BootStatus((Jot::BootStatus *)v223);
  if ( (v224 & 0x1F) == 0 && !v218 )
    Jot::RunNotebookRegistryMigration(v55);
  if ( byte_14025A5A0 < 0 )
    v57 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_14025A5A0);
  else
    v57 = byte_14025A5A0 != 0;
  if ( !v57 )
  {
    API = Mso::Sqm::GetAPI(v55);
    (**(void (__fastcall ***)(struct Mso::Sqm::ISqmApi *, __int64, void *, void *, void *))API)(
      API,
      11,
      &vmsoridOneNoteMTTF,
      &vmsoridOneNoteMTTA,
      &vmsoridOneNoteMTTT);
  }
  v59 = (Jot::CJotSingleApp *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)8, v54, v56);
  v212 = v59;
  if ( v59 )
    v60 = Jot::CJotSingleApp::CJotSingleApp(v59);
  else
    v60 = 0;
  MsoCF::COwnerPtr<Jot::CJotSingleApp,MsoCF::COwnerPtr_Delete_Auto<Jot::CJotSingleApp>>::Attach((char *)v1 + 632, v60);
  hKey = 0;
  v208[0] = 0;
  v61 = *((_QWORD *)v1 + 79);
  v63 = MsoCF::Frame::TheApp(v62);
  v64 = (*(__int64 (__fastcall **)(struct MsoCF::AFrameApp *))(*(_QWORD *)v63 + 152LL))(v63);
  started = Jot::CJotSingleApp::StartSingleInstance(v61, v64, v65, &hKey, v208);
  if ( started )
  {
    if ( started == 1 )
    {
      v69 = hKey;
      if ( hKey )
      {
        if ( *((_DWORD *)v1 + 76) == 1 )
        {
          SendMessageW((HWND)hKey, 0x408u, 0, 0);
        }
        else
        {
          std::wstring::wstring(&pguid, *((_QWORD *)v1 + 36));
          if ( Jot::CJotApp::FQueryCommandLineFlag(v1, L"/hardwareinvoke", 0, 0) && v208[0] )
            std::wstring::append(&pguid);
          lParam[0] = 38739;
          lParam[1] = (unsigned int)(2 * (_DWORD)v248 + 2);
          p_pguid = &pguid;
          if ( v249 > 7 )
            p_pguid = *(GUID **)&pguid.Data1;
          v254 = p_pguid;
          if ( !SendMessageW((HWND)v69, 0x4Au, 0, (LPARAM)lParam) && GetLastError() == 5 )
          {
            if ( Jot::CJotApp::FQueryCommandLineFlag(v1, L"/screencapture", 0, 0)
              || Jot::CJotApp::FQueryCommandLineFlag(v1, L"/screencaptureToIP", 0, 0) )
            {
              v75 = 235552404;
            }
            else
            {
              v72 = 0;
              v73 = 0;
              if ( *((int *)v1 + 76) > 0 )
              {
                v74 = 0;
                do
                {
                  if ( v72 )
                    break;
                  v72 = !MsoCF::Strings::IsWzPrefixOfWz(
                           (MsoCF::Strings *)L"/",
                           *(const wchar_t **)(*((_QWORD *)v1 + 37) + v74),
                           v71);
                  ++v73;
                  v74 += 8;
                }
                while ( v73 < *((_DWORD *)v1 + 76) );
              }
              if ( Jot::CJotApp::FQueryCommandLineFlag(v1, L"/hyperlink", 0, 0)
                || Jot::CJotApp::FQueryCommandLineFlag(v1, L"/openro", 0, 0)
                || v72 )
              {
                v75 = -1662216527;
              }
              else
              {
                v75 = -1094609581;
              }
            }
            MsoAlertIds(*((HINSTANCE *)v1 + 62), v75, 48, 0);
          }
          std::wstring::~wstring(&pguid);
        }
      }
      v67 = byte_14025A5A0 == 0;
      v68 = byte_14025A5A0 < 0;
    }
    else
    {
      v67 = byte_14025A5A0 == 0;
      v68 = byte_14025A5A0 < 0;
    }
    if ( v68 )
      v76 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_14025A5A0);
    else
      v76 = !v67;
    if ( !v76 )
      MsoDisableSqmThisSession();
    MsoCF::COwnerPtr<Jot::CJotSingleApp,MsoCF::COwnerPtr_Delete_Auto<Jot::CJotSingleApp>>::Attach((char *)v1 + 632, 0);
    goto LABEL_61;
  }
  v77 = 0;
  v208[0] = 0;
  v205 = 0;
  v206 = 0;
  if ( Jot::CJotApp::FQueryCommandLineFlag(v1, L"-embedding", 0, 0) )
  {
    v206 = 1;
    v77 = (v224 & 0x1F) != 0;
    v208[0] = v77;
    LOBYTE(v78) = 2;
    Mso::BootActivity::SetActivationKind(v78);
    v205 = v77;
  }
  if ( v211 )
  {
    LOBYTE(v78) = 3;
LABEL_114:
    Mso::BootActivity::SetActivationKind(v78);
    goto LABEL_121;
  }
  if ( (_BYTE)v209 )
  {
    LOBYTE(v78) = 4;
    goto LABEL_114;
  }
  if ( !v77 )
  {
    DesktopWindow = GetDesktopWindow();
    Src = 0;
    v242 = (void **)DesktopWindow;
    v243 = 0x100000001LL;
    v244 = 0;
    *(_DWORD *)v245 = 1;
    *(_OWORD *)&v245[4] = 0;
    if ( Jot::CJotApp::FQueryCommandLineFlag(v1, L"/memorywindow", 0, 0) )
    {
      v82 = (void **)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x10, v80, v81);
      if ( v82 )
      {
        v82[1] = 0;
        *v82 = &Jot::MemorySplashUser::`vftable';
        Src = v82;
      }
      else
      {
        Src = 0;
      }
    }
    MsoFShowSplash((const struct MsoSplashParams *)&Src);
  }
LABEL_121:
  MsoFInitializeCtxUIManager(0);
  if ( Jot::IsTellMeMemorySearchInWin32Enabled(v83) )
    InitializeTellMeFindInMemoryProvider();
  Enabled = Jot::IsOneNoteSubstrateV2QueryEnabled(v84);
  if ( *(char *)Enabled < 0 )
    v88 = Mso::AB::Optimized::FeatureGate::Evaluate(Enabled);
  else
    v88 = *(_BYTE *)Enabled != 0;
  if ( v88 )
    Jot::InitializeTellMeOneNoteSubstrateResultsProvider(v87);
  MsoCF::RegisterPropertySpace((MsoCF *)&Jot::PropertySpace_JotExe::g_prspi, v86);
  v90 = MsoCF::Frame::TheApp(v89);
  *((_QWORD *)v1 + 53) = v90;
  (*(void (__fastcall **)(struct MsoCF::AFrameApp *, _QWORD))(*(_QWORD *)v90 + 128LL))(v90, *((_QWORD *)v1 + 62));
  if ( (v223[9] & 0x1F) == 0 && Jot::CJotApp::FQueryCommandLineFlag(v1, L"/insertdoc", 0, 0) )
  {
    v50 = -65689955;
    goto LABEL_60;
  }
  if ( (v224 & 0x1F) == 0 )
  {
    MsoInstance = Jot::CJotApp::GetMsoInstance(v1);
    MsoFFirstRun(MsoInstance);
    sub_140121120();
    Jot::CreateAddinHive(v92);
    if ( (v224 & 0x1F) == 0 )
    {
      hKey = 0;
      if ( Jot::FGetMyDocumentsFolder((Jot *)&hKey, v93)
        && hKey
        && (v94 = (*(__int64 (__fastcall **)(HKEY))(*(_QWORD *)hKey + 24LL))(hKey),
            !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v94 + 184LL))(v94)) )
      {
        v221 = 0;
        if ( __eh34_try(-1, 2) )
        {
          __eh34_scope_strut(2);
          v95 = hKey;
          v96 = *(__int64 (__fastcall **)(HKEY, Jot::CJotSingleApp **, void ***, _QWORD, int, int, char, _BYTE, const char **, __int64 *))(*(_QWORD *)hKey + 88LL);
          v229[0] = &v226;
          v226 = 0;
          v228[0] = &v220;
          v220 = 0;
          pguid = 0;
          v97 = CoCreateGuid(&pguid);
          if ( v97 < 0 )
          {
            CrashWithRecoveryHrTag(v97, 0x1F3088C5u);
            __debugbreak();
          }
          *(GUID *)lParam = pguid;
          MsoCF::ToWStringWithConverter<_GUID>(&Src, (GUID *)lParam);
          p_Src = &Src;
          if ( v244 > 7 )
            p_Src = (void ***)Src;
          LOBYTE(v185) = 0;
          LOBYTE(phkResult) = 0;
          v99 = (char **)v96(v95, &v212, p_Src, 0, phkResult, v185, 1, 0, &v220, &v226);
          v100 = *v99;
          *v99 = 0;
          v221 = v100;
          if ( v212 )
            (*(void (__fastcall **)(Jot::CJotSingleApp *))(*(_QWORD *)v212 + 16LL))(v212);
          std::wstring::~wstring(&Src);
        }
        if ( __eh34_catch(2) )
        {
          if ( __eh34_catch_type(2, &Ofc::CException `RTTI Type Descriptor', 0) )
          {
            v77 = v205;
            v208[0] = v205;
            v100 = v221;
            v1 = (Jot::CJotApp *)v215;
            __eh34_try_continuation(2, &Ofc::CException `RTTI Type Descriptor', &loc_14001309B);
          }
        }
        if ( (!v100
           || !(*(unsigned __int8 (__fastcall **)(char *, _QWORD, __int64))(*(_QWORD *)v100 + 80LL))(v100, 0, 600000000))
          && MsoAlertIds(*((HINSTANCE *)v1 + 62), 290066912, 308, 0) == 7 )
        {
          if ( v100 )
            (*(void (__fastcall **)(char *))(*(_QWORD *)v100 + 16LL))(v100);
          goto LABEL_166;
        }
        if ( v100 )
        {
          LOBYTE(v194) = 0;
          LOBYTE(v190) = 1;
          LOBYTE(v186) = 0;
          (*(void (__fastcall **)(char *, _QWORD, _QWORD, _QWORD, _QWORD, int, int, int))(*(_QWORD *)v100 + 312LL))(
            v100,
            0,
            0,
            0,
            0,
            v186,
            v190,
            v194);
          (*(void (__fastcall **)(char *))(*(_QWORD *)v100 + 16LL))(v100);
        }
      }
      else if ( MsoAlertIds(*((HINSTANCE *)v1 + 62), 290066912, 308, 0) == 7 )
      {
LABEL_166:
        if ( !hKey )
          goto LABEL_61;
        v109 = *(void (**)(void))(*(_QWORD *)hKey + 16LL);
LABEL_168:
        v109();
        goto LABEL_61;
      }
      v101 = hKey;
      if ( hKey )
        (*(void (__fastcall **)(HKEY))(*(_QWORD *)hKey + 16LL))(hKey);
      if ( (v224 & 0x1F) == 0 )
        goto LABEL_155;
    }
  }
  v102 = Jot::CJotApp::FQueryCommandLineFlag(v1, L"/initjumplist", 0, 0);
  LOBYTE(v101) = 0;
  if ( v102 )
LABEL_155:
    LOBYTE(v101) = 1;
  sub_140047AC8((char)v101);
  Jot::ExeServer::Init(
    (Jot::ExeServer *)&Jot::g_HostModule,
    *((struct Jot::ATLUtils::IJotHostComModule **)v1 + 34),
    v103);
  if ( !v77 )
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v1 + 53) + 144LL))(*((_QWORD *)v1 + 53), 0);
  AddAtomW(L"_CTF_ENABLE_PROCESS_ATOM_");
  AddAtomW(L"_CTF_PROCESS_ATOM_");
  if ( !Jot::CJotApp::FQueryCommandLineFlag(v1, L"/sidenote", 0, 0)
    && !v77
    && !Jot::CJotApp::FQueryCommandLineFlag(v1, L"/runcit_loadandrender", 0, 0)
    && !Jot::CJotApp::FQueryCommandLineFlag(v1, L"/runcit_core", 0, 0) )
  {
    MsoUIBootCheck();
  }
  Jot::RegisterMsoWindowTransitionUser(v104);
  v107 = (Jot::CDialogManager *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x50, v105, v106);
  v228[0] = v107;
  if ( v107 )
    v108 = Jot::CDialogManager::CDialogManager(v107, v1);
  else
    v108 = 0;
  v110 = (Jot::CDialogManager *)*((_QWORD *)v1 + 64);
  if ( (Jot::CDialogManager *)v108 != v110 || !v108 )
  {
    *((_QWORD *)v1 + 64) = v108;
    if ( v110 )
    {
      Jot::CDialogManager::~CDialogManager(v110);
      operator delete(v110);
    }
  }
  NetUI::NodeClassInfo<NetUI::Element,Jot::CSimpleNavUIButton,NetUI::SimpleButton,0>::Register();
  NetUI::NodeClassInfo<NetUI::Element,Jot::CNavUIButton,Jot::CSimpleNavUIButton,0>::Register();
  if ( (v224 & 0x1F) == 0 )
    Jot::CJotApp::InitializeProgressWindowPositions(v111);
  v210 = 0;
  v112 = v218;
  v113 = *((_BYTE *)v1 + 644);
  v114 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v1 + 53) + 8LL))(*((_QWORD *)v1 + 53));
  v115 = (***((__int64 (__fastcall ****)(_QWORD))v1 + 53))(*((_QWORD *)v1 + 53));
  LOBYTE(phkResult) = v113;
  v116 = Jot::CreateMainApp(v115, v114, (char *)v1 + 16, (char *)v1 + 592, phkResult, v223, v112, &v210);
  v117 = (void (__fastcall ***)(_QWORD))*((_QWORD *)v1 + 54);
  if ( (void (__fastcall ***)(_QWORD))v116 != v117 || !v116 )
  {
    *((_QWORD *)v1 + 54) = v116;
    if ( v117 )
      (**v117)(v117);
  }
  if ( v210 )
  {
    v109 = *(void (**)(void))(**((_QWORD **)v1 + 54) + 240LL);
    goto LABEL_168;
  }
  if ( *((_BYTE *)v1 + 308) )
  {
    *((_QWORD *)v1 + 36) = 0;
    v118 = (void *)*((_QWORD *)v1 + 37);
    if ( v118 )
      LocalFree(v118);
    *((_QWORD *)v1 + 37) = 0;
    *((_DWORD *)v1 + 76) = 0;
  }
  Instance = MsoCF::CJotComObject<Jot::CDragDropManager,MsoCF::CAllocatorOnNew>::CreateInstance();
  v120 = Instance;
  if ( Instance )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)Instance + 8LL))(Instance);
  v121 = *((_QWORD *)v1 + 76);
  *((_QWORD *)v1 + 76) = v120;
  if ( v121 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v121 + 16LL))(v121);
  MsoRegisterAWSUser((Jot::CJotApp *)((char *)v1 + 568));
  v122 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v1 + 53) + 8LL))(*((_QWORD *)v1 + 53));
  v123 = *(void (__fastcall **)(__int64, __int64, const struct MsoCF::KeyMapEntry near *const *, __int64, int, __int64, const wchar_t *, int, _DWORD))(*(_QWORD *)v122 + 32LL);
  v124 = L"IDR_MAIN";
  if ( (unsigned int)MsoGetUILcid() == 1033 )
    v124 = 0;
  if ( (unsigned int)MsoGetUILcid() == 1033 )
    v125 = 0;
  else
    v125 = *((_QWORD *)v1 + 62);
  LOBYTE(v195) = 1;
  v123(v122, 1, &Jot::CJotApp::m_rgMainKeyMapEntry, 79, 1, v125, v124, v195, 0);
  v126 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v1 + 53) + 8LL))(*((_QWORD *)v1 + 53));
  v212 = *(Jot::CJotSingleApp **)(*(_QWORD *)v126 + 32LL);
  MsoGetUILcid();
  MsoGetUILcid();
  ((void (__fastcall *)(__int64, __int64, const struct MsoCF::KeyMapEntry near *const *))v212)(
    v126,
    2,
    &Jot::CJotApp::m_rgNavKeyMapEntry);
  v127 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v1 + 53) + 8LL))(*((_QWORD *)v1 + 53));
  v212 = *(Jot::CJotSingleApp **)(*(_QWORD *)v127 + 32LL);
  MsoGetUILcid();
  MsoGetUILcid();
  ((void (__fastcall *)(__int64, __int64, const struct MsoCF::KeyMapEntry near *const *))v212)(
    v127,
    3,
    &Jot::CJotApp::m_rgEditKeyMapEntry);
  v128 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v1 + 53) + 8LL))(*((_QWORD *)v1 + 53));
  v212 = *(Jot::CJotSingleApp **)(*(_QWORD *)v128 + 32LL);
  MsoGetUILcid();
  MsoGetUILcid();
  ((void (__fastcall *)(__int64, __int64, const struct MsoCF::KeyMapEntry near *const *))v212)(
    v128,
    4,
    &Jot::CJotApp::m_rgExeKeyMapEntry);
  v129 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v1 + 53) + 8LL))(*((_QWORD *)v1 + 53));
  v212 = *(Jot::CJotSingleApp **)(*(_QWORD *)v129 + 32LL);
  MsoGetUILcid();
  MsoGetUILcid();
  ((void (__fastcall *)(__int64, __int64, const struct MsoCF::KeyMapEntry near *const *))v212)(
    v129,
    7,
    &Jot::CJotApp::m_rgExeFrameAppKeyMapEntry);
  v130 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v1 + 53) + 8LL))(*((_QWORD *)v1 + 53));
  v212 = *(Jot::CJotSingleApp **)(*(_QWORD *)v130 + 32LL);
  MsoGetUILcid();
  MsoGetUILcid();
  ((void (__fastcall *)(__int64, __int64, const struct MsoCF::KeyMapEntry near *const *))v212)(
    v130,
    5,
    &Jot::CJotApp::m_rgShortcutKeysKeyMapEntry);
  v131 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v1 + 53) + 8LL))(*((_QWORD *)v1 + 53));
  v212 = *(Jot::CJotSingleApp **)(*(_QWORD *)v131 + 32LL);
  v132 = L"IDR_FIND";
  if ( (unsigned int)MsoGetUILcid() == 1033 )
    v132 = 0;
  if ( (unsigned int)MsoGetUILcid() == 1033 )
    v133 = 0;
  else
    v133 = *((_QWORD *)v1 + 62);
  LOBYTE(v196) = 1;
  ((void (__fastcall *)(__int64, __int64, const struct MsoCF::KeyMapEntry near *const *, __int64, int, __int64, const wchar_t *, int, _DWORD))v212)(
    v131,
    6,
    &Jot::CJotApp::m_rgFindKeyMapEntry,
    1,
    1,
    v133,
    v132,
    v196,
    0);
  v134 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v1 + 53) + 8LL))(*((_QWORD *)v1 + 53));
  v212 = *(Jot::CJotSingleApp **)(*(_QWORD *)v134 + 32LL);
  v135 = L"IDR_ENVELOPE";
  if ( (unsigned int)MsoGetUILcid() == 1033 )
    v135 = 0;
  if ( (unsigned int)MsoGetUILcid() == 1033 )
    v136 = 0;
  else
    v136 = *((_QWORD *)v1 + 62);
  LOBYTE(v197) = 1;
  ((void (__fastcall *)(__int64, __int64, const struct MsoCF::KeyMapEntry near *const *, __int64, int, __int64, const wchar_t *, int, _DWORD))v212)(
    v134,
    8,
    &Jot::CJotApp::m_rgEnvelopeKeyMapEntry,
    2,
    1,
    v136,
    v135,
    v197,
    0);
  v137 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v1 + 53) + 8LL))(*((_QWORD *)v1 + 53));
  v138 = *(void (__fastcall **)(__int64, __int64, const char *, __int64, int, __int64, const wchar_t *, int, _DWORD))(*(_QWORD *)v137 + 32LL);
  v139 = L"IDR_COPILOTNOTEBOOK";
  if ( (unsigned int)MsoGetUILcid() == 1033 )
    v139 = 0;
  if ( (unsigned int)MsoGetUILcid() == 1033 )
    v140 = 0;
  else
    v140 = *((_QWORD *)v1 + 62);
  LOBYTE(v198) = 1;
  v138(v137, 9, "]", 1, 1, v140, v139, v198, 0);
  v141 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v1 + 53) + 8LL))(*((_QWORD *)v1 + 53));
  (*(void (__fastcall **)(__int64, void *))(*(_QWORD *)v141 + 96LL))(v141, &Jot::CJotApp::GetWtzFromKcm);
  v142 = (***((__int64 (__fastcall ****)(_QWORD))v1 + 53))(*((_QWORD *)v1 + 53));
  (*(void (__fastcall **)(__int64, __int64 *, const struct MsoCF::ActionRegistration near *const *, __int64, int))(*(_QWORD *)v142 + 88LL))(
    v142,
    actcatidJotExe,
    &Jot::CJotApp::m_rgactregJotExe,
    148,
    3);
  v143 = (***((__int64 (__fastcall ****)(_QWORD))v1 + 53))(*((_QWORD *)v1 + 53));
  (*(void (__fastcall **)(__int64, __int64 *, const struct MsoCF::ActorRegistrationList * near **))(*(_QWORD *)v143
                                                                                                  + 104LL))(
    v143,
    actcatidJotExe,
    &Jot::CJotApp::m_rgpActorRegListJotExe);
  v144 = (***((__int64 (__fastcall ****)(_QWORD))v1 + 53))(*((_QWORD *)v1 + 53));
  (*(void (__fastcall **)(__int64, __int64 *, const struct MsoCF::ActorRegistrationList * near **))(*(_QWORD *)v144
                                                                                                  + 104LL))(
    v144,
    actcatidMain,
    &Jot::CJotApp::m_rgpActorRegListJotMain);
  Jot::ExeServer::Start(v145);
  v212 = v1;
  v147 = Mso::Memory::AllocateEx((Mso::Memory *)0x18, 0, v146);
  if ( !v147 )
  {
    CrashWithRecoveryOnOOM(0x131F462u);
    __debugbreak();
  }
  v215 = (__int64 (__fastcall ***)())sub_140007518(v147, &v212);
  Mso::Async::Post(&v215);
  v148 = v215;
  if ( v215 )
  {
    v215 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)()))(*v148)[2])(v148);
  }
  v149 = v206;
  if ( !v206 )
    Jot::CJotApp::NewInstance(v1, *((const wchar_t **)v1 + 36), 1, 0);
  v219 = 0;
  (*(void (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)v1 + 53) + 112LL))(*((_QWORD *)v1 + 53), &v219);
  v150 = *(_DWORD *)(MsoCF::CLangConfig::Instance() + 24);
  MsoFRegSetDw((const struct _msoreg *)&vmsoridUILanguageForQnote, v150);
  if ( (v224 & 0x1F) != 0 )
  {
    v151 = 0;
    if ( Dw != v150 )
    {
      LODWORD(hKey) = 0;
      if ( MsoFRegGetDw((const struct _msoreg *)&vmsoridOneNoteRunSystemTrayApp, (unsigned int *)&hKey) )
      {
        if ( (_DWORD)hKey == 1 )
        {
          (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v1 + 54) + 392LL))(*((_QWORD *)v1 + 54), 2);
          v151 = 1;
        }
      }
    }
    v152 = MsoDwRegGetDw((const struct _msoreg *)&vmsoridOneNoteRunSystemTrayApp);
    v153 = v151;
    if ( v152 == 1 )
      v153 = 1;
    if ( v153 )
    {
      Dw = 196735;
      v154 = (***((__int64 (__fastcall ****)(_QWORD))v1 + 53))(*((_QWORD *)v1 + 53));
      LOBYTE(v202) = 0;
      LOBYTE(v199) = 0;
      LOBYTE(v191) = 1;
      LOBYTE(v187) = 0;
      (*(void (__fastcall **)(__int64, unsigned int *, __int64, __int64, int, int, int, int, int))(*(_QWORD *)v154
                                                                                                 + 256LL))(
        v154,
        &Dw,
        v219,
        10,
        10000,
        v187,
        v191,
        v199,
        v202);
    }
  }
  else
  {
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v1 + 54) + 392LL))(*((_QWORD *)v1 + 54), 3);
  }
  v227 = 196740;
  v155 = (***((__int64 (__fastcall ****)(_QWORD))v1 + 53))(*((_QWORD *)v1 + 53));
  LOBYTE(v202) = 0;
  LOBYTE(v199) = 0;
  LOBYTE(v191) = 1;
  LOBYTE(v187) = 0;
  (*(void (__fastcall **)(__int64, int *, __int64, __int64, int, int, int, int, int))(*(_QWORD *)v155 + 256LL))(
    v155,
    &v227,
    v219,
    10,
    10000,
    v187,
    v191,
    v199,
    v202);
  v158 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x20, v156, v157);
  v159 = v158;
  if ( v158 )
  {
    v158[2] = 0;
    v158[1] = Jot::COneNoteOfficeCenterUser::`vbtable';
    v158[3] = &OfficeSpace::ISharePlaceUser::`vftable'{for `IUnknown'};
    *v158 = &Jot::COneNoteOfficeCenterUser::`vftable'{for `IMsoOfficeCenterUser'};
    v158[3] = &Jot::COneNoteOfficeCenterUser::`vftable'{for `IUnknown'};
    *((_DWORD *)v158 + 4) = 0;
  }
  else
  {
    v159 = 0;
  }
  if ( v159 )
  {
    v160 = (char *)v159 + *(int *)(v159[1] + 4LL) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v160 + 8LL))(v160);
  }
  v161 = *((_QWORD *)v1 + 83);
  *((_QWORD *)v1 + 83) = v159;
  MsoCF::CIPtr<Jot::COneNoteOfficeCenterUser,Jot::COneNoteOfficeCenterUser>::Release(v161);
  v162 = (struct IMsoOfficeCenterUser *)*((_QWORD *)v1 + 83);
  v163 = Jot::CJotApp::GetMsoInstance(v1);
  MsoHrRegisterOfficeCenterUser(v163, v162);
  v164 = (Mso::Clipboard *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v1 + 53) + 152LL))(*((_QWORD *)v1 + 53));
  Mso::Clipboard::MsoAddFormatChangeListener(v164, v165);
  MsoDestroyStartup();
  if ( v149 )
  {
    LOBYTE(v166) = 1;
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v1 + 53) + 200LL))(*((_QWORD *)v1 + 53), v166);
  }
  v222 = 131422;
  v167 = (***((__int64 (__fastcall ****)(_QWORD))v1 + 53))(*((_QWORD *)v1 + 53));
  LOBYTE(v203) = 0;
  LOBYTE(v200) = 0;
  LOBYTE(v192) = 1;
  LOBYTE(v188) = 0;
  (*(void (__fastcall **)(__int64, int *, __int64, __int64, int, int, int, int, int))(*(_QWORD *)v167 + 256LL))(
    v167,
    &v222,
    v219,
    2,
    60000,
    v188,
    v192,
    v200,
    v203);
  if ( (v224 & 0x1F) != 0 )
  {
    v168 = *((_QWORD *)v1 + 58);
    if ( v168 )
    {
      if ( *(_QWORD *)(v168 + 104) )
      {
        Dw = 132343;
        v169 = (***((__int64 (__fastcall ****)(_QWORD))v1 + 53))(*((_QWORD *)v1 + 53));
        LOBYTE(v204) = 0;
        LOBYTE(v201) = 1;
        LOBYTE(v193) = 1;
        LOBYTE(v189) = 0;
        (*(void (__fastcall **)(__int64, unsigned int *, __int64, __int64, int, int, int, int, int))(*(_QWORD *)v169 + 256LL))(
          v169,
          &Dw,
          v219,
          100,
          60000,
          v189,
          v193,
          v201,
          v204);
      }
    }
  }
  MsoFForceAcbInit();
  MsoBfileLimit(0);
  *((_BYTE *)v1 + 309) = 1;
  Jot::CCommandLineProcessor::ProcessCommandLines((Jot::CJotApp *)((char *)v1 + 576));
  OneNoteApplicationDocumentsUser::OnAppInitialized();
  Jot::EDP::RegisterEDPRevokeEvent(v170);
  MsoInitDigSigEx(0, 0, 12, 0, 0);
  if ( !byte_14025A311 )
  {
    v172 = OneNote::Flighting::PremiumFeatureEnablement::UsePremiumFeatureEnablement(v171);
    (*(void (__fastcall **)(struct OneNote::Flighting::PremiumFeatureEnablement::APremiumFeatureEnablement *, Jot::CJotSingleApp **, _QWORD))(*(_QWORD *)v172 + 8LL))(
      v172,
      &v212,
      0);
    __1__Functor___A6AXX_E_Mso__QEAA_XZ(&v212);
    if ( Jot::IsMemoryWindowAutoRestoreEnabled(0, v173)
      && !v208[0]
      && !v149
      && (!Jot::IsPreventMemoryWindowAutoRestoreOnOneNoteLaunchEnabled(v174) || (_BYTE)v209) )
    {
      v215 = &off_1402050D0;
      v176 = Jot::FastIntegration::UseCurrentExecutionContext(v175);
      v177 = (*(__int64 (__fastcall **)(struct Mso::ApplicationModel::IExecutionContext *))(*(_QWORD *)v176 + 16LL))(v176);
      Mso::Async::PostIdle<FastModel::Thread &>(v177, &v215);
      v178 = v215;
      if ( v215 )
      {
        v215 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)()))(*v178)[2])(v178);
      }
    }
    byte_14025A311 = 1;
  }
  *((_BYTE *)v1 + 321) = 1;
  v179 = (void **)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v1 + 54) + 896LL))(*((_QWORD *)v1 + 54));
  v243 = (__int64)off_1401CAEC0;
  v244 = (unsigned __int64)v1;
  v246 = &v243;
  v242 = v179;
  Src = (void **)*v179;
  *v179 = &Src;
  if ( Src )
    Src[1] = &Src;
  Jot::CNotifierHelper<Jot::CNotifierSingleThreadedConfig,>::Registration::operator=((char *)v1 + 680, &Src);
  Jot::CNotifierHelper<Jot::CNotifierSingleThreadedConfig,enum Tutorial::TutorialAction>::Registration::~Registration(&Src);
  MsoCF::PerfMetrics::Mark((MsoCF::PerfMetrics *)0x1F6, v180);
  if ( v219 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v219 + 16LL))(v219);
  Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(v255);
  Mso::Telemetry::Activity::~Activity((Mso::Telemetry::Activity *)v225);
  return 1;
}

```

## disassembly

```asm
0x1400121c8  mov     [rsp+arg_8], rbx
0x1400121cd  mov     [rsp+arg_10], rsi
0x1400121d2  push    rdi
0x1400121d3  push    r12
0x1400121d5  push    r13
0x1400121d7  push    r14
0x1400121d9  push    r15
0x1400121db  sub     rsp, 690h
0x1400121e2  mov     rax, cs:__security_cookie
0x1400121e9  xor     rax, rsp
0x1400121ec  mov     [rsp+6B8h+var_38], rax
0x1400121f4  mov     r15, rcx
0x1400121f7  mov     [rsp+6B8h+var_630], rcx
0x1400121ff  xor     ebx, ebx
0x140012201  lea     rcx, [rsp+6B8h+var_654]
0x140012206  call    ?GetDPIRegKeySetting@DPIAwareness@Jot@@YA?AV?$optional@_N@std@@XZ; Jot::DPIAwareness::GetDPIRegKeySetting(void)
0x14001220b  call    ?DisableDDPIBasedOnUserRegkeySetting@DPIAwareness@Jot@@YA_NXZ; Jot::DPIAwareness::DisableDDPIBasedOnUserRegkeySetting(void)
0x140012210  mov     sil, al
0x140012213  mov     r13b, [rsp+6B8h+var_654+1]
0x140012218  mov     cl, r13b
0x14001221b  neg     cl
0x14001221d  sbb     dl, dl
0x14001221f  movzx   edi, word ptr [rsp+6B8h+var_654]
0x140012224  test    dil, dl
0x140012227  jz      short loc_14001224E
0x140012229  call    sub_140001A40
0x14001222e  test    al, al
0x140012230  jz      short loc_14001224E
0x140012232  test    sil, sil
0x140012235  jnz     short loc_14001224E
0x140012237  lea     rcx, [rbx-4]
0x14001223b  call    cs:__imp_SetThreadDpiAwarenessContext
0x140012241  lea     r12d, [rbx+1]
0x140012245  mov     [r15+140h], r12b
0x14001224c  jmp     short loc_140012254
0x14001224e  mov     r12d, 1
0x140012254  mov     ecx, 11h; vKey
0x140012259  call    cs:__imp_GetAsyncKeyState
0x14001225f  shr     ax, 0Fh
0x140012263  mov     [r15+134h], al
0x14001226a  xor     edx, edx; hFile
0x14001226c  mov     r8d, 1000h; dwFlags
0x140012272  lea     rcx, LibFileName; "user32.dll"
0x140012279  call    cs:__imp_LoadLibraryExW
0x14001227f  mov     rsi, rax
0x140012282  test    rax, rax
0x140012285  jz      short loc_1400122AD
0x140012287  lea     rdx, aEnablemouseinp; "EnableMouseInPointer"
0x14001228e  mov     rcx, rax; hModule
0x140012291  call    cs:__imp_GetProcAddress
0x140012297  test    rax, rax
0x14001229a  jz      short loc_1400122A4
0x14001229c  xor     ecx, ecx
0x14001229e  call    cs:__guard_dispatch_icall_fptr
0x1400122a4  mov     rcx, rsi; hLibModule
0x1400122a7  call    cs:__imp_FreeLibrary
0x1400122ad  xor     edx, edx; bool
0x1400122af  lea     rcx, qword_140259EA8; this
0x1400122b6  call    ?Load@DllData@LoadMso@Mso@@QEAAPEAUHINSTANCE__@@_N@Z; Mso::LoadMso::DllData::Load(bool)
0x1400122bb  test    rax, rax
0x1400122be  jnz     short loc_1400122D0
0x1400122c0  call    ?DisplayAppNotConfiguredMsg@@YAXXZ; DisplayAppNotConfiguredMsg(void)
0x1400122c5  mov     edx, 28DD64Ah
0x1400122ca  call    ?ThrowTag@CAbortException@Ofc@@SAXW4ExcAbortStrategy@2@K@Z; Ofc::CAbortException::ThrowTag(Ofc::ExcAbortStrategy,ulong)
0x1400122cf  int     3; Trap to Debugger
0x1400122d0  call    cs:__imp_?JotMain_SetMainThreadID@Jot@@YAXXZ; Jot::JotMain_SetMainThreadID(void)
0x1400122d6  lea     rcx, ?JotUnhandledExceptionFilter@Jot@@YAJPEAU_EXCEPTION_POINTERS@@@Z; Jot::JotUnhandledExceptionFilter(_EXCEPTION_POINTERS *)
0x1400122dd  call    cs:__imp_?MsoSetUnhandledExceptionFilter@@YAP6AJPEAU_EXCEPTION_POINTERS@@@ZP6AJ0@Z@Z; MsoSetUnhandledExceptionFilter(long (*)(_EXCEPTION_POINTERS *))
0x1400122e3  call    cs:__imp_?EnableCrashRecoveryOnPureCall@CrashDetails@Mso@@YAXXZ; Mso::CrashDetails::EnableCrashRecoveryOnPureCall(void)
0x1400122e9  call    cs:__imp_?EnableCrashRecoveryOnInvalidParameter@CrashDetails@Mso@@YAXXZ; Mso::CrashDetails::EnableCrashRecoveryOnInvalidParameter(void)
0x1400122ef  lea     rcx, [r15+108h]
0x1400122f6  call    cs:__imp_?RegisterErrorHandler@MsoCF@@YAXPEAUAErrorHandler@1@@Z; MsoCF::RegisterErrorHandler(MsoCF::AErrorHandler *)
0x1400122fc  xor     r9d, r9d; struct Jot::CWzInBuffer *
0x1400122ff  xor     r8d, r8d; bool
0x140012302  lea     rdx, aSidenote; "/sidenote"
0x140012309  mov     rcx, r15; this
0x14001230c  call    ?FQueryCommandLineFlag@CJotApp@Jot@@QEAA_NPEB_W_NPEAVCWzInBuffer@2@@Z; Jot::CJotApp::FQueryCommandLineFlag(wchar_t const *,bool,Jot::CWzInBuffer *)
0x140012311  mov     sil, al
0x140012314  mov     [rsp+6B8h+var_64B], al
0x140012318  call    cs:__imp_?GetNamespace@Boot@OneNote@Office@@YAAEBUTelemetryNamespace@Telemetry@Mso@@XZ; Office::OneNote::Boot::GetNamespace(void)
0x14001231e  mov     [rsp+6B8h+var_5D0], rax
0x140012326  lea     rax, aInitinstance; "InitInstance"
0x14001232d  mov     [rsp+6B8h+var_5C8], rax
0x140012335  lea     rdx, [rsp+6B8h+var_5D0]; struct Mso::Telemetry::EventName *
0x14001233d  lea     rcx, [rsp+6B8h+var_5F0]; this
0x140012345  call    ??0Activity@Telemetry@Mso@@QEAA@AEBUEventName@12@@Z; Mso::Telemetry::Activity::Activity(Mso::Telemetry::EventName const &)
0x14001234a  nop
0x14001234b  lea     rcx, [rsp+6B8h+var_5F0]
0x140012353  call    cs:__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x140012359  mov     r8b, sil
0x14001235c  lea     rdx, aQuicknote; "QuickNote"
0x140012363  mov     rcx, rax
0x140012366  call    ??$Add@_N@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBD_NW4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<bool>(char const *,bool,Mso::Logging::DataClassifications)
0x14001236b  xor     r9d, r9d; struct Jot::CWzInBuffer *
0x14001236e  xor     r8d, r8d; bool
0x140012371  lea     rdx, aHyperlink; "/hyperlink"
0x140012378  mov     rcx, r15; this
0x14001237b  call    ?FQueryCommandLineFlag@CJotApp@Jot@@QEAA_NPEB_W_NPEAVCWzInBuffer@2@@Z; Jot::CJotApp::FQueryCommandLineFlag(wchar_t const *,bool,Jot::CWzInBuffer *)
0x140012380  test    al, al
0x140012382  jnz     short loc_14001239D
0x140012384  xor     r9d, r9d; struct Jot::CWzInBuffer *
0x140012387  xor     r8d, r8d; bool
0x14001238a  lea     rdx, aOneindex; "/oneindex"
0x140012391  mov     rcx, r15; this
0x140012394  call    ?FQueryCommandLineFlag@CJotApp@Jot@@QEAA_NPEB_W_NPEAVCWzInBuffer@2@@Z; Jot::CJotApp::FQueryCommandLineFlag(wchar_t const *,bool,Jot::CWzInBuffer *)
0x140012399  test    al, al
0x14001239b  jz      short loc_1400123A4
0x14001239d  mov     [r15+134h], bl
0x1400123a4  mov     ecx, 14h
0x1400123a9  call    cs:__imp_?Start@PerfMetrics@MsoCF@@YAXH@Z; MsoCF::PerfMetrics::Start(int)
0x1400123af  xor     r9d, r9d; struct Jot::CWzInBuffer *
0x1400123b2  xor     r8d, r8d; bool
0x1400123b5  lea     rdx, aMarkersoff; "/markersoff"
0x1400123bc  mov     rcx, r15; this
0x1400123bf  call    ?FQueryCommandLineFlag@CJotApp@Jot@@QEAA_NPEB_W_NPEAVCWzInBuffer@2@@Z; Jot::CJotApp::FQueryCommandLineFlag(wchar_t const *,bool,Jot::CWzInBuffer *)
0x1400123c4  test    al, al
0x1400123c6  jnz     short loc_1400123CE
0x1400123c8  call    cs:__imp_?Activate@PerfMetrics@MsoCF@@YAXXZ; MsoCF::PerfMetrics::Activate(void)
0x1400123ce  call    cs:__imp__Xtime_get_ticks
0x1400123d4  cmp     [r15+150h], bl
0x1400123db  jnz     short loc_1400123E4
0x1400123dd  mov     [r15+150h], r12b
0x1400123e4  mov     [r15+148h], rax
0x1400123eb  xor     ecx, ecx; pvReserved
0x1400123ed  call    cs:__imp_OleInitialize
0x1400123f3  test    eax, eax
0x1400123f5  jns     short loc_140012405
0x1400123f7  mov     edx, 28DD64Bh
0x1400123fc  mov     ecx, eax
0x1400123fe  call    cs:__imp_?CrashWithRecoveryHrTag@@YAXHI@Z; CrashWithRecoveryHrTag(int,uint)
0x140012404  int     3; Trap to Debugger
0x140012405  lea     r8, [r15+230h]
0x14001240c  lea     rdx, vfcf
0x140012413  mov     ecx, 0D0000h
0x140012418  call    cs:__imp_?MsoInitGimme@@YAXHPEBU_msotcfcf@@PEAUIMsoGimmeUser@@@Z; MsoInitGimme(int,_msotcfcf const *,IMsoGimmeUser *)
0x14001241e  mov     ecx, r12d
0x140012421  call    cs:__imp_?MsoThemeHaveManifest@@YAXH@Z; MsoThemeHaveManifest(int)
0x140012427  lea     rsi, ?vmsoridOneNoteLastUILang@@3U_msoreg@@B; _msoreg const vmsoridOneNoteLastUILang
0x14001242e  mov     rcx, rsi
0x140012431  call    cs:__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z; MsoDwRegGetDw(_msoreg const *)
0x140012437  mov     [rsp+6B8h+var_638], eax
0x14001243e  mov     [rsp+6B8h+var_578], bx
0x140012446  mov     [rsp+6B8h+var_570], rbx
0x14001244e  mov     [rsp+6B8h+var_554], 0FFFFFFFEh
0x140012459  mov     rax, [r15+110h]
0x140012460  mov     [rsp+6B8h+var_5A8], rax
0x140012468  lea     rax, [r15+8]
0x14001246c  mov     [rsp+6B8h+var_5A0], rax
0x140012474  mov     [rsp+6B8h+var_598], r15
0x14001247c  lea     rax, aMicrosoftOneno; "Microsoft OneNote"
0x140012483  mov     [rsp+6B8h+var_590], rax
0x14001248b  lea     rax, aOnenote_1; "OneNote"
0x140012492  mov     [rsp+6B8h+var_588], rax
0x14001249a  lea     rax, ?vmsoridCUBrandOneNoteName@@3U_msoreg@@B; _msoreg const vmsoridCUBrandOneNoteName
0x1400124a1  mov     [rsp+6B8h+var_580], rax
0x1400124a9  mov     [rsp+6B8h+var_568], rsi
0x1400124b1  mov     [rsp+6B8h+var_560], r12b
0x1400124b9  mov     [rsp+6B8h+var_55C], 0Ch
0x1400124c4  mov     [rsp+6B8h+var_558], 100h
0x1400124ce  mov     [rsp+6B8h+var_550], r12d
0x1400124d6  mov     [rsp+6B8h+var_54C], r12b
0x1400124de  lea     rcx, [rsp+6B8h+var_5A8]
0x1400124e6  call    cs:__imp_?CreateTheApp@Frame@MsoCF@@YAXAEAUCreateTheAppArgs@12@@Z; MsoCF::Frame::CreateTheApp(MsoCF::Frame::CreateTheAppArgs &)
0x1400124ec  call    cs:__imp_?TheApp@Frame@MsoCF@@YAPEAUAFrameApp@2@XZ; MsoCF::Frame::TheApp(void)
0x1400124f2  mov     r8, rax
0x1400124f5  mov     rcx, [rax]
0x1400124f8  mov     rax, [rcx+0F0h]
0x1400124ff  lea     rdx, [rsp+6B8h+var_5A8]
0x140012507  mov     rcx, r8
0x14001250a  call    cs:__guard_dispatch_icall_fptr
0x140012510  mov     rcx, r15; this
0x140012513  call    ?InitPluggableUI@CJotApp@Jot@@AEAAXXZ; Jot::CJotApp::InitPluggableUI(void)
0x140012518  call    cs:__imp_?TheApp@Frame@MsoCF@@YAPEAUAFrameApp@2@XZ; MsoCF::Frame::TheApp(void)
0x14001251e  mov     r8, rax
0x140012521  mov     rcx, [rax]
0x140012524  mov     rax, [rcx+0F8h]
0x14001252b  lea     rdx, [rsp+6B8h+var_5A8]
0x140012533  mov     rcx, r8
0x140012536  call    cs:__guard_dispatch_icall_fptr
0x14001253c  nop
0x14001253d  jmp     short loc_14001256C
0x14001253f  lea     rcx, [rsp+6B8h+var_5F0]
0x140012547  call    cs:__imp_??1Activity@Telemetry@Mso@@QEAA@XZ; Mso::Telemetry::Activity::~Activity(void)
0x14001254d  xor     al, al
0x14001254f  jmp     loc_140013F9A
0x140012554  xor     ebx, ebx
0x140012556  lea     r12d, [rbx+1]
0x14001255a  movzx   edi, word ptr [rsp+6B8h+var_654]
0x14001255f  mov     r13b, [rsp+6B8h+var_654+1]
0x140012564  mov     r15, [rsp+6B8h+var_630]
0x14001256c  test    r13b, r13b
0x14001256f  setnz   [rsp+6B8h+var_654]
0x140012574  lea     rax, aIsdpiawareness_0; "IsDPIAwarenessRegSet"
0x14001257b  mov     [rsp+6B8h+var_618], rax
0x140012583  lea     rax, aIsdpiawareness_0+14h; ""
0x14001258a  mov     [rsp+6B8h+var_610], rax
0x140012592  lea     r8, [rsp+6B8h+var_610]
0x14001259a  lea     rdx, [rsp+6B8h+var_618]
0x1400125a2  lea     rcx, [rsp+6B8h+var_648]
0x1400125a7  call    ??$make_unique@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAPEBDPEBD$0A@@std@@YA?AV?$unique_ptr@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@0@AEAPEBD$$QEAPEBD@Z; std::make_unique<std::wstring const,char const * &,char const *,0>(char const * &,char const * &&)
0x1400125ac  mov     r14, rax
0x1400125af  mov     rcx, [rax]
0x1400125b2  cmp     qword ptr [rcx+18h], 7
0x1400125b7  jbe     short loc_1400125BC
0x1400125b9  mov     rcx, [rcx]
0x1400125bc  lea     rsi, psz
0x1400125c3  test    rcx, rcx
0x1400125c6  jz      short loc_1400125DE
0x1400125c8  mov     [rsp+6B8h+var_4D8], rcx
0x1400125d0  mov     [rsp+6B8h+var_4D0], 0FFFFFFFFFFFFFFFFh
0x1400125dc  jmp     short loc_1400125EE
0x1400125de  mov     [rsp+6B8h+var_4D8], rsi
0x1400125e6  mov     [rsp+6B8h+var_4D0], rbx
0x1400125ee  lea     rax, [rsp+6B8h+var_654]
0x1400125f3  mov     [rsp+6B8h+var_4C8], rax
0x1400125fb  mov     eax, 4
0x140012600  mov     [rsp+6B8h+var_4C0], ax
0x140012608  lea     rax, ??_7?$StructuredTraceKeyHolder@U?$StructuredTraceImplementation@_N@details@Logging@Jot@@_N@details@Logging@Jot@@6BIStructuredTrace@2Mso@@@; const Jot::Logging::details::StructuredTraceKeyHolder<Jot::Logging::details::StructuredTraceImplementation<bool>,bool>::`vftable'{for `Mso::Logging::IStructuredTrace'}
0x14001260f  mov     qword ptr [rsp+6B8h+pguid.Data1], rax
0x140012617  lea     rax, ??_7?$StructuredTraceKeyHolder@U?$StructuredTraceImplementation@_N@details@Logging@Jot@@_N@details@Logging@Jot@@6BIDataField@Telemetry@Mso@@@; const Jot::Logging::details::StructuredTraceKeyHolder<Jot::Logging::details::StructuredTraceImplementation<bool>,bool>::`vftable'{for `Mso::Telemetry::IDataField'}
0x14001261e  mov     qword ptr [rsp+6B8h+pguid.Data4], rax
0x140012626  mov     rax, [r14]
0x140012629  mov     [r14], rbx
0x14001262c  mov     [rsp+6B8h+var_4B8], rax
0x140012634  cmp     [r14], rbx
0x140012637  jz      short loc_140012644
0x140012639  mov     edx, r12d
0x14001263c  mov     rcx, [r14]; void *
0x14001263f  call    ??_G?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAPEAXI@Z; std::wstring::`scalar deleting destructor'(uint)
0x140012644  mov     qword ptr [r14], 4DE1h
0x14001264b  neg     r13b
0x14001264e  sbb     al, al
0x140012650  and     al, dil
0x140012653  mov     [rsp+6B8h+var_658], al
0x140012657  lea     rax, aIsdpiawareness; "IsDPIAwarenessEnabled"
0x14001265e  mov     [rsp+6B8h+var_618], rax
0x140012666  lea     rax, aIsdpiawareness+15h; ""
0x14001266d  mov     [rsp+6B8h+var_610], rax
0x140012675  lea     r8, [rsp+6B8h+var_610]
0x14001267d  lea     rdx, [rsp+6B8h+var_618]
0x140012685  lea     rcx, [rsp+6B8h+var_648]
0x14001268a  call    ??$make_unique@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAPEBDPEBD$0A@@std@@YA?AV?$unique_ptr@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@0@AEAPEBD$$QEAPEBD@Z; std::make_unique<std::wstring const,char const * &,char const *,0>(char const * &,char const * &&)
0x14001268f  mov     rdi, rax
0x140012692  mov     rcx, [rax]
0x140012695  cmp     qword ptr [rcx+18h], 7
0x14001269a  jbe     short loc_14001269F
0x14001269c  mov     rcx, [rcx]
0x14001269f  test    rcx, rcx
0x1400126a2  jz      short loc_1400126BA
0x1400126a4  mov     [rsp+6B8h+var_528], rcx
0x1400126ac  mov     [rsp+6B8h+var_520], 0FFFFFFFFFFFFFFFFh
0x1400126b8  jmp     short loc_1400126CA
0x1400126ba  mov     [rsp+6B8h+var_528], rsi
0x1400126c2  mov     [rsp+6B8h+var_520], rbx
0x1400126ca  lea     rax, [rsp+6B8h+var_658]
0x1400126cf  mov     qword ptr [rsp+6B8h+var_518], rax
0x1400126d7  mov     eax, 4
0x1400126dc  mov     word ptr [rsp+6B8h+var_518+8], ax
0x1400126e4  lea     rax, ??_7?$StructuredTraceKeyHolder@U?$StructuredTraceImplementation@_N@details@Logging@Jot@@_N@details@Logging@Jot@@6BIStructuredTrace@2Mso@@@; const Jot::Logging::details::StructuredTraceKeyHolder<Jot::Logging::details::StructuredTraceImplementation<bool>,bool>::`vftable'{for `Mso::Logging::IStructuredTrace'}
0x1400126eb  mov     [rsp+6B8h+Src], rax
0x1400126f3  lea     rax, ??_7?$StructuredTraceKeyHolder@U?$StructuredTraceImplementation@_N@details@Logging@Jot@@_N@details@Logging@Jot@@6BIDataField@Telemetry@Mso@@@; const Jot::Logging::details::StructuredTraceKeyHolder<Jot::Logging::details::StructuredTraceImplementation<bool>,bool>::`vftable'{for `Mso::Telemetry::IDataField'}
0x1400126fa  mov     [rsp+6B8h+var_530], rax
0x140012702  mov     rax, [rdi]
0x140012705  mov     [rdi], rbx
0x140012708  mov     [rsp+6B8h+var_508], rax
0x140012710  cmp     [rdi], rbx
0x140012713  jz      short loc_140012720
0x140012715  mov     edx, r12d
0x140012718  mov     rcx, [rdi]; void *
0x14001271b  call    ??_G?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAPEAXI@Z; std::wstring::`scalar deleting destructor'(uint)
0x140012720  mov     qword ptr [rdi], 4DE1h
0x140012727  mov     [rsp+6B8h+var_64F], bl
0x14001272b  mov     r14d, 2
0x140012731  mov     word ptr [rsp+6B8h+hKey], r14w
0x140012737  mov     byte ptr [rsp+6B8h+hKey+2], r12b
0x14001273c  mov     [rsp+6B8h+var_627], bl
0x140012743  mov     [rsp+6B8h+var_625], bl
0x14001274a  mov     [rsp+6B8h+var_64E], 101h
0x140012751  lea     rax, [rsp+6B8h+var_650]
0x140012756  mov     [rsp+6B8h+var_690], rax
0x14001275b  lea     rax, [rsp+6B8h+hKey]
0x140012760  mov     [rsp+6B8h+phkResult], rax
0x140012765  lea     r9, [rsp+6B8h+var_628]
0x14001276d  lea     r8, [rsp+6B8h+var_626]
0x140012775  lea     rdx, [rsp+6B8h+var_64E]
0x14001277a  lea     rcx, [rsp+6B8h+var_5E0]
0x140012782  call    cs:__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z; Mso::Telemetry::EventFlags::EventFlags(std::optional<Mso::Telemetry::SamplingPolicy> const &,std::optional<Mso::Telemetry::PersistencePriority> const &,std::optional<Mso::Telemetry::CostPriority> const &,std::optional<Mso::Telemetry::DataCategories> const &,std::optional<Mso::Telemetry::DiagnosticLevel> const &)
0x140012788  call    cs:__imp_?GetNamespace@OneNote@Office@@YAAEBUTelemetryNamespace@Telemetry@Mso@@XZ; Office::OneNote::GetNamespace(void)
0x14001278e  mov     [rsp+6B8h+var_5C0], rax
0x140012796  lea     rax, aSetapptodpiawa; "SetAppToDPIAwareState"
0x14001279d  mov     [rsp+6B8h+var_5B8], rax
0x1400127a5  lea     r9, [rsp+6B8h+pguid]
0x1400127ad  lea     r8, [rsp+6B8h+Src]
0x1400127b5  lea     rdx, [rsp+6B8h+var_5E0]
0x1400127bd  lea     rcx, [rsp+6B8h+var_5C0]
0x1400127c5  call    ??$SendTelemetryEvent@U?$StructuredTraceKeyHolder@U?$StructuredTraceImplementation@_N@details@Logging@Jot@@_N@details@Logging@Jot@@U1234@@Logging@Jot@@YAXAEBUEventName@Telemetry@Mso@@AEBUEventFlags@34@$$QEAU?$StructuredTraceKeyHolder@U?$StructuredTraceImplementation@_N@details@Logging@Jot@@_N@details@01@2@Z; Jot::Logging::SendTelemetryEvent<Jot::Logging::details::StructuredTraceKeyHolder<Jot::Logging::details::StructuredTraceImplementation<bool>,bool>,Jot::Logging::details::StructuredTraceKeyHolder<Jot::Logging::details::StructuredTraceImplementation<bool>,bool>>(Mso::Telemetry::EventName const &,Mso::Telemetry::EventFlags const &,Jot::Logging::details::StructuredTraceKeyHolder<Jot::Logging::details::StructuredTraceImplementation<bool>,bool> &&,Jot::Logging::details::StructuredTraceKeyHolder<Jot::Logging::details::StructuredTraceImplementation<bool>,bool> &&)
0x1400127ca  lea     rcx, [rsp+6B8h+var_508]
0x1400127d2  call    ??1?$unique_ptr@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring const>::~unique_ptr<std::wstring const,std::default_delete<std::wstring const>>(void)
0x1400127d7  lea     rcx, [rsp+6B8h+var_4B8]
0x1400127df  call    ??1?$unique_ptr@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring const>::~unique_ptr<std::wstring const,std::default_delete<std::wstring const>>(void)
  ... truncated ...
```
