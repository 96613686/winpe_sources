# WinMain

- ea: `0x14002afa0`
- end: `0x14002bd87`
- name: `WinMain`
- size: `3559`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `42`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001cff0`

## callees

- `0x1400064b0`
- `0x14000aca0`
- `0x140025a60`
- `0x140026e50`
- `0x14002afa0`
- `0x14002bd90`
- `0x14002e040`
- `0x14002eef0`
- `0x1400306e0`
- `0x1400312d0`
- `0x140036200`
- `0x1400368c0`
- `0x1400388a0`
- `0x140045730`
- `0x14004a560`
- `0x14004a5b0`
- `0x14004a630`
- `0x14004e060`
- `0x14004e670`
- `0x140052450`
- `0x140059030`
- `0x14007f360`
- `0x1400a1880`
- `0x1400a1a20`
- `0x1400a30c0`
- `0x1400a91f0`
- `0x1400b8760`
- `0x1400cb568`
- `0x1400cf590`
- `0x1401090c0`
- `0x140203970`
- `0x1408c6d20`
- `0x1408cc450`
- `0x1408cc4b0`
- `0x14110b8c0`
- `0x14113d724`
- `0x141347330`
- `0x1413e0b50`
- `0x141f2a130`
- `0x14247bd70`
- `0x14247c010`
- `0x1432cc9b0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14002aff8`
- `KERNEL32!GetCurrentThreadId` at `0x14002b161`
- `KERNEL32!GetCurrentThreadId` at `0x14002aff8`
- `KERNEL32!GetCurrentThreadId` at `0x14002b161`
- `KERNEL32!InitializeCriticalSection` at `0x14002b04e`
- `KERNEL32!InitializeCriticalSection` at `0x14002b060`
- `KERNEL32!InitializeCriticalSection` at `0x14002b06d`
- `KERNEL32!InitializeCriticalSection` at `0x14002b04e`
- `KERNEL32!InitializeCriticalSection` at `0x14002b060`
- `KERNEL32!InitializeCriticalSection` at `0x14002b06d`
- `KERNEL32!GetCurrentProcess` at `0x14002afe3`
- `KERNEL32!GetCurrentProcess` at `0x14002afe3`
- `KERNEL32!GetCommandLineW` at `0x14002b2a7`
- `KERNEL32!GetCommandLineW` at `0x14002b2a7`
- `api-ms-win-crt-runtime-l1-1-0!exit` at `0x14002bd80`
- `api-ms-win-crt-runtime-l1-1-0!exit` at `0x14002bd80`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x14002b2c0`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x14002b2c0`
- `USER32!RegisterWindowMessageA` at `0x14002ba40`
- `USER32!RegisterWindowMessageA` at `0x14002ba53`
- `USER32!RegisterWindowMessageA` at `0x14002ba40`
- `USER32!RegisterWindowMessageA` at `0x14002ba53`
- `USER32!WaitForInputIdle` at `0x14002afee`
- `USER32!WaitForInputIdle` at `0x14002afee`
- `USER32!GetDC` at `0x14002b176`
- `USER32!GetDC` at `0x14002b176`
- `MSO!__imp_?OsrHrInitClient@@YAJXZ` at `0x14002b1e5`
- `MSO!__imp_?OsrHrInitClient@@YAJXZ` at `0x14002b1e5`
- `MSO!__imp_MsoUninitEarlyOffice` at `0x14002bd74`
- `MSO!__imp_MsoUninitEarlyOffice` at `0x14002bd74`
- `MSO!__imp_?MsoEndBoot@@YAXXZ` at `0x14002bbe0`
- `MSO!__imp_?MsoEndBoot@@YAXXZ` at `0x14002bbe0`
- `MSO!__imp_?MsoStartShutdown@@YAXXZ` at `0x14002bd6e`
- `MSO!__imp_?MsoStartShutdown@@YAXXZ` at `0x14002bd6e`
- `MSO!__imp_MsoBeginBootEx` at `0x14002b7c2`
- `MSO!__imp_MsoBeginBootEx` at `0x14002b7c2`
- `Mso98Win32Client!__imp_?MsoSetIsRibbonApp@@YAX_N@Z` at `0x14002b8ae`
- `Mso98Win32Client!__imp_?MsoSetIsRibbonApp@@YAX_N@Z` at `0x14002b8ae`
- `Mso98Win32Client!__imp_?MsoInitGimme@@YAXHPEBU_msotcfcf@@PEAUIMsoGimmeUser@@@Z` at `0x14002b8a0`
- `Mso98Win32Client!__imp_?MsoInitGimme@@YAXHPEBU_msotcfcf@@PEAUIMsoGimmeUser@@@Z` at `0x14002b8a0`
- `Mso98Win32Client!__imp_?SetDynamicCanvasBootArguments@DynamicCanvas@Mso@@YAXAEBUBootArguments@12@@Z` at `0x14002b736`
- `Mso98Win32Client!__imp_?SetDynamicCanvasBootArguments@DynamicCanvas@Mso@@YAXAEBUBootArguments@12@@Z` at `0x14002b736`
- `mso40uiWin32Client!__imp_?EnableWhatsNewOnBoot@WhatsNew@Mso@@YAXXZ` at `0x14002b326`
- `mso40uiWin32Client!__imp_?EnableWhatsNewOnBoot@WhatsNew@Mso@@YAXXZ` at `0x14002b326`
- `mso40uiWin32Client!__imp_?DisableBootIdle@ApplicationModel@Mso@@YAXXZ` at `0x14002b72b`
- `mso40uiWin32Client!__imp_?DisableBootIdle@ApplicationModel@Mso@@YAXXZ` at `0x14002b72b`
- `Mso30Win32Client!__imp_?FShouldActivateChildWindowMixedMode@DisplayAssistant@Mso@@YA_NXZ` at `0x14002b7ec`
- `Mso30Win32Client!__imp_?FShouldActivateChildWindowMixedMode@DisplayAssistant@Mso@@YA_NXZ` at `0x14002b7ec`
- `Mso30Win32Client!__imp_?MsoGetUserDefaultLocaleName@Config@Mso@@YA_NPEA_WH@Z` at `0x14002b9a0`
- `Mso30Win32Client!__imp_?MsoGetUserDefaultLocaleName@Config@Mso@@YA_NPEA_WH@Z` at `0x14002b9a0`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x14002b920`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x14002b920`
- `Mso30Win32Client!__imp_?MsoSetUnhandledExceptionFilterEx@@YAP6AJPEAU_EXCEPTION_POINTERS@@@ZP6AJ0@ZW4MSORCOF@@@Z` at `0x14002b260`
- `Mso30Win32Client!__imp_?MsoSetUnhandledExceptionFilterEx@@YAP6AJPEAU_EXCEPTION_POINTERS@@@ZP6AJ0@ZW4MSORCOF@@@Z` at `0x14002b260`
- `Mso30Win32Client!__imp_?SetFForceDisablePerMonitorMode@DisplayAssistant@Mso@@YAXXZ` at `0x14002b689`
- `Mso30Win32Client!__imp_?SetFForceDisablePerMonitorMode@DisplayAssistant@Mso@@YAXXZ` at `0x14002b689`
- `Mso30Win32Client!__imp_?GetOsrClient@Client@SecureReader@Mso@@YAPEAUIOsrClient@123@XZ` at `0x14002b1f1`
- `Mso30Win32Client!__imp_?GetOsrClient@Client@SecureReader@Mso@@YAPEAUIOsrClient@123@XZ` at `0x14002b1f1`
- `Mso30Win32Client!__imp_?MsoGimmeLocalizedLibrary@@YAPEAUHINSTANCE__@@HPEAKKPEA_WHK@Z` at `0x14002b963`
- `Mso30Win32Client!__imp_?MsoGimmeLocalizedLibrary@@YAPEAUHINSTANCE__@@HPEAKKPEA_WHK@Z` at `0x14002b963`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x14002b1ae`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x14002b1ae`
- `Mso20Win32Client!__imp_??1BootActivity@Mso@@QEAA@XZ` at `0x14002ba2a`
- `Mso20Win32Client!__imp_??1BootActivity@Mso@@QEAA@XZ` at `0x14002bd60`
- `Mso20Win32Client!__imp_??1BootActivity@Mso@@QEAA@XZ` at `0x14002ba2a`
- `Mso20Win32Client!__imp_??1BootActivity@Mso@@QEAA@XZ` at `0x14002bd60`
- `Mso20Win32Client!__imp_?MsoFIsRunningRestricted@@YAHXZ` at `0x14002bb2f`
- `Mso20Win32Client!__imp_?MsoFIsRunningRestricted@@YAHXZ` at `0x14002bb70`
- `Mso20Win32Client!__imp_?MsoFIsRunningRestricted@@YAHXZ` at `0x14002bbb6`
- `Mso20Win32Client!__imp_?MsoFIsRunningRestricted@@YAHXZ` at `0x14002bb2f`
- `Mso20Win32Client!__imp_?MsoFIsRunningRestricted@@YAHXZ` at `0x14002bb70`
- `Mso20Win32Client!__imp_?MsoFIsRunningRestricted@@YAHXZ` at `0x14002bbb6`
- `Mso20Win32Client!__imp_?MsoSetThreadDpiHostingBehavior@Mso@@YA?AW4DPI_HOSTING_BEHAVIOR@@W42@@Z` at `0x14002b814`
- `Mso20Win32Client!__imp_?MsoSetThreadDpiHostingBehavior@Mso@@YA?AW4DPI_HOSTING_BEHAVIOR@@W42@@Z` at `0x14002b814`
- `Mso20Win32Client!__imp_?OverrideSessionFlag@UngracefulExit@Telemetry@Mso@@YAXW4SessionFlag@123@_N@Z` at `0x14002bb48`
- `Mso20Win32Client!__imp_?OverrideSessionFlag@UngracefulExit@Telemetry@Mso@@YAXW4SessionFlag@123@_N@Z` at `0x14002bb89`
- `Mso20Win32Client!__imp_?OverrideSessionFlag@UngracefulExit@Telemetry@Mso@@YAXW4SessionFlag@123@_N@Z` at `0x14002bbd3`
- `Mso20Win32Client!__imp_?OverrideSessionFlag@UngracefulExit@Telemetry@Mso@@YAXW4SessionFlag@123@_N@Z` at `0x14002bb48`
- `Mso20Win32Client!__imp_?OverrideSessionFlag@UngracefulExit@Telemetry@Mso@@YAXW4SessionFlag@123@_N@Z` at `0x14002bb89`
- `Mso20Win32Client!__imp_?OverrideSessionFlag@UngracefulExit@Telemetry@Mso@@YAXW4SessionFlag@123@_N@Z` at `0x14002bbd3`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x14002bc00`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x14002bc00`
- `Mso20Win32Client!__imp_?SetActivationKind@BootActivity@Mso@@SAXW4ActivationKind@12@@Z` at `0x14002b66b`
- `Mso20Win32Client!__imp_?SetActivationKind@BootActivity@Mso@@SAXW4ActivationKind@12@@Z` at `0x14002b66b`
- `Mso20Win32Client!__imp_?EnableCrashRecoveryOnPureCall@CrashDetails@Mso@@YAXXZ` at `0x14002b280`
- `Mso20Win32Client!__imp_?EnableCrashRecoveryOnPureCall@CrashDetails@Mso@@YAXXZ` at `0x14002b280`
- `Mso20Win32Client!__imp_?EnableCrashRecoveryOnInvalidParameter@CrashDetails@Mso@@YAXXZ` at `0x14002b274`
- `Mso20Win32Client!__imp_?EnableCrashRecoveryOnInvalidParameter@CrashDetails@Mso@@YAXXZ` at `0x14002b274`
- `Mso20Win32Client!Mso20Win32Client_48782` at `0x14002b78b`
- `Mso20Win32Client!Mso20Win32Client_48782` at `0x14002b78b`
- `Mso20Win32Client!__imp_?Set@RPA@Process@Mso@@YAX_N@Z` at `0x14002b6a7`
- `Mso20Win32Client!__imp_?Set@RPA@Process@Mso@@YAX_N@Z` at `0x14002b6a7`
- `Mso20Win32Client!__imp_??0BootActivity@Mso@@QEAA@AEBV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@chrono@std@@_N@Z` at `0x14002b246`
- `Mso20Win32Client!__imp_??0BootActivity@Mso@@QEAA@AEBV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@chrono@std@@_N@Z` at `0x14002b246`

## pseudocode

```c

```
