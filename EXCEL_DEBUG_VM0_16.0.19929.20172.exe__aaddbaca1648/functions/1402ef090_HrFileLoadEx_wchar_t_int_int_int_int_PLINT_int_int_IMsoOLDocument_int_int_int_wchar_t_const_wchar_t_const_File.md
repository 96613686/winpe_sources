# HrFileLoadEx(wchar_t *,int,int,int,int,PLINT * *,int,int,IMsoOLDocument * *,int,int,int,wchar_t const *,wchar_t const *,FileLoadContext *,XlLoadReason,wchar_t const *,XlSyncStateChangeListenerLoad *,VersionHistoryWindowParams *,int *)

- ea: `0x1402ef090`
- end: `0x1402fc87f`
- name: `?HrFileLoadEx@@YAJPEA_WHHHHPEAPEAUPLINT@@HHPEAPEAUIMsoOLDocument@@HHHPEB_W3PEAVFileLoadContext@@W4XlLoadReason@@3PEAVXlSyncStateChangeListenerLoad@@PEAVVersionHistoryWindowParams@@PEAH@Z`
- size: `55279`
- prototype: ``
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
  __int64 v79; // rax
  __int64 v80; // rdx
  Excel::XlBoot **v81; // rax
  wchar_t *v82; // r12
  unsigned int v83; // ebx
  wchar_t *v84; // rax
  const wchar_t *v85; // rax
  struct IMsoOLDocument *v86; // rcx
  char v87; // si
  int v88; // ebx
  bool v89; // di
  OlDocFilePath *v90; // rax
  int v91; // eax
  unsigned int v92; // eax
  _QWORD *v93; // rax
  void *v94; // rdx
  struct IMsoOLDocument *v95; // rcx
  __int64 v96; // rdx
  __int64 v98; // rax
  const wchar_t *v99; // rax
  const wchar_t *v100; // rax
  __int64 v101; // rax
  bool v102; // bl
  struct IMemHeap *v103; // r15
  ZrtUtility *v104; // rax
  const wchar_t *v105; // rdx
  ExpressionService *v106; // rax
  struct WORKBOOKCOLLECTION *v107; // rax
  OlDocFilePath *v108; // rbx
  struct OpenTelemetry *v109; // rax
  OlDocFilePath *v110; // rbx
  SXVWGEOM *v111; // rax
  unsigned int v112; // eax
  int v113; // eax
  int v114; // r15d
  OlDocFilePath *v115; // rax
  struct IMsoOLDocument *v116; // rbx
  ZrtUtility *v117; // rax
  struct IMsoOLDocument *v118; // r9
  ArtUserInterfaceSite *v119; // rbx
  bool v120; // dl
  OpenTelemetry *v121; // rax
  struct OpenTelemetry *v122; // rax
  OlDocFilePath *v123; // rax
  const struct OlDocFilePath *v124; // rax
  int v125; // eax
  OlDocFilePath *v126; // rax
  const wchar_t *v127; // rax
  int v128; // eax
  const wchar_t *v129; // rax
  struct IMsoOLDocument *v130; // rbx
  struct IMemHeap *v131; // rax
  OlDocFilePath *v132; // rax
  const wchar_t *v133; // rax
  const wchar_t *v134; // rax
  IMsoOLDocument *v135; // rcx
  __int64 (__fastcall *v136)(struct IMsoOLDocument *, const wchar_t *, unsigned int *, __int64); // rbx
  const wchar_t *v137; // rax
  int v138; // edi
  int v139; // eax
  OpenTelemetry *v140; // rax
  const wchar_t *v141; // rax
  BOOL v142; // r14d
  bool v143; // di
  unsigned int v144; // ebx
  unsigned int v145; // eax
  BKORWS *v146; // rcx
  const wchar_t *v147; // rax
  __int64 v148; // r9
  wchar_t *v149; // r8
  wchar_t *v150; // rdi
  const wchar_t *v151; // rax
  wchar_t *v152; // rbx
  const wchar_t *v153; // rax
  __int64 v154; // rcx
  const wchar_t *v155; // rax
  unsigned int v156; // ebx
  char v157; // si
  struct IMsoOLDocumentCoauth *v158; // rax
  SXVWGEOM *v159; // rax
  unsigned int v160; // eax
  SXVWGEOM *v161; // rax
  unsigned int v162; // eax
  struct LXTAB *v163; // rax
  struct LXTAB *v164; // rbx
  const wchar_t *v165; // rax
  wchar_t *v166; // rbx
  char v167; // al
  int v168; // esi
  int v169; // eax
  const wchar_t *v170; // rbx
  struct IMemHeap *v171; // rax
  int v172; // eax
  char v173; // al
  int v174; // eax
  struct BOOK *v175; // r8
  bool v176; // al
  struct SH **v177; // rcx
  BOOK *v178; // rax
  struct IMsoOLDocument *v179; // rax
  struct IMsoOLDocument *v180; // rcx
  __int64 v181; // rax
  char v182; // di
  __int64 v183; // rax
  char v184; // al
  int v185; // ebx
  BKORWS *v186; // rax
  struct IMsoOLDocumentCoauth *v187; // rax
  SXVWGEOM *v188; // rax
  unsigned int v189; // eax
  SXVWGEOM *v190; // rax
  unsigned int v191; // eax
  struct IMsoOLDocument *v192; // rdi
  __int64 v193; // rbx
  SXVWGEOM *v194; // rax
  unsigned int v195; // eax
  __int64 v196; // r9
  __int64 v197; // r8
  BOOK *v198; // rbx
  SXVWGEOM *v199; // rax
  unsigned int v200; // eax
  struct IMsoOLDocument *v201; // rax
  __int64 v202; // r8
  struct IMsoOLDocument *v203; // rcx
  SXVWGEOM *v204; // rax
  unsigned int v205; // eax
  BOOK *v206; // rbx
  SXVWGEOM *v207; // rax
  unsigned int v208; // eax
  bool v209; // r14
  __int64 v210; // rsi
  char v211; // di
  char v212; // bl
  struct IMsoOLDocument *v213; // rax
  unsigned int v214; // edx
  const wchar_t *v215; // rax
  __int64 v216; // rcx
  int v217; // ebx
  int v218; // eax
  const struct CXO *v219; // rax
  unsigned int v220; // r8d
  struct BOOK *v221; // rax
  __int64 v222; // rcx
  int inited; // eax
  char v224; // cl
  SXVWGEOM *v225; // rax
  unsigned int v226; // eax
  _QWORD *v227; // rdx
  __int64 v228; // rcx
  _QWORD *v229; // r8
  struct WNX *v230; // rbx
  unsigned __int64 v231; // rax
  SH *v232; // rcx
  struct BOOK *v233; // rax
  __int64 v234; // r8
  __int64 v235; // rax
  struct BOOK *v236; // rax
  SXVWGEOM *v237; // rax
  unsigned int v238; // eax
  _QWORD *v239; // rdx
  __int64 v240; // rcx
  _QWORD *v241; // r8
  SXVWGEOM *v242; // rax
  unsigned int v243; // eax
  _QWORD *v244; // rdx
  __int64 v245; // rcx
  _QWORD *v246; // r8
  unsigned int v247; // edx
  ExpressionService *v248; // rax
  struct WORKBOOKCOLLECTION *v249; // rax
  OlDocFilePath *v250; // rbx
  SXVWGEOM *v251; // rax
  unsigned int v252; // eax
  __int64 v253; // rax
  __int64 v254; // rax
  const wchar_t *Target; // rax
  unsigned int v256; // edx
  const struct OlDocFilePath *v257; // rax
  int v258; // eax
  __int64 v259; // r8
  OlDocFilePath *v260; // rax
  const wchar_t *v261; // rax
  void *v262; // rax
  __int64 v263; // rax
  struct STGI *v264; // r12
  void *v265; // rax
  int v266; // eax
  int v267; // eax
  int v268; // edi
  unsigned int v269; // ebx
  struct IStorage *v270; // rax
  int v271; // eax
  bool v272; // bl
  struct IStorage *v273; // rax
  int v274; // ebx
  int v275; // eax
  wchar_t *v276; // rdi
  wchar_t *v277; // rdi
  int v278; // esi
  struct IMemHeap *v279; // rax
  int v280; // ebx
  wchar_t *v281; // rax
  int CnvTempFile; // eax
  MaxPathStzPoke *v283; // rcx
  int v284; // ebx
  wchar_t *v285; // rax
  int v286; // eax
  const wchar_t *v287; // rax
  const wchar_t *v288; // rax
  int v289; // eax
  __int64 v290; // rcx
  const wchar_t *v291; // rax
  struct OpenTelemetry *v292; // rax
  __int64 v293; // rax
  LXBASE *v294; // rbx
  SXVWGEOM *v295; // rax
  struct STGI *v296; // rax
  int v297; // ebx
  int v298; // eax
  BKORWS *v299; // rcx
  struct SH *v300; // rax
  struct ISlicerView *v301; // rax
  AppGuard::Config *v302; // rcx
  int v303; // eax
  void *v304; // rcx
  __int64 v305; // rax
  __int64 v306; // rbx
  SXVWGEOM *v307; // rax
  unsigned int v308; // eax
  int v309; // ebx
  struct IMemHeap *v310; // rdi
  const struct ILocaleInfo *v311; // rax
  int v312; // edi
  unsigned int v313; // edx
  int v314; // ecx
  MaxPathHolder *v315; // rcx
  __int64 v316; // rax
  CorruptionMetaData *v317; // rax
  CorruptionMetaData *v318; // rbx
  char v319; // al
  __int64 v320; // rax
  __int64 v321; // rax
  __int64 v322; // rax
  LXBASE *v323; // rbx
  SXVWGEOM *v324; // rax
  int v325; // eax
  unsigned int v326; // r8d
  int v327; // ecx
  __int64 v328; // r9
  const wchar_t *v329; // rax
  __int64 v330; // rax
  __int64 v331; // rbx
  SXVWGEOM *v332; // rax
  unsigned int v333; // eax
  __int64 v334; // rdx
  int v335; // edi
  struct IMemHeap *v336; // rax
  wchar_t *v337; // rax
  const wchar_t *v338; // rbx
  const wchar_t *v339; // rax
  struct SH *v340; // rbx
  struct BOOK *v341; // rax
  __int64 v342; // rax
  int v343; // eax
  unsigned int v344; // ebx
  int v345; // ecx
  __int64 v346; // r8
  char v347; // r14
  unsigned int v348; // edx
  int v349; // ecx
  struct SH *v350; // rax
  XlsActivity *v351; // rsi
  struct SH *v352; // rdi
  unsigned __int8 v353; // al
  unsigned int v354; // edx
  struct SH *v355; // rax
  XlsActivity *v356; // rsi
  struct SH *v357; // rdi
  bool v358; // cl
  int v359; // eax
  char v360; // cl
  int v361; // ecx
  const struct ILocaleInfo *v362; // rax
  unsigned __int16 v363; // ax
  int v364; // edi
  __int64 v365; // rax
  __int64 v366; // rbx
  SXVWGEOM *v367; // rax
  unsigned int v368; // eax
  unsigned __int16 v369; // ax
  int v370; // ebx
  unsigned __int16 v371; // di
  char v372; // si
  unsigned int v373; // edx
  int v374; // ecx
  const struct ILocaleInfo *v375; // rax
  OlDocFilePath *v376; // rax
  const struct Mso::Clp::IClpDocument *v377; // rbx
  struct IStorage *EncryptedStorage; // rax
  __int64 v379; // rax
  int DeferredError; // eax
  int v381; // eax
  int v382; // ebx
  char v383; // al
  struct IMemHeap *v384; // rax
  int FileTemp; // eax
  __int64 v386; // r8
  const wchar_t *v387; // rax
  struct FileSource *v388; // rdx
  bool v389; // bl
  const wchar_t *v390; // rax
  wchar_t *v391; // rdx
  __int64 v392; // rdx
  int v393; // eax
  __int64 v394; // rax
  __int64 v395; // rbx
  SXVWGEOM *v396; // rax
  unsigned int v397; // eax
  bool v398; // al
  BOOL v399; // eax
  struct SH *v400; // rax
  int v401; // ecx
  __int64 v402; // rax
  __int64 v403; // rbx
  SXVWGEOM *v404; // rax
  unsigned int v405; // eax
  __int64 v406; // rdx
  struct XPACKAGE *v407; // rax
  struct IMsoOLDocument **v408; // rsi
  __int64 *v409; // rax
  __int64 v410; // rcx
  __int64 v411; // rax
  __int64 v412; // rcx
  struct SXVIEW *v413; // rax
  int v414; // ecx
  __int64 v415; // rax
  LXBASE *v416; // rbx
  SXVWGEOM *v417; // rax
  struct SH *v418; // r13
  OlDocFilePath *v419; // rax
  struct SH *v420; // r14
  struct IMsoDocumentEncryptor *v421; // r15
  int v422; // edi
  struct OpenTelemetry *v423; // r12
  int v424; // esi
  int v425; // ebx
  struct ISlicerView *v426; // rax
  int v427; // r8d
  void *v428; // rax
  struct Api::Workbook *v429; // rax
  __int64 v430; // rcx
  OcsTransitionController *v431; // rax
  XLSBOOK *v432; // rax
  SlicerViewImpl *v433; // rax
  TAB *v434; // rbx
  OcsTransitionController *v435; // rax
  XLSBOOK *v436; // rax
  TAB *v437; // r12
  void *v438; // r14
  struct SH *v439; // rax
  unsigned __int8 v440; // al
  SXVWGEOM *v441; // rax
  unsigned int v442; // edi
  struct SH *v443; // rax
  __int64 v444; // rdx
  __int64 v445; // rcx
  _QWORD *v446; // r8
  _QWORD *v447; // rdx
  __int64 v448; // rax
  SXVWGEOM *v450; // rax
  unsigned int v451; // eax
  _QWORD *v452; // rdx
  __int64 v453; // rcx
  _QWORD *v454; // r8
  struct WNX *v455; // rcx
  const wchar_t *v456; // rax
  CorruptionMetaData *v457; // rax
  struct SXVIEW *v458; // rax
  __int64 v459; // rax
  __int64 v460; // rax
  __int64 v461; // rbx
  SXVWGEOM *v462; // rax
  unsigned int v463; // eax
  __int64 v464; // rax
  struct SXVIEW *v465; // rax
  unsigned int v466; // edi
  struct IStorage *v467; // rax
  int v468; // eax
  __int64 v469; // rax
  __int64 v470; // rcx
  OlDocFilePath *v471; // rax
  const struct Mso::Clp::IClpDocument *v472; // rbx
  struct IStorage *v473; // rax
  bool v474; // al
  OlDocFilePath *v475; // rax
  const struct Mso::Clp::IClpDocument *v476; // rbx
  struct IStorage *v477; // rax
  int v478; // ebx
  struct SXVIEW *v479; // rax
  const wchar_t *v480; // rax
  struct IMemHeap *v481; // rax
  int v482; // eax
  __int64 v483; // rax
  LXBASE *v484; // rbx
  SXVWGEOM *v485; // rax
  const wchar_t *v486; // rax
  int v487; // eax
  SXVWGEOM *v488; // rax
  unsigned int v489; // eax
  _QWORD *v490; // rdx
  __int64 v491; // rcx
  _QWORD *v492; // r8
  const wchar_t *v493; // rax
  struct WNX *v494; // rcx
  __int64 v495; // r8
  int v496; // eax
  __int64 v497; // rbx
  const wchar_t *v498; // rax
  __int64 v499; // rcx
  __int64 v500; // rcx
  unsigned int v501; // r8d
  struct IMsoOLDocument **v502; // rsi
  SXVWGEOM *v503; // rax
  unsigned int v504; // eax
  bool v505; // al
  __int64 v506; // rax
  struct SXVIEW *v507; // rax
  __int64 v508; // rax
  wchar_t **v509; // rbx
  const wchar_t *v510; // rax
  __int64 v511; // rax
  BOOK *v512; // rbx
  SXVWGEOM *v513; // rax
  unsigned int v514; // eax
  __int64 v515; // r8
  Mso::Telemetry::Activity *v516; // rbx
  struct IMsoOLDocumentCoauth *v517; // rax
  SXVWGEOM *v518; // rax
  unsigned int v519; // eax
  struct Mso::Telemetry::IDataFieldCollection *v520; // rax
  unsigned int v521; // edi
  struct Mso::Telemetry::IDataFieldCollection *v522; // rax
  BOOK *v523; // rcx
  struct IMsoXmlDataStore *v524; // rbx
  struct IMsoOLDocument *v525; // rax
  __int64 v526; // rax
  __int64 v527; // rcx
  struct OfficeSpace::IOutSpace *OutSpace; // rdi
  void (__fastcall *v529)(struct OfficeSpace::IOutSpace *, _QWORD, struct IMsoOLDocument *); // rbx
  struct IMsoOLDocument *v530; // rax
  struct IMsoOLDocument *v531; // rax
  struct IMsoAddInX **v532; // rdx
  struct IMsoOLDocument *v533; // rax
  __int64 v534; // rax
  SXVWGEOM *v535; // rax
  unsigned int v536; // eax
  __int64 v537; // rax
  __int64 v538; // r8
  int v539; // eax
  __int64 v540; // rdx
  __int64 v541; // rcx
  unsigned __int64 v542; // rax
  struct SXVIEW *v543; // rax
  struct SXVIEW *v544; // rax
  struct OpenTelemetry *v545; // rax
  __int64 v546; // rdx
  int v547; // eax
  const struct ILocaleInfo *v548; // rax
  BOOL v549; // ecx
  struct STGI *v550; // rax
  unsigned int v551; // ebx
  struct IStorage *v552; // rax
  const wchar_t *v553; // rax
  const struct ILocaleInfo *v554; // rax
  int v555; // eax
  unsigned int v556; // edx
  __int64 v557; // rax
  int v558; // edx
  int v559; // eax
  bool v560; // zf
  int v561; // eax
  XlSecurity *v562; // rax
  int v563; // eax
  __int64 v564; // rax
  LXBASE *v565; // rbx
  SXVWGEOM *v566; // rax
  XllFlighting *v567; // rcx
  struct CELLW *v568; // rax
  PcellwGuard *v569; // rax
  __int64 v570; // rdx
  int XllFileFromOutsideCalc; // eax
  unsigned int v572; // edx
  const wchar_t *v573; // rax
  __int64 v574; // rax
  struct SXVIEW *v575; // rax
  __int64 *v576; // rax
  __int64 v577; // rcx
  __int64 v578; // rax
  unsigned int v579; // edx
  __int64 v580; // rax
  __int64 v581; // rax
  struct SXVIEW *v582; // rax
  __int64 v583; // rax
  __int64 v584; // rbx
  SXVWGEOM *v585; // rax
  unsigned int v586; // eax
  void *v587; // rax
  __int64 v588; // rax
  int v589; // ebx
  __int64 v590; // r8
  SH *v591; // r13
  __int64 v592; // rax
  const struct BOOK *v593; // rdx
  const wchar_t *v594; // rax
  int v595; // eax
  bool v596; // r14
  __int64 v597; // rax
  wchar_t **v598; // rdi
  const wchar_t *v599; // rax
  const wchar_t *v600; // rax
  const wchar_t *v601; // rax
  int v602; // r13d
  int v603; // eax
  int v604; // ebx
  void *v605; // rax
  __int64 v606; // rdx
  __int64 v607; // rdx
  __int64 v608; // rdx
  SXVWGEOM *v609; // rax
  unsigned int v610; // eax
  _QWORD *v611; // rdx
  __int64 v612; // rcx
  int v613; // eax
  int v614; // eax
  __int64 v615; // rax
  LXBASE *v616; // rbx
  SXVWGEOM *v617; // rax
  int v618; // r14d
  wchar_t *v619; // rdi
  int v620; // eax
  struct SH *v621; // rax
  wchar_t *v622; // rax
  int BookXmlSpreadsheet; // eax
  __int64 v624; // rax
  wchar_t **v625; // rdi
  const wchar_t *v626; // rax
  SXVWGEOM *v627; // rax
  unsigned int v628; // eax
  struct SH *v629; // rax
  struct SH *v630; // rax
  int OptDialog; // eax
  BOOL v632; // r12d
  const wchar_t *v633; // rbx
  wchar_t *v634; // rax
  struct SH *v635; // rax
  struct IMsoOLDocument *v636; // rdi
  struct STM *v637; // r14
  struct OpenTelemetry *v638; // rbx
  const wchar_t *v639; // rsi
  wchar_t *v640; // rax
  void *v641; // rax
  struct IMsoOLDocument *v642; // rdi
  __int64 v643; // rcx
  void *v644; // rax
  int Project2; // eax
  int v646; // eax
  int HtmlFailed; // eax
  struct IMemHeap *v648; // rax
  const wchar_t *v649; // rdx
  const wchar_t *v650; // rbx
  const wchar_t *v651; // rax
  int Xml; // eax
  void *v653; // rax
  int v654; // edi
  struct IMsoOLDocument *v655; // rsi
  __int64 v656; // rcx
  void *v657; // rax
  XLSWORKBOOK *v658; // rax
  OcsTransitionController *v659; // rax
  struct Api::CoauthTransitionState *v660; // rax
  __int64 v661; // rcx
  int v662; // eax
  bool v663; // al
  int v664; // eax
  __int64 v665; // rcx
  XLSBOOK *v666; // rax
  SXVWGEOM *v667; // rax
  unsigned int v668; // eax
  struct IMsoOLDocument *v669; // r10
  int v670; // eax
  int v671; // ebx
  struct SH *v672; // rax
  int v673; // esi
  int v674; // ebx
  int v675; // edi
  wchar_t *v676; // rax
  int BookHtml; // eax
  __int64 v678; // rax
  wchar_t **v679; // rdi
  const wchar_t *v680; // rax
  __int64 v681; // rax
  __int64 v682; // rbx
  SXVWGEOM *v683; // rax
  unsigned int v684; // eax
  char v685; // al
  struct SXVIEW *v686; // rax
  struct IMemHeap *v687; // rax
  int v688; // eax
  __int64 v689; // rax
  LXBASE *v690; // rbx
  SXVWGEOM *v691; // rax
  struct SH *v692; // rax
  struct IMsoOLDocument *v693; // rdi
  struct STM *v694; // r14
  struct OpenTelemetry *v695; // rbx
  const wchar_t *v696; // rsi
  wchar_t *v697; // rax
  int v698; // ebx
  __int64 v699; // rax
  wchar_t **v700; // rdi
  const wchar_t *v701; // rax
  BOOL v702; // ebx
  BOOL v703; // r8d
  BOOL v704; // edi
  BOOL v705; // r9d
  __int64 v706; // rax
  __int64 v707; // r10
  const struct OLDocFactory *v708; // rax
  BOOK *v709; // rbx
  SXVWGEOM *v710; // rax
  unsigned int v711; // eax
  __int64 v712; // rcx
  void *v713; // rax
  __int64 v714; // rdx
  unsigned __int8 v715; // al
  unsigned int v716; // eax
  SXVWGEOM *v717; // rax
  unsigned int v718; // eax
  bool v719; // r8
  bool v720; // r13
  __int64 v721; // rax
  LXBASE *v722; // rbx
  SXVWGEOM *v723; // rax
  __int64 v724; // rax
  void *v725; // rax
  __int64 v726; // rax
  int v727; // eax
  char v728; // r12
  Mso::DocumentWindow::EventMgr *v729; // rcx
  WN *v730; // rcx
  UIFRAME *v731; // rax
  struct IMsoOLDocument *v732; // rbx
  Excel::XlMso *v733; // rax
  HWND v734; // r8
  struct IMsoOLDocument *v735; // rax
  struct Api::CoauthTransitionState *v736; // rbx
  unsigned int v737; // eax
  struct Api::Workbook *v738; // rax
  struct XlFileProtocol *Protocol; // rbx
  MsoReserveTag *v740; // rax
  struct BOOK *v741; // rdi
  unsigned int v742; // ebx
  struct SH *v743; // rax
  __int64 v744; // rax
  __int64 v745; // rdx
  _DWORD *v746; // rax
  __int64 v747; // rax
  struct Api::Workbook *v748; // rax
  XlAsyncFileIO *v749; // rax
  XlRenameHandler *v750; // rax
  unsigned int v751; // ebx
  __int64 v752; // rax
  __int64 v753; // rax
  struct Api::Workbook *v754; // rax
  struct IMerge *v755; // rax
  __int64 v756; // rax
  __int64 v757; // rax
  struct Api::Workbook *v758; // rax
  struct Mso::Telemetry::IDataFieldCollection *v759; // rbx
  unsigned int refreshed; // eax
  __int64 v761; // rax
  IEndpointAgent *v762; // rax
  ClassifyLabelProtectManager *v763; // rax
  IdleLoop *v764; // rcx
  __int64 v765; // rax
  AutoSaveManager *v766; // rax
  struct BOOKO *v767; // rdx
  int v768; // eax
  SXVWGEOM *v769; // rax
  unsigned int v770; // r10d
  __int64 v771; // rcx
  struct SH *v772; // r9
  _QWORD *v773; // rax
  __int64 v774; // rcx
  _QWORD *v775; // rdx
  __int64 v776; // rax
  struct WNX *v777; // rdi
  void *v778; // r14
  struct WNX *v779; // rax
  struct WNX *v780; // rbx
  struct WNX *v781; // rdx
  int v782; // ecx
  struct SH *v783; // r12
  SXVWGEOM *v784; // rax
  unsigned int v785; // eax
  __int64 v786; // rdx
  __int64 v787; // rcx
  _QWORD *v788; // r8
  _QWORD *v789; // rdx
  __int64 v790; // rdx
  __int64 v791; // rcx
  __int64 v792; // rax
  struct CS *v793; // rax
  SXVWGEOM *v794; // rax
  unsigned int v795; // eax
  __int64 v796; // rdx
  __int64 v797; // rcx
  _QWORD *v798; // r8
  _QWORD *v799; // rdx
  unsigned int v800; // edx
  MsoReserveTag *v801; // rcx
  __int64 v802; // rax
  __int64 v803; // r8
  int v804; // eax
  __int64 v805; // rax
  __int64 v806; // rax
  __int64 v807; // r8
  struct BOOK *v808; // r8
  IMsoOLDocument *v809; // rax
  struct IMsoOLDocument *v810; // rax
  struct IMsoOLDocument *v811; // rax
  unsigned int v812; // esi
  __int64 v813; // r14
  SXVWGEOM *v814; // rax
  unsigned int v815; // edi
  unsigned int v816; // ebx
  struct IMsoOLDocument *v817; // rax
  struct IMsoOLDocument *v818; // rax
  SXVWGEOM *v819; // rax
  unsigned int v820; // ebx
  struct IMsoOLDocument *v821; // rax
  struct IMsoOLDocument *v822; // rax
  struct IMsoOLDocument *v823; // rax
  struct IMsoOLDocument *v824; // rax
  struct IMsoOLDocument *v825; // rax
  struct IMsoOLDocument *v826; // rax
  const wchar_t *v827; // rax
  struct IMsoOLDocument *v828; // rax
  void *v829; // rax
  __int64 v830; // r8
  int v831; // eax
  __int64 v832; // rcx
  struct BOOK *v833; // rax
  SXVWGEOM *v834; // rax
  unsigned int v835; // ebx
  struct LXTAB *v836; // rax
  TAB *v837; // rax
  struct SH *v838; // rax
  _QWORD *v839; // rdx
  __int64 v840; // rcx
  _QWORD *v841; // r8
  int v842; // ebx
  const wchar_t *v843; // rax
  struct IMsoOLDocument *v844; // rax
  struct IMsoOLDocument *v845; // rax
  __int64 v846; // rcx
  const wchar_t *v847; // rax
  SXVWGEOM *v848; // rax
  unsigned int v849; // eax
  _QWORD *v850; // rdx
  __int64 v851; // rcx
  _QWORD *v852; // r8
  __int64 v853; // rcx
  struct BOOK *v854; // rcx
  const struct Api::Workbook *v855; // rax
  Excel::AppGuard::Actions **v856; // r8
  int v857; // eax
  wchar_t *v858; // rdi
  char v859; // si
  __int64 v860; // rcx
  struct BOOK *v861; // rbx
  __int64 v862; // r8
  SXVWGEOM *v863; // rax
  unsigned int v864; // eax
  _QWORD *v865; // r8
  __int64 v866; // rcx
  _QWORD *v867; // rdx
  __int64 v868; // rcx
  __int64 v869; // rax
  __int64 v870; // rcx
  __int64 v871; // rcx
  __int64 v872; // r8
  __int64 v873; // rax
  SXVWGEOM *v874; // rax
  unsigned int v875; // eax
  _QWORD *v876; // rdx
  __int64 v877; // rcx
  _QWORD *v878; // r8
  SXVWGEOM *v879; // rax
  unsigned int v880; // eax
  _QWORD *v881; // rdx
  __int64 v882; // rcx
  _QWORD *v883; // r8
  void *v884; // rax
  void *v885; // rax
  __int64 v886; // rcx
  __int64 v887; // rcx
  int v888; // eax
  __int64 v889; // rcx
  struct IMsoOLDocument *v890; // rax
  __int64 v891; // rcx
  struct IMsoOLDocument *v892; // rax
  SXVWGEOM *v893; // rax
  unsigned int v894; // eax
  __int64 v895; // rcx
  __int64 v896; // rax
  SXVWGEOM *v897; // rax
  unsigned int v898; // eax
  const struct Api::Workbook *v899; // rbx
  struct ExpressionService *v900; // rax
  __int64 v901; // rax
  void *v902; // rax
  struct XlsActivity *v903; // rbx
  const struct Api::Workbook *v904; // rax
  struct LXTAB *v905; // rbx
  TAB *v906; // rbx
  struct SH *v907; // rax
  unsigned __int8 v908; // cl
  struct SH *v909; // rax
  struct Mso::Telemetry::IDataFieldCollection *v910; // rax
  struct Mso::Telemetry::IDataFieldCollection *v911; // rax
  SXVWGEOM *v912; // rax
  unsigned int v913; // eax
  _QWORD *v914; // rdx
  __int64 v915; // rcx
  _QWORD *v916; // r8
  const wchar_t *v917; // rax
  __int64 v918; // rax
  OlDocFilePath *v919; // rax
  struct IMsoOLDocument *v920; // rbx
  SXVWGEOM *v921; // rax
  unsigned int v922; // eax
  SXVWGEOM *v923; // rax
  unsigned int v924; // eax
  __int64 v925; // rax
  __int64 v926; // rcx
  struct Api::Workbook *v927; // rax
  struct Mso::Telemetry::IDataFieldCollection *v928; // rax
  __int64 v929; // r8
  int v930; // edx
  unsigned __int64 v931; // rax
  struct IMsoOLDocument *v932; // rax
  CardView::DataElementRecord *v933; // rax
  PivotMetadataCache *v934; // rax
  OcsTransitionController *v935; // rax
  struct Api::CoauthTransitionState *v936; // rax
  struct IMsoOLDocument *v937; // rax
  char v938; // bl
  BKORWS *v939; // rdi
  CardView::DataElementRecord *v940; // rax
  struct SH *v941; // rbx
  __int64 v942; // rax
  struct SH *v943; // rbx
  struct Api::Workbook *v944; // rax
  struct QuickLoadContext *v945; // r8
  struct IMemHeap *v946; // rbx
  unsigned int v947; // edi
  struct Api::Workbook *v948; // rax
  XlAsyncFileIO *v949; // rax
  __int64 v950; // rax
  int v951; // eax
  bool v952; // cf
  __int64 v953; // r8
  struct Api::CoauthTransitionState *v954; // rax
  __int64 v955; // rax
  struct Api::Workbook *v956; // rax
  struct Api::Workbook *v957; // rbx
  const struct WN *v958; // r8
  struct IMemHeap *v959; // rdi
  struct BOOK *v960; // rcx
  unsigned int v961; // ebx
  ZrtUtility *v962; // rax
  int v963; // r9d
  __int64 v964; // rax
  BKORWS *v965; // rbx
  QuickLoadContext *v966; // rax
  const wchar_t *v967; // rbx
  __int64 v968; // rcx
  const struct BOOK *v969; // rcx
  int Only; // eax
  int v971; // ecx
  int v972; // r8d
  struct BOOK *v973; // rdi
  __int64 v974; // rax
  __int64 v975; // rax
  BOOL v976; // ebx
  struct IMsoOLDocument *v977; // rax
  bool v978; // bl
  unsigned int v979; // eax
  struct IMsoOLDocument *v980; // rax
  struct IMsoOLDocument *v981; // rax
  Api::RichDataSharedManager *v982; // rax
  Api::LinkedEntityFeature *LinkedEntityFeature; // rax
  RichDataManagerHost *v984; // rax
  const struct Api::Workbook *v985; // rdx
  CleanupWorkbookStylesBusinessBar *v986; // rax
  struct Api::Workbook *v987; // rdx
  unsigned __int64 v988; // rbx
  unsigned int v989; // eax
  char v990; // al
  struct OSRC *Osrc; // rax
  int v992; // eax
  unsigned int v993; // edx
  CorruptionMetaData *v994; // rax
  char v995; // al
  LoadRecovery *v996; // rcx
  int v997; // edx
  unsigned __int64 v998; // rax
  int v999; // ebx
  bool v1000; // al
  unsigned __int64 BookCorrupt; // rbx
  void *v1002; // rax
  unsigned __int64 v1003; // rax
  __int64 v1004; // rcx
  unsigned int v1005; // eax
  int v1006; // ebx
  const wchar_t *v1007; // rax
  int v1008; // r8d
  __int64 v1009; // r8
  wchar_t *v1010; // rbx
  const wchar_t *v1011; // rbx
  unsigned int v1012; // eax
  struct IMsoOLDocument **v1013; // rbx
  SXVWGEOM *v1014; // rax
  unsigned int v1015; // eax
  OlDocFilePath *v1016; // rax
  struct IMsoOLDocument **v1017; // rbx
  SXVWGEOM *v1018; // rax
  unsigned int v1019; // eax
  SXVWGEOM *v1020; // rax
  unsigned int v1021; // eax
  unsigned int v1022; // edx
  int v1023; // ecx
  int v1024; // eax
  unsigned int v1025; // edx
  int v1026; // eax
  int v1027; // ecx
  char v1028; // al
  unsigned int v1029; // eax
  unsigned __int64 Count; // rax
  UIFRAME *v1031; // rax
  HWND v1032; // rax
  __int64 v1033; // rax
  __int64 v1034; // rbx
  SXVWGEOM *v1035; // rax
  unsigned int v1036; // eax
  __int64 v1037; // rax
  __int64 v1038; // rax
  __int64 v1039; // rax
  __int64 v1040; // rax
  SXVWGEOM *v1041; // rax
  unsigned int v1042; // eax
  unsigned int v1043; // edx
  SXVWGEOM *v1044; // rax
  unsigned int v1045; // eax
  int v1046; // eax
  __int64 Title; // rax
  __int64 v1048; // rdx
  __int64 v1049; // rsi
  SXVWGEOM *v1050; // rax
  int v1051; // ebx
  Mso::Telemetry *v1052; // rax
  unsigned int v1053; // r9d
  int v1054; // eax
  __int64 v1055; // r8
  SXVWGEOM *v1056; // rax
  unsigned int v1057; // eax
  const wchar_t *v1058; // rax
  struct IMsoOLDocument *v1059; // rax
  __int64 v1060; // rdx
  ZrtUtility *v1061; // rax
  struct IMsoOLDocument *v1062; // rdx
  __int64 v1063; // rax
  CorruptionMetaData *v1064; // rax
  unsigned __int8 v1065; // al
  __int64 v1066; // r9
  __int64 v1067; // r8
  struct IMsoOLDocument *v1068; // rax
  struct BOOK *v1069; // r8
  int v1070; // eax
  CorruptionMetaData *v1071; // rax
  Mso::History *v1072; // rcx
  int v1073; // ecx
  int v1074; // ecx
  unsigned int v1075; // edx
  wchar_t *v1076; // rdx
  int v1077; // ecx
  ODFROBUSTLOAD *AffectedProcessSessionId; // rax
  wchar_t *v1079; // rdx
  int v1080; // ecx
  ODFROBUSTLOAD *v1081; // rax
  ODFROBUSTLOAD *v1082; // rax
  __int64 v1083; // rax
  __int64 v1084; // r8
  struct Api::Workbook *v1085; // rax
  struct IPowerQueryWorkbookManager *Manager; // rax
  struct IMsoOLDocument *v1087; // rax
  __int64 v1088; // rcx
  unsigned int v1089; // eax
  unsigned int v1090; // ebx
  int v1091; // eax
  int v1092; // edx
  int v1093; // eax
  __int64 v1094; // rax
  SXVWGEOM *v1095; // rax
  unsigned int v1096; // eax
  __int64 v1097; // r8
  __int64 v1098; // rax
  __int64 v1099; // rax
  int Sz; // ebx
  int v1101; // eax
  __int64 *v1102; // rcx
  int v1103; // ebx
  __int64 v1104; // rcx
  int v1105; // edx
  __int64 v1106; // rcx
  int v1107; // eax
  unsigned int v1108; // eax
  SXVWGEOM *v1109; // rax
  unsigned int v1110; // eax
  bool v1111; // dl
  SXVWGEOM *v1112; // rax
  SXVWGEOM *v1113; // rax
  unsigned int v1114; // eax
  const wchar_t *v1115; // rax
  SXVWGEOM *v1116; // rax
  unsigned int v1117; // eax
  _QWORD *v1118; // rdx
  __int64 v1119; // rcx
  __int64 v1120; // rax
  __int64 v1121; // rdx
  __int64 v1122; // rdx
  __int64 v1123; // rdx
  struct IStream **v1124; // [rsp+20h] [rbp-140h]
  struct IStream **v1125; // [rsp+20h] [rbp-140h]
  struct IStream **v1126; // [rsp+28h] [rbp-138h]
  struct IStream **v1127; // [rsp+28h] [rbp-138h]
  wchar_t *v1128; // [rsp+30h] [rbp-130h]
  struct LoadRecovery *v1129; // [rsp+38h] [rbp-128h]
  struct LoadRecovery *v1130; // [rsp+38h] [rbp-128h]
  struct XlsActivity *v1131; // [rsp+40h] [rbp-120h]
  struct XlsActivity *v1132; // [rsp+40h] [rbp-120h]
  wchar_t *v1133; // [rsp+48h] [rbp-118h]
  struct ENV *v1134; // [rsp+48h] [rbp-118h]
  struct OpenTelemetry *v1135; // [rsp+50h] [rbp-110h]
  bool v1136; // [rsp+50h] [rbp-110h]
  struct LoadRecovery *v1137; // [rsp+58h] [rbp-108h]
  struct IMsoDocumentEncryptor *v1138; // [rsp+60h] [rbp-100h]
  bool v1139; // [rsp+68h] [rbp-F8h]
  struct IMsoOLDocument *v1140; // [rsp+70h] [rbp-F0h]
  const wchar_t *v1141; // [rsp+78h] [rbp-E8h]
  struct VersionHistoryWindowParams *v1142; // [rsp+80h] [rbp-E0h]
  struct BOOK *v1143; // [rsp+80h] [rbp-E0h]
  bool v1144; // [rsp+88h] [rbp-D8h]
  int v1145[2]; // [rsp+90h] [rbp-D0h]
  int v1146; // [rsp+90h] [rbp-D0h]
  bool v1147; // [rsp+A0h] [rbp-C0h]
  int v1148; // [rsp+A8h] [rbp-B8h]
  int v1149; // [rsp+C0h] [rbp-A0h]
  int *v1150; // [rsp+C0h] [rbp-A0h]
  char v1151; // [rsp+E0h] [rbp-80h]
  int v1152; // [rsp+E4h] [rbp-7Ch]
  int v1153; // [rsp+E8h] [rbp-78h] BYREF
  bool v1154; // [rsp+ECh] [rbp-74h]
  unsigned __int8 v1155; // [rsp+EDh] [rbp-73h] BYREF
  struct BOOK *lp; // [rsp+F0h] [rbp-70h] BYREF
  struct IMsoOLDocument *v1157; // [rsp+F8h] [rbp-68h] BYREF
  wchar_t *v1158; // [rsp+100h] [rbp-60h]
  bool v1159; // [rsp+108h] [rbp-58h]
  wchar_t *v1160; // [rsp+110h] [rbp-50h]
  struct IMsoOLDocument **v1161; // [rsp+118h] [rbp-48h]
  char v1162; // [rsp+120h] [rbp-40h]
  char v1163; // [rsp+121h] [rbp-3Fh]
  char v1164; // [rsp+122h] [rbp-3Eh]
  bool v1165; // [rsp+123h] [rbp-3Dh]
  int v1166; // [rsp+124h] [rbp-3Ch] BYREF
  struct STM *v1167; // [rsp+128h] [rbp-38h] BYREF
  char v1168; // [rsp+130h] [rbp-30h]
  char v1169; // [rsp+131h] [rbp-2Fh]
  char v1170; // [rsp+132h] [rbp-2Eh]
  int v1171; // [rsp+134h] [rbp-2Ch]
  int v1172; // [rsp+138h] [rbp-28h] BYREF
  bool v1173; // [rsp+13Ch] [rbp-24h]
  char v1174; // [rsp+13Dh] [rbp-23h]
  bool v1175; // [rsp+13Eh] [rbp-22h]
  bool v1176; // [rsp+13Fh] [rbp-21h] BYREF
  int v1177; // [rsp+140h] [rbp-20h] BYREF
  int v1178; // [rsp+144h] [rbp-1Ch]
  __int64 v1179; // [rsp+148h] [rbp-18h] BYREF
  bool v1180; // [rsp+150h] [rbp-10h]
  bool v1181; // [rsp+151h] [rbp-Fh]
  bool v1182; // [rsp+152h] [rbp-Eh]
  bool v1183; // [rsp+153h] [rbp-Dh]
  char v1184; // [rsp+154h] [rbp-Ch]
  unsigned int v1185; // [rsp+158h] [rbp-8h]
  char v1186; // [rsp+15Ch] [rbp-4h]
  int v1187; // [rsp+160h] [rbp+0h] BYREF
  char v1188; // [rsp+164h] [rbp+4h]
  bool v1189; // [rsp+165h] [rbp+5h]
  char v1190; // [rsp+168h] [rbp+8h] BYREF
  char v1191; // [rsp+169h] [rbp+9h]
  bool v1192[4]; // [rsp+16Ch] [rbp+Ch] BYREF
  bool v1193; // [rsp+170h] [rbp+10h] BYREF
  int v1194; // [rsp+174h] [rbp+14h] BYREF
  int v1195; // [rsp+178h] [rbp+18h] BYREF
  unsigned int v1196; // [rsp+17Ch] [rbp+1Ch] BYREF
  struct BOOK *v1197; // [rsp+180h] [rbp+20h] BYREF
  bool v1198; // [rsp+188h] [rbp+28h] BYREF
  char v1199; // [rsp+189h] [rbp+29h]
  bool v1200; // [rsp+18Ah] [rbp+2Ah]
  unsigned __int8 v1201; // [rsp+18Bh] [rbp+2Bh]
  char v1202; // [rsp+18Ch] [rbp+2Ch]
  bool v1203; // [rsp+18Dh] [rbp+2Dh] BYREF
  bool v1204; // [rsp+18Eh] [rbp+2Eh] BYREF
  char v1205; // [rsp+18Fh] [rbp+2Fh] BYREF
  char v1206; // [rsp+190h] [rbp+30h] BYREF
  bool v1207; // [rsp+191h] [rbp+31h] BYREF
  char v1208; // [rsp+194h] [rbp+34h] BYREF
  char v1209; // [rsp+195h] [rbp+35h]
  int v1210; // [rsp+198h] [rbp+38h]
  char v1211; // [rsp+19Ch] [rbp+3Ch]
  bool v1212; // [rsp+19Dh] [rbp+3Dh] BYREF
  XlsActivity *v1213; // [rsp+1A0h] [rbp+40h] BYREF
  int v1214; // [rsp+1A8h] [rbp+48h]
  struct STGI *v1215; // [rsp+1B0h] [rbp+50h]
  int v1216; // [rsp+1B8h] [rbp+58h] BYREF
  int v1217; // [rsp+1BCh] [rbp+5Ch]
  int v1218; // [rsp+1C0h] [rbp+60h] BYREF
  int v1219; // [rsp+1C4h] [rbp+64h] BYREF
  struct ENV *v1220; // [rsp+1C8h] [rbp+68h]
  bool v1221; // [rsp+1D0h] [rbp+70h] BYREF
  int v1222; // [rsp+1D4h] [rbp+74h] BYREF
  int v1223; // [rsp+1D8h] [rbp+78h] BYREF
  int v1224; // [rsp+1E0h] [rbp+80h]
  bool v1225; // [rsp+1E8h] [rbp+88h]
  char v1226; // [rsp+1E9h] [rbp+89h]
  char v1227; // [rsp+1EAh] [rbp+8Ah] BYREF
  char v1228; // [rsp+1EBh] [rbp+8Bh] BYREF
  int v1229; // [rsp+1ECh] [rbp+8Ch] BYREF
  int v1230; // [rsp+1F0h] [rbp+90h] BYREF
  int v1231; // [rsp+1F4h] [rbp+94h]
  unsigned int v1232; // [rsp+1F8h] [rbp+98h] BYREF
  wchar_t *v1233; // [rsp+200h] [rbp+A0h]
  char v1234[8]; // [rsp+208h] [rbp+A8h] BYREF
  int v1235; // [rsp+210h] [rbp+B0h] BYREF
  int v1236; // [rsp+218h] [rbp+B8h]
  _BYTE *v1237; // [rsp+220h] [rbp+C0h]
  BOOL v1238; // [rsp+228h] [rbp+C8h]
  int v1239; // [rsp+230h] [rbp+D0h]
  int v1240; // [rsp+234h] [rbp+D4h] BYREF
  _BYTE v1241[4]; // [rsp+238h] [rbp+D8h] BYREF
  unsigned int v1242; // [rsp+23Ch] [rbp+DCh]
  int v1243; // [rsp+240h] [rbp+E0h] BYREF
  void *v1244; // [rsp+248h] [rbp+E8h] BYREF
  struct IMsoOLDocument **v1245; // [rsp+250h] [rbp+F0h]
  struct IMsoPKMClient *v1246; // [rsp+258h] [rbp+F8h] BYREF
  int v1247; // [rsp+260h] [rbp+100h]
  int v1248; // [rsp+264h] [rbp+104h] BYREF
  int v1249; // [rsp+268h] [rbp+108h]
  int v1250; // [rsp+26Ch] [rbp+10Ch] BYREF
  struct IMsoDocumentEncryptor *v1251; // [rsp+270h] [rbp+110h] BYREF
  struct IMsoOpTimer *v1252; // [rsp+278h] [rbp+118h] BYREF
  HANDLE hObject; // [rsp+280h] [rbp+120h] BYREF
  int v1254; // [rsp+288h] [rbp+128h]
  _BYTE v1255[2]; // [rsp+28Ch] [rbp+12Ch] BYREF
  __int16 v1256; // [rsp+28Eh] [rbp+12Eh] BYREF
  unsigned int v1257; // [rsp+290h] [rbp+130h] BYREF
  BOOL v1258; // [rsp+294h] [rbp+134h]
  int v1259; // [rsp+298h] [rbp+138h] BYREF
  int v1260; // [rsp+29Ch] [rbp+13Ch] BYREF
  int v1261; // [rsp+2A0h] [rbp+140h] BYREF
  int v1262; // [rsp+2A4h] [rbp+144h] BYREF
  int v1263; // [rsp+2A8h] [rbp+148h] BYREF
  int v1264; // [rsp+2ACh] [rbp+14Ch] BYREF
  __int64 v1265; // [rsp+2B0h] [rbp+150h] BYREF
  struct XLXMLMAP *v1266; // [rsp+2B8h] [rbp+158h] BYREF
  const wchar_t *v1267; // [rsp+2C0h] [rbp+160h]
  struct SH *v1268; // [rsp+2C8h] [rbp+168h]
  struct REVERT *v1269; // [rsp+2D0h] [rbp+170h] BYREF
  wchar_t *v1270; // [rsp+2D8h] [rbp+178h]
  int v1271; // [rsp+2E0h] [rbp+180h] BYREF
  __int64 v1272; // [rsp+2E8h] [rbp+188h] BYREF
  struct VersionHistoryWindowParams *v1273; // [rsp+2F0h] [rbp+190h]
  BKORWS *v1274; // [rsp+2F8h] [rbp+198h]
  struct WNX *v1275; // [rsp+300h] [rbp+1A0h]
  struct IMsoUrl *v1276; // [rsp+308h] [rbp+1A8h] BYREF
  int v1277; // [rsp+310h] [rbp+1B0h] BYREF
  int v1278; // [rsp+314h] [rbp+1B4h] BYREF
  int v1279; // [rsp+318h] [rbp+1B8h] BYREF
  int v1280; // [rsp+31Ch] [rbp+1BCh]
  int v1281; // [rsp+320h] [rbp+1C0h] BYREF
  int v1282; // [rsp+324h] [rbp+1C4h] BYREF
  int v1283; // [rsp+328h] [rbp+1C8h] BYREF
  int v1284; // [rsp+32Ch] [rbp+1CCh] BYREF
  int v1285; // [rsp+330h] [rbp+1D0h] BYREF
  int v1286; // [rsp+334h] [rbp+1D4h] BYREF
  int v1287; // [rsp+338h] [rbp+1D8h] BYREF
  int v1288; // [rsp+33Ch] [rbp+1DCh] BYREF
  int v1289; // [rsp+340h] [rbp+1E0h] BYREF
  int v1290; // [rsp+344h] [rbp+1E4h] BYREF
  int v1291; // [rsp+348h] [rbp+1E8h] BYREF
  int v1292; // [rsp+34Ch] [rbp+1ECh] BYREF
  struct IStorage *v1293; // [rsp+350h] [rbp+1F0h] BYREF
  wchar_t *Src; // [rsp+358h] [rbp+1F8h]
  char v1295[8]; // [rsp+360h] [rbp+200h] BYREF
  struct IMemHeap *v1296; // [rsp+368h] [rbp+208h]
  SH *v1297; // [rsp+370h] [rbp+210h]
  __int64 v1298; // [rsp+378h] [rbp+218h]
  struct IMsoOLDocument *v1299; // [rsp+380h] [rbp+220h] BYREF
  struct IMemHeap *v1300; // [rsp+388h] [rbp+228h] BYREF
  __int64 v1301; // [rsp+390h] [rbp+230h]
  struct BOOK *v1302; // [rsp+398h] [rbp+238h]
  struct SH *v1303; // [rsp+3A0h] [rbp+240h]
  int v1304; // [rsp+3A8h] [rbp+248h] BYREF
  _BYTE v1305[128]; // [rsp+3B0h] [rbp+250h] BYREF
  struct IStream *v1306; // [rsp+430h] [rbp+2D0h] BYREF
  struct STM *v1307; // [rsp+438h] [rbp+2D8h] BYREF
  unsigned __int64 v1308; // [rsp+440h] [rbp+2E0h]
  char v1309[8]; // [rsp+448h] [rbp+2E8h] BYREF
  char v1310[8]; // [rsp+450h] [rbp+2F0h] BYREF
  __int64 v1311; // [rsp+458h] [rbp+2F8h] BYREF
  struct IStream *v1312; // [rsp+460h] [rbp+300h] BYREF
  _BYTE v1313[40]; // [rsp+468h] [rbp+308h] BYREF
  int v1314; // [rsp+490h] [rbp+330h] BYREF
  int v1315; // [rsp+494h] [rbp+334h]
  int v1316; // [rsp+498h] [rbp+338h]
  int v1317; // [rsp+49Ch] [rbp+33Ch] BYREF
  int v1318; // [rsp+4A0h] [rbp+340h]
  int v1319; // [rsp+4A4h] [rbp+344h] BYREF
  unsigned int v1320; // [rsp+4A8h] [rbp+348h] BYREF
  int v1321; // [rsp+4ACh] [rbp+34Ch] BYREF
  int v1322; // [rsp+4B0h] [rbp+350h]
  int v1323; // [rsp+4B4h] [rbp+354h] BYREF
  int v1324; // [rsp+4B8h] [rbp+358h] BYREF
  int v1325; // [rsp+4BCh] [rbp+35Ch] BYREF
  int v1326; // [rsp+4C0h] [rbp+360h] BYREF
  int v1327; // [rsp+4C4h] [rbp+364h] BYREF
  Api::ReloadContext *v1328; // [rsp+4C8h] [rbp+368h] BYREF
  char v1329[8]; // [rsp+4D0h] [rbp+370h] BYREF
  struct Api::ReloadContext *v1330; // [rsp+4D8h] [rbp+378h] BYREF
  struct WNX *v1331; // [rsp+4E0h] [rbp+380h]
  struct IMsoOLDocument *v1332; // [rsp+4E8h] [rbp+388h] BYREF
  __int64 v1333; // [rsp+4F0h] [rbp+390h]
  int *v1334; // [rsp+4F8h] [rbp+398h]
  int v1335; // [rsp+500h] [rbp+3A0h] BYREF
  _BYTE v1336[24]; // [rsp+508h] [rbp+3A8h] BYREF
  int v1337; // [rsp+520h] [rbp+3C0h] BYREF
  char v1338[8]; // [rsp+528h] [rbp+3C8h] BYREF
  _BYTE v1339[40]; // [rsp+530h] [rbp+3D0h] BYREF
  _BYTE v1340[40]; // [rsp+558h] [rbp+3F8h] BYREF
  unsigned __int64 v1341; // [rsp+580h] [rbp+420h]
  struct CVINFO *v1342; // [rsp+588h] [rbp+428h] BYREF
  char v1343[8]; // [rsp+590h] [rbp+430h] BYREF
  _BYTE v1344[16]; // [rsp+598h] [rbp+438h] BYREF
  struct SHTI *v1345; // [rsp+5A8h] [rbp+448h] BYREF
  struct IMsoOLDocument *v1346; // [rsp+5B0h] [rbp+450h] BYREF
  char v1347[8]; // [rsp+5B8h] [rbp+458h] BYREF
  _BYTE v1348[40]; // [rsp+5C0h] [rbp+460h] BYREF
  struct IMsoOLDocument *v1349; // [rsp+5E8h] [rbp+488h]
  _BYTE v1350[40]; // [rsp+5F0h] [rbp+490h] BYREF
  _BYTE v1351[32]; // [rsp+618h] [rbp+4B8h] BYREF
  char v1352; // [rsp+638h] [rbp+4D8h] BYREF
  char v1353; // [rsp+63Ch] [rbp+4DCh] BYREF
  char v1354; // [rsp+640h] [rbp+4E0h] BYREF
  char v1355; // [rsp+644h] [rbp+4E4h] BYREF
  char v1356; // [rsp+648h] [rbp+4E8h] BYREF
  char v1357[4]; // [rsp+64Ch] [rbp+4ECh] BYREF
  char v1358; // [rsp+650h] [rbp+4F0h] BYREF
  char v1359; // [rsp+654h] [rbp+4F4h] BYREF
  char v1360[4]; // [rsp+658h] [rbp+4F8h] BYREF
  char v1361[4]; // [rsp+65Ch] [rbp+4FCh] BYREF
  char v1362; // [rsp+660h] [rbp+500h] BYREF
  char v1363[4]; // [rsp+664h] [rbp+504h] BYREF
  char v1364; // [rsp+668h] [rbp+508h] BYREF
  char v1365; // [rsp+66Ch] [rbp+50Ch] BYREF
  char v1366[4]; // [rsp+670h] [rbp+510h] BYREF
  char v1367[4]; // [rsp+674h] [rbp+514h] BYREF
  char v1368[4]; // [rsp+678h] [rbp+518h] BYREF
  char v1369[4]; // [rsp+67Ch] [rbp+51Ch] BYREF
  char v1370[4]; // [rsp+680h] [rbp+520h] BYREF
  int v1371; // [rsp+684h] [rbp+524h]
  int v1372; // [rsp+688h] [rbp+528h]
  int v1373; // [rsp+68Ch] [rbp+52Ch]
  char v1374[4]; // [rsp+690h] [rbp+530h] BYREF
  char v1375[4]; // [rsp+694h] [rbp+534h] BYREF
  char v1376[4]; // [rsp+698h] [rbp+538h] BYREF
  char v1377[4]; // [rsp+69Ch] [rbp+53Ch] BYREF
  char v1378[4]; // [rsp+6A0h] [rbp+540h] BYREF
  char v1379[4]; // [rsp+6A4h] [rbp+544h] BYREF
  char v1380[4]; // [rsp+6A8h] [rbp+548h] BYREF
  char v1381[4]; // [rsp+6ACh] [rbp+54Ch] BYREF
  char v1382[4]; // [rsp+6B0h] [rbp+550h] BYREF
  char v1383[4]; // [rsp+6B4h] [rbp+554h] BYREF
  char v1384[4]; // [rsp+6B8h] [rbp+558h] BYREF
  char v1385[4]; // [rsp+6BCh] [rbp+55Ch] BYREF
  char v1386[4]; // [rsp+6C0h] [rbp+560h] BYREF
  char v1387[4]; // [rsp+6C4h] [rbp+564h] BYREF
  char v1388[4]; // [rsp+6C8h] [rbp+568h] BYREF
  char v1389[4]; // [rsp+6CCh] [rbp+56Ch] BYREF
  char v1390[4]; // [rsp+6D0h] [rbp+570h] BYREF
  char v1391[4]; // [rsp+6D4h] [rbp+574h] BYREF
  char v1392[4]; // [rsp+6D8h] [rbp+578h] BYREF
  char v1393[4]; // [rsp+6DCh] [rbp+57Ch] BYREF
  char v1394[4]; // [rsp+6E0h] [rbp+580h] BYREF
  char v1395[4]; // [rsp+6E4h] [rbp+584h] BYREF
  char v1396[4]; // [rsp+6E8h] [rbp+588h] BYREF
  char v1397; // [rsp+6ECh] [rbp+58Ch] BYREF
  char v1398[4]; // [rsp+6F0h] [rbp+590h] BYREF
  char v1399[4]; // [rsp+6F4h] [rbp+594h] BYREF
  char v1400[4]; // [rsp+6F8h] [rbp+598h] BYREF
  char v1401[4]; // [rsp+6FCh] [rbp+59Ch] BYREF
  char v1402[4]; // [rsp+700h] [rbp+5A0h] BYREF
  char v1403[4]; // [rsp+704h] [rbp+5A4h] BYREF
  char v1404[4]; // [rsp+708h] [rbp+5A8h] BYREF
  char v1405[4]; // [rsp+70Ch] [rbp+5ACh] BYREF
  char v1406[4]; // [rsp+710h] [rbp+5B0h] BYREF
  char v1407[4]; // [rsp+714h] [rbp+5B4h] BYREF
  char v1408[4]; // [rsp+718h] [rbp+5B8h] BYREF
  char v1409[4]; // [rsp+71Ch] [rbp+5BCh] BYREF
  char v1410[4]; // [rsp+720h] [rbp+5C0h] BYREF
  char v1411[4]; // [rsp+724h] [rbp+5C4h] BYREF
  char v1412[4]; // [rsp+728h] [rbp+5C8h] BYREF
  char v1413[4]; // [rsp+72Ch] [rbp+5CCh] BYREF
  char v1414[4]; // [rsp+730h] [rbp+5D0h] BYREF
  char v1415[4]; // [rsp+734h] [rbp+5D4h] BYREF
  char v1416[4]; // [rsp+738h] [rbp+5D8h] BYREF
  char v1417[4]; // [rsp+73Ch] [rbp+5DCh] BYREF
  char v1418[4]; // [rsp+740h] [rbp+5E0h] BYREF
  char v1419[4]; // [rsp+744h] [rbp+5E4h] BYREF
  char v1420[4]; // [rsp+748h] [rbp+5E8h] BYREF
  char v1421[4]; // [rsp+74Ch] [rbp+5ECh] BYREF
  char v1422[4]; // [rsp+750h] [rbp+5F0h] BYREF
  char v1423[4]; // [rsp+754h] [rbp+5F4h] BYREF
  char v1424[4]; // [rsp+758h] [rbp+5F8h] BYREF
  char v1425[4]; // [rsp+75Ch] [rbp+5FCh] BYREF
  char v1426[4]; // [rsp+760h] [rbp+600h] BYREF
  char v1427[4]; // [rsp+764h] [rbp+604h] BYREF
  char v1428[4]; // [rsp+768h] [rbp+608h] BYREF
  char v1429[4]; // [rsp+76Ch] [rbp+60Ch] BYREF
  char v1430[4]; // [rsp+770h] [rbp+610h] BYREF
  char v1431[4]; // [rsp+774h] [rbp+614h] BYREF
  void ***v1432; // [rsp+778h] [rbp+618h] BYREF
  char v1433[8]; // [rsp+780h] [rbp+620h] BYREF
  char v1434[8]; // [rsp+788h] [rbp+628h] BYREF
  __int64 v1435; // [rsp+790h] [rbp+630h] BYREF
  struct XLExpressionService *v1436; // [rsp+798h] [rbp+638h] BYREF
  _BYTE *v1437; // [rsp+7A0h] [rbp+640h] BYREF
  char v1438[8]; // [rsp+7A8h] [rbp+648h] BYREF
  struct IMsoOLDocument *v1439; // [rsp+7B0h] [rbp+650h] BYREF
  struct SH *v1440; // [rsp+7B8h] [rbp+658h] BYREF
  struct IMemHeap *v1441; // [rsp+7C0h] [rbp+660h] BYREF
  __int64 v1442; // [rsp+7C8h] [rbp+668h]
  struct ClpLoadContext *Context; // [rsp+7D0h] [rbp+670h]
  __int64 v1444; // [rsp+7D8h] [rbp+678h]
  __int64 v1445; // [rsp+7E0h] [rbp+680h]
  struct IMsoOLDocument *v1446; // [rsp+7E8h] [rbp+688h]
  __int64 v1447; // [rsp+7F0h] [rbp+690h]
  __int64 v1448; // [rsp+7F8h] [rbp+698h]
  struct SH *v1449; // [rsp+800h] [rbp+6A0h]
  _QWORD v1450[2]; // [rsp+808h] [rbp+6A8h] BYREF
  const char *v1451; // [rsp+818h] [rbp+6B8h] BYREF
  struct SHTI *v1452; // [rsp+820h] [rbp+6C0h] BYREF
  char v1453[4]; // [rsp+828h] [rbp+6C8h] BYREF
  char v1454[4]; // [rsp+82Ch] [rbp+6CCh] BYREF
  char v1455[4]; // [rsp+830h] [rbp+6D0h] BYREF
  char v1456[4]; // [rsp+834h] [rbp+6D4h] BYREF
  char v1457; // [rsp+838h] [rbp+6D8h] BYREF
  char v1458; // [rsp+83Ch] [rbp+6DCh] BYREF
  char v1459; // [rsp+840h] [rbp+6E0h] BYREF
  char v1460[4]; // [rsp+844h] [rbp+6E4h] BYREF
  char v1461; // [rsp+848h] [rbp+6E8h] BYREF
  _BYTE v1462[40]; // [rsp+850h] [rbp+6F0h] BYREF
  char v1463; // [rsp+878h] [rbp+718h] BYREF
  int *v1464; // [rsp+880h] [rbp+720h] BYREF
  wchar_t *v1465; // [rsp+888h] [rbp+728h] BYREF
  int v1466; // [rsp+890h] [rbp+730h]
  struct SH *v1467; // [rsp+898h] [rbp+738h]
  int v1468; // [rsp+8A0h] [rbp+740h]
  void *v1469; // [rsp+8A8h] [rbp+748h]
  struct IMsoOLDocument *v1470; // [rsp+8B0h] [rbp+750h]
  BOOL v1471; // [rsp+8B8h] [rbp+758h]
  unsigned int v1472; // [rsp+8BCh] [rbp+75Ch]
  BOOL v1473; // [rsp+8C0h] [rbp+760h]
  int v1474; // [rsp+8C8h] [rbp+768h]
  struct ISlicerView *v1475; // [rsp+8D0h] [rbp+770h]
  wchar_t *v1476; // [rsp+8D8h] [rbp+778h]
  bool v1477; // [rsp+8E0h] [rbp+780h]
  bool v1478; // [rsp+8E1h] [rbp+781h]
  bool v1479; // [rsp+8E2h] [rbp+782h]
  wchar_t *v1480; // [rsp+8E8h] [rbp+788h]
  _BYTE v1481[40]; // [rsp+8F0h] [rbp+790h] BYREF
  _BYTE v1482[40]; // [rsp+918h] [rbp+7B8h] BYREF
  _BYTE v1483[24]; // [rsp+940h] [rbp+7E0h] BYREF
  _BYTE v1484[24]; // [rsp+958h] [rbp+7F8h] BYREF
  _BYTE v1485[56]; // [rsp+970h] [rbp+810h] BYREF
  _BYTE v1486[16]; // [rsp+9A8h] [rbp+848h] BYREF
  _BYTE v1487[24]; // [rsp+9B8h] [rbp+858h] BYREF
  _BYTE v1488[24]; // [rsp+9D0h] [rbp+870h] BYREF
  _BYTE v1489[24]; // [rsp+9E8h] [rbp+888h] BYREF
  _BYTE v1490[24]; // [rsp+A00h] [rbp+8A0h] BYREF
  _BYTE v1491[40]; // [rsp+A18h] [rbp+8B8h] BYREF
  __int128 v1492; // [rsp+A40h] [rbp+8E0h]
  __int128 v1493; // [rsp+A50h] [rbp+8F0h]
  __int128 v1494; // [rsp+A60h] [rbp+900h]
  __int128 v1495; // [rsp+A70h] [rbp+910h]
  __int128 v1496; // [rsp+A80h] [rbp+920h]
  __int128 v1497; // [rsp+A90h] [rbp+930h]
  __int128 v1498; // [rsp+AA0h] [rbp+940h]
  __int128 v1499; // [rsp+AB0h] [rbp+950h]
  int *v1500; // [rsp+AC0h] [rbp+960h]
  char v1501[8]; // [rsp+AC8h] [rbp+968h] BYREF
  _BYTE v1502[24]; // [rsp+AD0h] [rbp+970h] BYREF
  _BYTE v1503[24]; // [rsp+AE8h] [rbp+988h] BYREF
  _BYTE v1504[24]; // [rsp+B00h] [rbp+9A0h] BYREF
  _BYTE v1505[24]; // [rsp+B18h] [rbp+9B8h] BYREF
  wchar_t *v1506; // [rsp+B30h] [rbp+9D0h]
  __int128 v1507; // [rsp+B40h] [rbp+9E0h] BYREF
  _BYTE v1508[16]; // [rsp+B50h] [rbp+9F0h] BYREF
  _BYTE v1509[40]; // [rsp+B60h] [rbp+A00h] BYREF
  _BYTE v1510[40]; // [rsp+B88h] [rbp+A28h] BYREF
  _BYTE v1511[40]; // [rsp+BB0h] [rbp+A50h] BYREF
  _BYTE v1512[48]; // [rsp+BD8h] [rbp+A78h] BYREF
  _OWORD v1513[2]; // [rsp+C08h] [rbp+AA8h] BYREF
  __int64 v1514; // [rsp+C28h] [rbp+AC8h]
  _BYTE v1515[48]; // [rsp+C30h] [rbp+AD0h] BYREF
  _BYTE v1516[64]; // [rsp+C60h] [rbp+B00h] BYREF
  _BYTE v1517[24]; // [rsp+CA0h] [rbp+B40h] BYREF
  _BYTE v1518[24]; // [rsp+CB8h] [rbp+B58h] BYREF
  _BYTE v1519[80]; // [rsp+CD0h] [rbp+B70h] BYREF
  _QWORD v1520[12]; // [rsp+D20h] [rbp+BC0h] BYREF
  _QWORD v1521[12]; // [rsp+D80h] [rbp+C20h] BYREF
  char v1522[16]; // [rsp+DE0h] [rbp+C80h] BYREF
  char v1523[16]; // [rsp+DF0h] [rbp+C90h] BYREF
  _BYTE v1524[160]; // [rsp+E00h] [rbp+CA0h] BYREF
  _BYTE v1525[40]; // [rsp+EA0h] [rbp+D40h] BYREF
  _BYTE v1526[40]; // [rsp+EC8h] [rbp+D68h] BYREF
  _BYTE v1527[40]; // [rsp+EF0h] [rbp+D90h] BYREF
  _BYTE v1528[56]; // [rsp+F18h] [rbp+DB8h] BYREF
  _BYTE v1529[128]; // [rsp+F50h] [rbp+DF0h] BYREF
  _BYTE v1530[48]; // [rsp+FD0h] [rbp+E70h] BYREF
  _OWORD v1531[8]; // [rsp+1000h] [rbp+EA0h] BYREF
  int *v1532; // [rsp+1080h] [rbp+F20h]
  char v1533; // [rsp+1088h] [rbp+F28h]
  char v1534[32]; // [rsp+1090h] [rbp+F30h] BYREF
  char v1535[32]; // [rsp+10B0h] [rbp+F50h] BYREF
  char v1536[32]; // [rsp+10D0h] [rbp+F70h] BYREF
  char v1537[32]; // [rsp+10F0h] [rbp+F90h] BYREF
  _BYTE v1538[1584]; // [rsp+1110h] [rbp+FB0h] BYREF
  _BYTE v1539[8448]; // [rsp+1740h] [rbp+15E0h] BYREF
  _BYTE v1540[2784]; // [rsp+3840h] [rbp+36E0h] BYREF
  int v1541; // [rsp+4320h] [rbp+41C0h] BYREF
  int v1542; // [rsp+4324h] [rbp+41C4h]
  wchar_t v1543[2086]; // [rsp+4330h] [rbp+41D0h] BYREF
  wchar_t v1544[2090]; // [rsp+537Ch] [rbp+521Ch] BYREF
  struct ISlicerView *v1545; // [rsp+63D0h] [rbp+6270h]
  _BYTE v1546[40]; // [rsp+7430h] [rbp+72D0h] BYREF
  _BYTE v1547[24]; // [rsp+7458h] [rbp+72F8h] BYREF
  char v1548[24]; // [rsp+7470h] [rbp+7310h] BYREF
  unsigned int v1549; // [rsp+7488h] [rbp+7328h]
  unsigned int v1550; // [rsp+748Ch] [rbp+732Ch]
  __int64 v1551; // [rsp+74C0h] [rbp+7360h] BYREF
  int v1552; // [rsp+74C8h] [rbp+7368h]
  jmp_buf Buf; // [rsp+74D0h] [rbp+7370h] BYREF
  __int64 v1554; // [rsp+75D0h] [rbp+7470h] BYREF
  int v1555; // [rsp+75D8h] [rbp+7478h]
  jmp_buf v1556; // [rsp+75E0h] [rbp+7480h] BYREF
  __int64 v1557; // [rsp+76E0h] [rbp+7580h] BYREF
  int v1558; // [rsp+76E8h] [rbp+7588h]
  jmp_buf v1559; // [rsp+76F0h] [rbp+7590h] BYREF
  __int64 v1560; // [rsp+77F0h] [rbp+7690h] BYREF
  int v1561; // [rsp+77F8h] [rbp+7698h]
  jmp_buf v1562; // [rsp+7800h] [rbp+76A0h] BYREF
  _DWORD v1563[196]; // [rsp+7900h] [rbp+77A0h] BYREF
  _BYTE v1564[4720]; // [rsp+7C10h] [rbp+7AB0h] BYREF
  _BYTE v1565[336]; // [rsp+8E80h] [rbp+8D20h] BYREF
  wchar_t v1566[16]; // [rsp+8FD0h] [rbp+8E70h] BYREF
  wchar_t v1567; // [rsp+8FF0h] [rbp+8E90h] BYREF
  wchar_t v1568[263]; // [rsp+8FF2h] [rbp+8E92h] BYREF
  wchar_t v1569[16]; // [rsp+9200h] [rbp+90A0h] BYREF
  wchar_t v1570[264]; // [rsp+9220h] [rbp+90C0h] BYREF
  wchar_t v1571[256]; // [rsp+9430h] [rbp+92D0h] BYREF
  _BYTE v1572[528]; // [rsp+9630h] [rbp+94D0h] BYREF
  wchar_t v1573[256]; // [rsp+9840h] [rbp+96E0h] BYREF
  wchar_t v1574[256]; // [rsp+9A40h] [rbp+98E0h] BYREF
  wchar_t v1575[256]; // [rsp+9C40h] [rbp+9AE0h] BYREF
  wchar_t v1576[264]; // [rsp+9E40h] [rbp+9CE0h] BYREF
  wchar_t v1577[256]; // [rsp+A050h] [rbp+9EF0h] BYREF
  wchar_t String1[2088]; // [rsp+A250h] [rbp+A0F0h] BYREF
  char v1579[528]; // [rsp+B2A0h] [rbp+B140h] BYREF
  wchar_t v1580; // [rsp+B4B0h] [rbp+B350h] BYREF
  _BYTE v1581[4174]; // [rsp+B4B2h] [rbp+B352h] BYREF
  wchar_t v1582[2088]; // [rsp+C500h] [rbp+C3A0h] BYREF
  wchar_t v1583[4112]; // [rsp+D550h] [rbp+D3F0h] BYREF

  v21 = a15;
  v22 = a18;
  v23 = a20;
  v1161 = a9;
  v1245 = a9;
  v1270 = a13;
  v1445 = a14;
  v1267 = a17;
  v1273 = a19;
  v1242 = 0;
  v1160 = a1;
  Src = a1;
  v1224 = a2;
  v1191 = 1;
  v1214 = a4;
  v1333 = a6;
  v1274 = a15;
  v1296 = a18;
  v1334 = a20;
  sub_1402DACDC();
  v1209 = 1;
  v1351[24] = 0;
  v24 = Mso::AB::Optimized::FeatureGate::operator bool(&byte_143FDFC20);
  v25 = a16;
  if ( v24 )
  {
    v1228 = 1;
    v1321 = 0;
    std::optional<XlSecurity::XllTelemetry>::~optional<XlSecurity::XllTelemetry>(v1351);
    std::_Optional_construct_base<XlSecurity::XllTelemetry>::_Construct<enum XlSecurity::XllTelemetry::Entry,bool>(
      v1351,
      &v1321,
      &v1228);
    v26 = (Mso::Telemetry::Activity *)std::optional<XlSecurity::XllTelemetry>::operator->(v1351);
    v27 = Mso::Telemetry::Activity::DataFields(v26);
    Mso::Telemetry::IDataFieldCollection::Add<int>(v27, "LoadReason", v25, 4);
  }
  v1192[1] = 0;
  if ( (unsigned __int8)((__int64 (*)(void))CircularReferenceTailValue::FGetFlagsShadowBag)() )
  {
    std::_Optional_destruct_base<SecuritySettings::ExternalLinks::TrustedLocationCacheScope,0>::~_Optional_destruct_base<SecuritySettings::ExternalLinks::TrustedLocationCacheScope,0>(v1192);
    std::_Optional_construct_base<SecuritySettings::ExternalLinks::TrustedLocationCacheScope>::_Construct<>(v1192);
  }
  v1159 = 0;
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
  v1153 = 0;
  v1170 = 0;
  v1262 = 0;
  v1269 = 0;
  v1169 = 0;
  v1297 = 0;
  v1268 = 0;
  v1275 = 0;
  v1331 = 0;
  v1266 = 0;
  v1223 = 0;
  lp = 0;
  v1188 = 0;
  v1163 = 0;
  v1292 = 0;
  v1232 = 0;
  v1217 = 0;
  v1230 = 0;
  v1551 = 0;
  v1172 = v29;
  v1318 = a10 & 1;
  v1194 = 256;
  v1322 = a10 & 2;
  v1552 = -1;
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
  v1249 = v31;
  if ( (v30 & 0x10) != 0
    || *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1712LL)
    || (v32 = 0, v1172) )
  {
    v32 = FOsrc() == 0;
  }
  v1280 = v32;
  hObject = (HANDLE)-1LL;
  v1173 = 0;
  v1218 = 0;
  v1162 = 0;
  v1181 = 0;
  v1246 = 0;
  v1260 = 0;
  v1185 = 0;
  v1180 = 0;
  v1174 = 0;
  v1299 = 0;
  v1189 = 0;
  v1183 = 0;
  v1201 = 0;
  v1175 = 0;
  memset_0(v1572, 0, 0x202u);
  v1210 = 1;
  v1281 = 0;
  v1264 = 0;
  v1225 = a4 != 0;
  v1211 = 0;
  v1251 = 0;
  v1303 = (struct SH *)65534;
  v1235 = 0;
  v1236 = 0;
  v1237 = 0;
  v1238 = 0;
  v1155 = 0;
  v1195 = 0;
  v1186 = 0;
  v1288 = 0;
  v1165 = 0;
  v1164 = 0;
  v33 = CountBooks();
  LOBYTE(v34) = std::weak_ordering::equivalent;
  v1254 = v33;
  v1250 = -2147467259;
  v1176 = 0;
  v1226 = 0;
  v1221 = 0;
  v1432 = &TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain;
  std::_Deleted_move_assign<std::_Optional_construct_base<CorruptionMetaData>,CorruptionMetaData>::_Deleted_move_assign<std::_Optional_construct_base<CorruptionMetaData>,CorruptionMetaData>(
    v1538,
    v34,
    &v1432);
  v1271 = 0;
  FishbowlTracker::FishbowlTracker((FishbowlTracker *)v1540, 0);
  OpenWorkbooksTracker::OpenWorkbooksTracker((OpenWorkbooksTracker *)v1434);
  v1198 = 1;
  v1193 = 0;
  v1207 = 0;
  v1199 = 0;
  v1184 = 0;
  v1200 = (a10 & 0x100000) != 0;
  OsfOpenScope::OsfOpenScope((OsfOpenScope *)v1485);
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v1298 = 304;
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
  v1229 = 68;
  v42 = v41 >= 0;
  v1187 = 0;
  v1258 = 0;
  v1342 = 0;
  Dw = iUseSentinelFile;
  v1182 = v42;
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
  if ( !v44 && !(unsigned int)FOpenSentinelFile(v1160, 393226, &hObject) )
  {
    *v23 = 0;
LABEL_137:
    OsfOpenScope::~OsfOpenScope((OsfOpenScope *)v1485);
    FishbowlTracker::~FishbowlTracker((FishbowlTracker *)v1540);
    std::_Optional_destruct_base<CorruptionMetaData,0>::~_Optional_destruct_base<CorruptionMetaData,0>(v1538);
    std::_Optional_destruct_base<SecuritySettings::ExternalLinks::TrustedLocationCacheScope,0>::~_Optional_destruct_base<SecuritySettings::ExternalLinks::TrustedLocationCacheScope,0>(v1192);
    std::optional<XlSecurity::XllTelemetry>::~optional<XlSecurity::XllTelemetry>(v1351);
    if ( v1209 )
      sub_141232A50();
    if ( v1191 )
      sub_14240D630(&v1190);
    return 0;
  }
  v45 = (wchar_t *)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
  v1158 = v45;
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
    v1233 = v45;
  }
  else
  {
    v45 = 0;
    v1158 = 0;
    v1233 = 0;
  }
  v1300 = 0;
  v1177 = 0;
  v1263 = 0;
  v1519[64] = 0;
  v1341 = 0;
  v1308 = 0;
  if ( v46 )
  {
    memset(v1513, 0, sizeof(v1513));
    v1514 = 0;
    memset_0(v1564, 0, 0x1268u);
    (*(void (__fastcall **)(void *, struct IMemHeap **, _QWORD))(qword_144012CA0 + 8LL))(&qword_144012CA0, &v1300, 0);
    if ( (int)LoadRecovery::HrInit(
                v45,
                v1300,
                *(unsigned int *)(*(_QWORD *)(*(_QWORD *)(v1298 + *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer)
                                            + 872LL)
                                + 104LL),
                v1564,
                v1513) < 0 )
      v45 = 0;
    v1158 = v45;
    v1233 = v45;
  }
  CchStToStz(v1160, &v1580, 2086);
  v1276 = 0;
  MsoHrCreateUrlSimpleFromUser(&v1276, v1581, 0, 0, 0, 0);
  WriteOpenStartPerfEvent(v1276);
  v1179 = 0;
  v1311 = 0;
  v1272 = 0;
  MeasurementsIdFromPath(v1546, v1581);
  if ( v1161 )
    v47 = *v1161;
  else
    v47 = 0;
  v1506 = &v1580;
  v1507 = *(_OWORD *)RgchView::RgchView(v1522, &v1580);
  v48 = OpenTelemetry::SpotEnsureOpenTelemetry(v1433, &TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain, &v1507, v47);
  Mso::TCntPtr<Mso::IRefCounted>::operator=(&v1179, v48);
  Mso::TCntPtr<IWebAddInOptionalProperties>::~TCntPtr<IWebAddInOptionalProperties>(v1433);
  if ( v22 )
  {
    v49 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
    Mso::TCntPtr<OpenFileEventTimings>::operator=<OpenFileEventTimings,void>(
      (char *)v22 + 2824,
      *(_QWORD *)(v49 + 30016));
  }
  v50 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
  v1371 = 520926677;
  v51 = (LXBASE *)(v50 + 576);
  if ( XlDisplayElementInfoAll::FXlClient(v52) && *((_DWORD *)v51 + 7160) == -1 )
    WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v51);
  v53 = (LinkedEntityManager *)Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
  v1213 = LinkedEntityManager::PRefreshManager(v53);
  v1227 = 1;
  v1256 = 1;
  v54 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
  v55 = PAllocateObjectOrNull<Measurements::StartOrContinueCapture,Measurements::Identifier const &,enum Measurements::Scenario,bool>(
          (unsigned int)&TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain,
          0,
          v54 + 328,
          (unsigned int)&v1256,
          (__int64)&v1227);
  std::unique_ptr<Measurements::StartOrContinueCapture,HeapDeleter<Measurements::StartOrContinueCapture>>::reset(
    &v1272,
    v55);
  v56 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
  v1372 = 520926676;
  WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo((LXBASE *)(v56 + 576));
  LODWORD(v1499) = v25;
  *(_QWORD *)&v1492 = &v1272;
  v57 = 128;
  *((_QWORD *)&v1492 + 1) = &lp;
  *(_QWORD *)&v1493 = &v1179;
  *((_QWORD *)&v1493 + 1) = &v1213;
  *(_QWORD *)&v1494 = &v1177;
  *((_QWORD *)&v1494 + 1) = &v1153;
  *(_QWORD *)&v1495 = &v1176;
  *((_QWORD *)&v1495 + 1) = v1546;
  *(_QWORD *)&v1496 = &v1155;
  *((_QWORD *)&v1496 + 1) = v1538;
  *(_QWORD *)&v1497 = &v1271;
  *((_QWORD *)&v1497 + 1) = v1540;
  *(_QWORD *)&v1498 = v1434;
  *((_QWORD *)&v1498 + 1) = &v1198;
  *((_QWORD *)&v1499 + 1) = &a10;
  v1500 = &v1172;
  v1531[0] = v1492;
  v1531[1] = v1493;
  v1531[2] = v1494;
  v1531[3] = v1495;
  v1531[4] = v1496;
  v1531[5] = v1497;
  v1531[6] = v1498;
  v1531[7] = v1499;
  v1532 = &v1172;
  LOBYTE(v57) = std::weak_ordering::equivalent;
  v1533 = 1;
  sub_1402DB250(v1524, v57, v1531);
  if ( v1533 )
    sub_1404750A0(v1531);
  LOBYTE(v58) = std::weak_ordering::equivalent;
  std::_Deleted_move_assign<std::_Optional_construct_base<Measurements::MeasureElapsedTime>,Measurements::MeasureElapsedTime>::_Deleted_move_assign<std::_Optional_construct_base<Measurements::MeasureElapsedTime>,Measurements::MeasureElapsedTime>(
    v1512,
    v58,
    &Measurements::MeasurementId::ExcelFileLoad);
  v1252 = 0;
  if ( (int)MsoCreateOpTimer(1, 1, &v1252) >= 0 )
  {
    v59 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1252);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 32LL))(v59);
  }
  v1539[8440] = 0;
  v1435 = *(_QWORD *)v21;
  std::optional<OlDocFilePath>::~optional<OlDocFilePath>(v1539);
  std::_Optional_construct_base<OlDocFilePath>::_Construct<QuickLoadContext *>(v1539, &v1435);
  v60 = v1298;
  v1568[0] = 0;
  v1567 = 0;
  v61 = 7;
  v62 = *(_QWORD *)(v1298 + *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer);
  if ( (*(_DWORD *)(*(_QWORD *)(v62 + 864) + 24LL) & 0x200000) != 0 && !*(_DWORD *)(*(_QWORD *)(v62 + 872) + 104LL) )
  {
    v63 = v1158;
    v1218 = 1;
    if ( v1158 )
      *((_DWORD *)v1158 + 16) |= 4u;
    v64 = *(_QWORD *)(v60 + *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer);
    *(_DWORD *)(*(_QWORD *)(v64 + 872) + 104LL) = (*(_DWORD *)(*(_QWORD *)(v64 + 864) + 24LL) >> 22) & 7;
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v60 + *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer) + 872LL) + 108LL) = 0;
    if ( OSRH::m_vpxlosrea )
    {
      v65 = *(_DWORD *)(*(_QWORD *)OSRH::m_vpxlosrea + 32LL);
      v1180 = (v65 & 0x20000) != 0;
      if ( (v65 & 0x20000) != 0 )
      {
        v1185 = 4;
        if ( (v65 & 0x40000) != 0 )
          v1185 = 6;
      }
    }
    else if ( !*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v60 + *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer) + 872LL)
                         + 104LL)
           && !v1172 )
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
            Mso::Memory::Free((Mso::Memory *)v63, v94);
          }
          if ( v1161 )
          {
            v95 = *v1161;
            v1157 = v95;
            if ( v95 )
            {
              (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v95 + 56LL))(
                v95,
                0xFFFFFFFFLL,
                7);
              v1373 = 594109130;
              OlDocFilePath::FReleaseIOLDoc(&v1157, 1, 1, 0x236962CAu);
            }
          }
          if ( iUseSentinelFile > 0 && hObject != (HANDLE)-1LL )
          {
            CloseHandle(hObject);
            hObject = (HANDLE)-1LL;
          }
          if ( (unsigned int)FHotFix(2) )
          {
            v96 = 63999;
            *(_WORD *)(*(_QWORD *)&UIGLOBALS::UIGLOBALSCONTAINER::m_posi + 1520LL) &= 0xF9FFu;
          }
          if ( v42 )
            Mso::PerfScenario::HrEndScenario(
              (Mso::PerfScenario *)&vmsoperfidOfficeXLFileOpen,
              (const struct Mso::PerfScenario::MsoPerfScenarioId *)v96);
          XlsDiag::LogSetHrCoreTag(-2146827284, 0x17976D2u);
          *v23 = 0;
          std::optional<OlDocFilePath>::~optional<OlDocFilePath>(v1539);
          Mso::TCntPtr<Uxpp::UxppAnnotationsService>::~TCntPtr<Uxpp::UxppAnnotationsService>(&v1252);
          std::_Optional_destruct_base<Measurements::MeasureElapsedTime,0>::~_Optional_destruct_base<Measurements::MeasureElapsedTime,0>(v1512);
          sub_140475070(v1524);
          std::pair<enum Osf::ModifierKeyFlags const,std::wstring>::~pair<enum Osf::ModifierKeyFlags const,std::wstring>(v1546);
          std::unique_ptr<Measurements::StartOrContinueCapture,HeapDeleter<Measurements::StartOrContinueCapture>>::~unique_ptr<Measurements::StartOrContinueCapture,HeapDeleter<Measurements::StartOrContinueCapture>>(&v1272);
          std::unique_ptr<XlsActivity::XlsDetachedActivity,HeapDeleter<XlsActivity::XlsDetachedActivity>>::~unique_ptr<XlsActivity::XlsDetachedActivity,HeapDeleter<XlsActivity::XlsDetachedActivity>>(&v1311);
          Mso::TCntPtr<IWebAddInOptionalProperties>::~TCntPtr<IWebAddInOptionalProperties>(&v1179);
          Mso::TCntPtr<Uxpp::UxppAnnotationsService>::~TCntPtr<Uxpp::UxppAnnotationsService>(&v1276);
          std::optional<NumberConversionSettingsOverride>::~optional<NumberConversionSettingsOverride>(v1519);
          goto LABEL_137;
        }
        if ( MsoDwRegGetDw((const struct _msoreg *)&vmsoridExcelExtractDataFormulas) == 1 )
          v91 = CustomTwoAlertSecBtnDefault(262265, 0, -1161035121, -1161035120);
        else
          v91 = CustomTwoAlert(262265, 0, -1161035121, -1161035120);
        v1180 = 1;
        v560 = v91 == 102;
        v92 = 4;
        if ( v560 )
          v92 = 6;
        v1185 = v92;
        v93 = NtCurrentTeb()->ThreadLocalStoragePointer;
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v60 + *v93) + 872LL) + 104LL) = 2;
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v60 + *v93) + 872LL) + 108LL) = 0;
      }
    }
  }
  v68 = v1158;
  v69 = v1160;
  if ( v1158 )
  {
    v70 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v60 + *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer) + 872LL)
                    + 104LL);
    *(_DWORD *)v1158 = v70;
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
  sub_1402DA650(&v1541, a6, v61);
  v1349 = vpoldocument;
  MaxPathHolder::MaxPathHolder(
    (MaxPathHolder *)v1340,
    (struct IMemHeap *)&TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain,
    259,
    0);
  MaxPathHolder::MaxPathHolder(
    (MaxPathHolder *)v1462,
    (struct IMemHeap *)&TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain,
    259,
    0);
  MaxPathHolder::MaxPathHolder(
    (MaxPathHolder *)v1339,
    (struct IMemHeap *)&TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain,
    259,
    0);
  MaxPathHolder::MaxPathHolder(
    (MaxPathHolder *)v1482,
    (struct IMemHeap *)&TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain,
    259,
    0);
  MaxPathHolder::MaxPathHolder(
    (MaxPathHolder *)v1348,
    (struct IMemHeap *)&TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain,
    259,
    0);
  MaxPathHolder::MaxPathHolder(
    (MaxPathHolder *)v1350,
    (struct IMemHeap *)&TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain,
    259,
    0);
  FileSource::FileSource((FileSource *)v1305, (struct IMemHeap *)&TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain);
  std::_Optional_construct_base<FutureFunctionLabelCreationTracker>::_Optional_construct_base<FutureFunctionLabelCreationTracker>(v1516);
  AutoConversionParameters::AutoConversionParameters((AutoConversionParameters *)v1518);
  std::optional<AutomaticNumberConversionLoadPasteHelper>::optional<AutomaticNumberConversionLoadPasteHelper>(v1344);
  v72 = sub_1402DB5D0(v1255, &v1265);
  sub_1402DB4F0(v1234, v72);
  sub_1402DB510(v1255);
  v73 = 1;
LABEL_79:
  v1231 = 0;
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
  v1178 = 1;
  v75 = *(_QWORD *)(*(_QWORD *)(v60 + *v74) + 1328LL);
  v76 = 0;
  *(_DWORD *)(v75 + 20) = 0;
  if ( *v69 )
    v76 = a7 != 1024;
  v1154 = v76;
  v77 = (struct IMsoOLDocument *)v1161;
  if ( v1161 )
    v77 = *v1161;
  v1157 = v77;
  if ( v1172 || v1155 )
    v1214 = 1;
  v78 = *(TLSW **)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v60);
  v1301 = *((_QWORD *)v78 + 5);
  v1302 = 0;
  v1436 = TLSW::PesExpressionService(v78);
  std::optional<FutureFunctionLabelCreationTracker>::emplace<XLExpressionService *>(v1516, &v1436);
  v79 = FeatureGateCollectionBase<UserVoiceFeatureGates>::Instance();
  if ( (unsigned __int8)FeatureExposure::operator bool(v79 + 56) )
  {
    v1437 = v1518;
    std::optional<AutomaticNumberConversionLoadPasteHelper>::emplace<AutoConversionParameters *>(v1344, &v1437);
  }
  v1151 = 1;
  v80 = *(_QWORD *)(v60 + *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer);
  v1220 = *(struct ENV **)(v80 + 336);
  *(_QWORD *)(v80 + 336) = &v1551;
  v1552 = 36737602;
  v1166 = setjmp(Buf);
  if ( v1166 )
    goto LABEL_1133;
  v81 = (Excel::XlBoot **)NtCurrentTeb()->ThreadLocalStoragePointer;
  if ( !*(_QWORD *)(*(_QWORD *)((char *)*v81 + v60) + 784LL) )
    Excel::XlBoot::InitUserNameCur(*v81);
  v82 = Src;
  v83 = v1224;
  v1160 = Src;
  if ( v1322 && !(unsigned int)FFilenameFromSt(Src, Src, v1224) )
  {
    v1010 = v1233;
    if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL) + 8LL)
        & 1) == 0
      && v1233 )
    {
      LoadRecovery::Destroy((LoadRecovery *)v1233);
      FreeHpst(v1010);
      v1010 = 0;
      v1233 = 0;
    }
    v1153 = 0;
    XlsDiag::LogSetHrCoreTag(-2147024690, 0x17976D4u);
    v1150 = v1334;
    v1148 = v1254;
    v1147 = v1175;
    v1146 = -2147024690;
    v1144 = v1181;
    v1143 = v1302;
    v1141 = v1270;
    v1140 = v1157;
    v1139 = v1159;
    v1138 = v1251;
    v1137 = v1246;
    v1136 = v1195 != 0;
    v1134 = v1220;
    v1132 = v1300;
    v1130 = (struct LoadRecovery *)v1010;
    goto LABEL_2113;
  }
  v68 = v1233;
  v1158 = v1233;
  if ( v1233 )
  {
    v84 = (wchar_t *)XLSBOOK::Plxtab((XLSBOOK *)v1233);
    CchStToSt(v82, v84, 2084);
    MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1462, v82);
  }
  if ( !FileLoad::FProcessDisabledDocument(v82, v1157, v1172 != 0) )
  {
    v114 = -2147024809;
    XlsDiag::LogSetHrCoreTag(-2147024809, 0x17976D5u);
    goto LABEL_2100;
  }
  MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1348, v82);
  v85 = MaxPathHolder::SzPath((MaxPathHolder *)v1348);
  if ( MsoFIsInFileSysWzPersistentName(v85, 0) && wProjLoad != 2 && !(unsigned int)FileExists(v82) )
    FEnsureExtension(v82, v83, 0xFFFFFFFFLL, 50);
  v86 = v1157;
  if ( v1157 )
  {
    (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v1157 + 56LL))(v1157, 1, 9);
    v86 = v1157;
  }
  v87 = v1184;
  v88 = v1214;
  v1168 = v1184;
  v1171 = v1214;
  if ( v1154 )
  {
    v1196 = 2;
    v89 = v86 == 0;
    if ( v86 && (*(unsigned int (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v86 + 208LL))(v86) )
    {
      v1196 = 0;
      v90 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
      OlDocFilePath::IncOpenCount(v90);
    }
    if ( v88 )
    {
      operator|=(&v1196, 1);
    }
    else if ( (a10 & 0x200) != 0 )
    {
      operator|=(&v1196, 8);
    }
    if ( (unsigned int)FFinderFile(v82)
      || vfInstallTemplates
      && *(_DWORD *)(*(_QWORD *)(v60 + *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer) + 1764LL) )
    {
      operator|=(&v1196, 32);
    }
    v98 = FeatureGateCollectionBase<LoadSaveFeatureGates>::Instance();
    if ( (unsigned __int8)Mso::AB::Optimized::FeatureGate::operator bool(v98 + 8) )
    {
      v99 = MaxPathHolder::SzPath((MaxPathHolder *)v1348);
      if ( MsoFIsInFileSysWzPersistentName(v99, 0) )
      {
        v100 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1348);
        if ( (unsigned int)FIsPathAnXll(v100, 1) )
          operator|=(&v1196, 32);
      }
    }
    if ( (a10 & 0x20000) != 0 )
      operator|=(&v1196, 256);
    LODWORD(v1124) = v1196;
    XlsDiag::SendTraceTag(41039177, 187, 100, L"FFileLoadEx: OlDocSetupFlags oldsf = 0x%x", v1124);
    if ( v89 && a16 == 16 && !(unsigned int)FOsrhInTransition() )
      operator|=(&v1196, 512);
    v101 = FeatureGateCollectionBase<ZipItFeatureGates>::Instance();
    if ( (unsigned __int8)Mso::AB::Optimized::FeatureGate::operator bool(v101 + 72) )
      v102 = 1;
    else
      v102 = v87 == 0;
    v103 = v1296;
    if ( v1296 )
    {
      v104 = (ZrtUtility *)MaxPathHolder::SzPath((MaxPathHolder *)v1348);
      if ( ZrtUtility::FCanUseServerOnlyAsyncOpen(v104, v105) && v102 )
        operator|=(&v1196, 1024);
    }
    v106 = TLSW::PesExpressionService(*(TLSW **)(v1298 + *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer));
    v107 = ExpressionService::Pwbkcoll(v106);
    RevisionLatencyOutlierTracker::RevisionLatencyOutlierTracker(v1530, v107, 16);
    v108 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
    v109 = BKORWS::Psh((BKORWS *)&v1179);
    OlDocFilePath::SetOpenTelemetry(v108, v109);
    operator|=(&v1196, 4096);
    v110 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
    v111 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1374, 0x236962C9u);
    v112 = SXVWGEOM::RwFirst(v111);
    v113 = OlDocFilePath::HrSetupAndRetrievePathTitle(
             v110,
             (struct FileSource *)v1305,
             &v1157,
             v82,
             &v1232,
             (enum OlDocSetupFlags *)&v1196,
             v103,
             v112,
             0,
             0);
    v114 = v113;
    if ( v113 < 0 )
      XlsDiag::LogSetHrCoreTag(v113, 0x27C1404u);
    RevisionLatencyOutlierTracker::~RevisionLatencyOutlierTracker((RevisionLatencyOutlierTracker *)v1530);
    v115 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
    if ( (int)OlDocFilePath::COpenCount(v115) > 1 )
      MsoShipAssertTagProc(505205964);
    if ( v1296 )
    {
      v116 = v1157;
      v117 = APPCORE::PmemheapMain((APPCORE *)&vapp);
      v1159 = ZrtUtility::FOpeningAsServerOnlyAsync(v117, v1296, v116, v118);
    }
    if ( v114 < 0 )
    {
      if ( v1157 )
        Mso::DocumentTelemetry::AddAllDocumentTelemetryFieldsToActivity<XlsActivity,IMsoOLDocument,void>(
          v1375,
          v1213,
          v1157,
          0);
    }
    else
    {
      v119 = (ArtUserInterfaceSite *)Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
      v120 = CoauthoringInternals::FCoauthoringFeatureEnabled() && XlAsyncFileIO::FCoauthorableFileIO(v1157);
      ArtUserInterfaceSite::SetCurrentToolLockState(v119, v120);
      v121 = (OpenTelemetry *)Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
      OpenTelemetry::SetPoldoc(v121, v1157);
    }
    v122 = BKORWS::Psh((BKORWS *)&v1179);
    XlFileProtocolManager::SetFallbackReason(v1157, v122);
    if ( v114 < 0
      || (v123 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1539),
          !(unsigned int)OlDocFilePath::CchPath(v123)) )
    {
      if ( v1157 )
      {
        v1332 = v1157;
        (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v1157 + 56LL))(
          v1157,
          0xFFFFFFFFLL,
          7);
        v1016 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
        OlDocFilePath::RecordEventForCloseOldoc(v1016, v1157, 0);
        v1017 = v1245;
        if ( v1245 && *v1245 == v1157 )
        {
          v1018 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1454, 0x236962C8u);
          v1019 = SXVWGEOM::RwFirst(v1018);
          OlDocFilePath::FReleaseIOLDoc(&v1332, 0, 1, v1019);
          *v1017 = v1332;
        }
        else
        {
          v1020 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1455, 0x236962C7u);
          v1021 = SXVWGEOM::RwFirst(v1020);
          OlDocFilePath::FReleaseIOLDoc(&v1332, 0, 1, v1021);
        }
      }
      goto LABEL_2100;
    }
    v124 = (const struct OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
    v125 = FileSource::HrSetOlDocFilePath((FileSource *)v1305, v124);
    v114 = v125;
    if ( v125 < 0 )
    {
      XlsDiag::LogSetHrCoreTag(v125, 0x279F29Cu);
      goto LABEL_2100;
    }
    v126 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
    v127 = OlDocFilePath::StzTitle(v126);
    if ( MaxPathHolder::FExceedsMaxFileName(*v127) )
    {
      Error(655635);
      if ( v1157 )
      {
        (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v1157 + 56LL))(
          v1157,
          0xFFFFFFFFLL,
          7);
        HrRecordEvent(v1157, 0x40000000u, 0);
        v1014 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1453, 0x236962C6u);
        v1015 = SXVWGEOM::RwFirst(v1014);
        OlDocFilePath::FReleaseIOLDoc(&v1157, 1, 1, v1015);
      }
      goto LABEL_2100;
    }
    v128 = XLFileIOMockable::HrSetPoldoc((struct FileSource *)v1305, v1157, v1274, v1213);
    v1152 = v128;
    v114 = v128;
    if ( v128 < 0 )
    {
      XlsDiag::LogSetHrCoreTag(v128, 0x279F29Du);
      goto LABEL_2100;
    }
    v129 = FileSource::StzFilePath((FileSource *)v1305);
    if ( !(unsigned int)FIsPathAnXll(v129, 1) )
    {
      v130 = v1157;
      v131 = APPCORE::PmemheapMain((APPCORE *)&vapp);
      Api::DataLossProtectionSessionManager::NotifyEvent(v131, 0, v130, 0);
    }
    if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 2972LL)
      && v1270
      && *v1270 )
    {
      CchSzToStz(v1270 + 1, &v1567, 257);
    }
    else
    {
      v132 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
      v133 = OlDocFilePath::StzTitle(v132);
      CchStToStz(v133, &v1567, 257);
    }
    MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1348, v82);
    v134 = MaxPathHolder::SzPath((MaxPathHolder *)v1348);
    if ( !MsoFIsInFileSysWzPersistentName(v134, 0) && v1567 > 0xF9u )
    {
      v1567 = 249;
      MakeStStzTruncOK(&v1567, 257);
    }
    v135 = v1157;
    vpoldocument = v1157;
    v1161 = v1245;
    if ( v89 )
    {
      if ( v1245 )
      {
        *v1245 = v1157;
        v135 = v1157;
      }
      else
      {
        v1161 = &v1157;
        v1245 = &v1157;
      }
    }
    if ( v1542 || !(unsigned int)IMsoOLDocument::IsInFileSys(v135) )
    {
      v82 = v1160;
    }
    else
    {
      v1541 |= 0x10u;
      v1257 = 0;
      MaxPathSzPoke::MaxPathSzPoke((MaxPathSzPoke *)v1487, (struct MaxPathHolder *)v1339);
      v1257 = MaxPathSzPoke::CchSzBufferSize((MaxPathSzPoke *)v1487);
      v136 = *(__int64 (__fastcall **)(struct IMsoOLDocument *, const wchar_t *, unsigned int *, __int64))(*(_QWORD *)v1157 + 64LL);
      v137 = AugmentationLoop::TranslateDetectLanguagesArrayAnnotationResponse::SzId((AugmentationLoop::TranslateDetectLanguagesArrayAnnotationResponse *)v1487);
      v138 = v136(v1157, v137, &v1257, 3);
      MaxPathSzPoke::~MaxPathSzPoke((MaxPathSzPoke *)v1487);
      if ( v138 < 0 )
      {
        if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1232LL)
                       + 32LL) )
        {
          v1011 = MaxPathHolder::SzPath((MaxPathHolder *)v1348);
          v1012 = MsoServerErrorTypeGet(0);
          MsoServerErrorAlert(v1012, v1011, 0);
        }
        v114 = v138;
        XlsDiag::LogSetHrCoreTag(v138, 0x26C77DFu);
        goto LABEL_1861;
      }
      v82 = v1160;
      if ( v1257 <= 1 && (int)RootPathWithMph(v1160, (struct MaxPathHolder *)v1339) < 0 )
        MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1339, v82);
    }
    if ( (unsigned __int8)FFlagSet(v1196, 8) )
      v1173 = 1;
  }
  else
  {
    XlsDiag::LogSetHrCoreTag(-2147467259, 0x27C1405u);
    v139 = FileSource::HrSetPoldoc((FileSource *)v1305, v1157, v1274, v1213);
    v1152 = v139;
    v114 = v139;
    if ( v139 < 0 )
      XlsDiag::LogSetHrCoreTag(v139, 0x279F29Eu);
    if ( (unsigned __int8)std::shared_ptr<Mso::ActivityScope::IMsoLoggingScope>::operator bool(&v1179) )
    {
      v140 = (OpenTelemetry *)Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
      OpenTelemetry::SetPoldoc(v140, v1157);
    }
    if ( v114 < 0 )
    {
      OkAlert(196655, v1568);
      v1013 = v1245;
      goto LABEL_2092;
    }
    FileSource::FGetPathname((FileSource *)v1305, v82 + 1, *v82, &v1567, 257);
    v1161 = v1245;
  }
  if ( !(unsigned int)MaxPathHolder::CchLength((MaxPathHolder *)v1339) )
  {
    v141 = FileSource::StzFilePath((FileSource *)v1305);
    MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1339, v141);
  }
  v142 = v1258;
  v1247 = v1258;
  if ( !v1172 )
  {
    if ( (unsigned int)FOsrhInTransition() )
    {
      if ( (a10 & 0x10000) != 0 )
        OSRR::SetFatalOnlyFlag((OSRR *)&v1235);
      goto LABEL_244;
    }
    if ( v1155 )
    {
LABEL_243:
      v1237 = v1572;
      v1238 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                        + 104LL) == 0;
      OSRR::SetCreateNew((OSRR *)&v1235, a10 & 0x400);
      goto LABEL_244;
    }
    v143 = 0;
    CchStToSz(v82, String1, 2084);
    if ( fInIdle && v1157 )
    {
      v144 = 2;
      if ( (int)MsoCchWzLen(String1) <= 2 )
      {
LABEL_229:
        v145 = a10;
        if ( (a10 & 0x80000) != 0 )
        {
          if ( !v1187 || (v146 = (BKORWS *)v1482, v142) )
            v146 = (BKORWS *)v1339;
          v147 = (const wchar_t *)BKORWS::Psh(v146);
          v560 = !FShouldOpenInAppGuard(v147, 0);
          v145 = a10;
          if ( v560 )
          {
            v145 = a10 & 0xFFFFEFFF;
            a10 &= ~0x1000u;
          }
        }
        if ( (v145 & 0x2000) != 0 )
        {
          v144 = 3;
        }
        else if ( (v145 & 0x10000) == 0 )
        {
          v144 = (v145 & 0x1000) != 0;
        }
        if ( v143 )
        {
          v148 = (unsigned int)MsoCchWzLen(String1);
          v149 = String1;
        }
        else
        {
          v148 = *v82;
          v149 = v82 + 1;
        }
        XlProtectionMockable::InitOSRR(&v1235, v144, v149, v148);
        goto LABEL_243;
      }
      if ( !wcsncmp(String1, L"\\\\", 2u)
        && !MsoFReservedWzPersistentName(String1)
        && FIsHttpRedirFile(String1, 0, 0, 0, 0) )
      {
        v143 = MsoFConvertHttpRedirUNCToHttp(String1, String1, 2084) != 0;
      }
    }
    v144 = 2;
    goto LABEL_229;
  }
LABEL_244:
  v150 = v1158;
  if ( v1158 )
  {
    v151 = (const wchar_t *)XLSBOOK::Plxtab((XLSBOOK *)v1158);
    if ( !(unsigned int)FHasPath(v151) )
    {
      v152 = (wchar_t *)XLSBOOK::Plxtab((XLSBOOK *)v150);
      v153 = FileSource::StzFilePath((FileSource *)v1305);
      CchStToSt(v153, v152, 2084);
    }
    if ( !v1280
      && (*((_BYTE *)PivotOperationBase::PSxview((PivotOperationBase *)v150) + 36) & 8) == 0
      && (unsigned int)ObjectModelState::FInCallback((ObjectModelState *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                    + 304LL)
                                                                        + 1200LL)) != 2 )
    {
      v154 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
      if ( (!*(_DWORD *)(*(_QWORD *)(v154 + 1232) + 80LL)
         || (unsigned int)ObjectModelState::FInCallback((ObjectModelState *)(v154 + 1200)) == 2)
        && !(unsigned int)ObjectModelState::FInCallback((ObjectModelState *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                       + 304LL)
                                                                           + 1200LL)) )
      {
        FStartLoadAction(
          2 - (v1249 != 0),
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                    + 104LL),
          (struct LoadRecovery *)v150);
      }
    }
  }
  if ( !v1542 )
  {
    CchStToStz(&v1567, v1570, 257);
    v155 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1339);
    MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1340, v155);
  }
  if ( v1157 )
  {
    v1282 = 0;
    v156 = (*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1157 + 80LL))(v1157);
    XlAsyncFileIO::SpOLDocCoauthFromPOLDoc(v1309, v1157);
    if ( v87
      || (v157 = 0, (unsigned __int8)std::shared_ptr<Mso::ActivityScope::IMsoLoggingScope>::operator bool(v1309))
      && (v158 = BKORWS::Psh((BKORWS *)v1309), XlAsyncFileIO::FIsDistributedBlobsFile(v158)) )
    {
      v157 = 1;
      v1168 = 1;
    }
    else
    {
      v1168 = 0;
    }
    v1184 = v157;
    v159 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1376, 0x21C730Du);
    v160 = SXVWGEOM::RwFirst(v159);
    OldocHelper::SetAttrInAttrMask(
      v1157,
      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1232LL) + 32LL) != 0
    ? 0x20000
    : 0,
      0x20000u,
      v160);
    (*(void (__fastcall **)(struct IMsoOLDocument *, struct IMsoPKMClient **))(*(_QWORD *)v1157 + 168LL))(v1157, &v1246);
    v161 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1377, 0x21C730Eu);
    v162 = SXVWGEOM::RwFirst(v161);
    OldocHelper::SetAttrInAttrMask(v1157, v156, 0x20000u, v162);
    if ( v1246 )
      (*(void (__fastcall **)(struct IMsoPKMClient *))(*(_QWORD *)v1246 + 104LL))(v1246);
    if ( (*(int (__fastcall **)(struct IMsoOLDocument *, int *, __int64))(*(_QWORD *)v1157 + 48LL))(v1157, &v1282, 20) >= 0
      && v1282 )
    {
      v114 = -2147467260;
      XlsDiag::LogSetHrCoreTag(-2147467260, 0x17976D7u);
      Mso::TCntPtr<Uxpp::UxppAnnotationsService>::~TCntPtr<Uxpp::UxppAnnotationsService>(v1309);
      goto LABEL_1871;
    }
    Mso::TCntPtr<Uxpp::UxppAnnotationsService>::~TCntPtr<Uxpp::UxppAnnotationsService>(v1309);
  }
  if ( v150 )
  {
    v163 = XLSBOOK::Plxtab((XLSBOOK *)v150);
    CchStToSt(&v1567, (wchar_t *)v163 + 2084, 257);
    v164 = XLSBOOK::Plxtab((XLSBOOK *)v150);
    *((_WORD *)v164 + *((unsigned __int16 *)XLSBOOK::Plxtab((XLSBOOK *)v150) + 2084) + 2085) = 0;
  }
  MaxPathSzPoke::MaxPathSzPoke((MaxPathSzPoke *)v1484, (struct MaxPathHolder *)v1348);
  v165 = 0;
  if ( v1211 )
  {
    v168 = v1171;
  }
  else
  {
    if ( v1157 )
    {
      if ( (unsigned int)IMsoOLDocument::IsInFileSys(v1157) )
        v165 = AugmentationLoop::TranslateDetectLanguagesArrayAnnotationResponse::SzId((AugmentationLoop::TranslateDetectLanguagesArrayAnnotationResponse *)v1484);
      else
        v165 = 0;
    }
    v166 = (wchar_t *)v165;
    v167 = FIsTrue<int>(vgrbitScanload & 2);
    v168 = v1171;
    v169 = sub_1402D9860(v1157, (struct FileSource *)v1305, v1171 != 0, v167, v166, (struct OSRR *)&v1235);
    v1152 = v169;
    v114 = v169;
    if ( v169 < 0 )
    {
      XlsDiag::LogSetHrCoreTag(v169, 0x1E107807u);
LABEL_1872:
      MaxPathSzPoke::~MaxPathSzPoke((MaxPathSzPoke *)v1484);
      goto LABEL_1871;
    }
    v170 = v1267;
    if ( v1267 )
    {
      v171 = APPCORE::PmemheapMain((APPCORE *)&vapp);
      FileSource::FileSource((FileSource *)v1529, v171);
      v172 = FileSource::HrSetWin32PathSt((FileSource *)v1529, v170);
      if ( v172 < 0 )
        XlsDiag::LogSetHrCoreTag(v172, 0x1E109581u);
      v173 = FIsTrue<int>(vgrbitScanload & 2);
      v174 = sub_1402D9860(v1157, (struct FileSource *)v1529, v168 != 0, v173, 0, (struct OSRR *)&v1235);
      v1152 = v174;
      v114 = v174;
      if ( v174 < 0 )
      {
        XlsDiag::LogSetHrCoreTag(v174, 0x1E107806u);
        FileSource::~FileSource((FileSource *)v1529);
        goto LABEL_1872;
      }
      FileSource::~FileSource((FileSource *)v1529);
    }
  }
  v1211 = 1;
  MaxPathSzPoke::~MaxPathSzPoke((MaxPathSzPoke *)v1484);
  v175 = PbookFromTitle(v1567, v1568);
  v1197 = v175;
  if ( v175 )
  {
    v176 = BOOK::FFailedToFreeWhileLoading(v175);
    v175 = v1197;
    if ( v176 || !*((_QWORD *)v1197 + 141) )
    {
      if ( !BOOK::FFailedToFreeWhileLoading(v1197) )
        MsoShipAssertTagProc(40981770);
      v175 = 0;
      v1197 = 0;
    }
    if ( v175 )
    {
      if ( (unsigned int)FOsrc() )
      {
        SetLoadForPreviewError(-2147024891);
        v1022 = 24737497;
        v1023 = -2147024891;
        v114 = -2147024891;
        goto LABEL_1874;
      }
      v175 = v1197;
    }
  }
  if ( v1155 && !v175 )
  {
    FixUpFileTitle(&v1567);
    v175 = PbookFromTitle(v1567, v1568);
    v1197 = v175;
  }
  v177 = *(struct SH ***)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
  if ( v177[5] )
  {
    v178 = v177[5];
    if ( (*((_DWORD *)v178 + 221) & 0x200) != 0 )
    {
      v179 = BOOK::Pioldoc(v178);
      v180 = v1157;
      if ( v1157 != v179 )
      {
        MsoShipAssertTagProc(1650811750);
        v180 = v1157;
      }
      if ( !v180 )
        goto LABEL_410;
      HrRecordEvent(v180, 0x40000000u, 0);
      v181 = FeatureGateCollectionBase<ZipItFeatureGates>::Instance();
      v182 = 0;
      if ( (unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(v181 + 424) )
      {
        v185 = v1242;
      }
      else
      {
        v183 = FeatureGateCollectionBase<ZipItFeatureGates>::Instance();
        v184 = Mso::AB::Optimized::ChangeGate::operator bool(v183 + 440);
        v185 = v1242;
        if ( !v184 )
          goto LABEL_306;
        v185 = v1242 | 1;
        v1242 |= 1u;
        v186 = (BKORWS *)XlAsyncFileIO::SpOLDocCoauthFromPOLDoc(v1438, v1157);
        v187 = BKORWS::Psh(v186);
        if ( !XlAsyncFileIO::FIsDistributedBlobsFile(v187) )
          goto LABEL_306;
      }
      v182 = 1;
LABEL_306:
      if ( (v185 & 1) != 0 )
      {
        v1242 = v185 & 0xFFFFFFFE;
        Mso::TCntPtr<Uxpp::UxppAnnotationsService>::~TCntPtr<Uxpp::UxppAnnotationsService>(v1438);
      }
      if ( v182 )
      {
        v1283 = -1;
        if ( (*(int (__fastcall **)(struct IMsoOLDocument *, int *))(*(_QWORD *)v1157 + 200LL))(v1157, &v1283) < 0
          || v1283 <= 0 )
        {
          MsoShipAssertTagProc(504410975);
        }
        if ( v168 )
        {
          MsoShipAssertTagProc(504414753);
          v188 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1378, 0x1E113313u);
          v189 = SXVWGEOM::RwFirst(v188);
          OldocHelper::SetReadOnly(v1157, v189);
        }
        else
        {
          v190 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1379, 0x1E113312u);
          v191 = SXVWGEOM::RwFirst(v190);
          OldocHelper::ClearReadOnly(v1157, v191);
        }
        v192 = v1157;
        v193 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL);
        v194 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1380, 0x1E10B250u);
        v195 = SXVWGEOM::RwFirst(v194);
        LOBYTE(v196) = 33;
        LOBYTE(v197) = 5;
        Mementos::LogObjectLifetimeEvent(v195, 3, v197, v196, v193, v192);
        (*(void (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1157 + 16LL))(v1157);
        if ( !(unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(&unk_144028920) )
        {
          v198 = *(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL);
          v199 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1381, 0x1E113311u);
          v200 = SXVWGEOM::RwFirst(v199);
          BOOK::SetPioldoc(v198, 0, v200);
        }
        v1178 = 0;
      }
      else
      {
        v201 = BOOK::Pioldoc(*(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL));
        v203 = v1157;
        if ( v1157 == v201 )
        {
          LOBYTE(v202) = 1;
          Mso::TRestorer<bool>::TRestorer<bool>(v1508, &XlFileProtocol::s_fInClose, v202);
          v1439 = v1157;
          v204 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1382, 0x236962C5u);
          v205 = SXVWGEOM::RwFirst(v204);
          OlDocFilePath::FReleaseIOLDoc(&v1439, 1, 0, v205);
          v206 = *(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL);
          v207 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1383, 0x236962C4u);
          v208 = SXVWGEOM::RwFirst(v207);
          BOOK::SetPioldoc(v206, 0, v208);
          Mso::TRestorer<bool>::~TRestorer<bool>(v1508);
          v203 = v1157;
        }
        v1178 = FBeginCmdIOLDoc(v203, v168 != 0 ? 4 : 2, 0, &v1232, 0);
      }
      goto LABEL_409;
    }
  }
  if ( !v175 || wProjLoad == 2 )
    goto LABEL_410;
  v560 = v175 == v177[5];
  v1268 = v177[4];
  v209 = !v560;
  v1275 = v177[13];
  if ( v177[13] )
  {
    SH::Pbook(*((SH **)v177[13] + 3));
    v175 = v1197;
  }
  v210 = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)v175 + 205) + 32LL))((__int64)v175 + 1640);
  v211 = 0;
  v212 = 0;
  v213 = BOOK::Pioldoc(v1197);
  if ( v1157 != v213 )
  {
    if ( !v210 )
    {
      v214 = 34146077;
LABEL_335:
      v211 = 1;
      XlsDiag::LogSetHrCoreTag(-2147467260, v214);
      goto LABEL_336;
    }
    if ( !OfficeSharedApiImpl::BusinessBarShowArgs::GetHideCloseButton((OfficeSharedApiImpl::BusinessBarShowArgs *)v1305)
      || (v215 = FileSource::StzFilePath((FileSource *)v1305), (unsigned int)CmpTextHp(v210, v215, 0xFFFFFFFFLL)) )
    {
      v211 = 1;
      XlsDiag::LogSetHrCoreTag(-2147467260, 0x209071Eu);
      v212 = 1;
    }
  }
  if ( !v212 )
  {
    v216 = *((_QWORD *)v1197 + 66);
    if ( v216 )
    {
      if ( *(_QWORD *)(v216 + 208) )
      {
        v214 = 34146079;
        goto LABEL_335;
      }
    }
  }
LABEL_336:
  if ( v211 )
  {
    if ( (a3 & 4) == 0 )
      OkAlert(196753, v1568);
    fCeCanceled = 1;
    v114 = -2147467260;
    XlsDiag::LogSetHrCoreTag(-2147467260, 0x2385704u);
    v1033 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
    v1034 = OpenTelemetry::POpenFileStageModel(v1033);
    v1035 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1456, 0x1F0CB5D3u);
    v1036 = SXVWGEOM::RwFirst(v1035);
    WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v1034, 2214658819LL, v1036);
    goto LABEL_1871;
  }
  if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1232LL) + 80LL) )
  {
    v217 = XLOSRR::FMustUseOsr((XLOSRR *)&v1235);
    if ( (unsigned int)FOsrhBook(v1197) != v217 )
    {
      v1024 = FOsrhBook(v1197);
      OkAlert(589891 - (v1024 != 0), 0);
      v1022 = 24737499;
      goto LABEL_1876;
    }
  }
  if ( (*((_DWORD *)v1197 + 221) & 0x100) != 0
    && *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1836LL) )
  {
    OkAlert(196948, v1568);
    v1025 = 24737500;
    goto LABEL_1878;
  }
  v1284 = 0;
  v218 = HrGroupAction(0, v1197, 9, 0, &v1284);
  if ( v218 < 0 )
  {
    v1166 = v218;
    goto LABEL_1133;
  }
  if ( v1284 )
  {
    v1022 = 24737501;
LABEL_1876:
    v114 = -2147024809;
    v1023 = -2147024809;
LABEL_1874:
    XlsDiag::LogSetHrCoreTag(v1023, v1022);
LABEL_1871:
    v68 = v1158;
LABEL_1861:
    v1013 = v1161;
    goto LABEL_2092;
  }
  if ( !FileSource::FFileExists((FileSource *)v1305) )
  {
    OkAlert(196655, v1568);
    v1026 = -2147319765;
    v1025 = 24737502;
    goto LABEL_1879;
  }
  if ( PcxoFromPbook(v1197) )
  {
    v219 = PcxoFromPbook(v1197);
    if ( (unsigned int)FCxoLocked(v219) )
    {
      if ( (*((_DWORD *)v1197 + 222) & 0x400) == 0 )
        Error(393653);
      v1025 = 24737503;
LABEL_1878:
      v1026 = -2147024809;
LABEL_1879:
      v114 = v1026;
      v1027 = v1026;
      goto LABEL_1880;
    }
  }
  v220 = 2;
  if ( (a3 & 2) == 0 )
  {
    if ( vfPastingHlink )
    {
      v1025 = 24737504;
    }
    else
    {
      if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1232LL)
                     + 32LL) == 2 )
        fCeCanceled = 1;
      if ( (*(_BYTE *)(*((_QWORD *)v1197 + 141) + 3058LL) & 0x18) != 0 )
      {
        v1028 = 1;
      }
      else
      {
        v1029 = FActivatePbook(v1197);
        v1028 = FIsTrue<int>(v1029);
      }
      v1176 = v1028;
      vfLoadAbortedOnActivatedAlreadyOpenedBook = v1028;
      if ( v1028 )
      {
        v1451 = "Unconditionally setting foreground window for already opened book";
        Mso::Diagnostics::SendDiagnosticTrace<>(556414216, 2485, 50, 2, (__int64)&v1451);
        Count = Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection::GetCount(v1197);
        v1031 = WN::Puiframe(*(WN **)(Count + 16));
        v1032 = UIFRAME::HwndFrame(v1031);
        SetForegroundWindow(v1032);
        v1026 = -2147467260;
        v1025 = 37246725;
        goto LABEL_1879;
      }
      v1025 = 24737505;
    }
LABEL_1893:
    v114 = -2146827284;
    goto LABEL_1894;
  }
  if ( UIGLOBALS::UIGLOBALSCONTAINER::m_selection )
  {
    v221 = SH::Pbook(*(SH **)(UIGLOBALS::UIGLOBALSCONTAINER::m_selection + 24LL));
    if ( v221 == v1197
      && (!*(_QWORD *)&UIGLOBALS::UIGLOBALSCONTAINER::m_posi
       || (v222 = *(_QWORD *)(*(_QWORD *)&UIGLOBALS::UIGLOBALSCONTAINER::m_posi + 1568LL)) == 0
       || *(_QWORD *)(v222 + 256))
      && !(unsigned int)FOsrhBook(v1197) )
    {
      inited = HrInitRevert((struct REVARG *)v1565, 336, &v1269);
      v224 = v1170;
      if ( inited >= 0 )
        v224 = 1;
      v1170 = v224;
    }
  }
  Marquee::FreeAllMarqueeTag(0, 20789206, v220);
  DestroyWorkgroup();
  v225 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1384, 0x237630DCu);
  v226 = SXVWGEOM::RwFirst(v225);
  v227 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 128LL);
  v228 = 0;
  if ( v227 )
  {
    v229 = v227;
    do
    {
      v228 = v229[1];
      if ( v228 )
        break;
      v227 = (_QWORD *)*v227;
      v229 = v227;
    }
    while ( v227 );
  }
  LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v228 + 96), v1197, v226);
  if ( Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection::GetCount(*(Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 32LL))
    && *(_QWORD *)(Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection::GetCount(*(Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 32LL))
                 + 16) )
  {
    v230 = (struct WNX *)Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection::GetCount(*(Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 32LL));
    v231 = Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection::GetCount(*(Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 32LL));
    AttachWnxToWn(*(struct WN **)(v231 + 16), v230);
  }
  if ( (unsigned int)FLogRevs(v1197) && (*((_BYTE *)v1197 + 884) & 0x20) == 0 )
    FFreeUsrInfo(v1197, *(_DWORD *)(*((_QWORD *)v1197 + 125) + 16LL), 0, 0, 0);
  HrRecordEvent(v1157, 0x40000000u, 0);
  if ( v209 )
  {
    if ( v1275 )
    {
      v232 = (SH *)*((_QWORD *)v1275 + 3);
      if ( v232 )
      {
        v233 = SH::Pbook(v232);
        if ( v233 == v1197 )
          v209 = 0;
      }
    }
  }
  sub_1416A3634();
  v234 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
  if ( *(_QWORD *)(v234 + 992) )
  {
    v235 = *(_QWORD *)(v234 + 992);
    if ( *(_QWORD *)(v235 + 48) )
    {
      v236 = SH::Pbook(*(SH **)(*(_QWORD *)(v235 + 48) + 24LL));
      if ( v236 == v1197 )
        FreeCfr();
    }
  }
  v114 = XlReopenBook::HrCloseBookForReopen(
           &v1197,
           (struct REVERT **)((unsigned __int64)&v1269 & -(__int64)(v1170 != 0)));
  if ( v114 < 0 )
  {
    v1022 = 34174687;
    v1023 = v114;
    goto LABEL_1874;
  }
  v1301 = 0;
  if ( v209 )
  {
    v237 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1385, 0x237630DBu);
    v238 = SXVWGEOM::RwFirst(v237);
    v239 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 128LL);
    v240 = 0;
    if ( v239 )
    {
      v241 = v239;
      do
      {
        v240 = v241[1];
        if ( v240 )
          break;
        v239 = (_QWORD *)*v239;
        v241 = v239;
      }
      while ( v239 );
    }
    LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v240 + 96), v1268, v238);
    v242 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1386, 0x237630DAu);
    v243 = SXVWGEOM::RwFirst(v242);
    v244 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 128LL);
    v245 = 0;
    if ( v244 )
    {
      v246 = v244;
      do
      {
        v245 = v246[3];
        if ( v245 )
          break;
        v244 = (_QWORD *)*v244;
        v246 = v244;
      }
      while ( v244 );
    }
    VIEWCONTEXTDATA::CurWnx(*(VIEWCONTEXTDATA **)(v245 + 16), v1275, v243);
  }
  v168 = v1171;
  v1219 = 2;
  if ( v1171 || (v247 = 2, v1173) )
    v247 = 4;
  v1178 = FBeginCmdIOLDoc(v1157, v247, 0, &v1232, 0);
  if ( (*(unsigned int (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1157 + 208LL))(v1157) )
    v1219 = 0;
  if ( v168 )
  {
    operator|=(&v1219, 1);
  }
  else if ( (a10 & 0x200) != 0 )
  {
    operator|=(&v1219, 8);
  }
  if ( (unsigned int)FFinderFile(v82) )
    operator|=(&v1219, 32);
  if ( (a10 & 0x20000) != 0 )
    operator|=(&v1219, 256);
  LODWORD(v1125) = v1219;
  XlsDiag::SendTraceTag(41039178, 187, 100, L"FFileLoadEx: OlDocSetupFlags oldsf = 0x%x", v1125);
  v248 = TLSW::PesExpressionService(*(TLSW **)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL));
  v249 = ExpressionService::Pwbkcoll(v248);
  RevisionLatencyOutlierTracker::RevisionLatencyOutlierTracker(v1528, v249, 16);
  operator|=(&v1219, 4096);
  v250 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
  v251 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1387, 0x236962C3u);
  v252 = SXVWGEOM::RwFirst(v251);
  v114 = OlDocFilePath::HrSetupAndRetrievePathTitle(
           v250,
           (struct FileSource *)v1305,
           &v1157,
           v82,
           &v1232,
           (enum OlDocSetupFlags *)&v1219,
           0,
           v252,
           0,
           0);
  RevisionLatencyOutlierTracker::~RevisionLatencyOutlierTracker((RevisionLatencyOutlierTracker *)v1528);
  if ( v114 < 0 )
  {
    if ( v1170 && v1269 )
      FreeRevert(v1269);
    v1025 = 24737506;
LABEL_1894:
    v1027 = v114;
LABEL_1880:
    XlsDiag::LogSetHrCoreTag(v1027, v1025);
LABEL_1881:
    v68 = v1158;
LABEL_1882:
    v1013 = v1161;
LABEL_2092:
    if ( v1157 )
    {
      LOBYTE(v259) = v1187 != 0;
      sub_1416B0FA0(v1157, v1305, v259);
      (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v1157 + 56LL))(
        v1157,
        0xFFFFFFFFLL,
        7);
      if ( v1178 )
      {
        HrRecordEvent(v1157, 0x40000000u, 0);
        if ( v1013 && *v1013 )
        {
          v1109 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1366, 0x236962C2u);
          v1110 = SXVWGEOM::RwFirst(v1109);
          v1111 = 0;
          goto LABEL_2097;
        }
      }
      else
      {
        v1112 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1367, 0x236962C1u);
        v1110 = SXVWGEOM::RwFirst(v1112);
        v1111 = 1;
LABEL_2097:
        OlDocFilePath::FReleaseIOLDoc(v1013, v1111, 1, v1110);
      }
    }
LABEL_1935:
    v82 = v1160;
LABEL_2100:
    if ( v1542 )
    {
      if ( v1299 != v1157 && v1299 )
      {
        (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v1299 + 56LL))(
          v1299,
          0xFFFFFFFFLL,
          7);
        if ( v1189 )
          HrRecordEvent(v1299, 0x40000000u, 0);
        v1113 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1368, 0x236962C0u);
        v1114 = SXVWGEOM::RwFirst(v1113);
        OlDocFilePath::FReleaseIOLDoc(&v1299, 1, 1, v1114);
      }
      v1115 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1462);
      CchStToSt(v1115, v82, v1224);
    }
    XslClear((struct XSL *)&v1541);
    vpoldocument = v1349;
    if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL) + 8LL)
        & 1) == 0 )
    {
      FRemoveLoadAction((struct LoadRecovery *)v68, 0);
      if ( v68 )
      {
        LoadRecovery::Destroy((LoadRecovery *)v68);
        FreeHpst(v68);
        v68 = 0;
        v1233 = 0;
      }
    }
    ResetLoadRecovery();
    v1153 = 0;
    if ( !XlFileProtocolManager::FForceCobaltReopenHr(v114) )
    {
      v114 = -2146827284;
      XlsDiag::LogSetHrCoreTag(-2146827284, 0x2385706u);
    }
    v1150 = v1334;
    v1148 = v1254;
    v1147 = v1175;
    v1146 = v114;
    v1144 = v1181;
    v1143 = v1302;
    v1141 = v1270;
    v1140 = v1157;
    v1139 = v1159;
    v1138 = v1251;
    v1137 = v1246;
    v1136 = v1195 != 0;
    v1134 = v1220;
    v1132 = v1300;
    v1130 = (struct LoadRecovery *)v68;
LABEL_2113:
    v1070 = HrFileCompleteLoadEx(
              v82,
              hObject,
              v1153,
              v1182,
              lp,
              v1176,
              v1165,
              v1130,
              v1132,
              v1134,
              v1136,
              v1137,
              v1138,
              v1139,
              v1140,
              v1141,
              v1143,
              v1144,
              v1146,
              (const struct MaxPathHolder *)v1340,
              v1147,
              v1148,
              (struct OsfOpenScope *)v1485,
              (const struct XLOSRR *)&v1235,
              v1150);
LABEL_1992:
    v604 = v1070;
    goto LABEL_2136;
  }
  v253 = FeatureGateCollectionBase<LoadSaveFeatureGates>::Instance();
  if ( (unsigned __int8)Mso::AB::Optimized::FeatureGate::operator bool(v253 + 8) )
  {
    v257 = (const struct OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
    v258 = FileSource::HrSetOlDocFilePath((FileSource *)v1305, v257);
    v114 = v258;
    if ( v258 < 0 )
    {
      XlsDiag::LogSetHrCoreTag(v258, 0x27D405Fu);
      goto LABEL_1881;
    }
    v1152 = FileSource::HrSetPoldoc((FileSource *)v1305, v1157, v1274, v1213);
    v114 = v1152;
    if ( v1152 >= 0 )
      goto LABEL_408;
    v256 = 41969047;
    goto LABEL_407;
  }
  v254 = std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
  Target = (const wchar_t *)OfficeExtension::ServerRuntime::RichApiMessageEntry::GetTarget(v254);
  v1152 = FileSource::HrSetWin32PathSt((FileSource *)v1305, Target);
  v114 = v1152;
  if ( v1152 < 0 )
  {
    v256 = 41185885;
LABEL_407:
    XlsDiag::LogSetHrCoreTag(v114, v256);
    if ( v114 < 0 )
      goto LABEL_1881;
  }
LABEL_408:
  v260 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
  v261 = OlDocFilePath::StzTitle(v260);
  CchStToStz(v261, &v1567, 257);
  v142 = v1247;
LABEL_409:
  v150 = v1158;
LABEL_410:
  v262 = NtCurrentTeb()->ThreadLocalStoragePointer;
  vhpstErrPath = v82;
  v263 = *(_QWORD *)(*(_QWORD *)v262 + 304LL);
  *(_DWORD *)(v263 + 2024) = 1;
  *(_DWORD *)(v263 + 2028) = 38879640;
  v1153 = 0;
  v264 = 0;
  v1239 = 0;
  v1215 = 0;
  errDeferred = 0;
  v265 = NtCurrentTeb()->ThreadLocalStoragePointer;
  v1244 = (void *)-1LL;
  if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v265 + 304LL) + 872LL) + 104LL) == 2
    && !(unsigned int)FMetroFileEx((struct FileSource *)v1305, 0)
    && !v1155 )
  {
    v1167 = 0;
    if ( MsoDwRegGetDw((const struct _msoreg *)&vmsoridExcelExtractDataMode) == 1 )
      v1185 |= 1u;
    if ( !v1180 && MsoDwRegGetDw((const struct _msoreg *)&vmsoridExcelExtractDataFormulas) == 1 )
      v1185 |= 2u;
    if ( (v1185 & 1) == 0 )
    {
      v264 = FileSource::HpstgiFileOpen(
               (FileSource *)v1305,
               &v1567,
               (unsigned int)(v168 != 0) + 1056,
               0,
               0,
               0,
               0,
               0,
               v1213);
      v1215 = v264;
      v266 = 0;
      if ( !v1157 )
        goto LABEL_422;
      errDeferred = _IMsoOLDocument_GetDeferredError(v1157);
      if ( errDeferred )
        goto LABEL_427;
      v266 = 0;
LABEL_422:
      if ( !v168 )
      {
        if ( (unsigned int)FErrPstgi(v264) )
          v266 = (unsigned __int16)PstgiFromErr((unsigned __int16)v264);
        else
          v266 = 0;
      }
      errDeferred = v266;
      if ( v266 )
      {
LABEL_427:
        v1163 = 1;
        v264 = FileSource::HpstgiFileOpen((FileSource *)v1305, &v1567, 0x421u, 0, 0, 0, 0, 0, v1213);
        v1215 = v264;
      }
    }
    if ( (unsigned int)FErrPstgi(v264) )
    {
LABEL_437:
      v1185 |= 1u;
    }
    else
    {
      v1167 = 0;
      v267 = SXVWGEOM::RwFirst(v264);
      STGI::SetSlf(v264, v267 & 0xFFFFFFDF);
      if ( v168 || (v268 = 1152, v1163) )
        v268 = 1153;
      v269 = v268 | SXVWGEOM::RwFirst(v264) & 0x800;
      v270 = STGI::Lpstg(v264);
      v271 = ScStgIdsStreamOpen(v270, v269, 0, v1566, &v1167, -1161035344, 9);
      v272 = v271 == 0;
      if ( !v271 && !(unsigned int)FValidDRDocStream(v1167) )
      {
        StreamClose(v1167);
        v1167 = 0;
        v272 = 0;
      }
      if ( !v272 )
      {
        StgiFileClose(v264);
        v264 = 0;
        v1215 = 0;
        goto LABEL_437;
      }
    }
    if ( (v1185 & 1) == 0 )
      goto LABEL_439;
LABEL_1015:
    v553 = FileSource::StzFileName((FileSource *)v1305);
    if ( (unsigned int)FFinderFile(v553) )
    {
      v168 = 1;
      v1171 = 1;
      v1214 = 1;
      vfPretendNotStg = 1;
    }
    goto LABEL_1038;
  }
  if ( wProjLoad != 2 )
  {
    if ( a7 == 1024 )
    {
      v372 = v1164;
      goto LABEL_658;
    }
    v1212 = 0;
    v278 = 0;
    v279 = APPCORE::PmemheapMain((APPCORE *)&vapp);
    MaxPathHolder::MaxPathHolder((MaxPathHolder *)v1313, v279, 259, 0);
    if ( (unsigned int)FOsrcHostedByExcel() )
    {
      MaxPathStzPoke::MaxPathStzPoke((MaxPathStzPoke *)v1483, (struct MaxPathHolder *)v1313);
      v280 = MaxPathStzPoke::CchStzBufferSize((MaxPathStzPoke *)v1483);
      v281 = (wchar_t *)SlicerViewImpl::PSlicerView((SlicerViewImpl *)v1483);
      CnvTempFile = FileSource::HrGetCnvTempFile((FileSource *)v1305, v281, v280, &v1229, &v1187);
      v278 = CnvTempFile;
      if ( CnvTempFile < 0 )
      {
        v114 = CnvTempFile;
        XlsDiag::LogSetHrCoreTag(CnvTempFile, 0x17976E3u);
        MaxPathStzPoke::~MaxPathStzPoke((MaxPathStzPoke *)v1483);
LABEL_465:
        MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1313);
        goto LABEL_466;
      }
      v283 = (MaxPathStzPoke *)v1483;
    }
    else
    {
      if ( v1155 || v1172 )
      {
LABEL_473:
        if ( v1187 )
        {
          if ( v1157 )
          {
            v142 = IMsoOLDocument::IsInFileSys(v1157) != 0;
            v1247 = v142;
            v1258 = v142;
          }
          v286 = v1171;
          if ( v1229 == 68 )
            v286 = 1;
          v1171 = v286;
          v1214 = v286;
          v287 = FileSource::SzFilePath((FileSource *)v1305);
          MaxPathHolder::CchCopyFromSz((MaxPathHolder *)v1482, v287);
          v288 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1313);
          v289 = FileSource::HrSetWin32PathSt((FileSource *)v1305, v288);
          v1152 = v289;
          v114 = v289;
          if ( v289 < 0 )
          {
            XlsDiag::LogSetHrCoreTag(v289, 0x274139Du);
            goto LABEL_465;
          }
          v290 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL);
          v1249 = 0;
          *(_DWORD *)(v290 + 104) = 0;
          a10 &= ~8u;
          FRemoveLoadAction((struct LoadRecovery *)v150, 0);
          if ( v150 )
          {
            LoadRecovery::Destroy((LoadRecovery *)v150);
            FreeHpst(v150);
            v1158 = 0;
            v1233 = 0;
          }
        }
        v291 = FileSource::StzFileName((FileSource *)v1305);
        if ( (unsigned int)FFinderFile(v291) )
        {
          v1185 |= 1u;
          v1169 = 1;
          v1167 = 0;
          MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1313);
          goto LABEL_1014;
        }
        if ( v1155 )
        {
          if ( !v1168 )
          {
            v293 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
            v294 = (LXBASE *)OpenTelemetry::POpenFileStageModel(v293);
            v295 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1388, 0x1F0CB5D1u);
            SXVWGEOM::RwFirst(v295);
            WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v294);
            v296 = PstgiFromErr(1u);
            v297 = v1187;
            v264 = v296;
            v1215 = v296;
            v298 = v1236;
            v1194 = 5;
            if ( v1187 )
              v298 = v1229;
            v1236 = v298;
            v1464 = 0;
            memset_0(&v1465, 0, 0x58u);
            v1466 = 257;
            v1477 = 0;
            v1478 = 0;
            v1479 = 0;
            v1480 = 0;
            v1465 = &v1567;
            if ( !v297 || (v299 = (BKORWS *)v1482, v142) )
              v299 = (BKORWS *)v1339;
            v300 = BKORWS::Psh(v299);
            v68 = v1158;
            v1467 = v300;
            v1468 = a5;
            v1469 = v1244;
            v1470 = v1157;
            v1464 = &v1235;
            v1480 = v1158;
            MaxPathStzPoke::MaxPathStzPoke((MaxPathStzPoke *)v1502, (struct MaxPathHolder *)v1313);
            v301 = 0;
            if ( v1187 )
              v301 = SlicerViewImpl::PSlicerView((SlicerViewImpl *)v1502);
            v1475 = v301;
            MaxPathStzPoke::~MaxPathStzPoke((MaxPathStzPoke *)v1502);
            v1474 = v1187;
            v1471 = v1180;
            v1472 = v1185 & 2;
            v1473 = v1210 != 1;
            v1476 = v1270;
            v1479 = v1225;
            if ( AppGuard::Config::IsEnabled(v302) )
              v1477 = (a10 & 0x80000) != 0;
            v1478 = v1216 == 1;
            v303 = HrLoadInSecureReader((const struct XLOSRLA *)&v1464, v1213);
            v304 = NtCurrentTeb()->ThreadLocalStoragePointer;
            v1177 = v303;
            v1153 = v303 >= 0;
            v1244 = (void *)-1LL;
            v1223 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v304 + 304LL) + 2924LL);
            if ( v303 >= 0 )
              RenumberWind(*(struct SH **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                         + 32LL));
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1220;
            v1151 = 0;
            v114 = v1177;
            v1152 = v1177;
            if ( v1177 < 0 )
            {
              XlsDiag::LogSetHrCoreTag(v1177, 0x1797700u);
              if ( v1177 < 0 )
              {
                v305 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
                v306 = OpenTelemetry::POpenFileStageModel(v305);
                v307 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1389, 0x1F0CB5D0u);
                v308 = SXVWGEOM::RwFirst(v307);
                WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v306, (unsigned int)v1177, v308);
              }
            }
            MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1313);
            goto LABEL_910;
          }
          v292 = BKORWS::Psh((BKORWS *)&v1179);
          if ( (int)XlFileProtocolManager::HrRequestCobaltReopen(v1157, v1200, -1662189471, v292) < 0 )
            MsoShipAssertTagProc(506512324);
          v114 = -1662189471;
          XlsDiag::LogSetHrCoreTag(-1662189471, 0x1E30C3C3u);
          goto LABEL_465;
        }
        v309 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                         + 104LL);
        v310 = APPCORE::PmemheapMain((APPCORE *)&vapp);
        v311 = APPCORE::PlocaleinfoUSEN((APPCORE *)&vapp);
        v312 = FSmellsLikeMetroFileCancelable(
                 (struct FileSource *)v1305,
                 v311,
                 0,
                 v310,
                 &v1248,
                 v309 == 0,
                 &v1240,
                 &v1212);
        if ( v1212 )
        {
          v313 = 579396827;
          v314 = -2147023673;
LABEL_506:
          XlsDiag::LogSetHrCoreTag(v314, v313);
LABEL_507:
          v315 = (MaxPathHolder *)v1313;
LABEL_508:
          MaxPathHolder::~MaxPathHolder(v315);
          v68 = v1158;
          goto LABEL_815;
        }
        v316 = FeatureGateCollectionBase<LoadSaveFeatureGates>::Instance();
        if ( (unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(v316 + 488) )
        {
          v317 = (CorruptionMetaData *)std::_Optional_construct_base<CorruptionMetaData>::operator*(v1538);
          CorruptionMetaData::SetFEncrypted(v317, v1240 != 0);
          v318 = (CorruptionMetaData *)std::_Optional_construct_base<CorruptionMetaData>::operator*(v1538);
          v319 = sub_1402DFAB0(v1539);
          CorruptionMetaData::SetFDrmProtected(v318, v319);
        }
        if ( v1267 && !v312 )
        {
          MsoShipAssertTagProc(504410774);
          v313 = 504410773;
          v314 = -2147467260;
          goto LABEL_506;
        }
        if ( v1187 && (v1248 || !v312) )
        {
          FileSource::HrDeleteTemp((FileSource *)v1305);
          v114 = -2146827284;
          v320 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          *(_DWORD *)(v320 + 2024) = 0;
          *(_DWORD *)(v320 + 2028) = 0;
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1220;
          XlsDiag::LogSetHrCoreTag(-2146827284, 0x1797701u);
          MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1313);
          v68 = v1158;
          goto LABEL_518;
        }
        v68 = v1158;
        if ( v1248 && !LoadRecovery::FRepairPkg((LoadRecovery *)v1158) )
        {
          LoadRecovery::SetRepairPkg((LoadRecovery *)v68);
          v321 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          *(_DWORD *)(v321 + 2024) = 0;
          *(_DWORD *)(v321 + 2028) = 0;
          v114 = -2146827284;
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1220;
          XlsDiag::LogSetHrCoreTag(-2146827284, 0x1797702u);
          MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1313);
LABEL_467:
          v277 = v1160;
          goto LABEL_1664;
        }
        v322 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
        v323 = (LXBASE *)OpenTelemetry::POpenFileStageModel(v322);
        v324 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1390, 0x1F0CB5CFu);
        SXVWGEOM::RwFirst(v324);
        WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v323);
        if ( !v312 )
        {
          MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1313);
          goto LABEL_524;
        }
        v264 = PstgiFromErr(7u);
        v1215 = v264;
        if ( v1172 )
        {
          if ( !(unsigned int)FOsrc() )
          {
            v329 = FileSource::StzFileName((FileSource *)v1305);
            if ( !(unsigned int)sub_14240ED50(v329) )
            {
              SetLoadForPreviewError(-2147467259);
              XlsDiag::LogSetHrCoreTag(-2147467260, 0x1797703u);
              v330 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
              v331 = OpenTelemetry::POpenFileStageModel(v330);
              v332 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1460, 0x1F0CB5CEu);
              v333 = SXVWGEOM::RwFirst(v332);
              WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v331, 2214658820LL, v333);
LABEL_543:
              MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1313);
              goto LABEL_815;
            }
          }
        }
        std::optional<DataLossProtection::NotifyRaiiHintsForPrePostEvents>::optional<DataLossProtection::NotifyRaiiHintsForPrePostEvents>(v1336);
        v335 = v1171;
        if ( !v1171 && !FileSource::FCloud((FileSource *)v1305) )
        {
          v336 = APPCORE::PmemheapMain((APPCORE *)&vapp);
          MaxPathHolder::MaxPathHolder((MaxPathHolder *)v1509, v336, 259, 0);
          if ( IsWin32AppRunningInWdag() )
            v337 = (wchar_t *)FileSource::StzFileName((FileSource *)v1305);
          else
            v337 = v1160;
          MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1509, v337);
          v338 = *(const wchar_t **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 784LL);
          v339 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1509);
          v278 = HrWriteOwnerFile(v1157, v339, v338, &v1244);
          v340 = BKORWS::Psh((BKORWS *)v1509);
          v341 = PbookFromPioldoc(v1157);
          DataLossProtectionHelper::spCreateCustomInfoContext(v1343, v341, v340);
          v1440 = BKORWS::Psh((BKORWS *)v1343);
          v1324 = 5;
          v1323 = 6;
          v1441 = APPCORE::PmemheapMain((APPCORE *)&vapp);
          std::optional<DataLossProtection::NotifyRaiiHintsForPrePostEvents>::emplace<IMemHeap *,IMsoOLDocument * &,enum Mso::Dlp::Event,enum Mso::Dlp::Event,DataLossProtection::XLSInfoContext *>(
            (unsigned int)v1336,
            (unsigned int)&v1441,
            (unsigned int)&v1157,
            (unsigned int)&v1324,
            (__int64)&v1323,
            (__int64)&v1440);
          Mso::TCntPtr<DataLossProtection::XLSInfoContext>::~TCntPtr<DataLossProtection::XLSInfoContext>(v1343);
          MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1509);
        }
        LOBYTE(v334) = std::nullopt;
        if ( !(unsigned __int8)std::operator==<DataLossProtection::NotifyRaiiHintsForPrePostEvents>(v1336, v334) )
        {
          v342 = sub_1404519F0(v1523, v1336, &v1177);
          sub_1406219BC(v1517, v342);
          sub_1406219CC(v1517);
        }
        if ( v278 == -2147024864 )
        {
          v264 = PstgiFromErr(2u);
          v1215 = v264;
LABEL_618:
          if ( (unsigned int)FErrPstgi(v264) )
          {
            v369 = (unsigned __int16)PstgiFromErr((unsigned __int16)v264);
            v370 = v1222;
            v371 = v369;
            if ( v369 == 7 )
            {
              v372 = v1164;
              if ( v1222 == -2147024891 )
                v372 = 1;
              v1164 = v372;
            }
            else
            {
              v372 = v1164;
            }
            v68 = v1158;
            if ( v369 != 7 && v369 != 2 && v1249 && v1158 && LoadRecovery::FRepairPkg((LoadRecovery *)v1158) )
            {
              v1264 = 1;
              LoadRecovery::SetRepairState((LoadRecovery *)v68, -2146827284);
              if ( v371 == 1 && (unsigned int)(v370 + 2134241024) > 1 )
              {
                if ( v370 >= 0 )
                  v370 = -2146827284;
                XlsDiag::LogSetHrCoreTag(v370, 0x1797706u);
                std::_Optional_destruct_base<DataLossProtection::NotifyRaiiHintsForPrePostEvents,0>::reset(v1336);
                MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1313);
                goto LABEL_817;
              }
              if ( v370 >= 0 )
                v370 = -2147467260;
              v373 = 24737543;
              v374 = v370;
              goto LABEL_642;
            }
            if ( v371 == 1 )
            {
              if ( v370 == -2134195936
                && (unsigned int)Mso::Details::ConstexprFunctorBase<Mso::IFunctor<bool,FeaturePropertyValue const &,FeaturePropertyValue const &>>::Release(&vapp) )
              {
                v1177 = v1222;
                ErrorAlert(459071, v1568);
                v374 = v1177;
                if ( v1177 >= 0 )
                {
LABEL_643:
                  std::_Optional_destruct_base<DataLossProtection::NotifyRaiiHintsForPrePostEvents,0>::reset(v1336);
                  goto LABEL_543;
                }
                v373 = 24737544;
LABEL_642:
                XlsDiag::LogSetHrCoreTag(v374, v373);
                goto LABEL_643;
              }
              v114 = -2146827284;
              v1152 = -2146827284;
              XlsDiag::LogSetHrCoreTag(-2146827284, 0x230E1E1u);
              std::_Optional_destruct_base<DataLossProtection::NotifyRaiiHintsForPrePostEvents,0>::reset(v1336);
              MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1313);
LABEL_645:
              v375 = APPCORE::PlocaleinfoUSEN((APPCORE *)&vapp);
              if ( (unsigned int)FMetroFileExt((const struct FileSource *)v1305, v375, 0, 0) )
              {
                v68 = v1158;
                if ( v1158 )
                {
                  if ( LoadRecovery::FRepairPkg((LoadRecovery *)v1158)
                    || (unsigned __int16)PstgiFromErr((unsigned __int16)v264) == 7 )
                  {
                    OkAlert(v372 != 0 ? 262202 : 458868, v1568);
                    XlsDiag::LogSetHrCoreTag(v372 != 0 ? -2147024891 : -2146827284, 0x230E200u);
                    if ( !v372 )
                    {
                      v457 = (CorruptionMetaData *)std::_Optional_construct_base<CorruptionMetaData>::operator*(v1538);
                      CorruptionMetaData::MarkAsCorrupt(v457);
                    }
                    if ( v1172 )
                      SetLoadForPreviewError(v372 != 0 ? -2147024891 : -2042494972);
                    goto LABEL_815;
                  }
                  v1248 = 1;
                  LoadRecovery::SetRepairPkg((LoadRecovery *)v68);
                }
LABEL_817:
                v459 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                *(_DWORD *)(v459 + 2024) = 0;
                *(_DWORD *)(v459 + 2028) = 0;
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1220;
                v1151 = 0;
                if ( (unsigned int)FErrPstgi(v264) && v1244 != (void *)-1LL )
                {
                  CloseSentinelFile(v1244);
                  v1244 = (void *)-1LL;
                }
                v114 = -2146827284;
                XlsDiag::LogSetHrCoreTag(-2146827284, 0x230E201u);
                goto LABEL_821;
              }
LABEL_524:
              v168 = v1171;
              if ( a7 == 1024 )
                goto LABEL_839;
              v325 = 1024;
              v326 = 1024;
              if ( v1171 )
              {
                v325 = 1025;
                v326 = 1025;
              }
              v327 = v325;
              if ( *(_QWORD *)&UIGLOBALS::UIGLOBALSCONTAINER::m_posi )
              {
                v328 = *(_QWORD *)(*(_QWORD *)&UIGLOBALS::UIGLOBALSCONTAINER::m_posi + 1568LL);
                if ( v328 )
                {
                  if ( !*(_QWORD *)(v328 + 256) )
                  {
                    v326 = v325 | 0x20;
                    v327 = v325 | 0x20;
                  }
                }
              }
              if ( v1172 )
                v326 = v327 | 0x1000000;
              v264 = FileSource::HpstgiFileOpen((FileSource *)v1305, &v1567, v326, 0, &v1243, 0, 0, 0, v1213);
              v1215 = v264;
              v1174 = 1;
              if ( !v1172 || !(unsigned int)FErrPstgi(v264) || (unsigned int)FOsrc() && !MsoFDrmErrorCode(v1243) )
              {
                if ( (unsigned int)FErrPstgi(v264)
                  && (unsigned __int16)PstgiFromErr((unsigned __int16)v264) != 4
                  && !*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                            + 872LL)
                                + 104LL)
                  && v1249
                  && (v1243 == -2147286775 || v1243 == -2147287010) )
                {
                  v1231 = 1;
                }
LABEL_839:
                if ( a7 == 1024
                  || (unsigned int)FErrPstgi(v264) && (unsigned __int16)PstgiFromErr((unsigned __int16)v264) == 4 )
                {
                  goto LABEL_1015;
                }
                v1167 = 0;
                if ( (unsigned int)FErrPstgi(v264) )
                {
                  v468 = 0;
                  if ( v1157 )
                  {
                    errDeferred = _IMsoOLDocument_GetDeferredError(v1157);
                    if ( errDeferred )
                      goto LABEL_853;
                    v468 = 0;
                  }
                  if ( !v168 )
                  {
                    if ( (unsigned int)FErrPstgi(v264) )
                      v468 = (unsigned __int16)PstgiFromErr((unsigned __int16)v264);
                    else
                      v468 = 0;
                  }
                  errDeferred = v468;
                  goto LABEL_852;
                }
                v466 = ((v168 != 0) + 1024) | SXVWGEOM::RwFirst(v264) & 0x800;
                v467 = STGI::Lpstg(v264);
                ScStgIdsStreamOpen(v467, v466, 0, v1566, &v1167, -1161035344, 9);
                v468 = errDeferred;
LABEL_852:
                if ( !v468 )
                  goto LABEL_439;
LABEL_853:
                v1250 = -2147467259;
LABEL_1005:
                v1231 = 0;
                v1163 = 1;
                v549 = v1157
                    && ((*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1157 + 224LL))(v1157) & 1) != 0
                    && errDeferred == 2;
                v550 = FileSource::HpstgiFileOpen((FileSource *)v1305, &v1567, 0x401u, 0, &v1250, 0, 0, v549, v1213);
                v114 = v1250;
                v264 = v550;
                v1215 = v550;
                v1152 = v1250;
                if ( !(unsigned int)FErrPstgi(v550) )
                {
                  v1169 = 0;
                  v551 = SXVWGEOM::RwFirst(v264) & 0x800 | 0x401;
                  v552 = STGI::Lpstg(v264);
                  ScStgIdsStreamOpen(v552, v551, 0, v1566, &v1167, -1161035344, 9);
                  v168 = v1171;
                  goto LABEL_439;
                }
                if ( (unsigned __int16)PstgiFromErr((unsigned __int16)v264) != 4 )
                {
                  if ( v1250 == -2147287010 || v1250 == -2147286775 )
                  {
                    OkAlert(262188, 0);
                  }
                  else if ( v1250 != -2147217391 )
                  {
                    MsoSetLastWAlertHRTag(v1250, 0x376C7370u);
                    MsoShipAssertTagProc(892367981);
                    OkAlert(196657, v1568);
                    MsoResetLastWAlertHR();
                  }
LABEL_1022:
                  v168 = v1171;
                  goto LABEL_439;
                }
                v1169 = 1;
LABEL_1014:
                v168 = v1171;
                goto LABEL_1015;
              }
              if ( MsoFDrmErrorCode(v1243) )
              {
                v114 = -2042494975;
              }
              else if ( (unsigned __int16)PstgiFromErr((unsigned __int16)v264) == 4 )
              {
                v114 = -2042490872;
              }
              else if ( v1243 == -2147286775
                     || (unsigned int)(v1243 + 2147286780) <= 1
                     || v1243 == -2147286960
                     || (v114 = -2147467259, v1243 == -2147287010) )
              {
                v114 = -2042494972;
              }
              SetLoadForPreviewError(v114);
              XlsDiag::LogSetHrCoreTag(v114, 0x179770Eu);
              v460 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
              v461 = OpenTelemetry::POpenFileStageModel(v460);
              v462 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1398, 0x1F0CB5C9u);
              v463 = SXVWGEOM::RwFirst(v462);
              WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v461, (unsigned int)v114, v463);
              v68 = v1158;
              v464 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
              *(_DWORD *)(v464 + 2024) = 0;
              *(_DWORD *)(v464 + 2028) = 0;
              *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1220;
              LOBYTE(v264) = 0;
              if ( v68 )
                goto LABEL_830;
              v277 = v1160;
              goto LABEL_1664;
            }
          }
          else
          {
            v372 = v1164;
          }
          if ( !(unsigned int)FErrPstgi(v264) )
          {
            if ( v1240 )
            {
              if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1836LL) )
              {
                v376 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
                v377 = OlDocFilePath::PClpDocument(v376);
                EncryptedStorage = STGI::GetEncryptedStorage(v264);
                if ( !(unsigned int)FDrmQueryRightsStg(EncryptedStorage, 2u, v377) )
                {
                  StgiFileClose(v264);
                  HandleLockError(327752);
                  v348 = 36757986;
                  v379 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                  *(_DWORD *)(v379 + 2024) = 0;
                  *(_DWORD *)(v379 + 2028) = 0;
                  goto LABEL_589;
                }
              }
            }
          }
          std::_Optional_destruct_base<DataLossProtection::NotifyRaiiHintsForPrePostEvents,0>::reset(v1336);
          MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1313);
LABEL_658:
          if ( a7 == 1024
            || (unsigned int)FErrPstgi(v264) && (unsigned __int16)PstgiFromErr((unsigned __int16)v264) == 7 )
          {
            goto LABEL_645;
          }
          if ( !(unsigned int)FErrPstgi(v264) || (unsigned __int16)PstgiFromErr((unsigned __int16)v264) == 8 )
          {
            DeferredError = errDeferred;
          }
          else
          {
            DeferredError = 0;
            if ( v1157 )
            {
              DeferredError = _IMsoOLDocument_GetDeferredError(v1157);
              errDeferred = DeferredError;
              if ( DeferredError )
                goto LABEL_673;
              DeferredError = 0;
            }
            if ( !v1171 )
            {
              if ( (unsigned int)FErrPstgi(v264) )
              {
                DeferredError = (unsigned __int16)PstgiFromErr((unsigned __int16)v264);
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
            v68 = v1158;
            goto LABEL_734;
          }
LABEL_673:
          if ( v1244 != (void *)-1LL )
          {
            CloseSentinelFile(v1244);
            DeferredError = errDeferred;
            v1244 = (void *)-1LL;
          }
          if ( v1187 )
          {
            v382 = v1210;
          }
          else
          {
            v381 = FIsShareErr(DeferredError);
            v382 = v1210;
            if ( v381
              && v1210 == 1
              && (int)HrGetRealMetroFileType((struct FileSource *)v1305, (enum FILETYPE *)&v1285) >= 0
              && (v1285 == 54 || v1285 == 17 ? (v383 = 1) : (v383 = 0), v383) )
            {
              DeferredError = 0;
              errDeferred = 0;
            }
            else
            {
              DeferredError = errDeferred;
            }
          }
          if ( (unsigned int)FIsShareErr(DeferredError) && v382 == 1 )
          {
            v384 = APPCORE::PmemheapMain((APPCORE *)&vapp);
            MaxPathHolder::MaxPathHolder((MaxPathHolder *)v1491, v384, 259, 0);
            ENV::ENV((ENV *)&v1554);
            MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1491, v1160);
            FileTemp = FileSource::HrGetFileTemp(v1305, 5);
            v1152 = FileTemp;
            if ( FileTemp < 0 )
            {
              XlsDiag::LogSetHrCoreTag(FileTemp, 0x2806598u);
              XlsDiag::LogSetHrCoreTag(-2146827284, 0x2806599u);
              v315 = (MaxPathHolder *)v1491;
              goto LABEL_508;
            }
            v386 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
            v1442 = *(_QWORD *)(v386 + 336);
            *(_QWORD *)(v386 + 336) = &v1554;
            v1555 = 36737603;
            if ( !setjmp(v1556) )
            {
              v387 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1491);
              if ( (int)HrReadOwnerFile(v387, v1576, 257) < 0 )
              {
                v389 = !v1187 && FileHost::FIsEncryptedMetroFile((FileHost *)v1305, v388);
                v390 = FileSource::StzFilePath((FileSource *)v1305);
                v391 = 0;
              }
              else
              {
                v389 = !v1187 && FileHost::FIsEncryptedMetroFile((FileHost *)v1305, v388);
                v390 = FileSource::StzFilePath((FileSource *)v1305);
                v391 = v1576;
              }
              HrDeferredSRO(&v1567, v391, v390, 0, v389);
            }
            v392 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
            *(_QWORD *)(v392 + 336) = v1442;
            if ( (_QWORD)xmmword_143FE0F70 )
            {
              LOBYTE(v392) = v1183;
              v393 = sub_141224980(v1157, v392, &v1195);
              v1210 = v393;
              if ( v393 < 0 )
              {
                errDeferred = 0;
                v1165 = 1;
                XlsDiag::LogSetHrCoreTag(v393, 0x1797709u);
                v394 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
                v395 = OpenTelemetry::POpenFileStageModel(v394);
                v396 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1392, 0x1F0CB5CCu);
                v397 = SXVWGEOM::RwFirst(v396);
                WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v395, 2214658821LL, v397);
                MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1491);
                v68 = v1233;
                v264 = v1215;
                v1160 = Src;
                v1161 = v1245;
                v1171 = v1214;
                goto LABEL_815;
              }
              if ( v1195 )
                OSRR::SetAppAllowed((OSRR *)&v1235, 0);
            }
            MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1491);
            v68 = v1233;
            v114 = v1152;
            v372 = v1164;
            v1168 = v1184;
            v1247 = v1258;
            v1160 = Src;
            v1171 = v1214;
            v1161 = v1245;
            v1158 = v1233;
          }
          else
          {
            v68 = v1158;
          }
          v398 = 0;
          if ( v68 )
            v398 = (int)LoadRecovery::Lrmode(v68) > 0;
          v399 = v398 && LoadRecovery::FRepairPkg((LoadRecovery *)v68);
          v1248 = v399;
          v400 = BKORWS::Psh((BKORWS *)&v1179);
          v1215 = (struct STGI *)FileSource::HpstgiFileOpenEx(
                                   v1305,
                                   2098177,
                                   0,
                                   &v1259,
                                   0,
                                   v1248,
                                   0,
                                   0,
                                   0,
                                   v1572,
                                   &v1251,
                                   &v1567,
                                   0,
                                   0,
                                   0,
                                   0,
                                   v1267,
                                   0,
                                   v1213,
                                   v400);
          v264 = v1215;
          if ( (unsigned int)FErrPstgi(v1215) )
          {
            v114 = -2146827284;
            v1152 = -2146827284;
            XlsDiag::LogSetHrCoreTag(-2146827284, 0x230E1E3u);
          }
          else
          {
            v1186 = 1;
          }
          if ( (unsigned int)FErrPstgi(v264) && (unsigned __int16)PstgiFromErr((unsigned __int16)v264) == 8 )
          {
            v401 = v1259;
LABEL_724:
            if ( v401 == -2147168507 )
            {
              MsoShipAssertTagProc(505156896);
              v401 = v1259;
            }
            v1177 = v401;
            if ( v401 >= 0 )
              v401 = -2147467260;
            XlsDiag::LogSetHrCoreTag(v401, 0x179770Au);
            v402 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
            v403 = OpenTelemetry::POpenFileStageModel(v402);
            v404 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1393, 0x1F0CB5CBu);
            v405 = SXVWGEOM::RwFirst(v404);
            v406 = 2214658821LL;
            if ( v1177 < 0 )
              v406 = (unsigned int)v1177;
            WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v403, v406, v405);
            goto LABEL_815;
          }
          v401 = v1259;
          if ( v1259 == -2147168507 )
            goto LABEL_724;
          if ( !(unsigned int)FErrPstgi(v264) )
          {
            v1163 = 1;
            errDeferred = 0;
          }
LABEL_734:
          if ( !(unsigned int)FErrPstgi(v264) )
          {
            if ( !v1157
              || ((*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1157 + 224LL))(v1157) & 1) == 0
              || (v407 = STGI::Pxpkg(v264), !(unsigned int)FIsSharedWbk(v407)) )
            {
              if ( v68 )
              {
                v413 = PivotOperationBase::PSxview((PivotOperationBase *)v68);
                *((_WORD *)v413 + 18) |= 4u;
              }
              v414 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 2024LL);
              v1198 = v414 != 0;
              if ( !v414 )
                XlsDiag::SendTraceTag(38048668, 187, 50, 4, L"FInLoad expected to be false at that point");
              v415 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
              v416 = (LXBASE *)OpenTelemetry::POpenFileStageModel(v415);
              v417 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1394, 0x1F0CB5CAu);
              SXVWGEOM::RwFirst(v417);
              WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v416);
              MaxPathStPoke::MaxPathStPoke((MaxPathStPoke *)v1489, (struct MaxPathHolder *)v1339);
              v418 = BKORWS::Psh((BKORWS *)&v1179);
              v419 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
              Context = OlDocFilePath::PClpLoadContext(v419);
              v1444 = std::_Optional_construct_base<CorruptionMetaData>::operator*(v1538);
              v1446 = v1157;
              if ( v1187 )
                v420 = BKORWS::Psh((BKORWS *)v1482);
              else
                v420 = 0;
              v421 = v1251;
              v422 = a10 & 0x800;
              v423 = (struct OpenTelemetry *)v1244;
              if ( v1171 || (v424 = 0, v1163) )
                v424 = 1;
              v425 = MaxPathSzPoke::CchSzBufferSize((MaxPathSzPoke *)v1489);
              v426 = SlicerViewImpl::PSlicerView((SlicerViewImpl *)v1489);
              LOBYTE(v1149) = v1159;
              v1145[0] = v1247;
              v1142 = v420;
              v68 = v1158;
              v1135 = v423;
              v264 = v1215;
              LODWORD(v1133) = 0;
              LODWORD(v1131) = a7;
              LODWORD(v1129) = a5;
              LODWORD(v1128) = v424;
              LODWORD(v1126) = v425;
              v1177 = HrLoadMetro(
                        0,
                        v1215,
                        &v1567,
                        v1305,
                        v426,
                        v1126,
                        v1128,
                        v1129,
                        v1131,
                        v1133,
                        v1135,
                        &v1194,
                        v1158,
                        v1572,
                        v421,
                        v422,
                        v1142,
                        &v1235,
                        *(_QWORD *)v1145,
                        v1446,
                        v1270,
                        v1445,
                        &v1288,
                        v1444,
                        v1149,
                        Context,
                        v1273,
                        v418);
              MaxPathStPoke::~MaxPathStPoke((MaxPathStPoke *)v1489);
              v427 = v1177;
              v1152 = v1177;
              v114 = v1177;
              if ( v1177 < 0 )
              {
                XlsDiag::LogSetHrCoreTag(v1177, 0x17D88D8u);
                v427 = v1177;
                if ( v1177 < 0 )
                {
                  if ( OSRR::FReadyForOsr((OSRR *)&v1235) )
                  {
                    v73 = 1;
                    goto LABEL_764;
                  }
                  v427 = v1177;
                }
              }
              v1153 = v427 >= 0;
              if ( v427 >= 0 )
                v1302 = *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                        + 40LL);
              v428 = NtCurrentTeb()->ThreadLocalStoragePointer;
              v1244 = (void *)-1LL;
              v1223 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v428 + 304LL) + 2924LL);
              if ( v427 < 0 )
              {
                if ( v1187 )
                {
                  FileSource::HrDeleteTemp((FileSource *)v1305);
                  v427 = v1177;
                }
                if ( v68 && (v427 == -2134142954 || v427 == -2134188030) )
                  LoadRecovery::SetRepairState((LoadRecovery *)v68, v427);
                v73 = 1;
              }
              else
              {
                if ( v1187 && v1229 != 68 )
                {
                  v429 = LOCATIONCONTEXTDATA::PWorkbookCur((LOCATIONCONTEXTDATA *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                             + 304LL)
                                                                                 + 8LL));
                  Api::Workbook::SetFt(v429, (unsigned int)v1229, 0);
                }
                v430 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                if ( *(_DWORD *)(*(_QWORD *)(v430 + 872) + 104LL) == 2 && (v1185 & 2) == 0 )
                {
                  v1268 = *(struct SH **)(v430 + 32);
                  v431 = LOCATIONCONTEXTDATA::PWorkbookCur((LOCATIONCONTEXTDATA *)(v430 + 8));
                  v432 = OcsTransitionController::PCoauthTransitionState(v431);
                  v433 = XLSBOOK::Plxtab(v432);
                  v434 = SlicerViewImpl::PSlicerView(v433);
                  v435 = LOCATIONCONTEXTDATA::PWorkbookCur((LOCATIONCONTEXTDATA *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                             + 304LL)
                                                                                 + 8LL));
                  v436 = OcsTransitionController::PCoauthTransitionState(v435);
                  v437 = (TAB *)((char *)v434 + 16 * *((int *)XLSBOOK::Plxtab(v436) + 1));
                  if ( v434 < v437 )
                  {
                    v438 = NtCurrentTeb()->ThreadLocalStoragePointer;
                    do
                    {
                      v439 = TAB::PshDesktopOnly(v434);
                      if ( (*((_BYTE *)v439 + 10) & 4) != 0 )
                        v440 = 0;
                      else
                        v440 = *((_BYTE *)v439 + 8);
                      if ( v440 <= 1u )
                      {
                        v441 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1395, 0x237630D9u);
                        v442 = SXVWGEOM::RwFirst(v441);
                        v443 = TAB::PshDesktopOnly(v434);
                        v444 = *(_QWORD *)(*(_QWORD *)v438 + 304LL);
                        v445 = 0;
                        v446 = *(_QWORD **)(v444 + 128);
                        if ( v446 )
                        {
                          v447 = *(_QWORD **)(v444 + 128);
                          do
                          {
                            v445 = v447[1];
                            if ( v445 )
                              break;
                            v446 = (_QWORD *)*v446;
                            v447 = v446;
                          }
                          while ( v446 );
                        }
                        LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v445 + 96), v443, v442);
                        v448 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v438 + 304LL) + 32LL);
                        if ( !((*(_BYTE *)(v448 + 10) & 4) != 0 ? 0 : *(_BYTE *)(v448 + 8)) )
                        {
                          v275 = HrConvertSheetFmlaToVal();
                          if ( v275 < 0 )
                          {
LABEL_1910:
                            v1166 = v275;
                            goto LABEL_1133;
                          }
                        }
                      }
                      v434 = (TAB *)((char *)v434 + 16);
                    }
                    while ( v434 < v437 );
                    v68 = v1158;
                  }
                  v450 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1396, 0x237630D8u);
                  v451 = SXVWGEOM::RwFirst(v450);
                  v452 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 128LL);
                  v453 = 0;
                  if ( v452 )
                  {
                    v454 = v452;
                    do
                    {
                      v453 = v454[1];
                      if ( v453 )
                        break;
                      v452 = (_QWORD *)*v452;
                      v454 = v452;
                    }
                    while ( v452 );
                  }
                  LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v453 + 96), v1268, v451);
                  v264 = v1215;
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
                v455 = (struct WNX *)UIGLOBALS::UIGLOBALSCONTAINER::m_selection;
                if ( !UIGLOBALS::UIGLOBALSCONTAINER::m_selection )
                {
                  SetWnxSel(*(struct WNX **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                           + 104LL));
                  v455 = (struct WNX *)UIGLOBALS::UIGLOBALSCONTAINER::m_selection;
                }
                v73 = 1;
                FActivateListWnx(v455, 1, 0);
              }
              *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1220;
              v1151 = 0;
              goto LABEL_910;
            }
            StgiFileClose(v264);
            if ( v1244 != (void *)-1LL )
            {
              CloseSentinelFile(v1244);
              v1244 = (void *)-1LL;
            }
            if ( v1178 )
            {
              HrRecordEvent(v1157, 0x40000000u, 0);
              v1178 = 0;
            }
            if ( (*(int (__fastcall **)(struct IMsoOLDocument *, _QWORD, __int64))(*(_QWORD *)v1157 + 232LL))(
                   v1157,
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
              v114 = -2146827284;
              XlsDiag::LogSetHrCoreTag(-2146827284, 0x179770Bu);
              v1037 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
              *(_DWORD *)(v1037 + 2024) = 0;
              *(_DWORD *)(v1037 + 2028) = 0;
              goto LABEL_1882;
            }
LABEL_743:
            v408 = v1161;
            goto LABEL_744;
          }
          if ( (unsigned __int16)PstgiFromErr((unsigned __int16)v264) )
            goto LABEL_645;
          v456 = FileSource::SzFilePath((FileSource *)v1305);
          OkAlert(196758, v456);
          XlsDiag::LogSetHrCoreTag(-2147319765, 0x179770Du);
LABEL_815:
          if ( v68 )
          {
            v458 = PivotOperationBase::PSxview((PivotOperationBase *)v68);
            *((_WORD *)v458 + 18) |= 8u;
          }
          goto LABEL_817;
        }
        v343 = 2098176;
        v344 = 2098176;
        if ( v335 )
        {
          v343 = 2098177;
          v344 = 2098177;
        }
        v345 = v343;
        if ( *(_QWORD *)&UIGLOBALS::UIGLOBALSCONTAINER::m_posi )
        {
          v346 = *(_QWORD *)(*(_QWORD *)&UIGLOBALS::UIGLOBALSCONTAINER::m_posi + 1568LL);
          if ( v346 )
          {
            if ( !*(_QWORD *)(v346 + 256) )
            {
              v344 = v343 | 0x20;
              v345 = v343 | 0x20;
            }
          }
        }
        if ( v1172 )
          v344 = v345 | 0x1000000;
        v347 = v1186;
        if ( v1186 )
          v344 |= 0x20000000u;
        if ( v1267 && FileSource::FCloud((FileSource *)v1305) )
        {
          MsoShipAssertTagProc(504422487);
          v348 = 504422486;
          v349 = -2147467260;
LABEL_567:
          XlsDiag::LogSetHrCoreTag(v349, v348);
          std::_Optional_destruct_base<DataLossProtection::NotifyRaiiHintsForPrePostEvents,0>::reset(v1336);
          goto LABEL_507;
        }
        if ( v1240 )
        {
          v350 = BKORWS::Psh((BKORWS *)&v1179);
          v351 = v1213;
          v352 = v350;
          v353 = (unsigned __int8)v1158;
          if ( v1158 )
            v353 = LoadRecovery::FRepairPkg((LoadRecovery *)v1158);
          v1215 = (struct STGI *)FileSource::HpstgiFileOpenEx(
                                   v1305,
                                   v344,
                                   0,
                                   &v1222,
                                   0,
                                   v353,
                                   0,
                                   0,
                                   0,
                                   v1572,
                                   &v1251,
                                   &v1567,
                                   0,
                                   0,
                                   &v1240,
                                   1,
                                   v1267,
                                   0,
                                   v351,
                                   v352);
          v264 = v1215;
          if ( (unsigned int)FErrPstgi(v1215) )
          {
            v354 = 36757983;
LABEL_579:
            v114 = -2146827284;
            v1152 = -2146827284;
            XlsDiag::LogSetHrCoreTag(-2146827284, v354);
          }
        }
        else
        {
          v355 = BKORWS::Psh((BKORWS *)&v1179);
          v356 = v1213;
          v357 = v355;
          v358 = v1158 && LoadRecovery::FRepairPkg((LoadRecovery *)v1158);
          LOBYTE(v1124) = v358;
          v1215 = (struct STGI *)XLFileIOMockable::PstgiFileOpen(
                                   v1305,
                                   v344,
                                   0,
                                   &v1222,
                                   (_DWORD)v1124,
                                   0,
                                   v1267,
                                   v356,
                                   v357);
          v264 = v1215;
          if ( (unsigned int)FErrPstgi(v1215) )
          {
            v354 = 36757984;
            goto LABEL_579;
          }
        }
        v359 = FErrPstgi(v264);
        v360 = v347;
        if ( !v359 )
          v360 = 1;
        v1186 = v360;
        if ( !(unsigned int)FErrPstgi(v264) && OSRR::IsAppAllowed((OSRR *)&v1235) )
        {
          if ( v1251 )
          {
            OSRR::SetAppAllowed((OSRR *)&v1235, 0);
            if ( (unsigned int)XLOSRR::FMustUseOsr((XLOSRR *)&v1235)
              || OSRR::FHasReasons((OSRR *)&v1235) && (unsigned int)NoYesAlert(589864, &v1567) == 7 )
            {
              StgiFileClose(v264);
              v348 = 24737540;
              v264 = 0;
              v1215 = 0;
LABEL_589:
              v349 = -2146827284;
              goto LABEL_567;
            }
          }
        }
        if ( !v1172 || !(unsigned int)FErrPstgi(v264) )
          goto LABEL_607;
        if ( (unsigned __int16)PstgiFromErr((unsigned __int16)v264) == 7 )
        {
          v362 = APPCORE::PlocaleinfoUSEN((APPCORE *)&vapp);
          if ( !(unsigned int)FMetroFileExt((const struct FileSource *)v1305, v362, 0, 0) )
            goto LABEL_607;
        }
        else
        {
          if ( MsoFDrmErrorCode(v1222) )
          {
            v361 = -2042494975;
LABEL_606:
            SetLoadForPreviewError(v361);
LABEL_607:
            if ( (unsigned int)FErrPstgi(v264) )
            {
              v363 = (unsigned __int16)PstgiFromErr((unsigned __int16)v264);
              v364 = v1222;
              if ( v363 == 8 || v1222 == -2147168507 )
              {
                if ( v1222 == -2147168507 )
                {
                  MsoShipAssertTagProc(505157471);
                  v364 = v1222;
                }
                v1177 = v364;
                v1165 = 1;
                if ( v1187 )
                {
                  FileSource::HrDeleteTemp((FileSource *)v1305);
                  v364 = v1177;
                }
                if ( v364 >= 0 )
                  v364 = -2147467260;
                XlsDiag::LogSetHrCoreTag(v364, 0x1797705u);
                v365 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
                v366 = OpenTelemetry::POpenFileStageModel(v365);
                v367 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1391, 0x1F0CB5CDu);
                v368 = SXVWGEOM::RwFirst(v367);
                WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v366, (unsigned int)v364, v368);
                std::_Optional_destruct_base<DataLossProtection::NotifyRaiiHintsForPrePostEvents,0>::reset(v1336);
                MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1313);
                v68 = v1158;
                goto LABEL_815;
              }
            }
            v1174 = 1;
            goto LABEL_618;
          }
          if ( (unsigned __int16)PstgiFromErr((unsigned __int16)v264) != 4
            && v1222 != -2147286775
            && (unsigned int)(v1222 + 2147286780) > 1
            && v1222 != -2147286960
            && v1222 != -2147287010 )
          {
            if ( (unsigned __int16)PstgiFromErr((unsigned __int16)v264) == 8 )
            {
              v361 = -2147467260;
            }
            else
            {
              if ( (unsigned int)FOsrc() )
                goto LABEL_607;
              v361 = -2147467259;
            }
            goto LABEL_606;
          }
        }
        v361 = -2042494972;
        goto LABEL_606;
      }
      MaxPathStzPoke::MaxPathStzPoke((MaxPathStzPoke *)v1488, (struct MaxPathHolder *)v1313);
      v284 = MaxPathStzPoke::CchStzBufferSize((MaxPathStzPoke *)v1488);
      v285 = (wchar_t *)SlicerViewImpl::PSlicerView((SlicerViewImpl *)v1488);
      v1187 = FHandleConverterFile(
                (struct FileSource *)v1305,
                v285,
                v284,
                (enum FILETYPE *)&v1229,
                &v1342,
                (struct XLOSRR *)&v1235,
                v1160);
      v283 = (MaxPathStzPoke *)v1488;
    }
    MaxPathStzPoke::~MaxPathStzPoke(v283);
    goto LABEL_473;
  }
  v469 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
  if ( *(_QWORD *)(v469 + 40) )
    v1167 = *(struct STM **)(*(_QWORD *)(v469 + 40) + 56LL);
  else
    v1167 = 0;
  do
  {
LABEL_439:
    if ( !SbFromHpCore(v1167) )
    {
      if ( wProjLoad == 1 )
        wProjLoad = 5;
      if ( (unsigned int)FErrPstgi(v264) )
      {
        v68 = v1158;
        if ( !v1158 || v1231 )
        {
LABEL_987:
          v502 = v1161;
          goto LABEL_954;
        }
        v544 = PivotOperationBase::PSxview((PivotOperationBase *)v1158);
        *((_WORD *)v544 + 18) |= 8u;
LABEL_953:
        v502 = v1161;
        goto LABEL_954;
      }
LABEL_969:
      OSRR::SetAppAllowed((OSRR *)&v1235, 0);
      if ( (unsigned int)XLOSRR::FMustUseOsr((XLOSRR *)&v1235) )
      {
        StgiFileClose(v264);
        v114 = -2147024809;
        XlsDiag::LogSetHrCoreTag(-2147024809, 0x1797716u);
        v68 = v1158;
        v1153 = 0;
        errDeferred = 0;
        v580 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        *(_DWORD *)(v580 + 2024) = 0;
        *(_DWORD *)(v580 + 2028) = 0;
LABEL_821:
        LOBYTE(v264) = v1151;
        goto LABEL_518;
      }
      v114 = FileSource::HrGetFileTemp(v1305, 13);
      v1152 = v114;
      if ( v114 >= 0 )
      {
        v277 = v1160;
        if ( (unsigned int)FFinderFile(v1160) )
        {
          vfPretendNotStg = 1;
          StgiFileClose(v264);
          v579 = 1049729;
          if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                         + 104LL) != 2 )
            v579 = 1025;
          v1167 = FileSource::StreamOpen((FileSource *)v1305, v579, 0);
          vhpstm = v1167;
          goto LABEL_1078;
        }
      }
      else
      {
        XlsDiag::LogSetHrCoreTag(v114, 0x27413C0u);
      }
      if ( v1188
        && *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1232LL)
                     + 32LL) )
      {
        v539 = FExecWWWHelp(-1);
        v540 = 0;
        if ( v539 )
        {
          v68 = v1158;
LABEL_977:
          StgiFileClose(v264);
          goto LABEL_953;
        }
      }
      else
      {
        v540 = 0;
      }
      if ( v1567 < 0xFFu )
      {
        v541 = 58;
        v1568[v1567] = 58;
        v542 = 2LL * v1567 + 4;
        if ( v542 >= 0x202 )
          goto LABEL_2137;
        *(wchar_t *)((char *)&v1568[-1] + v542) = 0;
        OkAlert(196665, v1568);
        MakeStStzTruncOK(&v1567, 257);
      }
      v68 = v1158;
      if ( v1158 )
      {
        v543 = PivotOperationBase::PSxview((PivotOperationBase *)v1158);
        *((_WORD *)v543 + 18) |= 8u;
      }
      goto LABEL_977;
    }
    if ( hpFileSelInfo )
    {
      if ( *(int *)hpFileSelInfo >= 21 && !v1172 )
      {
        OSRR::SetAppAllowed((OSRR *)&v1235, 0);
        if ( (unsigned int)XLOSRR::FMustUseOsr((XLOSRR *)&v1235) )
        {
          if ( SbFromHpCore(v1167) )
            StreamClose(v1167);
          v1167 = 0;
          v1153 = 0;
          v114 = -2146827284;
          vhpstm = 0;
          errDeferred = 0;
          v574 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          *(_DWORD *)(v574 + 2024) = 0;
          *(_DWORD *)(v574 + 2028) = 0;
          XlsDiag::LogSetHrCoreTag(-2146827284, 0x1797710u);
LABEL_466:
          v68 = v1158;
          LOBYTE(v264) = v1151;
          goto LABEL_467;
        }
      }
    }
    if ( v1153
      || !SbFromHpCore(v1167)
      || *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                   + 104LL) == 2 )
    {
      if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                     + 104LL) == 2 )
      {
        ENV::ENV((ENV *)&v1557);
        v495 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        v1447 = *(_QWORD *)(v495 + 336);
        *(_QWORD *)(v495 + 336) = &v1557;
        v1558 = 36737604;
        v496 = setjmp(v1559);
        v497 = v1447;
        if ( v496
          || (v498 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1339), (int)HrDeferredSRO(&v1567, 0, v498, 0, 0) < 0) )
        {
          v1152 = -2147467259;
          v114 = -2147467259;
          XlsDiag::LogSetHrCoreTag(-2147467259, 0x279F29Fu);
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v497;
        }
        else
        {
          v114 = v1152;
        }
        v68 = v1233;
        v168 = v1214;
        v499 = *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer;
        v1158 = v1233;
        v1171 = v1214;
        *(_QWORD *)(*(_QWORD *)(v499 + 304) + 336LL) = v497;
        v500 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1304LL);
        *(_WORD *)(v500 + 56) &= ~8u;
        v1168 = v1184;
        v1160 = Src;
        v1161 = v1245;
        v1153 = 2;
      }
      else
      {
        v68 = v1158;
      }
      goto LABEL_901;
    }
    if ( (unsigned int)FErrPstgi(v264) || (v273 = STGI::Lpstg(v264), !(unsigned int)FMultiUsrStg(v273)) )
    {
      v274 = 0;
    }
    else
    {
      v274 = 1;
      if ( vgkr == -1 && MsoFShouldGatekeep((const struct _msoreg *)&vmsoridEnableExcelGKOnLoad) )
      {
        v1287 = 0;
        if ( (unsigned int)FBeginDiskIO(v1167) )
        {
          v1286 = 0;
          v275 = HrWPlatformSpecificFromStream2(&v1286);
          if ( v275 < 0 )
            goto LABEL_1910;
          if ( (v1286 & 0xF1FF) == 9 )
          {
            v276 = v1158;
            v1325 = 0;
            v275 = HrReadBof(v1286, 0, (struct LoadRecovery *)v1158, &v1325);
            if ( v275 < 0 )
              goto LABEL_1910;
            v275 = HrReadFileAccess(v1583, 8224, &v1567, 0, 0, 0, 0, (struct LoadRecovery *)v276, &v1262, &v1287);
            if ( v275 < 0 )
              goto LABEL_1910;
          }
          v275 = HrStreamSetPos2(0);
          if ( v275 < 0 )
            goto LABEL_1910;
          v275 = HrEndDiskIO2(0);
          if ( v275 < 0 )
            goto LABEL_1910;
        }
        if ( !v1287 )
        {
          StreamClose(v1167);
          StgiFileClose(v264);
          v1038 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          v1025 = 40981772;
          *(_DWORD *)(v1038 + 2024) = 0;
          *(_DWORD *)(v1038 + 2028) = 0;
          goto LABEL_1878;
        }
        v277 = v1160;
        LOBYTE(v1128) = 1;
        LODWORD(v1124) = 0;
        SafeToLoad::FGatekeep(v1160, v1305, 0, 0, v1124, &v1235, (_DWORD)v1128);
        goto LABEL_859;
      }
    }
    v277 = v1160;
LABEL_859:
    if ( v274
      && v1157
      && ((*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1157 + 224LL))(v1157) & 1) != 0 )
    {
      StreamClose(v1167);
      StgiFileClose(v264);
      if ( v1178 )
      {
        HrRecordEvent(v1157, 0x40000000u, 0);
        v1178 = 0;
      }
      if ( (*(int (__fastcall **)(struct IMsoOLDocument *, _QWORD, __int64))(*(_QWORD *)v1157 + 232LL))(v1157, 0, 1) < 0 )
      {
        Error(196658);
        XlsDiag::SendTraceTag(
          18088268,
          187,
          10,
          4,
          L"FFileLoad Failed to disable the RobustifiedUNC behavior on the file.");
        v1039 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        v1025 = 24737554;
        *(_DWORD *)(v1039 + 2024) = 0;
        *(_DWORD *)(v1039 + 2028) = 0;
        goto LABEL_1893;
      }
      goto LABEL_1072;
    }
    v470 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1304LL);
    *(_WORD *)(v470 + 56) &= ~8u;
    *(_WORD *)(v470 + 56) |= 8 * (_WORD)v274;
    v474 = 0;
    if ( !(unsigned int)FErrPstgi(v264) )
    {
      v471 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
      v472 = OlDocFilePath::PClpDocument(v471);
      v473 = STGI::Lpstg(v264);
      if ( !(unsigned int)FDrmQueryRightsStg(v473, 4u, v472) )
        v474 = 1;
    }
    v1183 = v474;
    if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1836LL) )
    {
      if ( !(unsigned int)FErrPstgi(v264) )
      {
        v475 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
        v476 = OlDocFilePath::PClpDocument(v475);
        v477 = STGI::Lpstg(v264);
        if ( !(unsigned int)FDrmQueryRightsStg(v477, 2u, v476) )
        {
          StreamClose(v1167);
          StgiFileClose(v264);
          HandleLockError(327752);
          v1025 = 24737555;
          v1040 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          v114 = -1662124019;
          *(_DWORD *)(v1040 + 2024) = 0;
          *(_DWORD *)(v1040 + 2028) = 0;
          goto LABEL_1894;
        }
      }
    }
    v68 = v1158;
    lp = *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL);
    if ( v1158 )
    {
      v478 = a10 & 0x400;
      v479 = PivotOperationBase::PSxview((PivotOperationBase *)v1158);
      *((_WORD *)v479 + 18) &= ~0x40u;
      *((_WORD *)v479 + 18) |= v478 != 0 ? 0x40 : 0;
    }
    if ( (a10 & 0x8000) != 0 )
      OSRR::SetHasInvalidPivot((OSRR *)&v1235, 1);
    v480 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1339);
    CchStToStz(v480, v1582, 2084);
    v481 = APPCORE::PmemheapMain((APPCORE *)&vapp);
    MaxPathHolder::MaxPathHolder((MaxPathHolder *)v1481, v481, 259, 0);
    v482 = FileSource::HrGetFileTemp(v1305, 10);
    v1152 = v482;
    v114 = v482;
    if ( v482 < 0 )
    {
      XlsDiag::LogSetHrCoreTag(v482, 0x27413A3u);
      StreamClose(v1167);
      StgiFileClose(v264);
      Error(327845);
      MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1481);
      goto LABEL_1861;
    }
    v483 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
    v484 = (LXBASE *)OpenTelemetry::POpenFileStageModel(v483);
    v485 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1399, 0x1F0CB5C7u);
    SXVWGEOM::RwFirst(v485);
    WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v484);
    v486 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1481);
    v487 = HrLoadBiff(
             &v1167,
             &v1567,
             v1582,
             v486,
             v168,
             a5,
             a7,
             v264,
             0,
             &v1194,
             &v1223,
             (struct LoadRecovery *)v68,
             &lp,
             (struct XLOSRR *)&v1235,
             v1270,
             &v1262,
             v1273,
             &v1153);
    if ( v487 < 0 )
    {
      v1166 = v487;
      MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1481);
      goto LABEL_1133;
    }
    MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1339, v1582);
    if ( !v1153 && OSRR::FReadyForOsr((OSRR *)&v1235) )
    {
      XlsDiag::LogSetHrCoreTag(-2147024809, 0x205C2A1u);
      v1155 = 1;
      MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1481);
      v408 = v1161;
      goto LABEL_744;
    }
    if ( lp != *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL)
      && (unsigned int)FResidentBook(lp) )
    {
      v1303 = *(struct SH **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 32LL);
      v488 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1400, 0x2375A798u);
      v489 = SXVWGEOM::RwFirst(v488);
      v490 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 128LL);
      v491 = 0;
      if ( v490 )
      {
        v492 = v490;
        do
        {
          v491 = v492[1];
          if ( v491 )
            break;
          v490 = (_QWORD *)*v490;
          v492 = v490;
        }
        while ( v490 );
      }
      LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v491 + 96), lp, v489);
    }
    if ( v1153 && *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL) )
    {
      if ( !v1172 )
      {
        v493 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1481);
        if ( (unsigned int)HrCheckCollaboration(v277, v493) == -2147467260 )
        {
          errDeferred = 0;
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1220;
          LOBYTE(v264) = 0;
          if ( v68 )
          {
            v575 = PivotOperationBase::PSxview((PivotOperationBase *)v68);
            *((_WORD *)v575 + 18) |= 8u;
          }
          v114 = -2147467260;
          XlsDiag::LogSetHrCoreTag(-2147467260, 0x1797714u);
          v1153 = 0;
          MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1481);
          goto LABEL_1664;
        }
      }
      v494 = (struct WNX *)UIGLOBALS::UIGLOBALSCONTAINER::m_selection;
      v1174 = 1;
      if ( !UIGLOBALS::UIGLOBALSCONTAINER::m_selection )
      {
        SetWnxSel(*(struct WNX **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 104LL));
        v494 = (struct WNX *)UIGLOBALS::UIGLOBALSCONTAINER::m_selection;
      }
      FActivateListWnx(v494, 1, 0);
    }
    MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1481);
LABEL_901:
    if ( v1153 == 16 )
    {
      if ( v168 || (v501 = 1024, v1163) )
        v501 = 1025;
      v264 = FileSource::HpstgiFileOpen((FileSource *)v1305, &v1567, v501, 0, 0, 0, 0, 0, v1213);
      v1215 = v264;
      v1188 = 1;
      v1153 = 0;
      if ( !(unsigned int)FErrPstgi(v264) )
        goto LABEL_969;
      v1152 = -2146827284;
      v114 = -2146827284;
      XlsDiag::LogSetHrCoreTag(-2146827284, 0x230E203u);
    }
    else
    {
      v264 = v1215;
    }
    if ( v1194 == 32 && (unsigned int)OkCancelAlert(196937, 0) == 1 )
    {
      v1167 = FileSource::StreamOpen((FileSource *)v1305, 0x401u, 0);
      vhpstm = v1167;
      goto LABEL_1077;
    }
LABEL_910:
    if ( !v1154 )
      goto LABEL_987;
    if ( !(unsigned int)sub_1404867C0((unsigned int)v1194, (unsigned int)v1223) || v1153 == 2 )
    {
      v508 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
      if ( *(_QWORD *)(v508 + 40) && (v1153 == 1 || (*(_DWORD *)(*(_QWORD *)(v508 + 40) + 884LL) & 0x200) != 0) )
      {
        if ( (unsigned int)IMsoOLDocument::IsInFileSys(v1157) )
        {
          v509 = (wchar_t **)XLSBOOK::Plxtab(*(XLSBOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                     + 304LL)
                                                         + 40LL));
          FreeHpstTempPath((struct STB *)v509);
          if ( v1187 )
          {
            v510 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1482);
          }
          else if ( FileSource::FCloudStreaming((FileSource *)v1305) )
          {
            v511 = std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
            v510 = (const wchar_t *)OfficeExtension::ServerRuntime::RichApiMessageEntry::GetTarget(v511);
          }
          else
          {
            v510 = FileSource::StzFilePath((FileSource *)v1305);
          }
          if ( (int)HrStDupSt(v510, v509 + 21) < 0 )
            v509[21] = 0;
        }
        v512 = *(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL);
        v513 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1402, 0x236962A0u);
        v514 = SXVWGEOM::RwFirst(v513);
        BOOK::SetPioldoc(v512, v1157, v514);
        v515 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        if ( *(_QWORD *)(v515 + 40) != v1301
          && (*(_DWORD *)(*(_QWORD *)(v515 + 40) + 1440LL) & 0x8000000) != 0
          && (*(unsigned int (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1157 + 208LL))(v1157) == 2 )
        {
          v516 = v1213;
          XlAsyncFileIO::SpOLDocCoauthFromPOLDoc(v1338, v1157);
          if ( (unsigned __int8)std::shared_ptr<Mso::ActivityScope::IMsoLoggingScope>::operator bool(v1338)
            && (v517 = BKORWS::Psh((BKORWS *)v1338), XlAsyncFileIO::FIsDistributedBlobsFile(v517)) )
          {
            v1199 = 1;
            v518 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1403, 0x1E307684u);
            v519 = SXVWGEOM::RwFirst(v518);
            OldocHelper::SetReadOnly(v1157, v519);
            if ( v516 )
            {
              v520 = Mso::Telemetry::Activity::DataFields(v516);
              Mso::Telemetry::IDataFieldCollection::Add(v520, "SwitchToRO", "ZipItOldocSetReadOnly");
            }
          }
          else
          {
            HrRecordEvent(v1157, 0x40000000u, 0);
            v521 = (*(__int64 (__fastcall **)(struct IMsoOLDocument *, __int64, _QWORD, _QWORD))(*(_QWORD *)v1157 + 104LL))(
                     v1157,
                     4,
                     0,
                     *(int *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                        + 1232LL)
                            + 80LL));
            if ( v521 - 3473424 <= 1 )
              XlFileProtocolManager::TrackOpen(v1157);
            if ( v516 )
            {
              v522 = Mso::Telemetry::Activity::DataFields(v516);
              Mso::Telemetry::IDataFieldCollection::Add<int>(v522, "SwitchToRO", v521, 4);
            }
          }
          v523 = *(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL);
          v524 = (struct IMsoXmlDataStore *)*((_QWORD *)v523 + 604);
          v525 = BOOK::Pioldoc(v523);
          XlMsoMockable::MsoHrCreateMetadataProfile(v525, v524, 0);
          v526 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          *(_DWORD *)(*(_QWORD *)(v526 + 40) + 1440LL) &= ~0x8000000u;
          Mso::TCntPtr<Uxpp::UxppAnnotationsService>::~TCntPtr<Uxpp::UxppAnnotationsService>(v1338);
        }
        v527 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        if ( *(_QWORD *)(v527 + 40) != v1301 )
        {
          OutSpace = BOOK::GetOutSpace(*(BOOK **)(v527 + 40));
          if ( OutSpace )
          {
            v529 = *(void (__fastcall **)(struct OfficeSpace::IOutSpace *, _QWORD, struct IMsoOLDocument *))(*(_QWORD *)OutSpace + 312LL);
            v530 = BOOK::Pioldoc(*(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                          + 40LL));
            v529(OutSpace, 0, v530);
          }
        }
        if ( v1288 )
        {
          v531 = BOOK::Pioldoc(*(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                        + 40LL));
          ShowOdsRegexBusBar(v531);
        }
        if ( (unsigned int)FContainPowerView(*(const struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                               + 304LL)
                                                                   + 40LL))
          && !(unsigned int)Excel::Addins::FPowerViewAddinEnabled(0, v532) )
        {
          v533 = BOOK::Pioldoc(*(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                        + 40LL));
          ShowPowerBiBusBar(v533);
        }
      }
      goto LABEL_953;
    }
    if ( (unsigned int)FIsShareErr(errDeferred) && (_QWORD)xmmword_143FE0F70 )
      goto LABEL_987;
    HrRecordEvent(v1157, 0x40000000u, 0);
    v502 = v1161;
    v1178 = 0;
    if ( *v1161 )
      _IMsoOLDocument_SetIReDownload(*v1161, -1);
    v503 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1401, 0x236962A1u);
    v504 = SXVWGEOM::RwFirst(v503);
    v505 = OlDocFilePath::FReleaseIOLDoc(&v1157, 1, 1, v504);
    *v502 = 0;
    if ( v1153 && !v505 )
    {
      errDeferred = 0;
      v506 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
      *(_DWORD *)(v506 + 2024) = 0;
      *(_DWORD *)(v506 + 2028) = 0;
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1220;
      LOBYTE(v264) = 0;
      if ( v68 )
      {
        v507 = PivotOperationBase::PSxview((PivotOperationBase *)v68);
        *((_WORD *)v507 + 18) |= 8u;
      }
      v114 = -2146827284;
      XlsDiag::LogSetHrCoreTag(-2146827284, 0x1797715u);
      goto LABEL_467;
    }
LABEL_954:
    if ( v1154 && v1178 && v1153 != 2 && (!(unsigned int)FIsShareErr(errDeferred) || !(_QWORD)xmmword_143FE0F70) )
    {
      v534 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
      if ( !*(_QWORD *)(v534 + 40) || (*(_DWORD *)(*(_QWORD *)(v534 + 40) + 884LL) & 0x200) == 0 )
      {
        if ( (a10 & 0x100) != 0 )
        {
          v535 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1404, 0x21C730Fu);
          v536 = SXVWGEOM::RwFirst(v535);
          OldocHelper::SetAttrInAttrMask(v1157, 0, 0x100000u, v536);
        }
        if ( v1199 && v1153 )
        {
          v537 = Measurements::Stopwatch::Stopwatch((Measurements::Stopwatch *)v1537);
          LOBYTE(v538) = 1;
          Measurements::MeasureElapsedTime::MeasureElapsedTime(
            v1525,
            Measurements::MeasurementId::ExcelRecordEvent,
            v538,
            v537);
          v1326 = 3473425;
          (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, int *, _QWORD))(*(_QWORD *)v1157 + 112LL))(
            v1157,
            0x40000000,
            &v1326,
            0);
          Measurements::MeasureElapsedTime::~MeasureElapsedTime((Measurements::MeasureElapsedTime *)v1525);
        }
        else
        {
          v545 = BKORWS::Psh((BKORWS *)&v1179);
          if ( (unsigned int)XlFileProtocolManager::HrRecordEvent(v1157, 0x40000000u, v1153 != 0, v1200, v545) == -1662189464 )
          {
            v114 = -1662189464;
            XlsDiag::LogSetHrCoreTag(-1662189464, 0x1E26384Cu);
            v1178 = 0;
            goto LABEL_1882;
          }
        }
        v1178 = 0;
      }
    }
    if ( !(unsigned int)FIsShareErr(errDeferred) || !(_QWORD)xmmword_143FE0F70 )
      goto LABEL_1105;
    v546 = 304;
    if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                   + 104LL) == 2 )
    {
      v589 = v1210;
      if ( v1210 == 1 )
      {
        LOBYTE(v546) = v1183;
        v589 = sub_141224980(v1157, v546, &v1195);
        v1210 = v589;
        if ( v1195 )
          OSRR::SetAppAllowed((OSRR *)&v1235, 0);
      }
      else
      {
        sub_1413EEE50();
      }
      if ( v589 < 0 )
      {
        if ( SbFromHpCore(v1167) )
          StreamClose(v1167);
        if ( !(unsigned int)FErrPstgi(v264) )
          StgiFileClose(v264);
        v1215 = 0;
        v1167 = 0;
        v114 = v589;
        XlsDiag::LogSetHrCoreTag(v589, 0x1797717u);
        v1153 = 0;
LABEL_1093:
        errDeferred = 0;
        v587 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v1165 = 1;
        v588 = *(_QWORD *)(*(_QWORD *)v587 + 304LL);
        *(_DWORD *)(v588 + 2024) = 0;
        *(_DWORD *)(v588 + 2028) = 0;
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1220;
        LOBYTE(v264) = 0;
        if ( v68 )
        {
LABEL_830:
          v465 = PivotOperationBase::PSxview((PivotOperationBase *)v68);
          *((_WORD *)v465 + 18) |= 8u;
        }
LABEL_518:
        v277 = v1160;
LABEL_1664:
        if ( v1542 )
        {
          v917 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1462);
          CchStToSt(v917, v277, v1224);
        }
        XslClear((struct XSL *)&v1541);
        if ( v1170 && v1269 )
          FreeRevert(v1269);
        if ( !OSRR::IsAppAllowed((OSRR *)&v1235) && (unsigned int)XLOSRR::FMustUseOsr((XLOSRR *)&v1235) )
        {
          OkAlert(589889, 0);
          v114 = -2147467260;
          v1217 = -2147467260;
          v1153 = 0;
          XlsDiag::LogSetHrCoreTag(-2147467260, 0x179771Bu);
        }
        v408 = v1161;
        vpoldocument = v1349;
        if ( v1154 && *v1161 && v1239 != -2 )
        {
          if ( v1153
            || (v918 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL), *(_QWORD *)(v918 + 40))
            && (*(_DWORD *)(*(_QWORD *)(v918 + 40) + 884LL) & 0x200) != 0 )
          {
            if ( v1178 )
            {
              v925 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
              if ( *(_QWORD *)(v925 + 40) && (*(_DWORD *)(*(_QWORD *)(v925 + 40) + 884LL) & 0x200) != 0 )
                XlFileProtocolManager::MarkOpenDone(v1157, 1, 0);
              HrRecordEvent(v1157, 0x40000000u, 1);
            }
            (*(void (__fastcall **)(struct IMsoOLDocument *, _QWORD, __int64))(*(_QWORD *)*v408 + 56LL))(*v408, 0, 7);
          }
          else
          {
            if ( v1178 )
            {
              v919 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
              OlDocFilePath::RecordEventForCloseOldoc(v919, v1157, 0);
            }
            _IMsoOLDocument_SetIReDownload(*v408, -1);
            if ( (*(unsigned int (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1157 + 208LL))(v1157) )
              MsoShipAssertTagProc(946484024);
            if ( lp )
            {
              v920 = *v408;
              if ( BOOK::Pioldoc(lp) == v920 && !(unsigned int)FOsrhInTransition() )
              {
                v921 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1430, 0x2369629Bu);
                v922 = SXVWGEOM::RwFirst(v921);
                BOOK::SetPioldoc(lp, 0, v922);
              }
            }
            v923 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1431, 0x2369629Au);
            v924 = SXVWGEOM::RwFirst(v923);
            OlDocFilePath::FReleaseIOLDoc(v408, 0, 1, v924);
            *v408 = 0;
          }
        }
        v926 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1304LL);
        *(_WORD *)(v926 + 56) &= ~8u;
        if ( !v1155 && !*(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 2436LL) )
        {
          if ( v1153 && lp && !(unsigned int)XLSWORKBOOK::FAddin((struct BOOK *)((char *)lp + 1640)) )
          {
            v927 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
            HrRegisterDynamicUdfs(v927, &v1193);
          }
          v928 = Mso::Telemetry::Activity::DataFields(v1213);
          LOBYTE(v929) = v1193;
          Mso::Telemetry::IDataFieldCollection::Add<bool>(v928, "FUdfNeedsRecalc", v929, 4);
        }
        if ( v1153 == 1 && lp && (v1194 != 256 || v1223 == 4) && (v1194 & 0xE80) == 0 )
        {
          VbaLoadRefBegin();
          if ( (sksEvt & 4) == 0 || (v930 = 1, v1318) )
            v930 = 0;
          HrBookLoadComplete(lp, v930, (struct LoadRecovery *)v68, 1, &v1207);
          if ( (unsigned int)FBookHasProject(lp, 1) )
          {
            v931 = HprojectFromPbook(lp);
            HrVbpSetDirty(v931, 0);
          }
          VbaLoadRefEnd();
          if ( !v1195 )
          {
            if ( v1157 )
            {
              v932 = BOOK::Pioldoc(lp);
              if ( v1157 == v932 )
              {
                v933 = XLSWORKBOOK::Pcm((struct BOOK *)((char *)lp + 1640));
                if ( CardView::DataElementRecord::FExpanded(v933) )
                  sub_1412CEFD0(lp);
              }
            }
          }
        }
        if ( lp )
          XLSWORKBOOK::PostDocumentLoad((char *)lp + 1640, 0, 0);
        if ( v1193 && !v1207 )
        {
          v934 = LOCATIONCONTEXTDATA::PWorkbookCur((LOCATIONCONTEXTDATA *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                     + 304LL)
                                                                         + 8LL));
          v935 = (OcsTransitionController *)PivotMetadataCache::PvMemProps(v934);
          v936 = OcsTransitionController::PCoauthTransitionState(v935);
          Api::RecalcService::HrRecalcAll(v936, 0);
        }
        if ( !v1153 || !lp || v1195 || !BOOK::Pioldoc(lp) || (v937 = BOOK::Pioldoc(lp), v938 = 1, v1157 != v937) )
          v938 = 0;
        if ( v938 )
          XlFileProtocolManager::MarkOpenDone(v1157, 1, 0);
        v939 = v1274;
        if ( !BKORWS::Psh(v1274) || !v938 )
          goto LABEL_1755;
        v940 = XLSWORKBOOK::Pcm((struct BOOK *)((char *)lp + 1640));
        if ( !CardView::DataElementRecord::FExpanded(v940) )
          goto LABEL_1750;
        v1203 = 0;
        v1204 = 0;
        if ( v68 && BOOK::FRepairedBookCloudFile(lp) )
        {
          v941 = BKORWS::Psh(v939);
          v942 = LoadRecovery::StmfOfRepair(v68);
          QuickLoadContext::SetWorkbookRepairStmf(v941, v942);
        }
        v943 = BKORWS::Psh(v939);
        v944 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
        v945 = v943;
        v946 = v1296;
        v947 = XlAsyncFileIO::HrHandlePostLoadTasks(v944, v1296, v945, &v1221, &v1203, &v1204);
        if ( v947 == -2147023673 )
        {
          v1319 = 0;
          Title = Mso::Swagger::Schema::GetTitle(v946);
          LOBYTE(v1048) = std::nullopt;
          v1049 = Title;
          if ( !(unsigned __int8)std::operator==<XlsActivity>(Title, v1048) )
          {
            v1050 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1360, 0x28572D2u);
            v1051 = SXVWGEOM::RwFirst(v1050);
            v1052 = (Mso::Telemetry *)std::_Optional_construct_base<XlsActivity>::operator*(v1049);
            Mso::Telemetry::SetActivityResultHr(v1052, (struct Mso::Telemetry::Activity *)v947, v1051, v1053);
          }
          v1054 = HrDoCloseBookCore(&v1319, 0, 0, 0, 1, 0, 0);
          if ( v1054 < 0 )
            XlsDiag::LogSetHrCoreTag(v1054, 0x280659Bu);
          lp = 0;
          sub_1402DA650(&v1541, v1333, v1055);
          fCeCanceled = 1;
          v114 = v947;
          XlsDiag::LogSetHrCoreTag(v947, 0x280659Cu);
          v1153 = 0;
          goto LABEL_1935;
        }
        if ( !v1203 )
        {
          BOOK::StartCoauth(lp, 1);
LABEL_1750:
          v954 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
          v955 = FeatureGateCollectionBase<GuidedReapplyFeatureGates>::Instance(v954);
          if ( (unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(v955 + 40) )
          {
            v956 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
            v1330 = 0;
            v957 = v956;
            Api::ReloadContext::RetrieveRctxFromWorkbook(v956, &v1330);
            if ( v1330 && Api::ReloadContext::FHasData(v1330) )
              Api::ReloadContext::RestoreCoauthPanesPostReload(v1330, v957);
            XlAsyncFileIO::ClearReloadContext(v957);
          }
LABEL_1755:
          if ( (unsigned __int8)CircularReferenceTailValue::FGetFlagsShadowBag(&vapp) && v68 )
          {
            LoadRecovery::StmfOfRepair(v68);
            FormatCh_ProcIds((void *const *)&vapp);
          }
          v959 = v1296;
          v960 = lp;
          if ( v1296 && lp && v1159 )
          {
            ZrtUtility::RenderWindowsPostContentNotification(lp, UIGLOBALS::UIGLOBALSCONTAINER::m_pwnChoEdit, v958);
            v961 = v1177;
            v962 = BOOK::Pioldoc(lp);
            ZrtUtility::LogZrtOpenInformation(v962, v959, (struct XlSyncStateChangeListenerLoad *)v961, v963);
            v960 = lp;
          }
          if ( v1153 == 1 )
          {
            if ( v960 )
            {
              if ( !(unsigned int)FOsrhBook(v960) )
              {
                v1205 = 0;
                v964 = CastOrNull<XLSWORKBOOK,BOOK>(lp);
                CoauthUtil::RunDuplicateUidCheck(v964, 2, &v1205);
                if ( v1205 )
                {
                  v965 = v1274;
                  if ( BKORWS::Psh(v1274) )
                  {
                    v966 = BKORWS::Psh(v965);
                    QuickLoadContext::SetCoauthStateChanged(v966, 1);
                  }
                }
              }
            }
          }
          v967 = L"and force template load";
          v968 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          v560 = *(_DWORD *)(v968 + 1836) == 0;
          v969 = *(const struct BOOK **)(v968 + 40);
          if ( v560 )
            v967 = &WindowName;
          Only = FPioldocReadOnly(v969);
          if ( lp )
            v971 = (*((_DWORD *)lp + 360) >> 1) & 0xF;
          else
            v971 = 0;
          LODWORD(v1128) = Only;
          LODWORD(v1126) = v971;
          XlsDiag::SendTraceTag(
            7091154,
            187,
            50,
            4,
            L"Loading workbook with Auto refresh load status: %d and read only mode: %d %s",
            v1126,
            v1128,
            v967);
          v972 = v1153;
          if ( v1153 && fShowWn )
          {
            v973 = lp;
            if ( lp && (*((_BYTE *)lp + 1440) & 0x10) == 0
              || (v974 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL),
                  *(_QWORD *)(v974 + 40))
              && (*(_DWORD *)(*(_QWORD *)(v974 + 40) + 884LL) & 0x200) != 0 )
            {
              v975 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
              if ( !*(_DWORD *)(v975 + 1836) )
              {
                if ( !lp )
                  v973 = *(struct BOOK **)(v975 + 40);
                v976 = v1173;
                v977 = BOOK::Pioldoc(v973);
                MsoSetReadWriteOnSaveIoldoc(v977, v976);
                LODWORD(v1127) = v1230;
                XlsDiag::SendTraceTag(
                  7091155,
                  187,
                  50,
                  4,
                  L"Check for XML Load Options value: %d prior to displaying business bar",
                  v1127);
                if ( ((v1230 - 1) & 0xFFFFFFFD) != 0 )
                {
                  v978 = 0;
                  if ( (int)sub_14046F720(v973) < 0 )
                  {
                    v979 = FPioldocReadOnly(v973);
                    v978 = (unsigned __int8)FIsTrue<int>(v979) != 0;
                  }
                  v980 = BOOK::Pioldoc(v973);
                  v1173 = MsoFReadWriteOnSaveIoldoc(v980) != 0;
                  if ( !BOOK::FFailedLockTransition(v973)
                    && !AsyncFileLockHandler::FPendingLockTransitionToState(v973, 0)
                    || (*((_DWORD *)v973 + 221) & 0x200) != 0 )
                  {
                    AssistedReading::ResetAssistedReading(v973, 8u, 0);
                  }
                  if ( v978 && Api::Workbook::FHasReadOnlyRecommended((struct BOOK *)((char *)v973 + 1640)) )
                  {
                    v1173 = 0;
                    v981 = BOOK::Pioldoc(v973);
                    MsoSetReadWriteOnSaveIoldoc(v981, 0);
                  }
                }
                FileLoad::ShowVersionFileBusBar(v1160, v973);
                if ( XLSWORKBOOK::Prdsharedmanager((struct BOOK *)((char *)v973 + 1640)) )
                {
                  v982 = XLSWORKBOOK::Prdsharedmanager((struct BOOK *)((char *)v973 + 1640));
                  LinkedEntityFeature = Api::RichDataSharedManager::GetLinkedEntityFeature(v982);
                  if ( Api::LinkedEntityFeature::FShouldShowFinanceBusinessBar(LinkedEntityFeature) )
                  {
                    if ( (unsigned int)FOsrc() )
                    {
                      OsrcSetFEverHadFinanceLinkedEntity(v973);
                    }
                    else
                    {
                      v984 = (RichDataManagerHost *)CastOrNull<XLSWORKBOOK,BOOK>(v973);
                      RichDataManagerHost::FShowFinanceBusinessBar(v984, v985);
                    }
                  }
                }
                v986 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)v973 + 1640));
                CleanupWorkbookStylesBusinessBar::ShowCleanupWorkbookStyleskBusinessBarIfNeeded(v986, v987);
                v972 = v1153;
                goto LABEL_1798;
              }
            }
          }
          else
          {
LABEL_1798:
            v973 = lp;
          }
          v988 = v1308;
          FileLoad::CheckAttemptRepair(
            v973,
            (struct LoadRecovery *)v68,
            v972,
            v1172,
            v1155,
            v1231,
            v1280,
            a10,
            v1308,
            &v1177,
            &v1281,
            &v1264,
            &v1218);
          if ( !v1281 )
          {
            if ( v1264 )
            {
LABEL_1994:
              v1071 = (CorruptionMetaData *)std::_Optional_construct_base<CorruptionMetaData>::operator*(v1538);
              CorruptionMetaData::MarkAsCorrupt(v1071);
              if ( !v68 )
                goto LABEL_2001;
              if ( (unsigned int)OfficeSharedApiImpl::UserFeedbackScreenshotInfo::GetScreenshotSourceType(v68) == -2147418113 )
              {
                v1073 = 459015;
                goto LABEL_2003;
              }
              v1072 = (Mso::History *)(unsigned int)v1177;
              if ( v1177 == -2134188030 || v1177 == -2134142954 )
              {
                v1320 = 256;
                MetroFGetErrorWz(v1177, v1575, &v1320);
                ErrorAlert(459023, v1575);
              }
              else
              {
LABEL_2001:
                if ( !Mso::History::IsVersionCrawlForRepairEnabled(v1072)
                  || (int)FileLoad::HrCheckVersionHistoryRepair(v1160) < 0 )
                {
                  v1073 = 458893;
LABEL_2003:
                  Error(v1073);
                }
              }
LABEL_2038:
              if ( v1153 )
              {
LABEL_2039:
                if ( (a10 & 0x20) != 0 && (unsigned int)FHpshtiFromStt(&v1452, 50) )
                  *((_QWORD *)v1452 + 3) = lp;
              }
              if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                         + 872LL)
                             + 8LL)
                  & 1) == 0
                && v1153
                && lp )
              {
                v1083 = Measurements::Stopwatch::Stopwatch((Measurements::Stopwatch *)v1534);
                LOBYTE(v1084) = 1;
                Measurements::MeasureElapsedTime::MeasureElapsedTime(
                  v1527,
                  Measurements::MeasurementId::ExcelPQEventing,
                  v1084,
                  v1083);
                v1085 = (struct Api::Workbook *)CastOrNull<XLSWORKBOOK,BOOK>(lp);
                XLSEVENTDISPATCHER::HrOnWorkbookOpen(v1085);
                v1206 = 0;
                if ( PowerQueryManager::FPowerQueryIEVersionCheckFailed() )
                {
                  Manager = Api::Workbook::PPowerQueryManager((struct BOOK *)((char *)lp + 1640));
                  if ( (*(int (__fastcall **)(struct IPowerQueryWorkbookManager *, char *))(*(_QWORD *)Manager + 224LL))(
                         Manager,
                         &v1206) >= 0 )
                  {
                    if ( v1206 )
                    {
                      v1087 = BOOK::Pioldoc(*(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                 + 304LL)
                                                     + 40LL));
                      ShowPowerQueryIEBusBar(v1087);
                    }
                  }
                }
                Measurements::MeasureElapsedTime::~MeasureElapsedTime((Measurements::MeasureElapsedTime *)v1527);
                v1088 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL);
                if ( *(_DWORD *)(v1088 + 104) == 1 )
                {
                  *((_DWORD *)lp + 644) |= 0x20u;
                }
                else if ( *(_DWORD *)(v1088 + 104) == 2 )
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
                    v1089 = IdwaFromIds(458968);
                    MsoDoWatsonAlertBegin(v1089, 0, 0, (struct WADD *)v1547);
                  }
                  v1090 = v1185 & 4;
                  if ( (a10 & 0x20) != 0 || (v1091 = FOsrhInTransition(), v1092 = 0, v1091) )
                    v1092 = 1;
                  v1093 = XlUIMockable::HrShowRecoveryErrors2(lp, v1092, v1090, 0);
                  v604 = v1093;
                  if ( (_BYTE)v264 )
                  {
                    if ( v1093 < 0 )
                    {
LABEL_1742:
                      v1166 = v604;
                      goto LABEL_1133;
                    }
                  }
                  else if ( v1093 < 0 )
                  {
                    v800 = 512506015;
                    v801 = (MsoReserveTag *)&v1362;
                    goto LABEL_1925;
                  }
                  if ( *((char *)lp + 892) >= 0 )
                  {
                    std::optional<EditCommandTrackingFreezer>::optional<EditCommandTrackingFreezer>(v1241);
                    v1094 = FeatureGateCollectionBase<CoauthFeatureGates>::Instance();
                    if ( (unsigned __int8)Mso::AB::Optimized::FeatureGate::operator bool(v1094 + 408) )
                      std::optional<EditCommandTrackingFreezer>::emplace<>(v1241);
                    v1095 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1363, 0x231C69Fu);
                    v1096 = SXVWGEOM::RwFirst(v1095);
                    BookDirty(lp, 1, v1096);
                    std::optional<EditCommandTrackingFreezer>::~optional<EditCommandTrackingFreezer>(v1241);
                  }
                  if ( *((_QWORD *)lp + 162) )
                    MsoDoWatsonAlertEnd((struct WADD *)v1547, *((const wchar_t **)lp + 163));
                }
                v1097 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                v1098 = *(_QWORD *)(v1097 + 872);
                if ( *(_DWORD *)(v1098 + 104) != 1 && (*(_BYTE *)(v1098 + 8) & 1) == 0 )
                {
                  v1099 = *(_QWORD *)(v1097 + 1328);
                  if ( *(_DWORD *)(v1099 + 20) )
                  {
                    Sz = 0;
                    if ( wverLastXLSaved < 3 || *(char *)(v1099 + 20) < 0 )
                      Sz = CchLoadSz(v1571, 327873, 256);
                    v1101 = CchLoadSz(&v1571[Sz], 327874, 256 - Sz);
                    v1102 = (__int64 *)NtCurrentTeb()->ThreadLocalStoragePointer;
                    v1103 = v1101 + Sz;
                    v540 = *v1102;
                    v1104 = *(_QWORD *)(*(_QWORD *)(*v1102 + 304) + 1328LL);
                    if ( (*(_DWORD *)(v1104 + 20) & 0x10) == 0 && *(char *)(v1104 + 20) >= 0 )
                      goto LABEL_2080;
                    v1105 = -1161035032;
                    *(_DWORD *)(v1104 + 20) &= (*(_DWORD *)(v1104 + 20) & 0x10) != 0 ? -17 : -129;
                    while ( 1 )
                    {
                      v1103 += CchLoadSz(&v1571[v1103], v1105, 256 - v1103);
LABEL_2080:
                      v1106 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                        + 1328LL);
                      v1107 = *(_DWORD *)(v1106 + 20);
                      if ( (v1107 & 0x20) != 0 )
                      {
                        v1105 = -1161035031;
                        v1108 = v1107 & 0xFFFFFFDF;
                      }
                      else
                      {
                        if ( (v1107 & 0x40) == 0 )
                        {
                          v541 = 512;
                          if ( (unsigned __int64)(2LL * v1103) < 0x200 )
                          {
                            v1571[v1103] = 0;
                            ShowAlert(10, 458968, v1571, 0, 0, 0);
                            goto LABEL_1954;
                          }
LABEL_2137:
                          _report_rangecheckfailure(v541, v540);
                        }
                        v1105 = -1161035030;
                        v1108 = v1107 & 0xFFFFFFBF;
                      }
                      *(_DWORD *)(v1106 + 20) = v1108;
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
                && !v1153 )
              {
                v1074 = v1177;
                if ( v1177 == -2147023673 || v1177 == -2147467260 || *(&vscd + 1) )
                {
                  if ( *(&vscd + 1) )
                  {
                    v114 = -2147467260;
                    v1075 = 33931969;
                    v1074 = -2147467260;
                    goto LABEL_2015;
                  }
                  v114 = v1177;
                  if ( v1177 < 0 )
                  {
                    v1075 = 33931970;
LABEL_2015:
                    XlsDiag::LogSetHrCoreTag(v1074, v1075);
                  }
                  v1076 = 0;
                  v1077 = 458924;
LABEL_2028:
                  OkAlert(v1077, v1076);
                  goto LABEL_2038;
                }
              }
              if ( *((char *)PivotOperationBase::PSxview((PivotOperationBase *)v68) + 36) < 0 )
              {
                if ( v1153 )
                {
                  AffectedProcessSessionId = (ODFROBUSTLOAD *)OfficeSharedApiImpl::UserFeedbackV2Config::GetAffectedProcessSessionId(v68);
                  if ( ODFROBUSTLOAD::FRepairAlertDisplayed(AffectedProcessSessionId) )
                  {
                    CchLoadSz(v1577, -1161035131, 255);
                    v1079 = v1577;
                    v1080 = 467262;
                    goto LABEL_2037;
                  }
                  if ( v1153 )
                    goto LABEL_2039;
                }
                v1081 = (ODFROBUSTLOAD *)OfficeSharedApiImpl::UserFeedbackV2Config::GetAffectedProcessSessionId(v68);
                if ( ODFROBUSTLOAD::FPasswordHashFound(v1081) )
                {
                  v114 = -2147467260;
                  XlsDiag::LogSetHrCoreTag(-2147467260, 0x205C2C3u);
                  v1077 = 459071;
                }
                else
                {
                  if ( v1153 )
                    goto LABEL_2039;
                  v1082 = (ODFROBUSTLOAD *)OfficeSharedApiImpl::UserFeedbackV2Config::GetAffectedProcessSessionId(v68);
                  if ( !ODFROBUSTLOAD::FBadNullDate(v1082) )
                    goto LABEL_2038;
                  v114 = -2147467260;
                  XlsDiag::LogSetHrCoreTag(-2147467260, 0x205C2C4u);
                  v1077 = 459072;
                }
                v1076 = v1568;
                goto LABEL_2028;
              }
            }
            if ( !v1187
              || !(unsigned int)Mso::Details::ConstexprFunctorBase<Mso::IFunctor<bool,FeaturePropertyValue const &,FeaturePropertyValue const &>>::Release(&vapp)
              || (unsigned int)FOsrhInTransition()
              || (unsigned int)FOsrc() )
            {
              goto LABEL_2038;
            }
            CchSzToSt(*((const wchar_t **)v1342 + 3), v1574, 255);
            SuppressStExt(v1574, 255);
            if ( v1153 )
            {
              CchInsert2St(v1573, 459073, &v1567, v1574, 255);
              v1080 = 467265;
            }
            else
            {
              v114 = -2146827284;
              XlsDiag::LogSetHrCoreTag(-2146827284, 0x205C2C5u);
              CchInsert2St(v1573, 459075, &v1567, v1574, 255);
              v1080 = 467267;
            }
            v1079 = v1573;
LABEL_2037:
            OkInfoAlert(v1080, v1079);
            goto LABEL_2038;
          }
          if ( v1264 )
            goto LABEL_1994;
          if ( v1172 && !(unsigned int)FOsrcHostedByExcel() )
          {
            SetLoadForPreviewError(-2042494972);
            v1218 = 0;
            v1162 = 0;
            goto LABEL_1826;
          }
          if ( !v1218 )
          {
            v989 = FOsrhInTransition();
            v1162 = FIsTrue<int>(v989);
            if ( v1162 || (unsigned __int8)CircularReferenceTailValue::FGetFlagsShadowBag(&vapp) || (v990 = 0, v1159) )
              v990 = 1;
            v1162 = v990;
            if ( !v990 )
            {
              if ( v1240 && !MsoFDrmUIEnabled() )
              {
                Error(589882);
                goto LABEL_1826;
              }
              if ( (unsigned int)FOsrc() )
              {
                Osrc = GetOsrc();
                v992 = OSRC::DwPromptUser(Osrc, 0, 0, 0, 0, 0);
                v1162 = v992 != 0;
                if ( !v992 )
                  SetLoadForPreviewError(-2147467260);
                goto LABEL_1826;
              }
              if ( v1273 && VersionHistoryWindowParams::FSkipCorruptVersionOpens(v1273) )
              {
                v993 = 504443348;
LABEL_1822:
                v114 = -2146827284;
                XlsDiag::LogSetHrCoreTag(-2146827284, v993);
                v988 = v1308;
                goto LABEL_1826;
              }
              if ( (unsigned int)Art::IOMHost::GetEnvId((Art::IOMHost *)&vapp) )
              {
                if ( (unsigned int)YesNoAlert(458912, v1568) != 6 )
                {
                  v114 = -2146827284;
                  XlsDiag::LogSetHrCoreTag(-2146827284, 0x230E208u);
                  goto LABEL_1826;
                }
              }
              else if ( (unsigned int)XlUIMockable::NoYesAlert(458912, v1568) != 6 )
              {
                v993 = 36758023;
                goto LABEL_1822;
              }
              v1162 = 1;
            }
          }
LABEL_1826:
          v994 = (CorruptionMetaData *)std::_Optional_construct_base<CorruptionMetaData>::operator*(v1538);
          CorruptionMetaData::MarkAsCorrupt(v994);
          if ( !v1218 && !v1162 )
            goto LABEL_2038;
          if ( v1231 || (*((_BYTE *)PivotOperationBase::PSxview((PivotOperationBase *)v68) + 36) & 2) != 0 )
          {
            BookCorrupt = LoadRecovery::GrbitGetBookCorrupt((LoadRecovery *)v68);
            v1002 = PivotMetadataCache::PvMemProps((PivotMetadataCache *)v68);
            LoadRecovery::HrHandleLoadMode((LoadRecovery *)v68, v1002 == (void *)BookCorrupt);
            LoadRecovery::HrHandleLoadMode((LoadRecovery *)v68, v1231);
            v1003 = LoadRecovery::GrbitGetBookCorrupt((LoadRecovery *)v68);
            LoadRecovery::GrbitSetBookCorruptOld((LoadRecovery *)v68, v1003);
          }
          else
          {
            if ( !v68 || (v44 = (int)LoadRecovery::Lrmode(v68) <= 0, v995 = 1, v44) )
              v995 = 0;
            v996 = (LoadRecovery *)v68;
            if ( v995 )
            {
              LoadRecovery::IncrementRepairAttemptCount((LoadRecovery *)v68);
              if ( LoadRecovery::CGetPartCount((LoadRecovery *)v68) < v988 )
              {
                v997 = 1;
                v996 = (LoadRecovery *)v68;
                goto LABEL_1844;
              }
              if ( v988 )
              {
                if ( LoadRecovery::CGetPartCount((LoadRecovery *)v68) == v988 )
                {
                  v998 = LoadRecovery::CGetIRTCount((LoadRecovery *)v68);
                  if ( v998 <= v1341 )
                  {
                    v999 = v988 - 1;
                    v1000 = LoadRecovery::FNoProgressOnPart((LoadRecovery *)v68, v999);
                    v996 = (LoadRecovery *)v68;
                    if ( v1000 )
                    {
                      v997 = 1;
                      goto LABEL_1844;
                    }
                    if ( !LoadRecovery::FCorruptPart((LoadRecovery *)v68, v999) )
                    {
                      LoadRecovery::SetCorruptPart((LoadRecovery *)v68, v999);
                      LoadRecovery::SetFNoProgressOnPart((LoadRecovery *)v68, v999);
                    }
                  }
                }
              }
            }
            else
            {
              v997 = 0;
LABEL_1844:
              LoadRecovery::HrHandleLoadMode(v996, v997);
            }
            v1341 = LoadRecovery::CGetIRTCount((LoadRecovery *)v68);
            v1308 = LoadRecovery::CGetPartCount((LoadRecovery *)v68);
          }
          ClearStatusString(11);
          if ( (unsigned int)LoadRecovery::Lrmode(v68) == 1 )
          {
            if ( !v1218 )
            {
              v1004 = 1752853862;
              goto LABEL_1851;
            }
          }
          else
          {
            v1004 = 1752853863;
LABEL_1851:
            MsoShipAssertTagProc(v1004);
            v1218 = 1;
          }
          if ( v1159 )
            goto LABEL_744;
          v1005 = LoadRecovery::Lrmode(v68);
          SetLoadRecovery(v1005);
          v1006 = MaxPathHolder::CchMaxPath();
          v1007 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1462);
          v1008 = v1006;
          v69 = v1160;
          CchStToSt(v1007, v1160, v1008);
          v1269 = 0;
          sub_1402DA650(&v1541, v1333, v1009);
          goto LABEL_745;
        }
        OsfOpenScope::OpenCompleted((OsfOpenScope *)v1485);
        v1186 = 0;
        (*(void (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1157 + 8LL))(v1157);
        v948 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
        v949 = XlAsyncFileIO::PxlasyncFileIOFromWorkbook(v948);
        if ( v949 )
          XlAsyncFileIO::NotifyWorkbookInClose(v949, 1);
        v950 = FeatureGateCollectionBase<CoauthFeatureGates>::Instance();
        if ( (unsigned __int8)Mso::AB::Optimized::FeatureGate::operator bool(v950 + 472) )
          BOOK::SetFCloseForReopen(lp, 1);
        v951 = HrFreeBook2(lp);
        v604 = v951;
        if ( (_BYTE)v264 )
        {
          if ( v951 < 0 )
            goto LABEL_1742;
        }
        else if ( v951 < 0 )
        {
          v800 = 512506016;
          v801 = (MsoReserveTag *)&v1359;
          goto LABEL_1925;
        }
        lp = 0;
        if ( v1204 )
          (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v1157 + 56LL))(v1157, 1, 7);
        v952 = v1171 != 0;
        v1171 = -v1171;
        FBeginCmdIOLDoc(v1157, v952 ? 4 : 2, 0, &v1232, 0);
        if ( v1246 )
        {
          (*(void (__fastcall **)(struct IMsoPKMClient *))(*(_QWORD *)v1246 + 184LL))(v1246);
          v1246 = 0;
        }
        sub_1402DA650(&v1541, v1333, v953);
        XlsActivity::ResetStoredTagData(v1213);
LABEL_744:
        v69 = v1160;
LABEL_745:
        if ( v1159 && (v1155 || v1162) )
        {
          if ( v1157 )
          {
            if ( v1178 )
              HrRecordEvent(v1157, 0x40000000u, 0);
            if ( *v408 )
            {
              v1056 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1361, 0x23696299u);
              v1057 = SXVWGEOM::RwFirst(v1056);
              OlDocFilePath::FReleaseIOLDoc(v408, 1, 1, v1057);
            }
          }
          Mso::TCntPtr<IOfficeSolutionFramework>::TCntPtr<IOfficeSolutionFramework>(v1310);
          v1058 = MaxPathHolder::SzPath((MaxPathHolder *)v1462);
          v1059 = MsoPIOLDocFindWithWzPersistentName(v1058);
          Mso::TCntPtr<IMsoOLDocument>::Attach(v1310, v1059);
          if ( (unsigned __int8)std::shared_ptr<Mso::ActivityScope::IMsoLoggingScope>::operator bool(v1310) )
          {
            v1061 = BKORWS::Psh((BKORWS *)v1310);
            ZrtUtility::OptOutOfServerOnlyAsyncOpen(v1061, v1062);
          }
          if ( v1155 )
            XslClear((struct XSL *)&v1541);
          LOBYTE(v1060) = std::nullopt;
          if ( !(unsigned __int8)sub_14240D428(v1524, v1060) )
          {
            v1063 = sub_14240D5FC(v1524);
            sub_141836A58(v1063);
          }
          v114 = -1491861503;
          v1153 = -1491861503;
          XlsDiag::LogSetHrCoreTag(-1491861503, 0x300B394u);
          Mso::TCntPtr<Uxpp::UxppAnnotationsService>::~TCntPtr<Uxpp::UxppAnnotationsService>(v1310);
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
                v114 = -2146827284;
                XlsDiag::LogSetHrCoreTag(-2146827284, 0x23404CEu);
                v1064 = (CorruptionMetaData *)std::_Optional_construct_base<CorruptionMetaData>::operator*(v1538);
                CorruptionMetaData::MarkAsCorrupt(v1064);
                Error(327845);
              }
              LoadRecovery::Destroy((LoadRecovery *)v68);
              FreeHpst(v68);
              v68 = 0;
              v1233 = 0;
            }
          }
          if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                         + 8LL)
              & 1) == 0
            && v1153
            && lp
            && !(unsigned int)FBookAddin(lp)
            && (*((_DWORD *)lp + 222) & 0x804000) == 0
            && (a10 & 0x20) == 0
            && (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 864LL)
                          + 24LL)
              & 0x40000) == 0
            && !v1172 )
          {
            XLDRPPERS::XLDRPPERS((XLDRPPERS *)v1563);
            memset_0(v1563, 0, 0x308u);
            v1065 = Api::Workbook::FtFileType((char *)lp + 1640);
            v1066 = 1;
            LOBYTE(v1131) = 0;
            LOBYTE(v1129) = 1;
            v1563[0] = (2 * v1065) | v1563[0] & 0xFFFFFE01;
            if ( v1155 )
              v1066 = 65537;
            LODWORD(v1124) = 1;
            if ( (unsigned int)FSaveRecoveryDrp(lp, 0, 0, v1066, v1124, v1563, 0, v1129, v1131) )
              *((_DWORD *)lp + 320) = 1;
          }
          if ( lp )
            *((_DWORD *)lp + 222) &= ~0x800000u;
          if ( v1174
            && (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                         + 8LL)
              & 1) == 0
            && v1153
            && lp
            && (v1194 == 5 || v1194 == 16)
            && !v1172 )
          {
            FileLoad::CheckShared(lp);
          }
          v1067 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          if ( (*(_BYTE *)(*(_QWORD *)(v1067 + 872) + 8LL) & 1) == 0 && v1153 && lp && !v1172 )
          {
            if ( !*(_DWORD *)(*(_QWORD *)(v1067 + 1232) + 80LL) && !(unsigned int)FOsrhBook(lp) )
              v73 = 0;
            v1068 = BOOK::Pioldoc(lp);
            MsoHrSimpleOfflineOpenFile(
              v1068,
              (int (__high *)(enum MSOSCA, struct IMsoOLDocument *, unsigned int))&HrSimpleOfflineUser,
              v73);
          }
          ResetLoadRecovery();
          v1069 = lp;
          if ( lp )
          {
            FShowTrustBar(lp);
            *((_DWORD *)lp + 222) &= ~0x8000000u;
            v1069 = lp;
          }
          v1070 = HrFileCompleteLoadEx(
                    v1160,
                    hObject,
                    v1153,
                    v1182,
                    v1069,
                    v1176,
                    v1165,
                    (struct LoadRecovery *)v68,
                    v1300,
                    v1220,
                    v1195 != 0,
                    v1246,
                    v1251,
                    v1159,
                    v1157,
                    v1270,
                    v1302,
                    v1181,
                    v114,
                    (const struct MaxPathHolder *)v1340,
                    v1175,
                    v1254,
                    (struct OsfOpenScope *)v1485,
                    (const struct XLOSRR *)&v1235,
                    v1334);
          goto LABEL_1992;
        }
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1220;
        FRemoveLoadAction((struct LoadRecovery *)v68, 0);
        XlsActivity::SetSuccessful(v1213);
        std::_Optional_destruct_base<CorruptionMetaData,0>::~_Optional_destruct_base<CorruptionMetaData,0>(v1538);
        v1450[0] = APPCORE::PmemheapMain((APPCORE *)&vapp);
        std::optional<CorruptionMetaData>::emplace<IMemHeap *>(v1538, v1450);
        v1450[1] = BKORWS::Psh(v1274);
        std::optional<OlDocFilePath>::emplace<QuickLoadContext *>((OlDocFilePath *)v1539);
        ++v1271;
        v409 = (__int64 *)NtCurrentTeb()->ThreadLocalStoragePointer;
        v60 = v1298;
        v1153 = 0;
        v1194 = 256;
        v1223 = 0;
        lp = 0;
        v1232 = 0;
        v410 = *v409;
        v1169 = 0;
        v1297 = 0;
        v1268 = 0;
        v411 = *(_QWORD *)(v410 + 304);
        v1275 = 0;
        v1331 = 0;
        v1188 = 0;
        v412 = *(_QWORD *)(v411 + 1304);
        v1163 = 0;
        v1164 = 0;
        *(_WORD *)(v412 + 56) &= ~8u;
        if ( v1251 )
        {
          (*(void (__fastcall **)(struct IMsoDocumentEncryptor *))(*(_QWORD *)v1251 + 16LL))(v1251);
          v1251 = 0;
        }
        goto LABEL_79;
      }
LABEL_1105:
      errDeferred = 0;
      v590 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
      if ( *(_QWORD *)(v590 + 40) && (*(_DWORD *)(*(_QWORD *)(v590 + 40) + 884LL) & 0x200) != 0 )
      {
        RenumberWind(*(struct SH **)(v590 + 32));
        v591 = v1297;
        v592 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        *(_DWORD *)(v592 + 2024) = 0;
        *(_DWORD *)(v592 + 2028) = 0;
        v593 = *(const struct BOOK **)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        *((_QWORD *)v593 + 42) = v1220;
        LOBYTE(v264) = 0;
        goto LABEL_1549;
      }
      if ( v1153 != 2 )
      {
LABEL_1360:
        v720 = v1154;
        v408 = v1161;
        goto LABEL_1361;
      }
      if ( *(_DWORD *)(*(_QWORD *)(v590 + 872) + 104LL) == 2 )
      {
        if ( OSRR::FOsrCandidate((OSRR *)&v1235) )
        {
          OSRR::SetAppReady((OSRR *)&v1235, 1);
LABEL_764:
          v1155 = 1;
          goto LABEL_743;
        }
        v594 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1339);
        v595 = HrLoadDataRecover(v1167, v264, &v1567, 257, v594, a5, 0, v1185, (struct LoadRecovery *)v68);
        v1152 = v595;
        v114 = v595;
        if ( v595 < 0 )
          XlsDiag::LogSetHrCoreTag(v595, 0x2156755u);
        v596 = v1154;
        v1153 = v114 >= 0;
        if ( v1154 )
        {
          if ( (unsigned int)IMsoOLDocument::IsInFileSys(v1157) )
          {
            if ( v1153
              || (v597 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL),
                  *(_QWORD *)(v597 + 40))
              && (*(_DWORD *)(*(_QWORD *)(v597 + 40) + 884LL) & 0x200) != 0 )
            {
              v598 = (wchar_t **)XLSBOOK::Plxtab(*(XLSBOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                         + 304LL)
                                                             + 40LL));
              FreeHpstTempPath((struct STB *)v598);
              v599 = FileSource::StzFilePath((FileSource *)v1305);
              if ( (int)HrStDupSt(v599, v598 + 21) < 0 )
                v598[21] = 0;
            }
          }
        }
        v1215 = 0;
LABEL_1272:
        if ( v1153 )
          v1194 = 5;
        if ( v1542 )
        {
          if ( v1157 )
          {
            (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v1157 + 56LL))(
              v1157,
              0xFFFFFFFFLL,
              7);
            if ( v1178 )
              HrRecordEvent(v1157, 0x40000000u, 0);
            v667 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1411, 0x2369629Eu);
            v668 = SXVWGEOM::RwFirst(v667);
            OlDocFilePath::FReleaseIOLDoc(v1161, 1, v1153 == 0, v668);
          }
          v669 = v1299;
          v1178 = v1189;
          v1157 = v1299;
        }
        else
        {
          v669 = v1157;
        }
        if ( v1239 == -2 )
        {
          v68 = v1158;
          goto LABEL_1360;
        }
        v702 = 0;
        v703 = 0;
        v704 = 0;
        v705 = 0;
        if ( v1178 )
        {
          v702 = 0;
          if ( !v1153 )
          {
            v706 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
            if ( !*(_QWORD *)(v706 + 40) || (*(_DWORD *)(*(_QWORD *)(v706 + 40) + 884LL) & 0x200) == 0 )
              v702 = 1;
          }
          HrRecordEvent(v669, 0x40000000u, !v702);
          v703 = v702;
          v1178 = 0;
          v705 = v702;
          v704 = v702;
        }
        v707 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        if ( *(_QWORD *)(v707 + 40) != v1301 )
        {
          v702 = v703;
          v704 = v705;
          if ( v1153 )
          {
            if ( *(_QWORD *)(v707 + 40) )
            {
              if ( v1260 )
              {
                v708 = OLDocFactory::PInstance();
                v1217 = (*(__int64 (__fastcall **)(const struct OLDocFactory *, _QWORD, struct IMsoOLDocument **))(*(_QWORD *)v708 + 56LL))(
                          v708,
                          0,
                          &v1346);
                v1217 = (*(__int64 (__fastcall **)(struct IMsoOLDocument *, __int64, _QWORD))(*(_QWORD *)v1157 + 96LL))(
                          v1157,
                          8,
                          0);
                v1217 = (*(__int64 (__fastcall **)(struct IMsoOLDocument *, __int64, _QWORD, _QWORD))(*(_QWORD *)v1157 + 112LL))(
                          v1157,
                          0x40000000,
                          0,
                          0);
                v1217 = (*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1157 + 16LL))(v1157);
                *v1161 = v1346;
                v1157 = v1346;
              }
              v709 = *(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL);
              v710 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1412, 0x2369629Cu);
              v711 = SXVWGEOM::RwFirst(v710);
              BOOK::SetPioldoc(v709, v1157, v711);
              LOBYTE(v712) = 1;
              if ( (unsigned __int8)FeatureExposure::FRunLicensedFeature(v712) )
              {
                v713 = NtCurrentTeb()->ThreadLocalStoragePointer;
                v1304 = -1;
                v714 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v713 + 304LL) + 32LL);
                v715 = 0;
                if ( (*(_BYTE *)(v714 + 10) & 4) == 0 )
                  v715 = *(_BYTE *)(v714 + 8);
                v716 = FtDefault(v715);
                if ( (unsigned __int8)FShouldShowDataLossBusBar(v716, &v1304) )
                  ShowDataLossBusBarIfNeeded(
                    *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL),
                    v1304);
              }
            }
            v68 = v1158;
            goto LABEL_1360;
          }
        }
        v408 = v1161;
        _IMsoOLDocument_SetIReDownload(*v1161, -1);
        v717 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1413, 0x2369629Du);
        v718 = SXVWGEOM::RwFirst(v717);
        if ( v1153 )
        {
          v719 = 0;
          v702 = v704;
        }
        else
        {
          v719 = 1;
        }
        OlDocFilePath::FReleaseIOLDoc(v408, !v702, v719, v718);
        if ( v596 )
          *v408 = 0;
        v68 = v1158;
        v720 = 0;
        v1154 = 0;
LABEL_1361:
        v721 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
        v722 = (LXBASE *)OpenTelemetry::POpenFileStageModel(v721);
        v723 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1414, 0x1F0CB5C2u);
        SXVWGEOM::RwFirst(v723);
        WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v722);
        v724 = FeatureGateCollectionBase<CoauthFeatureGates>::Instance();
        if ( !(unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(v724 + 1680) || v1153 )
          lp = *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL);
        v725 = NtCurrentTeb()->ThreadLocalStoragePointer;
        vhpstErrPath = 0;
        v726 = *(_QWORD *)(*(_QWORD *)v725 + 304LL);
        *(_DWORD *)(v726 + 2024) = 0;
        *(_DWORD *)(v726 + 2028) = 0;
        v1202 = 0;
        v727 = sub_140430470(lp);
        v728 = v1151;
        v604 = v727;
        if ( v1151 )
        {
          if ( v727 < 0 )
          {
LABEL_1132:
            v1166 = v604;
            goto LABEL_1133;
          }
        }
        else if ( v727 < 0 )
        {
          v800 = 512506050;
          v801 = (MsoReserveTag *)&v1365;
          goto LABEL_1925;
        }
        if ( v1202 )
        {
          lp = 0;
          v73 = 1;
          goto LABEL_744;
        }
        if ( v720 )
        {
          sub_14046D5A0(v1157);
          if ( Mso::DocumentWindow::EventMgr::IsDocumentWindowEventManagerEnabled(v729) )
            sub_140431960(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL));
        }
        if ( v1153 )
        {
          if ( lp )
          {
            v730 = (WN *)*((_QWORD *)lp + 53);
            if ( v730 )
            {
              v731 = WN::Puiframe(v730);
              v732 = (struct IMsoOLDocument *)UIFRAME::HwndFrame(v731);
              v733 = BOOK::Pioldoc(lp);
              Excel::XlMso::EmitOpenEventForOLDocument(v733, v732, v734);
            }
          }
          if ( v1153 )
          {
            if ( lp )
            {
              if ( !v1195 )
              {
                if ( BOOK::Pioldoc(lp) )
                {
                  v735 = BOOK::Pioldoc(lp);
                  if ( v1157 == v735 && !(unsigned int)FIsLocalVersionXL(v1160) )
                  {
                    v736 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
                    v737 = Api::Workbook::FtFileType((char *)lp + 1640);
                    if ( (unsigned __int8)CoauthUtil::FValidXluidLoadedFt(v737, v736) )
                      XLSWORKBOOK::SetFValidUidStateLoaded((struct BOOK *)((char *)lp + 1640), 1);
                    if ( !XLSWORKBOOK::FValidUidStateLoaded((struct BOOK *)((char *)lp + 1640)) )
                    {
                      v738 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
                      CoauthUtil::CreateValidUidStateOnLoad(v738);
                    }
                    if ( v1168 )
                    {
                      Protocol = XlFileProtocolManager::GetProtocol(v1157);
                      if ( !Protocol )
                      {
                        MsoShipAssertTagProc(506056966);
                        v1043 = 506056965;
                        v604 = -2147418113;
                        goto LABEL_2135;
                      }
                      v740 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1415, 0x1E1968DCu);
                      XlFileProtocol::TakeZipItScheduler(Protocol, v1347, *(unsigned int *)v740);
                      v741 = lp;
                      v742 = *(_DWORD *)MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1416, 0x1E1968DBu);
                      v743 = BKORWS::Psh((BKORWS *)v1347);
                      XLSWORKBOOK::SetZipItScheduler((char *)v741 + 1640, v743, v742);
                      Mso::TCntPtr<IWebAddInOptionalProperties>::~TCntPtr<IWebAddInOptionalProperties>(v1347);
                    }
                    v744 = FeatureGateCollectionBase<CoauthFeatureGates>::Instance();
                    if ( (unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(v744 + 1264) )
                    {
                      LOBYTE(v745) = std::nullopt;
                      if ( !(unsigned __int8)std::operator==<CoauthoringInternals::RecoveredFileCoauthorableState>(
                                               &CoauthoringInternals::s_optRecoveredFileCoauthorableState,
                                               v745) )
                      {
                        v746 = (_DWORD *)std::optional<CoauthoringInternals::RecoveredFileCoauthorableState>::operator->(&CoauthoringInternals::s_optRecoveredFileCoauthorableState);
                        *((_DWORD *)lp + 320) = *v746;
                        v747 = std::optional<CoauthoringInternals::RecoveredFileCoauthorableState>::operator->(&CoauthoringInternals::s_optRecoveredFileCoauthorableState);
                        *((_QWORD *)lp + 161) = *(_QWORD *)(v747 + 8);
                      }
                    }
                    BOOKO::UpdateCoauth((struct BOOK *)((char *)lp + 1640), 1);
                    v748 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
                    v749 = XlAsyncFileIO::PxlasyncFileIOFromWorkbook(v748);
                    if ( v749 )
                    {
                      v750 = XlAsyncFileIO::Pxlrh(v749);
                      XlRenameHandler::HrCheckForRenameOnFileLoad(v750);
                    }
                    v751 = 0;
                    if ( (unsigned __int8)std::shared_ptr<Mso::ActivityScope::IMsoLoggingScope>::operator bool(&v1252) )
                    {
                      v752 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1252);
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v752 + 48LL))(v752);
                      v753 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1252);
                      v751 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v753 + 128LL))(v753, 0);
                    }
                    v754 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
                    v755 = IMerge::PMergeFromWorkbook(v754);
                    if ( v755 )
                    {
                      v756 = (*(__int64 (__fastcall **)(struct IMerge *))(*(_QWORD *)v755 + 216LL))(v755);
                      v757 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v756 + 288LL))(v756);
                      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v757 + 48LL))(v757, v751);
                    }
                    v1328 = 0;
                    v758 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
                    Api::ReloadContext::RetrieveRctxFromWorkbook(v758, &v1328);
                    if ( v1328 && Api::ReloadContext::FValid(v1328) )
                    {
                      v1181 = 1;
                      v759 = Mso::Telemetry::Activity::DataFields(v1213);
                      refreshed = Api::ReloadContext::RefreshType(v1328);
                      v761 = Api::ReloadContext::SzFromBookRefreshType(refreshed);
                      Mso::Telemetry::IDataFieldCollection::Add(v759, "RefreshType", v761, 4);
                    }
                    if ( BKORWS::Psh((struct BOOK *)((char *)lp + 3088)) )
                    {
                      v762 = BKORWS::Psh((struct BOOK *)((char *)lp + 3088));
                      IEndpointAgent::HrLoadComplete(v762);
                    }
                    v763 = XLSWORKBOOK::ClpManager((struct BOOK *)((char *)lp + 1640));
                    ClassifyLabelProtectManager::OnLoadComplete(v763);
                    if ( IdleLoop::FEnabled(v764) )
                    {
                      v765 = FeatureGateCollectionBase<PerformanceFeatureGates>::Instance();
                      if ( (unsigned __int8)Mso::AB::Optimized::FeatureGate::operator bool(v765 + 416) )
                        UpdateCLPLabelIndicator(lp);
                    }
                    v766 = APPCORE::PautoSaveManager((APPCORE *)&vapp);
                    AutoSaveManager::SetAutoSaveStatusOnFileLoad(v766, lp);
                    Copilot::EvaluatePrerequisitesForBook((struct BOOK *)((char *)lp + 1640), v767);
                  }
                }
              }
            }
          }
        }
        if ( v1170 )
          ApplyRevert(v1269, (const struct REVARG *)v1565, v1153);
        v1269 = 0;
        v768 = HrEnsureChartSheetsAreNonBlank(lp, 1);
        v604 = v768;
        if ( v1151 )
        {
          if ( v768 < 0 )
          {
            v1166 = v768;
            goto LABEL_1133;
          }
        }
        else if ( v768 < 0 )
        {
          v800 = 512506049;
          v801 = (MsoReserveTag *)&v1364;
          goto LABEL_1925;
        }
        if ( fShowWn )
        {
          v591 = *(SH **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 32LL);
          v1297 = v591;
          v769 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1417, 0x2375A797u);
          v770 = SXVWGEOM::RwFirst(v769);
          v771 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          if ( *(_QWORD *)(v771 + 104) )
            v772 = *(struct SH **)(*(_QWORD *)(v771 + 104) + 24LL);
          else
            v772 = 0;
          v773 = *(_QWORD **)(v771 + 128);
          v774 = 0;
          if ( v773 )
          {
            v775 = v773;
            do
            {
              v774 = v775[1];
              if ( v774 )
                break;
              v773 = (_QWORD *)*v773;
              v775 = v773;
            }
            while ( v773 );
          }
          LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v774 + 96), v772, v770);
        }
        else
        {
          v591 = v1297;
        }
        v776 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        v777 = *(struct WNX **)(v776 + 344);
        if ( v777 )
        {
          v778 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v779 = *(struct WNX **)(v776 + 344);
          v780 = v777;
          v781 = v777;
          do
          {
            v782 = *((_DWORD *)v779 + 2);
            if ( v782 == 2 )
            {
              if ( (*(_WORD *)(CastOrNull<CS,SH>(*((_QWORD *)v780 + 3), v781) + 424) & 0x200) != 0 )
              {
                v783 = *(struct SH **)(*(_QWORD *)(*(_QWORD *)v778 + 304LL) + 32LL);
                v784 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1418, 0x237630D7u);
                v785 = SXVWGEOM::RwFirst(v784);
                v786 = *(_QWORD *)(*(_QWORD *)v778 + 304LL);
                v787 = 0;
                v788 = *(_QWORD **)(v786 + 128);
                if ( v788 )
                {
                  v789 = *(_QWORD **)(v786 + 128);
                  do
                  {
                    v787 = v789[1];
                    if ( v787 )
                      break;
                    v788 = (_QWORD *)*v788;
                    v789 = v788;
                  }
                  while ( v788 );
                }
                LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v787 + 96), *((struct SH **)v780 + 3), v785);
                if ( SbFromHpCore(*(const void **)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v778 + 304LL) + 48LL) + 13280LL)) )
                {
                  v604 = HrRecalcCho(0);
                  if ( v1151 )
                  {
                    if ( v604 < 0 )
                      goto LABEL_1185;
                  }
                  else if ( v604 < 0 )
                  {
                    v800 = 512506048;
                    v801 = (MsoReserveTag *)&v1355;
                    goto LABEL_1925;
                  }
                }
                v791 = *(_QWORD *)(*(_QWORD *)v778 + 304LL);
                if ( *(_QWORD *)(v791 + 40) )
                {
                  v792 = *(_QWORD *)(v791 + 40);
                  v790 = 2048;
                  if ( (*(_WORD *)(v792 + 482) & 0x800) != 0 )
                  {
                    if ( *(_QWORD *)(v792 + 528) )
                      *(_WORD *)(*(_QWORD *)(v792 + 528) + 8LL) |= 0x200u;
                  }
                }
                v793 = (struct CS *)CastOrNull<CS,SH>(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v778 + 304LL) + 32LL), v790);
                CheckDdeCh(v793, 1);
                v794 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1419, 0x237630D6u);
                v795 = SXVWGEOM::RwFirst(v794);
                v796 = *(_QWORD *)(*(_QWORD *)v778 + 304LL);
                v797 = 0;
                v798 = *(_QWORD **)(v796 + 128);
                if ( v798 )
                {
                  v799 = *(_QWORD **)(v796 + 128);
                  do
                  {
                    v797 = v799[1];
                    if ( v797 )
                      break;
                    v798 = (_QWORD *)*v798;
                    v799 = v798;
                  }
                  while ( v798 );
                }
                LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v797 + 96), v783, v795);
                v728 = v1151;
              }
            }
            else if ( !v782 )
            {
              if ( (*((_BYTE *)v781 + 216) & 0x10) != 0 )
              {
                v604 = HrDoDeferredLayoutView(v777);
                if ( v728 )
                {
                  if ( v604 < 0 )
                    goto LABEL_1185;
                }
                else if ( v604 < 0 )
                {
                  v800 = 509215971;
                  v801 = (MsoReserveTag *)&v1356;
LABEL_1925:
                  v1041 = MsoReserveTag::MsoReserveTag(v801, v800);
                  v1042 = SXVWGEOM::RwFirst(v1041);
                  XlsDiag::LogFailRetTag(v604, v1042);
                  goto LABEL_2136;
                }
              }
              else if ( (*((_DWORD *)v777 + 54) & 0x100) != 0 )
              {
                v802 = Measurements::Stopwatch::Stopwatch((Measurements::Stopwatch *)v1536);
                LOBYTE(v803) = 1;
                Measurements::MeasureElapsedTime::MeasureElapsedTime(
                  v1515,
                  Measurements::MeasurementId::ExcelDoDeferredPageLayoutView,
                  v803,
                  v802);
                v1335 = 0;
                v804 = HrXlDoDeferredPageLayoutView(v777, 1, &v1335);
                v604 = v804;
                if ( v728 )
                {
                  if ( v804 < 0 )
                  {
                    v1166 = v804;
                    Measurements::MeasureElapsedTime::~MeasureElapsedTime((Measurements::MeasureElapsedTime *)v1515);
                    goto LABEL_1133;
                  }
                }
                else if ( v804 < 0 )
                {
                  v1044 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1357, 0x1E8C38A3u);
                  v1045 = SXVWGEOM::RwFirst(v1044);
                  XlsDiag::LogFailRetTag(v604, v1045);
                  Measurements::MeasureElapsedTime::~MeasureElapsedTime((Measurements::MeasureElapsedTime *)v1515);
                  goto LABEL_2136;
                }
                Measurements::MeasureElapsedTime::~MeasureElapsedTime((Measurements::MeasureElapsedTime *)v1515);
              }
            }
            v777 = *(struct WNX **)v777;
            v779 = v777;
            v780 = v777;
            v781 = v777;
          }
          while ( v777 );
        }
        if ( !wProjLoad )
        {
          if ( fShowWn )
          {
            v805 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
            if ( !*(_DWORD *)(v805 + 2704) && !*(_DWORD *)(v805 + 1888) )
            {
              v806 = Measurements::Stopwatch::Stopwatch((Measurements::Stopwatch *)v1535);
              LOBYTE(v807) = 1;
              Measurements::MeasureElapsedTime::MeasureElapsedTime(
                v1526,
                Measurements::MeasurementId::ExcelNewFmla,
                v807,
                v806);
              NewFmla(0);
              Measurements::MeasureElapsedTime::~MeasureElapsedTime((Measurements::MeasureElapsedTime *)v1526);
            }
          }
        }
        v808 = lp;
        if ( v1153 )
        {
          if ( lp && !v1172 && !v1155 )
          {
            if ( !v1246 )
            {
              if ( BOOK::Pioldoc(lp) )
              {
                v809 = BOOK::Pioldoc(lp);
                if ( !(unsigned int)IMsoOLDocument::IsInFileSys(v809)
                  || (v810 = BOOK::Pioldoc(lp),
                      ((*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v810 + 224LL))(v810) & 1) != 0) )
                {
                  v811 = BOOK::Pioldoc(lp);
                  v812 = 1;
                  v813 = (*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v811 + 80LL))(v811) & 0x20000;
                  if ( !*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                              + 1232LL)
                                  + 32LL) )
                    v812 = 3;
                  v814 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1420, 0x21C7310u);
                  v815 = SXVWGEOM::RwFirst(v814);
                  v816 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                               + 1232LL)
                                   + 32LL) != 0
                       ? 0x20000
                       : 0;
                  v817 = BOOK::Pioldoc(lp);
                  OldocHelper::SetAttrInAttrMask(v817, v816, 0x20000u, v815);
                  v818 = BOOK::Pioldoc(lp);
                  (*(void (__fastcall **)(struct IMsoOLDocument *, _QWORD, struct IMsoPKMClient **))(*(_QWORD *)v818 + 216LL))(
                    v818,
                    v812,
                    &v1246);
                  v819 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1421, 0x21C7311u);
                  v820 = SXVWGEOM::RwFirst(v819);
                  v821 = BOOK::Pioldoc(lp);
                  OldocHelper::SetAttrInAttrMask(v821, v813, 0x20000u, v820);
                }
              }
              v808 = lp;
            }
            v822 = BOOK::Pioldoc(v808);
            MsoHrMetadataEvent(v822, 32);
            v823 = BOOK::Pioldoc(lp);
            MsoHrTaxonomyOnDocOpen(v823);
            v808 = lp;
          }
          if ( v1153 )
          {
            if ( v808 && !v1172 )
            {
              v824 = BOOK::Pioldoc(v808);
              FileLoad::HrHandleSharepointWorkflows(v824);
              v808 = lp;
            }
            if ( v1153 )
            {
              BuildBookWnxSel();
              v808 = lp;
              if ( v1153 )
              {
                if ( v1246 && lp )
                {
                  *((_QWORD *)lp + 172) = v1246;
                  (*(void (__fastcall **)(struct IMsoPKMClient *))(*(_QWORD *)v1246 + 104LL))(v1246);
                  v808 = lp;
                }
                if ( v1153 && v808 && !*((_QWORD *)v808 + 57) )
                {
                  if ( BOOK::Pioldoc(v808) )
                  {
                    v825 = BOOK::Pioldoc(lp);
                    if ( ((*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v825 + 224LL))(v825) & 1) != 0 )
                    {
                      v826 = BOOK::Pioldoc(lp);
                      if ( ((*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v826 + 80LL))(v826) & 0x40) == 0 )
                      {
                        v827 = MaxPathHolder::SzPath((MaxPathHolder *)v1348);
                        if ( !(unsigned int)FFileInOfflineFilesCache(v827) )
                        {
                          v1293 = 0;
                          v828 = BOOK::Pioldoc(lp);
                          if ( (*(int (__fastcall **)(struct IMsoOLDocument *, struct IStorage **, GUID *))(*(_QWORD *)v828 + 32LL))(
                                 v828,
                                 &v1293,
                                 &IID_IStorage) >= 0 )
                          {
                            v1316 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                              + 2924LL);
                            v1315 = rupBuild;
                            v829 = NtCurrentTeb()->ThreadLocalStoragePointer;
                            v1277 = 0;
                            v1449 = *(struct SH **)(*(_QWORD *)(*(_QWORD *)v829 + 304LL) + 32LL);
                            ENV::ENV((ENV *)&v1560);
                            v830 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                            v1448 = *(_QWORD *)(v830 + 336);
                            *(_QWORD *)(v830 + 336) = &v1560;
                            v1561 = 36737605;
                            v831 = setjmp(v1562);
                            v68 = v1233;
                            v1158 = v1233;
                            if ( v831 )
                            {
                              v114 = v1152;
                            }
                            else
                            {
                              v114 = -2147467259;
                              XlsDiag::LogSetHrCoreTag(-2147467259, 0x279F2A0u);
                              v1307 = 0;
                              ScStgIdsStreamOpen(v1293, 0, 0, v1569, &v1307, -1161035344, 9);
                              if ( SbFromHpCore(v1307) )
                              {
                                if ( !(unsigned int)FBeginDiskIO(v1307) )
                                  goto LABEL_1510;
                                v1261 = 0;
                                if ( (int)HrWPlatformSpecificFromStream2(&v1261) >= 0 )
                                {
                                  if ( (v1261 & 0xF1FF) != 9 )
                                    goto LABEL_1509;
                                  v832 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                                  if ( !*(_QWORD *)(v832 + 32) || (v833 = SH::Pbook(*(SH **)(v832 + 32)), v833 != lp) )
                                  {
                                    v834 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1422, 0x2375A796u);
                                    v835 = SXVWGEOM::RwFirst(v834);
                                    v836 = XLSBOOK::Plxtab((struct BOOK *)((char *)lp + 1640));
                                    v837 = (TAB *)LXTYPE<UsedRange>::PFromI(v836, 0);
                                    v838 = TAB::PshDesktopOnly(v837);
                                    v839 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                  + 304LL)
                                                      + 128LL);
                                    v840 = 0;
                                    if ( v839 )
                                    {
                                      v841 = v839;
                                      do
                                      {
                                        v840 = v841[1];
                                        if ( v840 )
                                          break;
                                        v839 = (_QWORD *)*v839;
                                        v841 = v839;
                                      }
                                      while ( v839 );
                                    }
                                    LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v840 + 96), v838, v835);
                                  }
                                  v1314 = 0;
                                  if ( (int)HrReadBof(v1261, 0, (struct LoadRecovery *)v68, &v1314) >= 0 )
                                  {
                                    v842 = v1262;
                                    v843 = MaxPathHolder::SzPath((MaxPathHolder *)v1348);
                                    if ( (int)HrUpdateWriteAccess(v1579, 516, v843, v842, &v1277) >= 0 )
                                    {
LABEL_1509:
                                      if ( (int)HrEndDiskIO2(0) >= 0 )
                                      {
LABEL_1510:
                                        StreamClose(v1307);
                                        goto LABEL_1511;
                                      }
                                    }
                                  }
                                }
                              }
                              else
                              {
LABEL_1511:
                                if ( v1277 )
                                {
                                  ((void (__fastcall *)(struct IStorage *, _QWORD))v1293->lpVtbl->Commit)(v1293, 0);
                                  if ( ((int (__fastcall *)(struct IStorage *, char *, __int64))v1293->lpVtbl->Stat)(
                                         v1293,
                                         v1548,
                                         1) >= 0 )
                                  {
                                    v844 = BOOK::Pioldoc(lp);
                                    (*(void (__fastcall **)(struct IMsoOLDocument *, _QWORD, __int64))(*(_QWORD *)v844 + 56LL))(
                                      v844,
                                      v1549,
                                      16);
                                    v845 = BOOK::Pioldoc(lp);
                                    (*(void (__fastcall **)(struct IMsoOLDocument *, _QWORD, __int64))(*(_QWORD *)v845 + 56LL))(
                                      v845,
                                      v1550,
                                      17);
                                  }
                                  v846 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                               + 304LL)
                                                   + 40LL)
                                       + 1640LL;
                                  v847 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v846 + 32LL))(v846);
                                  if ( FileLoad::FCheckTimeStampOnThisFile(
                                         *(const struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                           + 304LL)
                                                               + 40LL),
                                         v847,
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
                            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1448;
                            v848 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1423, 0x237630D5u);
                            v849 = SXVWGEOM::RwFirst(v848);
                            v850 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                              + 128LL);
                            v851 = 0;
                            if ( v850 )
                            {
                              v852 = v850;
                              do
                              {
                                v851 = v852[1];
                                if ( v851 )
                                  break;
                                v850 = (_QWORD *)*v850;
                                v852 = v850;
                              }
                              while ( v850 );
                            }
                            LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v851 + 96), v1449, v849);
                            rupBuild = v1315;
                            *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                      + 2924LL) = v1316;
                            ((void (__fastcall *)(struct IStorage *))v1293->lpVtbl->Release)(v1293);
                            v591 = v1297;
                            v808 = lp;
                            v1160 = Src;
                            v1171 = v1214;
                            v1161 = v1245;
LABEL_1524:
                            if ( v1153 )
                            {
                              v853 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                              if ( *(_QWORD *)(v853 + 40) )
                              {
                                sub_14046F5B0(*(_QWORD *)(v853 + 40));
                                v808 = lp;
                              }
                              if ( v1153
                                && v808
                                && !(unsigned int)XlSecurity::FMaaFinal(v808, 5)
                                && !(unsigned int)XlSecurity::FMaaDetected(lp, 5)
                                && !IsWin32AppRunningInWdag() )
                              {
                                EnableMaa(lp, 5);
                                FinalMaa(lp, 5);
                              }
                            }
                            if ( Python::FeatureGates::FEnabledPython(0) && v1153 )
                            {
                              v854 = lp;
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
                              v854 = lp;
                            }
                            if ( CastOrNull<XLSWORKBOOK,BOOK>(v854) )
                            {
                              v855 = (const struct Api::Workbook *)CastOrNull<XLSWORKBOOK,BOOK>(lp);
                              if ( Api::ImportFunctionsManager::FIsFeatureEnabled(v855)
                                && v1153
                                && !(unsigned int)XlSecurity::FMaaFinal(lp, 9)
                                && !(unsigned int)XlSecurity::FMaaDetected(lp, 9)
                                && !IsWin32AppRunningInWdag() )
                              {
                                EnableMaa(lp, 9);
                                FinalMaa(lp, 9);
                              }
                            }
                            LOBYTE(v264) = v1151;
LABEL_1549:
                            v856 = (Excel::AppGuard::Actions **)lp;
                            if ( v1153 )
                            {
                              if ( lp )
                              {
                                if ( !Excel::AppGuard::FTryInitAfterLoad(lp, v593) )
                                {
                                  Error(196663);
                                  v1046 = HrFreeBook2(lp);
                                  v604 = v1046;
                                  if ( (_BYTE)v264 )
                                  {
                                    if ( v1046 < 0 )
                                    {
                                      v1166 = v1046;
                                      goto LABEL_1133;
                                    }
                                  }
                                  else if ( v1046 < 0 )
                                  {
                                    v800 = 512506018;
                                    v801 = (MsoReserveTag *)&v1358;
                                    goto LABEL_1925;
                                  }
                                  lp = 0;
                                  v1153 = 0;
                                  goto LABEL_1935;
                                }
                                v856 = (Excel::AppGuard::Actions **)lp;
                              }
                              if ( v1153 && v856 && (a10 & 0x40000) != 0 )
                              {
                                Excel::AppGuard::Actions::AddTrustPromotionRecord(v856[192], (unsigned __int64)v593);
                                v856 = (Excel::AppGuard::Actions **)lp;
                              }
                            }
                            if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                           + 1440LL)
                              && v856 )
                            {
                              v857 = FBookAddin((const struct BOOK *)v856);
                              v858 = v1160;
                              if ( v857 && (int)AddinManager::HrAddOpenAddin(v1160 + 1, *v1160, &vpoldocument) < 0 )
                              {
                                sub_1411BEB10();
                                sub_141232A50();
                                XlsDiag::LogSetHrCoreTag(-2080308954, 0x1E8C38A1u);
                                v604 = -2080308954;
                                goto LABEL_2136;
                              }
                            }
                            else
                            {
                              v858 = v1160;
                            }
                            v859 = 0;
                            if ( v591 )
                            {
                              v860 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                              v861 = *(_QWORD *)(v860 + 32)
                                   ? SH::Pbook(*(SH **)(v860 + 32))
                                   : *(struct BOOK **)(v860 + 40);
                              if ( v861 != SH::Pbook(v591) )
                              {
                                v859 = 1;
                                v862 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                                v1268 = *(struct SH **)(v862 + 32);
                                v1275 = *(struct WNX **)(v862 + 104);
                                v1331 = (struct WNX *)UIGLOBALS::UIGLOBALSCONTAINER::m_selection;
                                v863 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1424, 0x237630D4u);
                                v864 = SXVWGEOM::RwFirst(v863);
                                v865 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                              + 304LL)
                                                  + 128LL);
                                v866 = 0;
                                if ( v865 )
                                {
                                  v867 = v865;
                                  do
                                  {
                                    v866 = v867[1];
                                    if ( v866 )
                                      break;
                                    v865 = (_QWORD *)*v865;
                                    v867 = v865;
                                  }
                                  while ( v865 );
                                }
                                LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v866 + 96), v591, v864);
                              }
                            }
                            if ( v1153 )
                            {
                              v868 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                              if ( *(_QWORD *)(v868 + 40) )
                              {
                                if ( (*(_BYTE *)(*(_QWORD *)(v868 + 1304) + 56LL) & 8) != 0
                                  && (unsigned int)FAnyListsInBook(*(const struct BOOK **)(v868 + 40)) )
                                {
                                  v560 = (unsigned int)CustomTwoAlert(327820, 0, -282329067, -282329066) == 102;
                                  v869 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                                  if ( v560 )
                                    RemoveBookLists(*(const struct BOOK **)(v869 + 40));
                                  else
                                    *(_WORD *)(*(_QWORD *)(v869 + 1304) + 56LL) &= ~8u;
                                }
                              }
                            }
                            if ( !v1153 )
                              goto LABEL_1630;
                            v870 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                            if ( *(_QWORD *)(v870 + 40) )
                            {
                              if ( (*(_BYTE *)(*(_QWORD *)(v870 + 1304) + 56LL) & 8) != 0 )
                              {
                                if ( !XLSBOOK::Plxtab(*(XLSBOOK **)(v870 + 40))
                                  || (v871 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                   + 304LL)
                                                       + 40LL)
                                           + 1640LL,
                                      !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v871 + 32LL))(v871)) )
                                {
                                  v872 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                                  v873 = *(_QWORD *)(v872 + 40);
                                  if ( *(_DWORD *)(v872 + 1836) )
                                  {
                                    *(_DWORD *)(v873 + 884) |= 0x400000u;
                                    goto LABEL_1587;
                                  }
                                  if ( (*(_DWORD *)(v873 + 884) & 0x100) != 0 )
                                  {
                                    *(_DWORD *)(v873 + 884) |= 0x400000u;
                                    v884 = NtCurrentTeb()->ThreadLocalStoragePointer;
                                    *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v884 + 304LL) + 1304LL) + 16LL) = *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v884 + 304LL) + 1232LL) + 110LL);
                                    v73 = 1;
                                    *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                     + 304LL)
                                                         + 1232LL)
                                             + 110LL) = 0;
                                    fnSave(0, 0, 1);
                                    v885 = NtCurrentTeb()->ThreadLocalStoragePointer;
                                    *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v885 + 304LL) + 1232LL) + 110LL) = *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v885 + 304LL) + 1304LL) + 16LL);
                                    goto LABEL_1588;
                                  }
                                }
                              }
                            }
                            if ( !v1153 )
                              goto LABEL_1630;
                            v886 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                            if ( (*(_BYTE *)(*(_QWORD *)(v886 + 1304) + 56LL) & 8) != 0 )
                            {
                              if ( *(_QWORD *)(v886 + 40) )
                              {
                                if ( XLSBOOK::Plxtab(*(XLSBOOK **)(v886 + 40)) )
                                {
                                  v887 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                               + 304LL)
                                                   + 40LL)
                                       + 1640LL;
                                  if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v887 + 32LL))(v887) )
                                  {
                                    v888 = FileSource::HrGetFileTemp(v1305, 12);
                                    v114 = v888;
                                    if ( v888 < 0 )
                                      XlsDiag::LogSetHrCoreTag(v888, 0x280659Au);
                                    if ( v114 < 0 )
                                    {
                                      v114 = -2147467260;
LABEL_1587:
                                      v73 = 1;
                                      goto LABEL_1588;
                                    }
                                    if ( (int)HrStartSharingWbk(
                                                *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                            + 304LL)
                                                                + 40LL),
                                                v1153,
                                                v858,
                                                v1224,
                                                (struct LoadRecovery *)v68,
                                                &v1317,
                                                &v1263) >= 0 )
                                    {
                                      if ( v1154 )
                                      {
                                        v891 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                                        if ( *(_QWORD *)(v891 + 40) )
                                          v892 = BOOK::Pioldoc(*(BOOK **)(v891 + 40));
                                        else
                                          v892 = 0;
                                        *v1161 = v892;
                                        v1157 = v892;
                                      }
                                    }
                                    else
                                    {
                                      if ( v1263 )
                                      {
                                        *v1161 = 0;
                                        v1157 = 0;
                                      }
                                      else if ( v1154 )
                                      {
                                        v889 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                                        if ( *(_QWORD *)(v889 + 40) )
                                          v890 = BOOK::Pioldoc(*(BOOK **)(v889 + 40));
                                        else
                                          v890 = 0;
                                        *v1161 = v890;
                                        v1157 = v890;
                                      }
                                      if ( v1317 || v1263 )
                                        goto LABEL_1587;
                                    }
                                  }
                                }
                              }
                            }
                            if ( v1153
                              && *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                           + 40LL)
                              && v1267 )
                            {
                              v893 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1425, 0x1E111215u);
                              v894 = SXVWGEOM::RwFirst(v893);
                              v73 = 1;
                              BookDirty(
                                *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                            + 304LL)
                                                + 40LL),
                                1,
                                v894);
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
                            if ( v1153 )
                            {
                              v895 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                              if ( *(_QWORD *)(v895 + 40) )
                              {
                                if ( (unsigned int)FSharedBook(*(const struct BOOK **)(v895 + 40)) )
                                {
                                  v896 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                               + 304LL)
                                                   + 40LL);
                                  if ( (*(_BYTE *)(v896 + 892) & 0x20) != 0 )
                                  {
                                    *(_DWORD *)(v896 + 892) &= ~0x20u;
                                    v897 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1426, 0x231C69Cu);
                                    v898 = SXVWGEOM::RwFirst(v897);
                                    BookDirty(
                                      *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                  + 304LL)
                                                      + 40LL),
                                      1,
                                      v898);
                                    OkAlert(327877, 0);
                                  }
                                }
                              }
                              if ( v1153 )
                              {
                                if ( (unsigned int)FSharedBook(*(const struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                                 + 304LL)
                                                                                     + 40LL)) )
                                {
                                  v899 = LOCATIONCONTEXTDATA::PWorkbookCur((LOCATIONCONTEXTDATA *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                                                                                 + 8LL));
                                  v900 = TLSW::PesExpressionService(*(TLSW **)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                             + 304LL));
                                  ConvertAllDynamicArraystoLegacyArrays(v900, v899);
                                }
                                if ( v1153 )
                                {
                                  if ( *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                             + 304LL)
                                                 + 40LL)
                                    && (unsigned int)sub_14046FB20() )
                                  {
                                    SetAutoRefreshPending(1, 0);
                                  }
                                  if ( v1153
                                    && *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                             + 304LL)
                                                 + 40LL) )
                                  {
                                    v901 = FeatureGateCollectionBase<LoadSaveFeatureGates>::Instance();
                                    v560 = (unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(v901 + 424) == 0;
                                    v902 = NtCurrentTeb()->ThreadLocalStoragePointer;
                                    if ( v560 )
                                    {
                                      v1278 = 0;
                                      v1279 = 0;
                                      v905 = XLSBOOK::Plxtab((XLSBOOK *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v902 + 304LL)
                                                                                   + 40LL)
                                                                       + 1640LL));
                                      XlPng::DyHeight(v905, v1295);
                                      LXContainerContiguousIterators<LXTYPE<TAB>,TAB,LXBASE>::end(v905, v1329);
                                      if ( (unsigned __int8)LXContiguousConstIterator<LXTYPE<TAB>>::operator!=(
                                                              v1295,
                                                              v1329) )
                                      {
                                        do
                                        {
                                          v906 = BKORWS::Psh((BKORWS *)v1295);
                                          v907 = TAB::PshDesktopOnly(v906);
                                          if ( (*((_BYTE *)v907 + 10) & 4) != 0 )
                                            v908 = 0;
                                          else
                                            v908 = *((_BYTE *)v907 + 8);
                                          if ( v908 <= 1u )
                                          {
                                            v909 = TAB::PshDesktopOnly(v906);
                                            GetOartDataForTelemetry(v909, &v1278, &v1279);
                                          }
                                          LXContiguousIterator<LXTYPE<TAB>>::operator++(v1295);
                                        }
                                        while ( (unsigned __int8)LXContiguousConstIterator<LXTYPE<TAB>>::operator!=(
                                                                   v1295,
                                                                   v1329) );
                                        v68 = v1158;
                                      }
                                      LXContiguousIterator<LXTYPE<std::pair<XLUID,DocumentTasks::SharedAuthorMapValue>>>::~LXContiguousIterator<LXTYPE<std::pair<XLUID,DocumentTasks::SharedAuthorMapValue>>>(v1329);
                                      LXContiguousIterator<LXTYPE<std::pair<XLUID,DocumentTasks::SharedAuthorMapValue>>>::~LXContiguousIterator<LXTYPE<std::pair<XLUID,DocumentTasks::SharedAuthorMapValue>>>(v1295);
                                      v910 = Mso::Telemetry::Activity::DataFields(v1213);
                                      Mso::Telemetry::IDataFieldCollection::Add<int>(
                                        v910,
                                        "cMsoShapes",
                                        (unsigned int)v1278,
                                        4);
                                      v911 = Mso::Telemetry::Activity::DataFields(v1213);
                                      Mso::Telemetry::IDataFieldCollection::Add<int>(
                                        v911,
                                        "numShapes",
                                        (unsigned int)v1279,
                                        4);
                                    }
                                    else
                                    {
                                      v903 = v1213;
                                      v904 = LOCATIONCONTEXTDATA::PWorkbookCur((LOCATIONCONTEXTDATA *)(*(_QWORD *)(*(_QWORD *)v902 + 304LL) + 8LL));
                                      ArtUtil::LogOartDataForOpenedWorkbook(v904, v903);
                                    }
                                  }
                                }
                              }
                            }
                            if ( v1226 )
                            {
                              v277 = v1160;
                              CeToggleFileAttr(v1160, v1224, 3, 6u);
                            }
                            else
                            {
LABEL_1588:
                              v277 = v1160;
                            }
                            if ( v859 )
                            {
                              v874 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1427, 0x237630D3u);
                              v875 = SXVWGEOM::RwFirst(v874);
                              v876 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                            + 304LL)
                                                + 128LL);
                              v877 = 0;
                              if ( v876 )
                              {
                                v878 = v876;
                                do
                                {
                                  v877 = v878[1];
                                  if ( v877 )
                                    break;
                                  v876 = (_QWORD *)*v876;
                                  v878 = v876;
                                }
                                while ( v876 );
                              }
                              LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v877 + 96), v1268, v875);
                              v879 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1428, 0x237630D2u);
                              v880 = SXVWGEOM::RwFirst(v879);
                              v881 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                            + 304LL)
                                                + 128LL);
                              v882 = 0;
                              if ( v881 )
                              {
                                v883 = v881;
                                do
                                {
                                  v882 = v883[3];
                                  if ( v882 )
                                    break;
                                  v881 = (_QWORD *)*v881;
                                  v883 = v881;
                                }
                                while ( v881 );
                              }
                              VIEWCONTEXTDATA::CurWnx(*(VIEWCONTEXTDATA **)(v882 + 16), v1275, v880);
                              SetWnxSel(v1331);
                            }
                            else if ( v1303 != (struct SH *)65534 )
                            {
                              v912 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1429, 0x237630D1u);
                              v913 = SXVWGEOM::RwFirst(v912);
                              v914 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                            + 304LL)
                                                + 128LL);
                              v915 = 0;
                              if ( v914 )
                              {
                                v916 = v914;
                                do
                                {
                                  v915 = v916[1];
                                  if ( v915 )
                                    break;
                                  v914 = (_QWORD *)*v914;
                                  v916 = v914;
                                }
                                while ( v914 );
                              }
                              LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v915 + 96), v1303, v913);
                            }
                            goto LABEL_1664;
                          }
                        }
                      }
                    }
                  }
                  v808 = lp;
                }
              }
            }
          }
        }
        v68 = v1158;
        goto LABEL_1524;
      }
      v600 = FileSource::StzFileName((FileSource *)v1305);
      if ( !FForeignFileExtension(v600) && (v1172 || !(unsigned int)FFinderFile(&v1567)) )
      {
        v601 = FileSource::StzFilePath((FileSource *)v1305);
        CchStToStz(v601, v1543, 2086);
        if ( !v1542 )
        {
          MaxPathStzPoke::MaxPathStzPoke((MaxPathStzPoke *)v1503, (struct MaxPathHolder *)v1340);
          v1545 = SlicerViewImpl::PSlicerView((SlicerViewImpl *)v1503);
          MaxPathStzPoke::~MaxPathStzPoke((MaxPathStzPoke *)v1503);
        }
        if ( v1172 && !(unsigned int)FOsrc() )
        {
          v602 = v1217;
LABEL_1130:
          v603 = HrEndDiskIO2(0);
          v604 = v603;
          if ( v1151 )
          {
            if ( v603 < 0 )
              goto LABEL_1132;
          }
          else if ( v603 < 0 )
          {
            v800 = 512506060;
            v801 = (MsoReserveTag *)&v1354;
            goto LABEL_1925;
          }
          StreamClose(v1167);
          if ( (unsigned int)(v602 + 2146697471) <= 1 )
          {
            if ( v68 )
              LoadRecovery::SetRepairState((LoadRecovery *)v68, v602);
            else
              *(&vscd + 1) = 1;
          }
          v114 = -2146827284;
          v1153 = 0;
          v1152 = -2146827284;
          XlsDiag::LogSetHrCoreTag(-2146827284, 0x1797719u);
          v681 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
          v682 = OpenTelemetry::POpenFileStageModel(v681);
          v683 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1409, 0x1F0CB5C5u);
          v684 = SXVWGEOM::RwFirst(v683);
          WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v682, 2214658822LL, v684);
          v596 = v1154;
          goto LABEL_1272;
        }
        v613 = HrDetectWebType(v1157, (enum MSOFF *)&v1216, &v1292, 0, 0);
        v1217 = v613;
        v602 = v613;
        if ( v613 < 0 )
          goto LABEL_1130;
        if ( v613 == 1 )
        {
          if ( (unsigned int)FCmpTextEq(&v1566[v1567 + 13], L".xml", 4, 4)
            || (unsigned int)FCmpTextEq(&v1566[v1567 + 13], L".xsd", 4, 4) )
          {
            v1201 = 1;
            v614 = 3;
          }
          else
          {
            v614 = 0;
          }
          v1216 = v614;
        }
        if ( (unsigned int)FOsrc() && (unsigned int)(v1216 - 1) > 2 )
          goto LABEL_1130;
        v615 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
        v616 = (LXBASE *)OpenTelemetry::POpenFileStageModel(v615);
        v617 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1407, 0x1F0CB5C4u);
        SXVWGEOM::RwFirst(v617);
        WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v616);
        v618 = a11;
        if ( v1216 == 1 || v1216 == 2 )
        {
          v619 = v1158;
          goto LABEL_1288;
        }
        if ( v1216 == 3 )
        {
          v619 = v1158;
          v620 = HrDetectXMLTypeAndPreprocess(a11, (struct XSL *)&v1541, (struct LoadRecovery *)v1158, 0, 1, 1, v1201);
          v1217 = v620;
          v602 = v620;
          if ( v620 != -2147467263 )
          {
            if ( v620 == -2147418113 )
              goto LABEL_1189;
            if ( v620 == -2147352567 )
            {
              v73 = 1;
              if ( v1542 == 1 )
              {
                MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1462, v1160);
                v1189 = v1178 != 0;
                v1299 = v1157;
              }
              else if ( v1157 )
              {
                (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v1157 + 56LL))(
                  v1157,
                  0xFFFFFFFFLL,
                  7);
                if ( v1178 )
                  HrRecordEvent(v1157, 0x40000000u, 0);
                v627 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1408, 0x2369629Fu);
                v628 = SXVWGEOM::RwFirst(v627);
                OlDocFilePath::FReleaseIOLDoc(v502, 1, 1, v628);
              }
              v408 = 0;
              v1161 = 0;
              v1245 = 0;
              CchStToSt(v1544, v1160, v1224);
              v1214 = 1;
              v604 = HrEndDiskIO2(0);
              if ( v1151 )
              {
                if ( v604 < 0 )
                  goto LABEL_1185;
              }
              else if ( v604 < 0 )
              {
                v800 = 512506059;
                v801 = (MsoReserveTag *)&v1457;
                goto LABEL_1925;
              }
              StreamClose(v1167);
              v68 = v1158;
              a11 = 65001;
              goto LABEL_744;
            }
            if ( v620 )
            {
              if ( v620 != 1 )
              {
                if ( v620 == -2146827284 )
                  Error(262267);
                v68 = v1158;
                goto LABEL_1130;
              }
LABEL_1189:
              v1216 = 1;
              (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v1157 + 56LL))(
                v1157,
                1,
                11);
LABEL_1288:
              FSwitchLoadActionType(2, 0, (struct LoadRecovery *)v619);
              v671 = -(v1216 != 2);
              v672 = BKORWS::Psh((BKORWS *)v1340);
              v673 = 0;
              if ( (unsigned __int8)SafeToLoad::FSafeToLoadOnFileExtensionPfilesource(
                                      v672,
                                      v1305,
                                      (unsigned int)(v671 + 44),
                                      &v1235) )
              {
                MaxPathStzPoke::MaxPathStzPoke((MaxPathStzPoke *)v1505, (struct MaxPathHolder *)v1340);
                v674 = v1292;
                v675 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1836LL);
                LOBYTE(v673) = v1216 == 2;
                v676 = (wchar_t *)SlicerViewImpl::PSlicerView((SlicerViewImpl *)v1505);
                BookHtml = HrLoadBookHtml(v1167, 0, v1570, v676, a5, 0, v674, v618, v673, v675, (struct OSRR *)&v1235);
                v1152 = BookHtml;
                v114 = BookHtml;
                if ( BookHtml < 0 )
                  XlsDiag::LogSetHrCoreTag(BookHtml, 0x2156756u);
                MaxPathStzPoke::~MaxPathStzPoke((MaxPathStzPoke *)v1505);
                v1153 = v114 >= 0;
                if ( v114 >= 0 || !OSRR::FReadyForOsr((OSRR *)&v1235) )
                {
                  v596 = v1154;
                  if ( v1154 )
                  {
                    if ( (unsigned int)IMsoOLDocument::IsInFileSys(v1157) )
                    {
                      if ( v1153
                        || (v678 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL),
                            *(_QWORD *)(v678 + 40))
                        && (*(_DWORD *)(*(_QWORD *)(v678 + 40) + 884LL) & 0x200) != 0 )
                      {
                        v679 = (wchar_t **)XLSBOOK::Plxtab(*(XLSBOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                   + 304LL)
                                                                       + 40LL));
                        FreeHpstTempPath((struct STB *)v679);
                        v680 = FileSource::StzFilePath((FileSource *)v1305);
                        if ( (int)HrStDupSt(v680, v679 + 21) < 0 )
                          v679[21] = 0;
                      }
                    }
                  }
                  v1174 = 1;
                  goto LABEL_1272;
                }
                v73 = 1;
LABEL_1168:
                v1155 = 1;
LABEL_1072:
                v68 = v1158;
                goto LABEL_743;
              }
LABEL_1284:
              v68 = v1158;
              goto LABEL_1130;
            }
            v621 = BKORWS::Psh((BKORWS *)v1340);
            if ( !(unsigned __int8)SafeToLoad::FSafeToLoadOnFileExtensionPfilesource(v621, v1305, 45, &v1235) )
              goto LABEL_1284;
            MaxPathStzPoke::MaxPathStzPoke((MaxPathStzPoke *)v1504, (struct MaxPathHolder *)v1340);
            v622 = (wchar_t *)SlicerViewImpl::PSlicerView((SlicerViewImpl *)v1504);
            BookXmlSpreadsheet = HrLoadBookXmlSpreadsheet(v1167, v1570, v622, a5, 0, v618, (struct OSRR *)&v1235);
            v1152 = BookXmlSpreadsheet;
            v114 = BookXmlSpreadsheet;
            if ( BookXmlSpreadsheet < 0 )
              XlsDiag::LogSetHrCoreTag(BookXmlSpreadsheet, 0x2156757u);
            MaxPathStzPoke::~MaxPathStzPoke((MaxPathStzPoke *)v1504);
            v1153 = v114 >= 0;
            if ( v114 < 0 && OSRR::FReadyForOsr((OSRR *)&v1235) )
            {
              v73 = 1;
              goto LABEL_1168;
            }
            v596 = v1154;
            if ( v1154 )
            {
              if ( (unsigned int)IMsoOLDocument::IsInFileSys(v1157) )
              {
                if ( v1153
                  || (v624 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL),
                      *(_QWORD *)(v624 + 40))
                  && (*(_DWORD *)(*(_QWORD *)(v624 + 40) + 884LL) & 0x200) != 0 )
                {
                  v625 = (wchar_t **)XLSBOOK::Plxtab(*(XLSBOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                             + 304LL)
                                                                 + 40LL));
                  FreeHpstTempPath((struct STB *)v625);
                  v626 = FileSource::StzFilePath((FileSource *)v1305);
                  if ( (int)HrStDupSt(v626, v625 + 21) < 0 )
                    v625[21] = 0;
                }
              }
            }
LABEL_1270:
            v665 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
            if ( *(_QWORD *)(v665 + 24) )
            {
              v666 = OcsTransitionController::PCoauthTransitionState(*(OcsTransitionController **)(v665 + 24));
              XLSBOOK::HrEnsureAllSheetXluids(v666);
            }
            goto LABEL_1272;
          }
          v629 = BKORWS::Psh((BKORWS *)v1340);
          if ( !(unsigned __int8)SafeToLoad::FSafeToLoadOnFileExtensionPfilesource(v629, v1305, 48, &v1235) )
            goto LABEL_1284;
          v630 = BKORWS::Psh((BKORWS *)v1339);
          if ( (unsigned int)FBlockOfficeFile(33, v630, 0) )
            OptDialog = 1223;
          else
            OptDialog = HrShowXmlLoadOptDialog((enum XMLLOADOPTIONS *)&v1230, a12);
          if ( OptDialog )
          {
            if ( OptDialog < 0 )
              XlsDiag::LogSetHrCoreTag(OptDialog, 0x2156759u);
            goto LABEL_1284;
          }
          CodeMarker(1124);
          if ( v1230 != 1 )
          {
            if ( v1230 == 2 )
            {
              if ( v1157
                && ((*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1157 + 80LL))(v1157) & 0x40) == 0
                && (int)HrRecordEvent(v1157, 0x40000000u, 0) >= 0 )
              {
                FBeginCmdIOLDoc(v1157, 4u, 0, 0, 0);
              }
              v648 = APPCORE::PmemheapMain((APPCORE *)&vapp);
              MaxPathHolder::MaxPathHolder((MaxPathHolder *)v1510, v648, 259, 0);
              if ( v1542 )
                v649 = (const wchar_t *)((char *)v1167 + 48);
              else
                v649 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1340);
              MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1510, v649);
              v650 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1340);
              v651 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1510);
              Xml = HrLoadXml(v1167, v1570, 257, v651, v650, 0, a5, 1, 1);
              v1152 = Xml;
              v114 = Xml;
              if ( Xml < 0 )
                XlsDiag::LogSetHrCoreTag(Xml, 0x2156758u);
              MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1510);
              v1153 = v114 >= 0;
              if ( v114 < 0 )
                StreamClose(v1167);
            }
            else
            {
              if ( v1230 != 3 )
              {
                if ( v1230 == 4 )
                {
                  if ( SbFromHpCore(v1167) )
                    StreamClose(v1167);
                  v1167 = FileSource::StreamOpen((FileSource *)v1305, 0x401u, 0);
                  if ( SbFromHpCore(v1167) )
                  {
                    v560 = g_fPromptTextFile == 0;
                    g_fPromptTextFile = 0;
                    v632 = !v560;
                    v1290 = 0;
                    v633 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1350);
                    v634 = (wchar_t *)BKORWS::Psh((BKORWS *)v1350);
                    v604 = HrLoadBiff(
                             &v1167,
                             &v1567,
                             v634,
                             v633,
                             1,
                             a5,
                             a7,
                             v1215,
                             0,
                             &v1194,
                             &v1223,
                             (struct LoadRecovery *)v619,
                             &lp,
                             0,
                             0,
                             0,
                             v1273,
                             &v1290);
                    if ( v1151 )
                    {
                      if ( v604 < 0 )
                        goto LABEL_1185;
                    }
                    else if ( v604 < 0 )
                    {
                      v800 = 512506057;
                      v801 = (MsoReserveTag *)&v1458;
                      goto LABEL_1925;
                    }
                    if ( v1290 )
                    {
                      v635 = BKORWS::Psh((BKORWS *)&v1179);
                      v636 = v1157;
                      v637 = v1167;
                      v638 = v635;
                      v639 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1350);
                      v640 = (wchar_t *)BKORWS::Psh((BKORWS *)v1340);
                      v1239 = FLoadForeign(v1570, v640, v639, v637, a5, 2, &v1260, v636, 0, v1273, v638);
                    }
                    g_fPromptTextFile = v632;
                  }
                }
                goto LABEL_1264;
              }
              v1327 = 0;
              if ( v1157
                && ((*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1157 + 80LL))(v1157) & 0x40) == 0
                && (int)HrRecordEvent(v1157, 0x40000000u, 0) >= 0 )
              {
                FBeginCmdIOLDoc(v1157, 4u, 0, 0, 0);
              }
              v641 = NtCurrentTeb()->ThreadLocalStoragePointer;
              v642 = vpoldocument;
              v1520[7] = 0;
              v1520[3] = 0;
              v643 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v641 + 304LL) + 32LL);
              v644 = NtCurrentTeb()->ThreadLocalStoragePointer;
              v1520[0] = v643;
              v1520[1] = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v644 + 304LL) + 104LL);
              v1520[2] = UIGLOBALS::UIGLOBALSCONTAINER::m_selection;
              (*(void (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)vpoldocument + 8LL))(vpoldocument);
              Project2 = HrCreateProject2(0, 0, 5, 7u, 0, 1);
              v604 = Project2;
              if ( v1151 )
              {
                if ( Project2 < 0 )
                  goto LABEL_1215;
              }
              else if ( Project2 < 0 )
              {
                v800 = 512506053;
                v801 = (MsoReserveTag *)&v1461;
                goto LABEL_1925;
              }
              SuspendRecording();
              if ( (unsigned int)HrDesignXMLCore(v642, &v1327) )
              {
                ResumeRecording();
                if ( v1266 )
                  FreePxlxmlmap(v1266);
                HtmlFailed = HrBookLoadHtmlFailed((struct BLG *)v1520);
                v604 = HtmlFailed;
                if ( v1151 )
                {
                  if ( HtmlFailed < 0 )
                    goto LABEL_1215;
                }
                else if ( HtmlFailed < 0 )
                {
                  v800 = 512506051;
                  v801 = (MsoReserveTag *)&v1397;
                  goto LABEL_1925;
                }
                (*(void (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v642 + 16LL))(v642);
                goto LABEL_1284;
              }
              ResumeRecording();
              RenumberWind(*(struct SH **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                         + 32LL));
              v646 = HrEndDiskIO2(0);
              v604 = v646;
              if ( v1151 )
              {
                if ( v646 < 0 )
                  goto LABEL_1132;
              }
              else if ( v646 < 0 )
              {
                v800 = 512506052;
                v801 = (MsoReserveTag *)&v1459;
                goto LABEL_1925;
              }
              StreamClose(v1167);
              v1153 = 1;
              (*(void (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v642 + 16LL))(v642);
              if ( !FVbaEventEnabled() )
                goto LABEL_1264;
LABEL_1223:
              HrVbaEventDoBookOpen(
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL),
                2);
            }
LABEL_1264:
            CodeMarker(1125);
            v663 = v1175;
            if ( v1153 )
              v663 = 1;
            v1175 = v663;
            if ( ((v1230 - 1) & 0xFFFFFFFD) != 0 )
            {
              v596 = v1154;
            }
            else
            {
              v1345 = 0;
              v664 = FHpshtiFromStt(&v1345, 61);
              v596 = v1154;
              if ( v664 )
                *((_DWORD *)v1345 + 6) = v1230;
            }
            goto LABEL_1270;
          }
          v653 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v654 = 0;
          v1337 = 0;
          v1312 = 0;
          v1306 = 0;
          v1521[7] = 0;
          v1521[3] = 0;
          v655 = vpoldocument;
          v1291 = 1;
          v656 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v653 + 304LL) + 32LL);
          v657 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v1521[0] = v656;
          v1521[1] = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v657 + 304LL) + 104LL);
          v1521[2] = UIGLOBALS::UIGLOBALSCONTAINER::m_selection;
          (*(void (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)vpoldocument + 8LL))(vpoldocument);
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 2132LL) = 1;
          v604 = HrCreateProject2(0, 0, 5, 7u, 0, 1);
          if ( v1151 )
          {
            if ( v604 < 0 )
            {
LABEL_1185:
              v1166 = v604;
              goto LABEL_1133;
            }
          }
          else if ( v604 < 0 )
          {
            v800 = 512506056;
            v801 = (MsoReserveTag *)&v1353;
            goto LABEL_1925;
          }
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 2132LL) = 0;
          SetRef((struct REF *)v1486, 0, 0, 0, 0);
          SuspendRecording();
          if ( (unsigned int)FEnsureVpxierrinfo()
            && !(unsigned int)HrXlXmlMapFromOlDocument(v655, &v1266, &v1337, &v1291, &v1312, &v1306, 1) )
          {
            v658 = LOCATIONCONTEXTDATA::PWorkbookCur((LOCATIONCONTEXTDATA *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                       + 304LL)
                                                                           + 8LL));
            v659 = XLSWORKBOOK::Pcm(v658);
            v660 = OcsTransitionController::PCoauthTransitionState(v659);
            CollabManager::FDisableRevisionGeneration(v660, 196, 0);
            v661 = *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer;
            if ( v1291 )
            {
              LOBYTE(v654) = (unsigned int)HrAutoDesignXML(
                                             0,
                                             v1312,
                                             v1306,
                                             *(struct SH **)(*(_QWORD *)(v661 + 304) + 32LL),
                                             (const struct REF *)v1486,
                                             v1266,
                                             0) == 0;
            }
            else if ( !(unsigned int)HrAutoDesignXML(
                                       v655,
                                       0,
                                       0,
                                       *(struct SH **)(*(_QWORD *)(v661 + 304) + 32LL),
                                       (const struct REF *)v1486,
                                       v1266,
                                       0) )
            {
              v654 = 1;
            }
          }
          (*(void (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v655 + 16LL))(v655);
          if ( v1312 )
          {
            ((void (__fastcall *)(struct IStream *))v1312->lpVtbl->Release)(v1312);
            v1312 = 0;
          }
          if ( v1306 )
          {
            ((void (__fastcall *)(struct IStream *))v1306->lpVtbl->Release)(v1306);
            v1306 = 0;
          }
          DisplayCleanupXIErr();
          ResumeRecording();
          if ( !v654 )
          {
            v670 = HrBookLoadHtmlFailed((struct BLG *)v1521);
            v604 = v670;
            if ( v1151 )
            {
              if ( v670 < 0 )
              {
LABEL_1215:
                v1166 = v604;
                goto LABEL_1133;
              }
            }
            else if ( v670 < 0 )
            {
              v800 = 512506054;
              v801 = (MsoReserveTag *)&v1352;
              goto LABEL_1925;
            }
            goto LABEL_1284;
          }
          if ( *((_DWORD *)vpxsl + 1) )
          {
            FreeHpst(*((wchar_t **)v1266 + 14));
            *((_QWORD *)v1266 + 14) = 0;
            *((_DWORD *)v1266 + 24) = 0;
          }
          v662 = HrEndDiskIO2(0);
          v604 = v662;
          if ( v1151 )
          {
            if ( v662 < 0 )
              goto LABEL_1215;
          }
          else if ( v662 < 0 )
          {
            v800 = 512506055;
            v801 = (MsoReserveTag *)&v1463;
            goto LABEL_1925;
          }
          StreamClose(v1167);
          v1153 = 1;
          if ( !FVbaEventEnabled() )
            goto LABEL_1264;
          goto LABEL_1223;
        }
      }
LABEL_1077:
      v277 = v1160;
LABEL_1078:
      if ( !FEnableForeignFileProtectedView() )
      {
        OSRR::SetAppAllowed((OSRR *)&v1235, 0);
        if ( (unsigned int)XLOSRR::FMustUseOsr((XLOSRR *)&v1235) )
        {
          if ( SbFromHpCore(v1167) )
            StreamClose(v1167);
          v576 = (__int64 *)NtCurrentTeb()->ThreadLocalStoragePointer;
          v1167 = 0;
          v1153 = 0;
          v577 = *v576;
          vhpstm = 0;
          errDeferred = 0;
          v578 = *(_QWORD *)(v577 + 304);
          *(_DWORD *)(v578 + 2024) = 0;
          *(_DWORD *)(v578 + 2028) = 0;
          v114 = -2147024809;
          XlsDiag::LogSetHrCoreTag(-2147024809, 0x179771Au);
          v68 = v1158;
          v73 = 1;
LABEL_1083:
          LOBYTE(v264) = v1151;
          goto LABEL_1664;
        }
      }
      v68 = v1158;
      if ( v1158 && (int)LoadRecovery::Lrmode(v1158) > 0 )
      {
        v73 = 1;
        v685 = 1;
      }
      else
      {
        v685 = 0;
        v73 = 1;
      }
      if ( v685 )
      {
        v686 = PivotOperationBase::PSxview((PivotOperationBase *)v68);
        *((_WORD *)v686 + 18) |= 8u;
      }
      FSwitchLoadActionType(2, 0, (struct LoadRecovery *)v68);
      MaxPathStzPoke::MaxPathStzPoke((MaxPathStzPoke *)v1490, (struct MaxPathHolder *)v1340);
      v687 = APPCORE::PmemheapMain((APPCORE *)&vapp);
      MaxPathHolder::MaxPathHolder((MaxPathHolder *)v1511, v687, 259, 0);
      v688 = FileSource::HrGetFileTemp(v1305, 11);
      v1152 = v688;
      v114 = v688;
      if ( v688 < 0 )
        XlsDiag::LogSetHrCoreTag(v688, 0x27413C1u);
      if ( v114 < 0 )
      {
        if ( SbFromHpCore(v1167) )
          StreamClose(v1167);
        v1167 = 0;
        vhpstm = 0;
        Error(327845);
        errDeferred = 0;
        v1153 = 0;
        MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1511);
        MaxPathStzPoke::~MaxPathStzPoke((MaxPathStzPoke *)v1490);
        goto LABEL_1083;
      }
      v689 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
      v690 = (LXBASE *)OpenTelemetry::POpenFileStageModel(v689);
      v691 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1410, 0x1F0CB5C3u);
      SXVWGEOM::RwFirst(v691);
      WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v690);
      v692 = BKORWS::Psh((BKORWS *)&v1179);
      v693 = v1157;
      v694 = v1167;
      v695 = v692;
      v696 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1511);
      v697 = (wchar_t *)SlicerViewImpl::PSlicerView((SlicerViewImpl *)v1490);
      v1239 = FLoadForeign(v1570, v697, v696, v694, a5, a8, &v1260, v693, (struct XLOSRR *)&v1235, v1273, v695);
      v698 = v1239;
      MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1511);
      MaxPathStzPoke::~MaxPathStzPoke((MaxPathStzPoke *)v1490);
      if ( v698 == -2 )
      {
        v1153 = 0;
        goto LABEL_1323;
      }
      v1153 = v1239;
      if ( !v698 )
      {
LABEL_1323:
        if ( OSRR::FReadyForOsr((OSRR *)&v1235) )
        {
          v68 = v1158;
          v408 = v1161;
          v1155 = 1;
          goto LABEL_744;
        }
        v1152 = -2146827284;
        v114 = -2146827284;
        XlsDiag::LogSetHrCoreTag(-2146827284, 0x230E205u);
      }
      v596 = v1154;
      if ( v1154 )
      {
        if ( (unsigned int)IMsoOLDocument::IsInFileSys(v1157) )
        {
          if ( v1153
            || (v699 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL), *(_QWORD *)(v699 + 40))
            && (*(_DWORD *)(*(_QWORD *)(v699 + 40) + 884LL) & 0x200) != 0 )
          {
            v700 = (wchar_t **)XLSBOOK::Plxtab(*(XLSBOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                       + 304LL)
                                                           + 40LL));
            FreeHpstTempPath((struct STB *)v700);
            v701 = FileSource::StzFilePath((FileSource *)v1305);
            if ( (int)HrStDupSt(v701, v700 + 21) < 0 )
              v700[21] = 0;
          }
        }
      }
      goto LABEL_1272;
    }
    v1167 = 0;
    if ( v1210 != 1 )
    {
      sub_1413EEE50();
      goto LABEL_997;
    }
    LOBYTE(v546) = v1183;
    v547 = sub_141224980(v1157, v546, &v1195);
    v1210 = v547;
    if ( v1195 )
    {
      OSRR::SetAppAllowed((OSRR *)&v1235, 0);
LABEL_997:
      v547 = v1210;
    }
    if ( v547 < 0 )
    {
      v114 = v547;
      XlsDiag::LogSetHrCoreTag(v547, 0x1797718u);
      v583 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
      v584 = OpenTelemetry::POpenFileStageModel(v583);
      v585 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1406, 0x1F0CB5C6u);
      v586 = SXVWGEOM::RwFirst(v585);
      WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v584, 2214658821LL, v586);
      goto LABEL_1093;
    }
    if ( v1154 && !vpoldocument )
      vpoldocument = v1157;
    errDeferred = 0;
    if ( !v1169 )
    {
      v548 = BOOKO::Plocaleinfo((BOOKO *)&vapp);
      if ( FStBundled(v548, &v1567) )
        StripProjNameSt(&v1567, 257);
      goto LABEL_1005;
    }
    v554 = BOOKO::Plocaleinfo((BOOKO *)&vapp);
    if ( FStBundled(v554, &v1567) )
      StripProjNameSt(&v1567, 257);
    v168 = v1171;
LABEL_1026:
    v1169 = 1;
    v555 = FileSource::HrGetFileTemp(v1305, 6);
    v1152 = v555;
    v114 = v555;
    if ( v555 < 0 )
    {
      XlsDiag::LogSetHrCoreTag(v555, 0x274139Eu);
      Error(327845);
      goto LABEL_466;
    }
    v556 = 1049729;
    if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                   + 104LL) != 2 )
      v556 = 1025;
    v1167 = FileSource::StreamOpen((FileSource *)v1305, v556, 0);
    while ( 1 )
    {
      if ( a7 == 1024 )
        goto LABEL_1053;
      if ( !SbFromHpCore(v1167) )
        goto LABEL_1053;
      v557 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
      if ( *(_QWORD *)(v557 + 40) )
      {
        if ( (*(_DWORD *)(*(_QWORD *)(v557 + 40) + 884LL) & 0x200) != 0 )
          goto LABEL_1053;
      }
      if ( v168 || !(unsigned int)FIsExecutableFile(*((void **)v1167 + 1)) )
        break;
      v168 = 1;
      v1171 = 1;
      v1214 = 1;
      StreamClose(v1167);
LABEL_1038:
      v558 = 1048704;
      if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                     + 104LL) != 2 )
        v558 = 0;
      v1167 = FileSource::StreamOpen((FileSource *)v1305, ((v168 != 0) + 1024) | (unsigned int)v558, 0);
      v559 = 0;
      if ( !v1157 )
        goto LABEL_1043;
      errDeferred = _IMsoOLDocument_GetDeferredError(v1157);
      v560 = errDeferred == 0;
      if ( !errDeferred )
      {
        v559 = 0;
LABEL_1043:
        if ( !v168 )
        {
          if ( SbFromHpCore(v1167) )
            v559 = 0;
          else
            v559 = (unsigned __int16)v1167;
        }
        errDeferred = v559;
        v560 = v559 == 0;
      }
      if ( !v560 )
        goto LABEL_1026;
    }
    v561 = FileSource::HrGetFileTemp(v1305, 8);
    v1152 = v561;
    v114 = v561;
    if ( v561 < 0 )
    {
      XlsDiag::LogSetHrCoreTag(v561, 0x27413A0u);
      goto LABEL_1088;
    }
    v562 = BKORWS::Psh((BKORWS *)v1350);
    if ( !(unsigned int)sub_140798B90(v562, (__int64)v1339, (__int64)v1305, a16, (__int64)&v1235) )
    {
LABEL_1089:
      v581 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
      *(_DWORD *)(v581 + 2024) = 0;
      *(_DWORD *)(v581 + 2028) = 0;
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1220;
      LOBYTE(v264) = 0;
      StreamClose(v1167);
      v68 = v1158;
      if ( v1158 )
      {
        v582 = PivotOperationBase::PSxview((PivotOperationBase *)v1158);
        *((_WORD *)v582 + 18) |= 8u;
      }
      v114 = -2146827284;
      XlsDiag::LogSetHrCoreTag(-2146827284, 0x179770Fu);
      goto LABEL_518;
    }
LABEL_1053:
    if ( SbFromHpCore(v1167) )
      goto LABEL_1022;
  }
  while ( (_WORD)v1167 != 2 );
  v563 = FileSource::HrGetFileTemp(v1305, 9);
  v1152 = v563;
  v114 = v563;
  if ( v563 < 0 )
  {
    XlsDiag::LogSetHrCoreTag(v563, 0x27413A1u);
LABEL_1088:
    Error(327845);
    goto LABEL_1089;
  }
  v564 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
  v565 = (LXBASE *)OpenTelemetry::POpenFileStageModel(v564);
  v566 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1405, 0x1F0CB5C8u);
  SXVWGEOM::RwFirst(v566);
  WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v565);
  if ( !XllFlighting::FComponentizedXlls(v567) )
  {
    v1289 = 0;
    v573 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1350);
    v114 = HrRidLoadDLLFile_Deprecated(v573, &v1289, &v1166);
    v1152 = v114;
    if ( v114 < 0 )
      goto LABEL_1133;
    if ( v1289 )
    {
LABEL_1065:
      errDeferred = 0;
      v1153 = 3;
    }
    else
    {
      v572 = 506057947;
      v114 = -2147287008;
      v1152 = -2147287008;
LABEL_1064:
      XlsDiag::LogSetHrCoreTag(-2147287008, v572);
      OkAlert(196759, v1568);
    }
    goto LABEL_439;
  }
  v568 = BKORWS::Psh((BKORWS *)v1350);
  v569 = PcellwGuard::PcellwGuard((PcellwGuard *)v1501, v568);
  LOBYTE(v570) = 1;
  XllFileFromOutsideCalc = XllHost::HrLoadXllFileFromOutsideCalc(*(_QWORD *)v569, v570, 0);
  v1166 = XllFileFromOutsideCalc;
  if ( XllFileFromOutsideCalc >= 0 )
    goto LABEL_1065;
  if ( XllFileFromOutsideCalc == -2080308478 )
  {
    v572 = 36758018;
    v114 = -2147287008;
    v1152 = -2147287008;
    goto LABEL_1064;
  }
LABEL_1133:
  if ( !v1166 )
  {
    MsoShipAssertTagProc(545059735);
    if ( !v1166 )
      v1166 = -2080308954;
  }
  v605 = NtCurrentTeb()->ThreadLocalStoragePointer;
  vfPretendNotStg = 0;
  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v605 + 304LL) + 336LL) = v1220;
  XlsDiag::LogSetHrCoreTag(-2146827284, 0x17976D3u);
  LOBYTE(v606) = std::nullopt;
  std::optional<Measurements::MeasureElapsedTime>::operator=(v1512, v606);
  LOBYTE(v607) = std::nullopt;
  sub_14240D570(v1524, v607);
  OsfOpenScope::Destroy((OsfOpenScope *)v1485);
  XslClear((struct XSL *)&v1541);
  ClearStatusString(11);
  v608 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
  if ( *(_QWORD *)(v608 + 40) != v1301 )
    XlsDiag::SendTraceTag(20509321, 187, 10, 4, L"Jumped during load, global book changed");
  if ( v1302 )
  {
    v608 = 304;
    if ( *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL) == v1302 )
    {
      XlsDiag::SendTraceTag(20509322, 187, 10, 4, L"Jumping after loading a book, possibly corrupt");
      if ( !BOOK::Pioldoc(*(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL)) )
      {
        HrFreeBook(*(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL));
        v609 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1369, 0x237630DEu);
        v610 = SXVWGEOM::RwFirst(v609);
        v611 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 128LL);
        v612 = 0;
        while ( v611 )
        {
          v612 = v611[1];
          if ( v612 )
            break;
          v611 = (_QWORD *)*v611;
        }
        LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v612 + 96), 0, v610);
      }
    }
  }
  if ( v1303 != (struct SH *)65534 )
  {
    v1116 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1370, 0x237630DDu);
    v1117 = SXVWGEOM::RwFirst(v1116);
    v1118 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 128LL);
    v1119 = 0;
    while ( v1118 )
    {
      v1119 = v1118[1];
      if ( v1119 )
        break;
      v1118 = (_QWORD *)*v1118;
    }
    LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v1119 + 96), v1303, v1117);
  }
  if ( v1182 )
    Mso::PerfScenario::HrEndScenario(
      (Mso::PerfScenario *)&vmsoperfidOfficeXLFileOpen,
      (const struct Mso::PerfScenario::MsoPerfScenarioId *)v608);
  if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL) + 8LL)
      & 1) != 0 )
  {
    CrashAlert(0, "Crash in FFileLoad (ignoreable/informational)");
    if ( v1153 && lp )
      FailBookLoad(lp);
    if ( iUseSentinelFile > 0 && hObject != (HANDLE)-1LL )
    {
      CloseHandle(hObject);
      hObject = (HANDLE)-1LL;
    }
  }
  v1120 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
  *(_DWORD *)(v1120 + 2024) = 0;
  *(_DWORD *)(v1120 + 2028) = 0;
  GLOBALS::GLOBALSCONTAINER::m_fs = 0;
  sub_1411BEB10();
  sub_141232A50();
  LOBYTE(v1121) = std::nullopt;
  std::optional<FutureFunctionLabelCreationTracker>::operator=(v1516, v1121);
  LOBYTE(v1122) = std::nullopt;
  std::optional<AutomaticNumberConversionLoadPasteHelper>::operator=(v1344, v1122);
  LOBYTE(v1123) = std::nullopt;
  sub_14240D5B0(v1234, v1123);
  std::optional<XlSecurity::XllTelemetry>::~optional<XlSecurity::XllTelemetry>(v1351);
  v604 = v1166;
  if ( v1166 < 0 )
  {
    v1043 = 512506062;
LABEL_2135:
    XlsDiag::LogSetHrCoreTag(v604, v1043);
  }
LABEL_2136:
  sub_140475F40(v1234);
  std::optional<AutomaticNumberConversionLoadPasteHelper>::~optional<AutomaticNumberConversionLoadPasteHelper>(v1344);
  std::optional<FutureFunctionLabelCreationTracker>::~optional<FutureFunctionLabelCreationTracker>(v1516);
  FileSource::~FileSource((FileSource *)v1305);
  MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1350);
  MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1348);
  MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1482);
  MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1339);
  MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1462);
  MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1340);
  std::optional<OlDocFilePath>::~optional<OlDocFilePath>(v1539);
  Mso::TCntPtr<Uxpp::UxppAnnotationsService>::~TCntPtr<Uxpp::UxppAnnotationsService>(&v1252);
  std::_Optional_destruct_base<Measurements::MeasureElapsedTime,0>::~_Optional_destruct_base<Measurements::MeasureElapsedTime,0>(v1512);
  sub_140475070(v1524);
  std::pair<enum Osf::ModifierKeyFlags const,std::wstring>::~pair<enum Osf::ModifierKeyFlags const,std::wstring>(v1546);
  std::unique_ptr<Measurements::StartOrContinueCapture,HeapDeleter<Measurements::StartOrContinueCapture>>::~unique_ptr<Measurements::StartOrContinueCapture,HeapDeleter<Measurements::StartOrContinueCapture>>(&v1272);
  std::unique_ptr<XlsActivity::XlsDetachedActivity,HeapDeleter<XlsActivity::XlsDetachedActivity>>::~unique_ptr<XlsActivity::XlsDetachedActivity,HeapDeleter<XlsActivity::XlsDetachedActivity>>(&v1311);
  Mso::TCntPtr<IWebAddInOptionalProperties>::~TCntPtr<IWebAddInOptionalProperties>(&v1179);
  Mso::TCntPtr<Uxpp::UxppAnnotationsService>::~TCntPtr<Uxpp::UxppAnnotationsService>(&v1276);
  std::optional<NumberConversionSettingsOverride>::~optional<NumberConversionSettingsOverride>(v1519);
  OsfOpenScope::~OsfOpenScope((OsfOpenScope *)v1485);
  FishbowlTracker::~FishbowlTracker((FishbowlTracker *)v1540);
  std::_Optional_destruct_base<CorruptionMetaData,0>::~_Optional_destruct_base<CorruptionMetaData,0>(v1538);
  std::_Optional_destruct_base<SecuritySettings::ExternalLinks::TrustedLocationCacheScope,0>::~_Optional_destruct_base<SecuritySettings::ExternalLinks::TrustedLocationCacheScope,0>(v1192);
  std::optional<XlSecurity::XllTelemetry>::~optional<XlSecurity::XllTelemetry>(v1351);
  sub_140474C00(&v1208);
  sub_140474D20(&v1190);
  return (unsigned int)v604;
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
