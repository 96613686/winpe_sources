# HrFileLoadEx(wchar_t *,int,int,int,int,PLINT * *,int,int,IMsoOLDocument * *,int,int,int,wchar_t const *,wchar_t const *,FileLoadContext *,XlLoadReason,wchar_t const *,XlSyncStateChangeListenerLoad *,VersionHistoryWindowParams *,int *)

- ea: `0x1402ef090`
- end: `0x1402fc87f`
- name: `?HrFileLoadEx@@YAJPEA_WHHHHPEAPEAUPLINT@@HHPEAPEAUIMsoOLDocument@@HHHPEB_W3PEAVFileLoadContext@@W4XlLoadReason@@3PEAVXlSyncStateChangeListenerLoad@@PEAVVersionHistoryWindowParams@@PEAH@Z`
- size: `55279`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _DWORD, _QWORD)`
- caller_count: `6`
- callee_count: `578`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1402eac40`
- `0x140477100`
- `0x14086ef40`
- `0x141448790`
- `0x142321000`
- `0x14240fce0`

## callees

- `0x140045350`
- `0x140051818`
- `0x1400524b0`
- `0x1400524d8`
- `0x140052520`
- `0x14005258c`
- `0x1400525e0`
- `0x1400526a0`
- `0x140054f30`
- `0x140056050`
- `0x140056330`
- `0x1400581d0`
- `0x140058790`
- `0x140058840`
- `0x140059090`
- `0x14006d980`
- `0x140075f40`
- `0x140076020`
- `0x140076b0c`
- `0x140076b50`
- `0x140077ce0`
- `0x140079180`
- `0x14007d410`
- `0x14007db10`
- `0x14007f3c0`
- `0x14007f590`
- `0x14007f620`
- `0x140095800`
- `0x1400a6ec0`
- `0x1400b2a60`
- `0x1400b4910`
- `0x1400b4b10`
- `0x1400c7970`
- `0x1400cb5c8`
- `0x1400cc050`
- `0x1400da4a0`
- `0x1400f82d0`
- `0x1401052c0`
- `0x1401590d0`
- `0x1401602d0`
- `0x140175740`
- `0x14018e9f0`
- `0x140190a90`
- `0x14019a734`
- `0x14019e510`
- `0x14019f5e0`
- `0x1401b5650`
- `0x1401b9d90`
- `0x1401bc1e4`
- `0x1401bd020`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1402f0346`
- `KERNEL32!CloseHandle` at `0x1402fc66f`
- `KERNEL32!CloseHandle` at `0x1402f0346`
- `KERNEL32!CloseHandle` at `0x1402fc66f`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x1402f0c43`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x1402f0c43`
- `USER32!SetForegroundWindow` at `0x1402fb160`
- `USER32!SetForegroundWindow` at `0x1402fb160`
- `MSO!__imp_?MsoDoWatsonAlertBegin@@YAXK_NJPEAUWADD@@@Z` at `0x1402fbfc4`
- `MSO!__imp_?MsoDoWatsonAlertBegin@@YAXK_NJPEAUWADD@@@Z` at `0x1402fbfc4`
- `MSO!__imp_?IsVersionCrawlForRepairEnabled@History@Mso@@YA_NXZ` at `0x1402fbb60`
- `MSO!__imp_?IsVersionCrawlForRepairEnabled@History@Mso@@YA_NXZ` at `0x1402fbb60`
- `MSO!__imp_?MsoHrSimpleOfflineOpenFile@@YAJPEAUIMsoOLDocument@@P6AJW4MSOSCA@@0K@ZK@Z` at `0x1402fb9a0`
- `MSO!__imp_?MsoHrSimpleOfflineOpenFile@@YAJPEAUIMsoOLDocument@@P6AJW4MSOSCA@@0K@ZK@Z` at `0x1402fb9a0`
- `MSO!__imp_?MsoHrMetadataEvent@@YAJPEBUIMsoOLDocument@@W4_MSOFME@@PEAX@Z` at `0x1402f8bc0`
- `MSO!__imp_?MsoHrMetadataEvent@@YAJPEBUIMsoOLDocument@@W4_MSOFME@@PEAX@Z` at `0x1402f8bc0`
- `MSO!__imp_?MsoDoWatsonAlertEnd@@YAXPEAUWADD@@PEB_W@Z` at `0x1402fc0a0`
- `MSO!__imp_?MsoDoWatsonAlertEnd@@YAXPEAUWADD@@PEB_W@Z` at `0x1402fc0a0`
- `MSO!__imp_?MsoFDrmErrorCode@@YAHJ@Z` at `0x1402f2cd7`
- `MSO!__imp_?MsoFDrmErrorCode@@YAHJ@Z` at `0x1402f2cee`
- `MSO!__imp_?MsoFDrmErrorCode@@YAHJ@Z` at `0x1402f32c8`
- `MSO!__imp_?MsoFDrmErrorCode@@YAHJ@Z` at `0x1402f2cd7`
- `MSO!__imp_?MsoFDrmErrorCode@@YAHJ@Z` at `0x1402f2cee`
- `MSO!__imp_?MsoFDrmErrorCode@@YAHJ@Z` at `0x1402f32c8`
- `MSO!__imp_?MsoServerErrorAlert@@YAXW4_MSOSRVERRTYPE@@PEB_W1@Z` at `0x1402fade4`
- `MSO!__imp_?MsoServerErrorAlert@@YAXW4_MSOSRVERRTYPE@@PEB_W1@Z` at `0x1402fade4`
- `MSO!__imp_?MsoHrTaxonomyOnDocOpen@@YAJPEAUIMsoOLDocument@@@Z` at `0x1402f8bd2`
- `MSO!__imp_?MsoHrTaxonomyOnDocOpen@@YAJPEAUIMsoOLDocument@@@Z` at `0x1402f8bd2`
- `MSO!__imp_?MsoServerErrorTypeGet@@YA?AW4_MSOSRVERRTYPE@@PEAPEA_W@Z` at `0x1402fadd6`
- `MSO!__imp_?MsoServerErrorTypeGet@@YA?AW4_MSOSRVERRTYPE@@PEAPEA_W@Z` at `0x1402fadd6`
- `MSO!__imp_?MsoFShouldGatekeep@@YAHPEBU_msoreg@@@Z` at `0x1402f222e`
- `MSO!__imp_?MsoFShouldGatekeep@@YAHPEBU_msoreg@@@Z` at `0x1402f222e`
- `Mso98Win32Client!__imp_?MsoSetReadWriteOnSaveIoldoc@@YAXPEAUIMsoOLDocument@@H@Z` at `0x1402fa70a`
- `Mso98Win32Client!__imp_?MsoSetReadWriteOnSaveIoldoc@@YAXPEAUIMsoOLDocument@@H@Z` at `0x1402fa800`
- `Mso98Win32Client!__imp_?MsoSetReadWriteOnSaveIoldoc@@YAXPEAUIMsoOLDocument@@H@Z` at `0x1402fa70a`
- `Mso98Win32Client!__imp_?MsoSetReadWriteOnSaveIoldoc@@YAXPEAUIMsoOLDocument@@H@Z` at `0x1402fa800`
- `Mso98Win32Client!__imp_?IsDocumentWindowEventManagerEnabled@EventMgr@DocumentWindow@Mso@@YA_NXZ` at `0x1402f818e`
- `Mso98Win32Client!__imp_?IsDocumentWindowEventManagerEnabled@EventMgr@DocumentWindow@Mso@@YA_NXZ` at `0x1402f818e`
- `Mso98Win32Client!__imp_?FIsHttpRedirFile@@YAHPEB_WHHHPEAH@Z` at `0x1402f0c80`
- `Mso98Win32Client!__imp_?FIsHttpRedirFile@@YAHPEB_WHHHPEAH@Z` at `0x1402f0c80`
- `Mso98Win32Client!__imp_?MsoFConvertHttpRedirUNCToHttp@@YAHPEB_WPEA_WH@Z` at `0x1402f0ca0`
- `Mso98Win32Client!__imp_?MsoFConvertHttpRedirUNCToHttp@@YAHPEB_WPEA_WH@Z` at `0x1402f0ca0`
- `Mso98Win32Client!__imp_?MsoFReservedWzPersistentName@@YAHPEB_W@Z` at `0x1402f0c57`
- `Mso98Win32Client!__imp_?MsoFReservedWzPersistentName@@YAHPEB_W@Z` at `0x1402f0c57`
- `Mso98Win32Client!__imp_?MsoFReadWriteOnSaveIoldoc@@YAHPEAUIMsoOLDocument@@@Z` at `0x1402fa78c`
- `Mso98Win32Client!__imp_?MsoFReadWriteOnSaveIoldoc@@YAHPEAUIMsoOLDocument@@@Z` at `0x1402fa78c`
- `Mso98Win32Client!__imp_?MsoFIsInFileSysWzPersistentName@@YA_NPEB_W0@Z` at `0x1402f012a`
- `Mso98Win32Client!__imp_?MsoFIsInFileSysWzPersistentName@@YA_NPEB_W0@Z` at `0x1402f0500`
- `Mso98Win32Client!__imp_?MsoFIsInFileSysWzPersistentName@@YA_NPEB_W0@Z` at `0x1402f0960`
- `Mso98Win32Client!__imp_?MsoFIsInFileSysWzPersistentName@@YA_NPEB_W0@Z` at `0x1402f012a`
- `Mso98Win32Client!__imp_?MsoFIsInFileSysWzPersistentName@@YA_NPEB_W0@Z` at `0x1402f0500`
- `Mso98Win32Client!__imp_?MsoFIsInFileSysWzPersistentName@@YA_NPEB_W0@Z` at `0x1402f0960`
- `Mso98Win32Client!__imp_?MetroFGetErrorWz@@YA_NJPEA_WPEAI@Z` at `0x1402fbb40`
- `Mso98Win32Client!__imp_?MetroFGetErrorWz@@YA_NJPEA_WPEAI@Z` at `0x1402fbb40`
- `Mso98Win32Client!__imp_?MsoFDrmUIEnabled@@YAHXZ` at `0x1402fa990`
- `Mso98Win32Client!__imp_?MsoFDrmUIEnabled@@YAHXZ` at `0x1402fa990`
- `Mso30Win32Client!__imp_?MsoCreateOpTimer@@YAJHHPEAPEAUIMsoOpTimer@@@Z` at `0x1402efac1`
- `Mso30Win32Client!__imp_?MsoCreateOpTimer@@YAJHHPEAPEAUIMsoOpTimer@@@Z` at `0x1402efac1`
- `Mso30Win32Client!__imp_?IsEnabled@Config@AppGuard@@YA_NXZ` at `0x1402f2820`
- `Mso30Win32Client!__imp_?IsEnabled@Config@AppGuard@@YA_NXZ` at `0x1402f2820`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1402ef5ac`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1402efc51`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1402f0230`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1402f1f4a`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1402f1f6c`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1402ef5ac`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1402efc51`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1402f0230`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1402f1f4a`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1402f1f6c`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402ef4f2`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f070a`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f12a2`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f1355`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f144d`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f1460`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f2660`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f2a63`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f302e`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f33b9`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f3ce0`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f5c0e`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f67cc`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f9f36`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402fac03`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402fb479`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402ef4f2`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f070a`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f12a2`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f1355`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f144d`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f1460`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f2660`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f2a63`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f302e`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f33b9`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f3ce0`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f5c0e`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f67cc`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f9f36`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402fac03`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402fb479`
- `Mso20Win32Client!__imp_?HrCancelScenario@PerfScenario@Mso@@YAJPEBUMsoPerfScenarioId@12@@Z` at `0x1402ef554`
- `Mso20Win32Client!__imp_?HrCancelScenario@PerfScenario@Mso@@YAJPEBUMsoPerfScenarioId@12@@Z` at `0x1402ef554`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1402ef1e0`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1402f5480`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1402f550d`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1402f84f6`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1402f9ce9`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1402f9d0c`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1402fa0a9`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1402ef1e0`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1402f5480`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1402f550d`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1402f84f6`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1402f9ce9`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1402f9d0c`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1402fa0a9`
- `Mso20Win32Client!__imp_?MsoResetLastWAlertHR@@YAXXZ` at `0x1402f5c25`
- `Mso20Win32Client!__imp_?MsoResetLastWAlertHR@@YAXXZ` at `0x1402f5c25`
- `Mso20Win32Client!__imp_?FScenarioActive@PerfScenario@Mso@@YA_NPEBUMsoPerfScenarioId@12@@Z` at `0x1402ef543`
- `Mso20Win32Client!__imp_?FScenarioActive@PerfScenario@Mso@@YA_NPEBUMsoPerfScenarioId@12@@Z` at `0x1402ef543`
- `Mso20Win32Client!__imp_?MsoSetLastWAlertHRTag@@YAXJK@Z` at `0x1402f5c03`
- `Mso20Win32Client!__imp_?MsoSetLastWAlertHRTag@@YAXJK@Z` at `0x1402f5c03`
- `Mso20Win32Client!__imp_?HrEndScenario@PerfScenario@Mso@@YAJPEBUMsoPerfScenarioId@12@@Z` at `0x1402f038b`
- `Mso20Win32Client!__imp_?HrEndScenario@PerfScenario@Mso@@YAJPEBUMsoPerfScenarioId@12@@Z` at `0x1402fc612`
- `Mso20Win32Client!__imp_?HrEndScenario@PerfScenario@Mso@@YAJPEBUMsoPerfScenarioId@12@@Z` at `0x1402f038b`
- `Mso20Win32Client!__imp_?HrEndScenario@PerfScenario@Mso@@YAJPEBUMsoPerfScenarioId@12@@Z` at `0x1402fc612`
- `Mso20Win32Client!__imp_?SetActivationKind@BootActivity@Mso@@SAXW4ActivationKind@12@@Z` at `0x1402ef560`
- `Mso20Win32Client!__imp_?SetActivationKind@BootActivity@Mso@@SAXW4ActivationKind@12@@Z` at `0x1402ef560`
- `Mso20Win32Client!__imp_?MsoFRegSetDw@@YAHPEBU_msoreg@@K@Z` at `0x1402ef5cd`
- `Mso20Win32Client!__imp_?MsoFRegSetDw@@YAHPEBU_msoreg@@K@Z` at `0x1402ef5cd`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1402f57ae`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1402f8954`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1402f8970`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1402f8a00`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1402fb4c5`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1402fbf05`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1402f57ae`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1402f8954`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1402f8970`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1402f8a00`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1402fb4c5`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1402fbf05`
- `Mso20Win32Client!__imp_??0MeasureElapsedTime@Measurements@@QEAA@UMeasurementIdType@1@_N$$QEAVStopwatch@1@@Z` at `0x1402f5771`
- `Mso20Win32Client!__imp_??0MeasureElapsedTime@Measurements@@QEAA@UMeasurementIdType@1@_N$$QEAVStopwatch@1@@Z` at `0x1402f8920`
- `Mso20Win32Client!__imp_??0MeasureElapsedTime@Measurements@@QEAA@UMeasurementIdType@1@_N$$QEAVStopwatch@1@@Z` at `0x1402f89e7`
- `Mso20Win32Client!__imp_??0MeasureElapsedTime@Measurements@@QEAA@UMeasurementIdType@1@_N$$QEAVStopwatch@1@@Z` at `0x1402fbe80`
- `Mso20Win32Client!__imp_??0MeasureElapsedTime@Measurements@@QEAA@UMeasurementIdType@1@_N$$QEAVStopwatch@1@@Z` at `0x1402f5771`
- `Mso20Win32Client!__imp_??0MeasureElapsedTime@Measurements@@QEAA@UMeasurementIdType@1@_N$$QEAVStopwatch@1@@Z` at `0x1402f8920`
- `Mso20Win32Client!__imp_??0MeasureElapsedTime@Measurements@@QEAA@UMeasurementIdType@1@_N$$QEAVStopwatch@1@@Z` at `0x1402f89e7`
- `Mso20Win32Client!__imp_??0MeasureElapsedTime@Measurements@@QEAA@UMeasurementIdType@1@_N$$QEAVStopwatch@1@@Z` at `0x1402fbe80`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1402f02e0`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1402f02e0`
- `Mso20Win32Client!__imp_?MsoHrCreateUrlSimpleFromUser@@YAJPEAPEAUIMsoUrl@@PEB_WKPEBU1@W4MsoUrlCreateFlags@@PEAUIMsoMemHeap@@@Z` at `0x1402ef7a0`
- `Mso20Win32Client!__imp_?MsoHrCreateUrlSimpleFromUser@@YAJPEAPEAUIMsoUrl@@PEB_WKPEBU1@W4MsoUrlCreateFlags@@PEAUIMsoMemHeap@@@Z` at `0x1402ef7a0`
- `Mso20Win32Client!__imp_?HrBeginScenario@PerfScenario@Mso@@YAJPEBUMsoPerfScenarioId@12@@Z` at `0x1402ef56d`
- `Mso20Win32Client!__imp_?HrBeginScenario@PerfScenario@Mso@@YAJPEBUMsoPerfScenarioId@12@@Z` at `0x1402ef56d`

## string_xrefs

- `0x1402fa72b`: `Check for XML Load Options value: %d prior to displaying business bar`
- `0x1402fa5db`: `and force template load`
- `0x1402fa639`: `Loading workbook with Auto refresh load status: %d and read only mode: %d %s`
- `0x1402f6886`: `Jumped during load, global book changed`
- `0x1402fb10d`: `Unconditionally setting foreground window for already opened book`
- `0x1402f548f`: `ZipItOldocSetReadOnly`
- `0x1402f9a15`: `Dirtying workbook because it was loaded from a backup copy.`

## pseudocode

```c
__int64 __fastcall HrFileLoadEx(
        wchar_t *a1,
        int a2,
        char a3,
        int a4,
        int a5,
        __int64 a6,
        int a7,
        int a8,
        struct IMsoOLDocument **a9,
        int a10,
        int a11,
        int a12,
        wchar_t *a13,
        __int64 a14,
        BKORWS *a15,
        unsigned int a16,
        const wchar_t *a17,
        struct IMemHeap *a18,
        struct VersionHistoryWindowParams *a19,
        int *a20)
{
  BKORWS *v21; // r15
  struct IMemHeap *v22; // rdi
  int *v23; // r14
  char v24; // al
  unsigned int v25; // r12d
  Mso::Telemetry::Activity *v26; // rax
  struct Mso::Telemetry::IDataFieldCollection *v27; // rax
  __int64 v28; // rcx
  int v29; // edx
  char v30; // cl
  int v31; // eax
  BOOL v32; // eax
  int v33; // eax
  __int64 v34; // rdx
  void *ThreadLocalStoragePointer; // rax
  __int64 v36; // rax
  const struct Mso::PerfScenario::MsoPerfScenarioId *v37; // rdx
  const struct Mso::PerfScenario::MsoPerfScenarioId *v38; // rdx
  __int64 v39; // rcx
  const struct Mso::PerfScenario::MsoPerfScenarioId *v40; // rdx
  int v41; // eax
  bool v42; // bl
  int Dw; // eax
  bool v44; // cc
  wchar_t *v45; // rsi
  wchar_t *v46; // rax
  struct IMsoOLDocument *v47; // rsi
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rax
  LXBASE *v51; // rdi
  XlDisplayElementInfoAll *v52; // rcx
  LinkedEntityManager *v53; // rax
  int v54; // eax
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rdx
  __int64 v58; // rdx
  __int64 v59; // rax
  __int64 v60; // r15
  __int64 v61; // r8
  __int64 v62; // rdx
  wchar_t *v63; // rsi
  __int64 v64; // rdx
  int v65; // ecx
  int v66; // eax
  _QWORD *v67; // rax
  wchar_t *v68; // r14
  wchar_t *v69; // rbx
  int v70; // eax
  char v71; // al
  __int64 v72; // rax
  unsigned int v73; // r13d
  _QWORD *v74; // rax
  __int64 v75; // rcx
  bool v76; // al
  struct IMsoOLDocument *v77; // rax
  TLSW *v78; // rcx
  __int64 v79; // rdx
  __int64 v80; // rcx
  __int64 v81; // rax
  __int64 v82; // rdx
  Excel::XlBoot **v83; // rax
  wchar_t *v84; // r12
  unsigned int v85; // ebx
  wchar_t *v86; // rax
  const wchar_t *v87; // rax
  struct IMsoOLDocument *v88; // rcx
  char v89; // si
  int v90; // ebx
  bool v91; // di
  OlDocFilePath *v92; // rax
  int v93; // eax
  unsigned int v94; // eax
  _QWORD *v95; // rax
  void *v96; // rdx
  struct IMsoOLDocument *v97; // rcx
  __int64 v98; // rdx
  __int64 v100; // rax
  const wchar_t *v101; // rax
  const wchar_t *v102; // rax
  __int64 v103; // rax
  bool v104; // bl
  struct IMemHeap *v105; // r15
  ZrtUtility *v106; // rax
  const wchar_t *v107; // rdx
  ExpressionService *v108; // rax
  struct WORKBOOKCOLLECTION *v109; // rax
  OlDocFilePath *v110; // rbx
  struct OpenTelemetry *v111; // rax
  OlDocFilePath *v112; // rbx
  SXVWGEOM *v113; // rax
  unsigned int v114; // eax
  int v115; // eax
  int v116; // r15d
  OlDocFilePath *v117; // rax
  struct IMsoOLDocument *v118; // rbx
  ZrtUtility *v119; // rax
  struct IMsoOLDocument *v120; // r9
  ArtUserInterfaceSite *v121; // rbx
  bool v122; // dl
  OpenTelemetry *v123; // rax
  struct OpenTelemetry *v124; // rax
  OlDocFilePath *v125; // rax
  const struct OlDocFilePath *v126; // rax
  int v127; // eax
  OlDocFilePath *v128; // rax
  const wchar_t *v129; // rax
  int v130; // eax
  const wchar_t *v131; // rax
  struct IMsoOLDocument *v132; // rbx
  struct IMemHeap *v133; // rax
  OlDocFilePath *v134; // rax
  const wchar_t *v135; // rax
  const wchar_t *v136; // rax
  IMsoOLDocument *v137; // rcx
  __int64 (__fastcall *v138)(struct IMsoOLDocument *, const wchar_t *, unsigned int *, __int64); // rbx
  const wchar_t *v139; // rax
  int v140; // edi
  int v141; // eax
  OpenTelemetry *v142; // rax
  const wchar_t *v143; // rax
  BOOL v144; // r14d
  bool v145; // di
  unsigned int v146; // ebx
  unsigned int v147; // eax
  BKORWS *v148; // rcx
  const wchar_t *v149; // rax
  __int64 v150; // r9
  wchar_t *v151; // r8
  wchar_t *v152; // rdi
  const wchar_t *v153; // rax
  wchar_t *v154; // rbx
  const wchar_t *v155; // rax
  __int64 v156; // rcx
  const wchar_t *v157; // rax
  unsigned int v158; // ebx
  char v159; // si
  struct IMsoOLDocumentCoauth *v160; // rax
  SXVWGEOM *v161; // rax
  unsigned int v162; // eax
  SXVWGEOM *v163; // rax
  unsigned int v164; // eax
  struct LXTAB *v165; // rax
  struct LXTAB *v166; // rbx
  const wchar_t *v167; // rax
  wchar_t *v168; // rbx
  char v169; // al
  int v170; // esi
  int v171; // eax
  const wchar_t *v172; // rbx
  struct IMemHeap *v173; // rax
  int v174; // eax
  char v175; // al
  int v176; // eax
  struct BOOK *v177; // r8
  bool v178; // al
  struct SH **v179; // rcx
  BOOK *v180; // rax
  struct IMsoOLDocument *v181; // rax
  struct IMsoOLDocument *v182; // rcx
  __int64 v183; // rax
  char v184; // di
  __int64 v185; // rax
  char v186; // al
  int v187; // ebx
  BKORWS *v188; // rax
  struct IMsoOLDocumentCoauth *v189; // rax
  SXVWGEOM *v190; // rax
  unsigned int v191; // eax
  SXVWGEOM *v192; // rax
  unsigned int v193; // eax
  struct IMsoOLDocument *v194; // rdi
  __int64 v195; // rbx
  SXVWGEOM *v196; // rax
  unsigned int v197; // eax
  __int64 v198; // r9
  __int64 v199; // r8
  BOOK *v200; // rbx
  SXVWGEOM *v201; // rax
  unsigned int v202; // eax
  struct IMsoOLDocument *v203; // rax
  __int64 v204; // r8
  struct IMsoOLDocument *v205; // rcx
  SXVWGEOM *v206; // rax
  unsigned int v207; // eax
  BOOK *v208; // rbx
  SXVWGEOM *v209; // rax
  unsigned int v210; // eax
  bool v211; // r14
  __int64 v212; // rsi
  char v213; // di
  char v214; // bl
  struct IMsoOLDocument *v215; // rax
  unsigned int v216; // edx
  const wchar_t *v217; // rax
  __int64 v218; // rcx
  int v219; // ebx
  int v220; // eax
  const struct CXO *v221; // rax
  unsigned int v222; // r8d
  struct BOOK *v223; // rax
  __int64 v224; // rcx
  int inited; // eax
  char v226; // cl
  SXVWGEOM *v227; // rax
  unsigned int v228; // eax
  _QWORD *v229; // rdx
  __int64 v230; // rcx
  _QWORD *v231; // r8
  struct WNX *v232; // rbx
  unsigned __int64 v233; // rax
  SH *v234; // rcx
  struct BOOK *v235; // rax
  __int64 v236; // r8
  __int64 v237; // rax
  struct BOOK *v238; // rax
  SXVWGEOM *v239; // rax
  unsigned int v240; // eax
  _QWORD *v241; // rdx
  __int64 v242; // rcx
  _QWORD *v243; // r8
  SXVWGEOM *v244; // rax
  unsigned int v245; // eax
  _QWORD *v246; // rdx
  __int64 v247; // rcx
  _QWORD *v248; // r8
  unsigned int v249; // edx
  ExpressionService *v250; // rax
  struct WORKBOOKCOLLECTION *v251; // rax
  OlDocFilePath *v252; // rbx
  SXVWGEOM *v253; // rax
  unsigned int v254; // eax
  __int64 v255; // rax
  __int64 v256; // rax
  const wchar_t *Target; // rax
  unsigned int v258; // edx
  const struct OlDocFilePath *v259; // rax
  int v260; // eax
  __int64 v261; // r8
  OlDocFilePath *v262; // rax
  const wchar_t *v263; // rax
  void *v264; // rax
  __int64 v265; // rax
  struct STGI *v266; // r12
  void *v267; // rax
  int v268; // eax
  int v269; // eax
  int v270; // edi
  unsigned int v271; // ebx
  struct IStorage *v272; // rax
  int v273; // eax
  bool v274; // bl
  struct IStorage *v275; // rax
  int v276; // ebx
  int v277; // eax
  wchar_t *v278; // rdi
  wchar_t *v279; // rdi
  int v280; // esi
  struct IMemHeap *v281; // rax
  int v282; // ebx
  wchar_t *v283; // rax
  int CnvTempFile; // eax
  MaxPathStzPoke *v285; // rcx
  int v286; // ebx
  wchar_t *v287; // rax
  int v288; // eax
  const wchar_t *v289; // rax
  const wchar_t *v290; // rax
  int v291; // eax
  __int64 v292; // rcx
  const wchar_t *v293; // rax
  struct OpenTelemetry *v294; // rax
  __int64 v295; // rax
  LXBASE *v296; // rbx
  SXVWGEOM *v297; // rax
  struct STGI *v298; // rax
  int v299; // ebx
  int v300; // eax
  BKORWS *v301; // rcx
  struct SH *v302; // rax
  struct ISlicerView *v303; // rax
  AppGuard::Config *v304; // rcx
  int v305; // eax
  void *v306; // rcx
  __int64 v307; // rax
  __int64 v308; // rbx
  SXVWGEOM *v309; // rax
  unsigned int v310; // eax
  int v311; // ebx
  struct IMemHeap *v312; // rdi
  const struct ILocaleInfo *v313; // rax
  int v314; // edi
  unsigned int v315; // edx
  int v316; // ecx
  MaxPathHolder *v317; // rcx
  __int64 v318; // rax
  CorruptionMetaData *v319; // rax
  CorruptionMetaData *v320; // rbx
  char v321; // al
  __int64 v322; // rax
  __int64 v323; // rax
  __int64 v324; // rax
  LXBASE *v325; // rbx
  SXVWGEOM *v326; // rax
  int v327; // eax
  unsigned int v328; // r8d
  int v329; // ecx
  __int64 v330; // r9
  const wchar_t *v331; // rax
  __int64 v332; // rax
  __int64 v333; // rbx
  SXVWGEOM *v334; // rax
  unsigned int v335; // eax
  __int64 v336; // rdx
  int v337; // edi
  struct IMemHeap *v338; // rax
  wchar_t *v339; // rax
  const wchar_t *v340; // rbx
  const wchar_t *v341; // rax
  struct SH *v342; // rbx
  struct BOOK *v343; // rax
  __int64 v344; // rax
  int v345; // eax
  unsigned int v346; // ebx
  int v347; // ecx
  __int64 v348; // r8
  char v349; // r14
  unsigned int v350; // edx
  int v351; // ecx
  struct SH *v352; // rax
  XlsActivity *v353; // rsi
  struct SH *v354; // rdi
  unsigned __int8 v355; // al
  unsigned int v356; // edx
  struct SH *v357; // rax
  XlsActivity *v358; // rsi
  struct SH *v359; // rdi
  bool v360; // cl
  int v361; // eax
  char v362; // cl
  int v363; // ecx
  const struct ILocaleInfo *v364; // rax
  unsigned __int16 v365; // ax
  int v366; // edi
  __int64 v367; // rax
  __int64 v368; // rbx
  SXVWGEOM *v369; // rax
  unsigned int v370; // eax
  unsigned __int16 v371; // ax
  int v372; // ebx
  unsigned __int16 v373; // di
  char v374; // si
  unsigned int v375; // edx
  int v376; // ecx
  const struct ILocaleInfo *v377; // rax
  OlDocFilePath *v378; // rax
  const struct Mso::Clp::IClpDocument *v379; // rbx
  struct IStorage *EncryptedStorage; // rax
  __int64 v381; // rax
  int DeferredError; // eax
  int v383; // eax
  int v384; // ebx
  char v385; // al
  struct IMemHeap *v386; // rax
  int FileTemp; // eax
  __int64 v388; // r8
  const wchar_t *v389; // rax
  struct FileSource *v390; // rdx
  bool v391; // bl
  const wchar_t *v392; // rax
  wchar_t *v393; // rdx
  __int64 v394; // rdx
  int v395; // eax
  __int64 v396; // rax
  __int64 v397; // rbx
  SXVWGEOM *v398; // rax
  unsigned int v399; // eax
  bool v400; // al
  BOOL v401; // eax
  struct SH *v402; // rax
  int v403; // ecx
  __int64 v404; // rax
  __int64 v405; // rbx
  SXVWGEOM *v406; // rax
  unsigned int v407; // eax
  __int64 v408; // rdx
  struct XPACKAGE *v409; // rax
  struct IMsoOLDocument **v410; // rsi
  __int64 *v411; // rax
  __int64 v412; // rcx
  __int64 v413; // rax
  __int64 v414; // rcx
  struct SXVIEW *v415; // rax
  int v416; // ecx
  __int64 v417; // rax
  LXBASE *v418; // rbx
  SXVWGEOM *v419; // rax
  struct SH *v420; // r13
  OlDocFilePath *v421; // rax
  struct SH *v422; // r14
  struct IMsoDocumentEncryptor *v423; // r15
  int v424; // edi
  struct OpenTelemetry *v425; // r12
  int v426; // esi
  int v427; // ebx
  struct ISlicerView *v428; // rax
  int v429; // r8d
  void *v430; // rax
  struct Api::Workbook *v431; // rax
  __int64 v432; // rcx
  OcsTransitionController *v433; // rax
  XLSBOOK *v434; // rax
  SlicerViewImpl *v435; // rax
  TAB *v436; // rbx
  OcsTransitionController *v437; // rax
  XLSBOOK *v438; // rax
  TAB *v439; // r12
  void *v440; // r14
  struct SH *v441; // rax
  unsigned __int8 v442; // al
  SXVWGEOM *v443; // rax
  unsigned int v444; // edi
  struct SH *v445; // rax
  __int64 v446; // rdx
  __int64 v447; // rcx
  _QWORD *v448; // r8
  _QWORD *v449; // rdx
  __int64 v450; // rax
  SXVWGEOM *v452; // rax
  unsigned int v453; // eax
  _QWORD *v454; // rdx
  __int64 v455; // rcx
  _QWORD *v456; // r8
  struct WNX *v457; // rcx
  const wchar_t *v458; // rax
  CorruptionMetaData *v459; // rax
  struct SXVIEW *v460; // rax
  __int64 v461; // rax
  __int64 v462; // rax
  __int64 v463; // rbx
  SXVWGEOM *v464; // rax
  unsigned int v465; // eax
  __int64 v466; // rax
  struct SXVIEW *v467; // rax
  unsigned int v468; // edi
  struct IStorage *v469; // rax
  int v470; // eax
  __int64 v471; // rax
  __int64 v472; // rcx
  OlDocFilePath *v473; // rax
  const struct Mso::Clp::IClpDocument *v474; // rbx
  struct IStorage *v475; // rax
  bool v476; // al
  OlDocFilePath *v477; // rax
  const struct Mso::Clp::IClpDocument *v478; // rbx
  struct IStorage *v479; // rax
  int v480; // ebx
  struct SXVIEW *v481; // rax
  const wchar_t *v482; // rax
  struct IMemHeap *v483; // rax
  int v484; // eax
  __int64 v485; // rax
  LXBASE *v486; // rbx
  SXVWGEOM *v487; // rax
  const wchar_t *v488; // rax
  int v489; // eax
  SXVWGEOM *v490; // rax
  unsigned int v491; // eax
  _QWORD *v492; // rdx
  __int64 v493; // rcx
  _QWORD *v494; // r8
  const wchar_t *v495; // rax
  struct WNX *v496; // rcx
  __int64 v497; // r8
  int v498; // eax
  __int64 v499; // rbx
  const wchar_t *v500; // rax
  __int64 v501; // rcx
  __int64 v502; // rcx
  unsigned int v503; // r8d
  struct IMsoOLDocument **v504; // rsi
  SXVWGEOM *v505; // rax
  unsigned int v506; // eax
  bool v507; // al
  __int64 v508; // rax
  struct SXVIEW *v509; // rax
  __int64 v510; // rax
  wchar_t **v511; // rbx
  const wchar_t *v512; // rax
  __int64 v513; // rax
  BOOK *v514; // rbx
  SXVWGEOM *v515; // rax
  unsigned int v516; // eax
  __int64 v517; // r8
  Mso::Telemetry::Activity *v518; // rbx
  struct IMsoOLDocumentCoauth *v519; // rax
  SXVWGEOM *v520; // rax
  unsigned int v521; // eax
  struct Mso::Telemetry::IDataFieldCollection *v522; // rax
  unsigned int v523; // edi
  struct Mso::Telemetry::IDataFieldCollection *v524; // rax
  BOOK *v525; // rcx
  struct IMsoXmlDataStore *v526; // rbx
  struct IMsoOLDocument *v527; // rax
  __int64 v528; // rax
  __int64 v529; // rcx
  struct OfficeSpace::IOutSpace *OutSpace; // rdi
  void (__fastcall *v531)(struct OfficeSpace::IOutSpace *, _QWORD, struct IMsoOLDocument *); // rbx
  struct IMsoOLDocument *v532; // rax
  struct IMsoOLDocument *v533; // rax
  struct IMsoAddInX **v534; // rdx
  struct IMsoOLDocument *v535; // rax
  __int64 v536; // rax
  SXVWGEOM *v537; // rax
  unsigned int v538; // eax
  __int64 v539; // rax
  __int64 v540; // r8
  int v541; // eax
  __int64 v542; // rdx
  __int64 v543; // rcx
  unsigned __int64 v544; // rax
  struct SXVIEW *v545; // rax
  struct SXVIEW *v546; // rax
  struct OpenTelemetry *v547; // rax
  __int64 v548; // rdx
  int v549; // eax
  const struct ILocaleInfo *v550; // rax
  BOOL v551; // ecx
  struct STGI *v552; // rax
  unsigned int v553; // ebx
  struct IStorage *v554; // rax
  const wchar_t *v555; // rax
  const struct ILocaleInfo *v556; // rax
  int v557; // eax
  unsigned int v558; // edx
  __int64 v559; // rax
  int v560; // edx
  int v561; // eax
  bool v562; // zf
  int v563; // eax
  XlSecurity *v564; // rax
  int v565; // eax
  __int64 v566; // rax
  LXBASE *v567; // rbx
  SXVWGEOM *v568; // rax
  XllFlighting *v569; // rcx
  struct CELLW *v570; // rax
  PcellwGuard *v571; // rax
  __int64 v572; // rdx
  int XllFileFromOutsideCalc; // eax
  unsigned int v574; // edx
  const wchar_t *v575; // rax
  __int64 v576; // rax
  struct SXVIEW *v577; // rax
  __int64 *v578; // rax
  __int64 v579; // rcx
  __int64 v580; // rax
  unsigned int v581; // edx
  __int64 v582; // rax
  __int64 v583; // rax
  struct SXVIEW *v584; // rax
  __int64 v585; // rax
  __int64 v586; // rbx
  SXVWGEOM *v587; // rax
  unsigned int v588; // eax
  void *v589; // rax
  __int64 v590; // rax
  int v591; // ebx
  __int64 v592; // r8
  SH *v593; // r13
  __int64 v594; // rax
  const struct BOOK *v595; // rdx
  const wchar_t *v596; // rax
  int v597; // eax
  bool v598; // r14
  __int64 v599; // rax
  wchar_t **v600; // rdi
  const wchar_t *v601; // rax
  const wchar_t *v602; // rax
  const wchar_t *v603; // rax
  int v604; // r13d
  int v605; // eax
  int v606; // ebx
  void *v607; // rax
  __int64 v608; // rdx
  __int64 v609; // rdx
  __int64 v610; // rdx
  SXVWGEOM *v611; // rax
  unsigned int v612; // eax
  _QWORD *v613; // rdx
  __int64 v614; // rcx
  int v615; // eax
  int v616; // eax
  __int64 v617; // rax
  LXBASE *v618; // rbx
  SXVWGEOM *v619; // rax
  int v620; // r14d
  wchar_t *v621; // rdi
  int v622; // eax
  struct SH *v623; // rax
  wchar_t *v624; // rax
  int BookXmlSpreadsheet; // eax
  __int64 v626; // rax
  wchar_t **v627; // rdi
  const wchar_t *v628; // rax
  SXVWGEOM *v629; // rax
  unsigned int v630; // eax
  struct SH *v631; // rax
  struct SH *v632; // rax
  int OptDialog; // eax
  BOOL v634; // r12d
  const wchar_t *v635; // rbx
  wchar_t *v636; // rax
  struct SH *v637; // rax
  struct IMsoOLDocument *v638; // rdi
  struct STM *v639; // r14
  struct OpenTelemetry *v640; // rbx
  const wchar_t *v641; // rsi
  wchar_t *v642; // rax
  void *v643; // rax
  struct IMsoOLDocument *v644; // rdi
  __int64 v645; // rcx
  void *v646; // rax
  int Project2; // eax
  int v648; // eax
  int HtmlFailed; // eax
  struct IMemHeap *v650; // rax
  const wchar_t *v651; // rdx
  const wchar_t *v652; // rbx
  const wchar_t *v653; // rax
  int Xml; // eax
  void *v655; // rax
  int v656; // edi
  struct IMsoOLDocument *v657; // rsi
  __int64 v658; // rcx
  void *v659; // rax
  XLSWORKBOOK *v660; // rax
  OcsTransitionController *v661; // rax
  struct Api::CoauthTransitionState *v662; // rax
  __int64 v663; // rcx
  int v664; // eax
  bool v665; // al
  int v666; // eax
  __int64 v667; // rcx
  XLSBOOK *v668; // rax
  SXVWGEOM *v669; // rax
  unsigned int v670; // eax
  struct IMsoOLDocument *v671; // r10
  int v672; // eax
  int v673; // ebx
  struct SH *v674; // rax
  int v675; // esi
  int v676; // ebx
  int v677; // edi
  wchar_t *v678; // rax
  int BookHtml; // eax
  __int64 v680; // rax
  wchar_t **v681; // rdi
  const wchar_t *v682; // rax
  __int64 v683; // rax
  __int64 v684; // rbx
  SXVWGEOM *v685; // rax
  unsigned int v686; // eax
  char v687; // al
  struct SXVIEW *v688; // rax
  struct IMemHeap *v689; // rax
  int v690; // eax
  __int64 v691; // rax
  LXBASE *v692; // rbx
  SXVWGEOM *v693; // rax
  struct SH *v694; // rax
  struct IMsoOLDocument *v695; // rdi
  struct STM *v696; // r14
  struct OpenTelemetry *v697; // rbx
  const wchar_t *v698; // rsi
  wchar_t *v699; // rax
  int v700; // ebx
  __int64 v701; // rax
  wchar_t **v702; // rdi
  const wchar_t *v703; // rax
  BOOL v704; // ebx
  BOOL v705; // r8d
  BOOL v706; // edi
  BOOL v707; // r9d
  __int64 v708; // rax
  __int64 v709; // r10
  const struct OLDocFactory *v710; // rax
  BOOK *v711; // rbx
  SXVWGEOM *v712; // rax
  unsigned int v713; // eax
  __int64 v714; // rcx
  void *v715; // rax
  __int64 v716; // rdx
  unsigned __int8 v717; // al
  unsigned int v718; // eax
  SXVWGEOM *v719; // rax
  unsigned int v720; // eax
  bool v721; // r8
  bool v722; // r13
  __int64 v723; // rax
  LXBASE *v724; // rbx
  SXVWGEOM *v725; // rax
  __int64 v726; // rax
  void *v727; // rax
  __int64 v728; // rax
  int v729; // eax
  char v730; // r12
  Mso::DocumentWindow::EventMgr *v731; // rcx
  WN *v732; // rcx
  UIFRAME *v733; // rax
  struct IMsoOLDocument *v734; // rbx
  Excel::XlMso *v735; // rax
  HWND v736; // r8
  struct IMsoOLDocument *v737; // rax
  struct Api::CoauthTransitionState *v738; // rbx
  unsigned int v739; // eax
  struct Api::Workbook *v740; // rax
  struct XlFileProtocol *Protocol; // rbx
  MsoReserveTag *v742; // rax
  struct BOOK *v743; // rdi
  unsigned int v744; // ebx
  struct SH *v745; // rax
  __int64 v746; // rax
  __int64 v747; // rdx
  _DWORD *v748; // rax
  __int64 v749; // rax
  struct Api::Workbook *v750; // rax
  XlAsyncFileIO *v751; // rax
  XlRenameHandler *v752; // rax
  unsigned int v753; // ebx
  __int64 v754; // rax
  __int64 v755; // rax
  struct Api::Workbook *v756; // rax
  struct IMerge *v757; // rax
  __int64 v758; // rax
  __int64 v759; // rax
  struct Api::Workbook *v760; // rax
  struct Mso::Telemetry::IDataFieldCollection *v761; // rbx
  unsigned int refreshed; // eax
  __int64 v763; // rax
  IEndpointAgent *v764; // rax
  ClassifyLabelProtectManager *v765; // rax
  IdleLoop *v766; // rcx
  __int64 v767; // rax
  AutoSaveManager *v768; // rax
  struct BOOKO *v769; // rdx
  int v770; // eax
  SXVWGEOM *v771; // rax
  unsigned int v772; // r10d
  __int64 v773; // rcx
  struct SH *v774; // r9
  _QWORD *v775; // rax
  __int64 v776; // rcx
  _QWORD *v777; // rdx
  __int64 v778; // rax
  struct WNX *v779; // rdi
  void *v780; // r14
  struct WNX *v781; // rax
  struct WNX *v782; // rbx
  struct WNX *v783; // rdx
  int v784; // ecx
  struct SH *v785; // r12
  SXVWGEOM *v786; // rax
  unsigned int v787; // eax
  __int64 v788; // rdx
  __int64 v789; // rcx
  _QWORD *v790; // r8
  _QWORD *v791; // rdx
  __int64 v792; // rdx
  __int64 v793; // rcx
  __int64 v794; // rax
  struct CS *v795; // rax
  SXVWGEOM *v796; // rax
  unsigned int v797; // eax
  __int64 v798; // rdx
  __int64 v799; // rcx
  _QWORD *v800; // r8
  _QWORD *v801; // rdx
  unsigned int v802; // edx
  MsoReserveTag *v803; // rcx
  __int64 v804; // rax
  __int64 v805; // r8
  int v806; // eax
  __int64 v807; // rax
  __int64 v808; // rax
  __int64 v809; // r8
  struct BOOK *v810; // r8
  IMsoOLDocument *v811; // rax
  struct IMsoOLDocument *v812; // rax
  struct IMsoOLDocument *v813; // rax
  unsigned int v814; // esi
  __int64 v815; // r14
  SXVWGEOM *v816; // rax
  unsigned int v817; // edi
  unsigned int v818; // ebx
  struct IMsoOLDocument *v819; // rax
  struct IMsoOLDocument *v820; // rax
  SXVWGEOM *v821; // rax
  unsigned int v822; // ebx
  struct IMsoOLDocument *v823; // rax
  struct IMsoOLDocument *v824; // rax
  struct IMsoOLDocument *v825; // rax
  struct IMsoOLDocument *v826; // rax
  struct IMsoOLDocument *v827; // rax
  struct IMsoOLDocument *v828; // rax
  const wchar_t *v829; // rax
  struct IMsoOLDocument *v830; // rax
  void *v831; // rax
  __int64 v832; // r8
  int v833; // eax
  __int64 v834; // rcx
  struct BOOK *v835; // rax
  SXVWGEOM *v836; // rax
  unsigned int v837; // ebx
  struct LXTAB *v838; // rax
  TAB *v839; // rax
  struct SH *v840; // rax
  _QWORD *v841; // rdx
  __int64 v842; // rcx
  _QWORD *v843; // r8
  int v844; // ebx
  const wchar_t *v845; // rax
  struct IMsoOLDocument *v846; // rax
  struct IMsoOLDocument *v847; // rax
  __int64 v848; // rcx
  const wchar_t *v849; // rax
  SXVWGEOM *v850; // rax
  unsigned int v851; // eax
  _QWORD *v852; // rdx
  __int64 v853; // rcx
  _QWORD *v854; // r8
  __int64 v855; // rcx
  struct BOOK *v856; // rcx
  const struct Api::Workbook *v857; // rax
  Excel::AppGuard::Actions **v858; // r8
  int v859; // eax
  wchar_t *v860; // rdi
  char v861; // si
  __int64 v862; // rcx
  struct BOOK *v863; // rbx
  __int64 v864; // r8
  SXVWGEOM *v865; // rax
  unsigned int v866; // eax
  _QWORD *v867; // r8
  __int64 v868; // rcx
  _QWORD *v869; // rdx
  __int64 v870; // rcx
  __int64 v871; // rax
  __int64 v872; // rcx
  __int64 v873; // rcx
  __int64 v874; // r8
  __int64 v875; // rax
  SXVWGEOM *v876; // rax
  unsigned int v877; // eax
  _QWORD *v878; // rdx
  __int64 v879; // rcx
  _QWORD *v880; // r8
  SXVWGEOM *v881; // rax
  unsigned int v882; // eax
  _QWORD *v883; // rdx
  __int64 v884; // rcx
  _QWORD *v885; // r8
  void *v886; // rax
  void *v887; // rax
  __int64 v888; // rcx
  __int64 v889; // rcx
  int v890; // eax
  __int64 v891; // rcx
  struct IMsoOLDocument *v892; // rax
  __int64 v893; // rcx
  struct IMsoOLDocument *v894; // rax
  SXVWGEOM *v895; // rax
  unsigned int v896; // eax
  __int64 v897; // rcx
  __int64 v898; // rax
  SXVWGEOM *v899; // rax
  unsigned int v900; // eax
  const struct Api::Workbook *v901; // rbx
  struct ExpressionService *v902; // rax
  __int64 v903; // rax
  void *v904; // rax
  struct XlsActivity *v905; // rbx
  const struct Api::Workbook *v906; // rax
  struct LXTAB *v907; // rbx
  TAB *v908; // rbx
  struct SH *v909; // rax
  unsigned __int8 v910; // cl
  struct SH *v911; // rax
  struct Mso::Telemetry::IDataFieldCollection *v912; // rax
  struct Mso::Telemetry::IDataFieldCollection *v913; // rax
  SXVWGEOM *v914; // rax
  unsigned int v915; // eax
  _QWORD *v916; // rdx
  __int64 v917; // rcx
  _QWORD *v918; // r8
  const wchar_t *v919; // rax
  __int64 v920; // rax
  OlDocFilePath *v921; // rax
  struct IMsoOLDocument *v922; // rbx
  SXVWGEOM *v923; // rax
  unsigned int v924; // eax
  SXVWGEOM *v925; // rax
  unsigned int v926; // eax
  __int64 v927; // rax
  __int64 v928; // rcx
  struct Api::Workbook *v929; // rax
  struct Mso::Telemetry::IDataFieldCollection *v930; // rax
  __int64 v931; // r8
  int v932; // edx
  unsigned __int64 v933; // rax
  struct IMsoOLDocument *v934; // rax
  CardView::DataElementRecord *v935; // rax
  PivotMetadataCache *v936; // rax
  OcsTransitionController *v937; // rax
  struct Api::CoauthTransitionState *v938; // rax
  struct IMsoOLDocument *v939; // rax
  char v940; // bl
  BKORWS *v941; // rdi
  CardView::DataElementRecord *v942; // rax
  struct SH *v943; // rbx
  __int64 v944; // rax
  struct SH *v945; // rbx
  struct Api::Workbook *v946; // rax
  struct QuickLoadContext *v947; // r8
  struct IMemHeap *v948; // rbx
  unsigned int v949; // edi
  struct Api::Workbook *v950; // rax
  XlAsyncFileIO *v951; // rax
  __int64 v952; // rax
  int v953; // eax
  bool v954; // cf
  __int64 v955; // r8
  struct Api::CoauthTransitionState *v956; // rax
  __int64 v957; // rax
  struct Api::Workbook *v958; // rax
  struct Api::Workbook *v959; // rbx
  const struct WN *v960; // r8
  struct IMemHeap *v961; // rdi
  struct BOOK *v962; // rcx
  unsigned int v963; // ebx
  ZrtUtility *v964; // rax
  int v965; // r9d
  __int64 v966; // rax
  BKORWS *v967; // rbx
  QuickLoadContext *v968; // rax
  const wchar_t *v969; // rbx
  __int64 v970; // rcx
  const struct BOOK *v971; // rcx
  int Only; // eax
  int v973; // ecx
  int v974; // r8d
  struct BOOK *v975; // rdi
  __int64 v976; // rax
  __int64 v977; // rax
  BOOL v978; // ebx
  struct IMsoOLDocument *v979; // rax
  bool v980; // bl
  unsigned int v981; // eax
  struct IMsoOLDocument *v982; // rax
  struct IMsoOLDocument *v983; // rax
  Api::RichDataSharedManager *v984; // rax
  Api::LinkedEntityFeature *LinkedEntityFeature; // rax
  RichDataManagerHost *v986; // rax
  const struct Api::Workbook *v987; // rdx
  CleanupWorkbookStylesBusinessBar *v988; // rax
  struct Api::Workbook *v989; // rdx
  unsigned __int64 v990; // rbx
  unsigned int v991; // eax
  char v992; // al
  struct OSRC *Osrc; // rax
  int v994; // eax
  unsigned int v995; // edx
  CorruptionMetaData *v996; // rax
  char v997; // al
  LoadRecovery *v998; // rcx
  int v999; // edx
  unsigned __int64 v1000; // rax
  int v1001; // ebx
  bool v1002; // al
  unsigned __int64 BookCorrupt; // rbx
  void *v1004; // rax
  unsigned __int64 v1005; // rax
  __int64 v1006; // rcx
  unsigned int v1007; // eax
  int v1008; // ebx
  const wchar_t *v1009; // rax
  int v1010; // r8d
  __int64 v1011; // r8
  wchar_t *v1012; // rbx
  const wchar_t *v1013; // rbx
  unsigned int v1014; // eax
  struct IMsoOLDocument **v1015; // rbx
  SXVWGEOM *v1016; // rax
  unsigned int v1017; // eax
  OlDocFilePath *v1018; // rax
  struct IMsoOLDocument **v1019; // rbx
  SXVWGEOM *v1020; // rax
  unsigned int v1021; // eax
  SXVWGEOM *v1022; // rax
  unsigned int v1023; // eax
  unsigned int v1024; // edx
  int v1025; // ecx
  int v1026; // eax
  unsigned int v1027; // edx
  int v1028; // eax
  int v1029; // ecx
  char v1030; // al
  unsigned int v1031; // eax
  unsigned __int64 Count; // rax
  UIFRAME *v1033; // rax
  HWND v1034; // rax
  __int64 v1035; // rax
  __int64 v1036; // rbx
  SXVWGEOM *v1037; // rax
  unsigned int v1038; // eax
  __int64 v1039; // rax
  __int64 v1040; // rax
  __int64 v1041; // rax
  __int64 v1042; // rax
  SXVWGEOM *v1043; // rax
  unsigned int v1044; // eax
  unsigned int v1045; // edx
  SXVWGEOM *v1046; // rax
  unsigned int v1047; // eax
  int v1048; // eax
  __int64 Title; // rax
  __int64 v1050; // rdx
  __int64 v1051; // rsi
  SXVWGEOM *v1052; // rax
  int v1053; // ebx
  Mso::Telemetry *v1054; // rax
  unsigned int v1055; // r9d
  int v1056; // eax
  __int64 v1057; // r8
  SXVWGEOM *v1058; // rax
  unsigned int v1059; // eax
  const wchar_t *v1060; // rax
  struct IMsoOLDocument *v1061; // rax
  __int64 v1062; // rdx
  ZrtUtility *v1063; // rax
  struct IMsoOLDocument *v1064; // rdx
  __int64 v1065; // rax
  CorruptionMetaData *v1066; // rax
  unsigned __int8 v1067; // al
  __int64 v1068; // r9
  __int64 v1069; // r8
  struct IMsoOLDocument *v1070; // rax
  struct BOOK *v1071; // r8
  int v1072; // eax
  CorruptionMetaData *v1073; // rax
  Mso::History *v1074; // rcx
  int v1075; // ecx
  int v1076; // ecx
  unsigned int v1077; // edx
  wchar_t *v1078; // rdx
  int v1079; // ecx
  ODFROBUSTLOAD *AffectedProcessSessionId; // rax
  wchar_t *v1081; // rdx
  int v1082; // ecx
  ODFROBUSTLOAD *v1083; // rax
  ODFROBUSTLOAD *v1084; // rax
  __int64 v1085; // rax
  __int64 v1086; // r8
  struct Api::Workbook *v1087; // rax
  struct IPowerQueryWorkbookManager *Manager; // rax
  struct IMsoOLDocument *v1089; // rax
  __int64 v1090; // rcx
  unsigned int v1091; // eax
  unsigned int v1092; // ebx
  int v1093; // eax
  int v1094; // edx
  int v1095; // eax
  __int64 v1096; // rax
  SXVWGEOM *v1097; // rax
  unsigned int v1098; // eax
  __int64 v1099; // r8
  __int64 v1100; // rax
  __int64 v1101; // rax
  int Sz; // ebx
  int v1103; // eax
  __int64 *v1104; // rcx
  int v1105; // ebx
  __int64 v1106; // rcx
  int v1107; // edx
  __int64 v1108; // rcx
  int v1109; // eax
  unsigned int v1110; // eax
  SXVWGEOM *v1111; // rax
  unsigned int v1112; // eax
  bool v1113; // dl
  SXVWGEOM *v1114; // rax
  SXVWGEOM *v1115; // rax
  unsigned int v1116; // eax
  const wchar_t *v1117; // rax
  SXVWGEOM *v1118; // rax
  unsigned int v1119; // eax
  _QWORD *v1120; // rdx
  __int64 v1121; // rcx
  __int64 v1122; // rax
  __int64 v1123; // rdx
  __int64 v1124; // rdx
  __int64 v1125; // rdx
  struct IStream **v1126; // [rsp+20h] [rbp-140h]
  struct IStream **v1127; // [rsp+20h] [rbp-140h]
  struct IStream **v1128; // [rsp+28h] [rbp-138h]
  struct IStream **v1129; // [rsp+28h] [rbp-138h]
  wchar_t *v1130; // [rsp+30h] [rbp-130h]
  struct LoadRecovery *v1131; // [rsp+38h] [rbp-128h]
  struct LoadRecovery *v1132; // [rsp+38h] [rbp-128h]
  struct XlsActivity *v1133; // [rsp+40h] [rbp-120h]
  struct XlsActivity *v1134; // [rsp+40h] [rbp-120h]
  wchar_t *v1135; // [rsp+48h] [rbp-118h]
  struct ENV *v1136; // [rsp+48h] [rbp-118h]
  struct OpenTelemetry *v1137; // [rsp+50h] [rbp-110h]
  bool v1138; // [rsp+50h] [rbp-110h]
  struct LoadRecovery *v1139; // [rsp+58h] [rbp-108h]
  struct IMsoDocumentEncryptor *v1140; // [rsp+60h] [rbp-100h]
  bool v1141; // [rsp+68h] [rbp-F8h]
  struct IMsoOLDocument *v1142; // [rsp+70h] [rbp-F0h]
  const wchar_t *v1143; // [rsp+78h] [rbp-E8h]
  struct VersionHistoryWindowParams *v1144; // [rsp+80h] [rbp-E0h]
  struct BOOK *v1145; // [rsp+80h] [rbp-E0h]
  bool v1146; // [rsp+88h] [rbp-D8h]
  int v1147[2]; // [rsp+90h] [rbp-D0h]
  int v1148; // [rsp+90h] [rbp-D0h]
  bool v1149; // [rsp+A0h] [rbp-C0h]
  int v1150; // [rsp+A8h] [rbp-B8h]
  int v1151; // [rsp+C0h] [rbp-A0h]
  int *v1152; // [rsp+C0h] [rbp-A0h]
  char v1153; // [rsp+E0h] [rbp-80h]
  int v1154; // [rsp+E4h] [rbp-7Ch]
  int v1155; // [rsp+E8h] [rbp-78h] BYREF
  bool v1156; // [rsp+ECh] [rbp-74h]
  unsigned __int8 v1157; // [rsp+EDh] [rbp-73h] BYREF
  struct BOOK *lp; // [rsp+F0h] [rbp-70h] BYREF
  struct IMsoOLDocument *v1159; // [rsp+F8h] [rbp-68h] BYREF
  wchar_t *v1160; // [rsp+100h] [rbp-60h]
  bool v1161; // [rsp+108h] [rbp-58h]
  wchar_t *v1162; // [rsp+110h] [rbp-50h]
  struct IMsoOLDocument **v1163; // [rsp+118h] [rbp-48h]
  char v1164; // [rsp+120h] [rbp-40h]
  char v1165; // [rsp+121h] [rbp-3Fh]
  char v1166; // [rsp+122h] [rbp-3Eh]
  bool v1167; // [rsp+123h] [rbp-3Dh]
  int v1168; // [rsp+124h] [rbp-3Ch] BYREF
  struct STM *v1169; // [rsp+128h] [rbp-38h] BYREF
  char v1170; // [rsp+130h] [rbp-30h]
  char v1171; // [rsp+131h] [rbp-2Fh]
  char v1172; // [rsp+132h] [rbp-2Eh]
  int v1173; // [rsp+134h] [rbp-2Ch]
  int v1174; // [rsp+138h] [rbp-28h] BYREF
  bool v1175; // [rsp+13Ch] [rbp-24h]
  char v1176; // [rsp+13Dh] [rbp-23h]
  bool v1177; // [rsp+13Eh] [rbp-22h]
  bool v1178; // [rsp+13Fh] [rbp-21h] BYREF
  int v1179; // [rsp+140h] [rbp-20h] BYREF
  int v1180; // [rsp+144h] [rbp-1Ch]
  __int64 v1181; // [rsp+148h] [rbp-18h] BYREF
  bool v1182; // [rsp+150h] [rbp-10h]
  bool v1183; // [rsp+151h] [rbp-Fh]
  bool v1184; // [rsp+152h] [rbp-Eh]
  bool v1185; // [rsp+153h] [rbp-Dh]
  char v1186; // [rsp+154h] [rbp-Ch]
  unsigned int v1187; // [rsp+158h] [rbp-8h]
  char v1188; // [rsp+15Ch] [rbp-4h]
  int v1189; // [rsp+160h] [rbp+0h] BYREF
  char v1190; // [rsp+164h] [rbp+4h]
  bool v1191; // [rsp+165h] [rbp+5h]
  char v1192; // [rsp+168h] [rbp+8h] BYREF
  char v1193; // [rsp+169h] [rbp+9h]
  bool v1194[4]; // [rsp+16Ch] [rbp+Ch] BYREF
  bool v1195; // [rsp+170h] [rbp+10h] BYREF
  int v1196; // [rsp+174h] [rbp+14h] BYREF
  int v1197; // [rsp+178h] [rbp+18h] BYREF
  unsigned int v1198; // [rsp+17Ch] [rbp+1Ch] BYREF
  struct BOOK *v1199; // [rsp+180h] [rbp+20h] BYREF
  bool v1200; // [rsp+188h] [rbp+28h] BYREF
  char v1201; // [rsp+189h] [rbp+29h]
  bool v1202; // [rsp+18Ah] [rbp+2Ah]
  unsigned __int8 v1203; // [rsp+18Bh] [rbp+2Bh]
  char v1204; // [rsp+18Ch] [rbp+2Ch]
  bool v1205; // [rsp+18Dh] [rbp+2Dh] BYREF
  bool v1206; // [rsp+18Eh] [rbp+2Eh] BYREF
  char v1207; // [rsp+18Fh] [rbp+2Fh] BYREF
  char v1208; // [rsp+190h] [rbp+30h] BYREF
  bool v1209; // [rsp+191h] [rbp+31h] BYREF
  char v1210; // [rsp+194h] [rbp+34h] BYREF
  char v1211; // [rsp+195h] [rbp+35h]
  int v1212; // [rsp+198h] [rbp+38h]
  char v1213; // [rsp+19Ch] [rbp+3Ch]
  bool v1214; // [rsp+19Dh] [rbp+3Dh] BYREF
  XlsActivity *v1215; // [rsp+1A0h] [rbp+40h] BYREF
  int v1216; // [rsp+1A8h] [rbp+48h]
  struct STGI *v1217; // [rsp+1B0h] [rbp+50h]
  int v1218; // [rsp+1B8h] [rbp+58h] BYREF
  int v1219; // [rsp+1BCh] [rbp+5Ch]
  int v1220; // [rsp+1C0h] [rbp+60h] BYREF
  int v1221; // [rsp+1C4h] [rbp+64h] BYREF
  struct ENV *v1222; // [rsp+1C8h] [rbp+68h]
  bool v1223; // [rsp+1D0h] [rbp+70h] BYREF
  int v1224; // [rsp+1D4h] [rbp+74h] BYREF
  int v1225; // [rsp+1D8h] [rbp+78h] BYREF
  int v1226; // [rsp+1E0h] [rbp+80h]
  bool v1227; // [rsp+1E8h] [rbp+88h]
  char v1228; // [rsp+1E9h] [rbp+89h]
  char v1229; // [rsp+1EAh] [rbp+8Ah] BYREF
  char v1230; // [rsp+1EBh] [rbp+8Bh] BYREF
  int v1231; // [rsp+1ECh] [rbp+8Ch] BYREF
  int v1232; // [rsp+1F0h] [rbp+90h] BYREF
  int v1233; // [rsp+1F4h] [rbp+94h]
  unsigned int v1234; // [rsp+1F8h] [rbp+98h] BYREF
  wchar_t *v1235; // [rsp+200h] [rbp+A0h]
  char v1236[8]; // [rsp+208h] [rbp+A8h] BYREF
  int v1237; // [rsp+210h] [rbp+B0h] BYREF
  int v1238; // [rsp+218h] [rbp+B8h]
  _BYTE *v1239; // [rsp+220h] [rbp+C0h]
  BOOL v1240; // [rsp+228h] [rbp+C8h]
  int v1241; // [rsp+230h] [rbp+D0h]
  int v1242; // [rsp+234h] [rbp+D4h] BYREF
  _BYTE v1243[4]; // [rsp+238h] [rbp+D8h] BYREF
  unsigned int v1244; // [rsp+23Ch] [rbp+DCh]
  int v1245; // [rsp+240h] [rbp+E0h] BYREF
  void *v1246; // [rsp+248h] [rbp+E8h] BYREF
  struct IMsoOLDocument **v1247; // [rsp+250h] [rbp+F0h]
  struct IMsoPKMClient *v1248; // [rsp+258h] [rbp+F8h] BYREF
  int v1249; // [rsp+260h] [rbp+100h]
  int v1250; // [rsp+264h] [rbp+104h] BYREF
  int v1251; // [rsp+268h] [rbp+108h]
  int v1252; // [rsp+26Ch] [rbp+10Ch] BYREF
  struct IMsoDocumentEncryptor *v1253; // [rsp+270h] [rbp+110h] BYREF
  struct IMsoOpTimer *v1254; // [rsp+278h] [rbp+118h] BYREF
  HANDLE hObject; // [rsp+280h] [rbp+120h] BYREF
  int v1256; // [rsp+288h] [rbp+128h]
  _BYTE v1257[2]; // [rsp+28Ch] [rbp+12Ch] BYREF
  __int16 v1258; // [rsp+28Eh] [rbp+12Eh] BYREF
  unsigned int v1259; // [rsp+290h] [rbp+130h] BYREF
  BOOL v1260; // [rsp+294h] [rbp+134h]
  int v1261; // [rsp+298h] [rbp+138h] BYREF
  int v1262; // [rsp+29Ch] [rbp+13Ch] BYREF
  int v1263; // [rsp+2A0h] [rbp+140h] BYREF
  int v1264; // [rsp+2A4h] [rbp+144h] BYREF
  int v1265; // [rsp+2A8h] [rbp+148h] BYREF
  int v1266; // [rsp+2ACh] [rbp+14Ch] BYREF
  __int64 v1267; // [rsp+2B0h] [rbp+150h] BYREF
  struct XLXMLMAP *v1268; // [rsp+2B8h] [rbp+158h] BYREF
  const wchar_t *v1269; // [rsp+2C0h] [rbp+160h]
  struct SH *v1270; // [rsp+2C8h] [rbp+168h]
  struct REVERT *v1271; // [rsp+2D0h] [rbp+170h] BYREF
  wchar_t *v1272; // [rsp+2D8h] [rbp+178h]
  int v1273; // [rsp+2E0h] [rbp+180h] BYREF
  __int64 v1274; // [rsp+2E8h] [rbp+188h] BYREF
  struct VersionHistoryWindowParams *v1275; // [rsp+2F0h] [rbp+190h]
  BKORWS *v1276; // [rsp+2F8h] [rbp+198h]
  struct WNX *v1277; // [rsp+300h] [rbp+1A0h]
  struct IMsoUrl *v1278; // [rsp+308h] [rbp+1A8h] BYREF
  int v1279; // [rsp+310h] [rbp+1B0h] BYREF
  int v1280; // [rsp+314h] [rbp+1B4h] BYREF
  int v1281; // [rsp+318h] [rbp+1B8h] BYREF
  int v1282; // [rsp+31Ch] [rbp+1BCh]
  int v1283; // [rsp+320h] [rbp+1C0h] BYREF
  int v1284; // [rsp+324h] [rbp+1C4h] BYREF
  int v1285; // [rsp+328h] [rbp+1C8h] BYREF
  int v1286; // [rsp+32Ch] [rbp+1CCh] BYREF
  int v1287; // [rsp+330h] [rbp+1D0h] BYREF
  int v1288; // [rsp+334h] [rbp+1D4h] BYREF
  int v1289; // [rsp+338h] [rbp+1D8h] BYREF
  int v1290; // [rsp+33Ch] [rbp+1DCh] BYREF
  int v1291; // [rsp+340h] [rbp+1E0h] BYREF
  int v1292; // [rsp+344h] [rbp+1E4h] BYREF
  int v1293; // [rsp+348h] [rbp+1E8h] BYREF
  int v1294; // [rsp+34Ch] [rbp+1ECh] BYREF
  struct IStorage *v1295; // [rsp+350h] [rbp+1F0h] BYREF
  wchar_t *Src; // [rsp+358h] [rbp+1F8h]
  char v1297[8]; // [rsp+360h] [rbp+200h] BYREF
  struct IMemHeap *v1298; // [rsp+368h] [rbp+208h]
  SH *v1299; // [rsp+370h] [rbp+210h]
  __int64 v1300; // [rsp+378h] [rbp+218h]
  struct IMsoOLDocument *v1301; // [rsp+380h] [rbp+220h] BYREF
  struct IMemHeap *v1302; // [rsp+388h] [rbp+228h] BYREF
  __int64 v1303; // [rsp+390h] [rbp+230h]
  struct BOOK *v1304; // [rsp+398h] [rbp+238h]
  struct SH *v1305; // [rsp+3A0h] [rbp+240h]
  int v1306; // [rsp+3A8h] [rbp+248h] BYREF
  _BYTE v1307[128]; // [rsp+3B0h] [rbp+250h] BYREF
  struct IStream *v1308; // [rsp+430h] [rbp+2D0h] BYREF
  struct STM *v1309; // [rsp+438h] [rbp+2D8h] BYREF
  unsigned __int64 v1310; // [rsp+440h] [rbp+2E0h]
  char v1311[8]; // [rsp+448h] [rbp+2E8h] BYREF
  char v1312[8]; // [rsp+450h] [rbp+2F0h] BYREF
  __int64 v1313; // [rsp+458h] [rbp+2F8h] BYREF
  struct IStream *v1314; // [rsp+460h] [rbp+300h] BYREF
  _BYTE v1315[40]; // [rsp+468h] [rbp+308h] BYREF
  int v1316; // [rsp+490h] [rbp+330h] BYREF
  int v1317; // [rsp+494h] [rbp+334h]
  int v1318; // [rsp+498h] [rbp+338h]
  int v1319; // [rsp+49Ch] [rbp+33Ch] BYREF
  int v1320; // [rsp+4A0h] [rbp+340h]
  int v1321; // [rsp+4A4h] [rbp+344h] BYREF
  unsigned int v1322; // [rsp+4A8h] [rbp+348h] BYREF
  int v1323; // [rsp+4ACh] [rbp+34Ch] BYREF
  int v1324; // [rsp+4B0h] [rbp+350h]
  int v1325; // [rsp+4B4h] [rbp+354h] BYREF
  int v1326; // [rsp+4B8h] [rbp+358h] BYREF
  int v1327; // [rsp+4BCh] [rbp+35Ch] BYREF
  int v1328; // [rsp+4C0h] [rbp+360h] BYREF
  int v1329; // [rsp+4C4h] [rbp+364h] BYREF
  Api::ReloadContext *v1330; // [rsp+4C8h] [rbp+368h] BYREF
  char v1331[8]; // [rsp+4D0h] [rbp+370h] BYREF
  struct Api::ReloadContext *v1332; // [rsp+4D8h] [rbp+378h] BYREF
  struct WNX *v1333; // [rsp+4E0h] [rbp+380h]
  struct IMsoOLDocument *v1334; // [rsp+4E8h] [rbp+388h] BYREF
  __int64 v1335; // [rsp+4F0h] [rbp+390h]
  int *v1336; // [rsp+4F8h] [rbp+398h]
  int v1337; // [rsp+500h] [rbp+3A0h] BYREF
  _BYTE v1338[24]; // [rsp+508h] [rbp+3A8h] BYREF
  int v1339; // [rsp+520h] [rbp+3C0h] BYREF
  char v1340[8]; // [rsp+528h] [rbp+3C8h] BYREF
  _BYTE v1341[40]; // [rsp+530h] [rbp+3D0h] BYREF
  _BYTE v1342[40]; // [rsp+558h] [rbp+3F8h] BYREF
  unsigned __int64 v1343; // [rsp+580h] [rbp+420h]
  struct CVINFO *v1344; // [rsp+588h] [rbp+428h] BYREF
  char v1345[8]; // [rsp+590h] [rbp+430h] BYREF
  _BYTE v1346[16]; // [rsp+598h] [rbp+438h] BYREF
  struct SHTI *v1347; // [rsp+5A8h] [rbp+448h] BYREF
  struct IMsoOLDocument *v1348; // [rsp+5B0h] [rbp+450h] BYREF
  char v1349[8]; // [rsp+5B8h] [rbp+458h] BYREF
  _BYTE v1350[40]; // [rsp+5C0h] [rbp+460h] BYREF
  struct IMsoOLDocument *v1351; // [rsp+5E8h] [rbp+488h]
  _BYTE v1352[40]; // [rsp+5F0h] [rbp+490h] BYREF
  _BYTE v1353[32]; // [rsp+618h] [rbp+4B8h] BYREF
  char v1354; // [rsp+638h] [rbp+4D8h] BYREF
  char v1355; // [rsp+63Ch] [rbp+4DCh] BYREF
  char v1356; // [rsp+640h] [rbp+4E0h] BYREF
  char v1357; // [rsp+644h] [rbp+4E4h] BYREF
  char v1358; // [rsp+648h] [rbp+4E8h] BYREF
  char v1359[4]; // [rsp+64Ch] [rbp+4ECh] BYREF
  char v1360; // [rsp+650h] [rbp+4F0h] BYREF
  char v1361; // [rsp+654h] [rbp+4F4h] BYREF
  char v1362[4]; // [rsp+658h] [rbp+4F8h] BYREF
  char v1363[4]; // [rsp+65Ch] [rbp+4FCh] BYREF
  char v1364; // [rsp+660h] [rbp+500h] BYREF
  char v1365[4]; // [rsp+664h] [rbp+504h] BYREF
  char v1366; // [rsp+668h] [rbp+508h] BYREF
  char v1367; // [rsp+66Ch] [rbp+50Ch] BYREF
  char v1368[4]; // [rsp+670h] [rbp+510h] BYREF
  char v1369[4]; // [rsp+674h] [rbp+514h] BYREF
  char v1370[4]; // [rsp+678h] [rbp+518h] BYREF
  char v1371[4]; // [rsp+67Ch] [rbp+51Ch] BYREF
  char v1372[4]; // [rsp+680h] [rbp+520h] BYREF
  int v1373; // [rsp+684h] [rbp+524h]
  int v1374; // [rsp+688h] [rbp+528h]
  int v1375; // [rsp+68Ch] [rbp+52Ch]
  char v1376[4]; // [rsp+690h] [rbp+530h] BYREF
  char v1377[4]; // [rsp+694h] [rbp+534h] BYREF
  char v1378[4]; // [rsp+698h] [rbp+538h] BYREF
  char v1379[4]; // [rsp+69Ch] [rbp+53Ch] BYREF
  char v1380[4]; // [rsp+6A0h] [rbp+540h] BYREF
  char v1381[4]; // [rsp+6A4h] [rbp+544h] BYREF
  char v1382[4]; // [rsp+6A8h] [rbp+548h] BYREF
  char v1383[4]; // [rsp+6ACh] [rbp+54Ch] BYREF
  char v1384[4]; // [rsp+6B0h] [rbp+550h] BYREF
  char v1385[4]; // [rsp+6B4h] [rbp+554h] BYREF
  char v1386[4]; // [rsp+6B8h] [rbp+558h] BYREF
  char v1387[4]; // [rsp+6BCh] [rbp+55Ch] BYREF
  char v1388[4]; // [rsp+6C0h] [rbp+560h] BYREF
  char v1389[4]; // [rsp+6C4h] [rbp+564h] BYREF
  char v1390[4]; // [rsp+6C8h] [rbp+568h] BYREF
  char v1391[4]; // [rsp+6CCh] [rbp+56Ch] BYREF
  char v1392[4]; // [rsp+6D0h] [rbp+570h] BYREF
  char v1393[4]; // [rsp+6D4h] [rbp+574h] BYREF
  char v1394[4]; // [rsp+6D8h] [rbp+578h] BYREF
  char v1395[4]; // [rsp+6DCh] [rbp+57Ch] BYREF
  char v1396[4]; // [rsp+6E0h] [rbp+580h] BYREF
  char v1397[4]; // [rsp+6E4h] [rbp+584h] BYREF
  char v1398[4]; // [rsp+6E8h] [rbp+588h] BYREF
  char v1399; // [rsp+6ECh] [rbp+58Ch] BYREF
  char v1400[4]; // [rsp+6F0h] [rbp+590h] BYREF
  char v1401[4]; // [rsp+6F4h] [rbp+594h] BYREF
  char v1402[4]; // [rsp+6F8h] [rbp+598h] BYREF
  char v1403[4]; // [rsp+6FCh] [rbp+59Ch] BYREF
  char v1404[4]; // [rsp+700h] [rbp+5A0h] BYREF
  char v1405[4]; // [rsp+704h] [rbp+5A4h] BYREF
  char v1406[4]; // [rsp+708h] [rbp+5A8h] BYREF
  char v1407[4]; // [rsp+70Ch] [rbp+5ACh] BYREF
  char v1408[4]; // [rsp+710h] [rbp+5B0h] BYREF
  char v1409[4]; // [rsp+714h] [rbp+5B4h] BYREF
  char v1410[4]; // [rsp+718h] [rbp+5B8h] BYREF
  char v1411[4]; // [rsp+71Ch] [rbp+5BCh] BYREF
  char v1412[4]; // [rsp+720h] [rbp+5C0h] BYREF
  char v1413[4]; // [rsp+724h] [rbp+5C4h] BYREF
  char v1414[4]; // [rsp+728h] [rbp+5C8h] BYREF
  char v1415[4]; // [rsp+72Ch] [rbp+5CCh] BYREF
  char v1416[4]; // [rsp+730h] [rbp+5D0h] BYREF
  char v1417[4]; // [rsp+734h] [rbp+5D4h] BYREF
  char v1418[4]; // [rsp+738h] [rbp+5D8h] BYREF
  char v1419[4]; // [rsp+73Ch] [rbp+5DCh] BYREF
  char v1420[4]; // [rsp+740h] [rbp+5E0h] BYREF
  char v1421[4]; // [rsp+744h] [rbp+5E4h] BYREF
  char v1422[4]; // [rsp+748h] [rbp+5E8h] BYREF
  char v1423[4]; // [rsp+74Ch] [rbp+5ECh] BYREF
  char v1424[4]; // [rsp+750h] [rbp+5F0h] BYREF
  char v1425[4]; // [rsp+754h] [rbp+5F4h] BYREF
  char v1426[4]; // [rsp+758h] [rbp+5F8h] BYREF
  char v1427[4]; // [rsp+75Ch] [rbp+5FCh] BYREF
  char v1428[4]; // [rsp+760h] [rbp+600h] BYREF
  char v1429[4]; // [rsp+764h] [rbp+604h] BYREF
  char v1430[4]; // [rsp+768h] [rbp+608h] BYREF
  char v1431[4]; // [rsp+76Ch] [rbp+60Ch] BYREF
  char v1432[4]; // [rsp+770h] [rbp+610h] BYREF
  char v1433[4]; // [rsp+774h] [rbp+614h] BYREF
  _QWORD *v1434; // [rsp+778h] [rbp+618h] BYREF
  char v1435[8]; // [rsp+780h] [rbp+620h] BYREF
  char v1436[8]; // [rsp+788h] [rbp+628h] BYREF
  __int64 v1437; // [rsp+790h] [rbp+630h] BYREF
  struct XLExpressionService *v1438; // [rsp+798h] [rbp+638h] BYREF
  _BYTE *v1439; // [rsp+7A0h] [rbp+640h] BYREF
  char v1440[8]; // [rsp+7A8h] [rbp+648h] BYREF
  struct IMsoOLDocument *v1441; // [rsp+7B0h] [rbp+650h] BYREF
  struct SH *v1442; // [rsp+7B8h] [rbp+658h] BYREF
  struct IMemHeap *v1443; // [rsp+7C0h] [rbp+660h] BYREF
  __int64 v1444; // [rsp+7C8h] [rbp+668h]
  struct ClpLoadContext *Context; // [rsp+7D0h] [rbp+670h]
  __int64 v1446; // [rsp+7D8h] [rbp+678h]
  __int64 v1447; // [rsp+7E0h] [rbp+680h]
  struct IMsoOLDocument *v1448; // [rsp+7E8h] [rbp+688h]
  __int64 v1449; // [rsp+7F0h] [rbp+690h]
  __int64 v1450; // [rsp+7F8h] [rbp+698h]
  struct SH *v1451; // [rsp+800h] [rbp+6A0h]
  _QWORD v1452[2]; // [rsp+808h] [rbp+6A8h] BYREF
  const char *v1453; // [rsp+818h] [rbp+6B8h] BYREF
  struct SHTI *v1454; // [rsp+820h] [rbp+6C0h] BYREF
  char v1455[4]; // [rsp+828h] [rbp+6C8h] BYREF
  char v1456[4]; // [rsp+82Ch] [rbp+6CCh] BYREF
  char v1457[4]; // [rsp+830h] [rbp+6D0h] BYREF
  char v1458[4]; // [rsp+834h] [rbp+6D4h] BYREF
  char v1459; // [rsp+838h] [rbp+6D8h] BYREF
  char v1460; // [rsp+83Ch] [rbp+6DCh] BYREF
  char v1461; // [rsp+840h] [rbp+6E0h] BYREF
  char v1462[4]; // [rsp+844h] [rbp+6E4h] BYREF
  char v1463; // [rsp+848h] [rbp+6E8h] BYREF
  _BYTE v1464[40]; // [rsp+850h] [rbp+6F0h] BYREF
  char v1465; // [rsp+878h] [rbp+718h] BYREF
  int *v1466; // [rsp+880h] [rbp+720h] BYREF
  wchar_t *v1467; // [rsp+888h] [rbp+728h] BYREF
  int v1468; // [rsp+890h] [rbp+730h]
  struct SH *v1469; // [rsp+898h] [rbp+738h]
  int v1470; // [rsp+8A0h] [rbp+740h]
  void *v1471; // [rsp+8A8h] [rbp+748h]
  struct IMsoOLDocument *v1472; // [rsp+8B0h] [rbp+750h]
  BOOL v1473; // [rsp+8B8h] [rbp+758h]
  unsigned int v1474; // [rsp+8BCh] [rbp+75Ch]
  BOOL v1475; // [rsp+8C0h] [rbp+760h]
  int v1476; // [rsp+8C8h] [rbp+768h]
  struct ISlicerView *v1477; // [rsp+8D0h] [rbp+770h]
  wchar_t *v1478; // [rsp+8D8h] [rbp+778h]
  bool v1479; // [rsp+8E0h] [rbp+780h]
  bool v1480; // [rsp+8E1h] [rbp+781h]
  bool v1481; // [rsp+8E2h] [rbp+782h]
  wchar_t *v1482; // [rsp+8E8h] [rbp+788h]
  _BYTE v1483[40]; // [rsp+8F0h] [rbp+790h] BYREF
  _BYTE v1484[40]; // [rsp+918h] [rbp+7B8h] BYREF
  _BYTE v1485[24]; // [rsp+940h] [rbp+7E0h] BYREF
  _BYTE v1486[24]; // [rsp+958h] [rbp+7F8h] BYREF
  _BYTE v1487[56]; // [rsp+970h] [rbp+810h] BYREF
  _BYTE v1488[16]; // [rsp+9A8h] [rbp+848h] BYREF
  _BYTE v1489[24]; // [rsp+9B8h] [rbp+858h] BYREF
  _BYTE v1490[24]; // [rsp+9D0h] [rbp+870h] BYREF
  _BYTE v1491[24]; // [rsp+9E8h] [rbp+888h] BYREF
  _BYTE v1492[24]; // [rsp+A00h] [rbp+8A0h] BYREF
  _BYTE v1493[40]; // [rsp+A18h] [rbp+8B8h] BYREF
  __int128 v1494; // [rsp+A40h] [rbp+8E0h]
  __int128 v1495; // [rsp+A50h] [rbp+8F0h]
  __int128 v1496; // [rsp+A60h] [rbp+900h]
  __int128 v1497; // [rsp+A70h] [rbp+910h]
  __int128 v1498; // [rsp+A80h] [rbp+920h]
  __int128 v1499; // [rsp+A90h] [rbp+930h]
  __int128 v1500; // [rsp+AA0h] [rbp+940h]
  __int128 v1501; // [rsp+AB0h] [rbp+950h]
  int *v1502; // [rsp+AC0h] [rbp+960h]
  char v1503[8]; // [rsp+AC8h] [rbp+968h] BYREF
  _BYTE v1504[24]; // [rsp+AD0h] [rbp+970h] BYREF
  _BYTE v1505[24]; // [rsp+AE8h] [rbp+988h] BYREF
  _BYTE v1506[24]; // [rsp+B00h] [rbp+9A0h] BYREF
  _BYTE v1507[24]; // [rsp+B18h] [rbp+9B8h] BYREF
  wchar_t *v1508; // [rsp+B30h] [rbp+9D0h]
  __int128 v1509; // [rsp+B40h] [rbp+9E0h] BYREF
  _BYTE v1510[16]; // [rsp+B50h] [rbp+9F0h] BYREF
  _BYTE v1511[40]; // [rsp+B60h] [rbp+A00h] BYREF
  _BYTE v1512[40]; // [rsp+B88h] [rbp+A28h] BYREF
  _BYTE v1513[40]; // [rsp+BB0h] [rbp+A50h] BYREF
  _BYTE v1514[48]; // [rsp+BD8h] [rbp+A78h] BYREF
  _OWORD v1515[2]; // [rsp+C08h] [rbp+AA8h] BYREF
  __int64 v1516; // [rsp+C28h] [rbp+AC8h]
  _BYTE v1517[48]; // [rsp+C30h] [rbp+AD0h] BYREF
  _BYTE v1518[64]; // [rsp+C60h] [rbp+B00h] BYREF
  _BYTE v1519[24]; // [rsp+CA0h] [rbp+B40h] BYREF
  _BYTE v1520[24]; // [rsp+CB8h] [rbp+B58h] BYREF
  _BYTE v1521[80]; // [rsp+CD0h] [rbp+B70h] BYREF
  _QWORD v1522[12]; // [rsp+D20h] [rbp+BC0h] BYREF
  _QWORD v1523[12]; // [rsp+D80h] [rbp+C20h] BYREF
  char v1524[16]; // [rsp+DE0h] [rbp+C80h] BYREF
  char v1525[16]; // [rsp+DF0h] [rbp+C90h] BYREF
  _BYTE v1526[160]; // [rsp+E00h] [rbp+CA0h] BYREF
  _BYTE v1527[40]; // [rsp+EA0h] [rbp+D40h] BYREF
  _BYTE v1528[40]; // [rsp+EC8h] [rbp+D68h] BYREF
  _BYTE v1529[40]; // [rsp+EF0h] [rbp+D90h] BYREF
  _BYTE v1530[56]; // [rsp+F18h] [rbp+DB8h] BYREF
  _BYTE v1531[128]; // [rsp+F50h] [rbp+DF0h] BYREF
  _BYTE v1532[48]; // [rsp+FD0h] [rbp+E70h] BYREF
  _OWORD v1533[8]; // [rsp+1000h] [rbp+EA0h] BYREF
  int *v1534; // [rsp+1080h] [rbp+F20h]
  char v1535; // [rsp+1088h] [rbp+F28h]
  char v1536[32]; // [rsp+1090h] [rbp+F30h] BYREF
  char v1537[32]; // [rsp+10B0h] [rbp+F50h] BYREF
  char v1538[32]; // [rsp+10D0h] [rbp+F70h] BYREF
  char v1539[32]; // [rsp+10F0h] [rbp+F90h] BYREF
  _BYTE v1540[1584]; // [rsp+1110h] [rbp+FB0h] BYREF
  _BYTE v1541[8448]; // [rsp+1740h] [rbp+15E0h] BYREF
  _BYTE v1542[2784]; // [rsp+3840h] [rbp+36E0h] BYREF
  int v1543; // [rsp+4320h] [rbp+41C0h] BYREF
  int v1544; // [rsp+4324h] [rbp+41C4h]
  wchar_t v1545[2086]; // [rsp+4330h] [rbp+41D0h] BYREF
  wchar_t v1546[2090]; // [rsp+537Ch] [rbp+521Ch] BYREF
  struct ISlicerView *v1547; // [rsp+63D0h] [rbp+6270h]
  _BYTE v1548[40]; // [rsp+7430h] [rbp+72D0h] BYREF
  _BYTE v1549[24]; // [rsp+7458h] [rbp+72F8h] BYREF
  char v1550[24]; // [rsp+7470h] [rbp+7310h] BYREF
  unsigned int v1551; // [rsp+7488h] [rbp+7328h]
  unsigned int v1552; // [rsp+748Ch] [rbp+732Ch]
  __int64 v1553; // [rsp+74C0h] [rbp+7360h] BYREF
  int v1554; // [rsp+74C8h] [rbp+7368h]
  jmp_buf Buf; // [rsp+74D0h] [rbp+7370h] BYREF
  __int64 v1556; // [rsp+75D0h] [rbp+7470h] BYREF
  int v1557; // [rsp+75D8h] [rbp+7478h]
  jmp_buf v1558; // [rsp+75E0h] [rbp+7480h] BYREF
  __int64 v1559; // [rsp+76E0h] [rbp+7580h] BYREF
  int v1560; // [rsp+76E8h] [rbp+7588h]
  jmp_buf v1561; // [rsp+76F0h] [rbp+7590h] BYREF
  __int64 v1562; // [rsp+77F0h] [rbp+7690h] BYREF
  int v1563; // [rsp+77F8h] [rbp+7698h]
  jmp_buf v1564; // [rsp+7800h] [rbp+76A0h] BYREF
  _DWORD v1565[196]; // [rsp+7900h] [rbp+77A0h] BYREF
  _BYTE v1566[4720]; // [rsp+7C10h] [rbp+7AB0h] BYREF
  _BYTE v1567[336]; // [rsp+8E80h] [rbp+8D20h] BYREF
  wchar_t v1568[16]; // [rsp+8FD0h] [rbp+8E70h] BYREF
  wchar_t v1569; // [rsp+8FF0h] [rbp+8E90h] BYREF
  wchar_t v1570[263]; // [rsp+8FF2h] [rbp+8E92h] BYREF
  wchar_t v1571[16]; // [rsp+9200h] [rbp+90A0h] BYREF
  wchar_t v1572[264]; // [rsp+9220h] [rbp+90C0h] BYREF
  wchar_t v1573[256]; // [rsp+9430h] [rbp+92D0h] BYREF
  _BYTE v1574[528]; // [rsp+9630h] [rbp+94D0h] BYREF
  wchar_t v1575[256]; // [rsp+9840h] [rbp+96E0h] BYREF
  wchar_t v1576[256]; // [rsp+9A40h] [rbp+98E0h] BYREF
  wchar_t v1577[256]; // [rsp+9C40h] [rbp+9AE0h] BYREF
  wchar_t v1578[264]; // [rsp+9E40h] [rbp+9CE0h] BYREF
  wchar_t v1579[256]; // [rsp+A050h] [rbp+9EF0h] BYREF
  wchar_t String1[2088]; // [rsp+A250h] [rbp+A0F0h] BYREF
  char v1581[528]; // [rsp+B2A0h] [rbp+B140h] BYREF
  wchar_t v1582; // [rsp+B4B0h] [rbp+B350h] BYREF
  _BYTE v1583[4174]; // [rsp+B4B2h] [rbp+B352h] BYREF
  wchar_t v1584[2088]; // [rsp+C500h] [rbp+C3A0h] BYREF
  wchar_t v1585[4112]; // [rsp+D550h] [rbp+D3F0h] BYREF

  v21 = a15;
  v22 = a18;
  v23 = a20;
  v1163 = a9;
  v1247 = a9;
  v1272 = a13;
  v1447 = a14;
  v1269 = a17;
  v1275 = a19;
  v1244 = 0;
  v1162 = a1;
  Src = a1;
  v1226 = a2;
  v1193 = 1;
  v1216 = a4;
  v1335 = a6;
  v1276 = a15;
  v1298 = a18;
  v1336 = a20;
  sub_1402DACDC();
  v1211 = 1;
  v1353[24] = 0;
  v24 = Mso::AB::Optimized::FeatureGate::operator bool(byte_143FDFC20);
  v25 = a16;
  if ( v24 )
  {
    v1230 = 1;
    v1323 = 0;
    std::optional<XlSecurity::XllTelemetry>::~optional<XlSecurity::XllTelemetry>(v1353);
    std::_Optional_construct_base<XlSecurity::XllTelemetry>::_Construct<enum XlSecurity::XllTelemetry::Entry,bool>(
      v1353,
      &v1323,
      &v1230);
    v26 = (Mso::Telemetry::Activity *)std::optional<XlSecurity::XllTelemetry>::operator->(v1353);
    v27 = Mso::Telemetry::Activity::DataFields(v26);
    Mso::Telemetry::IDataFieldCollection::Add<int>(v27, "LoadReason", v25, 4);
  }
  v1194[1] = 0;
  if ( (unsigned __int8)((__int64 (*)(void))CircularReferenceTailValue::FGetFlagsShadowBag)() )
  {
    std::_Optional_destruct_base<SecuritySettings::ExternalLinks::TrustedLocationCacheScope,0>::~_Optional_destruct_base<SecuritySettings::ExternalLinks::TrustedLocationCacheScope,0>(v1194);
    std::_Optional_construct_base<SecuritySettings::ExternalLinks::TrustedLocationCacheScope>::_Construct<>(v1194);
  }
  v1161 = 0;
  v29 = 0;
  if ( *(_QWORD *)&UIGLOBALS::UIGLOBALSCONTAINER::m_posi )
  {
    v28 = *(_QWORD *)(*(_QWORD *)&UIGLOBALS::UIGLOBALSCONTAINER::m_posi + 1568LL);
    if ( v28 )
    {
      if ( (*(_WORD *)(v28 + 12) & 0x4000) != 0 )
        v29 = 1;
    }
  }
  v30 = a10;
  v1155 = 0;
  v1172 = 0;
  v1264 = 0;
  v1271 = 0;
  v1171 = 0;
  v1299 = 0;
  v1270 = 0;
  v1277 = 0;
  v1333 = 0;
  v1268 = 0;
  v1225 = 0;
  lp = 0;
  v1190 = 0;
  v1165 = 0;
  v1294 = 0;
  v1234 = 0;
  v1219 = 0;
  v1232 = 0;
  v1553 = 0;
  v1174 = v29;
  v1320 = a10 & 1;
  v1196 = 256;
  v1324 = a10 & 2;
  v1554 = -1;
  if ( (a10 & 8) == 0 || vpoldocument || v29 )
  {
    if ( !(unsigned int)FOsrc() && !OSRH::m_vpxlosrea )
    {
      v30 = a10;
      v31 = 0;
      goto LABEL_18;
    }
    v30 = a10;
  }
  v31 = 1;
LABEL_18:
  v1251 = v31;
  if ( (v30 & 0x10) != 0
    || *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1712LL)
    || (v32 = 0, v1174) )
  {
    v32 = FOsrc() == 0;
  }
  v1282 = v32;
  hObject = (HANDLE)-1LL;
  v1175 = 0;
  v1220 = 0;
  v1164 = 0;
  v1183 = 0;
  v1248 = 0;
  v1262 = 0;
  v1187 = 0;
  v1182 = 0;
  v1176 = 0;
  v1301 = 0;
  v1191 = 0;
  v1185 = 0;
  v1203 = 0;
  v1177 = 0;
  memset_0(v1574, 0, 0x202u);
  v1212 = 1;
  v1283 = 0;
  v1266 = 0;
  v1227 = a4 != 0;
  v1213 = 0;
  v1253 = 0;
  v1305 = (struct SH *)65534;
  v1237 = 0;
  v1238 = 0;
  v1239 = 0;
  v1240 = 0;
  v1157 = 0;
  v1197 = 0;
  v1188 = 0;
  v1290 = 0;
  v1167 = 0;
  v1166 = 0;
  v33 = CountBooks();
  LOBYTE(v34) = std::weak_ordering::equivalent;
  v1256 = v33;
  v1252 = -2147467259;
  v1178 = 0;
  v1228 = 0;
  v1223 = 0;
  v1434 = TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain;
  std::_Deleted_move_assign<std::_Optional_construct_base<CorruptionMetaData>,CorruptionMetaData>::_Deleted_move_assign<std::_Optional_construct_base<CorruptionMetaData>,CorruptionMetaData>(
    v1540,
    v34,
    &v1434);
  v1273 = 0;
  FishbowlTracker::FishbowlTracker((FishbowlTracker *)v1542, 0);
  OpenWorkbooksTracker::OpenWorkbooksTracker((OpenWorkbooksTracker *)v1436);
  v1200 = 1;
  v1195 = 0;
  v1209 = 0;
  v1201 = 0;
  v1186 = 0;
  v1202 = (a10 & 0x100000) != 0;
  OsfOpenScope::OsfOpenScope((OsfOpenScope *)v1487);
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v1300 = 304;
  if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)ThreadLocalStoragePointer + 304LL) + 2024LL) )
    MsoShipAssertTagProc(39198978);
  v36 = FeatureGateCollectionBase<LoadSaveFeatureGates>::Instance();
  dword_143FDFCE8 = (unsigned __int8)Mso::AB::Optimized::FeatureGate::operator bool(v36 + 8) ^ 1;
  if ( !vfBootInitStartupFolder && !vfBootInstallAddins )
  {
    FeatureGateCollectionBase<PerformanceFeatureGates>::Instance();
    if ( !(unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(&PerformanceFeatureGates::c_cgADO11394021)
      && Mso::PerfScenario::FScenarioActive((Mso::PerfScenario *)&vmsoperfidOfficeXLBoot, v38) )
    {
      Mso::PerfScenario::HrCancelScenario((Mso::PerfScenario *)&vmsoperfidOfficeXLBoot, v40);
    }
    LOBYTE(v39) = 1;
    Mso::BootActivity::SetActivationKind(v39);
  }
  v41 = Mso::PerfScenario::HrBeginScenario((Mso::PerfScenario *)&vmsoperfidOfficeXLFileOpen, v37);
  v1231 = 68;
  v42 = v41 >= 0;
  v1189 = 0;
  v1260 = 0;
  v1344 = 0;
  Dw = iUseSentinelFile;
  v1184 = v42;
  if ( iUseSentinelFile == -1 )
  {
    Dw = MsoDwRegGetDw((const struct _msoreg *)&vmsoridExcelUseSentinelFile);
    iUseSentinelFile = Dw;
  }
  v44 = Dw <= 0;
  if ( Dw < 0 )
  {
    iUseSentinelFile = 0;
    MsoFRegSetDw((const struct _msoreg *)&vmsoridExcelUseSentinelFile, 0);
    v44 = iUseSentinelFile <= 0;
  }
  if ( !v44 && !(unsigned int)FOpenSentinelFile(v1162, 393226, &hObject) )
  {
    *v23 = 0;
LABEL_137:
    OsfOpenScope::~OsfOpenScope((OsfOpenScope *)v1487);
    FishbowlTracker::~FishbowlTracker((FishbowlTracker *)v1542);
    std::_Optional_destruct_base<CorruptionMetaData,0>::~_Optional_destruct_base<CorruptionMetaData,0>(v1540);
    std::_Optional_destruct_base<SecuritySettings::ExternalLinks::TrustedLocationCacheScope,0>::~_Optional_destruct_base<SecuritySettings::ExternalLinks::TrustedLocationCacheScope,0>(v1194);
    std::optional<XlSecurity::XllTelemetry>::~optional<XlSecurity::XllTelemetry>(v1353);
    if ( v1211 )
      sub_141232A50();
    if ( v1193 )
      sub_14240D630(&v1192);
    return 0;
  }
  v45 = (wchar_t *)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
  v1160 = v45;
  v46 = 0;
  if ( v45 )
  {
    memset_0(v45, 0, 0x68u);
    *(_DWORD *)v45 = -1;
    *((_DWORD *)v45 + 1) = -1;
    *((_QWORD *)v45 + 1) = 0;
    *((_QWORD *)v45 + 2) = 0;
    *((_QWORD *)v45 + 3) = 0;
    *((_QWORD *)v45 + 4) = 0;
    *((_QWORD *)v45 + 5) = 0;
    *((_DWORD *)v45 + 12) = -1;
    *((_DWORD *)v45 + 13) = 0;
    *((_QWORD *)v45 + 7) = 0;
    *((_DWORD *)v45 + 17) = 0;
    *((_QWORD *)v45 + 9) = 0;
    *((_BYTE *)v45 + 96) = 0;
    v46 = v45;
    v1235 = v45;
  }
  else
  {
    v45 = 0;
    v1160 = 0;
    v1235 = 0;
  }
  v1302 = 0;
  v1179 = 0;
  v1265 = 0;
  v1521[64] = 0;
  v1343 = 0;
  v1310 = 0;
  if ( v46 )
  {
    memset(v1515, 0, sizeof(v1515));
    v1516 = 0;
    memset_0(v1566, 0, 0x1268u);
    (*(void (__fastcall **)(void *, struct IMemHeap **, _QWORD))(qword_144012CA0 + 8LL))(&qword_144012CA0, &v1302, 0);
    if ( (int)LoadRecovery::HrInit(
                v45,
                v1302,
                *(unsigned int *)(*(_QWORD *)(*(_QWORD *)(v1300 + *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer)
                                            + 872LL)
                                + 104LL),
                v1566,
                v1515) < 0 )
      v45 = 0;
    v1160 = v45;
    v1235 = v45;
  }
  CchStToStz(v1162, &v1582, 2086);
  v1128 = 0;
  v1278 = 0;
  MsoHrCreateUrlSimpleFromUser(&v1278, v1583, 0);
  WriteOpenStartPerfEvent(v1278);
  v1181 = 0;
  v1313 = 0;
  v1274 = 0;
  MeasurementsIdFromPath(v1548, v1583);
  if ( v1163 )
    v47 = *v1163;
  else
    v47 = 0;
  v1508 = &v1582;
  v1509 = *(_OWORD *)RgchView::RgchView(v1524, &v1582);
  v48 = OpenTelemetry::SpotEnsureOpenTelemetry(v1435, TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain, &v1509, v47);
  Mso::TCntPtr<Mso::IRefCounted>::operator=(&v1181, v48);
  Mso::TCntPtr<IWebAddInOptionalProperties>::~TCntPtr<IWebAddInOptionalProperties>(v1435);
  if ( v22 )
  {
    v49 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1181);
    Mso::TCntPtr<OpenFileEventTimings>::operator=<OpenFileEventTimings,void>(
      (char *)v22 + 2824,
      *(_QWORD *)(v49 + 30016));
  }
  v50 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1181);
  v1373 = 520926677;
  v51 = (LXBASE *)(v50 + 576);
  if ( XlDisplayElementInfoAll::FXlClient(v52) && *((_DWORD *)v51 + 7160) == -1 )
    WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v51);
  v53 = (LinkedEntityManager *)Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1181);
  v1215 = LinkedEntityManager::PRefreshManager(v53);
  v1229 = 1;
  v1258 = 1;
  v54 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1181);
  v55 = PAllocateObjectOrNull<Measurements::StartOrContinueCapture,Measurements::Identifier const &,enum Measurements::Scenario,bool>(
          (unsigned int)TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain,
          0,
          v54 + 328,
          (unsigned int)&v1258,
          (__int64)&v1229);
  std::unique_ptr<Measurements::StartOrContinueCapture,HeapDeleter<Measurements::StartOrContinueCapture>>::reset(
    &v1274,
    v55);
  v56 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1181);
  v1374 = 520926676;
  WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo((LXBASE *)(v56 + 576));
  LODWORD(v1501) = v25;
  *(_QWORD *)&v1494 = &v1274;
  v57 = 128;
  *((_QWORD *)&v1494 + 1) = &lp;
  *(_QWORD *)&v1495 = &v1181;
  *((_QWORD *)&v1495 + 1) = &v1215;
  *(_QWORD *)&v1496 = &v1179;
  *((_QWORD *)&v1496 + 1) = &v1155;
  *(_QWORD *)&v1497 = &v1178;
  *((_QWORD *)&v1497 + 1) = v1548;
  *(_QWORD *)&v1498 = &v1157;
  *((_QWORD *)&v1498 + 1) = v1540;
  *(_QWORD *)&v1499 = &v1273;
  *((_QWORD *)&v1499 + 1) = v1542;
  *(_QWORD *)&v1500 = v1436;
  *((_QWORD *)&v1500 + 1) = &v1200;
  *((_QWORD *)&v1501 + 1) = &a10;
  v1502 = &v1174;
  v1533[0] = v1494;
  v1533[1] = v1495;
  v1533[2] = v1496;
  v1533[3] = v1497;
  v1533[4] = v1498;
  v1533[5] = v1499;
  v1533[6] = v1500;
  v1533[7] = v1501;
  v1534 = &v1174;
  LOBYTE(v57) = std::weak_ordering::equivalent;
  v1535 = 1;
  sub_1402DB250(v1526, v57, v1533);
  if ( v1535 )
    sub_1404750A0(v1533);
  LOBYTE(v58) = std::weak_ordering::equivalent;
  std::_Deleted_move_assign<std::_Optional_construct_base<Measurements::MeasureElapsedTime>,Measurements::MeasureElapsedTime>::_Deleted_move_assign<std::_Optional_construct_base<Measurements::MeasureElapsedTime>,Measurements::MeasureElapsedTime>(
    v1514,
    v58,
    &Measurements::MeasurementId::ExcelFileLoad);
  v1254 = 0;
  if ( (int)MsoCreateOpTimer(1, 1, &v1254) >= 0 )
  {
    v59 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1254);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 32LL))(v59);
  }
  v1541[8440] = 0;
  v1437 = *(_QWORD *)v21;
  std::optional<OlDocFilePath>::~optional<OlDocFilePath>(v1541);
  std::_Optional_construct_base<OlDocFilePath>::_Construct<QuickLoadContext *>(v1541, &v1437);
  v60 = v1300;
  v1570[0] = 0;
  v1569 = 0;
  v61 = 7;
  v62 = *(_QWORD *)(v1300 + *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer);
  if ( (*(_DWORD *)(*(_QWORD *)(v62 + 864) + 24LL) & 0x200000) != 0 && !*(_DWORD *)(*(_QWORD *)(v62 + 872) + 104LL) )
  {
    v63 = v1160;
    v1220 = 1;
    if ( v1160 )
      *((_DWORD *)v1160 + 16) |= 4u;
    v64 = *(_QWORD *)(v60 + *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer);
    *(_DWORD *)(*(_QWORD *)(v64 + 872) + 104LL) = (*(_DWORD *)(*(_QWORD *)(v64 + 864) + 24LL) >> 22) & 7;
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v60 + *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer) + 872LL) + 108LL) = 0;
    if ( OSRH::m_vpxlosrea )
    {
      v65 = *(_DWORD *)(*(_QWORD *)OSRH::m_vpxlosrea + 32LL);
      v1182 = (v65 & 0x20000) != 0;
      if ( (v65 & 0x20000) != 0 )
      {
        v1187 = 4;
        if ( (v65 & 0x40000) != 0 )
          v1187 = 6;
      }
    }
    else if ( !*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v60 + *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer) + 872LL)
                         + 104LL)
           && !v1174 )
    {
      if ( MsoDwRegGetDw((const struct _msoreg *)&vmsoridExcelExtractDataDisableUI) == 1 )
        v66 = 101;
      else
        v66 = CustomThreeAlertStop(262220, 0, -1161035137, -1161035136, -282329066);
      if ( v66 == 101 )
      {
        v67 = NtCurrentTeb()->ThreadLocalStoragePointer;
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v60 + *v67) + 872LL) + 104LL) = 1;
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v60 + *v67) + 872LL) + 108LL) = 0;
      }
      else
      {
        if ( v66 != 102 )
        {
          if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v60 + *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer) + 872LL)
                         + 8LL)
              & 1) == 0
            && v63 )
          {
            LoadRecovery::Destroy((LoadRecovery *)v63);
            Mso::Memory::Free((Mso::Memory *)v63, v96);
          }
          if ( v1163 )
          {
            v97 = *v1163;
            v1159 = v97;
            if ( v97 )
            {
              (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v97 + 56LL))(
                v97,
                0xFFFFFFFFLL,
                7);
              v1375 = 594109130;
              OlDocFilePath::FReleaseIOLDoc(&v1159, 1, 1, 0x236962CAu);
            }
          }
          if ( iUseSentinelFile > 0 && hObject != (HANDLE)-1LL )
          {
            CloseHandle(hObject);
            hObject = (HANDLE)-1LL;
          }
          if ( (unsigned int)FHotFix(2) )
          {
            v98 = 63999;
            *(_WORD *)(*(_QWORD *)&UIGLOBALS::UIGLOBALSCONTAINER::m_posi + 1520LL) &= 0xF9FFu;
          }
          if ( v42 )
            Mso::PerfScenario::HrEndScenario(
              (Mso::PerfScenario *)&vmsoperfidOfficeXLFileOpen,
              (const struct Mso::PerfScenario::MsoPerfScenarioId *)v98);
          XlsDiag::LogSetHrCoreTag(-2146827284, 0x17976D2u);
          *v23 = 0;
          std::optional<OlDocFilePath>::~optional<OlDocFilePath>(v1541);
          Mso::TCntPtr<Uxpp::UxppAnnotationsService>::~TCntPtr<Uxpp::UxppAnnotationsService>(&v1254);
          std::_Optional_destruct_base<Measurements::MeasureElapsedTime,0>::~_Optional_destruct_base<Measurements::MeasureElapsedTime,0>(v1514);
          sub_140475070(v1526);
          std::pair<enum Osf::ModifierKeyFlags const,std::wstring>::~pair<enum Osf::ModifierKeyFlags const,std::wstring>(v1548);
          std::unique_ptr<Measurements::StartOrContinueCapture,HeapDeleter<Measurements::StartOrContinueCapture>>::~unique_ptr<Measurements::StartOrContinueCapture,HeapDeleter<Measurements::StartOrContinueCapture>>(&v1274);
          std::unique_ptr<XlsActivity::XlsDetachedActivity,HeapDeleter<XlsActivity::XlsDetachedActivity>>::~unique_ptr<XlsActivity::XlsDetachedActivity,HeapDeleter<XlsActivity::XlsDetachedActivity>>(&v1313);
          Mso::TCntPtr<IWebAddInOptionalProperties>::~TCntPtr<IWebAddInOptionalProperties>(&v1181);
          Mso::TCntPtr<Uxpp::UxppAnnotationsService>::~TCntPtr<Uxpp::UxppAnnotationsService>(&v1278);
          std::optional<NumberConversionSettingsOverride>::~optional<NumberConversionSettingsOverride>(v1521);
          goto LABEL_137;
        }
        if ( MsoDwRegGetDw((const struct _msoreg *)&vmsoridExcelExtractDataFormulas) == 1 )
          v93 = CustomTwoAlertSecBtnDefault(262265, 0, -1161035121, -1161035120);
        else
          v93 = CustomTwoAlert(262265, 0, -1161035121, -1161035120);
        v1182 = 1;
        v562 = v93 == 102;
        v94 = 4;
        if ( v562 )
          v94 = 6;
        v1187 = v94;
        v95 = NtCurrentTeb()->ThreadLocalStoragePointer;
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v60 + *v95) + 872LL) + 104LL) = 2;
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v60 + *v95) + 872LL) + 108LL) = 0;
      }
    }
  }
  v68 = v1160;
  v69 = v1162;
  if ( v1160 )
  {
    v70 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v60 + *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer) + 872LL)
                    + 104LL);
    *(_DWORD *)v1160 = v70;
    *((_DWORD *)v68 + 1) = v70;
    if ( v69 )
      CchRgchToSt(v69 + 1, *v69, *((wchar_t **)v68 + 4), 2084);
    *(_WORD *)(*((_QWORD *)v68 + 4) + 4168LL) = 0;
    *(_WORD *)(*((_QWORD *)v68 + 4) + 2LL * *(unsigned __int16 *)(*((_QWORD *)v68 + 4) + 4168LL) + 4170) = 0;
    v71 = a10;
    if ( (a10 & 4) != 0 )
    {
      LoadRecovery::HrGrbitSetBookCorrupt((LoadRecovery *)v68, 0x1000u);
      v71 = a10;
    }
    if ( v71 < 0 )
      LoadRecovery::HrGrbitSetBookCorrupt((LoadRecovery *)v68, 0x8000000000uLL);
  }
  sub_1402DA650(&v1543, a6, v61);
  v1351 = vpoldocument;
  MaxPathHolder::MaxPathHolder(
    (MaxPathHolder *)v1342,
    (struct IMemHeap *)TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain,
    259,
    0);
  MaxPathHolder::MaxPathHolder(
    (MaxPathHolder *)v1464,
    (struct IMemHeap *)TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain,
    259,
    0);
  MaxPathHolder::MaxPathHolder(
    (MaxPathHolder *)v1341,
    (struct IMemHeap *)TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain,
    259,
    0);
  MaxPathHolder::MaxPathHolder(
    (MaxPathHolder *)v1484,
    (struct IMemHeap *)TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain,
    259,
    0);
  MaxPathHolder::MaxPathHolder(
    (MaxPathHolder *)v1350,
    (struct IMemHeap *)TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain,
    259,
    0);
  MaxPathHolder::MaxPathHolder(
    (MaxPathHolder *)v1352,
    (struct IMemHeap *)TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain,
    259,
    0);
  FileSource::FileSource((FileSource *)v1307, (struct IMemHeap *)TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain);
  std::_Optional_construct_base<FutureFunctionLabelCreationTracker>::_Optional_construct_base<FutureFunctionLabelCreationTracker>(v1518);
  AutoConversionParameters::AutoConversionParameters((AutoConversionParameters *)v1520);
  std::optional<AutomaticNumberConversionLoadPasteHelper>::optional<AutomaticNumberConversionLoadPasteHelper>(v1346);
  v72 = sub_1402DB5D0(v1257, &v1267);
  sub_1402DB4F0(v1236, v72);
  sub_1402DB510(v1257);
  v73 = 1;
LABEL_79:
  v1233 = 0;
  vfLoadAbortedOnFileExtension = 0;
  vfLoadAbortedOnGatekeeper = 0;
  vfLoadAbortedOnActivatedAlreadyOpenedBook = 0;
  if ( v68 )
  {
    if ( ((LoadRecovery::GrbitGetBookCorrupt((LoadRecovery *)v68) & 0x1000) != 0
       || (LoadRecovery::GrbitGetBookCorrupt((LoadRecovery *)v68) & 0x8000000000LL) != 0)
      && *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v60 + *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer) + 872LL) + 104LL) == 2 )
    {
      LoadRecovery::HrGrbitResetBookCorrupt((LoadRecovery *)v68, 0x1000u);
      LoadRecovery::HrGrbitResetBookCorrupt((LoadRecovery *)v68, 0x8000000000uLL);
    }
    LoadRecovery::ResetVolatile((LoadRecovery *)v68);
  }
  vdsv = 0;
  v74 = NtCurrentTeb()->ThreadLocalStoragePointer;
  vaction = 1;
  v1180 = 1;
  v75 = *(_QWORD *)(*(_QWORD *)(v60 + *v74) + 1328LL);
  v76 = 0;
  *(_DWORD *)(v75 + 20) = 0;
  if ( *v69 )
    v76 = a7 != 1024;
  v1156 = v76;
  v77 = (struct IMsoOLDocument *)v1163;
  if ( v1163 )
    v77 = *v1163;
  v1159 = v77;
  if ( v1174 || v1157 )
    v1216 = 1;
  v78 = *(TLSW **)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v60);
  v1303 = *((_QWORD *)v78 + 5);
  v1304 = 0;
  v1438 = TLSW::PesExpressionService(v78);
  std::optional<FutureFunctionLabelCreationTracker>::emplace<XLExpressionService *>(v1518, &v1438);
  v81 = FeatureGateCollectionBase<UserVoiceFeatureGates>::Instance(v80, v79);
  if ( (unsigned __int8)FeatureExposure::operator bool(v81 + 56) )
  {
    v1439 = v1520;
    std::optional<AutomaticNumberConversionLoadPasteHelper>::emplace<AutoConversionParameters *>(v1346, &v1439);
  }
  v1153 = 1;
  v82 = *(_QWORD *)(v60 + *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer);
  v1222 = *(struct ENV **)(v82 + 336);
  *(_QWORD *)(v82 + 336) = &v1553;
  v1554 = 36737602;
  v1168 = setjmp(Buf);
  if ( v1168 )
    goto LABEL_1133;
  v83 = (Excel::XlBoot **)NtCurrentTeb()->ThreadLocalStoragePointer;
  if ( !*(_QWORD *)(*(_QWORD *)((char *)*v83 + v60) + 784LL) )
    Excel::XlBoot::InitUserNameCur(*v83);
  v84 = Src;
  v85 = v1226;
  v1162 = Src;
  if ( v1324 && !(unsigned int)FFilenameFromSt(Src, Src, v1226) )
  {
    v1012 = v1235;
    if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL) + 8LL)
        & 1) == 0
      && v1235 )
    {
      LoadRecovery::Destroy((LoadRecovery *)v1235);
      FreeHpst(v1012);
      v1012 = 0;
      v1235 = 0;
    }
    v1155 = 0;
    XlsDiag::LogSetHrCoreTag(-2147024690, 0x17976D4u);
    v1152 = v1336;
    v1150 = v1256;
    v1149 = v1177;
    v1148 = -2147024690;
    v1146 = v1183;
    v1145 = v1304;
    v1143 = v1272;
    v1142 = v1159;
    v1141 = v1161;
    v1140 = v1253;
    v1139 = v1248;
    v1138 = v1197 != 0;
    v1136 = v1222;
    v1134 = v1302;
    v1132 = (struct LoadRecovery *)v1012;
    goto LABEL_2113;
  }
  v68 = v1235;
  v1160 = v1235;
  if ( v1235 )
  {
    v86 = (wchar_t *)XLSBOOK::Plxtab((XLSBOOK *)v1235);
    CchStToSt(v84, v86, 2084);
    MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1464, v84);
  }
  if ( !FileLoad::FProcessDisabledDocument(v84, v1159, v1174 != 0) )
  {
    v116 = -2147024809;
    XlsDiag::LogSetHrCoreTag(-2147024809, 0x17976D5u);
    goto LABEL_2100;
  }
  MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1350, v84);
  v87 = MaxPathHolder::SzPath((MaxPathHolder *)v1350);
  if ( MsoFIsInFileSysWzPersistentName(v87, 0) && wProjLoad != 2 && !(unsigned int)FileExists(v84) )
    FEnsureExtension(v84, v85, 0xFFFFFFFFLL, 50, (_DWORD)v1126, v1128);
  v88 = v1159;
  if ( v1159 )
  {
    (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v1159 + 56LL))(v1159, 1, 9);
    v88 = v1159;
  }
  v89 = v1186;
  v90 = v1216;
  v1170 = v1186;
  v1173 = v1216;
  if ( v1156 )
  {
    v1198 = 2;
    v91 = v88 == 0;
    if ( v88 && (*(unsigned int (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v88 + 208LL))(v88) )
    {
      v1198 = 0;
      v92 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1541);
      OlDocFilePath::IncOpenCount(v92);
    }
    if ( v90 )
    {
      operator|=(&v1198, 1);
    }
    else if ( (a10 & 0x200) != 0 )
    {
      operator|=(&v1198, 8);
    }
    if ( (unsigned int)FFinderFile(v84)
      || vfInstallTemplates
      && *(_DWORD *)(*(_QWORD *)(v60 + *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer) + 1764LL) )
    {
      operator|=(&v1198, 32);
    }
    v100 = FeatureGateCollectionBase<LoadSaveFeatureGates>::Instance();
    if ( (unsigned __int8)Mso::AB::Optimized::FeatureGate::operator bool(v100 + 8) )
    {
      v101 = MaxPathHolder::SzPath((MaxPathHolder *)v1350);
      if ( MsoFIsInFileSysWzPersistentName(v101, 0) )
      {
        v102 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1350);
        if ( (unsigned int)FIsPathAnXll(v102, 1) )
          operator|=(&v1198, 32);
      }
    }
    if ( (a10 & 0x20000) != 0 )
      operator|=(&v1198, 256);
    LODWORD(v1126) = v1198;
    XlsDiag::SendTraceTag(41039177, 187, 100, L"FFileLoadEx: OlDocSetupFlags oldsf = 0x%x", v1126);
    if ( v91 && a16 == 16 && !(unsigned int)FOsrhInTransition() )
      operator|=(&v1198, 512);
    v103 = FeatureGateCollectionBase<ZipItFeatureGates>::Instance();
    if ( (unsigned __int8)Mso::AB::Optimized::FeatureGate::operator bool(v103 + 72) )
      v104 = 1;
    else
      v104 = v89 == 0;
    v105 = v1298;
    if ( v1298 )
    {
      v106 = (ZrtUtility *)MaxPathHolder::SzPath((MaxPathHolder *)v1350);
      if ( ZrtUtility::FCanUseServerOnlyAsyncOpen(v106, v107) && v104 )
        operator|=(&v1198, 1024);
    }
    v108 = TLSW::PesExpressionService(*(TLSW **)(v1300 + *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer));
    v109 = ExpressionService::Pwbkcoll(v108);
    RevisionLatencyOutlierTracker::RevisionLatencyOutlierTracker(v1532, v109, 16);
    v110 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1541);
    v111 = BKORWS::Psh((BKORWS *)&v1181);
    OlDocFilePath::SetOpenTelemetry(v110, v111);
    operator|=(&v1198, 4096);
    v112 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1541);
    v113 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1376, 0x236962C9u);
    v114 = SXVWGEOM::RwFirst(v113);
    v115 = OlDocFilePath::HrSetupAndRetrievePathTitle(
             v112,
             (struct FileSource *)v1307,
             &v1159,
             v84,
             &v1234,
             (enum OlDocSetupFlags *)&v1198,
             v105,
             v114,
             0,
             0);
    v116 = v115;
    if ( v115 < 0 )
      XlsDiag::LogSetHrCoreTag(v115, 0x27C1404u);
    RevisionLatencyOutlierTracker::~RevisionLatencyOutlierTracker((RevisionLatencyOutlierTracker *)v1532);
    v117 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1541);
    if ( (int)OlDocFilePath::COpenCount(v117) > 1 )
      MsoShipAssertTagProc(505205964);
    if ( v1298 )
    {
      v118 = v1159;
      v119 = APPCORE::PmemheapMain((APPCORE *)&vapp);
      v1161 = ZrtUtility::FOpeningAsServerOnlyAsync(v119, v1298, v118, v120);
    }
    if ( v116 < 0 )
    {
      if ( v1159 )
        Mso::DocumentTelemetry::AddAllDocumentTelemetryFieldsToActivity<XlsActivity,IMsoOLDocument,void>(
          v1377,
          v1215,
          v1159,
          0);
    }
    else
    {
      v121 = (ArtUserInterfaceSite *)Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1181);
      v122 = CoauthoringInternals::FCoauthoringFeatureEnabled() && XlAsyncFileIO::FCoauthorableFileIO(v1159);
      ArtUserInterfaceSite::SetCurrentToolLockState(v121, v122);
      v123 = (OpenTelemetry *)Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1181);
      OpenTelemetry::SetPoldoc(v123, v1159);
    }
    v124 = BKORWS::Psh((BKORWS *)&v1181);
    XlFileProtocolManager::SetFallbackReason(v1159, v124);
    if ( v116 < 0
      || (v125 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1541),
          !(unsigned int)OlDocFilePath::CchPath(v125)) )
    {
      if ( v1159 )
      {
        v1334 = v1159;
        (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v1159 + 56LL))(
          v1159,
          0xFFFFFFFFLL,
          7);
        v1018 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1541);
        OlDocFilePath::RecordEventForCloseOldoc(v1018, v1159, 0);
        v1019 = v1247;
        if ( v1247 && *v1247 == v1159 )
        {
          v1020 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1456, 0x236962C8u);
          v1021 = SXVWGEOM::RwFirst(v1020);
          OlDocFilePath::FReleaseIOLDoc(&v1334, 0, 1, v1021);
          *v1019 = v1334;
        }
        else
        {
          v1022 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1457, 0x236962C7u);
          v1023 = SXVWGEOM::RwFirst(v1022);
          OlDocFilePath::FReleaseIOLDoc(&v1334, 0, 1, v1023);
        }
      }
      goto LABEL_2100;
    }
    v126 = (const struct OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1541);
    v127 = FileSource::HrSetOlDocFilePath((FileSource *)v1307, v126);
    v116 = v127;
    if ( v127 < 0 )
    {
      XlsDiag::LogSetHrCoreTag(v127, 0x279F29Cu);
      goto LABEL_2100;
    }
    v128 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1541);
    v129 = OlDocFilePath::StzTitle(v128);
    if ( MaxPathHolder::FExceedsMaxFileName(*v129) )
    {
      Error(655635);
      if ( v1159 )
      {
        (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v1159 + 56LL))(
          v1159,
          0xFFFFFFFFLL,
          7);
        HrRecordEvent(v1159, 0x40000000u, 0);
        v1016 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1455, 0x236962C6u);
        v1017 = SXVWGEOM::RwFirst(v1016);
        OlDocFilePath::FReleaseIOLDoc(&v1159, 1, 1, v1017);
      }
      goto LABEL_2100;
    }
    v130 = XLFileIOMockable::HrSetPoldoc((struct FileSource *)v1307, v1159, v1276, v1215);
    v1154 = v130;
    v116 = v130;
    if ( v130 < 0 )
    {
      XlsDiag::LogSetHrCoreTag(v130, 0x279F29Du);
      goto LABEL_2100;
    }
    v131 = FileSource::StzFilePath((FileSource *)v1307);
    if ( !(unsigned int)FIsPathAnXll(v131, 1) )
    {
      v132 = v1159;
      v133 = APPCORE::PmemheapMain((APPCORE *)&vapp);
      Api::DataLossProtectionSessionManager::NotifyEvent(v133, 0, v132, 0);
    }
    if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 2972LL)
      && v1272
      && *v1272 )
    {
      CchSzToStz(v1272 + 1, &v1569, 257);
    }
    else
    {
      v134 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1541);
      v135 = OlDocFilePath::StzTitle(v134);
      CchStToStz(v135, &v1569, 257);
    }
    MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1350, v84);
    v136 = MaxPathHolder::SzPath((MaxPathHolder *)v1350);
    if ( !MsoFIsInFileSysWzPersistentName(v136, 0) && v1569 > 0xF9u )
    {
      v1569 = 249;
      MakeStStzTruncOK(&v1569, 257);
    }
    v137 = v1159;
    vpoldocument = v1159;
    v1163 = v1247;
    if ( v91 )
    {
      if ( v1247 )
      {
        *v1247 = v1159;
        v137 = v1159;
      }
      else
      {
        v1163 = &v1159;
        v1247 = &v1159;
      }
    }
    if ( v1544 || !(unsigned int)IMsoOLDocument::IsInFileSys(v137) )
    {
      v84 = v1162;
    }
    else
    {
      v1543 |= 0x10u;
      v1259 = 0;
      MaxPathSzPoke::MaxPathSzPoke((MaxPathSzPoke *)v1489, (struct MaxPathHolder *)v1341);
      v1259 = MaxPathSzPoke::CchSzBufferSize((MaxPathSzPoke *)v1489);
      v138 = *(__int64 (__fastcall **)(struct IMsoOLDocument *, const wchar_t *, unsigned int *, __int64))(*(_QWORD *)v1159 + 64LL);
      v139 = AugmentationLoop::TranslateDetectLanguagesArrayAnnotationResponse::SzId((AugmentationLoop::TranslateDetectLanguagesArrayAnnotationResponse *)v1489);
      v140 = v138(v1159, v139, &v1259, 3);
      MaxPathSzPoke::~MaxPathSzPoke((MaxPathSzPoke *)v1489);
      if ( v140 < 0 )
      {
        if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1232LL)
                       + 32LL) )
        {
          v1013 = MaxPathHolder::SzPath((MaxPathHolder *)v1350);
          v1014 = MsoServerErrorTypeGet(0);
          MsoServerErrorAlert(v1014, v1013, 0);
        }
        v116 = v140;
        XlsDiag::LogSetHrCoreTag(v140, 0x26C77DFu);
        goto LABEL_1861;
      }
      v84 = v1162;
      if ( v1259 <= 1 && (int)RootPathWithMph(v1162, (struct MaxPathHolder *)v1341) < 0 )
        MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1341, v84);
    }
    if ( (unsigned __int8)FFlagSet(v1198, 8) )
      v1175 = 1;
  }
  else
  {
    XlsDiag::LogSetHrCoreTag(-2147467259, 0x27C1405u);
    v141 = FileSource::HrSetPoldoc((FileSource *)v1307, v1159, v1276, v1215);
    v1154 = v141;
    v116 = v141;
    if ( v141 < 0 )
      XlsDiag::LogSetHrCoreTag(v141, 0x279F29Eu);
    if ( (unsigned __int8)std::shared_ptr<Mso::ActivityScope::IMsoLoggingScope>::operator bool(&v1181) )
    {
      v142 = (OpenTelemetry *)Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1181);
      OpenTelemetry::SetPoldoc(v142, v1159);
    }
    if ( v116 < 0 )
    {
      OkAlert(196655, v1570);
      v1015 = v1247;
      goto LABEL_2092;
    }
    FileSource::FGetPathname((FileSource *)v1307, v84 + 1, *v84, &v1569, 257);
    v1163 = v1247;
  }
  if ( !(unsigned int)MaxPathHolder::CchLength((MaxPathHolder *)v1341) )
  {
    v143 = FileSource::StzFilePath((FileSource *)v1307);
    MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1341, v143);
  }
  v144 = v1260;
  v1249 = v1260;
  if ( !v1174 )
  {
    if ( (unsigned int)FOsrhInTransition() )
    {
      if ( (a10 & 0x10000) != 0 )
        OSRR::SetFatalOnlyFlag((OSRR *)&v1237);
      goto LABEL_244;
    }
    if ( v1157 )
    {
LABEL_243:
      v1239 = v1574;
      v1240 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                        + 104LL) == 0;
      OSRR::SetCreateNew((OSRR *)&v1237, a10 & 0x400);
      goto LABEL_244;
    }
    v145 = 0;
    CchStToSz(v84, String1, 2084);
    if ( fInIdle && v1159 )
    {
      v146 = 2;
      if ( (int)MsoCchWzLen(String1) <= 2 )
      {
LABEL_229:
        v147 = a10;
        if ( (a10 & 0x80000) != 0 )
        {
          if ( !v1189 || (v148 = (BKORWS *)v1484, v144) )
            v148 = (BKORWS *)v1341;
          v149 = (const wchar_t *)BKORWS::Psh(v148);
          v562 = !FShouldOpenInAppGuard(v149, 0);
          v147 = a10;
          if ( v562 )
          {
            v147 = a10 & 0xFFFFEFFF;
            a10 &= ~0x1000u;
          }
        }
        if ( (v147 & 0x2000) != 0 )
        {
          v146 = 3;
        }
        else if ( (v147 & 0x10000) == 0 )
        {
          v146 = (v147 & 0x1000) != 0;
        }
        if ( v145 )
        {
          v150 = (unsigned int)MsoCchWzLen(String1);
          v151 = String1;
        }
        else
        {
          v150 = *v84;
          v151 = v84 + 1;
        }
        XlProtectionMockable::InitOSRR(&v1237, v146, v151, v150);
        goto LABEL_243;
      }
      if ( !wcsncmp(String1, L"\\\\", 2u)
        && !MsoFReservedWzPersistentName(String1)
        && FIsHttpRedirFile(String1, 0, 0, 0, 0) )
      {
        v145 = MsoFConvertHttpRedirUNCToHttp(String1, String1, 2084) != 0;
      }
    }
    v146 = 2;
    goto LABEL_229;
  }
LABEL_244:
  v152 = v1160;
  if ( v1160 )
  {
    v153 = (const wchar_t *)XLSBOOK::Plxtab((XLSBOOK *)v1160);
    if ( !(unsigned int)FHasPath(v153) )
    {
      v154 = (wchar_t *)XLSBOOK::Plxtab((XLSBOOK *)v152);
      v155 = FileSource::StzFilePath((FileSource *)v1307);
      CchStToSt(v155, v154, 2084);
    }
    if ( !v1282
      && (*((_BYTE *)PivotOperationBase::PSxview((PivotOperationBase *)v152) + 36) & 8) == 0
      && (unsigned int)ObjectModelState::FInCallback((ObjectModelState *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                    + 304LL)
                                                                        + 1200LL)) != 2 )
    {
      v156 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
      if ( (!*(_DWORD *)(*(_QWORD *)(v156 + 1232) + 80LL)
         || (unsigned int)ObjectModelState::FInCallback((ObjectModelState *)(v156 + 1200)) == 2)
        && !(unsigned int)ObjectModelState::FInCallback((ObjectModelState *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                       + 304LL)
                                                                           + 1200LL)) )
      {
        FStartLoadAction(
          2 - (v1251 != 0),
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                    + 104LL),
          (struct LoadRecovery *)v152);
      }
    }
  }
  if ( !v1544 )
  {
    CchStToStz(&v1569, v1572, 257);
    v157 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1341);
    MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1342, v157);
  }
  if ( v1159 )
  {
    v1284 = 0;
    v158 = (*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1159 + 80LL))(v1159);
    XlAsyncFileIO::SpOLDocCoauthFromPOLDoc(v1311, v1159);
    if ( v89
      || (v159 = 0, (unsigned __int8)std::shared_ptr<Mso::ActivityScope::IMsoLoggingScope>::operator bool(v1311))
      && (v160 = BKORWS::Psh((BKORWS *)v1311), XlAsyncFileIO::FIsDistributedBlobsFile(v160)) )
    {
      v159 = 1;
      v1170 = 1;
    }
    else
    {
      v1170 = 0;
    }
    v1186 = v159;
    v161 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1378, 0x21C730Du);
    v162 = SXVWGEOM::RwFirst(v161);
    OldocHelper::SetAttrInAttrMask(
      v1159,
      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1232LL) + 32LL) != 0
    ? 0x20000
    : 0,
      0x20000u,
      v162);
    (*(void (__fastcall **)(struct IMsoOLDocument *, struct IMsoPKMClient **))(*(_QWORD *)v1159 + 168LL))(v1159, &v1248);
    v163 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1379, 0x21C730Eu);
    v164 = SXVWGEOM::RwFirst(v163);
    OldocHelper::SetAttrInAttrMask(v1159, v158, 0x20000u, v164);
    if ( v1248 )
      (*(void (__fastcall **)(struct IMsoPKMClient *))(*(_QWORD *)v1248 + 104LL))(v1248);
    if ( (*(int (__fastcall **)(struct IMsoOLDocument *, int *, __int64))(*(_QWORD *)v1159 + 48LL))(v1159, &v1284, 20) >= 0
      && v1284 )
    {
      v116 = -2147467260;
      XlsDiag::LogSetHrCoreTag(-2147467260, 0x17976D7u);
      Mso::TCntPtr<Uxpp::UxppAnnotationsService>::~TCntPtr<Uxpp::UxppAnnotationsService>(v1311);
      goto LABEL_1871;
    }
    Mso::TCntPtr<Uxpp::UxppAnnotationsService>::~TCntPtr<Uxpp::UxppAnnotationsService>(v1311);
  }
  if ( v152 )
  {
    v165 = XLSBOOK::Plxtab((XLSBOOK *)v152);
    CchStToSt(&v1569, (wchar_t *)v165 + 2084, 257);
    v166 = XLSBOOK::Plxtab((XLSBOOK *)v152);
    *((_WORD *)v166 + *((unsigned __int16 *)XLSBOOK::Plxtab((XLSBOOK *)v152) + 2084) + 2085) = 0;
  }
  MaxPathSzPoke::MaxPathSzPoke((MaxPathSzPoke *)v1486, (struct MaxPathHolder *)v1350);
  v167 = 0;
  if ( v1213 )
  {
    v170 = v1173;
  }
  else
  {
    if ( v1159 )
    {
      if ( (unsigned int)IMsoOLDocument::IsInFileSys(v1159) )
        v167 = AugmentationLoop::TranslateDetectLanguagesArrayAnnotationResponse::SzId((AugmentationLoop::TranslateDetectLanguagesArrayAnnotationResponse *)v1486);
      else
        v167 = 0;
    }
    v168 = (wchar_t *)v167;
    v169 = FIsTrue<int>(vgrbitScanload & 2);
    v170 = v1173;
    v171 = sub_1402D9860(v1159, (struct FileSource *)v1307, v1173 != 0, v169, v168, (struct OSRR *)&v1237);
    v1154 = v171;
    v116 = v171;
    if ( v171 < 0 )
    {
      XlsDiag::LogSetHrCoreTag(v171, 0x1E107807u);
LABEL_1872:
      MaxPathSzPoke::~MaxPathSzPoke((MaxPathSzPoke *)v1486);
      goto LABEL_1871;
    }
    v172 = v1269;
    if ( v1269 )
    {
      v173 = APPCORE::PmemheapMain((APPCORE *)&vapp);
      FileSource::FileSource((FileSource *)v1531, v173);
      v174 = FileSource::HrSetWin32PathSt((FileSource *)v1531, v172);
      if ( v174 < 0 )
        XlsDiag::LogSetHrCoreTag(v174, 0x1E109581u);
      v175 = FIsTrue<int>(vgrbitScanload & 2);
      v176 = sub_1402D9860(v1159, (struct FileSource *)v1531, v170 != 0, v175, 0, (struct OSRR *)&v1237);
      v1154 = v176;
      v116 = v176;
      if ( v176 < 0 )
      {
        XlsDiag::LogSetHrCoreTag(v176, 0x1E107806u);
        FileSource::~FileSource((FileSource *)v1531);
        goto LABEL_1872;
      }
      FileSource::~FileSource((FileSource *)v1531);
    }
  }
  v1213 = 1;
  MaxPathSzPoke::~MaxPathSzPoke((MaxPathSzPoke *)v1486);
  v177 = PbookFromTitle(v1569, v1570);
  v1199 = v177;
  if ( v177 )
  {
    v178 = BOOK::FFailedToFreeWhileLoading(v177);
    v177 = v1199;
    if ( v178 || !*((_QWORD *)v1199 + 141) )
    {
      if ( !BOOK::FFailedToFreeWhileLoading(v1199) )
        MsoShipAssertTagProc(40981770);
      v177 = 0;
      v1199 = 0;
    }
    if ( v177 )
    {
      if ( (unsigned int)FOsrc() )
      {
        SetLoadForPreviewError(-2147024891);
        v1024 = 24737497;
        v1025 = -2147024891;
        v116 = -2147024891;
        goto LABEL_1874;
      }
      v177 = v1199;
    }
  }
  if ( v1157 && !v177 )
  {
    FixUpFileTitle(&v1569);
    v177 = PbookFromTitle(v1569, v1570);
    v1199 = v177;
  }
  v179 = *(struct SH ***)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
  if ( v179[5] )
  {
    v180 = v179[5];
    if ( (*((_DWORD *)v180 + 221) & 0x200) != 0 )
    {
      v181 = BOOK::Pioldoc(v180);
      v182 = v1159;
      if ( v1159 != v181 )
      {
        MsoShipAssertTagProc(1650811750);
        v182 = v1159;
      }
      if ( !v182 )
        goto LABEL_410;
      HrRecordEvent(v182, 0x40000000u, 0);
      v183 = FeatureGateCollectionBase<ZipItFeatureGates>::Instance();
      v184 = 0;
      if ( (unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(v183 + 424) )
      {
        v187 = v1244;
      }
      else
      {
        v185 = FeatureGateCollectionBase<ZipItFeatureGates>::Instance();
        v186 = Mso::AB::Optimized::ChangeGate::operator bool(v185 + 440);
        v187 = v1244;
        if ( !v186 )
          goto LABEL_306;
        v187 = v1244 | 1;
        v1244 |= 1u;
        v188 = (BKORWS *)XlAsyncFileIO::SpOLDocCoauthFromPOLDoc(v1440, v1159);
        v189 = BKORWS::Psh(v188);
        if ( !XlAsyncFileIO::FIsDistributedBlobsFile(v189) )
          goto LABEL_306;
      }
      v184 = 1;
LABEL_306:
      if ( (v187 & 1) != 0 )
      {
        v1244 = v187 & 0xFFFFFFFE;
        Mso::TCntPtr<Uxpp::UxppAnnotationsService>::~TCntPtr<Uxpp::UxppAnnotationsService>(v1440);
      }
      if ( v184 )
      {
        v1285 = -1;
        if ( (*(int (__fastcall **)(struct IMsoOLDocument *, int *))(*(_QWORD *)v1159 + 200LL))(v1159, &v1285) < 0
          || v1285 <= 0 )
        {
          MsoShipAssertTagProc(504410975);
        }
        if ( v170 )
        {
          MsoShipAssertTagProc(504414753);
          v190 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1380, 0x1E113313u);
          v191 = SXVWGEOM::RwFirst(v190);
          OldocHelper::SetReadOnly(v1159, v191);
        }
        else
        {
          v192 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1381, 0x1E113312u);
          v193 = SXVWGEOM::RwFirst(v192);
          OldocHelper::ClearReadOnly(v1159, v193);
        }
        v194 = v1159;
        v195 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL);
        v196 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1382, 0x1E10B250u);
        v197 = SXVWGEOM::RwFirst(v196);
        LOBYTE(v198) = 33;
        LOBYTE(v199) = 5;
        Mementos::LogObjectLifetimeEvent(v197, 3, v199, v198, v195, v194);
        (*(void (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1159 + 16LL))(v1159);
        if ( !(unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(&unk_144028920) )
        {
          v200 = *(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL);
          v201 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1383, 0x1E113311u);
          v202 = SXVWGEOM::RwFirst(v201);
          BOOK::SetPioldoc(v200, 0, v202);
        }
        v1180 = 0;
      }
      else
      {
        v203 = BOOK::Pioldoc(*(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL));
        v205 = v1159;
        if ( v1159 == v203 )
        {
          LOBYTE(v204) = 1;
          Mso::TRestorer<bool>::TRestorer<bool>(v1510, &XlFileProtocol::s_fInClose, v204);
          v1441 = v1159;
          v206 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1384, 0x236962C5u);
          v207 = SXVWGEOM::RwFirst(v206);
          OlDocFilePath::FReleaseIOLDoc(&v1441, 1, 0, v207);
          v208 = *(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL);
          v209 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1385, 0x236962C4u);
          v210 = SXVWGEOM::RwFirst(v209);
          BOOK::SetPioldoc(v208, 0, v210);
          Mso::TRestorer<bool>::~TRestorer<bool>(v1510);
          v205 = v1159;
        }
        v1180 = FBeginCmdIOLDoc(v205, v170 != 0 ? 4 : 2, 0, &v1234, 0);
      }
      goto LABEL_409;
    }
  }
  if ( !v177 || wProjLoad == 2 )
    goto LABEL_410;
  v562 = v177 == v179[5];
  v1270 = v179[4];
  v211 = !v562;
  v1277 = v179[13];
  if ( v179[13] )
  {
    SH::Pbook(*((SH **)v179[13] + 3));
    v177 = v1199;
  }
  v212 = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)v177 + 205) + 32LL))((__int64)v177 + 1640);
  v213 = 0;
  v214 = 0;
  v215 = BOOK::Pioldoc(v1199);
  if ( v1159 != v215 )
  {
    if ( !v212 )
    {
      v216 = 34146077;
LABEL_335:
      v213 = 1;
      XlsDiag::LogSetHrCoreTag(-2147467260, v216);
      goto LABEL_336;
    }
    if ( !OfficeSharedApiImpl::BusinessBarShowArgs::GetHideCloseButton((OfficeSharedApiImpl::BusinessBarShowArgs *)v1307)
      || (v217 = FileSource::StzFilePath((FileSource *)v1307),
          (unsigned int)CmpTextHp(v212, v217, 0xFFFFFFFFLL, 0xFFFFFFFFLL)) )
    {
      v213 = 1;
      XlsDiag::LogSetHrCoreTag(-2147467260, 0x209071Eu);
      v214 = 1;
    }
  }
  if ( !v214 )
  {
    v218 = *((_QWORD *)v1199 + 66);
    if ( v218 )
    {
      if ( *(_QWORD *)(v218 + 208) )
      {
        v216 = 34146079;
        goto LABEL_335;
      }
    }
  }
LABEL_336:
  if ( v213 )
  {
    if ( (a3 & 4) == 0 )
      OkAlert(196753, v1570);
    fCeCanceled = 1;
    v116 = -2147467260;
    XlsDiag::LogSetHrCoreTag(-2147467260, 0x2385704u);
    v1035 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1181);
    v1036 = OpenTelemetry::POpenFileStageModel(v1035);
    v1037 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1458, 0x1F0CB5D3u);
    v1038 = SXVWGEOM::RwFirst(v1037);
    WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v1036, 2214658819LL, v1038);
    goto LABEL_1871;
  }
  if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1232LL) + 80LL) )
  {
    v219 = XLOSRR::FMustUseOsr((XLOSRR *)&v1237);
    if ( (unsigned int)FOsrhBook(v1199) != v219 )
    {
      v1026 = FOsrhBook(v1199);
      OkAlert(589891 - (v1026 != 0), 0);
      v1024 = 24737499;
      goto LABEL_1876;
    }
  }
  if ( (*((_DWORD *)v1199 + 221) & 0x100) != 0
    && *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1836LL) )
  {
    OkAlert(196948, v1570);
    v1027 = 24737500;
    goto LABEL_1878;
  }
  v1286 = 0;
  v220 = HrGroupAction(0, v1199, 9, 0, &v1286);
  if ( v220 < 0 )
  {
    v1168 = v220;
    goto LABEL_1133;
  }
  if ( v1286 )
  {
    v1024 = 24737501;
LABEL_1876:
    v116 = -2147024809;
    v1025 = -2147024809;
LABEL_1874:
    XlsDiag::LogSetHrCoreTag(v1025, v1024);
LABEL_1871:
    v68 = v1160;
LABEL_1861:
    v1015 = v1163;
    goto LABEL_2092;
  }
  if ( !FileSource::FFileExists((FileSource *)v1307) )
  {
    OkAlert(196655, v1570);
    v1028 = -2147319765;
    v1027 = 24737502;
    goto LABEL_1879;
  }
  if ( PcxoFromPbook(v1199) )
  {
    v221 = PcxoFromPbook(v1199);
    if ( (unsigned int)FCxoLocked(v221) )
    {
      if ( (*((_DWORD *)v1199 + 222) & 0x400) == 0 )
        Error(393653);
      v1027 = 24737503;
LABEL_1878:
      v1028 = -2147024809;
LABEL_1879:
      v116 = v1028;
      v1029 = v1028;
      goto LABEL_1880;
    }
  }
  v222 = 2;
  if ( (a3 & 2) == 0 )
  {
    if ( vfPastingHlink )
    {
      v1027 = 24737504;
    }
    else
    {
      if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1232LL)
                     + 32LL) == 2 )
        fCeCanceled = 1;
      if ( (*(_BYTE *)(*((_QWORD *)v1199 + 141) + 3058LL) & 0x18) != 0 )
      {
        v1030 = 1;
      }
      else
      {
        v1031 = FActivatePbook(v1199);
        v1030 = FIsTrue<int>(v1031);
      }
      v1178 = v1030;
      vfLoadAbortedOnActivatedAlreadyOpenedBook = v1030;
      if ( v1030 )
      {
        v1453 = "Unconditionally setting foreground window for already opened book";
        Mso::Diagnostics::SendDiagnosticTrace<>(556414216, 2485, 50, 2, (__int64)&v1453);
        Count = Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection::GetCount(v1199);
        v1033 = WN::Puiframe(*(WN **)(Count + 16));
        v1034 = UIFRAME::HwndFrame(v1033);
        SetForegroundWindow(v1034);
        v1028 = -2147467260;
        v1027 = 37246725;
        goto LABEL_1879;
      }
      v1027 = 24737505;
    }
LABEL_1893:
    v116 = -2146827284;
    goto LABEL_1894;
  }
  if ( UIGLOBALS::UIGLOBALSCONTAINER::m_selection )
  {
    v223 = SH::Pbook(*(SH **)(UIGLOBALS::UIGLOBALSCONTAINER::m_selection + 24LL));
    if ( v223 == v1199
      && (!*(_QWORD *)&UIGLOBALS::UIGLOBALSCONTAINER::m_posi
       || (v224 = *(_QWORD *)(*(_QWORD *)&UIGLOBALS::UIGLOBALSCONTAINER::m_posi + 1568LL)) == 0
       || *(_QWORD *)(v224 + 256))
      && !(unsigned int)FOsrhBook(v1199) )
    {
      inited = HrInitRevert((struct REVARG *)v1567, 336, &v1271);
      v226 = v1172;
      if ( inited >= 0 )
        v226 = 1;
      v1172 = v226;
    }
  }
  Marquee::FreeAllMarqueeTag(0, 20789206, v222);
  DestroyWorkgroup();
  v227 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1386, 0x237630DCu);
  v228 = SXVWGEOM::RwFirst(v227);
  v229 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 128LL);
  v230 = 0;
  if ( v229 )
  {
    v231 = v229;
    do
    {
      v230 = v231[1];
      if ( v230 )
        break;
      v229 = (_QWORD *)*v229;
      v231 = v229;
    }
    while ( v229 );
  }
  LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v230 + 96), v1199, v228);
  if ( Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection::GetCount(*(Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 32LL))
    && *(_QWORD *)(Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection::GetCount(*(Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 32LL))
                 + 16) )
  {
    v232 = (struct WNX *)Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection::GetCount(*(Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 32LL));
    v233 = Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection::GetCount(*(Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 32LL));
    AttachWnxToWn(*(struct WN **)(v233 + 16), v232);
  }
  if ( (unsigned int)FLogRevs(v1199) && (*((_BYTE *)v1199 + 884) & 0x20) == 0 )
    FFreeUsrInfo(v1199, *(_DWORD *)(*((_QWORD *)v1199 + 125) + 16LL), 0, 0, 0);
  HrRecordEvent(v1159, 0x40000000u, 0);
  if ( v211 )
  {
    if ( v1277 )
    {
      v234 = (SH *)*((_QWORD *)v1277 + 3);
      if ( v234 )
      {
        v235 = SH::Pbook(v234);
        if ( v235 == v1199 )
          v211 = 0;
      }
    }
  }
  sub_1416A3634();
  v236 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
  if ( *(_QWORD *)(v236 + 992) )
  {
    v237 = *(_QWORD *)(v236 + 992);
    if ( *(_QWORD *)(v237 + 48) )
    {
      v238 = SH::Pbook(*(SH **)(*(_QWORD *)(v237 + 48) + 24LL));
      if ( v238 == v1199 )
        FreeCfr();
    }
  }
  v116 = XlReopenBook::HrCloseBookForReopen(
           &v1199,
           (struct REVERT **)((unsigned __int64)&v1271 & -(__int64)(v1172 != 0)));
  if ( v116 < 0 )
  {
    v1024 = 34174687;
    v1025 = v116;
    goto LABEL_1874;
  }
  v1303 = 0;
  if ( v211 )
  {
    v239 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1387, 0x237630DBu);
    v240 = SXVWGEOM::RwFirst(v239);
    v241 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 128LL);
    v242 = 0;
    if ( v241 )
    {
      v243 = v241;
      do
      {
        v242 = v243[1];
        if ( v242 )
          break;
        v241 = (_QWORD *)*v241;
        v243 = v241;
      }
      while ( v241 );
    }
    LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v242 + 96), v1270, v240);
    v244 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1388, 0x237630DAu);
    v245 = SXVWGEOM::RwFirst(v244);
    v246 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 128LL);
    v247 = 0;
    if ( v246 )
    {
      v248 = v246;
      do
      {
        v247 = v248[3];
        if ( v247 )
          break;
        v246 = (_QWORD *)*v246;
        v248 = v246;
      }
      while ( v246 );
    }
    VIEWCONTEXTDATA::CurWnx(*(VIEWCONTEXTDATA **)(v247 + 16), v1277, v245);
  }
  v170 = v1173;
  v1221 = 2;
  if ( v1173 || (v249 = 2, v1175) )
    v249 = 4;
  v1180 = FBeginCmdIOLDoc(v1159, v249, 0, &v1234, 0);
  if ( (*(unsigned int (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1159 + 208LL))(v1159) )
    v1221 = 0;
  if ( v170 )
  {
    operator|=(&v1221, 1);
  }
  else if ( (a10 & 0x200) != 0 )
  {
    operator|=(&v1221, 8);
  }
  if ( (unsigned int)FFinderFile(v84) )
    operator|=(&v1221, 32);
  if ( (a10 & 0x20000) != 0 )
    operator|=(&v1221, 256);
  LODWORD(v1127) = v1221;
  XlsDiag::SendTraceTag(41039178, 187, 100, L"FFileLoadEx: OlDocSetupFlags oldsf = 0x%x", v1127);
  v250 = TLSW::PesExpressionService(*(TLSW **)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL));
  v251 = ExpressionService::Pwbkcoll(v250);
  RevisionLatencyOutlierTracker::RevisionLatencyOutlierTracker(v1530, v251, 16);
  operator|=(&v1221, 4096);
  v252 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1541);
  v253 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1389, 0x236962C3u);
  v254 = SXVWGEOM::RwFirst(v253);
  v116 = OlDocFilePath::HrSetupAndRetrievePathTitle(
           v252,
           (struct FileSource *)v1307,
           &v1159,
           v84,
           &v1234,
           (enum OlDocSetupFlags *)&v1221,
           0,
           v254,
           0,
           0);
  RevisionLatencyOutlierTracker::~RevisionLatencyOutlierTracker((RevisionLatencyOutlierTracker *)v1530);
  if ( v116 < 0 )
  {
    if ( v1172 && v1271 )
      FreeRevert(v1271);
    v1027 = 24737506;
LABEL_1894:
    v1029 = v116;
LABEL_1880:
    XlsDiag::LogSetHrCoreTag(v1029, v1027);
LABEL_1881:
    v68 = v1160;
LABEL_1882:
    v1015 = v1163;
LABEL_2092:
    if ( v1159 )
    {
      LOBYTE(v261) = v1189 != 0;
      sub_1416B0FA0(v1159, v1307, v261);
      (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v1159 + 56LL))(
        v1159,
        0xFFFFFFFFLL,
        7);
      if ( v1180 )
      {
        HrRecordEvent(v1159, 0x40000000u, 0);
        if ( v1015 && *v1015 )
        {
          v1111 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1368, 0x236962C2u);
          v1112 = SXVWGEOM::RwFirst(v1111);
          v1113 = 0;
          goto LABEL_2097;
        }
      }
      else
      {
        v1114 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1369, 0x236962C1u);
        v1112 = SXVWGEOM::RwFirst(v1114);
        v1113 = 1;
LABEL_2097:
        OlDocFilePath::FReleaseIOLDoc(v1015, v1113, 1, v1112);
      }
    }
LABEL_1935:
    v84 = v1162;
LABEL_2100:
    if ( v1544 )
    {
      if ( v1301 != v1159 && v1301 )
      {
        (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v1301 + 56LL))(
          v1301,
          0xFFFFFFFFLL,
          7);
        if ( v1191 )
          HrRecordEvent(v1301, 0x40000000u, 0);
        v1115 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1370, 0x236962C0u);
        v1116 = SXVWGEOM::RwFirst(v1115);
        OlDocFilePath::FReleaseIOLDoc(&v1301, 1, 1, v1116);
      }
      v1117 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1464);
      CchStToSt(v1117, v84, v1226);
    }
    XslClear((struct XSL *)&v1543);
    vpoldocument = v1351;
    if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL) + 8LL)
        & 1) == 0 )
    {
      FRemoveLoadAction((struct LoadRecovery *)v68, 0);
      if ( v68 )
      {
        LoadRecovery::Destroy((LoadRecovery *)v68);
        FreeHpst(v68);
        v68 = 0;
        v1235 = 0;
      }
    }
    ResetLoadRecovery();
    v1155 = 0;
    if ( !XlFileProtocolManager::FForceCobaltReopenHr(v116) )
    {
      v116 = -2146827284;
      XlsDiag::LogSetHrCoreTag(-2146827284, 0x2385706u);
    }
    v1152 = v1336;
    v1150 = v1256;
    v1149 = v1177;
    v1148 = v116;
    v1146 = v1183;
    v1145 = v1304;
    v1143 = v1272;
    v1142 = v1159;
    v1141 = v1161;
    v1140 = v1253;
    v1139 = v1248;
    v1138 = v1197 != 0;
    v1136 = v1222;
    v1134 = v1302;
    v1132 = (struct LoadRecovery *)v68;
LABEL_2113:
    v1072 = HrFileCompleteLoadEx(
              v84,
              hObject,
              v1155,
              v1184,
              lp,
              v1178,
              v1167,
              v1132,
              v1134,
              v1136,
              v1138,
              v1139,
              v1140,
              v1141,
              v1142,
              v1143,
              v1145,
              v1146,
              v1148,
              (const struct MaxPathHolder *)v1342,
              v1149,
              v1150,
              (struct OsfOpenScope *)v1487,
              (const struct XLOSRR *)&v1237,
              v1152);
LABEL_1992:
    v606 = v1072;
    goto LABEL_2136;
  }
  v255 = FeatureGateCollectionBase<LoadSaveFeatureGates>::Instance();
  if ( (unsigned __int8)Mso::AB::Optimized::FeatureGate::operator bool(v255 + 8) )
  {
    v259 = (const struct OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1541);
    v260 = FileSource::HrSetOlDocFilePath((FileSource *)v1307, v259);
    v116 = v260;
    if ( v260 < 0 )
    {
      XlsDiag::LogSetHrCoreTag(v260, 0x27D405Fu);
      goto LABEL_1881;
    }
    v1154 = FileSource::HrSetPoldoc((FileSource *)v1307, v1159, v1276, v1215);
    v116 = v1154;
    if ( v1154 >= 0 )
      goto LABEL_408;
    v258 = 41969047;
    goto LABEL_407;
  }
  v256 = std::_Optional_construct_base<OlDocFilePath>::operator*(v1541);
  Target = (const wchar_t *)OfficeExtension::ServerRuntime::RichApiMessageEntry::GetTarget(v256);
  v1154 = FileSource::HrSetWin32PathSt((FileSource *)v1307, Target);
  v116 = v1154;
  if ( v1154 < 0 )
  {
    v258 = 41185885;
LABEL_407:
    XlsDiag::LogSetHrCoreTag(v116, v258);
    if ( v116 < 0 )
      goto LABEL_1881;
  }
LABEL_408:
  v262 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1541);
  v263 = OlDocFilePath::StzTitle(v262);
  CchStToStz(v263, &v1569, 257);
  v144 = v1249;
LABEL_409:
  v152 = v1160;
LABEL_410:
  v264 = NtCurrentTeb()->ThreadLocalStoragePointer;
  vhpstErrPath = v84;
  v265 = *(_QWORD *)(*(_QWORD *)v264 + 304LL);
  *(_DWORD *)(v265 + 2024) = 1;
  *(_DWORD *)(v265 + 2028) = 38879640;
  v1155 = 0;
  v266 = 0;
  v1241 = 0;
  v1217 = 0;
  errDeferred = 0;
  v267 = NtCurrentTeb()->ThreadLocalStoragePointer;
  v1246 = (void *)-1LL;
  if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v267 + 304LL) + 872LL) + 104LL) == 2
    && !(unsigned int)FMetroFileEx((struct FileSource *)v1307, 0)
    && !v1157 )
  {
    v1169 = 0;
    if ( MsoDwRegGetDw((const struct _msoreg *)&vmsoridExcelExtractDataMode) == 1 )
      v1187 |= 1u;
    if ( !v1182 && MsoDwRegGetDw((const struct _msoreg *)&vmsoridExcelExtractDataFormulas) == 1 )
      v1187 |= 2u;
    if ( (v1187 & 1) == 0 )
    {
      v266 = FileSource::HpstgiFileOpen(
               (FileSource *)v1307,
               &v1569,
               (unsigned int)(v170 != 0) + 1056,
               0,
               0,
               0,
               0,
               0,
               v1215);
      v1217 = v266;
      v268 = 0;
      if ( !v1159 )
        goto LABEL_422;
      errDeferred = _IMsoOLDocument_GetDeferredError(v1159);
      if ( errDeferred )
        goto LABEL_427;
      v268 = 0;
LABEL_422:
      if ( !v170 )
      {
        if ( (unsigned int)FErrPstgi(v266) )
          v268 = (unsigned __int16)PstgiFromErr((unsigned __int16)v266);
        else
          v268 = 0;
      }
      errDeferred = v268;
      if ( v268 )
      {
LABEL_427:
        v1165 = 1;
        v266 = FileSource::HpstgiFileOpen((FileSource *)v1307, &v1569, 0x421u, 0, 0, 0, 0, 0, v1215);
        v1217 = v266;
      }
    }
    if ( (unsigned int)FErrPstgi(v266) )
    {
LABEL_437:
      v1187 |= 1u;
    }
    else
    {
      v1169 = 0;
      v269 = SXVWGEOM::RwFirst(v266);
      STGI::SetSlf(v266, v269 & 0xFFFFFFDF);
      if ( v170 || (v270 = 1152, v1165) )
        v270 = 1153;
      v271 = v270 | SXVWGEOM::RwFirst(v266) & 0x800;
      v272 = STGI::Lpstg(v266);
      v273 = ScStgIdsStreamOpen(v272, v271, 0, v1568, &v1169, -1161035344, 9);
      v274 = v273 == 0;
      if ( !v273 && !(unsigned int)FValidDRDocStream(v1169) )
      {
        StreamClose(v1169);
        v1169 = 0;
        v274 = 0;
      }
      if ( !v274 )
      {
        StgiFileClose(v266);
        v266 = 0;
        v1217 = 0;
        goto LABEL_437;
      }
    }
    if ( (v1187 & 1) == 0 )
      goto LABEL_439;
LABEL_1015:
    v555 = FileSource::StzFileName((FileSource *)v1307);
    if ( (unsigned int)FFinderFile(v555) )
    {
      v170 = 1;
      v1173 = 1;
      v1216 = 1;
      vfPretendNotStg = 1;
    }
    goto LABEL_1038;
  }
  if ( wProjLoad != 2 )
  {
    if ( a7 == 1024 )
    {
      v374 = v1166;
      goto LABEL_658;
    }
    v1214 = 0;
    v280 = 0;
    v281 = APPCORE::PmemheapMain((APPCORE *)&vapp);
    MaxPathHolder::MaxPathHolder((MaxPathHolder *)v1315, v281, 259, 0);
    if ( (unsigned int)FOsrcHostedByExcel() )
    {
      MaxPathStzPoke::MaxPathStzPoke((MaxPathStzPoke *)v1485, (struct MaxPathHolder *)v1315);
      v282 = MaxPathStzPoke::CchStzBufferSize((MaxPathStzPoke *)v1485);
      v283 = (wchar_t *)SlicerViewImpl::PSlicerView((SlicerViewImpl *)v1485);
      CnvTempFile = FileSource::HrGetCnvTempFile((FileSource *)v1307, v283, v282, &v1231, &v1189);
      v280 = CnvTempFile;
      if ( CnvTempFile < 0 )
      {
        v116 = CnvTempFile;
        XlsDiag::LogSetHrCoreTag(CnvTempFile, 0x17976E3u);
        MaxPathStzPoke::~MaxPathStzPoke((MaxPathStzPoke *)v1485);
LABEL_465:
        MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1315);
        goto LABEL_466;
      }
      v285 = (MaxPathStzPoke *)v1485;
    }
    else
    {
      if ( v1157 || v1174 )
      {
LABEL_473:
        if ( v1189 )
        {
          if ( v1159 )
          {
            v144 = IMsoOLDocument::IsInFileSys(v1159) != 0;
            v1249 = v144;
            v1260 = v144;
          }
          v288 = v1173;
          if ( v1231 == 68 )
            v288 = 1;
          v1173 = v288;
          v1216 = v288;
          v289 = FileSource::SzFilePath((FileSource *)v1307);
          MaxPathHolder::CchCopyFromSz((MaxPathHolder *)v1484, v289);
          v290 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1315);
          v291 = FileSource::HrSetWin32PathSt((FileSource *)v1307, v290);
          v1154 = v291;
          v116 = v291;
          if ( v291 < 0 )
          {
            XlsDiag::LogSetHrCoreTag(v291, 0x274139Du);
            goto LABEL_465;
          }
          v292 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL);
          v1251 = 0;
          *(_DWORD *)(v292 + 104) = 0;
          a10 &= ~8u;
          FRemoveLoadAction((struct LoadRecovery *)v152, 0);
          if ( v152 )
          {
            LoadRecovery::Destroy((LoadRecovery *)v152);
            FreeHpst(v152);
            v1160 = 0;
            v1235 = 0;
          }
        }
        v293 = FileSource::StzFileName((FileSource *)v1307);
        if ( (unsigned int)FFinderFile(v293) )
        {
          v1187 |= 1u;
          v1171 = 1;
          v1169 = 0;
          MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1315);
          goto LABEL_1014;
        }
        if ( v1157 )
        {
          if ( !v1170 )
          {
            v295 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1181);
            v296 = (LXBASE *)OpenTelemetry::POpenFileStageModel(v295);
            v297 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1390, 0x1F0CB5D1u);
            SXVWGEOM::RwFirst(v297);
            WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v296);
            v298 = PstgiFromErr(1u);
            v299 = v1189;
            v266 = v298;
            v1217 = v298;
            v300 = v1238;
            v1196 = 5;
            if ( v1189 )
              v300 = v1231;
            v1238 = v300;
            v1466 = 0;
            memset_0(&v1467, 0, 0x58u);
            v1468 = 257;
            v1479 = 0;
            v1480 = 0;
            v1481 = 0;
            v1482 = 0;
            v1467 = &v1569;
            if ( !v299 || (v301 = (BKORWS *)v1484, v144) )
              v301 = (BKORWS *)v1341;
            v302 = BKORWS::Psh(v301);
            v68 = v1160;
            v1469 = v302;
            v1470 = a5;
            v1471 = v1246;
            v1472 = v1159;
            v1466 = &v1237;
            v1482 = v1160;
            MaxPathStzPoke::MaxPathStzPoke((MaxPathStzPoke *)v1504, (struct MaxPathHolder *)v1315);
            v303 = 0;
            if ( v1189 )
              v303 = SlicerViewImpl::PSlicerView((SlicerViewImpl *)v1504);
            v1477 = v303;
            MaxPathStzPoke::~MaxPathStzPoke((MaxPathStzPoke *)v1504);
            v1476 = v1189;
            v1473 = v1182;
            v1474 = v1187 & 2;
            v1475 = v1212 != 1;
            v1478 = v1272;
            v1481 = v1227;
            if ( AppGuard::Config::IsEnabled(v304) )
              v1479 = (a10 & 0x80000) != 0;
            v1480 = v1218 == 1;
            v305 = HrLoadInSecureReader((const struct XLOSRLA *)&v1466, v1215);
            v306 = NtCurrentTeb()->ThreadLocalStoragePointer;
            v1179 = v305;
            v1155 = v305 >= 0;
            v1246 = (void *)-1LL;
            v1225 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v306 + 304LL) + 2924LL);
            if ( v305 >= 0 )
              RenumberWind(*(struct SH **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                         + 32LL));
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1222;
            v1153 = 0;
            v116 = v1179;
            v1154 = v1179;
            if ( v1179 < 0 )
            {
              XlsDiag::LogSetHrCoreTag(v1179, 0x1797700u);
              if ( v1179 < 0 )
              {
                v307 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1181);
                v308 = OpenTelemetry::POpenFileStageModel(v307);
                v309 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1391, 0x1F0CB5D0u);
                v310 = SXVWGEOM::RwFirst(v309);
                WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v308, (unsigned int)v1179, v310);
              }
            }
            MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1315);
            goto LABEL_910;
          }
          v294 = BKORWS::Psh((BKORWS *)&v1181);
          if ( (int)XlFileProtocolManager::HrRequestCobaltReopen(v1159, v1202, -1662189471, v294) < 0 )
            MsoShipAssertTagProc(506512324);
          v116 = -1662189471;
          XlsDiag::LogSetHrCoreTag(-1662189471, 0x1E30C3C3u);
          goto LABEL_465;
        }
        v311 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                         + 104LL);
        v312 = APPCORE::PmemheapMain((APPCORE *)&vapp);
        v313 = APPCORE::PlocaleinfoUSEN((APPCORE *)&vapp);
        v314 = FSmellsLikeMetroFileCancelable(
                 (struct FileSource *)v1307,
                 v313,
                 0,
                 v312,
                 &v1250,
                 v311 == 0,
                 &v1242,
                 &v1214);
        if ( v1214 )
        {
          v315 = 579396827;
          v316 = -2147023673;
LABEL_506:
          XlsDiag::LogSetHrCoreTag(v316, v315);
LABEL_507:
          v317 = (MaxPathHolder *)v1315;
LABEL_508:
          MaxPathHolder::~MaxPathHolder(v317);
          v68 = v1160;
          goto LABEL_815;
        }
        v318 = FeatureGateCollectionBase<LoadSaveFeatureGates>::Instance();
        if ( (unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(v318 + 488) )
        {
          v319 = (CorruptionMetaData *)std::_Optional_construct_base<CorruptionMetaData>::operator*(v1540);
          CorruptionMetaData::SetFEncrypted(v319, v1242 != 0);
          v320 = (CorruptionMetaData *)std::_Optional_construct_base<CorruptionMetaData>::operator*(v1540);
          v321 = sub_1402DFAB0(v1541);
          CorruptionMetaData::SetFDrmProtected(v320, v321);
        }
        if ( v1269 && !v314 )
        {
          MsoShipAssertTagProc(504410774);
          v315 = 504410773;
          v316 = -2147467260;
          goto LABEL_506;
        }
        if ( v1189 && (v1250 || !v314) )
        {
          FileSource::HrDeleteTemp((FileSource *)v1307);
          v116 = -2146827284;
          v322 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          *(_DWORD *)(v322 + 2024) = 0;
          *(_DWORD *)(v322 + 2028) = 0;
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1222;
          XlsDiag::LogSetHrCoreTag(-2146827284, 0x1797701u);
          MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1315);
          v68 = v1160;
          goto LABEL_518;
        }
        v68 = v1160;
        if ( v1250 && !LoadRecovery::FRepairPkg((LoadRecovery *)v1160) )
        {
          LoadRecovery::SetRepairPkg((LoadRecovery *)v68);
          v323 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          *(_DWORD *)(v323 + 2024) = 0;
          *(_DWORD *)(v323 + 2028) = 0;
          v116 = -2146827284;
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1222;
          XlsDiag::LogSetHrCoreTag(-2146827284, 0x1797702u);
          MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1315);
LABEL_467:
          v279 = v1162;
          goto LABEL_1664;
        }
        v324 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1181);
        v325 = (LXBASE *)OpenTelemetry::POpenFileStageModel(v324);
        v326 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1392, 0x1F0CB5CFu);
        SXVWGEOM::RwFirst(v326);
        WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v325);
        if ( !v314 )
        {
          MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1315);
          goto LABEL_524;
        }
        v266 = PstgiFromErr(7u);
        v1217 = v266;
        if ( v1174 )
        {
          if ( !(unsigned int)FOsrc() )
          {
            v331 = FileSource::StzFileName((FileSource *)v1307);
            if ( !(unsigned int)sub_14240ED50(v331) )
            {
              SetLoadForPreviewError(-2147467259);
              XlsDiag::LogSetHrCoreTag(-2147467260, 0x1797703u);
              v332 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1181);
              v333 = OpenTelemetry::POpenFileStageModel(v332);
              v334 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1462, 0x1F0CB5CEu);
              v335 = SXVWGEOM::RwFirst(v334);
              WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v333, 2214658820LL, v335);
LABEL_543:
              MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1315);
              goto LABEL_815;
            }
          }
        }
        std::optional<DataLossProtection::NotifyRaiiHintsForPrePostEvents>::optional<DataLossProtection::NotifyRaiiHintsForPrePostEvents>(v1338);
        v337 = v1173;
        if ( !v1173 && !FileSource::FCloud((FileSource *)v1307) )
        {
          v338 = APPCORE::PmemheapMain((APPCORE *)&vapp);
          MaxPathHolder::MaxPathHolder((MaxPathHolder *)v1511, v338, 259, 0);
          if ( IsWin32AppRunningInWdag() )
            v339 = (wchar_t *)FileSource::StzFileName((FileSource *)v1307);
          else
            v339 = v1162;
          MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1511, v339);
          v340 = *(const wchar_t **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 784LL);
          v341 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1511);
          v280 = HrWriteOwnerFile(v1159, v341, v340, &v1246);
          v342 = BKORWS::Psh((BKORWS *)v1511);
          v343 = PbookFromPioldoc(v1159);
          DataLossProtectionHelper::spCreateCustomInfoContext(v1345, v343, v342);
          v1442 = BKORWS::Psh((BKORWS *)v1345);
          v1326 = 5;
          v1325 = 6;
          v1443 = APPCORE::PmemheapMain((APPCORE *)&vapp);
          std::optional<DataLossProtection::NotifyRaiiHintsForPrePostEvents>::emplace<IMemHeap *,IMsoOLDocument * &,enum Mso::Dlp::Event,enum Mso::Dlp::Event,DataLossProtection::XLSInfoContext *>(
            (unsigned int)v1338,
            (unsigned int)&v1443,
            (unsigned int)&v1159,
            (unsigned int)&v1326,
            (__int64)&v1325,
            (__int64)&v1442);
          Mso::TCntPtr<DataLossProtection::XLSInfoContext>::~TCntPtr<DataLossProtection::XLSInfoContext>(v1345);
          MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1511);
        }
        LOBYTE(v336) = std::nullopt;
        if ( !(unsigned __int8)std::operator==<DataLossProtection::NotifyRaiiHintsForPrePostEvents>(v1338, v336) )
        {
          v344 = sub_1404519F0(v1525, v1338, &v1179);
          sub_1406219BC(v1519, v344);
          sub_1406219CC(v1519);
        }
        if ( v280 == -2147024864 )
        {
          v266 = PstgiFromErr(2u);
          v1217 = v266;
LABEL_618:
          if ( (unsigned int)FErrPstgi(v266) )
          {
            v371 = (unsigned __int16)PstgiFromErr((unsigned __int16)v266);
            v372 = v1224;
            v373 = v371;
            if ( v371 == 7 )
            {
              v374 = v1166;
              if ( v1224 == -2147024891 )
                v374 = 1;
              v1166 = v374;
            }
            else
            {
              v374 = v1166;
            }
            v68 = v1160;
            if ( v371 != 7 && v371 != 2 && v1251 && v1160 && LoadRecovery::FRepairPkg((LoadRecovery *)v1160) )
            {
              v1266 = 1;
              LoadRecovery::SetRepairState((LoadRecovery *)v68, -2146827284);
              if ( v373 == 1 && (unsigned int)(v372 + 2134241024) > 1 )
              {
                if ( v372 >= 0 )
                  v372 = -2146827284;
                XlsDiag::LogSetHrCoreTag(v372, 0x1797706u);
                std::_Optional_destruct_base<DataLossProtection::NotifyRaiiHintsForPrePostEvents,0>::reset(v1338);
                MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1315);
                goto LABEL_817;
              }
              if ( v372 >= 0 )
                v372 = -2147467260;
              v375 = 24737543;
              v376 = v372;
              goto LABEL_642;
            }
            if ( v373 == 1 )
            {
              if ( v372 == -2134195936
                && (unsigned int)Mso::Details::ConstexprFunctorBase<Mso::IFunctor<bool,FeaturePropertyValue const &,FeaturePropertyValue const &>>::Release(&vapp) )
              {
                v1179 = v1224;
                ErrorAlert(459071, v1570);
                v376 = v1179;
                if ( v1179 >= 0 )
                {
LABEL_643:
                  std::_Optional_destruct_base<DataLossProtection::NotifyRaiiHintsForPrePostEvents,0>::reset(v1338);
                  goto LABEL_543;
                }
                v375 = 24737544;
LABEL_642:
                XlsDiag::LogSetHrCoreTag(v376, v375);
                goto LABEL_643;
              }
              v116 = -2146827284;
              v1154 = -2146827284;
              XlsDiag::LogSetHrCoreTag(-2146827284, 0x230E1E1u);
              std::_Optional_destruct_base<DataLossProtection::NotifyRaiiHintsForPrePostEvents,0>::reset(v1338);
              MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1315);
LABEL_645:
              v377 = APPCORE::PlocaleinfoUSEN((APPCORE *)&vapp);
              if ( (unsigned int)FMetroFileExt((const struct FileSource *)v1307, v377, 0, 0) )
              {
                v68 = v1160;
                if ( v1160 )
                {
                  if ( LoadRecovery::FRepairPkg((LoadRecovery *)v1160)
                    || (unsigned __int16)PstgiFromErr((unsigned __int16)v266) == 7 )
                  {
                    OkAlert(v374 != 0 ? 262202 : 458868, v1570);
                    XlsDiag::LogSetHrCoreTag(v374 != 0 ? -2147024891 : -2146827284, 0x230E200u);
                    if ( !v374 )
                    {
                      v459 = (CorruptionMetaData *)std::_Optional_construct_base<CorruptionMetaData>::operator*(v1540);
                      CorruptionMetaData::MarkAsCorrupt(v459);
                    }
                    if ( v1174 )
                      SetLoadForPreviewError(v374 != 0 ? -2147024891 : -2042494972);
                    goto LABEL_815;
                  }
                  v1250 = 1;
                  LoadRecovery::SetRepairPkg((LoadRecovery *)v68);
                }
LABEL_817:
                v461 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                *(_DWORD *)(v461 + 2024) = 0;
                *(_DWORD *)(v461 + 2028) = 0;
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1222;
                v1153 = 0;
                if ( (unsigned int)FErrPstgi(v266) && v1246 != (void *)-1LL )
                {
                  CloseSentinelFile(v1246);
                  v1246 = (void *)-1LL;
                }
                v116 = -2146827284;
                XlsDiag::LogSetHrCoreTag(-2146827284, 0x230E201u);
                goto LABEL_821;
              }
LABEL_524:
              v170 = v1173;
              if ( a7 == 1024 )
                goto LABEL_839;
              v327 = 1024;
              v328 = 1024;
              if ( v1173 )
              {
                v327 = 1025;
                v328 = 1025;
              }
              v329 = v327;
              if ( *(_QWORD *)&UIGLOBALS::UIGLOBALSCONTAINER::m_posi )
              {
                v330 = *(_QWORD *)(*(_QWORD *)&UIGLOBALS::UIGLOBALSCONTAINER::m_posi + 1568LL);
                if ( v330 )
                {
                  if ( !*(_QWORD *)(v330 + 256) )
                  {
                    v328 = v327 | 0x20;
                    v329 = v327 | 0x20;
                  }
                }
              }
              if ( v1174 )
                v328 = v329 | 0x1000000;
              v266 = FileSource::HpstgiFileOpen((FileSource *)v1307, &v1569, v328, 0, &v1245, 0, 0, 0, v1215);
              v1217 = v266;
              v1176 = 1;
              if ( !v1174 || !(unsigned int)FErrPstgi(v266) || (unsigned int)FOsrc() && !MsoFDrmErrorCode(v1245) )
              {
                if ( (unsigned int)FErrPstgi(v266)
                  && (unsigned __int16)PstgiFromErr((unsigned __int16)v266) != 4
                  && !*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                            + 872LL)
                                + 104LL)
                  && v1251
                  && (v1245 == -2147286775 || v1245 == -2147287010) )
                {
                  v1233 = 1;
                }
LABEL_839:
                if ( a7 == 1024
                  || (unsigned int)FErrPstgi(v266) && (unsigned __int16)PstgiFromErr((unsigned __int16)v266) == 4 )
                {
                  goto LABEL_1015;
                }
                v1169 = 0;
                if ( (unsigned int)FErrPstgi(v266) )
                {
                  v470 = 0;
                  if ( v1159 )
                  {
                    errDeferred = _IMsoOLDocument_GetDeferredError(v1159);
                    if ( errDeferred )
                      goto LABEL_853;
                    v470 = 0;
                  }
                  if ( !v170 )
                  {
                    if ( (unsigned int)FErrPstgi(v266) )
                      v470 = (unsigned __int16)PstgiFromErr((unsigned __int16)v266);
                    else
                      v470 = 0;
                  }
                  errDeferred = v470;
                  goto LABEL_852;
                }
                v468 = ((v170 != 0) + 1024) | SXVWGEOM::RwFirst(v266) & 0x800;
                v469 = STGI::Lpstg(v266);
                ScStgIdsStreamOpen(v469, v468, 0, v1568, &v1169, -1161035344, 9);
                v470 = errDeferred;
LABEL_852:
                if ( !v470 )
                  goto LABEL_439;
LABEL_853:
                v1252 = -2147467259;
LABEL_1005:
                v1233 = 0;
                v1165 = 1;
                v551 = v1159
                    && ((*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1159 + 224LL))(v1159) & 1) != 0
                    && errDeferred == 2;
                v552 = FileSource::HpstgiFileOpen((FileSource *)v1307, &v1569, 0x401u, 0, &v1252, 0, 0, v551, v1215);
                v116 = v1252;
                v266 = v552;
                v1217 = v552;
                v1154 = v1252;
                if ( !(unsigned int)FErrPstgi(v552) )
                {
                  v1171 = 0;
                  v553 = SXVWGEOM::RwFirst(v266) & 0x800 | 0x401;
                  v554 = STGI::Lpstg(v266);
                  ScStgIdsStreamOpen(v554, v553, 0, v1568, &v1169, -1161035344, 9);
                  v170 = v1173;
                  goto LABEL_439;
                }
                if ( (unsigned __int16)PstgiFromErr((unsigned __int16)v266) != 4 )
                {
                  if ( v1252 == -2147287010 || v1252 == -2147286775 )
                  {
                    OkAlert(262188, 0);
                  }
                  else if ( v1252 != -2147217391 )
                  {
                    MsoSetLastWAlertHRTag(v1252, 0x376C7370u);
                    MsoShipAssertTagProc(892367981);
                    OkAlert(196657, v1570);
                    MsoResetLastWAlertHR();
                  }
LABEL_1022:
                  v170 = v1173;
                  goto LABEL_439;
                }
                v1171 = 1;
LABEL_1014:
                v170 = v1173;
                goto LABEL_1015;
              }
              if ( MsoFDrmErrorCode(v1245) )
              {
                v116 = -2042494975;
              }
              else if ( (unsigned __int16)PstgiFromErr((unsigned __int16)v266) == 4 )
              {
                v116 = -2042490872;
              }
              else if ( v1245 == -2147286775
                     || (unsigned int)(v1245 + 2147286780) <= 1
                     || v1245 == -2147286960
                     || (v116 = -2147467259, v1245 == -2147287010) )
              {
                v116 = -2042494972;
              }
              SetLoadForPreviewError(v116);
              XlsDiag::LogSetHrCoreTag(v116, 0x179770Eu);
              v462 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1181);
              v463 = OpenTelemetry::POpenFileStageModel(v462);
              v464 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1400, 0x1F0CB5C9u);
              v465 = SXVWGEOM::RwFirst(v464);
              WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v463, (unsigned int)v116, v465);
              v68 = v1160;
              v466 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
              *(_DWORD *)(v466 + 2024) = 0;
              *(_DWORD *)(v466 + 2028) = 0;
              *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1222;
              LOBYTE(v266) = 0;
              if ( v68 )
                goto LABEL_830;
              v279 = v1162;
              goto LABEL_1664;
            }
          }
          else
          {
            v374 = v1166;
          }
          if ( !(unsigned int)FErrPstgi(v266) )
          {
            if ( v1242 )
            {
              if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1836LL) )
              {
                v378 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1541);
                v379 = OlDocFilePath::PClpDocument(v378);
                EncryptedStorage = STGI::GetEncryptedStorage(v266);
                if ( !(unsigned int)FDrmQueryRightsStg(EncryptedStorage, 2u, v379) )
                {
                  StgiFileClose(v266);
                  HandleLockError(327752);
                  v350 = 36757986;
                  v381 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                  *(_DWORD *)(v381 + 2024) = 0;
                  *(_DWORD *)(v381 + 2028) = 0;
                  goto LABEL_589;
                }
              }
            }
          }
          std::_Optional_destruct_base<DataLossProtection::NotifyRaiiHintsForPrePostEvents,0>::reset(v1338);
          MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1315);
LABEL_658:
          if ( a7 == 1024
            || (unsigned int)FErrPstgi(v266) && (unsigned __int16)PstgiFromErr((unsigned __int16)v266) == 7 )
          {
            goto LABEL_645;
          }
          if ( !(unsigned int)FErrPstgi(v266) || (unsigned __int16)PstgiFromErr((unsigned __int16)v266) == 8 )
          {
            DeferredError = errDeferred;
          }
          else
          {
            DeferredError = 0;
            if ( v1159 )
            {
              DeferredError = _IMsoOLDocument_GetDeferredError(v1159);
              errDeferred = DeferredError;
              if ( DeferredError )
                goto LABEL_673;
              DeferredError = 0;
            }
            if ( !v1173 )
            {
              if ( (unsigned int)FErrPstgi(v266) )
              {
                DeferredError = (unsigned __int16)PstgiFromErr((unsigned __int16)v266);
                errDeferred = (unsigned __int16)DeferredError;
                goto LABEL_672;
              }
              DeferredError = 0;
            }
            errDeferred = 0;
          }
LABEL_672:
          if ( !DeferredError )
          {
            v68 = v1160;
            goto LABEL_734;
          }
LABEL_673:
          if ( v1246 != (void *)-1LL )
          {
            CloseSentinelFile(v1246);
            DeferredError = errDeferred;
            v1246 = (void *)-1LL;
          }
          if ( v1189 )
          {
            v384 = v1212;
          }
          else
          {
            v383 = FIsShareErr(DeferredError);
            v384 = v1212;
            if ( v383
              && v1212 == 1
              && (int)HrGetRealMetroFileType((struct FileSource *)v1307, (enum FILETYPE *)&v1287) >= 0
              && (v1287 == 54 || v1287 == 17 ? (v385 = 1) : (v385 = 0), v385) )
            {
              DeferredError = 0;
              errDeferred = 0;
            }
            else
            {
              DeferredError = errDeferred;
            }
          }
          if ( (unsigned int)FIsShareErr(DeferredError) && v384 == 1 )
          {
            v386 = APPCORE::PmemheapMain((APPCORE *)&vapp);
            MaxPathHolder::MaxPathHolder((MaxPathHolder *)v1493, v386, 259, 0);
            ENV::ENV((ENV *)&v1556);
            MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1493, v1162);
            FileTemp = FileSource::HrGetFileTemp(v1307, 5);
            v1154 = FileTemp;
            if ( FileTemp < 0 )
            {
              XlsDiag::LogSetHrCoreTag(FileTemp, 0x2806598u);
              XlsDiag::LogSetHrCoreTag(-2146827284, 0x2806599u);
              v317 = (MaxPathHolder *)v1493;
              goto LABEL_508;
            }
            v388 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
            v1444 = *(_QWORD *)(v388 + 336);
            *(_QWORD *)(v388 + 336) = &v1556;
            v1557 = 36737603;
            if ( !setjmp(v1558) )
            {
              v389 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1493);
              if ( (int)HrReadOwnerFile(v389, v1578, 257) < 0 )
              {
                v391 = !v1189 && FileHost::FIsEncryptedMetroFile((FileHost *)v1307, v390);
                v392 = FileSource::StzFilePath((FileSource *)v1307);
                v393 = 0;
              }
              else
              {
                v391 = !v1189 && FileHost::FIsEncryptedMetroFile((FileHost *)v1307, v390);
                v392 = FileSource::StzFilePath((FileSource *)v1307);
                v393 = v1578;
              }
              HrDeferredSRO(&v1569, v393, v392, 0, v391);
            }
            v394 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
            *(_QWORD *)(v394 + 336) = v1444;
            if ( (_QWORD)xmmword_143FE0F70 )
            {
              LOBYTE(v394) = v1185;
              v395 = sub_141224980(v1159, v394, &v1197);
              v1212 = v395;
              if ( v395 < 0 )
              {
                errDeferred = 0;
                v1167 = 1;
                XlsDiag::LogSetHrCoreTag(v395, 0x1797709u);
                v396 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1181);
                v397 = OpenTelemetry::POpenFileStageModel(v396);
                v398 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1394, 0x1F0CB5CCu);
                v399 = SXVWGEOM::RwFirst(v398);
                WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v397, 2214658821LL, v399);
                MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1493);
                v68 = v1235;
                v266 = v1217;
                v1162 = Src;
                v1163 = v1247;
                v1173 = v1216;
                goto LABEL_815;
              }
              if ( v1197 )
                OSRR::SetAppAllowed((OSRR *)&v1237, 0);
            }
            MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1493);
            v68 = v1235;
            v116 = v1154;
            v374 = v1166;
            v1170 = v1186;
            v1249 = v1260;
            v1162 = Src;
            v1173 = v1216;
            v1163 = v1247;
            v1160 = v1235;
          }
          else
          {
            v68 = v1160;
          }
          v400 = 0;
          if ( v68 )
            v400 = (int)LoadRecovery::Lrmode(v68) > 0;
          v401 = v400 && LoadRecovery::FRepairPkg((LoadRecovery *)v68);
          v1250 = v401;
          v402 = BKORWS::Psh((BKORWS *)&v1181);
          v1217 = (struct STGI *)FileSource::HpstgiFileOpenEx(
                                   v1307,
                                   2098177,
                                   0,
                                   &v1261,
                                   0,
                                   v1250,
                                   0,
                                   0,
                                   0,
                                   v1574,
                                   &v1253,
                                   &v1569,
                                   0,
                                   0,
                                   0,
                                   0,
                                   v1269,
                                   0,
                                   v1215,
                                   v402);
          v266 = v1217;
          if ( (unsigned int)FErrPstgi(v1217) )
          {
            v116 = -2146827284;
            v1154 = -2146827284;
            XlsDiag::LogSetHrCoreTag(-2146827284, 0x230E1E3u);
          }
          else
          {
            v1188 = 1;
          }
          if ( (unsigned int)FErrPstgi(v266) && (unsigned __int16)PstgiFromErr((unsigned __int16)v266) == 8 )
          {
            v403 = v1261;
LABEL_724:
            if ( v403 == -2147168507 )
            {
              MsoShipAssertTagProc(505156896);
              v403 = v1261;
            }
            v1179 = v403;
            if ( v403 >= 0 )
              v403 = -2147467260;
            XlsDiag::LogSetHrCoreTag(v403, 0x179770Au);
            v404 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1181);
            v405 = OpenTelemetry::POpenFileStageModel(v404);
            v406 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1395, 0x1F0CB5CBu);
            v407 = SXVWGEOM::RwFirst(v406);
            v408 = 2214658821LL;
            if ( v1179 < 0 )
              v408 = (unsigned int)v1179;
            WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v405, v408, v407);
            goto LABEL_815;
          }
          v403 = v1261;
          if ( v1261 == -2147168507 )
            goto LABEL_724;
          if ( !(unsigned int)FErrPstgi(v266) )
          {
            v1165 = 1;
            errDeferred = 0;
          }
LABEL_734:
          if ( !(unsigned int)FErrPstgi(v266) )
          {
            if ( !v1159
              || ((*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1159 + 224LL))(v1159) & 1) == 0
              || (v409 = STGI::Pxpkg(v266), !(unsigned int)FIsSharedWbk(v409)) )
            {
              if ( v68 )
              {
                v415 = PivotOperationBase::PSxview((PivotOperationBase *)v68);
                *((_WORD *)v415 + 18) |= 4u;
              }
              v416 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 2024LL);
              v1200 = v416 != 0;
              if ( !v416 )
                XlsDiag::SendTraceTag(38048668, 187, 50, 4, L"FInLoad expected to be false at that point");
              v417 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1181);
              v418 = (LXBASE *)OpenTelemetry::POpenFileStageModel(v417);
              v419 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1396, 0x1F0CB5CAu);
              SXVWGEOM::RwFirst(v419);
              WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v418);
              MaxPathStPoke::MaxPathStPoke((MaxPathStPoke *)v1491, (struct MaxPathHolder *)v1341);
              v420 = BKORWS::Psh((BKORWS *)&v1181);
              v421 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1541);
              Context = OlDocFilePath::PClpLoadContext(v421);
              v1446 = std::_Optional_construct_base<CorruptionMetaData>::operator*(v1540);
              v1448 = v1159;
              if ( v1189 )
                v422 = BKORWS::Psh((BKORWS *)v1484);
              else
                v422 = 0;
              v423 = v1253;
              v424 = a10 & 0x800;
              v425 = (struct OpenTelemetry *)v1246;
              if ( v1173 || (v426 = 0, v1165) )
                v426 = 1;
              v427 = MaxPathSzPoke::CchSzBufferSize((MaxPathSzPoke *)v1491);
              v428 = SlicerViewImpl::PSlicerView((SlicerViewImpl *)v1491);
              LOBYTE(v1151) = v1161;
              v1147[0] = v1249;
              v1144 = v422;
              v68 = v1160;
              v1137 = v425;
              v266 = v1217;
              LODWORD(v1135) = 0;
              LODWORD(v1133) = a7;
              LODWORD(v1131) = a5;
              LODWORD(v1130) = v426;
              LODWORD(v1128) = v427;
              v1179 = HrLoadMetro(
                        0,
                        v1217,
                        &v1569,
                        v1307,
                        v428,
                        v1128,
                        v1130,
                        v1131,
                        v1133,
                        v1135,
                        v1137,
                        &v1196,
                        v1160,
                        v1574,
                        v423,
                        v424,
                        v1144,
                        &v1237,
                        *(_QWORD *)v1147,
                        v1448,
                        v1272,
                        v1447,
                        &v1290,
                        v1446,
                        v1151,
                        Context,
                        v1275,
                        v420);
              MaxPathStPoke::~MaxPathStPoke((MaxPathStPoke *)v1491);
              v429 = v1179;
              v1154 = v1179;
              v116 = v1179;
              if ( v1179 < 0 )
              {
                XlsDiag::LogSetHrCoreTag(v1179, 0x17D88D8u);
                v429 = v1179;
                if ( v1179 < 0 )
                {
                  if ( OSRR::FReadyForOsr((OSRR *)&v1237) )
                  {
                    v73 = 1;
                    goto LABEL_764;
                  }
                  v429 = v1179;
                }
              }
              v1155 = v429 >= 0;
              if ( v429 >= 0 )
                v1304 = *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                        + 40LL);
              v430 = NtCurrentTeb()->ThreadLocalStoragePointer;
              v1246 = (void *)-1LL;
              v1225 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v430 + 304LL) + 2924LL);
              if ( v429 < 0 )
              {
                if ( v1189 )
                {
                  FileSource::HrDeleteTemp((FileSource *)v1307);
                  v429 = v1179;
                }
                if ( v68 && (v429 == -2134142954 || v429 == -2134188030) )
                  LoadRecovery::SetRepairState((LoadRecovery *)v68, v429);
                v73 = 1;
              }
              else
              {
                if ( v1189 && v1231 != 68 )
                {
                  v431 = LOCATIONCONTEXTDATA::PWorkbookCur((LOCATIONCONTEXTDATA *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                             + 304LL)
                                                                                 + 8LL));
                  Api::Workbook::SetFt(v431, (unsigned int)v1231, 0);
                }
                v432 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                if ( *(_DWORD *)(*(_QWORD *)(v432 + 872) + 104LL) == 2 && (v1187 & 2) == 0 )
                {
                  v1270 = *(struct SH **)(v432 + 32);
                  v433 = LOCATIONCONTEXTDATA::PWorkbookCur((LOCATIONCONTEXTDATA *)(v432 + 8));
                  v434 = OcsTransitionController::PCoauthTransitionState(v433);
                  v435 = XLSBOOK::Plxtab(v434);
                  v436 = SlicerViewImpl::PSlicerView(v435);
                  v437 = LOCATIONCONTEXTDATA::PWorkbookCur((LOCATIONCONTEXTDATA *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                             + 304LL)
                                                                                 + 8LL));
                  v438 = OcsTransitionController::PCoauthTransitionState(v437);
                  v439 = (TAB *)((char *)v436 + 16 * *((int *)XLSBOOK::Plxtab(v438) + 1));
                  if ( v436 < v439 )
                  {
                    v440 = NtCurrentTeb()->ThreadLocalStoragePointer;
                    do
                    {
                      v441 = TAB::PshDesktopOnly(v436);
                      if ( (*((_BYTE *)v441 + 10) & 4) != 0 )
                        v442 = 0;
                      else
                        v442 = *((_BYTE *)v441 + 8);
                      if ( v442 <= 1u )
                      {
                        v443 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1397, 0x237630D9u);
                        v444 = SXVWGEOM::RwFirst(v443);
                        v445 = TAB::PshDesktopOnly(v436);
                        v446 = *(_QWORD *)(*(_QWORD *)v440 + 304LL);
                        v447 = 0;
                        v448 = *(_QWORD **)(v446 + 128);
                        if ( v448 )
                        {
                          v449 = *(_QWORD **)(v446 + 128);
                          do
                          {
                            v447 = v449[1];
                            if ( v447 )
                              break;
                            v448 = (_QWORD *)*v448;
                            v449 = v448;
                          }
                          while ( v448 );
                        }
                        LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v447 + 96), v445, v444);
                        v450 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v440 + 304LL) + 32LL);
                        if ( !((*(_BYTE *)(v450 + 10) & 4) != 0 ? 0 : *(_BYTE *)(v450 + 8)) )
                        {
                          v277 = HrConvertSheetFmlaToVal();
                          if ( v277 < 0 )
                          {
LABEL_1910:
                            v1168 = v277;
                            goto LABEL_1133;
                          }
                        }
                      }
                      v436 = (TAB *)((char *)v436 + 16);
                    }
                    while ( v436 < v439 );
                    v68 = v1160;
                  }
                  v452 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1398, 0x237630D8u);
                  v453 = SXVWGEOM::RwFirst(v452);
                  v454 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 128LL);
                  v455 = 0;
                  if ( v454 )
                  {
                    v456 = v454;
                    do
                    {
                      v455 = v456[1];
                      if ( v455 )
                        break;
                      v454 = (_QWORD *)*v454;
                      v456 = v454;
                    }
                    while ( v454 );
                  }
                  LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v455 + 96), v1270, v453);
                  v266 = v1217;
                }
                if ( (unsigned int)Api::Workbook::FtFileType(
                                     *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                               + 40LL)
                                   + 1640LL) == 59 )
                  BindODFChartData(*(const struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                     + 304LL)
                                                         + 40LL));
                RenumberWind(*(struct SH **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                           + 32LL));
                v457 = (struct WNX *)UIGLOBALS::UIGLOBALSCONTAINER::m_selection;
                if ( !UIGLOBALS::UIGLOBALSCONTAINER::m_selection )
                {
                  SetWnxSel(*(struct WNX **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                           + 104LL));
                  v457 = (struct WNX *)UIGLOBALS::UIGLOBALSCONTAINER::m_selection;
                }
                v73 = 1;
                FActivateListWnx(v457, 1, 0);
              }
              *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1222;
              v1153 = 0;
              goto LABEL_910;
            }
            StgiFileClose(v266);
            if ( v1246 != (void *)-1LL )
            {
              CloseSentinelFile(v1246);
              v1246 = (void *)-1LL;
            }
            if ( v1180 )
            {
              HrRecordEvent(v1159, 0x40000000u, 0);
              v1180 = 0;
            }
            if ( (*(int (__fastcall **)(struct IMsoOLDocument *, _QWORD, __int64))(*(_QWORD *)v1159 + 232LL))(
                   v1159,
                   0,
                   1) < 0 )
            {
              Error(196658);
              XlsDiag::SendTraceTag(
                18088267,
                187,
                10,
                4,
                L"FFileLoad Failed to disable the RobustifiedUNC behavior on the Metro file.");
              v116 = -2146827284;
              XlsDiag::LogSetHrCoreTag(-2146827284, 0x179770Bu);
              v1039 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
              *(_DWORD *)(v1039 + 2024) = 0;
              *(_DWORD *)(v1039 + 2028) = 0;
              goto LABEL_1882;
            }
LABEL_743:
            v410 = v1163;
            goto LABEL_744;
          }
          if ( (unsigned __int16)PstgiFromErr((unsigned __int16)v266) )
            goto LABEL_645;
          v458 = FileSource::SzFilePath((FileSource *)v1307);
          OkAlert(196758, v458);
          XlsDiag::LogSetHrCoreTag(-2147319765, 0x179770Du);
LABEL_815:
          if ( v68 )
          {
            v460 = PivotOperationBase::PSxview((PivotOperationBase *)v68);
            *((_WORD *)v460 + 18) |= 8u;
          }
          goto LABEL_817;
        }
        v345 = 2098176;
        v346 = 2098176;
        if ( v337 )
        {
          v345 = 2098177;
          v346 = 2098177;
        }
        v347 = v345;
        if ( *(_QWORD *)&UIGLOBALS::UIGLOBALSCONTAINER::m_posi )
        {
          v348 = *(_QWORD *)(*(_QWORD *)&UIGLOBALS::UIGLOBALSCONTAINER::m_posi + 1568LL);
          if ( v348 )
          {
            if ( !*(_QWORD *)(v348 + 256) )
            {
              v346 = v345 | 0x20;
              v347 = v345 | 0x20;
            }
          }
        }
        if ( v1174 )
          v346 = v347 | 0x1000000;
        v349 = v1188;
        if ( v1188 )
          v346 |= 0x20000000u;
        if ( v1269 && FileSource::FCloud((FileSource *)v1307) )
        {
          MsoShipAssertTagProc(504422487);
          v350 = 504422486;
          v351 = -2147467260;
LABEL_567:
          XlsDiag::LogSetHrCoreTag(v351, v350);
          std::_Optional_destruct_base<DataLossProtection::NotifyRaiiHintsForPrePostEvents,0>::reset(v1338);
          goto LABEL_507;
        }
        if ( v1242 )
        {
          v352 = BKORWS::Psh((BKORWS *)&v1181);
          v353 = v1215;
          v354 = v352;
          v355 = (unsigned __int8)v1160;
          if ( v1160 )
            v355 = LoadRecovery::FRepairPkg((LoadRecovery *)v1160);
          v1217 = (struct STGI *)FileSource::HpstgiFileOpenEx(
                                   v1307,
                                   v346,
                                   0,
                                   &v1224,
                                   0,
                                   v355,
                                   0,
                                   0,
                                   0,
                                   v1574,
                                   &v1253,
                                   &v1569,
                                   0,
                                   0,
                                   &v1242,
                                   1,
                                   v1269,
                                   0,
                                   v353,
                                   v354);
          v266 = v1217;
          if ( (unsigned int)FErrPstgi(v1217) )
          {
            v356 = 36757983;
LABEL_579:
            v116 = -2146827284;
            v1154 = -2146827284;
            XlsDiag::LogSetHrCoreTag(-2146827284, v356);
          }
        }
        else
        {
          v357 = BKORWS::Psh((BKORWS *)&v1181);
          v358 = v1215;
          v359 = v357;
          v360 = v1160 && LoadRecovery::FRepairPkg((LoadRecovery *)v1160);
          LOBYTE(v1126) = v360;
          v1217 = (struct STGI *)XLFileIOMockable::PstgiFileOpen(
                                   v1307,
                                   v346,
                                   0,
                                   &v1224,
                                   (_DWORD)v1126,
                                   0,
                                   v1269,
                                   v358,
                                   v359);
          v266 = v1217;
          if ( (unsigned int)FErrPstgi(v1217) )
          {
            v356 = 36757984;
            goto LABEL_579;
          }
        }
        v361 = FErrPstgi(v266);
        v362 = v349;
        if ( !v361 )
          v362 = 1;
        v1188 = v362;
        if ( !(unsigned int)FErrPstgi(v266) && OSRR::IsAppAllowed((OSRR *)&v1237) )
        {
          if ( v1253 )
          {
            OSRR::SetAppAllowed((OSRR *)&v1237, 0);
            if ( (unsigned int)XLOSRR::FMustUseOsr((XLOSRR *)&v1237)
              || OSRR::FHasReasons((OSRR *)&v1237) && (unsigned int)NoYesAlert(589864, &v1569) == 7 )
            {
              StgiFileClose(v266);
              v350 = 24737540;
              v266 = 0;
              v1217 = 0;
LABEL_589:
              v351 = -2146827284;
              goto LABEL_567;
            }
          }
        }
        if ( !v1174 || !(unsigned int)FErrPstgi(v266) )
          goto LABEL_607;
        if ( (unsigned __int16)PstgiFromErr((unsigned __int16)v266) == 7 )
        {
          v364 = APPCORE::PlocaleinfoUSEN((APPCORE *)&vapp);
          if ( !(unsigned int)FMetroFileExt((const struct FileSource *)v1307, v364, 0, 0) )
            goto LABEL_607;
        }
        else
        {
          if ( MsoFDrmErrorCode(v1224) )
          {
            v363 = -2042494975;
LABEL_606:
            SetLoadForPreviewError(v363);
LABEL_607:
            if ( (unsigned int)FErrPstgi(v266) )
            {
              v365 = (unsigned __int16)PstgiFromErr((unsigned __int16)v266);
              v366 = v1224;
              if ( v365 == 8 || v1224 == -2147168507 )
              {
                if ( v1224 == -2147168507 )
                {
                  MsoShipAssertTagProc(505157471);
                  v366 = v1224;
                }
                v1179 = v366;
                v1167 = 1;
                if ( v1189 )
                {
                  FileSource::HrDeleteTemp((FileSource *)v1307);
                  v366 = v1179;
                }
                if ( v366 >= 0 )
                  v366 = -2147467260;
                XlsDiag::LogSetHrCoreTag(v366, 0x1797705u);
                v367 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1181);
                v368 = OpenTelemetry::POpenFileStageModel(v367);
                v369 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1393, 0x1F0CB5CDu);
                v370 = SXVWGEOM::RwFirst(v369);
                WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v368, (unsigned int)v366, v370);
                std::_Optional_destruct_base<DataLossProtection::NotifyRaiiHintsForPrePostEvents,0>::reset(v1338);
                MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1315);
                v68 = v1160;
                goto LABEL_815;
              }
            }
            v1176 = 1;
            goto LABEL_618;
          }
          if ( (unsigned __int16)PstgiFromErr((unsigned __int16)v266) != 4
            && v1224 != -2147286775
            && (unsigned int)(v1224 + 2147286780) > 1
            && v1224 != -2147286960
            && v1224 != -2147287010 )
          {
            if ( (unsigned __int16)PstgiFromErr((unsigned __int16)v266) == 8 )
            {
              v363 = -2147467260;
            }
            else
            {
              if ( (unsigned int)FOsrc() )
                goto LABEL_607;
              v363 = -2147467259;
            }
            goto LABEL_606;
          }
        }
        v363 = -2042494972;
        goto LABEL_606;
      }
      MaxPathStzPoke::MaxPathStzPoke((MaxPathStzPoke *)v1490, (struct MaxPathHolder *)v1315);
      v286 = MaxPathStzPoke::CchStzBufferSize((MaxPathStzPoke *)v1490);
      v287 = (wchar_t *)SlicerViewImpl::PSlicerView((SlicerViewImpl *)v1490);
      v1189 = FHandleConverterFile(
                (struct FileSource *)v1307,
                v287,
                v286,
                (enum FILETYPE *)&v1231,
                &v1344,
                (struct XLOSRR *)&v1237,
                v1162);
      v285 = (MaxPathStzPoke *)v1490;
    }
    MaxPathStzPoke::~MaxPathStzPoke(v285);
    goto LABEL_473;
  }
  v471 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
  if ( *(_QWORD *)(v471 + 40) )
    v1169 = *(struct STM **)(*(_QWORD *)(v471 + 40) + 56LL);
  else
    v1169 = 0;
  do
  {
LABEL_439:
    if ( !SbFromHpCore(v1169) )
    {
      if ( wProjLoad == 1 )
        wProjLoad = 5;
      if ( (unsigned int)FErrPstgi(v266) )
      {
        v68 = v1160;
        if ( !v1160 || v1233 )
        {
LABEL_987:
          v504 = v1163;
          goto LABEL_954;
        }
        v546 = PivotOperationBase::PSxview((PivotOperationBase *)v1160);
        *((_WORD *)v546 + 18) |= 8u;
LABEL_953:
        v504 = v1163;
        goto LABEL_954;
      }
LABEL_969:
      OSRR::SetAppAllowed((OSRR *)&v1237, 0);
      if ( (unsigned int)XLOSRR::FMustUseOsr((XLOSRR *)&v1237) )
      {
        StgiFileClose(v266);
        v116 = -2147024809;
        XlsDiag::LogSetHrCoreTag(-2147024809, 0x1797716u);
        v68 = v1160;
        v1155 = 0;
        errDeferred = 0;
        v582 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        *(_DWORD *)(v582 + 2024) = 0;
        *(_DWORD *)(v582 + 2028) = 0;
LABEL_821:
        LOBYTE(v266) = v1153;
        goto LABEL_518;
      }
      v116 = FileSource::HrGetFileTemp(v1307, 13);
      v1154 = v116;
      if ( v116 >= 0 )
      {
        v279 = v1162;
        if ( (unsigned int)FFinderFile(v1162) )
        {
          vfPretendNotStg = 1;
          StgiFileClose(v266);
          v581 = 1049729;
          if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                         + 104LL) != 2 )
            v581 = 1025;
          v1169 = FileSource::StreamOpen((FileSource *)v1307, v581, 0);
          vhpstm = v1169;
          goto LABEL_1078;
        }
      }
      else
      {
        XlsDiag::LogSetHrCoreTag(v116, 0x27413C0u);
      }
      if ( v1190
        && *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1232LL)
                     + 32LL) )
      {
        v541 = FExecWWWHelp(-1);
        v542 = 0;
        if ( v541 )
        {
          v68 = v1160;
LABEL_977:
          StgiFileClose(v266);
          goto LABEL_953;
        }
      }
      else
      {
        v542 = 0;
      }
      if ( v1569 < 0xFFu )
      {
        v543 = 58;
        v1570[v1569] = 58;
        v544 = 2LL * v1569 + 4;
        if ( v544 >= 0x202 )
          goto LABEL_2137;
        *(wchar_t *)((char *)&v1570[-1] + v544) = 0;
        OkAlert(196665, v1570);
        MakeStStzTruncOK(&v1569, 257);
      }
      v68 = v1160;
      if ( v1160 )
      {
        v545 = PivotOperationBase::PSxview((PivotOperationBase *)v1160);
        *((_WORD *)v545 + 18) |= 8u;
      }
      goto LABEL_977;
    }
    if ( hpFileSelInfo )
    {
      if ( *(int *)hpFileSelInfo >= 21 && !v1174 )
      {
        OSRR::SetAppAllowed((OSRR *)&v1237, 0);
        if ( (unsigned int)XLOSRR::FMustUseOsr((XLOSRR *)&v1237) )
        {
          if ( SbFromHpCore(v1169) )
            StreamClose(v1169);
          v1169 = 0;
          v1155 = 0;
          v116 = -2146827284;
          vhpstm = 0;
          errDeferred = 0;
          v576 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          *(_DWORD *)(v576 + 2024) = 0;
          *(_DWORD *)(v576 + 2028) = 0;
          XlsDiag::LogSetHrCoreTag(-2146827284, 0x1797710u);
LABEL_466:
          v68 = v1160;
          LOBYTE(v266) = v1153;
          goto LABEL_467;
        }
      }
    }
    if ( v1155
      || !SbFromHpCore(v1169)
      || *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                   + 104LL) == 2 )
    {
      if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                     + 104LL) == 2 )
      {
        ENV::ENV((ENV *)&v1559);
        v497 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        v1449 = *(_QWORD *)(v497 + 336);
        *(_QWORD *)(v497 + 336) = &v1559;
        v1560 = 36737604;
        v498 = setjmp(v1561);
        v499 = v1449;
        if ( v498
          || (v500 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1341), (int)HrDeferredSRO(&v1569, 0, v500, 0, 0) < 0) )
        {
          v1154 = -2147467259;
          v116 = -2147467259;
          XlsDiag::LogSetHrCoreTag(-2147467259, 0x279F29Fu);
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v499;
        }
        else
        {
          v116 = v1154;
        }
        v68 = v1235;
        v170 = v1216;
        v501 = *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer;
        v1160 = v1235;
        v1173 = v1216;
        *(_QWORD *)(*(_QWORD *)(v501 + 304) + 336LL) = v499;
        v502 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1304LL);
        *(_WORD *)(v502 + 56) &= ~8u;
        v1170 = v1186;
        v1162 = Src;
        v1163 = v1247;
        v1155 = 2;
      }
      else
      {
        v68 = v1160;
      }
      goto LABEL_901;
    }
    if ( (unsigned int)FErrPstgi(v266) || (v275 = STGI::Lpstg(v266), !(unsigned int)FMultiUsrStg(v275)) )
    {
      v276 = 0;
    }
    else
    {
      v276 = 1;
      if ( vgkr == -1 && MsoFShouldGatekeep((const struct _msoreg *)&vmsoridEnableExcelGKOnLoad) )
      {
        v1289 = 0;
        if ( (unsigned int)FBeginDiskIO(v1169) )
        {
          v1288 = 0;
          v277 = HrWPlatformSpecificFromStream2(&v1288);
          if ( v277 < 0 )
            goto LABEL_1910;
          if ( (v1288 & 0xF1FF) == 9 )
          {
            v278 = v1160;
            v1327 = 0;
            v277 = HrReadBof(v1288, 0, (struct LoadRecovery *)v1160, &v1327);
            if ( v277 < 0 )
              goto LABEL_1910;
            v277 = HrReadFileAccess(v1585, 8224, &v1569, 0, 0, 0, 0, (struct LoadRecovery *)v278, &v1264, &v1289);
            if ( v277 < 0 )
              goto LABEL_1910;
          }
          v277 = HrStreamSetPos2(0);
          if ( v277 < 0 )
            goto LABEL_1910;
          v277 = HrEndDiskIO2(0);
          if ( v277 < 0 )
            goto LABEL_1910;
        }
        if ( !v1289 )
        {
          StreamClose(v1169);
          StgiFileClose(v266);
          v1040 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          v1027 = 40981772;
          *(_DWORD *)(v1040 + 2024) = 0;
          *(_DWORD *)(v1040 + 2028) = 0;
          goto LABEL_1878;
        }
        v279 = v1162;
        LOBYTE(v1130) = 1;
        LODWORD(v1126) = 0;
        SafeToLoad::FGatekeep(v1162, v1307, 0, 0, v1126, &v1237, (_DWORD)v1130);
        goto LABEL_859;
      }
    }
    v279 = v1162;
LABEL_859:
    if ( v276
      && v1159
      && ((*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1159 + 224LL))(v1159) & 1) != 0 )
    {
      StreamClose(v1169);
      StgiFileClose(v266);
      if ( v1180 )
      {
        HrRecordEvent(v1159, 0x40000000u, 0);
        v1180 = 0;
      }
      if ( (*(int (__fastcall **)(struct IMsoOLDocument *, _QWORD, __int64))(*(_QWORD *)v1159 + 232LL))(v1159, 0, 1) < 0 )
      {
        Error(196658);
        XlsDiag::SendTraceTag(
          18088268,
          187,
          10,
          4,
          L"FFileLoad Failed to disable the RobustifiedUNC behavior on the file.");
        v1041 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        v1027 = 24737554;
        *(_DWORD *)(v1041 + 2024) = 0;
        *(_DWORD *)(v1041 + 2028) = 0;
        goto LABEL_1893;
      }
      goto LABEL_1072;
    }
    v472 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1304LL);
    *(_WORD *)(v472 + 56) &= ~8u;
    *(_WORD *)(v472 + 56) |= 8 * (_WORD)v276;
    v476 = 0;
    if ( !(unsigned int)FErrPstgi(v266) )
    {
      v473 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1541);
      v474 = OlDocFilePath::PClpDocument(v473);
      v475 = STGI::Lpstg(v266);
      if ( !(unsigned int)FDrmQueryRightsStg(v475, 4u, v474) )
        v476 = 1;
    }
    v1185 = v476;
    if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1836LL) )
    {
      if ( !(unsigned int)FErrPstgi(v266) )
      {
        v477 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1541);
        v478 = OlDocFilePath::PClpDocument(v477);
        v479 = STGI::Lpstg(v266);
        if ( !(unsigned int)FDrmQueryRightsStg(v479, 2u, v478) )
        {
          StreamClose(v1169);
          StgiFileClose(v266);
          HandleLockError(327752);
          v1027 = 24737555;
          v1042 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          v116 = -1662124019;
          *(_DWORD *)(v1042 + 2024) = 0;
          *(_DWORD *)(v1042 + 2028) = 0;
          goto LABEL_1894;
        }
      }
    }
    v68 = v1160;
    lp = *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL);
    if ( v1160 )
    {
      v480 = a10 & 0x400;
      v481 = PivotOperationBase::PSxview((PivotOperationBase *)v1160);
      *((_WORD *)v481 + 18) &= ~0x40u;
      *((_WORD *)v481 + 18) |= v480 != 0 ? 0x40 : 0;
    }
    if ( (a10 & 0x8000) != 0 )
      OSRR::SetHasInvalidPivot((OSRR *)&v1237, 1);
    v482 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1341);
    CchStToStz(v482, v1584, 2084);
    v483 = APPCORE::PmemheapMain((APPCORE *)&vapp);
    MaxPathHolder::MaxPathHolder((MaxPathHolder *)v1483, v483, 259, 0);
    v484 = FileSource::HrGetFileTemp(v1307, 10);
    v1154 = v484;
    v116 = v484;
    if ( v484 < 0 )
    {
      XlsDiag::LogSetHrCoreTag(v484, 0x27413A3u);
      StreamClose(v1169);
      StgiFileClose(v266);
      Error(327845);
      MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1483);
      goto LABEL_1861;
    }
    v485 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1181);
    v486 = (LXBASE *)OpenTelemetry::POpenFileStageModel(v485);
    v487 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1401, 0x1F0CB5C7u);
    SXVWGEOM::RwFirst(v487);
    WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v486);
    v488 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1483);
    v489 = HrLoadBiff(
             &v1169,
             &v1569,
             v1584,
             v488,
             v170,
             a5,
             a7,
             v266,
             0,
             &v1196,
             &v1225,
             (struct LoadRecovery *)v68,
             &lp,
             (struct XLOSRR *)&v1237,
             v1272,
             &v1264,
             v1275,
             &v1155);
    if ( v489 < 0 )
    {
      v1168 = v489;
      MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1483);
      goto LABEL_1133;
    }
    MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1341, v1584);
    if ( !v1155 && OSRR::FReadyForOsr((OSRR *)&v1237) )
    {
      XlsDiag::LogSetHrCoreTag(-2147024809, 0x205C2A1u);
      v1157 = 1;
      MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1483);
      v410 = v1163;
      goto LABEL_744;
    }
    if ( lp != *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL)
      && (unsigned int)FResidentBook(lp) )
    {
      v1305 = *(struct SH **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 32LL);
      v490 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1402, 0x2375A798u);
      v491 = SXVWGEOM::RwFirst(v490);
      v492 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 128LL);
      v493 = 0;
      if ( v492 )
      {
        v494 = v492;
        do
        {
          v493 = v494[1];
          if ( v493 )
            break;
          v492 = (_QWORD *)*v492;
          v494 = v492;
        }
        while ( v492 );
      }
      LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v493 + 96), lp, v491);
    }
    if ( v1155 && *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL) )
    {
      if ( !v1174 )
      {
        v495 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1483);
        if ( (unsigned int)HrCheckCollaboration(v279, v495) == -2147467260 )
        {
          errDeferred = 0;
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1222;
          LOBYTE(v266) = 0;
          if ( v68 )
          {
            v577 = PivotOperationBase::PSxview((PivotOperationBase *)v68);
            *((_WORD *)v577 + 18) |= 8u;
          }
          v116 = -2147467260;
          XlsDiag::LogSetHrCoreTag(-2147467260, 0x1797714u);
          v1155 = 0;
          MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1483);
          goto LABEL_1664;
        }
      }
      v496 = (struct WNX *)UIGLOBALS::UIGLOBALSCONTAINER::m_selection;
      v1176 = 1;
      if ( !UIGLOBALS::UIGLOBALSCONTAINER::m_selection )
      {
        SetWnxSel(*(struct WNX **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 104LL));
        v496 = (struct WNX *)UIGLOBALS::UIGLOBALSCONTAINER::m_selection;
      }
      FActivateListWnx(v496, 1, 0);
    }
    MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1483);
LABEL_901:
    if ( v1155 == 16 )
    {
      if ( v170 || (v503 = 1024, v1165) )
        v503 = 1025;
      v266 = FileSource::HpstgiFileOpen((FileSource *)v1307, &v1569, v503, 0, 0, 0, 0, 0, v1215);
      v1217 = v266;
      v1190 = 1;
      v1155 = 0;
      if ( !(unsigned int)FErrPstgi(v266) )
        goto LABEL_969;
      v1154 = -2146827284;
      v116 = -2146827284;
      XlsDiag::LogSetHrCoreTag(-2146827284, 0x230E203u);
    }
    else
    {
      v266 = v1217;
    }
    if ( v1196 == 32 && (unsigned int)OkCancelAlert(196937, 0) == 1 )
    {
      v1169 = FileSource::StreamOpen((FileSource *)v1307, 0x401u, 0);
      vhpstm = v1169;
      goto LABEL_1077;
    }
LABEL_910:
    if ( !v1156 )
      goto LABEL_987;
    if ( !(unsigned int)sub_1404867C0((unsigned int)v1196, (unsigned int)v1225) || v1155 == 2 )
    {
      v510 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
      if ( *(_QWORD *)(v510 + 40) && (v1155 == 1 || (*(_DWORD *)(*(_QWORD *)(v510 + 40) + 884LL) & 0x200) != 0) )
      {
        if ( (unsigned int)IMsoOLDocument::IsInFileSys(v1159) )
        {
          v511 = (wchar_t **)XLSBOOK::Plxtab(*(XLSBOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                     + 304LL)
                                                         + 40LL));
          FreeHpstTempPath((struct STB *)v511);
          if ( v1189 )
          {
            v512 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1484);
          }
          else if ( FileSource::FCloudStreaming((FileSource *)v1307) )
          {
            v513 = std::_Optional_construct_base<OlDocFilePath>::operator*(v1541);
            v512 = (const wchar_t *)OfficeExtension::ServerRuntime::RichApiMessageEntry::GetTarget(v513);
          }
          else
          {
            v512 = FileSource::StzFilePath((FileSource *)v1307);
          }
          if ( (int)HrStDupSt(v512, v511 + 21) < 0 )
            v511[21] = 0;
        }
        v514 = *(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL);
        v515 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1404, 0x236962A0u);
        v516 = SXVWGEOM::RwFirst(v515);
        BOOK::SetPioldoc(v514, v1159, v516);
        v517 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        if ( *(_QWORD *)(v517 + 40) != v1303
          && (*(_DWORD *)(*(_QWORD *)(v517 + 40) + 1440LL) & 0x8000000) != 0
          && (*(unsigned int (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1159 + 208LL))(v1159) == 2 )
        {
          v518 = v1215;
          XlAsyncFileIO::SpOLDocCoauthFromPOLDoc(v1340, v1159);
          if ( (unsigned __int8)std::shared_ptr<Mso::ActivityScope::IMsoLoggingScope>::operator bool(v1340)
            && (v519 = BKORWS::Psh((BKORWS *)v1340), XlAsyncFileIO::FIsDistributedBlobsFile(v519)) )
          {
            v1201 = 1;
            v520 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1405, 0x1E307684u);
            v521 = SXVWGEOM::RwFirst(v520);
            OldocHelper::SetReadOnly(v1159, v521);
            if ( v518 )
            {
              v522 = Mso::Telemetry::Activity::DataFields(v518);
              Mso::Telemetry::IDataFieldCollection::Add(v522, "SwitchToRO", "ZipItOldocSetReadOnly");
            }
          }
          else
          {
            HrRecordEvent(v1159, 0x40000000u, 0);
            v523 = (*(__int64 (__fastcall **)(struct IMsoOLDocument *, __int64, _QWORD, _QWORD))(*(_QWORD *)v1159 + 104LL))(
                     v1159,
                     4,
                     0,
                     *(int *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                        + 1232LL)
                            + 80LL));
            if ( v523 - 3473424 <= 1 )
              XlFileProtocolManager::TrackOpen(v1159);
            if ( v518 )
            {
              v524 = Mso::Telemetry::Activity::DataFields(v518);
              Mso::Telemetry::IDataFieldCollection::Add<int>(v524, "SwitchToRO", v523, 4);
            }
          }
          v525 = *(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL);
          v526 = (struct IMsoXmlDataStore *)*((_QWORD *)v525 + 604);
          v527 = BOOK::Pioldoc(v525);
          XlMsoMockable::MsoHrCreateMetadataProfile(v527, v526, 0);
          v528 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          *(_DWORD *)(*(_QWORD *)(v528 + 40) + 1440LL) &= ~0x8000000u;
          Mso::TCntPtr<Uxpp::UxppAnnotationsService>::~TCntPtr<Uxpp::UxppAnnotationsService>(v1340);
        }
        v529 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        if ( *(_QWORD *)(v529 + 40) != v1303 )
        {
          OutSpace = BOOK::GetOutSpace(*(BOOK **)(v529 + 40));
          if ( OutSpace )
          {
            v531 = *(void (__fastcall **)(struct OfficeSpace::IOutSpace *, _QWORD, struct IMsoOLDocument *))(*(_QWORD *)OutSpace + 312LL);
            v532 = BOOK::Pioldoc(*(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                          + 40LL));
            v531(OutSpace, 0, v532);
          }
        }
        if ( v1290 )
        {
          v533 = BOOK::Pioldoc(*(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                        + 40LL));
          ShowOdsRegexBusBar(v533);
        }
        if ( (unsigned int)FContainPowerView(*(const struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                               + 304LL)
                                                                   + 40LL))
          && !(unsigned int)Excel::Addins::FPowerViewAddinEnabled(0, v534) )
        {
          v535 = BOOK::Pioldoc(*(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                        + 40LL));
          ShowPowerBiBusBar(v535);
        }
      }
      goto LABEL_953;
    }
    if ( (unsigned int)FIsShareErr(errDeferred) && (_QWORD)xmmword_143FE0F70 )
      goto LABEL_987;
    HrRecordEvent(v1159, 0x40000000u, 0);
    v504 = v1163;
    v1180 = 0;
    if ( *v1163 )
      _IMsoOLDocument_SetIReDownload(*v1163, -1);
    v505 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1403, 0x236962A1u);
    v506 = SXVWGEOM::RwFirst(v505);
    v507 = OlDocFilePath::FReleaseIOLDoc(&v1159, 1, 1, v506);
    *v504 = 0;
    if ( v1155 && !v507 )
    {
      errDeferred = 0;
      v508 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
      *(_DWORD *)(v508 + 2024) = 0;
      *(_DWORD *)(v508 + 2028) = 0;
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1222;
      LOBYTE(v266) = 0;
      if ( v68 )
      {
        v509 = PivotOperationBase::PSxview((PivotOperationBase *)v68);
        *((_WORD *)v509 + 18) |= 8u;
      }
      v116 = -2146827284;
      XlsDiag::LogSetHrCoreTag(-2146827284, 0x1797715u);
      goto LABEL_467;
    }
LABEL_954:
    if ( v1156 && v1180 && v1155 != 2 && (!(unsigned int)FIsShareErr(errDeferred) || !(_QWORD)xmmword_143FE0F70) )
    {
      v536 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
      if ( !*(_QWORD *)(v536 + 40) || (*(_DWORD *)(*(_QWORD *)(v536 + 40) + 884LL) & 0x200) == 0 )
      {
        if ( (a10 & 0x100) != 0 )
        {
          v537 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1406, 0x21C730Fu);
          v538 = SXVWGEOM::RwFirst(v537);
          OldocHelper::SetAttrInAttrMask(v1159, 0, 0x100000u, v538);
        }
        if ( v1201 && v1155 )
        {
          v539 = Measurements::Stopwatch::Stopwatch((Measurements::Stopwatch *)v1539);
          LOBYTE(v540) = 1;
          Measurements::MeasureElapsedTime::MeasureElapsedTime(
            v1527,
            Measurements::MeasurementId::ExcelRecordEvent,
            v540,
            v539);
          v1328 = 3473425;
          (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, int *, _QWORD))(*(_QWORD *)v1159 + 112LL))(
            v1159,
            0x40000000,
            &v1328,
            0);
          Measurements::MeasureElapsedTime::~MeasureElapsedTime((Measurements::MeasureElapsedTime *)v1527);
        }
        else
        {
          v547 = BKORWS::Psh((BKORWS *)&v1181);
          if ( (unsigned int)XlFileProtocolManager::HrRecordEvent(v1159, 0x40000000u, v1155 != 0, v1202, v547) == -1662189464 )
          {
            v116 = -1662189464;
            XlsDiag::LogSetHrCoreTag(-1662189464, 0x1E26384Cu);
            v1180 = 0;
            goto LABEL_1882;
          }
        }
        v1180 = 0;
      }
    }
    if ( !(unsigned int)FIsShareErr(errDeferred) || !(_QWORD)xmmword_143FE0F70 )
      goto LABEL_1105;
    v548 = 304;
    if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                   + 104LL) == 2 )
    {
      v591 = v1212;
      if ( v1212 == 1 )
      {
        LOBYTE(v548) = v1185;
        v591 = sub_141224980(v1159, v548, &v1197);
        v1212 = v591;
        if ( v1197 )
          OSRR::SetAppAllowed((OSRR *)&v1237, 0);
      }
      else
      {
        sub_1413EEE50();
      }
      if ( v591 < 0 )
      {
        if ( SbFromHpCore(v1169) )
          StreamClose(v1169);
        if ( !(unsigned int)FErrPstgi(v266) )
          StgiFileClose(v266);
        v1217 = 0;
        v1169 = 0;
        v116 = v591;
        XlsDiag::LogSetHrCoreTag(v591, 0x1797717u);
        v1155 = 0;
LABEL_1093:
        errDeferred = 0;
        v589 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v1167 = 1;
        v590 = *(_QWORD *)(*(_QWORD *)v589 + 304LL);
        *(_DWORD *)(v590 + 2024) = 0;
        *(_DWORD *)(v590 + 2028) = 0;
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1222;
        LOBYTE(v266) = 0;
        if ( v68 )
        {
LABEL_830:
          v467 = PivotOperationBase::PSxview((PivotOperationBase *)v68);
          *((_WORD *)v467 + 18) |= 8u;
        }
LABEL_518:
        v279 = v1162;
LABEL_1664:
        if ( v1544 )
        {
          v919 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1464);
          CchStToSt(v919, v279, v1226);
        }
        XslClear((struct XSL *)&v1543);
        if ( v1172 && v1271 )
          FreeRevert(v1271);
        if ( !OSRR::IsAppAllowed((OSRR *)&v1237) && (unsigned int)XLOSRR::FMustUseOsr((XLOSRR *)&v1237) )
        {
          OkAlert(589889, 0);
          v116 = -2147467260;
          v1219 = -2147467260;
          v1155 = 0;
          XlsDiag::LogSetHrCoreTag(-2147467260, 0x179771Bu);
        }
        v410 = v1163;
        vpoldocument = v1351;
        if ( v1156 && *v1163 && v1241 != -2 )
        {
          if ( v1155
            || (v920 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL), *(_QWORD *)(v920 + 40))
            && (*(_DWORD *)(*(_QWORD *)(v920 + 40) + 884LL) & 0x200) != 0 )
          {
            if ( v1180 )
            {
              v927 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
              if ( *(_QWORD *)(v927 + 40) && (*(_DWORD *)(*(_QWORD *)(v927 + 40) + 884LL) & 0x200) != 0 )
                XlFileProtocolManager::MarkOpenDone(v1159, 1, 0);
              HrRecordEvent(v1159, 0x40000000u, 1);
            }
            (*(void (__fastcall **)(struct IMsoOLDocument *, _QWORD, __int64))(*(_QWORD *)*v410 + 56LL))(*v410, 0, 7);
          }
          else
          {
            if ( v1180 )
            {
              v921 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1541);
              OlDocFilePath::RecordEventForCloseOldoc(v921, v1159, 0);
            }
            _IMsoOLDocument_SetIReDownload(*v410, -1);
            if ( (*(unsigned int (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1159 + 208LL))(v1159) )
              MsoShipAssertTagProc(946484024);
            if ( lp )
            {
              v922 = *v410;
              if ( BOOK::Pioldoc(lp) == v922 && !(unsigned int)FOsrhInTransition() )
              {
                v923 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1432, 0x2369629Bu);
                v924 = SXVWGEOM::RwFirst(v923);
                BOOK::SetPioldoc(lp, 0, v924);
              }
            }
            v925 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1433, 0x2369629Au);
            v926 = SXVWGEOM::RwFirst(v925);
            OlDocFilePath::FReleaseIOLDoc(v410, 0, 1, v926);
            *v410 = 0;
          }
        }
        v928 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1304LL);
        *(_WORD *)(v928 + 56) &= ~8u;
        if ( !v1157 && !*(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 2436LL) )
        {
          if ( v1155 && lp && !(unsigned int)XLSWORKBOOK::FAddin((struct BOOK *)((char *)lp + 1640)) )
          {
            v929 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
            HrRegisterDynamicUdfs(v929, &v1195);
          }
          v930 = Mso::Telemetry::Activity::DataFields(v1215);
          LOBYTE(v931) = v1195;
          Mso::Telemetry::IDataFieldCollection::Add<bool>(v930, "FUdfNeedsRecalc", v931, 4);
        }
        if ( v1155 == 1 && lp && (v1196 != 256 || v1225 == 4) && (v1196 & 0xE80) == 0 )
        {
          VbaLoadRefBegin();
          if ( (sksEvt & 4) == 0 || (v932 = 1, v1320) )
            v932 = 0;
          HrBookLoadComplete(lp, v932, (struct LoadRecovery *)v68, 1, &v1209);
          if ( (unsigned int)FBookHasProject(lp, 1) )
          {
            v933 = HprojectFromPbook(lp);
            HrVbpSetDirty(v933, 0);
          }
          VbaLoadRefEnd();
          if ( !v1197 )
          {
            if ( v1159 )
            {
              v934 = BOOK::Pioldoc(lp);
              if ( v1159 == v934 )
              {
                v935 = XLSWORKBOOK::Pcm((struct BOOK *)((char *)lp + 1640));
                if ( CardView::DataElementRecord::FExpanded(v935) )
                  sub_1412CEFD0(lp);
              }
            }
          }
        }
        if ( lp )
          XLSWORKBOOK::PostDocumentLoad((char *)lp + 1640, 0, 0);
        if ( v1195 && !v1209 )
        {
          v936 = LOCATIONCONTEXTDATA::PWorkbookCur((LOCATIONCONTEXTDATA *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                     + 304LL)
                                                                         + 8LL));
          v937 = (OcsTransitionController *)PivotMetadataCache::PvMemProps(v936);
          v938 = OcsTransitionController::PCoauthTransitionState(v937);
          Api::RecalcService::HrRecalcAll(v938, 0);
        }
        if ( !v1155 || !lp || v1197 || !BOOK::Pioldoc(lp) || (v939 = BOOK::Pioldoc(lp), v940 = 1, v1159 != v939) )
          v940 = 0;
        if ( v940 )
          XlFileProtocolManager::MarkOpenDone(v1159, 1, 0);
        v941 = v1276;
        if ( !BKORWS::Psh(v1276) || !v940 )
          goto LABEL_1755;
        v942 = XLSWORKBOOK::Pcm((struct BOOK *)((char *)lp + 1640));
        if ( !CardView::DataElementRecord::FExpanded(v942) )
          goto LABEL_1750;
        v1205 = 0;
        v1206 = 0;
        if ( v68 && BOOK::FRepairedBookCloudFile(lp) )
        {
          v943 = BKORWS::Psh(v941);
          v944 = LoadRecovery::StmfOfRepair(v68);
          QuickLoadContext::SetWorkbookRepairStmf(v943, v944);
        }
        v945 = BKORWS::Psh(v941);
        v946 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
        v947 = v945;
        v948 = v1298;
        v949 = XlAsyncFileIO::HrHandlePostLoadTasks(v946, v1298, v947, &v1223, &v1205, &v1206);
        if ( v949 == -2147023673 )
        {
          v1321 = 0;
          Title = Mso::Swagger::Schema::GetTitle(v948);
          LOBYTE(v1050) = std::nullopt;
          v1051 = Title;
          if ( !(unsigned __int8)std::operator==<XlsActivity>(Title, v1050) )
          {
            v1052 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1362, 0x28572D2u);
            v1053 = SXVWGEOM::RwFirst(v1052);
            v1054 = (Mso::Telemetry *)std::_Optional_construct_base<XlsActivity>::operator*(v1051);
            Mso::Telemetry::SetActivityResultHr(v1054, (struct Mso::Telemetry::Activity *)v949, v1053, v1055);
          }
          v1056 = HrDoCloseBookCore(&v1321, 0, 0, 0, 1, 0, 0);
          if ( v1056 < 0 )
            XlsDiag::LogSetHrCoreTag(v1056, 0x280659Bu);
          lp = 0;
          sub_1402DA650(&v1543, v1335, v1057);
          fCeCanceled = 1;
          v116 = v949;
          XlsDiag::LogSetHrCoreTag(v949, 0x280659Cu);
          v1155 = 0;
          goto LABEL_1935;
        }
        if ( !v1205 )
        {
          BOOK::StartCoauth(lp, 1);
LABEL_1750:
          v956 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
          v957 = FeatureGateCollectionBase<GuidedReapplyFeatureGates>::Instance(v956);
          if ( (unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(v957 + 40) )
          {
            v958 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
            v1332 = 0;
            v959 = v958;
            Api::ReloadContext::RetrieveRctxFromWorkbook(v958, &v1332);
            if ( v1332 && Api::ReloadContext::FHasData(v1332) )
              Api::ReloadContext::RestoreCoauthPanesPostReload(v1332, v959);
            XlAsyncFileIO::ClearReloadContext(v959);
          }
LABEL_1755:
          if ( (unsigned __int8)CircularReferenceTailValue::FGetFlagsShadowBag(&vapp) && v68 )
          {
            LoadRecovery::StmfOfRepair(v68);
            FormatCh_ProcIds((void *const *)&vapp);
          }
          v961 = v1298;
          v962 = lp;
          if ( v1298 && lp && v1161 )
          {
            ZrtUtility::RenderWindowsPostContentNotification(lp, UIGLOBALS::UIGLOBALSCONTAINER::m_pwnChoEdit, v960);
            v963 = v1179;
            v964 = BOOK::Pioldoc(lp);
            ZrtUtility::LogZrtOpenInformation(v964, v961, (struct XlSyncStateChangeListenerLoad *)v963, v965);
            v962 = lp;
          }
          if ( v1155 == 1 )
          {
            if ( v962 )
            {
              if ( !(unsigned int)FOsrhBook(v962) )
              {
                v1207 = 0;
                v966 = CastOrNull<XLSWORKBOOK,BOOK>(lp);
                CoauthUtil::RunDuplicateUidCheck(v966, 2, &v1207);
                if ( v1207 )
                {
                  v967 = v1276;
                  if ( BKORWS::Psh(v1276) )
                  {
                    v968 = BKORWS::Psh(v967);
                    QuickLoadContext::SetCoauthStateChanged(v968, 1);
                  }
                }
              }
            }
          }
          v969 = L"and force template load";
          v970 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          v562 = *(_DWORD *)(v970 + 1836) == 0;
          v971 = *(const struct BOOK **)(v970 + 40);
          if ( v562 )
            v969 = &WindowName;
          Only = FPioldocReadOnly(v971);
          if ( lp )
            v973 = (*((_DWORD *)lp + 360) >> 1) & 0xF;
          else
            v973 = 0;
          LODWORD(v1130) = Only;
          LODWORD(v1128) = v973;
          XlsDiag::SendTraceTag(
            7091154,
            187,
            50,
            4,
            L"Loading workbook with Auto refresh load status: %d and read only mode: %d %s",
            v1128,
            v1130,
            v969);
          v974 = v1155;
          if ( v1155 && fShowWn )
          {
            v975 = lp;
            if ( lp && (*((_BYTE *)lp + 1440) & 0x10) == 0
              || (v976 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL),
                  *(_QWORD *)(v976 + 40))
              && (*(_DWORD *)(*(_QWORD *)(v976 + 40) + 884LL) & 0x200) != 0 )
            {
              v977 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
              if ( !*(_DWORD *)(v977 + 1836) )
              {
                if ( !lp )
                  v975 = *(struct BOOK **)(v977 + 40);
                v978 = v1175;
                v979 = BOOK::Pioldoc(v975);
                MsoSetReadWriteOnSaveIoldoc(v979, v978);
                LODWORD(v1129) = v1232;
                XlsDiag::SendTraceTag(
                  7091155,
                  187,
                  50,
                  4,
                  L"Check for XML Load Options value: %d prior to displaying business bar",
                  v1129);
                if ( ((v1232 - 1) & 0xFFFFFFFD) != 0 )
                {
                  v980 = 0;
                  if ( (int)sub_14046F720(v975) < 0 )
                  {
                    v981 = FPioldocReadOnly(v975);
                    v980 = (unsigned __int8)FIsTrue<int>(v981) != 0;
                  }
                  v982 = BOOK::Pioldoc(v975);
                  v1175 = MsoFReadWriteOnSaveIoldoc(v982) != 0;
                  if ( !BOOK::FFailedLockTransition(v975)
                    && !AsyncFileLockHandler::FPendingLockTransitionToState(v975, 0)
                    || (*((_DWORD *)v975 + 221) & 0x200) != 0 )
                  {
                    AssistedReading::ResetAssistedReading(v975, 8u, 0);
                  }
                  if ( v980 && Api::Workbook::FHasReadOnlyRecommended((struct BOOK *)((char *)v975 + 1640)) )
                  {
                    v1175 = 0;
                    v983 = BOOK::Pioldoc(v975);
                    MsoSetReadWriteOnSaveIoldoc(v983, 0);
                  }
                }
                FileLoad::ShowVersionFileBusBar(v1162, v975);
                if ( XLSWORKBOOK::Prdsharedmanager((struct BOOK *)((char *)v975 + 1640)) )
                {
                  v984 = XLSWORKBOOK::Prdsharedmanager((struct BOOK *)((char *)v975 + 1640));
                  LinkedEntityFeature = Api::RichDataSharedManager::GetLinkedEntityFeature(v984);
                  if ( Api::LinkedEntityFeature::FShouldShowFinanceBusinessBar(LinkedEntityFeature) )
                  {
                    if ( (unsigned int)FOsrc() )
                    {
                      OsrcSetFEverHadFinanceLinkedEntity(v975);
                    }
                    else
                    {
                      v986 = (RichDataManagerHost *)CastOrNull<XLSWORKBOOK,BOOK>(v975);
                      RichDataManagerHost::FShowFinanceBusinessBar(v986, v987);
                    }
                  }
                }
                v988 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)v975 + 1640));
                CleanupWorkbookStylesBusinessBar::ShowCleanupWorkbookStyleskBusinessBarIfNeeded(v988, v989);
                v974 = v1155;
                goto LABEL_1798;
              }
            }
          }
          else
          {
LABEL_1798:
            v975 = lp;
          }
          v990 = v1310;
          FileLoad::CheckAttemptRepair(
            v975,
            (struct LoadRecovery *)v68,
            v974,
            v1174,
            v1157,
            v1233,
            v1282,
            a10,
            v1310,
            &v1179,
            &v1283,
            &v1266,
            &v1220);
          if ( !v1283 )
          {
            if ( v1266 )
            {
LABEL_1994:
              v1073 = (CorruptionMetaData *)std::_Optional_construct_base<CorruptionMetaData>::operator*(v1540);
              CorruptionMetaData::MarkAsCorrupt(v1073);
              if ( !v68 )
                goto LABEL_2001;
              if ( (unsigned int)OfficeSharedApiImpl::UserFeedbackScreenshotInfo::GetScreenshotSourceType(v68) == -2147418113 )
              {
                v1075 = 459015;
                goto LABEL_2003;
              }
              v1074 = (Mso::History *)(unsigned int)v1179;
              if ( v1179 == -2134188030 || v1179 == -2134142954 )
              {
                v1322 = 256;
                MetroFGetErrorWz(v1179, v1577, &v1322);
                ErrorAlert(459023, v1577);
              }
              else
              {
LABEL_2001:
                if ( !Mso::History::IsVersionCrawlForRepairEnabled(v1074)
                  || (int)FileLoad::HrCheckVersionHistoryRepair(v1162) < 0 )
                {
                  v1075 = 458893;
LABEL_2003:
                  Error(v1075);
                }
              }
LABEL_2038:
              if ( v1155 )
              {
LABEL_2039:
                if ( (a10 & 0x20) != 0 && (unsigned int)FHpshtiFromStt(&v1454, 50) )
                  *((_QWORD *)v1454 + 3) = lp;
              }
              if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                         + 872LL)
                             + 8LL)
                  & 1) == 0
                && v1155
                && lp )
              {
                v1085 = Measurements::Stopwatch::Stopwatch((Measurements::Stopwatch *)v1536);
                LOBYTE(v1086) = 1;
                Measurements::MeasureElapsedTime::MeasureElapsedTime(
                  v1529,
                  Measurements::MeasurementId::ExcelPQEventing,
                  v1086,
                  v1085);
                v1087 = (struct Api::Workbook *)CastOrNull<XLSWORKBOOK,BOOK>(lp);
                XLSEVENTDISPATCHER::HrOnWorkbookOpen(v1087);
                v1208 = 0;
                if ( PowerQueryManager::FPowerQueryIEVersionCheckFailed() )
                {
                  Manager = Api::Workbook::PPowerQueryManager((struct BOOK *)((char *)lp + 1640));
                  if ( (*(int (__fastcall **)(struct IPowerQueryWorkbookManager *, char *))(*(_QWORD *)Manager + 224LL))(
                         Manager,
                         &v1208) >= 0 )
                  {
                    if ( v1208 )
                    {
                      v1089 = BOOK::Pioldoc(*(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                 + 304LL)
                                                     + 40LL));
                      ShowPowerQueryIEBusBar(v1089);
                    }
                  }
                }
                Measurements::MeasureElapsedTime::~MeasureElapsedTime((Measurements::MeasureElapsedTime *)v1529);
                v1090 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL);
                if ( *(_DWORD *)(v1090 + 104) == 1 )
                {
                  *((_DWORD *)lp + 644) |= 0x20u;
                }
                else if ( *(_DWORD *)(v1090 + 104) == 2 )
                {
                  *((_DWORD *)lp + 644) |= 0x10u;
                }
                if ( *((_QWORD *)lp + 162) || *((_QWORD *)lp + 163) )
                {
                  if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                             + 872LL)
                                 + 104LL) == 2 )
                    *((_DWORD *)lp + 223) |= 0x800u;
                  if ( *((_QWORD *)lp + 162) )
                  {
                    v1091 = IdwaFromIds(458968);
                    MsoDoWatsonAlertBegin(v1091, 0, 0, (struct WADD *)v1549);
                  }
                  v1092 = v1187 & 4;
                  if ( (a10 & 0x20) != 0 || (v1093 = FOsrhInTransition(), v1094 = 0, v1093) )
                    v1094 = 1;
                  v1095 = XlUIMockable::HrShowRecoveryErrors2(lp, v1094, v1092, 0);
                  v606 = v1095;
                  if ( (_BYTE)v266 )
                  {
                    if ( v1095 < 0 )
                    {
LABEL_1742:
                      v1168 = v606;
                      goto LABEL_1133;
                    }
                  }
                  else if ( v1095 < 0 )
                  {
                    v802 = 512506015;
                    v803 = (MsoReserveTag *)&v1364;
                    goto LABEL_1925;
                  }
                  if ( *((char *)lp + 892) >= 0 )
                  {
                    std::optional<EditCommandTrackingFreezer>::optional<EditCommandTrackingFreezer>(v1243);
                    v1096 = FeatureGateCollectionBase<CoauthFeatureGates>::Instance();
                    if ( (unsigned __int8)Mso::AB::Optimized::FeatureGate::operator bool(v1096 + 408) )
                      std::optional<EditCommandTrackingFreezer>::emplace<>(v1243);
                    v1097 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1365, 0x231C69Fu);
                    v1098 = SXVWGEOM::RwFirst(v1097);
                    BookDirty(lp, 1, v1098);
                    std::optional<EditCommandTrackingFreezer>::~optional<EditCommandTrackingFreezer>(v1243);
                  }
                  if ( *((_QWORD *)lp + 162) )
                    MsoDoWatsonAlertEnd((struct WADD *)v1549, *((const wchar_t **)lp + 163));
                }
                v1099 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                v1100 = *(_QWORD *)(v1099 + 872);
                if ( *(_DWORD *)(v1100 + 104) != 1 && (*(_BYTE *)(v1100 + 8) & 1) == 0 )
                {
                  v1101 = *(_QWORD *)(v1099 + 1328);
                  if ( *(_DWORD *)(v1101 + 20) )
                  {
                    Sz = 0;
                    if ( wverLastXLSaved < 3 || *(char *)(v1101 + 20) < 0 )
                      Sz = CchLoadSz(v1573, 327873, 256);
                    v1103 = CchLoadSz(&v1573[Sz], 327874, 256 - Sz);
                    v1104 = (__int64 *)NtCurrentTeb()->ThreadLocalStoragePointer;
                    v1105 = v1103 + Sz;
                    v542 = *v1104;
                    v1106 = *(_QWORD *)(*(_QWORD *)(*v1104 + 304) + 1328LL);
                    if ( (*(_DWORD *)(v1106 + 20) & 0x10) == 0 && *(char *)(v1106 + 20) >= 0 )
                      goto LABEL_2080;
                    v1107 = -1161035032;
                    *(_DWORD *)(v1106 + 20) &= (*(_DWORD *)(v1106 + 20) & 0x10) != 0 ? -17 : -129;
                    while ( 1 )
                    {
                      v1105 += CchLoadSz(&v1573[v1105], v1107, 256 - v1105);
LABEL_2080:
                      v1108 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                        + 1328LL);
                      v1109 = *(_DWORD *)(v1108 + 20);
                      if ( (v1109 & 0x20) != 0 )
                      {
                        v1107 = -1161035031;
                        v1110 = v1109 & 0xFFFFFFDF;
                      }
                      else
                      {
                        if ( (v1109 & 0x40) == 0 )
                        {
                          v543 = 512;
                          if ( (unsigned __int64)(2LL * v1105) < 0x200 )
                          {
                            v1573[v1105] = 0;
                            ShowAlert(10, 458968, v1573, 0, 0, 0);
                            goto LABEL_1954;
                          }
LABEL_2137:
                          _report_rangecheckfailure(v543, v542);
                        }
                        v1107 = -1161035030;
                        v1110 = v1109 & 0xFFFFFFBF;
                      }
                      *(_DWORD *)(v1108 + 20) = v1110;
                    }
                  }
                }
              }
              goto LABEL_1954;
            }
            if ( v68 )
            {
              if ( (int)LoadRecovery::Lrmode(v68) > 0
                && (*((_BYTE *)PivotOperationBase::PSxview((PivotOperationBase *)v68) + 36) & 8) == 0
                && !v1155 )
              {
                v1076 = v1179;
                if ( v1179 == -2147023673 || v1179 == -2147467260 || *(&vscd + 1) )
                {
                  if ( *(&vscd + 1) )
                  {
                    v116 = -2147467260;
                    v1077 = 33931969;
                    v1076 = -2147467260;
                    goto LABEL_2015;
                  }
                  v116 = v1179;
                  if ( v1179 < 0 )
                  {
                    v1077 = 33931970;
LABEL_2015:
                    XlsDiag::LogSetHrCoreTag(v1076, v1077);
                  }
                  v1078 = 0;
                  v1079 = 458924;
LABEL_2028:
                  OkAlert(v1079, v1078);
                  goto LABEL_2038;
                }
              }
              if ( *((char *)PivotOperationBase::PSxview((PivotOperationBase *)v68) + 36) < 0 )
              {
                if ( v1155 )
                {
                  AffectedProcessSessionId = (ODFROBUSTLOAD *)OfficeSharedApiImpl::UserFeedbackV2Config::GetAffectedProcessSessionId(v68);
                  if ( ODFROBUSTLOAD::FRepairAlertDisplayed(AffectedProcessSessionId) )
                  {
                    CchLoadSz(v1579, -1161035131, 255);
                    v1081 = v1579;
                    v1082 = 467262;
                    goto LABEL_2037;
                  }
                  if ( v1155 )
                    goto LABEL_2039;
                }
                v1083 = (ODFROBUSTLOAD *)OfficeSharedApiImpl::UserFeedbackV2Config::GetAffectedProcessSessionId(v68);
                if ( ODFROBUSTLOAD::FPasswordHashFound(v1083) )
                {
                  v116 = -2147467260;
                  XlsDiag::LogSetHrCoreTag(-2147467260, 0x205C2C3u);
                  v1079 = 459071;
                }
                else
                {
                  if ( v1155 )
                    goto LABEL_2039;
                  v1084 = (ODFROBUSTLOAD *)OfficeSharedApiImpl::UserFeedbackV2Config::GetAffectedProcessSessionId(v68);
                  if ( !ODFROBUSTLOAD::FBadNullDate(v1084) )
                    goto LABEL_2038;
                  v116 = -2147467260;
                  XlsDiag::LogSetHrCoreTag(-2147467260, 0x205C2C4u);
                  v1079 = 459072;
                }
                v1078 = v1570;
                goto LABEL_2028;
              }
            }
            if ( !v1189
              || !(unsigned int)Mso::Details::ConstexprFunctorBase<Mso::IFunctor<bool,FeaturePropertyValue const &,FeaturePropertyValue const &>>::Release(&vapp)
              || (unsigned int)FOsrhInTransition()
              || (unsigned int)FOsrc() )
            {
              goto LABEL_2038;
            }
            CchSzToSt(*((const wchar_t **)v1344 + 3), v1576, 255);
            SuppressStExt(v1576, 255);
            if ( v1155 )
            {
              CchInsert2St(v1575, 459073, &v1569, v1576, 255);
              v1082 = 467265;
            }
            else
            {
              v116 = -2146827284;
              XlsDiag::LogSetHrCoreTag(-2146827284, 0x205C2C5u);
              CchInsert2St(v1575, 459075, &v1569, v1576, 255);
              v1082 = 467267;
            }
            v1081 = v1575;
LABEL_2037:
            OkInfoAlert(v1082, v1081);
            goto LABEL_2038;
          }
          if ( v1266 )
            goto LABEL_1994;
          if ( v1174 && !(unsigned int)FOsrcHostedByExcel() )
          {
            SetLoadForPreviewError(-2042494972);
            v1220 = 0;
            v1164 = 0;
            goto LABEL_1826;
          }
          if ( !v1220 )
          {
            v991 = FOsrhInTransition();
            v1164 = FIsTrue<int>(v991);
            if ( v1164 || (unsigned __int8)CircularReferenceTailValue::FGetFlagsShadowBag(&vapp) || (v992 = 0, v1161) )
              v992 = 1;
            v1164 = v992;
            if ( !v992 )
            {
              if ( v1242 && !MsoFDrmUIEnabled() )
              {
                Error(589882);
                goto LABEL_1826;
              }
              if ( (unsigned int)FOsrc() )
              {
                Osrc = GetOsrc();
                v994 = OSRC::DwPromptUser(Osrc, 0, 0, 0, 0, 0);
                v1164 = v994 != 0;
                if ( !v994 )
                  SetLoadForPreviewError(-2147467260);
                goto LABEL_1826;
              }
              if ( v1275 && VersionHistoryWindowParams::FSkipCorruptVersionOpens(v1275) )
              {
                v995 = 504443348;
LABEL_1822:
                v116 = -2146827284;
                XlsDiag::LogSetHrCoreTag(-2146827284, v995);
                v990 = v1310;
                goto LABEL_1826;
              }
              if ( (unsigned int)Art::IOMHost::GetEnvId((Art::IOMHost *)&vapp) )
              {
                if ( (unsigned int)YesNoAlert(458912, v1570) != 6 )
                {
                  v116 = -2146827284;
                  XlsDiag::LogSetHrCoreTag(-2146827284, 0x230E208u);
                  goto LABEL_1826;
                }
              }
              else if ( (unsigned int)XlUIMockable::NoYesAlert(458912, v1570) != 6 )
              {
                v995 = 36758023;
                goto LABEL_1822;
              }
              v1164 = 1;
            }
          }
LABEL_1826:
          v996 = (CorruptionMetaData *)std::_Optional_construct_base<CorruptionMetaData>::operator*(v1540);
          CorruptionMetaData::MarkAsCorrupt(v996);
          if ( !v1220 && !v1164 )
            goto LABEL_2038;
          if ( v1233 || (*((_BYTE *)PivotOperationBase::PSxview((PivotOperationBase *)v68) + 36) & 2) != 0 )
          {
            BookCorrupt = LoadRecovery::GrbitGetBookCorrupt((LoadRecovery *)v68);
            v1004 = PivotMetadataCache::PvMemProps((PivotMetadataCache *)v68);
            LoadRecovery::HrHandleLoadMode((LoadRecovery *)v68, v1004 == (void *)BookCorrupt);
            LoadRecovery::HrHandleLoadMode((LoadRecovery *)v68, v1233);
            v1005 = LoadRecovery::GrbitGetBookCorrupt((LoadRecovery *)v68);
            LoadRecovery::GrbitSetBookCorruptOld((LoadRecovery *)v68, v1005);
          }
          else
          {
            if ( !v68 || (v44 = (int)LoadRecovery::Lrmode(v68) <= 0, v997 = 1, v44) )
              v997 = 0;
            v998 = (LoadRecovery *)v68;
            if ( v997 )
            {
              LoadRecovery::IncrementRepairAttemptCount((LoadRecovery *)v68);
              if ( LoadRecovery::CGetPartCount((LoadRecovery *)v68) < v990 )
              {
                v999 = 1;
                v998 = (LoadRecovery *)v68;
                goto LABEL_1844;
              }
              if ( v990 )
              {
                if ( LoadRecovery::CGetPartCount((LoadRecovery *)v68) == v990 )
                {
                  v1000 = LoadRecovery::CGetIRTCount((LoadRecovery *)v68);
                  if ( v1000 <= v1343 )
                  {
                    v1001 = v990 - 1;
                    v1002 = LoadRecovery::FNoProgressOnPart((LoadRecovery *)v68, v1001);
                    v998 = (LoadRecovery *)v68;
                    if ( v1002 )
                    {
                      v999 = 1;
                      goto LABEL_1844;
                    }
                    if ( !LoadRecovery::FCorruptPart((LoadRecovery *)v68, v1001) )
                    {
                      LoadRecovery::SetCorruptPart((LoadRecovery *)v68, v1001);
                      LoadRecovery::SetFNoProgressOnPart((LoadRecovery *)v68, v1001);
                    }
                  }
                }
              }
            }
            else
            {
              v999 = 0;
LABEL_1844:
              LoadRecovery::HrHandleLoadMode(v998, v999);
            }
            v1343 = LoadRecovery::CGetIRTCount((LoadRecovery *)v68);
            v1310 = LoadRecovery::CGetPartCount((LoadRecovery *)v68);
          }
          ClearStatusString(11);
          if ( (unsigned int)LoadRecovery::Lrmode(v68) == 1 )
          {
            if ( !v1220 )
            {
              v1006 = 1752853862;
              goto LABEL_1851;
            }
          }
          else
          {
            v1006 = 1752853863;
LABEL_1851:
            MsoShipAssertTagProc(v1006);
            v1220 = 1;
          }
          if ( v1161 )
            goto LABEL_744;
          v1007 = LoadRecovery::Lrmode(v68);
          SetLoadRecovery(v1007);
          v1008 = MaxPathHolder::CchMaxPath();
          v1009 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1464);
          v1010 = v1008;
          v69 = v1162;
          CchStToSt(v1009, v1162, v1010);
          v1271 = 0;
          sub_1402DA650(&v1543, v1335, v1011);
          goto LABEL_745;
        }
        OsfOpenScope::OpenCompleted((OsfOpenScope *)v1487);
        v1188 = 0;
        (*(void (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1159 + 8LL))(v1159);
        v950 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
        v951 = XlAsyncFileIO::PxlasyncFileIOFromWorkbook(v950);
        if ( v951 )
          XlAsyncFileIO::NotifyWorkbookInClose(v951, 1);
        v952 = FeatureGateCollectionBase<CoauthFeatureGates>::Instance();
        if ( (unsigned __int8)Mso::AB::Optimized::FeatureGate::operator bool(v952 + 472) )
          BOOK::SetFCloseForReopen(lp, 1);
        v953 = HrFreeBook2(lp);
        v606 = v953;
        if ( (_BYTE)v266 )
        {
          if ( v953 < 0 )
            goto LABEL_1742;
        }
        else if ( v953 < 0 )
        {
          v802 = 512506016;
          v803 = (MsoReserveTag *)&v1361;
          goto LABEL_1925;
        }
        lp = 0;
        if ( v1206 )
          (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v1159 + 56LL))(v1159, 1, 7);
        v954 = v1173 != 0;
        v1173 = -v1173;
        FBeginCmdIOLDoc(v1159, v954 ? 4 : 2, 0, &v1234, 0);
        if ( v1248 )
        {
          (*(void (__fastcall **)(struct IMsoPKMClient *))(*(_QWORD *)v1248 + 184LL))(v1248);
          v1248 = 0;
        }
        sub_1402DA650(&v1543, v1335, v955);
        XlsActivity::ResetStoredTagData(v1215);
LABEL_744:
        v69 = v1162;
LABEL_745:
        if ( v1161 && (v1157 || v1164) )
        {
          if ( v1159 )
          {
            if ( v1180 )
              HrRecordEvent(v1159, 0x40000000u, 0);
            if ( *v410 )
            {
              v1058 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1363, 0x23696299u);
              v1059 = SXVWGEOM::RwFirst(v1058);
              OlDocFilePath::FReleaseIOLDoc(v410, 1, 1, v1059);
            }
          }
          Mso::TCntPtr<IOfficeSolutionFramework>::TCntPtr<IOfficeSolutionFramework>(v1312);
          v1060 = MaxPathHolder::SzPath((MaxPathHolder *)v1464);
          v1061 = MsoPIOLDocFindWithWzPersistentName(v1060);
          Mso::TCntPtr<IMsoOLDocument>::Attach(v1312, v1061);
          if ( (unsigned __int8)std::shared_ptr<Mso::ActivityScope::IMsoLoggingScope>::operator bool(v1312) )
          {
            v1063 = BKORWS::Psh((BKORWS *)v1312);
            ZrtUtility::OptOutOfServerOnlyAsyncOpen(v1063, v1064);
          }
          if ( v1157 )
            XslClear((struct XSL *)&v1543);
          LOBYTE(v1062) = std::nullopt;
          if ( !(unsigned __int8)sub_14240D428(v1526, v1062) )
          {
            v1065 = sub_14240D5FC(v1526);
            sub_141836A58(v1065);
          }
          v116 = -1491861503;
          v1155 = -1491861503;
          XlsDiag::LogSetHrCoreTag(-1491861503, 0x300B394u);
          Mso::TCntPtr<Uxpp::UxppAnnotationsService>::~TCntPtr<Uxpp::UxppAnnotationsService>(v1312);
LABEL_1954:
          if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                         + 8LL)
              & 1) == 0 )
          {
            FRemoveLoadAction((struct LoadRecovery *)v68, 0);
            if ( v68 )
            {
              if ( (*((_BYTE *)PivotOperationBase::PSxview((PivotOperationBase *)v68) + 36) & 0x20) != 0 )
              {
                v116 = -2146827284;
                XlsDiag::LogSetHrCoreTag(-2146827284, 0x23404CEu);
                v1066 = (CorruptionMetaData *)std::_Optional_construct_base<CorruptionMetaData>::operator*(v1540);
                CorruptionMetaData::MarkAsCorrupt(v1066);
                Error(327845);
              }
              LoadRecovery::Destroy((LoadRecovery *)v68);
              FreeHpst(v68);
              v68 = 0;
              v1235 = 0;
            }
          }
          if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                         + 8LL)
              & 1) == 0
            && v1155
            && lp
            && !(unsigned int)FBookAddin(lp)
            && (*((_DWORD *)lp + 222) & 0x804000) == 0
            && (a10 & 0x20) == 0
            && (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 864LL)
                          + 24LL)
              & 0x40000) == 0
            && !v1174 )
          {
            XLDRPPERS::XLDRPPERS((XLDRPPERS *)v1565);
            memset_0(v1565, 0, 0x308u);
            v1067 = Api::Workbook::FtFileType((char *)lp + 1640);
            v1068 = 1;
            LOBYTE(v1133) = 0;
            LOBYTE(v1131) = 1;
            v1565[0] = (2 * v1067) | v1565[0] & 0xFFFFFE01;
            if ( v1157 )
              v1068 = 65537;
            LODWORD(v1126) = 1;
            if ( (unsigned int)FSaveRecoveryDrp(lp, 0, 0, v1068, v1126, v1565, 0, v1131, v1133) )
              *((_DWORD *)lp + 320) = 1;
          }
          if ( lp )
            *((_DWORD *)lp + 222) &= ~0x800000u;
          if ( v1176
            && (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                         + 8LL)
              & 1) == 0
            && v1155
            && lp
            && (v1196 == 5 || v1196 == 16)
            && !v1174 )
          {
            FileLoad::CheckShared(lp);
          }
          v1069 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          if ( (*(_BYTE *)(*(_QWORD *)(v1069 + 872) + 8LL) & 1) == 0 && v1155 && lp && !v1174 )
          {
            if ( !*(_DWORD *)(*(_QWORD *)(v1069 + 1232) + 80LL) && !(unsigned int)FOsrhBook(lp) )
              v73 = 0;
            v1070 = BOOK::Pioldoc(lp);
            MsoHrSimpleOfflineOpenFile(
              v1070,
              (int (__high *)(enum MSOSCA, struct IMsoOLDocument *, unsigned int))&HrSimpleOfflineUser,
              v73);
          }
          ResetLoadRecovery();
          v1071 = lp;
          if ( lp )
          {
            FShowTrustBar(lp);
            *((_DWORD *)lp + 222) &= ~0x8000000u;
            v1071 = lp;
          }
          v1072 = HrFileCompleteLoadEx(
                    v1162,
                    hObject,
                    v1155,
                    v1184,
                    v1071,
                    v1178,
                    v1167,
                    (struct LoadRecovery *)v68,
                    v1302,
                    v1222,
                    v1197 != 0,
                    v1248,
                    v1253,
                    v1161,
                    v1159,
                    v1272,
                    v1304,
                    v1183,
                    v116,
                    (const struct MaxPathHolder *)v1342,
                    v1177,
                    v1256,
                    (struct OsfOpenScope *)v1487,
                    (const struct XLOSRR *)&v1237,
                    v1336);
          goto LABEL_1992;
        }
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1222;
        FRemoveLoadAction((struct LoadRecovery *)v68, 0);
        XlsActivity::SetSuccessful(v1215);
        std::_Optional_destruct_base<CorruptionMetaData,0>::~_Optional_destruct_base<CorruptionMetaData,0>(v1540);
        v1452[0] = APPCORE::PmemheapMain((APPCORE *)&vapp);
        std::optional<CorruptionMetaData>::emplace<IMemHeap *>(v1540, v1452);
        v1452[1] = BKORWS::Psh(v1276);
        std::optional<OlDocFilePath>::emplace<QuickLoadContext *>((OlDocFilePath *)v1541);
        ++v1273;
        v411 = (__int64 *)NtCurrentTeb()->ThreadLocalStoragePointer;
        v60 = v1300;
        v1155 = 0;
        v1196 = 256;
        v1225 = 0;
        lp = 0;
        v1234 = 0;
        v412 = *v411;
        v1171 = 0;
        v1299 = 0;
        v1270 = 0;
        v413 = *(_QWORD *)(v412 + 304);
        v1277 = 0;
        v1333 = 0;
        v1190 = 0;
        v414 = *(_QWORD *)(v413 + 1304);
        v1165 = 0;
        v1166 = 0;
        *(_WORD *)(v414 + 56) &= ~8u;
        if ( v1253 )
        {
          (*(void (__fastcall **)(struct IMsoDocumentEncryptor *))(*(_QWORD *)v1253 + 16LL))(v1253);
          v1253 = 0;
        }
        goto LABEL_79;
      }
LABEL_1105:
      errDeferred = 0;
      v592 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
      if ( *(_QWORD *)(v592 + 40) && (*(_DWORD *)(*(_QWORD *)(v592 + 40) + 884LL) & 0x200) != 0 )
      {
        RenumberWind(*(struct SH **)(v592 + 32));
        v593 = v1299;
        v594 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        *(_DWORD *)(v594 + 2024) = 0;
        *(_DWORD *)(v594 + 2028) = 0;
        v595 = *(const struct BOOK **)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        *((_QWORD *)v595 + 42) = v1222;
        LOBYTE(v266) = 0;
        goto LABEL_1549;
      }
      if ( v1155 != 2 )
      {
LABEL_1360:
        v722 = v1156;
        v410 = v1163;
        goto LABEL_1361;
      }
      if ( *(_DWORD *)(*(_QWORD *)(v592 + 872) + 104LL) == 2 )
      {
        if ( OSRR::FOsrCandidate((OSRR *)&v1237) )
        {
          OSRR::SetAppReady((OSRR *)&v1237, 1);
LABEL_764:
          v1157 = 1;
          goto LABEL_743;
        }
        v596 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1341);
        v597 = HrLoadDataRecover(v1169, v266, &v1569, 257, v596, a5, 0, v1187, (struct LoadRecovery *)v68);
        v1154 = v597;
        v116 = v597;
        if ( v597 < 0 )
          XlsDiag::LogSetHrCoreTag(v597, 0x2156755u);
        v598 = v1156;
        v1155 = v116 >= 0;
        if ( v1156 )
        {
          if ( (unsigned int)IMsoOLDocument::IsInFileSys(v1159) )
          {
            if ( v1155
              || (v599 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL),
                  *(_QWORD *)(v599 + 40))
              && (*(_DWORD *)(*(_QWORD *)(v599 + 40) + 884LL) & 0x200) != 0 )
            {
              v600 = (wchar_t **)XLSBOOK::Plxtab(*(XLSBOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                         + 304LL)
                                                             + 40LL));
              FreeHpstTempPath((struct STB *)v600);
              v601 = FileSource::StzFilePath((FileSource *)v1307);
              if ( (int)HrStDupSt(v601, v600 + 21) < 0 )
                v600[21] = 0;
            }
          }
        }
        v1217 = 0;
LABEL_1272:
        if ( v1155 )
          v1196 = 5;
        if ( v1544 )
        {
          if ( v1159 )
          {
            (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v1159 + 56LL))(
              v1159,
              0xFFFFFFFFLL,
              7);
            if ( v1180 )
              HrRecordEvent(v1159, 0x40000000u, 0);
            v669 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1413, 0x2369629Eu);
            v670 = SXVWGEOM::RwFirst(v669);
            OlDocFilePath::FReleaseIOLDoc(v1163, 1, v1155 == 0, v670);
          }
          v671 = v1301;
          v1180 = v1191;
          v1159 = v1301;
        }
        else
        {
          v671 = v1159;
        }
        if ( v1241 == -2 )
        {
          v68 = v1160;
          goto LABEL_1360;
        }
        v704 = 0;
        v705 = 0;
        v706 = 0;
        v707 = 0;
        if ( v1180 )
        {
          v704 = 0;
          if ( !v1155 )
          {
            v708 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
            if ( !*(_QWORD *)(v708 + 40) || (*(_DWORD *)(*(_QWORD *)(v708 + 40) + 884LL) & 0x200) == 0 )
              v704 = 1;
          }
          HrRecordEvent(v671, 0x40000000u, !v704);
          v705 = v704;
          v1180 = 0;
          v707 = v704;
          v706 = v704;
        }
        v709 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        if ( *(_QWORD *)(v709 + 40) != v1303 )
        {
          v704 = v705;
          v706 = v707;
          if ( v1155 )
          {
            if ( *(_QWORD *)(v709 + 40) )
            {
              if ( v1262 )
              {
                v710 = OLDocFactory::PInstance();
                v1219 = (*(__int64 (__fastcall **)(const struct OLDocFactory *, _QWORD, struct IMsoOLDocument **))(*(_QWORD *)v710 + 56LL))(
                          v710,
                          0,
                          &v1348);
                v1219 = (*(__int64 (__fastcall **)(struct IMsoOLDocument *, __int64, _QWORD))(*(_QWORD *)v1159 + 96LL))(
                          v1159,
                          8,
                          0);
                v1219 = (*(__int64 (__fastcall **)(struct IMsoOLDocument *, __int64, _QWORD, _QWORD))(*(_QWORD *)v1159 + 112LL))(
                          v1159,
                          0x40000000,
                          0,
                          0);
                v1219 = (*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1159 + 16LL))(v1159);
                *v1163 = v1348;
                v1159 = v1348;
              }
              v711 = *(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL);
              v712 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1414, 0x2369629Cu);
              v713 = SXVWGEOM::RwFirst(v712);
              BOOK::SetPioldoc(v711, v1159, v713);
              LOBYTE(v714) = 1;
              if ( (unsigned __int8)FeatureExposure::FRunLicensedFeature(v714) )
              {
                v715 = NtCurrentTeb()->ThreadLocalStoragePointer;
                v1306 = -1;
                v716 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v715 + 304LL) + 32LL);
                v717 = 0;
                if ( (*(_BYTE *)(v716 + 10) & 4) == 0 )
                  v717 = *(_BYTE *)(v716 + 8);
                v718 = FtDefault(v717, v716);
                if ( (unsigned __int8)FShouldShowDataLossBusBar(v718, &v1306) )
                  ShowDataLossBusBarIfNeeded(
                    *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL),
                    v1306);
              }
            }
            v68 = v1160;
            goto LABEL_1360;
          }
        }
        v410 = v1163;
        _IMsoOLDocument_SetIReDownload(*v1163, -1);
        v719 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1415, 0x2369629Du);
        v720 = SXVWGEOM::RwFirst(v719);
        if ( v1155 )
        {
          v721 = 0;
          v704 = v706;
        }
        else
        {
          v721 = 1;
        }
        OlDocFilePath::FReleaseIOLDoc(v410, !v704, v721, v720);
        if ( v598 )
          *v410 = 0;
        v68 = v1160;
        v722 = 0;
        v1156 = 0;
LABEL_1361:
        v723 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1181);
        v724 = (LXBASE *)OpenTelemetry::POpenFileStageModel(v723);
        v725 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1416, 0x1F0CB5C2u);
        SXVWGEOM::RwFirst(v725);
        WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v724);
        v726 = FeatureGateCollectionBase<CoauthFeatureGates>::Instance();
        if ( !(unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(v726 + 1680) || v1155 )
          lp = *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL);
        v727 = NtCurrentTeb()->ThreadLocalStoragePointer;
        vhpstErrPath = 0;
        v728 = *(_QWORD *)(*(_QWORD *)v727 + 304LL);
        *(_DWORD *)(v728 + 2024) = 0;
        *(_DWORD *)(v728 + 2028) = 0;
        v1204 = 0;
        v729 = sub_140430470(lp);
        v730 = v1153;
        v606 = v729;
        if ( v1153 )
        {
          if ( v729 < 0 )
          {
LABEL_1132:
            v1168 = v606;
            goto LABEL_1133;
          }
        }
        else if ( v729 < 0 )
        {
          v802 = 512506050;
          v803 = (MsoReserveTag *)&v1367;
          goto LABEL_1925;
        }
        if ( v1204 )
        {
          lp = 0;
          v73 = 1;
          goto LABEL_744;
        }
        if ( v722 )
        {
          sub_14046D5A0(v1159);
          if ( Mso::DocumentWindow::EventMgr::IsDocumentWindowEventManagerEnabled(v731) )
            sub_140431960(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL));
        }
        if ( v1155 )
        {
          if ( lp )
          {
            v732 = (WN *)*((_QWORD *)lp + 53);
            if ( v732 )
            {
              v733 = WN::Puiframe(v732);
              v734 = (struct IMsoOLDocument *)UIFRAME::HwndFrame(v733);
              v735 = BOOK::Pioldoc(lp);
              Excel::XlMso::EmitOpenEventForOLDocument(v735, v734, v736);
            }
          }
          if ( v1155 )
          {
            if ( lp )
            {
              if ( !v1197 )
              {
                if ( BOOK::Pioldoc(lp) )
                {
                  v737 = BOOK::Pioldoc(lp);
                  if ( v1159 == v737 && !(unsigned int)FIsLocalVersionXL(v1162) )
                  {
                    v738 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
                    v739 = Api::Workbook::FtFileType((char *)lp + 1640);
                    if ( (unsigned __int8)CoauthUtil::FValidXluidLoadedFt(v739, v738) )
                      XLSWORKBOOK::SetFValidUidStateLoaded((struct BOOK *)((char *)lp + 1640), 1);
                    if ( !XLSWORKBOOK::FValidUidStateLoaded((struct BOOK *)((char *)lp + 1640)) )
                    {
                      v740 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
                      CoauthUtil::CreateValidUidStateOnLoad(v740);
                    }
                    if ( v1170 )
                    {
                      Protocol = XlFileProtocolManager::GetProtocol(v1159);
                      if ( !Protocol )
                      {
                        MsoShipAssertTagProc(506056966);
                        v1045 = 506056965;
                        v606 = -2147418113;
                        goto LABEL_2135;
                      }
                      v742 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1417, 0x1E1968DCu);
                      XlFileProtocol::TakeZipItScheduler(Protocol, v1349, *(unsigned int *)v742);
                      v743 = lp;
                      v744 = *(_DWORD *)MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1418, 0x1E1968DBu);
                      v745 = BKORWS::Psh((BKORWS *)v1349);
                      XLSWORKBOOK::SetZipItScheduler((char *)v743 + 1640, v745, v744);
                      Mso::TCntPtr<IWebAddInOptionalProperties>::~TCntPtr<IWebAddInOptionalProperties>(v1349);
                    }
                    v746 = FeatureGateCollectionBase<CoauthFeatureGates>::Instance();
                    if ( (unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(v746 + 1264) )
                    {
                      LOBYTE(v747) = std::nullopt;
                      if ( !(unsigned __int8)std::operator==<CoauthoringInternals::RecoveredFileCoauthorableState>(
                                               &CoauthoringInternals::s_optRecoveredFileCoauthorableState,
                                               v747) )
                      {
                        v748 = (_DWORD *)std::optional<CoauthoringInternals::RecoveredFileCoauthorableState>::operator->(&CoauthoringInternals::s_optRecoveredFileCoauthorableState);
                        *((_DWORD *)lp + 320) = *v748;
                        v749 = std::optional<CoauthoringInternals::RecoveredFileCoauthorableState>::operator->(&CoauthoringInternals::s_optRecoveredFileCoauthorableState);
                        *((_QWORD *)lp + 161) = *(_QWORD *)(v749 + 8);
                      }
                    }
                    BOOKO::UpdateCoauth((struct BOOK *)((char *)lp + 1640), 1);
                    v750 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
                    v751 = XlAsyncFileIO::PxlasyncFileIOFromWorkbook(v750);
                    if ( v751 )
                    {
                      v752 = XlAsyncFileIO::Pxlrh(v751);
                      XlRenameHandler::HrCheckForRenameOnFileLoad(v752);
                    }
                    v753 = 0;
                    if ( (unsigned __int8)std::shared_ptr<Mso::ActivityScope::IMsoLoggingScope>::operator bool(&v1254) )
                    {
                      v754 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1254);
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v754 + 48LL))(v754);
                      v755 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1254);
                      v753 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v755 + 128LL))(v755, 0);
                    }
                    v756 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
                    v757 = IMerge::PMergeFromWorkbook(v756);
                    if ( v757 )
                    {
                      v758 = (*(__int64 (__fastcall **)(struct IMerge *))(*(_QWORD *)v757 + 216LL))(v757);
                      v759 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v758 + 288LL))(v758);
                      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v759 + 48LL))(v759, v753);
                    }
                    v1330 = 0;
                    v760 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
                    Api::ReloadContext::RetrieveRctxFromWorkbook(v760, &v1330);
                    if ( v1330 && Api::ReloadContext::FValid(v1330) )
                    {
                      v1183 = 1;
                      v761 = Mso::Telemetry::Activity::DataFields(v1215);
                      refreshed = Api::ReloadContext::RefreshType(v1330);
                      v763 = Api::ReloadContext::SzFromBookRefreshType(refreshed);
                      Mso::Telemetry::IDataFieldCollection::Add(v761, "RefreshType", v763, 4);
                    }
                    if ( BKORWS::Psh((struct BOOK *)((char *)lp + 3088)) )
                    {
                      v764 = BKORWS::Psh((struct BOOK *)((char *)lp + 3088));
                      IEndpointAgent::HrLoadComplete(v764);
                    }
                    v765 = XLSWORKBOOK::ClpManager((struct BOOK *)((char *)lp + 1640));
                    ClassifyLabelProtectManager::OnLoadComplete(v765);
                    if ( IdleLoop::FEnabled(v766) )
                    {
                      v767 = FeatureGateCollectionBase<PerformanceFeatureGates>::Instance();
                      if ( (unsigned __int8)Mso::AB::Optimized::FeatureGate::operator bool(v767 + 416) )
                        UpdateCLPLabelIndicator(lp);
                    }
                    v768 = APPCORE::PautoSaveManager((APPCORE *)&vapp);
                    AutoSaveManager::SetAutoSaveStatusOnFileLoad(v768, lp);
                    Copilot::EvaluatePrerequisitesForBook((struct BOOK *)((char *)lp + 1640), v769);
                  }
                }
              }
            }
          }
        }
        if ( v1172 )
          ApplyRevert(v1271, (const struct REVARG *)v1567, v1155);
        v1271 = 0;
        v770 = HrEnsureChartSheetsAreNonBlank(lp, 1);
        v606 = v770;
        if ( v1153 )
        {
          if ( v770 < 0 )
          {
            v1168 = v770;
            goto LABEL_1133;
          }
        }
        else if ( v770 < 0 )
        {
          v802 = 512506049;
          v803 = (MsoReserveTag *)&v1366;
          goto LABEL_1925;
        }
        if ( fShowWn )
        {
          v593 = *(SH **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 32LL);
          v1299 = v593;
          v771 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1419, 0x2375A797u);
          v772 = SXVWGEOM::RwFirst(v771);
          v773 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          if ( *(_QWORD *)(v773 + 104) )
            v774 = *(struct SH **)(*(_QWORD *)(v773 + 104) + 24LL);
          else
            v774 = 0;
          v775 = *(_QWORD **)(v773 + 128);
          v776 = 0;
          if ( v775 )
          {
            v777 = v775;
            do
            {
              v776 = v777[1];
              if ( v776 )
                break;
              v775 = (_QWORD *)*v775;
              v777 = v775;
            }
            while ( v775 );
          }
          LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v776 + 96), v774, v772);
        }
        else
        {
          v593 = v1299;
        }
        v778 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        v779 = *(struct WNX **)(v778 + 344);
        if ( v779 )
        {
          v780 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v781 = *(struct WNX **)(v778 + 344);
          v782 = v779;
          v783 = v779;
          do
          {
            v784 = *((_DWORD *)v781 + 2);
            if ( v784 == 2 )
            {
              if ( (*(_WORD *)(CastOrNull<CS,SH>(*((_QWORD *)v782 + 3), v783) + 424) & 0x200) != 0 )
              {
                v785 = *(struct SH **)(*(_QWORD *)(*(_QWORD *)v780 + 304LL) + 32LL);
                v786 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1420, 0x237630D7u);
                v787 = SXVWGEOM::RwFirst(v786);
                v788 = *(_QWORD *)(*(_QWORD *)v780 + 304LL);
                v789 = 0;
                v790 = *(_QWORD **)(v788 + 128);
                if ( v790 )
                {
                  v791 = *(_QWORD **)(v788 + 128);
                  do
                  {
                    v789 = v791[1];
                    if ( v789 )
                      break;
                    v790 = (_QWORD *)*v790;
                    v791 = v790;
                  }
                  while ( v790 );
                }
                LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v789 + 96), *((struct SH **)v782 + 3), v787);
                if ( SbFromHpCore(*(const void **)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v780 + 304LL) + 48LL) + 13280LL)) )
                {
                  v606 = HrRecalcCho(0);
                  if ( v1153 )
                  {
                    if ( v606 < 0 )
                      goto LABEL_1185;
                  }
                  else if ( v606 < 0 )
                  {
                    v802 = 512506048;
                    v803 = (MsoReserveTag *)&v1357;
                    goto LABEL_1925;
                  }
                }
                v793 = *(_QWORD *)(*(_QWORD *)v780 + 304LL);
                if ( *(_QWORD *)(v793 + 40) )
                {
                  v794 = *(_QWORD *)(v793 + 40);
                  v792 = 2048;
                  if ( (*(_WORD *)(v794 + 482) & 0x800) != 0 )
                  {
                    if ( *(_QWORD *)(v794 + 528) )
                      *(_WORD *)(*(_QWORD *)(v794 + 528) + 8LL) |= 0x200u;
                  }
                }
                v795 = (struct CS *)CastOrNull<CS,SH>(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v780 + 304LL) + 32LL), v792);
                CheckDdeCh(v795, 1);
                v796 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1421, 0x237630D6u);
                v797 = SXVWGEOM::RwFirst(v796);
                v798 = *(_QWORD *)(*(_QWORD *)v780 + 304LL);
                v799 = 0;
                v800 = *(_QWORD **)(v798 + 128);
                if ( v800 )
                {
                  v801 = *(_QWORD **)(v798 + 128);
                  do
                  {
                    v799 = v801[1];
                    if ( v799 )
                      break;
                    v800 = (_QWORD *)*v800;
                    v801 = v800;
                  }
                  while ( v800 );
                }
                LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v799 + 96), v785, v797);
                v730 = v1153;
              }
            }
            else if ( !v784 )
            {
              if ( (*((_BYTE *)v783 + 216) & 0x10) != 0 )
              {
                v606 = HrDoDeferredLayoutView(v779);
                if ( v730 )
                {
                  if ( v606 < 0 )
                    goto LABEL_1185;
                }
                else if ( v606 < 0 )
                {
                  v802 = 509215971;
                  v803 = (MsoReserveTag *)&v1358;
LABEL_1925:
                  v1043 = MsoReserveTag::MsoReserveTag(v803, v802);
                  v1044 = SXVWGEOM::RwFirst(v1043);
                  XlsDiag::LogFailRetTag(v606, v1044);
                  goto LABEL_2136;
                }
              }
              else if ( (*((_DWORD *)v779 + 54) & 0x100) != 0 )
              {
                v804 = Measurements::Stopwatch::Stopwatch((Measurements::Stopwatch *)v1538);
                LOBYTE(v805) = 1;
                Measurements::MeasureElapsedTime::MeasureElapsedTime(
                  v1517,
                  Measurements::MeasurementId::ExcelDoDeferredPageLayoutView,
                  v805,
                  v804);
                v1337 = 0;
                v806 = HrXlDoDeferredPageLayoutView(v779, 1, &v1337);
                v606 = v806;
                if ( v730 )
                {
                  if ( v806 < 0 )
                  {
                    v1168 = v806;
                    Measurements::MeasureElapsedTime::~MeasureElapsedTime((Measurements::MeasureElapsedTime *)v1517);
                    goto LABEL_1133;
                  }
                }
                else if ( v806 < 0 )
                {
                  v1046 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1359, 0x1E8C38A3u);
                  v1047 = SXVWGEOM::RwFirst(v1046);
                  XlsDiag::LogFailRetTag(v606, v1047);
                  Measurements::MeasureElapsedTime::~MeasureElapsedTime((Measurements::MeasureElapsedTime *)v1517);
                  goto LABEL_2136;
                }
                Measurements::MeasureElapsedTime::~MeasureElapsedTime((Measurements::MeasureElapsedTime *)v1517);
              }
            }
            v779 = *(struct WNX **)v779;
            v781 = v779;
            v782 = v779;
            v783 = v779;
          }
          while ( v779 );
        }
        if ( !wProjLoad )
        {
          if ( fShowWn )
          {
            v807 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
            if ( !*(_DWORD *)(v807 + 2704) && !*(_DWORD *)(v807 + 1888) )
            {
              v808 = Measurements::Stopwatch::Stopwatch((Measurements::Stopwatch *)v1537);
              LOBYTE(v809) = 1;
              Measurements::MeasureElapsedTime::MeasureElapsedTime(
                v1528,
                Measurements::MeasurementId::ExcelNewFmla,
                v809,
                v808);
              NewFmla(0);
              Measurements::MeasureElapsedTime::~MeasureElapsedTime((Measurements::MeasureElapsedTime *)v1528);
            }
          }
        }
        v810 = lp;
        if ( v1155 )
        {
          if ( lp && !v1174 && !v1157 )
          {
            if ( !v1248 )
            {
              if ( BOOK::Pioldoc(lp) )
              {
                v811 = BOOK::Pioldoc(lp);
                if ( !(unsigned int)IMsoOLDocument::IsInFileSys(v811)
                  || (v812 = BOOK::Pioldoc(lp),
                      ((*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v812 + 224LL))(v812) & 1) != 0) )
                {
                  v813 = BOOK::Pioldoc(lp);
                  v814 = 1;
                  v815 = (*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v813 + 80LL))(v813) & 0x20000;
                  if ( !*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                              + 1232LL)
                                  + 32LL) )
                    v814 = 3;
                  v816 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1422, 0x21C7310u);
                  v817 = SXVWGEOM::RwFirst(v816);
                  v818 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                               + 1232LL)
                                   + 32LL) != 0
                       ? 0x20000
                       : 0;
                  v819 = BOOK::Pioldoc(lp);
                  OldocHelper::SetAttrInAttrMask(v819, v818, 0x20000u, v817);
                  v820 = BOOK::Pioldoc(lp);
                  (*(void (__fastcall **)(struct IMsoOLDocument *, _QWORD, struct IMsoPKMClient **))(*(_QWORD *)v820 + 216LL))(
                    v820,
                    v814,
                    &v1248);
                  v821 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1423, 0x21C7311u);
                  v822 = SXVWGEOM::RwFirst(v821);
                  v823 = BOOK::Pioldoc(lp);
                  OldocHelper::SetAttrInAttrMask(v823, v815, 0x20000u, v822);
                }
              }
              v810 = lp;
            }
            v824 = BOOK::Pioldoc(v810);
            MsoHrMetadataEvent(v824, 32);
            v825 = BOOK::Pioldoc(lp);
            MsoHrTaxonomyOnDocOpen(v825);
            v810 = lp;
          }
          if ( v1155 )
          {
            if ( v810 && !v1174 )
            {
              v826 = BOOK::Pioldoc(v810);
              FileLoad::HrHandleSharepointWorkflows(v826);
              v810 = lp;
            }
            if ( v1155 )
            {
              BuildBookWnxSel();
              v810 = lp;
              if ( v1155 )
              {
                if ( v1248 && lp )
                {
                  *((_QWORD *)lp + 172) = v1248;
                  (*(void (__fastcall **)(struct IMsoPKMClient *))(*(_QWORD *)v1248 + 104LL))(v1248);
                  v810 = lp;
                }
                if ( v1155 && v810 && !*((_QWORD *)v810 + 57) )
                {
                  if ( BOOK::Pioldoc(v810) )
                  {
                    v827 = BOOK::Pioldoc(lp);
                    if ( ((*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v827 + 224LL))(v827) & 1) != 0 )
                    {
                      v828 = BOOK::Pioldoc(lp);
                      if ( ((*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v828 + 80LL))(v828) & 0x40) == 0 )
                      {
                        v829 = MaxPathHolder::SzPath((MaxPathHolder *)v1350);
                        if ( !(unsigned int)FFileInOfflineFilesCache(v829) )
                        {
                          v1295 = 0;
                          v830 = BOOK::Pioldoc(lp);
                          if ( (*(int (__fastcall **)(struct IMsoOLDocument *, struct IStorage **, GUID *))(*(_QWORD *)v830 + 32LL))(
                                 v830,
                                 &v1295,
                                 &IID_IStorage) >= 0 )
                          {
                            v1318 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                              + 2924LL);
                            v1317 = rupBuild;
                            v831 = NtCurrentTeb()->ThreadLocalStoragePointer;
                            v1279 = 0;
                            v1451 = *(struct SH **)(*(_QWORD *)(*(_QWORD *)v831 + 304LL) + 32LL);
                            ENV::ENV((ENV *)&v1562);
                            v832 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                            v1450 = *(_QWORD *)(v832 + 336);
                            *(_QWORD *)(v832 + 336) = &v1562;
                            v1563 = 36737605;
                            v833 = setjmp(v1564);
                            v68 = v1235;
                            v1160 = v1235;
                            if ( v833 )
                            {
                              v116 = v1154;
                            }
                            else
                            {
                              v116 = -2147467259;
                              XlsDiag::LogSetHrCoreTag(-2147467259, 0x279F2A0u);
                              v1309 = 0;
                              ScStgIdsStreamOpen(v1295, 0, 0, v1571, &v1309, -1161035344, 9);
                              if ( SbFromHpCore(v1309) )
                              {
                                if ( !(unsigned int)FBeginDiskIO(v1309) )
                                  goto LABEL_1510;
                                v1263 = 0;
                                if ( (int)HrWPlatformSpecificFromStream2(&v1263) >= 0 )
                                {
                                  if ( (v1263 & 0xF1FF) != 9 )
                                    goto LABEL_1509;
                                  v834 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                                  if ( !*(_QWORD *)(v834 + 32) || (v835 = SH::Pbook(*(SH **)(v834 + 32)), v835 != lp) )
                                  {
                                    v836 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1424, 0x2375A796u);
                                    v837 = SXVWGEOM::RwFirst(v836);
                                    v838 = XLSBOOK::Plxtab((struct BOOK *)((char *)lp + 1640));
                                    v839 = (TAB *)LXTYPE<UsedRange>::PFromI(v838, 0);
                                    v840 = TAB::PshDesktopOnly(v839);
                                    v841 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                  + 304LL)
                                                      + 128LL);
                                    v842 = 0;
                                    if ( v841 )
                                    {
                                      v843 = v841;
                                      do
                                      {
                                        v842 = v843[1];
                                        if ( v842 )
                                          break;
                                        v841 = (_QWORD *)*v841;
                                        v843 = v841;
                                      }
                                      while ( v841 );
                                    }
                                    LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v842 + 96), v840, v837);
                                  }
                                  v1316 = 0;
                                  if ( (int)HrReadBof(v1263, 0, (struct LoadRecovery *)v68, &v1316) >= 0 )
                                  {
                                    v844 = v1264;
                                    v845 = MaxPathHolder::SzPath((MaxPathHolder *)v1350);
                                    if ( (int)HrUpdateWriteAccess(v1581, 516, v845, v844, &v1279) >= 0 )
                                    {
LABEL_1509:
                                      if ( (int)HrEndDiskIO2(0) >= 0 )
                                      {
LABEL_1510:
                                        StreamClose(v1309);
                                        goto LABEL_1511;
                                      }
                                    }
                                  }
                                }
                              }
                              else
                              {
LABEL_1511:
                                if ( v1279 )
                                {
                                  ((void (__fastcall *)(struct IStorage *, _QWORD))v1295->lpVtbl->Commit)(v1295, 0);
                                  if ( ((int (__fastcall *)(struct IStorage *, char *, __int64))v1295->lpVtbl->Stat)(
                                         v1295,
                                         v1550,
                                         1) >= 0 )
                                  {
                                    v846 = BOOK::Pioldoc(lp);
                                    (*(void (__fastcall **)(struct IMsoOLDocument *, _QWORD, __int64))(*(_QWORD *)v846 + 56LL))(
                                      v846,
                                      v1551,
                                      16);
                                    v847 = BOOK::Pioldoc(lp);
                                    (*(void (__fastcall **)(struct IMsoOLDocument *, _QWORD, __int64))(*(_QWORD *)v847 + 56LL))(
                                      v847,
                                      v1552,
                                      17);
                                  }
                                  v848 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                               + 304LL)
                                                   + 40LL)
                                       + 1640LL;
                                  v849 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v848 + 32LL))(v848);
                                  if ( FileLoad::FCheckTimeStampOnThisFile(
                                         *(const struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                           + 304LL)
                                                               + 40LL),
                                         v849,
                                         0,
                                         0) )
                                  {
                                    HrUpdateBookTimeStamps(*(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                       + 304LL)
                                                                           + 40LL));
                                  }
                                }
                              }
                            }
                            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1450;
                            v850 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1425, 0x237630D5u);
                            v851 = SXVWGEOM::RwFirst(v850);
                            v852 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                              + 128LL);
                            v853 = 0;
                            if ( v852 )
                            {
                              v854 = v852;
                              do
                              {
                                v853 = v854[1];
                                if ( v853 )
                                  break;
                                v852 = (_QWORD *)*v852;
                                v854 = v852;
                              }
                              while ( v852 );
                            }
                            LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v853 + 96), v1451, v851);
                            rupBuild = v1317;
                            *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                      + 2924LL) = v1318;
                            ((void (__fastcall *)(struct IStorage *))v1295->lpVtbl->Release)(v1295);
                            v593 = v1299;
                            v810 = lp;
                            v1162 = Src;
                            v1173 = v1216;
                            v1163 = v1247;
LABEL_1524:
                            if ( v1155 )
                            {
                              v855 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                              if ( *(_QWORD *)(v855 + 40) )
                              {
                                sub_14046F5B0(*(_QWORD *)(v855 + 40));
                                v810 = lp;
                              }
                              if ( v1155
                                && v810
                                && !(unsigned int)XlSecurity::FMaaFinal(v810, 5)
                                && !(unsigned int)XlSecurity::FMaaDetected(lp, 5)
                                && !IsWin32AppRunningInWdag() )
                              {
                                EnableMaa(lp, 5);
                                FinalMaa(lp, 5);
                              }
                            }
                            if ( Python::FeatureGates::FEnabledPython(0) && v1155 )
                            {
                              v856 = lp;
                              if ( lp )
                              {
                                if ( !(unsigned int)XlSecurity::FMaaFinal(lp, 8)
                                  && !(unsigned int)XlSecurity::FMaaDetected(lp, 8)
                                  && !IsWin32AppRunningInWdag() )
                                {
                                  EnableMaa(lp, 8);
                                  FinalMaa(lp, 8);
                                }
                                goto LABEL_1540;
                              }
                            }
                            else
                            {
LABEL_1540:
                              v856 = lp;
                            }
                            if ( CastOrNull<XLSWORKBOOK,BOOK>(v856) )
                            {
                              v857 = (const struct Api::Workbook *)CastOrNull<XLSWORKBOOK,BOOK>(lp);
                              if ( Api::ImportFunctionsManager::FIsFeatureEnabled(v857)
                                && v1155
                                && !(unsigned int)XlSecurity::FMaaFinal(lp, 9)
                                && !(unsigned int)XlSecurity::FMaaDetected(lp, 9)
                                && !IsWin32AppRunningInWdag() )
                              {
                                EnableMaa(lp, 9);
                                FinalMaa(lp, 9);
                              }
                            }
                            LOBYTE(v266) = v1153;
LABEL_1549:
                            v858 = (Excel::AppGuard::Actions **)lp;
                            if ( v1155 )
                            {
                              if ( lp )
                              {
                                if ( !Excel::AppGuard::FTryInitAfterLoad(lp, v595) )
                                {
                                  Error(196663);
                                  v1048 = HrFreeBook2(lp);
                                  v606 = v1048;
                                  if ( (_BYTE)v266 )
                                  {
                                    if ( v1048 < 0 )
                                    {
                                      v1168 = v1048;
                                      goto LABEL_1133;
                                    }
                                  }
                                  else if ( v1048 < 0 )
                                  {
                                    v802 = 512506018;
                                    v803 = (MsoReserveTag *)&v1360;
                                    goto LABEL_1925;
                                  }
                                  lp = 0;
                                  v1155 = 0;
                                  goto LABEL_1935;
                                }
                                v858 = (Excel::AppGuard::Actions **)lp;
                              }
                              if ( v1155 && v858 && (a10 & 0x40000) != 0 )
                              {
                                Excel::AppGuard::Actions::AddTrustPromotionRecord(v858[192], (unsigned __int64)v595);
                                v858 = (Excel::AppGuard::Actions **)lp;
                              }
                            }
                            if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                           + 1440LL)
                              && v858 )
                            {
                              v859 = FBookAddin((const struct BOOK *)v858);
                              v860 = v1162;
                              if ( v859 && (int)AddinManager::HrAddOpenAddin(v1162 + 1, *v1162, &vpoldocument) < 0 )
                              {
                                sub_1411BEB10();
                                sub_141232A50();
                                XlsDiag::LogSetHrCoreTag(-2080308954, 0x1E8C38A1u);
                                v606 = -2080308954;
                                goto LABEL_2136;
                              }
                            }
                            else
                            {
                              v860 = v1162;
                            }
                            v861 = 0;
                            if ( v593 )
                            {
                              v862 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                              v863 = *(_QWORD *)(v862 + 32)
                                   ? SH::Pbook(*(SH **)(v862 + 32))
                                   : *(struct BOOK **)(v862 + 40);
                              if ( v863 != SH::Pbook(v593) )
                              {
                                v861 = 1;
                                v864 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                                v1270 = *(struct SH **)(v864 + 32);
                                v1277 = *(struct WNX **)(v864 + 104);
                                v1333 = (struct WNX *)UIGLOBALS::UIGLOBALSCONTAINER::m_selection;
                                v865 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1426, 0x237630D4u);
                                v866 = SXVWGEOM::RwFirst(v865);
                                v867 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                              + 304LL)
                                                  + 128LL);
                                v868 = 0;
                                if ( v867 )
                                {
                                  v869 = v867;
                                  do
                                  {
                                    v868 = v869[1];
                                    if ( v868 )
                                      break;
                                    v867 = (_QWORD *)*v867;
                                    v869 = v867;
                                  }
                                  while ( v867 );
                                }
                                LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v868 + 96), v593, v866);
                              }
                            }
                            if ( v1155 )
                            {
                              v870 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                              if ( *(_QWORD *)(v870 + 40) )
                              {
                                if ( (*(_BYTE *)(*(_QWORD *)(v870 + 1304) + 56LL) & 8) != 0
                                  && (unsigned int)FAnyListsInBook(*(const struct BOOK **)(v870 + 40)) )
                                {
                                  v562 = (unsigned int)CustomTwoAlert(327820, 0, -282329067, -282329066) == 102;
                                  v871 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                                  if ( v562 )
                                    RemoveBookLists(*(const struct BOOK **)(v871 + 40));
                                  else
                                    *(_WORD *)(*(_QWORD *)(v871 + 1304) + 56LL) &= ~8u;
                                }
                              }
                            }
                            if ( !v1155 )
                              goto LABEL_1630;
                            v872 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                            if ( *(_QWORD *)(v872 + 40) )
                            {
                              if ( (*(_BYTE *)(*(_QWORD *)(v872 + 1304) + 56LL) & 8) != 0 )
                              {
                                if ( !XLSBOOK::Plxtab(*(XLSBOOK **)(v872 + 40))
                                  || (v873 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                   + 304LL)
                                                       + 40LL)
                                           + 1640LL,
                                      !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v873 + 32LL))(v873)) )
                                {
                                  v874 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                                  v875 = *(_QWORD *)(v874 + 40);
                                  if ( *(_DWORD *)(v874 + 1836) )
                                  {
                                    *(_DWORD *)(v875 + 884) |= 0x400000u;
                                    goto LABEL_1587;
                                  }
                                  if ( (*(_DWORD *)(v875 + 884) & 0x100) != 0 )
                                  {
                                    *(_DWORD *)(v875 + 884) |= 0x400000u;
                                    v886 = NtCurrentTeb()->ThreadLocalStoragePointer;
                                    *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v886 + 304LL) + 1304LL) + 16LL) = *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v886 + 304LL) + 1232LL) + 110LL);
                                    v73 = 1;
                                    *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                     + 304LL)
                                                         + 1232LL)
                                             + 110LL) = 0;
                                    fnSave(0, 0, 1);
                                    v887 = NtCurrentTeb()->ThreadLocalStoragePointer;
                                    *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v887 + 304LL) + 1232LL) + 110LL) = *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v887 + 304LL) + 1304LL) + 16LL);
                                    goto LABEL_1588;
                                  }
                                }
                              }
                            }
                            if ( !v1155 )
                              goto LABEL_1630;
                            v888 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                            if ( (*(_BYTE *)(*(_QWORD *)(v888 + 1304) + 56LL) & 8) != 0 )
                            {
                              if ( *(_QWORD *)(v888 + 40) )
                              {
                                if ( XLSBOOK::Plxtab(*(XLSBOOK **)(v888 + 40)) )
                                {
                                  v889 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                               + 304LL)
                                                   + 40LL)
                                       + 1640LL;
                                  if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v889 + 32LL))(v889) )
                                  {
                                    v890 = FileSource::HrGetFileTemp(v1307, 12);
                                    v116 = v890;
                                    if ( v890 < 0 )
                                      XlsDiag::LogSetHrCoreTag(v890, 0x280659Au);
                                    if ( v116 < 0 )
                                    {
                                      v116 = -2147467260;
LABEL_1587:
                                      v73 = 1;
                                      goto LABEL_1588;
                                    }
                                    if ( (int)HrStartSharingWbk(
                                                *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                            + 304LL)
                                                                + 40LL),
                                                v1155,
                                                v860,
                                                v1226,
                                                (struct LoadRecovery *)v68,
                                                &v1319,
                                                &v1265) >= 0 )
                                    {
                                      if ( v1156 )
                                      {
                                        v893 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                                        if ( *(_QWORD *)(v893 + 40) )
                                          v894 = BOOK::Pioldoc(*(BOOK **)(v893 + 40));
                                        else
                                          v894 = 0;
                                        *v1163 = v894;
                                        v1159 = v894;
                                      }
                                    }
                                    else
                                    {
                                      if ( v1265 )
                                      {
                                        *v1163 = 0;
                                        v1159 = 0;
                                      }
                                      else if ( v1156 )
                                      {
                                        v891 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                                        if ( *(_QWORD *)(v891 + 40) )
                                          v892 = BOOK::Pioldoc(*(BOOK **)(v891 + 40));
                                        else
                                          v892 = 0;
                                        *v1163 = v892;
                                        v1159 = v892;
                                      }
                                      if ( v1319 || v1265 )
                                        goto LABEL_1587;
                                    }
                                  }
                                }
                              }
                            }
                            if ( v1155
                              && *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                           + 40LL)
                              && v1269 )
                            {
                              v895 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1427, 0x1E111215u);
                              v896 = SXVWGEOM::RwFirst(v895);
                              v73 = 1;
                              BookDirty(
                                *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                            + 304LL)
                                                + 40LL),
                                1,
                                v896);
                              XlsDiag::SendTraceTag(
                                504410769,
                                187,
                                50,
                                4,
                                L"Dirtying workbook because it was loaded from a backup copy.");
                            }
                            else
                            {
LABEL_1630:
                              v73 = 1;
                            }
                            if ( v1155 )
                            {
                              v897 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                              if ( *(_QWORD *)(v897 + 40) )
                              {
                                if ( (unsigned int)FSharedBook(*(const struct BOOK **)(v897 + 40)) )
                                {
                                  v898 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                               + 304LL)
                                                   + 40LL);
                                  if ( (*(_BYTE *)(v898 + 892) & 0x20) != 0 )
                                  {
                                    *(_DWORD *)(v898 + 892) &= ~0x20u;
                                    v899 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1428, 0x231C69Cu);
                                    v900 = SXVWGEOM::RwFirst(v899);
                                    BookDirty(
                                      *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                  + 304LL)
                                                      + 40LL),
                                      1,
                                      v900);
                                    OkAlert(327877, 0);
                                  }
                                }
                              }
                              if ( v1155 )
                              {
                                if ( (unsigned int)FSharedBook(*(const struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                                 + 304LL)
                                                                                     + 40LL)) )
                                {
                                  v901 = LOCATIONCONTEXTDATA::PWorkbookCur((LOCATIONCONTEXTDATA *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                                                                                 + 8LL));
                                  v902 = TLSW::PesExpressionService(*(TLSW **)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                             + 304LL));
                                  ConvertAllDynamicArraystoLegacyArrays(v902, v901);
                                }
                                if ( v1155 )
                                {
                                  if ( *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                             + 304LL)
                                                 + 40LL)
                                    && (unsigned int)sub_14046FB20() )
                                  {
                                    SetAutoRefreshPending(1, 0);
                                  }
                                  if ( v1155
                                    && *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                             + 304LL)
                                                 + 40LL) )
                                  {
                                    v903 = FeatureGateCollectionBase<LoadSaveFeatureGates>::Instance();
                                    v562 = (unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(v903 + 424) == 0;
                                    v904 = NtCurrentTeb()->ThreadLocalStoragePointer;
                                    if ( v562 )
                                    {
                                      v1280 = 0;
                                      v1281 = 0;
                                      v907 = XLSBOOK::Plxtab((XLSBOOK *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v904 + 304LL)
                                                                                   + 40LL)
                                                                       + 1640LL));
                                      XlPng::DyHeight(v907, v1297);
                                      LXContainerContiguousIterators<LXTYPE<TAB>,TAB,LXBASE>::end(v907, v1331);
                                      if ( (unsigned __int8)LXContiguousConstIterator<LXTYPE<TAB>>::operator!=(
                                                              v1297,
                                                              v1331) )
                                      {
                                        do
                                        {
                                          v908 = BKORWS::Psh((BKORWS *)v1297);
                                          v909 = TAB::PshDesktopOnly(v908);
                                          if ( (*((_BYTE *)v909 + 10) & 4) != 0 )
                                            v910 = 0;
                                          else
                                            v910 = *((_BYTE *)v909 + 8);
                                          if ( v910 <= 1u )
                                          {
                                            v911 = TAB::PshDesktopOnly(v908);
                                            GetOartDataForTelemetry(v911, &v1280, &v1281);
                                          }
                                          LXContiguousIterator<LXTYPE<TAB>>::operator++(v1297);
                                        }
                                        while ( (unsigned __int8)LXContiguousConstIterator<LXTYPE<TAB>>::operator!=(
                                                                   v1297,
                                                                   v1331) );
                                        v68 = v1160;
                                      }
                                      LXContiguousIterator<LXTYPE<std::pair<XLUID,DocumentTasks::SharedAuthorMapValue>>>::~LXContiguousIterator<LXTYPE<std::pair<XLUID,DocumentTasks::SharedAuthorMapValue>>>(v1331);
                                      LXContiguousIterator<LXTYPE<std::pair<XLUID,DocumentTasks::SharedAuthorMapValue>>>::~LXContiguousIterator<LXTYPE<std::pair<XLUID,DocumentTasks::SharedAuthorMapValue>>>(v1297);
                                      v912 = Mso::Telemetry::Activity::DataFields(v1215);
                                      Mso::Telemetry::IDataFieldCollection::Add<int>(
                                        v912,
                                        "cMsoShapes",
                                        (unsigned int)v1280,
                                        4);
                                      v913 = Mso::Telemetry::Activity::DataFields(v1215);
                                      Mso::Telemetry::IDataFieldCollection::Add<int>(
                                        v913,
                                        "numShapes",
                                        (unsigned int)v1281,
                                        4);
                                    }
                                    else
                                    {
                                      v905 = v1215;
                                      v906 = LOCATIONCONTEXTDATA::PWorkbookCur((LOCATIONCONTEXTDATA *)(*(_QWORD *)(*(_QWORD *)v904 + 304LL) + 8LL));
                                      ArtUtil::LogOartDataForOpenedWorkbook(v906, v905);
                                    }
                                  }
                                }
                              }
                            }
                            if ( v1228 )
                            {
                              v279 = v1162;
                              CeToggleFileAttr(v1162, v1226, 3, 6u);
                            }
                            else
                            {
LABEL_1588:
                              v279 = v1162;
                            }
                            if ( v861 )
                            {
                              v876 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1429, 0x237630D3u);
                              v877 = SXVWGEOM::RwFirst(v876);
                              v878 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                            + 304LL)
                                                + 128LL);
                              v879 = 0;
                              if ( v878 )
                              {
                                v880 = v878;
                                do
                                {
                                  v879 = v880[1];
                                  if ( v879 )
                                    break;
                                  v878 = (_QWORD *)*v878;
                                  v880 = v878;
                                }
                                while ( v878 );
                              }
                              LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v879 + 96), v1270, v877);
                              v881 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1430, 0x237630D2u);
                              v882 = SXVWGEOM::RwFirst(v881);
                              v883 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                            + 304LL)
                                                + 128LL);
                              v884 = 0;
                              if ( v883 )
                              {
                                v885 = v883;
                                do
                                {
                                  v884 = v885[3];
                                  if ( v884 )
                                    break;
                                  v883 = (_QWORD *)*v883;
                                  v885 = v883;
                                }
                                while ( v883 );
                              }
                              VIEWCONTEXTDATA::CurWnx(*(VIEWCONTEXTDATA **)(v884 + 16), v1277, v882);
                              SetWnxSel(v1333);
                            }
                            else if ( v1305 != (struct SH *)65534 )
                            {
                              v914 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1431, 0x237630D1u);
                              v915 = SXVWGEOM::RwFirst(v914);
                              v916 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                            + 304LL)
                                                + 128LL);
                              v917 = 0;
                              if ( v916 )
                              {
                                v918 = v916;
                                do
                                {
                                  v917 = v918[1];
                                  if ( v917 )
                                    break;
                                  v916 = (_QWORD *)*v916;
                                  v918 = v916;
                                }
                                while ( v916 );
                              }
                              LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v917 + 96), v1305, v915);
                            }
                            goto LABEL_1664;
                          }
                        }
                      }
                    }
                  }
                  v810 = lp;
                }
              }
            }
          }
        }
        v68 = v1160;
        goto LABEL_1524;
      }
      v602 = FileSource::StzFileName((FileSource *)v1307);
      if ( !FForeignFileExtension(v602) && (v1174 || !(unsigned int)FFinderFile(&v1569)) )
      {
        v603 = FileSource::StzFilePath((FileSource *)v1307);
        CchStToStz(v603, v1545, 2086);
        if ( !v1544 )
        {
          MaxPathStzPoke::MaxPathStzPoke((MaxPathStzPoke *)v1505, (struct MaxPathHolder *)v1342);
          v1547 = SlicerViewImpl::PSlicerView((SlicerViewImpl *)v1505);
          MaxPathStzPoke::~MaxPathStzPoke((MaxPathStzPoke *)v1505);
        }
        if ( v1174 && !(unsigned int)FOsrc() )
        {
          v604 = v1219;
LABEL_1130:
          v605 = HrEndDiskIO2(0);
          v606 = v605;
          if ( v1153 )
          {
            if ( v605 < 0 )
              goto LABEL_1132;
          }
          else if ( v605 < 0 )
          {
            v802 = 512506060;
            v803 = (MsoReserveTag *)&v1356;
            goto LABEL_1925;
          }
          StreamClose(v1169);
          if ( (unsigned int)(v604 + 2146697471) <= 1 )
          {
            if ( v68 )
              LoadRecovery::SetRepairState((LoadRecovery *)v68, v604);
            else
              *(&vscd + 1) = 1;
          }
          v116 = -2146827284;
          v1155 = 0;
          v1154 = -2146827284;
          XlsDiag::LogSetHrCoreTag(-2146827284, 0x1797719u);
          v683 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1181);
          v684 = OpenTelemetry::POpenFileStageModel(v683);
          v685 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1411, 0x1F0CB5C5u);
          v686 = SXVWGEOM::RwFirst(v685);
          WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v684, 2214658822LL, v686);
          v598 = v1156;
          goto LABEL_1272;
        }
        LODWORD(v1126) = 0;
        v615 = HrDetectWebType(v1159, (enum MSOFF *)&v1218, &v1294, 0);
        v1219 = v615;
        v604 = v615;
        if ( v615 < 0 )
          goto LABEL_1130;
        if ( v615 == 1 )
        {
          if ( (unsigned int)FCmpTextEq(&v1568[v1569 + 13], L".xml", 4, 4)
            || (unsigned int)FCmpTextEq(&v1568[v1569 + 13], L".xsd", 4, 4) )
          {
            v1203 = 1;
            v616 = 3;
          }
          else
          {
            v616 = 0;
          }
          v1218 = v616;
        }
        if ( (unsigned int)FOsrc() && (unsigned int)(v1218 - 1) > 2 )
          goto LABEL_1130;
        v617 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1181);
        v618 = (LXBASE *)OpenTelemetry::POpenFileStageModel(v617);
        v619 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1409, 0x1F0CB5C4u);
        SXVWGEOM::RwFirst(v619);
        WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v618);
        v620 = a11;
        if ( v1218 == 1 || v1218 == 2 )
        {
          v621 = v1160;
          goto LABEL_1288;
        }
        if ( v1218 == 3 )
        {
          v621 = v1160;
          v622 = HrDetectXMLTypeAndPreprocess(a11, (struct XSL *)&v1543, (struct LoadRecovery *)v1160, 0, 1, 1, v1203);
          v1219 = v622;
          v604 = v622;
          if ( v622 != -2147467263 )
          {
            if ( v622 == -2147418113 )
              goto LABEL_1189;
            if ( v622 == -2147352567 )
            {
              v73 = 1;
              if ( v1544 == 1 )
              {
                MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1464, v1162);
                v1191 = v1180 != 0;
                v1301 = v1159;
              }
              else if ( v1159 )
              {
                (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v1159 + 56LL))(
                  v1159,
                  0xFFFFFFFFLL,
                  7);
                if ( v1180 )
                  HrRecordEvent(v1159, 0x40000000u, 0);
                v629 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1410, 0x2369629Fu);
                v630 = SXVWGEOM::RwFirst(v629);
                OlDocFilePath::FReleaseIOLDoc(v504, 1, 1, v630);
              }
              v410 = 0;
              v1163 = 0;
              v1247 = 0;
              CchStToSt(v1546, v1162, v1226);
              v1216 = 1;
              v606 = HrEndDiskIO2(0);
              if ( v1153 )
              {
                if ( v606 < 0 )
                  goto LABEL_1185;
              }
              else if ( v606 < 0 )
              {
                v802 = 512506059;
                v803 = (MsoReserveTag *)&v1459;
                goto LABEL_1925;
              }
              StreamClose(v1169);
              v68 = v1160;
              a11 = 65001;
              goto LABEL_744;
            }
            if ( v622 )
            {
              if ( v622 != 1 )
              {
                if ( v622 == -2146827284 )
                  Error(262267);
                v68 = v1160;
                goto LABEL_1130;
              }
LABEL_1189:
              v1218 = 1;
              (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v1159 + 56LL))(
                v1159,
                1,
                11);
LABEL_1288:
              FSwitchLoadActionType(2, 0, (struct LoadRecovery *)v621);
              v673 = -(v1218 != 2);
              v674 = BKORWS::Psh((BKORWS *)v1342);
              v675 = 0;
              if ( (unsigned __int8)SafeToLoad::FSafeToLoadOnFileExtensionPfilesource(
                                      v674,
                                      v1307,
                                      (unsigned int)(v673 + 44),
                                      &v1237) )
              {
                MaxPathStzPoke::MaxPathStzPoke((MaxPathStzPoke *)v1507, (struct MaxPathHolder *)v1342);
                v676 = v1294;
                v677 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1836LL);
                LOBYTE(v675) = v1218 == 2;
                v678 = (wchar_t *)SlicerViewImpl::PSlicerView((SlicerViewImpl *)v1507);
                BookHtml = HrLoadBookHtml(v1169, 0, v1572, v678, a5, 0, v676, v620, v675, v677, (struct OSRR *)&v1237);
                v1154 = BookHtml;
                v116 = BookHtml;
                if ( BookHtml < 0 )
                  XlsDiag::LogSetHrCoreTag(BookHtml, 0x2156756u);
                MaxPathStzPoke::~MaxPathStzPoke((MaxPathStzPoke *)v1507);
                v1155 = v116 >= 0;
                if ( v116 >= 0 || !OSRR::FReadyForOsr((OSRR *)&v1237) )
                {
                  v598 = v1156;
                  if ( v1156 )
                  {
                    if ( (unsigned int)IMsoOLDocument::IsInFileSys(v1159) )
                    {
                      if ( v1155
                        || (v680 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL),
                            *(_QWORD *)(v680 + 40))
                        && (*(_DWORD *)(*(_QWORD *)(v680 + 40) + 884LL) & 0x200) != 0 )
                      {
                        v681 = (wchar_t **)XLSBOOK::Plxtab(*(XLSBOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                   + 304LL)
                                                                       + 40LL));
                        FreeHpstTempPath((struct STB *)v681);
                        v682 = FileSource::StzFilePath((FileSource *)v1307);
                        if ( (int)HrStDupSt(v682, v681 + 21) < 0 )
                          v681[21] = 0;
                      }
                    }
                  }
                  v1176 = 1;
                  goto LABEL_1272;
                }
                v73 = 1;
LABEL_1168:
                v1157 = 1;
LABEL_1072:
                v68 = v1160;
                goto LABEL_743;
              }
LABEL_1284:
              v68 = v1160;
              goto LABEL_1130;
            }
            v623 = BKORWS::Psh((BKORWS *)v1342);
            if ( !(unsigned __int8)SafeToLoad::FSafeToLoadOnFileExtensionPfilesource(v623, v1307, 45, &v1237) )
              goto LABEL_1284;
            MaxPathStzPoke::MaxPathStzPoke((MaxPathStzPoke *)v1506, (struct MaxPathHolder *)v1342);
            v624 = (wchar_t *)SlicerViewImpl::PSlicerView((SlicerViewImpl *)v1506);
            BookXmlSpreadsheet = HrLoadBookXmlSpreadsheet(v1169, v1572, v624, a5, 0, v620, (struct OSRR *)&v1237);
            v1154 = BookXmlSpreadsheet;
            v116 = BookXmlSpreadsheet;
            if ( BookXmlSpreadsheet < 0 )
              XlsDiag::LogSetHrCoreTag(BookXmlSpreadsheet, 0x2156757u);
            MaxPathStzPoke::~MaxPathStzPoke((MaxPathStzPoke *)v1506);
            v1155 = v116 >= 0;
            if ( v116 < 0 && OSRR::FReadyForOsr((OSRR *)&v1237) )
            {
              v73 = 1;
              goto LABEL_1168;
            }
            v598 = v1156;
            if ( v1156 )
            {
              if ( (unsigned int)IMsoOLDocument::IsInFileSys(v1159) )
              {
                if ( v1155
                  || (v626 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL),
                      *(_QWORD *)(v626 + 40))
                  && (*(_DWORD *)(*(_QWORD *)(v626 + 40) + 884LL) & 0x200) != 0 )
                {
                  v627 = (wchar_t **)XLSBOOK::Plxtab(*(XLSBOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                             + 304LL)
                                                                 + 40LL));
                  FreeHpstTempPath((struct STB *)v627);
                  v628 = FileSource::StzFilePath((FileSource *)v1307);
                  if ( (int)HrStDupSt(v628, v627 + 21) < 0 )
                    v627[21] = 0;
                }
              }
            }
LABEL_1270:
            v667 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
            if ( *(_QWORD *)(v667 + 24) )
            {
              v668 = OcsTransitionController::PCoauthTransitionState(*(OcsTransitionController **)(v667 + 24));
              XLSBOOK::HrEnsureAllSheetXluids(v668);
            }
            goto LABEL_1272;
          }
          v631 = BKORWS::Psh((BKORWS *)v1342);
          if ( !(unsigned __int8)SafeToLoad::FSafeToLoadOnFileExtensionPfilesource(v631, v1307, 48, &v1237) )
            goto LABEL_1284;
          v632 = BKORWS::Psh((BKORWS *)v1341);
          if ( (unsigned int)FBlockOfficeFile(33, v632, 0) )
            OptDialog = 1223;
          else
            OptDialog = HrShowXmlLoadOptDialog((enum XMLLOADOPTIONS *)&v1232, a12);
          if ( OptDialog )
          {
            if ( OptDialog < 0 )
              XlsDiag::LogSetHrCoreTag(OptDialog, 0x2156759u);
            goto LABEL_1284;
          }
          CodeMarker(1124);
          if ( v1232 != 1 )
          {
            if ( v1232 == 2 )
            {
              if ( v1159
                && ((*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1159 + 80LL))(v1159) & 0x40) == 0
                && (int)HrRecordEvent(v1159, 0x40000000u, 0) >= 0 )
              {
                FBeginCmdIOLDoc(v1159, 4u, 0, 0, 0);
              }
              v650 = APPCORE::PmemheapMain((APPCORE *)&vapp);
              MaxPathHolder::MaxPathHolder((MaxPathHolder *)v1512, v650, 259, 0);
              if ( v1544 )
                v651 = (const wchar_t *)((char *)v1169 + 48);
              else
                v651 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1342);
              MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1512, v651);
              v652 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1342);
              v653 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1512);
              Xml = HrLoadXml(v1169, v1572, 257, v653, v652, 0, a5, 1, 1);
              v1154 = Xml;
              v116 = Xml;
              if ( Xml < 0 )
                XlsDiag::LogSetHrCoreTag(Xml, 0x2156758u);
              MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1512);
              v1155 = v116 >= 0;
              if ( v116 < 0 )
                StreamClose(v1169);
            }
            else
            {
              if ( v1232 != 3 )
              {
                if ( v1232 == 4 )
                {
                  if ( SbFromHpCore(v1169) )
                    StreamClose(v1169);
                  v1169 = FileSource::StreamOpen((FileSource *)v1307, 0x401u, 0);
                  if ( SbFromHpCore(v1169) )
                  {
                    v562 = g_fPromptTextFile == 0;
                    g_fPromptTextFile = 0;
                    v634 = !v562;
                    v1292 = 0;
                    v635 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1352);
                    v636 = (wchar_t *)BKORWS::Psh((BKORWS *)v1352);
                    v606 = HrLoadBiff(
                             &v1169,
                             &v1569,
                             v636,
                             v635,
                             1,
                             a5,
                             a7,
                             v1217,
                             0,
                             &v1196,
                             &v1225,
                             (struct LoadRecovery *)v621,
                             &lp,
                             0,
                             0,
                             0,
                             v1275,
                             &v1292);
                    if ( v1153 )
                    {
                      if ( v606 < 0 )
                        goto LABEL_1185;
                    }
                    else if ( v606 < 0 )
                    {
                      v802 = 512506057;
                      v803 = (MsoReserveTag *)&v1460;
                      goto LABEL_1925;
                    }
                    if ( v1292 )
                    {
                      v637 = BKORWS::Psh((BKORWS *)&v1181);
                      v638 = v1159;
                      v639 = v1169;
                      v640 = v637;
                      v641 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1352);
                      v642 = (wchar_t *)BKORWS::Psh((BKORWS *)v1342);
                      v1241 = FLoadForeign(v1572, v642, v641, v639, a5, 2, &v1262, v638, 0, v1275, v640);
                    }
                    g_fPromptTextFile = v634;
                  }
                }
                goto LABEL_1264;
              }
              v1329 = 0;
              if ( v1159
                && ((*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1159 + 80LL))(v1159) & 0x40) == 0
                && (int)HrRecordEvent(v1159, 0x40000000u, 0) >= 0 )
              {
                FBeginCmdIOLDoc(v1159, 4u, 0, 0, 0);
              }
              v643 = NtCurrentTeb()->ThreadLocalStoragePointer;
              v644 = vpoldocument;
              v1522[7] = 0;
              v1522[3] = 0;
              v645 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v643 + 304LL) + 32LL);
              v646 = NtCurrentTeb()->ThreadLocalStoragePointer;
              v1522[0] = v645;
              v1522[1] = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v646 + 304LL) + 104LL);
              v1522[2] = UIGLOBALS::UIGLOBALSCONTAINER::m_selection;
              (*(void (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)vpoldocument + 8LL))(vpoldocument);
              Project2 = HrCreateProject2(0, 0, 5, 7u, 0, 1);
              v606 = Project2;
              if ( v1153 )
              {
                if ( Project2 < 0 )
                  goto LABEL_1215;
              }
              else if ( Project2 < 0 )
              {
                v802 = 512506053;
                v803 = (MsoReserveTag *)&v1463;
                goto LABEL_1925;
              }
              SuspendRecording();
              if ( (unsigned int)HrDesignXMLCore(v644, &v1329) )
              {
                ResumeRecording();
                if ( v1268 )
                  FreePxlxmlmap(v1268);
                HtmlFailed = HrBookLoadHtmlFailed((struct BLG *)v1522);
                v606 = HtmlFailed;
                if ( v1153 )
                {
                  if ( HtmlFailed < 0 )
                    goto LABEL_1215;
                }
                else if ( HtmlFailed < 0 )
                {
                  v802 = 512506051;
                  v803 = (MsoReserveTag *)&v1399;
                  goto LABEL_1925;
                }
                (*(void (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v644 + 16LL))(v644);
                goto LABEL_1284;
              }
              ResumeRecording();
              RenumberWind(*(struct SH **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                         + 32LL));
              v648 = HrEndDiskIO2(0);
              v606 = v648;
              if ( v1153 )
              {
                if ( v648 < 0 )
                  goto LABEL_1132;
              }
              else if ( v648 < 0 )
              {
                v802 = 512506052;
                v803 = (MsoReserveTag *)&v1461;
                goto LABEL_1925;
              }
              StreamClose(v1169);
              v1155 = 1;
              (*(void (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v644 + 16LL))(v644);
              if ( !FVbaEventEnabled() )
                goto LABEL_1264;
LABEL_1223:
              HrVbaEventDoBookOpen(
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL),
                2);
            }
LABEL_1264:
            CodeMarker(1125);
            v665 = v1177;
            if ( v1155 )
              v665 = 1;
            v1177 = v665;
            if ( ((v1232 - 1) & 0xFFFFFFFD) != 0 )
            {
              v598 = v1156;
            }
            else
            {
              v1347 = 0;
              v666 = FHpshtiFromStt(&v1347, 61);
              v598 = v1156;
              if ( v666 )
                *((_DWORD *)v1347 + 6) = v1232;
            }
            goto LABEL_1270;
          }
          v655 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v656 = 0;
          v1339 = 0;
          v1314 = 0;
          v1308 = 0;
          v1523[7] = 0;
          v1523[3] = 0;
          v657 = vpoldocument;
          v1293 = 1;
          v658 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v655 + 304LL) + 32LL);
          v659 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v1523[0] = v658;
          v1523[1] = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v659 + 304LL) + 104LL);
          v1523[2] = UIGLOBALS::UIGLOBALSCONTAINER::m_selection;
          (*(void (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)vpoldocument + 8LL))(vpoldocument);
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 2132LL) = 1;
          v606 = HrCreateProject2(0, 0, 5, 7u, 0, 1);
          if ( v1153 )
          {
            if ( v606 < 0 )
            {
LABEL_1185:
              v1168 = v606;
              goto LABEL_1133;
            }
          }
          else if ( v606 < 0 )
          {
            v802 = 512506056;
            v803 = (MsoReserveTag *)&v1355;
            goto LABEL_1925;
          }
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 2132LL) = 0;
          SetRef((struct REF *)v1488, 0, 0, 0, 0);
          SuspendRecording();
          if ( (unsigned int)FEnsureVpxierrinfo()
            && !(unsigned int)HrXlXmlMapFromOlDocument(v657, &v1268, &v1339, &v1293, &v1314, &v1308, 1) )
          {
            v660 = LOCATIONCONTEXTDATA::PWorkbookCur((LOCATIONCONTEXTDATA *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                       + 304LL)
                                                                           + 8LL));
            v661 = XLSWORKBOOK::Pcm(v660);
            v662 = OcsTransitionController::PCoauthTransitionState(v661);
            CollabManager::FDisableRevisionGeneration(v662, 196, 0);
            v663 = *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer;
            if ( v1293 )
            {
              LOBYTE(v656) = (unsigned int)HrAutoDesignXML(
                                             0,
                                             v1314,
                                             v1308,
                                             *(struct SH **)(*(_QWORD *)(v663 + 304) + 32LL),
                                             (const struct REF *)v1488,
                                             v1268,
                                             0) == 0;
            }
            else if ( !(unsigned int)HrAutoDesignXML(
                                       v657,
                                       0,
                                       0,
                                       *(struct SH **)(*(_QWORD *)(v663 + 304) + 32LL),
                                       (const struct REF *)v1488,
                                       v1268,
                                       0) )
            {
              v656 = 1;
            }
          }
          (*(void (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v657 + 16LL))(v657);
          if ( v1314 )
          {
            ((void (__fastcall *)(struct IStream *))v1314->lpVtbl->Release)(v1314);
            v1314 = 0;
          }
          if ( v1308 )
          {
            ((void (__fastcall *)(struct IStream *))v1308->lpVtbl->Release)(v1308);
            v1308 = 0;
          }
          DisplayCleanupXIErr();
          ResumeRecording();
          if ( !v656 )
          {
            v672 = HrBookLoadHtmlFailed((struct BLG *)v1523);
            v606 = v672;
            if ( v1153 )
            {
              if ( v672 < 0 )
              {
LABEL_1215:
                v1168 = v606;
                goto LABEL_1133;
              }
            }
            else if ( v672 < 0 )
            {
              v802 = 512506054;
              v803 = (MsoReserveTag *)&v1354;
              goto LABEL_1925;
            }
            goto LABEL_1284;
          }
          if ( *((_DWORD *)vpxsl + 1) )
          {
            FreeHpst(*((wchar_t **)v1268 + 14));
            *((_QWORD *)v1268 + 14) = 0;
            *((_DWORD *)v1268 + 24) = 0;
          }
          v664 = HrEndDiskIO2(0);
          v606 = v664;
          if ( v1153 )
          {
            if ( v664 < 0 )
              goto LABEL_1215;
          }
          else if ( v664 < 0 )
          {
            v802 = 512506055;
            v803 = (MsoReserveTag *)&v1465;
            goto LABEL_1925;
          }
          StreamClose(v1169);
          v1155 = 1;
          if ( !FVbaEventEnabled() )
            goto LABEL_1264;
          goto LABEL_1223;
        }
      }
LABEL_1077:
      v279 = v1162;
LABEL_1078:
      if ( !FEnableForeignFileProtectedView() )
      {
        OSRR::SetAppAllowed((OSRR *)&v1237, 0);
        if ( (unsigned int)XLOSRR::FMustUseOsr((XLOSRR *)&v1237) )
        {
          if ( SbFromHpCore(v1169) )
            StreamClose(v1169);
          v578 = (__int64 *)NtCurrentTeb()->ThreadLocalStoragePointer;
          v1169 = 0;
          v1155 = 0;
          v579 = *v578;
          vhpstm = 0;
          errDeferred = 0;
          v580 = *(_QWORD *)(v579 + 304);
          *(_DWORD *)(v580 + 2024) = 0;
          *(_DWORD *)(v580 + 2028) = 0;
          v116 = -2147024809;
          XlsDiag::LogSetHrCoreTag(-2147024809, 0x179771Au);
          v68 = v1160;
          v73 = 1;
LABEL_1083:
          LOBYTE(v266) = v1153;
          goto LABEL_1664;
        }
      }
      v68 = v1160;
      if ( v1160 && (int)LoadRecovery::Lrmode(v1160) > 0 )
      {
        v73 = 1;
        v687 = 1;
      }
      else
      {
        v687 = 0;
        v73 = 1;
      }
      if ( v687 )
      {
        v688 = PivotOperationBase::PSxview((PivotOperationBase *)v68);
        *((_WORD *)v688 + 18) |= 8u;
      }
      FSwitchLoadActionType(2, 0, (struct LoadRecovery *)v68);
      MaxPathStzPoke::MaxPathStzPoke((MaxPathStzPoke *)v1492, (struct MaxPathHolder *)v1342);
      v689 = APPCORE::PmemheapMain((APPCORE *)&vapp);
      MaxPathHolder::MaxPathHolder((MaxPathHolder *)v1513, v689, 259, 0);
      v690 = FileSource::HrGetFileTemp(v1307, 11);
      v1154 = v690;
      v116 = v690;
      if ( v690 < 0 )
        XlsDiag::LogSetHrCoreTag(v690, 0x27413C1u);
      if ( v116 < 0 )
      {
        if ( SbFromHpCore(v1169) )
          StreamClose(v1169);
        v1169 = 0;
        vhpstm = 0;
        Error(327845);
        errDeferred = 0;
        v1155 = 0;
        MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1513);
        MaxPathStzPoke::~MaxPathStzPoke((MaxPathStzPoke *)v1492);
        goto LABEL_1083;
      }
      v691 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1181);
      v692 = (LXBASE *)OpenTelemetry::POpenFileStageModel(v691);
      v693 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1412, 0x1F0CB5C3u);
      SXVWGEOM::RwFirst(v693);
      WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v692);
      v694 = BKORWS::Psh((BKORWS *)&v1181);
      v695 = v1159;
      v696 = v1169;
      v697 = v694;
      v698 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1513);
      v699 = (wchar_t *)SlicerViewImpl::PSlicerView((SlicerViewImpl *)v1492);
      v1241 = FLoadForeign(v1572, v699, v698, v696, a5, a8, &v1262, v695, (struct XLOSRR *)&v1237, v1275, v697);
      v700 = v1241;
      MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1513);
      MaxPathStzPoke::~MaxPathStzPoke((MaxPathStzPoke *)v1492);
      if ( v700 == -2 )
      {
        v1155 = 0;
        goto LABEL_1323;
      }
      v1155 = v1241;
      if ( !v700 )
      {
LABEL_1323:
        if ( OSRR::FReadyForOsr((OSRR *)&v1237) )
        {
          v68 = v1160;
          v410 = v1163;
          v1157 = 1;
          goto LABEL_744;
        }
        v1154 = -2146827284;
        v116 = -2146827284;
        XlsDiag::LogSetHrCoreTag(-2146827284, 0x230E205u);
      }
      v598 = v1156;
      if ( v1156 )
      {
        if ( (unsigned int)IMsoOLDocument::IsInFileSys(v1159) )
        {
          if ( v1155
            || (v701 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL), *(_QWORD *)(v701 + 40))
            && (*(_DWORD *)(*(_QWORD *)(v701 + 40) + 884LL) & 0x200) != 0 )
          {
            v702 = (wchar_t **)XLSBOOK::Plxtab(*(XLSBOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                       + 304LL)
                                                           + 40LL));
            FreeHpstTempPath((struct STB *)v702);
            v703 = FileSource::StzFilePath((FileSource *)v1307);
            if ( (int)HrStDupSt(v703, v702 + 21) < 0 )
              v702[21] = 0;
          }
        }
      }
      goto LABEL_1272;
    }
    v1169 = 0;
    if ( v1212 != 1 )
    {
      sub_1413EEE50();
      goto LABEL_997;
    }
    LOBYTE(v548) = v1185;
    v549 = sub_141224980(v1159, v548, &v1197);
    v1212 = v549;
    if ( v1197 )
    {
      OSRR::SetAppAllowed((OSRR *)&v1237, 0);
LABEL_997:
      v549 = v1212;
    }
    if ( v549 < 0 )
    {
      v116 = v549;
      XlsDiag::LogSetHrCoreTag(v549, 0x1797718u);
      v585 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1181);
      v586 = OpenTelemetry::POpenFileStageModel(v585);
      v587 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1408, 0x1F0CB5C6u);
      v588 = SXVWGEOM::RwFirst(v587);
      WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v586, 2214658821LL, v588);
      goto LABEL_1093;
    }
    if ( v1156 && !vpoldocument )
      vpoldocument = v1159;
    errDeferred = 0;
    if ( !v1171 )
    {
      v550 = BOOKO::Plocaleinfo((BOOKO *)&vapp);
      if ( FStBundled(v550, &v1569) )
        StripProjNameSt(&v1569, 257);
      goto LABEL_1005;
    }
    v556 = BOOKO::Plocaleinfo((BOOKO *)&vapp);
    if ( FStBundled(v556, &v1569) )
      StripProjNameSt(&v1569, 257);
    v170 = v1173;
LABEL_1026:
    v1171 = 1;
    v557 = FileSource::HrGetFileTemp(v1307, 6);
    v1154 = v557;
    v116 = v557;
    if ( v557 < 0 )
    {
      XlsDiag::LogSetHrCoreTag(v557, 0x274139Eu);
      Error(327845);
      goto LABEL_466;
    }
    v558 = 1049729;
    if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                   + 104LL) != 2 )
      v558 = 1025;
    v1169 = FileSource::StreamOpen((FileSource *)v1307, v558, 0);
    while ( 1 )
    {
      if ( a7 == 1024 )
        goto LABEL_1053;
      if ( !SbFromHpCore(v1169) )
        goto LABEL_1053;
      v559 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
      if ( *(_QWORD *)(v559 + 40) )
      {
        if ( (*(_DWORD *)(*(_QWORD *)(v559 + 40) + 884LL) & 0x200) != 0 )
          goto LABEL_1053;
      }
      if ( v170 || !(unsigned int)FIsExecutableFile(*((void **)v1169 + 1)) )
        break;
      v170 = 1;
      v1173 = 1;
      v1216 = 1;
      StreamClose(v1169);
LABEL_1038:
      v560 = 1048704;
      if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                     + 104LL) != 2 )
        v560 = 0;
      v1169 = FileSource::StreamOpen((FileSource *)v1307, ((v170 != 0) + 1024) | (unsigned int)v560, 0);
      v561 = 0;
      if ( !v1159 )
        goto LABEL_1043;
      errDeferred = _IMsoOLDocument_GetDeferredError(v1159);
      v562 = errDeferred == 0;
      if ( !errDeferred )
      {
        v561 = 0;
LABEL_1043:
        if ( !v170 )
        {
          if ( SbFromHpCore(v1169) )
            v561 = 0;
          else
            v561 = (unsigned __int16)v1169;
        }
        errDeferred = v561;
        v562 = v561 == 0;
      }
      if ( !v562 )
        goto LABEL_1026;
    }
    v563 = FileSource::HrGetFileTemp(v1307, 8);
    v1154 = v563;
    v116 = v563;
    if ( v563 < 0 )
    {
      XlsDiag::LogSetHrCoreTag(v563, 0x27413A0u);
      goto LABEL_1088;
    }
    v564 = BKORWS::Psh((BKORWS *)v1352);
    if ( !(unsigned int)sub_140798B90(v564, (__int64)v1341, (__int64)v1307, a16, (__int64)&v1237) )
    {
LABEL_1089:
      v583 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
      *(_DWORD *)(v583 + 2024) = 0;
      *(_DWORD *)(v583 + 2028) = 0;
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1222;
      LOBYTE(v266) = 0;
      StreamClose(v1169);
      v68 = v1160;
      if ( v1160 )
      {
        v584 = PivotOperationBase::PSxview((PivotOperationBase *)v1160);
        *((_WORD *)v584 + 18) |= 8u;
      }
      v116 = -2146827284;
      XlsDiag::LogSetHrCoreTag(-2146827284, 0x179770Fu);
      goto LABEL_518;
    }
LABEL_1053:
    if ( SbFromHpCore(v1169) )
      goto LABEL_1022;
  }
  while ( (_WORD)v1169 != 2 );
  v565 = FileSource::HrGetFileTemp(v1307, 9);
  v1154 = v565;
  v116 = v565;
  if ( v565 < 0 )
  {
    XlsDiag::LogSetHrCoreTag(v565, 0x27413A1u);
LABEL_1088:
    Error(327845);
    goto LABEL_1089;
  }
  v566 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1181);
  v567 = (LXBASE *)OpenTelemetry::POpenFileStageModel(v566);
  v568 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1407, 0x1F0CB5C8u);
  SXVWGEOM::RwFirst(v568);
  WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v567);
  if ( !XllFlighting::FComponentizedXlls(v569) )
  {
    v1291 = 0;
    v575 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1352);
    v116 = HrRidLoadDLLFile_Deprecated(v575, &v1291, &v1168);
    v1154 = v116;
    if ( v116 < 0 )
      goto LABEL_1133;
    if ( v1291 )
    {
LABEL_1065:
      errDeferred = 0;
      v1155 = 3;
    }
    else
    {
      v574 = 506057947;
      v116 = -2147287008;
      v1154 = -2147287008;
LABEL_1064:
      XlsDiag::LogSetHrCoreTag(-2147287008, v574);
      OkAlert(196759, v1570);
    }
    goto LABEL_439;
  }
  v570 = BKORWS::Psh((BKORWS *)v1352);
  v571 = PcellwGuard::PcellwGuard((PcellwGuard *)v1503, v570);
  LOBYTE(v572) = 1;
  XllFileFromOutsideCalc = XllHost::HrLoadXllFileFromOutsideCalc(*(_QWORD *)v571, v572, 0);
  v1168 = XllFileFromOutsideCalc;
  if ( XllFileFromOutsideCalc >= 0 )
    goto LABEL_1065;
  if ( XllFileFromOutsideCalc == -2080308478 )
  {
    v574 = 36758018;
    v116 = -2147287008;
    v1154 = -2147287008;
    goto LABEL_1064;
  }
LABEL_1133:
  if ( !v1168 )
  {
    MsoShipAssertTagProc(545059735);
    if ( !v1168 )
      v1168 = -2080308954;
  }
  v607 = NtCurrentTeb()->ThreadLocalStoragePointer;
  vfPretendNotStg = 0;
  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v607 + 304LL) + 336LL) = v1222;
  XlsDiag::LogSetHrCoreTag(-2146827284, 0x17976D3u);
  LOBYTE(v608) = std::nullopt;
  std::optional<Measurements::MeasureElapsedTime>::operator=(v1514, v608);
  LOBYTE(v609) = std::nullopt;
  sub_14240D570(v1526, v609);
  OsfOpenScope::Destroy((OsfOpenScope *)v1487);
  XslClear((struct XSL *)&v1543);
  ClearStatusString(11);
  v610 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
  if ( *(_QWORD *)(v610 + 40) != v1303 )
    XlsDiag::SendTraceTag(20509321, 187, 10, 4, L"Jumped during load, global book changed");
  if ( v1304 )
  {
    v610 = 304;
    if ( *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL) == v1304 )
    {
      XlsDiag::SendTraceTag(20509322, 187, 10, 4, L"Jumping after loading a book, possibly corrupt");
      if ( !BOOK::Pioldoc(*(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL)) )
      {
        HrFreeBook(*(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL));
        v611 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1371, 0x237630DEu);
        v612 = SXVWGEOM::RwFirst(v611);
        v613 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 128LL);
        v614 = 0;
        while ( v613 )
        {
          v614 = v613[1];
          if ( v614 )
            break;
          v613 = (_QWORD *)*v613;
        }
        LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v614 + 96), 0, v612);
      }
    }
  }
  if ( v1305 != (struct SH *)65534 )
  {
    v1118 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1372, 0x237630DDu);
    v1119 = SXVWGEOM::RwFirst(v1118);
    v1120 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 128LL);
    v1121 = 0;
    while ( v1120 )
    {
      v1121 = v1120[1];
      if ( v1121 )
        break;
      v1120 = (_QWORD *)*v1120;
    }
    LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v1121 + 96), v1305, v1119);
  }
  if ( v1184 )
    Mso::PerfScenario::HrEndScenario(
      (Mso::PerfScenario *)&vmsoperfidOfficeXLFileOpen,
      (const struct Mso::PerfScenario::MsoPerfScenarioId *)v610);
  if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL) + 8LL)
      & 1) != 0 )
  {
    CrashAlert(0, "Crash in FFileLoad (ignoreable/informational)");
    if ( v1155 && lp )
      FailBookLoad(lp);
    if ( iUseSentinelFile > 0 && hObject != (HANDLE)-1LL )
    {
      CloseHandle(hObject);
      hObject = (HANDLE)-1LL;
    }
  }
  v1122 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
  *(_DWORD *)(v1122 + 2024) = 0;
  *(_DWORD *)(v1122 + 2028) = 0;
  GLOBALS::GLOBALSCONTAINER::m_fs = 0;
  sub_1411BEB10();
  sub_141232A50();
  LOBYTE(v1123) = std::nullopt;
  std::optional<FutureFunctionLabelCreationTracker>::operator=(v1518, v1123);
  LOBYTE(v1124) = std::nullopt;
  std::optional<AutomaticNumberConversionLoadPasteHelper>::operator=(v1346, v1124);
  LOBYTE(v1125) = std::nullopt;
  sub_14240D5B0(v1236, v1125);
  std::optional<XlSecurity::XllTelemetry>::~optional<XlSecurity::XllTelemetry>(v1353);
  v606 = v1168;
  if ( v1168 < 0 )
  {
    v1045 = 512506062;
LABEL_2135:
    XlsDiag::LogSetHrCoreTag(v606, v1045);
  }
LABEL_2136:
  sub_140475F40(v1236);
  std::optional<AutomaticNumberConversionLoadPasteHelper>::~optional<AutomaticNumberConversionLoadPasteHelper>(v1346);
  std::optional<FutureFunctionLabelCreationTracker>::~optional<FutureFunctionLabelCreationTracker>(v1518);
  FileSource::~FileSource((FileSource *)v1307);
  MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1352);
  MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1350);
  MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1484);
  MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1341);
  MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1464);
  MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1342);
  std::optional<OlDocFilePath>::~optional<OlDocFilePath>(v1541);
  Mso::TCntPtr<Uxpp::UxppAnnotationsService>::~TCntPtr<Uxpp::UxppAnnotationsService>(&v1254);
  std::_Optional_destruct_base<Measurements::MeasureElapsedTime,0>::~_Optional_destruct_base<Measurements::MeasureElapsedTime,0>(v1514);
  sub_140475070(v1526);
  std::pair<enum Osf::ModifierKeyFlags const,std::wstring>::~pair<enum Osf::ModifierKeyFlags const,std::wstring>(v1548);
  std::unique_ptr<Measurements::StartOrContinueCapture,HeapDeleter<Measurements::StartOrContinueCapture>>::~unique_ptr<Measurements::StartOrContinueCapture,HeapDeleter<Measurements::StartOrContinueCapture>>(&v1274);
  std::unique_ptr<XlsActivity::XlsDetachedActivity,HeapDeleter<XlsActivity::XlsDetachedActivity>>::~unique_ptr<XlsActivity::XlsDetachedActivity,HeapDeleter<XlsActivity::XlsDetachedActivity>>(&v1313);
  Mso::TCntPtr<IWebAddInOptionalProperties>::~TCntPtr<IWebAddInOptionalProperties>(&v1181);
  Mso::TCntPtr<Uxpp::UxppAnnotationsService>::~TCntPtr<Uxpp::UxppAnnotationsService>(&v1278);
  std::optional<NumberConversionSettingsOverride>::~optional<NumberConversionSettingsOverride>(v1521);
  OsfOpenScope::~OsfOpenScope((OsfOpenScope *)v1487);
  FishbowlTracker::~FishbowlTracker((FishbowlTracker *)v1542);
  std::_Optional_destruct_base<CorruptionMetaData,0>::~_Optional_destruct_base<CorruptionMetaData,0>(v1540);
  std::_Optional_destruct_base<SecuritySettings::ExternalLinks::TrustedLocationCacheScope,0>::~_Optional_destruct_base<SecuritySettings::ExternalLinks::TrustedLocationCacheScope,0>(v1194);
  std::optional<XlSecurity::XllTelemetry>::~optional<XlSecurity::XllTelemetry>(v1353);
  sub_140474C00(&v1210);
  sub_140474D20(&v1192);
  return (unsigned int)v606;
}

```

## disassembly

```asm
0x1402ef090  mov     [rsp-8+arg_10], r8d
0x1402ef096  push    rbp
0x1402ef097  push    rbx
0x1402ef098  push    rsi
0x1402ef099  push    rdi
0x1402ef09a  push    r12
0x1402ef09c  push    r13
0x1402ef09e  push    r14
0x1402ef0a0  push    r15
0x1402ef0a2  lea     rbp, [rsp-0F428h]
0x1402ef0aa  mov     eax, 0F588h
0x1402ef0af  call    _alloca_probe
0x1402ef0b4  sub     rsp, rax
0x1402ef0b7  mov     rax, cs:__security_cookie
0x1402ef0be  xor     rax, rsp
0x1402ef0c1  mov     [rbp+0F460h+var_50], rax
0x1402ef0c8  mov     rax, [rbp+0F460h+arg_40]
0x1402ef0cf  mov     ebx, r9d
0x1402ef0d2  mov     r13, [rbp+0F460h+arg_28]
0x1402ef0d9  mov     r15, [rbp+0F460h+arg_70]
0x1402ef0e0  mov     rdi, [rbp+0F460h+arg_88]
0x1402ef0e7  mov     r14, [rbp+0F460h+arg_98]
0x1402ef0ee  mov     [rbp+0F460h+var_F4A8], rax
0x1402ef0f2  mov     [rbp+0F460h+var_F370], rax
0x1402ef0f9  mov     rax, [rbp+0F460h+arg_60]
0x1402ef100  mov     [rbp+0F460h+var_F2E8], rax
0x1402ef107  mov     rax, [rbp+0F460h+arg_68]
0x1402ef10e  mov     [rbp+0F460h+var_EDE0], rax
0x1402ef115  mov     rax, [rbp+0F460h+arg_80]
0x1402ef11c  mov     [rbp+0F460h+var_F300], rax
0x1402ef123  mov     rax, [rbp+0F460h+arg_90]
0x1402ef12a  mov     [rbp+0F460h+var_F2D0], rax
0x1402ef131  xor     eax, eax
0x1402ef133  mov     [rbp+0F460h+var_F384], eax
0x1402ef139  mov     [rbp+0F460h+var_F4B0], rcx
0x1402ef13d  mov     [rbp+0F460h+Src], rcx
0x1402ef144  lea     esi, [rax+1]
0x1402ef147  mov     [rbp+0F460h+var_F3E0], edx
0x1402ef14d  mov     [rbp+0F460h+var_F457], sil
0x1402ef151  mov     [rbp+0F460h+var_F418], ebx
0x1402ef154  mov     [rbp+0F460h+var_F0D0], r13
0x1402ef15b  mov     [rbp+0F460h+var_F2C8], r15
0x1402ef162  mov     [rbp+0F460h+var_F258], rdi
0x1402ef169  mov     [rbp+0F460h+var_F0C8], r14
0x1402ef170  call    sub_1402DACDC
0x1402ef175  xor     eax, eax
0x1402ef177  mov     [rbp+0F460h+var_F42B], sil
0x1402ef17b  lea     rcx, byte_143FDFC20
0x1402ef182  mov     [rbp+0F460h+var_EF90], al
0x1402ef188  call    ??BFeatureGate@Optimized@AB@Mso@@QEGBA_NXZ; Mso::AB::Optimized::FeatureGate::operator bool(void)
0x1402ef18d  mov     r12d, [rbp+0F460h+arg_78]
0x1402ef194  test    al, al
0x1402ef196  jz      short loc_1402EF1FC
0x1402ef198  xor     eax, eax
0x1402ef19a  mov     [rbp+0F460h+var_F3D5], sil
0x1402ef1a1  lea     rcx, [rbp+0F460h+var_EFA8]
0x1402ef1a8  mov     [rbp+0F460h+var_F114], eax
0x1402ef1ae  call    ??1?$optional@VXllTelemetry@XlSecurity@@@std@@QEAA@XZ; std::optional<XlSecurity::XllTelemetry>::~optional<XlSecurity::XllTelemetry>(void)
0x1402ef1b3  lea     r8, [rbp+0F460h+var_F3D5]
0x1402ef1ba  lea     rdx, [rbp+0F460h+var_F114]
0x1402ef1c1  lea     rcx, [rbp+0F460h+var_EFA8]
0x1402ef1c8  call    ??$_Construct@W4Entry@XllTelemetry@XlSecurity@@_N@?$_Optional_construct_base@VXllTelemetry@XlSecurity@@@std@@QEAAAEAVXllTelemetry@XlSecurity@@$$QEAW4Entry@23@$$QEA_N@Z; std::_Optional_construct_base<XlSecurity::XllTelemetry>::_Construct<XlSecurity::XllTelemetry::Entry,bool>(XlSecurity::XllTelemetry::Entry &&,bool &&)
0x1402ef1cd  lea     rcx, [rbp+0F460h+var_EFA8]
0x1402ef1d4  call    ??C?$optional@VXllTelemetry@XlSecurity@@@std@@QEAAPEAVXllTelemetry@XlSecurity@@XZ; std::optional<XlSecurity::XllTelemetry>::operator->(void)
0x1402ef1d9  mov     rcx, rax
0x1402ef1e0  call    cs:__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x1402ef1e6  lea     r9d, [rsi+3]
0x1402ef1ea  mov     r8d, r12d
0x1402ef1ed  mov     rcx, rax
0x1402ef1f0  lea     rdx, aLoadreason; "LoadReason"
0x1402ef1f7  call    ??$Add@H@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBDHW4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<int>(char const *,int,Mso::Logging::DataClassifications)
0x1402ef1fc  xor     eax, eax
0x1402ef1fe  mov     [rbp+0F460h+var_F453], al
0x1402ef201  call    ?FGetFlagsShadowBag@CircularReferenceTailValue@@MEBA_NAEAV?$TCntPtr@VShadowBag@Api@@@Mso@@@Z; CircularReferenceTailValue::FGetFlagsShadowBag(Mso::TCntPtr<Api::ShadowBag> &)
0x1402ef206  test    al, al
0x1402ef208  jz      short loc_1402EF21D
0x1402ef20a  lea     rcx, [rbp+0Ch]
0x1402ef20f  call    ??1?$_Optional_destruct_base@VTrustedLocationCacheScope@ExternalLinks@SecuritySettings@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<SecuritySettings::ExternalLinks::TrustedLocationCacheScope,0>::~_Optional_destruct_base<SecuritySettings::ExternalLinks::TrustedLocationCacheScope,0>(void)
0x1402ef214  lea     rcx, [rbp+0F460h+var_F454]
0x1402ef218  call    ??$_Construct@$$V@?$_Optional_construct_base@VTrustedLocationCacheScope@ExternalLinks@SecuritySettings@@@std@@QEAAAEAVTrustedLocationCacheScope@ExternalLinks@SecuritySettings@@XZ; std::_Optional_construct_base<SecuritySettings::ExternalLinks::TrustedLocationCacheScope>::_Construct<>(void)
0x1402ef21d  xor     eax, eax
0x1402ef21f  mov     [rbp+0F460h+var_F4B8], al
0x1402ef222  mov     rax, cs:?m_posi@UIGLOBALSCONTAINER@UIGLOBALS@@0PEAVOSI@@EA; OSI * UIGLOBALS::UIGLOBALSCONTAINER::m_posi
0x1402ef229  test    rax, rax
0x1402ef22c  jz      short loc_1402EF24D
0x1402ef22e  mov     rcx, [rax+620h]
0x1402ef235  xor     eax, eax
0x1402ef237  test    rcx, rcx
0x1402ef23a  jz      short loc_1402EF24F
0x1402ef23c  mov     eax, 4000h
0x1402ef241  test    [rcx+0Ch], ax
0x1402ef245  jz      short loc_1402EF24D
0x1402ef247  mov     edx, esi
0x1402ef249  xor     eax, eax
0x1402ef24b  jmp     short loc_1402EF251
0x1402ef24d  xor     eax, eax
0x1402ef24f  mov     edx, eax
0x1402ef251  mov     ecx, [rbp+0F460h+arg_48]
0x1402ef257  mov     [rbp+0F460h+var_F4D8], eax
0x1402ef25a  mov     [rbp+0F460h+var_F48E], al
0x1402ef25d  mov     [rbp+0F460h+var_F31C], eax
0x1402ef263  mov     [rbp+0F460h+var_F2F0], rax
0x1402ef26a  mov     [rbp+0F460h+var_F48F], al
0x1402ef26d  mov     [rbp+0F460h+var_F250], rax
0x1402ef274  mov     [rbp+0F460h+var_F2F8], rax
0x1402ef27b  mov     [rbp+0F460h+var_F2C0], rax
0x1402ef282  mov     [rbp+0F460h+var_F0E0], rax
0x1402ef289  mov     [rbp+0F460h+var_F308], rax
0x1402ef290  mov     [rbp+0F460h+var_F3E8], eax
0x1402ef293  mov     [rbp+0F460h+lp], rax
0x1402ef297  mov     [rbp+0F460h+var_F45C], al
0x1402ef29a  mov     [rbp+0F460h+var_F49F], al
0x1402ef29d  mov     [rbp+0F460h+var_F274], eax
0x1402ef2a3  mov     [rbp+0F460h+var_F3C8], eax
0x1402ef2a9  mov     [rbp+0F460h+var_F404], eax
0x1402ef2ac  mov     [rbp+0F460h+var_F4DC], eax
0x1402ef2af  mov     [rbp+0F460h+var_F3D0], eax
0x1402ef2b5  mov     [rbp+0F460h+var_8100], rax
0x1402ef2bc  mov     eax, ecx
0x1402ef2be  and     eax, esi
0x1402ef2c0  mov     [rbp+0F460h+var_F488], edx
0x1402ef2c3  mov     [rbp+0F460h+var_F120], eax
0x1402ef2c9  mov     eax, ecx
0x1402ef2cb  and     eax, 2
0x1402ef2ce  mov     [rbp+0F460h+var_F44C], 100h
0x1402ef2d5  mov     [rbp+0F460h+var_F110], eax
0x1402ef2db  mov     eax, 8
0x1402ef2e0  mov     [rbp+0F460h+var_80F8], 0FFFFFFFFh
0x1402ef2ea  test    al, cl
0x1402ef2ec  jz      short loc_1402EF2FD
0x1402ef2ee  xor     eax, eax
0x1402ef2f0  cmp     cs:?vpoldocument@@3PEAUIMsoOLDocument@@EA, rax; IMsoOLDocument * vpoldocument
0x1402ef2f7  jnz     short loc_1402EF2FD
0x1402ef2f9  test    edx, edx
0x1402ef2fb  jz      short loc_1402EF32B
0x1402ef2fd  nop     dword ptr [rax]
0x1402ef300  call    ?FOsrc@@YAHXZ; FOsrc(void)
0x1402ef305  xor     ecx, ecx
0x1402ef307  test    eax, eax
0x1402ef309  jnz     short loc_1402EF325
0x1402ef30b  xor     eax, eax
0x1402ef30d  cmp     cs:?m_vpxlosrea@OSRH@@0PEAUXLOSREA@@EA, rcx; XLOSREA * OSRH::m_vpxlosrea
0x1402ef314  setnz   al
0x1402ef317  test    eax, eax
0x1402ef319  jnz     short loc_1402EF325
0x1402ef31b  mov     ecx, [rbp+0F460h+arg_48]
0x1402ef321  xor     eax, eax
0x1402ef323  jmp     short loc_1402EF32D
0x1402ef325  mov     ecx, [rbp+0F460h+arg_48]
0x1402ef32b  mov     eax, esi
0x1402ef32d  mov     [rbp+0F460h+var_F358], eax
0x1402ef333  mov     eax, 130h
0x1402ef338  test    cl, 10h
0x1402ef33b  jnz     short loc_1402EF365
0x1402ef33d  mov     edx, eax
0x1402ef33f  mov     rax, gs:58h
0x1402ef348  mov     rcx, [rax]
0x1402ef34b  mov     rax, [rdx+rcx]
0x1402ef34f  xor     ecx, ecx
0x1402ef351  cmp     [rax+6B0h], ecx
0x1402ef357  jnz     short loc_1402EF365
0x1402ef359  xor     eax, eax
0x1402ef360  cmp     [rbp+0F460h+var_F488], eax
0x1402ef363  jz      short loc_1402EF374
0x1402ef365  call    ?FOsrc@@YAHXZ; FOsrc(void)
0x1402ef36a  test    eax, eax
0x1402ef36c  jnz     short loc_1402EF372
0x1402ef36e  mov     eax, esi
0x1402ef370  jmp     short loc_1402EF374
0x1402ef372  xor     eax, eax
0x1402ef374  mov     [rbp+0F460h+var_F2A4], eax
0x1402ef37a  lea     rcx, [rbp+0F460h+var_5F90]; void *
0x1402ef381  xor     eax, eax
0x1402ef383  mov     [rbp+0F460h+hObject], 0FFFFFFFFFFFFFFFFh
0x1402ef38e  xor     edx, edx; Val
0x1402ef390  mov     [rbp+0F460h+var_F484], al
0x1402ef393  mov     r8d, 202h; Size
0x1402ef399  mov     [rbp+0F460h+var_F400], eax
0x1402ef39c  mov     [rbp+0F460h+var_F4A0], al
0x1402ef39f  mov     [rbp+0F460h+var_F46F], al
0x1402ef3a2  mov     [rbp+0F460h+var_F368], rax
0x1402ef3a9  mov     [rbp+0F460h+var_F324], eax
0x1402ef3af  mov     [rbp+0F460h+var_F468], eax
0x1402ef3b2  mov     [rbp+0F460h+var_F470], al
0x1402ef3b5  mov     [rbp+0F460h+var_F483], al
0x1402ef3b8  mov     [rbp+0F460h+var_F240], rax
0x1402ef3bf  mov     [rbp+0F460h+var_F45B], al
0x1402ef3c2  mov     [rbp+0F460h+var_F46D], al
0x1402ef3c5  mov     [rbp+0F460h+var_F435], al
0x1402ef3c8  mov     [rbp+0F460h+var_F482], al
0x1402ef3cb  call    memset_0
0x1402ef3d0  xor     eax, eax
0x1402ef3d2  mov     [rbp+0F460h+var_F428], esi
0x1402ef3d5  test    ebx, ebx
0x1402ef3d7  mov     [rbp+0F460h+var_F2A0], eax
0x1402ef3dd  mov     [rbp+0F460h+var_F314], eax
0x1402ef3e3  setnz   [rbp+0F460h+var_F3D8]
0x1402ef3ea  mov     [rbp+0F460h+var_F424], al
0x1402ef3ed  mov     [rbp+0F460h+var_F350], rax
0x1402ef3f4  mov     [rbp+0F460h+var_F220], 0FFFEh
0x1402ef3ff  mov     [rbp+0F460h+var_F3B0], eax
0x1402ef405  mov     [rbp+0F460h+var_F3A8], eax
0x1402ef40b  mov     [rbp+0F460h+var_F3A0], rax
0x1402ef412  mov     [rbp+0F460h+var_F398], eax
0x1402ef418  mov     [rbp+0F460h+var_F4D3], al
0x1402ef41b  mov     [rbp+0F460h+var_F448], eax
0x1402ef41e  mov     [rbp+0F460h+var_F464], al
0x1402ef421  mov     [rbp+0F460h+var_F284], eax
0x1402ef427  mov     [rbp+0F460h+var_F49D], al
0x1402ef42a  mov     [rbp+0F460h+var_F49E], al
0x1402ef42d  call    ?CountBooks@@YAHXZ; CountBooks(void)
0x1402ef432  mov     dl, cs:?equivalent@weak_ordering@std@@2U12@B; std::weak_ordering const std::weak_ordering::equivalent
0x1402ef438  lea     r8, [rbp+618h]
0x1402ef440  mov     [rbp+0F460h+var_F338], eax
0x1402ef446  lea     rcx, [rbp+0F460h+var_E4B0]
0x1402ef44d  xor     eax, eax
0x1402ef44f  mov     [rbp+0F460h+var_F354], 80004005h
0x1402ef459  mov     [rbp+0F460h+var_F481], al
0x1402ef45c  mov     [rbp+0F460h+var_F3D7], al
0x1402ef462  mov     [rbp+0F460h+var_F3F0], al
0x1402ef465  lea     rax, ?m_memheapMain@TSGLOBALSCONTAINER@TSGLOBALS@@0VCommonMemoryHeap@@A; CommonMemoryHeap TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain
0x1402ef46c  mov     [rbp+0F460h+var_EE48], rax
0x1402ef473  call    ??$?0PEAVIMemHeap@@@?$_Deleted_move_assign@U?$_Optional_construct_base@VCorruptionMetaData@@@std@@VCorruptionMetaData@@@std@@QEAA@Uin_place_t@1@$$QEAPEAVIMemHeap@@@Z; std::_Deleted_move_assign<std::_Optional_construct_base<CorruptionMetaData>,CorruptionMetaData>::_Deleted_move_assign<std::_Optional_construct_base<CorruptionMetaData>,CorruptionMetaData>(std::in_place_t,IMemHeap * &&)
0x1402ef478  xor     eax, eax
0x1402ef47a  lea     rcx, [rbp+0F460h+var_BD80]; this
0x1402ef481  xor     edx, edx; bool
0x1402ef483  mov     [rbp+0F460h+var_F2E0], eax
0x1402ef489  call    ??0FishbowlTracker@@QEAA@_N@Z; FishbowlTracker::FishbowlTracker(bool)
0x1402ef48e  lea     rcx, [rbp+0F460h+var_EE38]; this
0x1402ef495  call    ??0OpenWorkbooksTracker@@QEAA@XZ; OpenWorkbooksTracker::OpenWorkbooksTracker(void)
0x1402ef49a  xor     eax, eax
0x1402ef49c  mov     [rbp+0F460h+var_F438], sil
0x1402ef4a0  mov     [rbp+0F460h+var_F450], al
0x1402ef4a3  lea     rcx, [rbp+0F460h+var_EC50]; this
0x1402ef4aa  mov     [rbp+0F460h+var_F42F], al
0x1402ef4ad  mov     [rbp+0F460h+var_F437], al
0x1402ef4b0  mov     [rbp+0F460h+var_F46C], al
0x1402ef4b3  mov     eax, [rbp+0F460h+arg_48]
0x1402ef4b9  shr     eax, 14h
0x1402ef4bc  and     al, sil
0x1402ef4bf  mov     [rbp+0F460h+var_F436], al
0x1402ef4c2  call    ??0OsfOpenScope@@QEAA@XZ; OsfOpenScope::OsfOpenScope(void)
0x1402ef4c7  mov     rax, gs:58h
0x1402ef4d0  mov     edx, 130h
0x1402ef4d5  mov     [rbp+0F460h+var_F248], rdx
0x1402ef4dc  mov     rcx, [rax]
0x1402ef4df  mov     rax, [rdx+rcx]
0x1402ef4e3  xor     ecx, ecx
0x1402ef4e5  cmp     [rax+7E8h], ecx
0x1402ef4eb  jz      short loc_1402EF4F8
0x1402ef4ed  mov     ecx, 2562102h
0x1402ef4f2  call    cs:__imp_MsoShipAssertTagProc
0x1402ef4f8  call    ?Instance@?$FeatureGateCollectionBase@VLoadSaveFeatureGates@@@@SAAEBVLoadSaveFeatureGates@@XZ; FeatureGateCollectionBase<LoadSaveFeatureGates>::Instance(void)
0x1402ef4fd  mov     ecx, 8
0x1402ef502  add     rcx, rax
0x1402ef505  call    ??BFeatureGate@Optimized@AB@Mso@@QEGBA_NXZ; Mso::AB::Optimized::FeatureGate::operator bool(void)
0x1402ef50a  movzx   eax, al
0x1402ef50d  xor     eax, esi
0x1402ef50f  mov     cs:dword_143FDFCE8, eax
0x1402ef515  xor     eax, eax
0x1402ef517  cmp     cs:?vfBootInitStartupFolder@@3HA, eax; int vfBootInitStartupFolder
0x1402ef51d  jnz     short loc_1402EF566
0x1402ef51f  cmp     cs:?vfBootInstallAddins@@3HA, eax; int vfBootInstallAddins
0x1402ef525  jnz     short loc_1402EF566
0x1402ef527  call    ?Instance@?$FeatureGateCollectionBase@VPerformanceFeatureGates@@@@SAAEBVPerformanceFeatureGates@@XZ; FeatureGateCollectionBase<PerformanceFeatureGates>::Instance(void)
0x1402ef52c  lea     rcx, ?c_cgADO11394021@PerformanceFeatureGates@@2VChangeGate@Optimized@AB@Mso@@B; Mso::AB::Optimized::ChangeGate const PerformanceFeatureGates::c_cgADO11394021
0x1402ef533  call    ??BChangeGate@Optimized@AB@Mso@@QEGBA_NXZ; Mso::AB::Optimized::ChangeGate::operator bool(void)
0x1402ef538  test    al, al
0x1402ef53a  jnz     short loc_1402EF55A
0x1402ef53c  lea     rcx, ?vmsoperfidOfficeXLBoot@@3UMsoPerfScenarioId@PerfScenario@Mso@@B; Mso::PerfScenario::MsoPerfScenarioId const vmsoperfidOfficeXLBoot
0x1402ef543  call    cs:__imp_?FScenarioActive@PerfScenario@Mso@@YA_NPEBUMsoPerfScenarioId@12@@Z; Mso::PerfScenario::FScenarioActive(Mso::PerfScenario::MsoPerfScenarioId const *)
0x1402ef549  test    al, al
0x1402ef54b  jz      short loc_1402EF55A
0x1402ef54d  lea     rcx, ?vmsoperfidOfficeXLBoot@@3UMsoPerfScenarioId@PerfScenario@Mso@@B; Mso::PerfScenario::MsoPerfScenarioId const vmsoperfidOfficeXLBoot
0x1402ef554  call    cs:__imp_?HrCancelScenario@PerfScenario@Mso@@YAJPEBUMsoPerfScenarioId@12@@Z; Mso::PerfScenario::HrCancelScenario(Mso::PerfScenario::MsoPerfScenarioId const *)
0x1402ef55a  mov     cl, sil
0x1402ef560  call    cs:__imp_?SetActivationKind@BootActivity@Mso@@SAXW4ActivationKind@12@@Z; Mso::BootActivity::SetActivationKind(Mso::BootActivity::ActivationKind)
0x1402ef566  lea     rcx, ?vmsoperfidOfficeXLFileOpen@@3UMsoPerfScenarioId@PerfScenario@Mso@@B; Mso::PerfScenario::MsoPerfScenarioId const vmsoperfidOfficeXLFileOpen
0x1402ef56d  call    cs:__imp_?HrBeginScenario@PerfScenario@Mso@@YAJPEBUMsoPerfScenarioId@12@@Z; Mso::PerfScenario::HrBeginScenario(Mso::PerfScenario::MsoPerfScenarioId const *)
0x1402ef573  mov     ebx, eax
0x1402ef575  mov     [rbp+0F460h+var_F3D4], 44h ; 'D'
0x1402ef57f  xor     eax, eax
0x1402ef581  shr     ebx, 1Fh
0x1402ef584  xor     bl, sil
0x1402ef587  mov     [rbp+0F460h+var_F460], eax
0x1402ef58a  mov     [rbp+0F460h+var_F32C], eax
0x1402ef590  mov     [rbp+0F460h+var_F038], rax
0x1402ef597  mov     eax, cs:?iUseSentinelFile@@3HA; int iUseSentinelFile
0x1402ef59d  mov     [rbp+0F460h+var_F46E], bl
0x1402ef5a0  cmp     eax, 0FFFFFFFFh
0x1402ef5a3  jnz     short loc_1402EF5B8
0x1402ef5a5  lea     rcx, ?vmsoridExcelUseSentinelFile@@3U_msoreg@@B; _msoreg const vmsoridExcelUseSentinelFile
0x1402ef5ac  call    cs:__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z; MsoDwRegGetDw(_msoreg const *)
0x1402ef5b2  mov     cs:?iUseSentinelFile@@3HA, eax; int iUseSentinelFile
0x1402ef5b8  test    eax, eax
0x1402ef5ba  jns     short loc_1402EF5DB
0x1402ef5bc  xor     eax, eax
0x1402ef5be  lea     rcx, ?vmsoridExcelUseSentinelFile@@3U_msoreg@@B; _msoreg const vmsoridExcelUseSentinelFile
0x1402ef5c5  xor     edx, edx
0x1402ef5c7  mov     cs:?iUseSentinelFile@@3HA, eax; int iUseSentinelFile
  ... truncated ...
```
