# HrFileLoadEx(wchar_t *,int,int,int,int,PLINT * *,int,int,IMsoOLDocument * *,int,int,int,wchar_t const *,wchar_t const *,FileLoadContext *,XlLoadReason,wchar_t const *,XlSyncStateChangeListenerLoad *,VersionHistoryWindowParams *,int *)

- ea: `0x1402eeff0`
- end: `0x1402fc7df`
- name: `?HrFileLoadEx@@YAJPEA_WHHHHPEAPEAUPLINT@@HHPEAPEAUIMsoOLDocument@@HHHPEB_W3PEAVFileLoadContext@@W4XlLoadReason@@3PEAVXlSyncStateChangeListenerLoad@@PEAVVersionHistoryWindowParams@@PEAH@Z`
- size: `55279`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _DWORD, _QWORD, _DWORD, _DWORD, _DWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `578`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1402eaba0`
- `0x140477060`
- `0x14086eea0`
- `0x141448e10`
- `0x142320de0`
- `0x14240fac0`

## callees

- `0x1400452f0`
- `0x1400517b8`
- `0x140052450`
- `0x140052478`
- `0x1400524c0`
- `0x14005252c`
- `0x140052580`
- `0x140052640`
- `0x140054ed0`
- `0x140055ff0`
- `0x1400562d0`
- `0x140058170`
- `0x140058730`
- `0x1400587e0`
- `0x140059030`
- `0x14006d920`
- `0x140075ee0`
- `0x140075fc0`
- `0x140076aac`
- `0x140076af0`
- `0x140077c80`
- `0x140079120`
- `0x14007d3b0`
- `0x14007dab0`
- `0x14007f360`
- `0x14007f530`
- `0x14007f5c0`
- `0x1400957a0`
- `0x1400a6e60`
- `0x1400b2a00`
- `0x1400b48b0`
- `0x1400b4ab0`
- `0x1400c7910`
- `0x1400cb568`
- `0x1400cbff0`
- `0x1400da440`
- `0x1400f8270`
- `0x140105260`
- `0x140159070`
- `0x140160270`
- `0x1401756e0`
- `0x14018e990`
- `0x140190a30`
- `0x14019a6d4`
- `0x14019e4b0`
- `0x14019f580`
- `0x1401b55f0`
- `0x1401b9d30`
- `0x1401bc184`
- `0x1401bcfc0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1402f02a6`
- `KERNEL32!CloseHandle` at `0x1402fc5cf`
- `KERNEL32!CloseHandle` at `0x1402f02a6`
- `KERNEL32!CloseHandle` at `0x1402fc5cf`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x1402f0ba3`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x1402f0ba3`
- `USER32!SetForegroundWindow` at `0x1402fb0c0`
- `USER32!SetForegroundWindow` at `0x1402fb0c0`
- `MSO!__imp_?MsoDoWatsonAlertBegin@@YAXK_NJPEAUWADD@@@Z` at `0x1402fbf24`
- `MSO!__imp_?MsoDoWatsonAlertBegin@@YAXK_NJPEAUWADD@@@Z` at `0x1402fbf24`
- `MSO!__imp_?IsVersionCrawlForRepairEnabled@History@Mso@@YA_NXZ` at `0x1402fbac0`
- `MSO!__imp_?IsVersionCrawlForRepairEnabled@History@Mso@@YA_NXZ` at `0x1402fbac0`
- `MSO!__imp_?MsoHrSimpleOfflineOpenFile@@YAJPEAUIMsoOLDocument@@P6AJW4MSOSCA@@0K@ZK@Z` at `0x1402fb900`
- `MSO!__imp_?MsoHrSimpleOfflineOpenFile@@YAJPEAUIMsoOLDocument@@P6AJW4MSOSCA@@0K@ZK@Z` at `0x1402fb900`
- `MSO!__imp_?MsoHrMetadataEvent@@YAJPEBUIMsoOLDocument@@W4_MSOFME@@PEAX@Z` at `0x1402f8b20`
- `MSO!__imp_?MsoHrMetadataEvent@@YAJPEBUIMsoOLDocument@@W4_MSOFME@@PEAX@Z` at `0x1402f8b20`
- `MSO!__imp_?MsoDoWatsonAlertEnd@@YAXPEAUWADD@@PEB_W@Z` at `0x1402fc000`
- `MSO!__imp_?MsoDoWatsonAlertEnd@@YAXPEAUWADD@@PEB_W@Z` at `0x1402fc000`
- `MSO!__imp_?MsoFDrmErrorCode@@YAHJ@Z` at `0x1402f2c37`
- `MSO!__imp_?MsoFDrmErrorCode@@YAHJ@Z` at `0x1402f2c4e`
- `MSO!__imp_?MsoFDrmErrorCode@@YAHJ@Z` at `0x1402f3228`
- `MSO!__imp_?MsoFDrmErrorCode@@YAHJ@Z` at `0x1402f2c37`
- `MSO!__imp_?MsoFDrmErrorCode@@YAHJ@Z` at `0x1402f2c4e`
- `MSO!__imp_?MsoFDrmErrorCode@@YAHJ@Z` at `0x1402f3228`
- `MSO!__imp_?MsoServerErrorAlert@@YAXW4_MSOSRVERRTYPE@@PEB_W1@Z` at `0x1402fad44`
- `MSO!__imp_?MsoServerErrorAlert@@YAXW4_MSOSRVERRTYPE@@PEB_W1@Z` at `0x1402fad44`
- `MSO!__imp_?MsoHrTaxonomyOnDocOpen@@YAJPEAUIMsoOLDocument@@@Z` at `0x1402f8b32`
- `MSO!__imp_?MsoHrTaxonomyOnDocOpen@@YAJPEAUIMsoOLDocument@@@Z` at `0x1402f8b32`
- `MSO!__imp_?MsoServerErrorTypeGet@@YA?AW4_MSOSRVERRTYPE@@PEAPEA_W@Z` at `0x1402fad36`
- `MSO!__imp_?MsoServerErrorTypeGet@@YA?AW4_MSOSRVERRTYPE@@PEAPEA_W@Z` at `0x1402fad36`
- `MSO!__imp_?MsoFShouldGatekeep@@YAHPEBU_msoreg@@@Z` at `0x1402f218e`
- `MSO!__imp_?MsoFShouldGatekeep@@YAHPEBU_msoreg@@@Z` at `0x1402f218e`
- `Mso98Win32Client!__imp_?MsoSetReadWriteOnSaveIoldoc@@YAXPEAUIMsoOLDocument@@H@Z` at `0x1402fa66a`
- `Mso98Win32Client!__imp_?MsoSetReadWriteOnSaveIoldoc@@YAXPEAUIMsoOLDocument@@H@Z` at `0x1402fa760`
- `Mso98Win32Client!__imp_?MsoSetReadWriteOnSaveIoldoc@@YAXPEAUIMsoOLDocument@@H@Z` at `0x1402fa66a`
- `Mso98Win32Client!__imp_?MsoSetReadWriteOnSaveIoldoc@@YAXPEAUIMsoOLDocument@@H@Z` at `0x1402fa760`
- `Mso98Win32Client!__imp_?IsDocumentWindowEventManagerEnabled@EventMgr@DocumentWindow@Mso@@YA_NXZ` at `0x1402f80ee`
- `Mso98Win32Client!__imp_?IsDocumentWindowEventManagerEnabled@EventMgr@DocumentWindow@Mso@@YA_NXZ` at `0x1402f80ee`
- `Mso98Win32Client!__imp_?FIsHttpRedirFile@@YAHPEB_WHHHPEAH@Z` at `0x1402f0be0`
- `Mso98Win32Client!__imp_?FIsHttpRedirFile@@YAHPEB_WHHHPEAH@Z` at `0x1402f0be0`
- `Mso98Win32Client!__imp_?MsoFConvertHttpRedirUNCToHttp@@YAHPEB_WPEA_WH@Z` at `0x1402f0c00`
- `Mso98Win32Client!__imp_?MsoFConvertHttpRedirUNCToHttp@@YAHPEB_WPEA_WH@Z` at `0x1402f0c00`
- `Mso98Win32Client!__imp_?MsoFReservedWzPersistentName@@YAHPEB_W@Z` at `0x1402f0bb7`
- `Mso98Win32Client!__imp_?MsoFReservedWzPersistentName@@YAHPEB_W@Z` at `0x1402f0bb7`
- `Mso98Win32Client!__imp_?MsoFReadWriteOnSaveIoldoc@@YAHPEAUIMsoOLDocument@@@Z` at `0x1402fa6ec`
- `Mso98Win32Client!__imp_?MsoFReadWriteOnSaveIoldoc@@YAHPEAUIMsoOLDocument@@@Z` at `0x1402fa6ec`
- `Mso98Win32Client!__imp_?MsoFIsInFileSysWzPersistentName@@YA_NPEB_W0@Z` at `0x1402f008a`
- `Mso98Win32Client!__imp_?MsoFIsInFileSysWzPersistentName@@YA_NPEB_W0@Z` at `0x1402f0460`
- `Mso98Win32Client!__imp_?MsoFIsInFileSysWzPersistentName@@YA_NPEB_W0@Z` at `0x1402f08c0`
- `Mso98Win32Client!__imp_?MsoFIsInFileSysWzPersistentName@@YA_NPEB_W0@Z` at `0x1402f008a`
- `Mso98Win32Client!__imp_?MsoFIsInFileSysWzPersistentName@@YA_NPEB_W0@Z` at `0x1402f0460`
- `Mso98Win32Client!__imp_?MsoFIsInFileSysWzPersistentName@@YA_NPEB_W0@Z` at `0x1402f08c0`
- `Mso98Win32Client!__imp_?MetroFGetErrorWz@@YA_NJPEA_WPEAI@Z` at `0x1402fbaa0`
- `Mso98Win32Client!__imp_?MetroFGetErrorWz@@YA_NJPEA_WPEAI@Z` at `0x1402fbaa0`
- `Mso98Win32Client!__imp_?MsoFDrmUIEnabled@@YAHXZ` at `0x1402fa8f0`
- `Mso98Win32Client!__imp_?MsoFDrmUIEnabled@@YAHXZ` at `0x1402fa8f0`
- `Mso30Win32Client!__imp_?MsoCreateOpTimer@@YAJHHPEAPEAUIMsoOpTimer@@@Z` at `0x1402efa21`
- `Mso30Win32Client!__imp_?MsoCreateOpTimer@@YAJHHPEAPEAUIMsoOpTimer@@@Z` at `0x1402efa21`
- `Mso30Win32Client!__imp_?IsEnabled@Config@AppGuard@@YA_NXZ` at `0x1402f2780`
- `Mso30Win32Client!__imp_?IsEnabled@Config@AppGuard@@YA_NXZ` at `0x1402f2780`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1402ef50c`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1402efbb1`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1402f0190`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1402f1eaa`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1402f1ecc`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1402ef50c`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1402efbb1`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1402f0190`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1402f1eaa`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x1402f1ecc`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402ef452`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f066a`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f1202`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f12b5`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f13ad`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f13c0`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f25c0`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f29c3`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f2f8e`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f3319`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f3c40`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f5b6e`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f672c`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f9e96`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402fab63`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402fb3d9`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402ef452`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f066a`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f1202`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f12b5`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f13ad`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f13c0`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f25c0`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f29c3`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f2f8e`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f3319`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f3c40`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f5b6e`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f672c`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402f9e96`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402fab63`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1402fb3d9`
- `Mso20Win32Client!__imp_?HrCancelScenario@PerfScenario@Mso@@YAJPEBUMsoPerfScenarioId@12@@Z` at `0x1402ef4b4`
- `Mso20Win32Client!__imp_?HrCancelScenario@PerfScenario@Mso@@YAJPEBUMsoPerfScenarioId@12@@Z` at `0x1402ef4b4`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1402ef140`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1402f53e0`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1402f546d`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1402f8456`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1402f9c49`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1402f9c6c`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1402fa009`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1402ef140`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1402f53e0`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1402f546d`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1402f8456`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1402f9c49`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1402f9c6c`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1402fa009`
- `Mso20Win32Client!__imp_?MsoResetLastWAlertHR@@YAXXZ` at `0x1402f5b85`
- `Mso20Win32Client!__imp_?MsoResetLastWAlertHR@@YAXXZ` at `0x1402f5b85`
- `Mso20Win32Client!__imp_?FScenarioActive@PerfScenario@Mso@@YA_NPEBUMsoPerfScenarioId@12@@Z` at `0x1402ef4a3`
- `Mso20Win32Client!__imp_?FScenarioActive@PerfScenario@Mso@@YA_NPEBUMsoPerfScenarioId@12@@Z` at `0x1402ef4a3`
- `Mso20Win32Client!__imp_?MsoSetLastWAlertHRTag@@YAXJK@Z` at `0x1402f5b63`
- `Mso20Win32Client!__imp_?MsoSetLastWAlertHRTag@@YAXJK@Z` at `0x1402f5b63`
- `Mso20Win32Client!__imp_?HrEndScenario@PerfScenario@Mso@@YAJPEBUMsoPerfScenarioId@12@@Z` at `0x1402f02eb`
- `Mso20Win32Client!__imp_?HrEndScenario@PerfScenario@Mso@@YAJPEBUMsoPerfScenarioId@12@@Z` at `0x1402fc572`
- `Mso20Win32Client!__imp_?HrEndScenario@PerfScenario@Mso@@YAJPEBUMsoPerfScenarioId@12@@Z` at `0x1402f02eb`
- `Mso20Win32Client!__imp_?HrEndScenario@PerfScenario@Mso@@YAJPEBUMsoPerfScenarioId@12@@Z` at `0x1402fc572`
- `Mso20Win32Client!__imp_?SetActivationKind@BootActivity@Mso@@SAXW4ActivationKind@12@@Z` at `0x1402ef4c0`
- `Mso20Win32Client!__imp_?SetActivationKind@BootActivity@Mso@@SAXW4ActivationKind@12@@Z` at `0x1402ef4c0`
- `Mso20Win32Client!__imp_?MsoFRegSetDw@@YAHPEBU_msoreg@@K@Z` at `0x1402ef52d`
- `Mso20Win32Client!__imp_?MsoFRegSetDw@@YAHPEBU_msoreg@@K@Z` at `0x1402ef52d`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1402f570e`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1402f88b4`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1402f88d0`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1402f8960`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1402fb425`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1402fbe65`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1402f570e`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1402f88b4`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1402f88d0`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1402f8960`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1402fb425`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1402fbe65`
- `Mso20Win32Client!__imp_??0MeasureElapsedTime@Measurements@@QEAA@UMeasurementIdType@1@_N$$QEAVStopwatch@1@@Z` at `0x1402f56d1`
- `Mso20Win32Client!__imp_??0MeasureElapsedTime@Measurements@@QEAA@UMeasurementIdType@1@_N$$QEAVStopwatch@1@@Z` at `0x1402f8880`
- `Mso20Win32Client!__imp_??0MeasureElapsedTime@Measurements@@QEAA@UMeasurementIdType@1@_N$$QEAVStopwatch@1@@Z` at `0x1402f8947`
- `Mso20Win32Client!__imp_??0MeasureElapsedTime@Measurements@@QEAA@UMeasurementIdType@1@_N$$QEAVStopwatch@1@@Z` at `0x1402fbde0`
- `Mso20Win32Client!__imp_??0MeasureElapsedTime@Measurements@@QEAA@UMeasurementIdType@1@_N$$QEAVStopwatch@1@@Z` at `0x1402f56d1`
- `Mso20Win32Client!__imp_??0MeasureElapsedTime@Measurements@@QEAA@UMeasurementIdType@1@_N$$QEAVStopwatch@1@@Z` at `0x1402f8880`
- `Mso20Win32Client!__imp_??0MeasureElapsedTime@Measurements@@QEAA@UMeasurementIdType@1@_N$$QEAVStopwatch@1@@Z` at `0x1402f8947`
- `Mso20Win32Client!__imp_??0MeasureElapsedTime@Measurements@@QEAA@UMeasurementIdType@1@_N$$QEAVStopwatch@1@@Z` at `0x1402fbde0`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1402f0240`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1402f0240`
- `Mso20Win32Client!__imp_?MsoHrCreateUrlSimpleFromUser@@YAJPEAPEAUIMsoUrl@@PEB_WKPEBU1@W4MsoUrlCreateFlags@@PEAUIMsoMemHeap@@@Z` at `0x1402ef700`
- `Mso20Win32Client!__imp_?MsoHrCreateUrlSimpleFromUser@@YAJPEAPEAUIMsoUrl@@PEB_WKPEBU1@W4MsoUrlCreateFlags@@PEAUIMsoMemHeap@@@Z` at `0x1402ef700`
- `Mso20Win32Client!__imp_?HrBeginScenario@PerfScenario@Mso@@YAJPEBUMsoPerfScenarioId@12@@Z` at `0x1402ef4cd`
- `Mso20Win32Client!__imp_?HrBeginScenario@PerfScenario@Mso@@YAJPEBUMsoPerfScenarioId@12@@Z` at `0x1402ef4cd`

## string_xrefs

- `0x1402fa53b`: `and force template load`
- `0x1402fa599`: `Loading workbook with Auto refresh load status: %d and read only mode: %d %s`
- `0x1402fa68b`: `Check for XML Load Options value: %d prior to displaying business bar`
- `0x1402f67e6`: `Jumped during load, global book changed`
- `0x1402f53ef`: `ZipItOldocSetReadOnly`
- `0x1402f9975`: `Dirtying workbook because it was loaded from a backup copy.`
- `0x1402fb06d`: `Unconditionally setting foreground window for already opened book`

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
  int v334; // edi
  struct IMemHeap *v335; // rax
  wchar_t *v336; // rax
  const wchar_t *v337; // rbx
  const wchar_t *v338; // rax
  struct SH *v339; // rbx
  struct BOOK *v340; // rax
  __int64 v341; // rax
  int v342; // eax
  unsigned int v343; // ebx
  int v344; // ecx
  __int64 v345; // r8
  char v346; // r14
  unsigned int v347; // edx
  int v348; // ecx
  struct SH *v349; // rax
  XlsActivity *v350; // rsi
  struct SH *v351; // rdi
  unsigned __int8 v352; // al
  unsigned int v353; // edx
  struct SH *v354; // rax
  XlsActivity *v355; // rsi
  struct SH *v356; // rdi
  bool v357; // cl
  int v358; // eax
  char v359; // cl
  int v360; // ecx
  const struct ILocaleInfo *v361; // rax
  unsigned __int16 v362; // ax
  int v363; // edi
  __int64 v364; // rax
  __int64 v365; // rbx
  SXVWGEOM *v366; // rax
  unsigned int v367; // eax
  unsigned __int16 v368; // ax
  int v369; // ebx
  unsigned __int16 v370; // di
  char v371; // si
  unsigned int v372; // edx
  int v373; // ecx
  const struct ILocaleInfo *v374; // rax
  OlDocFilePath *v375; // rax
  const struct Mso::Clp::IClpDocument *v376; // rbx
  struct IStorage *EncryptedStorage; // rax
  __int64 v378; // rax
  int DeferredError; // eax
  int v380; // eax
  int v381; // ebx
  char v382; // al
  struct IMemHeap *v383; // rax
  int FileTemp; // eax
  __int64 v385; // r8
  const wchar_t *v386; // rax
  struct FileSource *v387; // rdx
  bool v388; // bl
  const wchar_t *v389; // rax
  wchar_t *v390; // rdx
  __int64 v391; // rdx
  int v392; // eax
  __int64 v393; // rax
  __int64 v394; // rbx
  SXVWGEOM *v395; // rax
  unsigned int v396; // eax
  bool v397; // al
  BOOL v398; // eax
  struct SH *v399; // rax
  int v400; // ecx
  __int64 v401; // rax
  __int64 v402; // rbx
  SXVWGEOM *v403; // rax
  unsigned int v404; // eax
  __int64 v405; // rdx
  struct XPACKAGE *v406; // rax
  struct IMsoOLDocument **v407; // rsi
  __int64 *v408; // rax
  __int64 v409; // rcx
  __int64 v410; // rax
  __int64 v411; // rcx
  struct SXVIEW *v412; // rax
  int v413; // ecx
  __int64 v414; // rax
  LXBASE *v415; // rbx
  SXVWGEOM *v416; // rax
  struct SH *v417; // r13
  OlDocFilePath *v418; // rax
  struct SH *v419; // r14
  struct IMsoDocumentEncryptor *v420; // r15
  int v421; // edi
  struct OpenTelemetry *v422; // r12
  int v423; // esi
  int v424; // ebx
  struct ISlicerView *v425; // rax
  int v426; // r8d
  void *v427; // rax
  struct Api::Workbook *v428; // rax
  __int64 v429; // rcx
  OcsTransitionController *v430; // rax
  XLSBOOK *v431; // rax
  SlicerViewImpl *v432; // rax
  TAB *v433; // rbx
  OcsTransitionController *v434; // rax
  XLSBOOK *v435; // rax
  TAB *v436; // r12
  void *v437; // r14
  struct SH *v438; // rax
  unsigned __int8 v439; // al
  SXVWGEOM *v440; // rax
  unsigned int v441; // edi
  struct SH *v442; // rax
  __int64 v443; // rdx
  __int64 v444; // rcx
  _QWORD *v445; // r8
  _QWORD *v446; // rdx
  __int64 v447; // rax
  SXVWGEOM *v449; // rax
  unsigned int v450; // eax
  _QWORD *v451; // rdx
  __int64 v452; // rcx
  _QWORD *v453; // r8
  struct WNX *v454; // rcx
  const wchar_t *v455; // rax
  CorruptionMetaData *v456; // rax
  struct SXVIEW *v457; // rax
  __int64 v458; // rax
  __int64 v459; // rax
  __int64 v460; // rbx
  SXVWGEOM *v461; // rax
  unsigned int v462; // eax
  __int64 v463; // rax
  struct SXVIEW *v464; // rax
  unsigned int v465; // edi
  struct IStorage *v466; // rax
  int v467; // eax
  __int64 v468; // rax
  __int64 v469; // rcx
  OlDocFilePath *v470; // rax
  const struct Mso::Clp::IClpDocument *v471; // rbx
  struct IStorage *v472; // rax
  bool v473; // al
  OlDocFilePath *v474; // rax
  const struct Mso::Clp::IClpDocument *v475; // rbx
  struct IStorage *v476; // rax
  int v477; // ebx
  struct SXVIEW *v478; // rax
  const wchar_t *v479; // rax
  struct IMemHeap *v480; // rax
  int v481; // eax
  __int64 v482; // rax
  LXBASE *v483; // rbx
  SXVWGEOM *v484; // rax
  const wchar_t *v485; // rax
  int v486; // eax
  SXVWGEOM *v487; // rax
  unsigned int v488; // eax
  _QWORD *v489; // rdx
  __int64 v490; // rcx
  _QWORD *v491; // r8
  const wchar_t *v492; // rax
  struct WNX *v493; // rcx
  __int64 v494; // r8
  int v495; // eax
  __int64 v496; // rbx
  const wchar_t *v497; // rax
  __int64 v498; // rcx
  __int64 v499; // rcx
  unsigned int v500; // r8d
  struct IMsoOLDocument **v501; // rsi
  SXVWGEOM *v502; // rax
  unsigned int v503; // eax
  bool v504; // al
  __int64 v505; // rax
  struct SXVIEW *v506; // rax
  __int64 v507; // rax
  wchar_t **v508; // rbx
  void *v509; // rdx
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
  __int64 v539; // r8
  int v540; // eax
  __int64 v541; // rdx
  __int64 v542; // rcx
  unsigned __int64 v543; // rax
  struct SXVIEW *v544; // rax
  struct SXVIEW *v545; // rax
  struct OpenTelemetry *v546; // rax
  __int64 v547; // rdx
  int v548; // eax
  const struct ILocaleInfo *v549; // rax
  BOOL v550; // ecx
  struct STGI *v551; // rax
  unsigned int v552; // ebx
  struct IStorage *v553; // rax
  const wchar_t *v554; // rax
  const struct ILocaleInfo *v555; // rax
  int v556; // eax
  unsigned int v557; // edx
  __int64 v558; // rax
  int v559; // edx
  int v560; // eax
  bool v561; // zf
  int v562; // eax
  XlSecurity *v563; // rax
  int v564; // eax
  __int64 v565; // rax
  LXBASE *v566; // rbx
  SXVWGEOM *v567; // rax
  XllFlighting *v568; // rcx
  struct CELLW *v569; // rax
  PcellwGuard *v570; // rax
  __int64 v571; // rdx
  int XllFileFromOutsideCalc; // eax
  unsigned int v573; // edx
  const wchar_t *v574; // rax
  __int64 v575; // rax
  struct SXVIEW *v576; // rax
  __int64 *v577; // rax
  __int64 v578; // rcx
  __int64 v579; // rax
  unsigned int v580; // edx
  __int64 v581; // rax
  __int64 v582; // rax
  struct SXVIEW *v583; // rax
  __int64 v584; // rax
  __int64 v585; // rbx
  SXVWGEOM *v586; // rax
  unsigned int v587; // eax
  void *v588; // rax
  __int64 v589; // rax
  int v590; // ebx
  __int64 v591; // r8
  SH *v592; // r13
  __int64 v593; // rax
  const struct BOOK *v594; // rdx
  const wchar_t *v595; // rax
  int v596; // eax
  bool v597; // r14
  __int64 v598; // rax
  wchar_t **v599; // rdi
  void *v600; // rdx
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
  void *v628; // rdx
  const wchar_t *v629; // rax
  SXVWGEOM *v630; // rax
  unsigned int v631; // eax
  struct SH *v632; // rax
  struct SH *v633; // rax
  int OptDialog; // eax
  BOOL v635; // r12d
  const wchar_t *v636; // rbx
  wchar_t *v637; // rax
  struct SH *v638; // rax
  struct IMsoOLDocument *v639; // rdi
  struct STM *v640; // r14
  struct OpenTelemetry *v641; // rbx
  const wchar_t *v642; // rsi
  wchar_t *v643; // rax
  void *v644; // rax
  struct IMsoOLDocument *v645; // rdi
  __int64 v646; // rcx
  void *v647; // rax
  int Project2; // eax
  int v649; // eax
  int HtmlFailed; // eax
  struct IMemHeap *v651; // rax
  const wchar_t *v652; // rdx
  const wchar_t *v653; // rbx
  const wchar_t *v654; // rax
  int Xml; // eax
  void *v656; // rax
  int v657; // edi
  struct IMsoOLDocument *v658; // rsi
  __int64 v659; // rcx
  void *v660; // rax
  XLSWORKBOOK *v661; // rax
  OcsTransitionController *v662; // rax
  struct Api::CoauthTransitionState *v663; // rax
  __int64 v664; // rcx
  int v665; // eax
  bool v666; // al
  int v667; // eax
  __int64 v668; // rcx
  XLSBOOK *v669; // rax
  SXVWGEOM *v670; // rax
  unsigned int v671; // eax
  struct IMsoOLDocument *v672; // r10
  int v673; // eax
  int v674; // ebx
  struct SH *v675; // rax
  int v676; // esi
  int v677; // ebx
  int v678; // edi
  wchar_t *v679; // rax
  int BookHtml; // eax
  __int64 v681; // rax
  wchar_t **v682; // rdi
  void *v683; // rdx
  const wchar_t *v684; // rax
  __int64 v685; // rax
  __int64 v686; // rbx
  SXVWGEOM *v687; // rax
  unsigned int v688; // eax
  char v689; // al
  struct SXVIEW *v690; // rax
  struct IMemHeap *v691; // rax
  int v692; // eax
  __int64 v693; // rax
  LXBASE *v694; // rbx
  SXVWGEOM *v695; // rax
  struct SH *v696; // rax
  struct IMsoOLDocument *v697; // rdi
  struct STM *v698; // r14
  struct OpenTelemetry *v699; // rbx
  const wchar_t *v700; // rsi
  wchar_t *v701; // rax
  int v702; // ebx
  __int64 v703; // rax
  wchar_t **v704; // rdi
  void *v705; // rdx
  const wchar_t *v706; // rax
  BOOL v707; // ebx
  BOOL v708; // r8d
  BOOL v709; // edi
  BOOL v710; // r9d
  __int64 v711; // rax
  __int64 v712; // r10
  const struct OLDocFactory *v713; // rax
  BOOK *v714; // rbx
  SXVWGEOM *v715; // rax
  unsigned int v716; // eax
  __int64 v717; // rcx
  void *v718; // rax
  __int64 v719; // rdx
  unsigned __int8 v720; // al
  unsigned int v721; // eax
  SXVWGEOM *v722; // rax
  unsigned int v723; // eax
  bool v724; // r8
  bool v725; // r13
  __int64 v726; // rax
  LXBASE *v727; // rbx
  SXVWGEOM *v728; // rax
  __int64 v729; // rax
  void *v730; // rax
  __int64 v731; // rax
  int v732; // eax
  char v733; // r12
  Mso::DocumentWindow::EventMgr *v734; // rcx
  WN *v735; // rcx
  UIFRAME *v736; // rax
  struct IMsoOLDocument *v737; // rbx
  Excel::XlMso *v738; // rax
  HWND v739; // r8
  struct IMsoOLDocument *v740; // rax
  struct Api::CoauthTransitionState *v741; // rbx
  unsigned int v742; // eax
  struct Api::Workbook *v743; // rax
  struct XlFileProtocol *Protocol; // rbx
  MsoReserveTag *v745; // rax
  struct BOOK *v746; // rdi
  unsigned int v747; // ebx
  struct SH *v748; // rax
  __int64 v749; // rax
  __int64 v750; // rdx
  _DWORD *v751; // rax
  __int64 v752; // rax
  struct Api::Workbook *v753; // rax
  XlAsyncFileIO *v754; // rax
  XlRenameHandler *v755; // rax
  unsigned int v756; // ebx
  __int64 v757; // rax
  __int64 v758; // rax
  struct Api::Workbook *v759; // rax
  struct IMerge *v760; // rax
  __int64 v761; // rax
  __int64 v762; // rax
  struct Api::Workbook *v763; // rax
  struct Mso::Telemetry::IDataFieldCollection *v764; // rbx
  unsigned int refreshed; // eax
  __int64 v766; // rax
  IEndpointAgent *v767; // rax
  ClassifyLabelProtectManager *v768; // rax
  IdleLoop *v769; // rcx
  __int64 v770; // rax
  AutoSaveManager *v771; // rax
  struct BOOKO *v772; // rdx
  int v773; // eax
  SXVWGEOM *v774; // rax
  unsigned int v775; // r10d
  __int64 v776; // rcx
  struct SH *v777; // r9
  _QWORD *v778; // rax
  __int64 v779; // rcx
  _QWORD *v780; // rdx
  __int64 v781; // rax
  struct WNX *v782; // rdi
  void *v783; // r14
  struct WNX *v784; // rax
  struct WNX *v785; // rbx
  struct WNX *v786; // rdx
  int v787; // ecx
  struct SH *v788; // r12
  SXVWGEOM *v789; // rax
  unsigned int v790; // eax
  __int64 v791; // rdx
  __int64 v792; // rcx
  _QWORD *v793; // r8
  _QWORD *v794; // rdx
  __int64 v795; // rdx
  __int64 v796; // rcx
  __int64 v797; // rax
  struct CS *v798; // rax
  SXVWGEOM *v799; // rax
  unsigned int v800; // eax
  __int64 v801; // rdx
  __int64 v802; // rcx
  _QWORD *v803; // r8
  _QWORD *v804; // rdx
  unsigned int v805; // edx
  MsoReserveTag *v806; // rcx
  __int64 v807; // rax
  __int64 v808; // r8
  int v809; // eax
  __int64 v810; // rax
  __int64 v811; // rax
  __int64 v812; // r8
  struct BOOK *v813; // r8
  IMsoOLDocument *v814; // rax
  struct IMsoOLDocument *v815; // rax
  struct IMsoOLDocument *v816; // rax
  unsigned int v817; // esi
  __int64 v818; // r14
  SXVWGEOM *v819; // rax
  unsigned int v820; // edi
  unsigned int v821; // ebx
  struct IMsoOLDocument *v822; // rax
  struct IMsoOLDocument *v823; // rax
  SXVWGEOM *v824; // rax
  unsigned int v825; // ebx
  struct IMsoOLDocument *v826; // rax
  struct IMsoOLDocument *v827; // rax
  struct IMsoOLDocument *v828; // rax
  struct IMsoOLDocument *v829; // rax
  struct IMsoOLDocument *v830; // rax
  struct IMsoOLDocument *v831; // rax
  const wchar_t *v832; // rax
  struct IMsoOLDocument *v833; // rax
  void *v834; // rax
  __int64 v835; // r8
  int v836; // eax
  __int64 v837; // rcx
  struct BOOK *v838; // rax
  SXVWGEOM *v839; // rax
  unsigned int v840; // ebx
  struct LXTAB *v841; // rax
  TAB *v842; // rax
  struct SH *v843; // rax
  _QWORD *v844; // rdx
  __int64 v845; // rcx
  _QWORD *v846; // r8
  int v847; // ebx
  const wchar_t *v848; // rax
  struct IMsoOLDocument *v849; // rax
  struct IMsoOLDocument *v850; // rax
  __int64 v851; // rcx
  const wchar_t *v852; // rax
  SXVWGEOM *v853; // rax
  unsigned int v854; // eax
  _QWORD *v855; // rdx
  __int64 v856; // rcx
  _QWORD *v857; // r8
  __int64 v858; // rcx
  struct BOOK *v859; // rcx
  const struct Api::Workbook *v860; // rax
  Excel::AppGuard::Actions **v861; // r8
  int v862; // eax
  wchar_t *v863; // rdi
  char v864; // si
  __int64 v865; // rcx
  struct BOOK *v866; // rbx
  __int64 v867; // r8
  SXVWGEOM *v868; // rax
  unsigned int v869; // eax
  _QWORD *v870; // r8
  __int64 v871; // rcx
  _QWORD *v872; // rdx
  __int64 v873; // rcx
  __int64 v874; // rax
  __int64 v875; // rcx
  __int64 v876; // rcx
  __int64 v877; // r8
  __int64 v878; // rax
  SXVWGEOM *v879; // rax
  unsigned int v880; // eax
  _QWORD *v881; // rdx
  __int64 v882; // rcx
  _QWORD *v883; // r8
  SXVWGEOM *v884; // rax
  unsigned int v885; // eax
  _QWORD *v886; // rdx
  __int64 v887; // rcx
  _QWORD *v888; // r8
  void *v889; // rax
  void *v890; // rax
  __int64 v891; // rcx
  __int64 v892; // rcx
  int v893; // eax
  __int64 v894; // rcx
  struct IMsoOLDocument *v895; // rax
  __int64 v896; // rcx
  struct IMsoOLDocument *v897; // rax
  SXVWGEOM *v898; // rax
  unsigned int v899; // eax
  __int64 v900; // rcx
  __int64 v901; // rax
  SXVWGEOM *v902; // rax
  unsigned int v903; // eax
  const struct Api::Workbook *v904; // rbx
  struct ExpressionService *v905; // rax
  __int64 v906; // rax
  void *v907; // rax
  struct XlsActivity *v908; // rbx
  const struct Api::Workbook *v909; // rax
  struct LXTAB *v910; // rbx
  TAB *v911; // rbx
  struct SH *v912; // rax
  unsigned __int8 v913; // cl
  struct SH *v914; // rax
  struct Mso::Telemetry::IDataFieldCollection *v915; // rax
  struct Mso::Telemetry::IDataFieldCollection *v916; // rax
  SXVWGEOM *v917; // rax
  unsigned int v918; // eax
  _QWORD *v919; // rdx
  __int64 v920; // rcx
  _QWORD *v921; // r8
  const wchar_t *v922; // rax
  __int64 v923; // rax
  OlDocFilePath *v924; // rax
  struct IMsoOLDocument *v925; // rbx
  SXVWGEOM *v926; // rax
  unsigned int v927; // eax
  SXVWGEOM *v928; // rax
  unsigned int v929; // eax
  __int64 v930; // rax
  __int64 v931; // rcx
  struct Api::Workbook *v932; // rax
  struct Mso::Telemetry::IDataFieldCollection *v933; // rax
  __int64 v934; // r8
  int v935; // edx
  unsigned __int64 v936; // rax
  struct IMsoOLDocument *v937; // rax
  CardView::DataElementRecord *v938; // rax
  PivotMetadataCache *v939; // rax
  OcsTransitionController *v940; // rax
  struct Api::CoauthTransitionState *v941; // rax
  struct IMsoOLDocument *v942; // rax
  char v943; // bl
  BKORWS *v944; // rdi
  CardView::DataElementRecord *v945; // rax
  struct SH *v946; // rbx
  __int64 v947; // rax
  struct SH *v948; // rbx
  struct Api::Workbook *v949; // rax
  struct QuickLoadContext *v950; // r8
  struct IMemHeap *v951; // rbx
  unsigned int v952; // edi
  struct Api::Workbook *v953; // rax
  XlAsyncFileIO *v954; // rax
  __int64 v955; // rax
  int v956; // eax
  bool v957; // cf
  __int64 v958; // r8
  struct Api::CoauthTransitionState *v959; // rax
  __int64 v960; // rax
  struct Api::Workbook *v961; // rax
  struct Api::Workbook *v962; // rbx
  const struct WN *v963; // r8
  struct IMemHeap *v964; // rdi
  struct BOOK *v965; // rcx
  unsigned int v966; // ebx
  ZrtUtility *v967; // rax
  int v968; // r9d
  __int64 v969; // rax
  BKORWS *v970; // rbx
  QuickLoadContext *v971; // rax
  const wchar_t *v972; // rbx
  __int64 v973; // rcx
  const struct BOOK *v974; // rcx
  int Only; // eax
  int v976; // ecx
  int v977; // r8d
  struct BOOK *v978; // rdi
  __int64 v979; // rax
  __int64 v980; // rax
  BOOL v981; // ebx
  struct IMsoOLDocument *v982; // rax
  bool v983; // bl
  unsigned int v984; // eax
  struct IMsoOLDocument *v985; // rax
  struct IMsoOLDocument *v986; // rax
  Api::RichDataSharedManager *v987; // rax
  Api::LinkedEntityFeature *LinkedEntityFeature; // rax
  RichDataManagerHost *v989; // rax
  const struct Api::Workbook *v990; // rdx
  CleanupWorkbookStylesBusinessBar *v991; // rax
  struct Api::Workbook *v992; // rdx
  unsigned __int64 v993; // rbx
  unsigned int v994; // eax
  char v995; // al
  struct OSRC *Osrc; // rax
  int v997; // eax
  unsigned int v998; // edx
  CorruptionMetaData *v999; // rax
  char v1000; // al
  LoadRecovery *v1001; // rcx
  int v1002; // edx
  unsigned __int64 v1003; // rax
  int v1004; // ebx
  bool v1005; // al
  unsigned __int64 BookCorrupt; // rbx
  void *v1007; // rax
  unsigned __int64 v1008; // rax
  __int64 v1009; // rcx
  unsigned int v1010; // eax
  int v1011; // ebx
  const wchar_t *v1012; // rax
  int v1013; // r8d
  __int64 v1014; // r8
  wchar_t *v1015; // rbx
  const wchar_t *v1016; // rbx
  unsigned int v1017; // eax
  struct IMsoOLDocument **v1018; // rbx
  SXVWGEOM *v1019; // rax
  unsigned int v1020; // eax
  OlDocFilePath *v1021; // rax
  struct IMsoOLDocument **v1022; // rbx
  SXVWGEOM *v1023; // rax
  unsigned int v1024; // eax
  SXVWGEOM *v1025; // rax
  unsigned int v1026; // eax
  unsigned int v1027; // edx
  int v1028; // ecx
  int v1029; // eax
  unsigned int v1030; // edx
  int v1031; // eax
  int v1032; // ecx
  char v1033; // al
  unsigned int v1034; // eax
  unsigned __int64 Count; // rax
  UIFRAME *v1036; // rax
  HWND v1037; // rax
  __int64 v1038; // rax
  __int64 v1039; // rbx
  SXVWGEOM *v1040; // rax
  unsigned int v1041; // eax
  __int64 v1042; // rax
  __int64 v1043; // rax
  __int64 v1044; // rax
  __int64 v1045; // rax
  SXVWGEOM *v1046; // rax
  unsigned int v1047; // eax
  unsigned int v1048; // edx
  SXVWGEOM *v1049; // rax
  unsigned int v1050; // eax
  int v1051; // eax
  __int64 Title; // rax
  __int64 v1053; // rdx
  __int64 v1054; // rsi
  SXVWGEOM *v1055; // rax
  int v1056; // ebx
  Mso::Telemetry *v1057; // rax
  unsigned int v1058; // r9d
  int v1059; // eax
  __int64 v1060; // r8
  SXVWGEOM *v1061; // rax
  unsigned int v1062; // eax
  const wchar_t *v1063; // rax
  struct IMsoOLDocument *v1064; // rax
  __int64 v1065; // rdx
  ZrtUtility *v1066; // rax
  struct IMsoOLDocument *v1067; // rdx
  __int64 v1068; // rax
  CorruptionMetaData *v1069; // rax
  unsigned __int8 v1070; // al
  __int64 v1071; // r9
  __int64 v1072; // r8
  struct IMsoOLDocument *v1073; // rax
  struct BOOK *v1074; // r8
  int v1075; // eax
  CorruptionMetaData *v1076; // rax
  Mso::History *v1077; // rcx
  int v1078; // ecx
  int v1079; // ecx
  unsigned int v1080; // edx
  wchar_t *v1081; // rdx
  int v1082; // ecx
  ODFROBUSTLOAD *AffectedProcessSessionId; // rax
  wchar_t *v1084; // rdx
  int v1085; // ecx
  ODFROBUSTLOAD *v1086; // rax
  ODFROBUSTLOAD *v1087; // rax
  __int64 v1088; // rax
  __int64 v1089; // r8
  struct Api::Workbook *v1090; // rax
  struct IPowerQueryWorkbookManager *Manager; // rax
  struct IMsoOLDocument *v1092; // rax
  __int64 v1093; // rcx
  unsigned int v1094; // eax
  unsigned int v1095; // ebx
  int v1096; // eax
  int v1097; // edx
  int v1098; // eax
  __int64 v1099; // rax
  SXVWGEOM *v1100; // rax
  unsigned int v1101; // eax
  __int64 v1102; // r8
  __int64 v1103; // rax
  __int64 v1104; // rax
  int Sz; // ebx
  int v1106; // eax
  __int64 *v1107; // rcx
  int v1108; // ebx
  __int64 v1109; // rcx
  int v1110; // edx
  __int64 v1111; // rcx
  int v1112; // eax
  unsigned int v1113; // eax
  SXVWGEOM *v1114; // rax
  unsigned int v1115; // eax
  bool v1116; // dl
  SXVWGEOM *v1117; // rax
  SXVWGEOM *v1118; // rax
  unsigned int v1119; // eax
  const wchar_t *v1120; // rax
  SXVWGEOM *v1121; // rax
  unsigned int v1122; // eax
  _QWORD *v1123; // rdx
  __int64 v1124; // rcx
  __int64 v1125; // rax
  __int64 v1126; // rdx
  __int64 v1127; // rdx
  __int64 v1128; // rdx
  struct IStream **v1129; // [rsp+20h] [rbp-140h]
  struct IStream **v1130; // [rsp+20h] [rbp-140h]
  struct IStream **v1131; // [rsp+28h] [rbp-138h]
  struct IStream **v1132; // [rsp+28h] [rbp-138h]
  wchar_t *v1133; // [rsp+30h] [rbp-130h]
  struct LoadRecovery *v1134; // [rsp+38h] [rbp-128h]
  struct LoadRecovery *v1135; // [rsp+38h] [rbp-128h]
  struct XlsActivity *v1136; // [rsp+40h] [rbp-120h]
  struct XlsActivity *v1137; // [rsp+40h] [rbp-120h]
  wchar_t *v1138; // [rsp+48h] [rbp-118h]
  struct ENV *v1139; // [rsp+48h] [rbp-118h]
  struct OpenTelemetry *v1140; // [rsp+50h] [rbp-110h]
  bool v1141; // [rsp+50h] [rbp-110h]
  struct LoadRecovery *v1142; // [rsp+58h] [rbp-108h]
  struct IMsoDocumentEncryptor *v1143; // [rsp+60h] [rbp-100h]
  bool v1144; // [rsp+68h] [rbp-F8h]
  struct IMsoOLDocument *v1145; // [rsp+70h] [rbp-F0h]
  const wchar_t *v1146; // [rsp+78h] [rbp-E8h]
  struct VersionHistoryWindowParams *v1147; // [rsp+80h] [rbp-E0h]
  struct BOOK *v1148; // [rsp+80h] [rbp-E0h]
  bool v1149; // [rsp+88h] [rbp-D8h]
  int v1150[2]; // [rsp+90h] [rbp-D0h]
  int v1151; // [rsp+90h] [rbp-D0h]
  bool v1152; // [rsp+A0h] [rbp-C0h]
  int v1153; // [rsp+A8h] [rbp-B8h]
  int v1154; // [rsp+C0h] [rbp-A0h]
  int *v1155; // [rsp+C0h] [rbp-A0h]
  char v1156; // [rsp+E0h] [rbp-80h]
  int v1157; // [rsp+E4h] [rbp-7Ch]
  int v1158; // [rsp+E8h] [rbp-78h] BYREF
  bool v1159; // [rsp+ECh] [rbp-74h]
  unsigned __int8 v1160; // [rsp+EDh] [rbp-73h] BYREF
  struct BOOK *lp; // [rsp+F0h] [rbp-70h] BYREF
  struct IMsoOLDocument *v1162; // [rsp+F8h] [rbp-68h] BYREF
  wchar_t *v1163; // [rsp+100h] [rbp-60h]
  bool v1164; // [rsp+108h] [rbp-58h]
  wchar_t *v1165; // [rsp+110h] [rbp-50h]
  struct IMsoOLDocument **v1166; // [rsp+118h] [rbp-48h]
  char v1167; // [rsp+120h] [rbp-40h]
  char v1168; // [rsp+121h] [rbp-3Fh]
  char v1169; // [rsp+122h] [rbp-3Eh]
  bool v1170; // [rsp+123h] [rbp-3Dh]
  int v1171; // [rsp+124h] [rbp-3Ch] BYREF
  struct STM *v1172; // [rsp+128h] [rbp-38h] BYREF
  char v1173; // [rsp+130h] [rbp-30h]
  char v1174; // [rsp+131h] [rbp-2Fh]
  char v1175; // [rsp+132h] [rbp-2Eh]
  int v1176; // [rsp+134h] [rbp-2Ch]
  int v1177; // [rsp+138h] [rbp-28h] BYREF
  bool v1178; // [rsp+13Ch] [rbp-24h]
  char v1179; // [rsp+13Dh] [rbp-23h]
  bool v1180; // [rsp+13Eh] [rbp-22h]
  bool v1181; // [rsp+13Fh] [rbp-21h] BYREF
  int v1182; // [rsp+140h] [rbp-20h] BYREF
  int v1183; // [rsp+144h] [rbp-1Ch]
  __int64 v1184; // [rsp+148h] [rbp-18h] BYREF
  bool v1185; // [rsp+150h] [rbp-10h]
  bool v1186; // [rsp+151h] [rbp-Fh]
  bool v1187; // [rsp+152h] [rbp-Eh]
  bool v1188; // [rsp+153h] [rbp-Dh]
  char v1189; // [rsp+154h] [rbp-Ch]
  unsigned int v1190; // [rsp+158h] [rbp-8h]
  char v1191; // [rsp+15Ch] [rbp-4h]
  int v1192; // [rsp+160h] [rbp+0h] BYREF
  char v1193; // [rsp+164h] [rbp+4h]
  bool v1194; // [rsp+165h] [rbp+5h]
  char v1195; // [rsp+168h] [rbp+8h] BYREF
  char v1196; // [rsp+169h] [rbp+9h]
  bool v1197[4]; // [rsp+16Ch] [rbp+Ch] BYREF
  bool v1198; // [rsp+170h] [rbp+10h] BYREF
  int v1199; // [rsp+174h] [rbp+14h] BYREF
  int v1200; // [rsp+178h] [rbp+18h] BYREF
  unsigned int v1201; // [rsp+17Ch] [rbp+1Ch] BYREF
  struct BOOK *v1202; // [rsp+180h] [rbp+20h] BYREF
  bool v1203; // [rsp+188h] [rbp+28h] BYREF
  char v1204; // [rsp+189h] [rbp+29h]
  bool v1205; // [rsp+18Ah] [rbp+2Ah]
  unsigned __int8 v1206; // [rsp+18Bh] [rbp+2Bh]
  char v1207; // [rsp+18Ch] [rbp+2Ch]
  bool v1208; // [rsp+18Dh] [rbp+2Dh] BYREF
  bool v1209; // [rsp+18Eh] [rbp+2Eh] BYREF
  char v1210; // [rsp+18Fh] [rbp+2Fh] BYREF
  char v1211; // [rsp+190h] [rbp+30h] BYREF
  bool v1212; // [rsp+191h] [rbp+31h] BYREF
  char v1213; // [rsp+194h] [rbp+34h] BYREF
  char v1214; // [rsp+195h] [rbp+35h]
  int v1215; // [rsp+198h] [rbp+38h]
  char v1216; // [rsp+19Ch] [rbp+3Ch]
  bool v1217; // [rsp+19Dh] [rbp+3Dh] BYREF
  XlsActivity *v1218; // [rsp+1A0h] [rbp+40h] BYREF
  int v1219; // [rsp+1A8h] [rbp+48h]
  struct STGI *v1220; // [rsp+1B0h] [rbp+50h]
  int v1221; // [rsp+1B8h] [rbp+58h] BYREF
  int v1222; // [rsp+1BCh] [rbp+5Ch]
  int v1223; // [rsp+1C0h] [rbp+60h] BYREF
  int v1224; // [rsp+1C4h] [rbp+64h] BYREF
  struct ENV *v1225; // [rsp+1C8h] [rbp+68h]
  bool v1226; // [rsp+1D0h] [rbp+70h] BYREF
  int v1227; // [rsp+1D4h] [rbp+74h] BYREF
  int v1228; // [rsp+1D8h] [rbp+78h] BYREF
  int v1229; // [rsp+1E0h] [rbp+80h]
  bool v1230; // [rsp+1E8h] [rbp+88h]
  char v1231; // [rsp+1E9h] [rbp+89h]
  char v1232; // [rsp+1EAh] [rbp+8Ah] BYREF
  char v1233; // [rsp+1EBh] [rbp+8Bh] BYREF
  int v1234; // [rsp+1ECh] [rbp+8Ch] BYREF
  int v1235; // [rsp+1F0h] [rbp+90h] BYREF
  int v1236; // [rsp+1F4h] [rbp+94h]
  unsigned int v1237; // [rsp+1F8h] [rbp+98h] BYREF
  wchar_t *v1238; // [rsp+200h] [rbp+A0h]
  char v1239[8]; // [rsp+208h] [rbp+A8h] BYREF
  int v1240; // [rsp+210h] [rbp+B0h] BYREF
  int v1241; // [rsp+218h] [rbp+B8h]
  _BYTE *v1242; // [rsp+220h] [rbp+C0h]
  BOOL v1243; // [rsp+228h] [rbp+C8h]
  int v1244; // [rsp+230h] [rbp+D0h]
  int v1245; // [rsp+234h] [rbp+D4h] BYREF
  _BYTE v1246[4]; // [rsp+238h] [rbp+D8h] BYREF
  unsigned int v1247; // [rsp+23Ch] [rbp+DCh]
  int v1248; // [rsp+240h] [rbp+E0h] BYREF
  void *v1249; // [rsp+248h] [rbp+E8h] BYREF
  struct IMsoOLDocument **v1250; // [rsp+250h] [rbp+F0h]
  struct IMsoPKMClient *v1251; // [rsp+258h] [rbp+F8h] BYREF
  int v1252; // [rsp+260h] [rbp+100h]
  int v1253; // [rsp+264h] [rbp+104h] BYREF
  int v1254; // [rsp+268h] [rbp+108h]
  int v1255; // [rsp+26Ch] [rbp+10Ch] BYREF
  struct IMsoDocumentEncryptor *v1256; // [rsp+270h] [rbp+110h] BYREF
  struct IMsoOpTimer *v1257; // [rsp+278h] [rbp+118h] BYREF
  HANDLE hObject; // [rsp+280h] [rbp+120h] BYREF
  int v1259; // [rsp+288h] [rbp+128h]
  _BYTE v1260[2]; // [rsp+28Ch] [rbp+12Ch] BYREF
  __int16 v1261; // [rsp+28Eh] [rbp+12Eh] BYREF
  unsigned int v1262; // [rsp+290h] [rbp+130h] BYREF
  BOOL v1263; // [rsp+294h] [rbp+134h]
  int v1264; // [rsp+298h] [rbp+138h] BYREF
  int v1265; // [rsp+29Ch] [rbp+13Ch] BYREF
  int v1266; // [rsp+2A0h] [rbp+140h] BYREF
  int v1267; // [rsp+2A4h] [rbp+144h] BYREF
  int v1268; // [rsp+2A8h] [rbp+148h] BYREF
  int v1269; // [rsp+2ACh] [rbp+14Ch] BYREF
  __int64 v1270; // [rsp+2B0h] [rbp+150h] BYREF
  struct XLXMLMAP *v1271; // [rsp+2B8h] [rbp+158h] BYREF
  const wchar_t *v1272; // [rsp+2C0h] [rbp+160h]
  struct SH *v1273; // [rsp+2C8h] [rbp+168h]
  struct REVERT *v1274; // [rsp+2D0h] [rbp+170h] BYREF
  wchar_t *v1275; // [rsp+2D8h] [rbp+178h]
  int v1276; // [rsp+2E0h] [rbp+180h] BYREF
  __int64 v1277; // [rsp+2E8h] [rbp+188h] BYREF
  struct VersionHistoryWindowParams *v1278; // [rsp+2F0h] [rbp+190h]
  BKORWS *v1279; // [rsp+2F8h] [rbp+198h]
  struct WNX *v1280; // [rsp+300h] [rbp+1A0h]
  struct IMsoUrl *v1281; // [rsp+308h] [rbp+1A8h] BYREF
  int v1282; // [rsp+310h] [rbp+1B0h] BYREF
  int v1283; // [rsp+314h] [rbp+1B4h] BYREF
  int v1284; // [rsp+318h] [rbp+1B8h] BYREF
  int v1285; // [rsp+31Ch] [rbp+1BCh]
  int v1286; // [rsp+320h] [rbp+1C0h] BYREF
  int v1287; // [rsp+324h] [rbp+1C4h] BYREF
  int v1288; // [rsp+328h] [rbp+1C8h] BYREF
  int v1289; // [rsp+32Ch] [rbp+1CCh] BYREF
  int v1290; // [rsp+330h] [rbp+1D0h] BYREF
  int v1291; // [rsp+334h] [rbp+1D4h] BYREF
  int v1292; // [rsp+338h] [rbp+1D8h] BYREF
  int v1293; // [rsp+33Ch] [rbp+1DCh] BYREF
  int v1294; // [rsp+340h] [rbp+1E0h] BYREF
  int v1295; // [rsp+344h] [rbp+1E4h] BYREF
  int v1296; // [rsp+348h] [rbp+1E8h] BYREF
  int v1297; // [rsp+34Ch] [rbp+1ECh] BYREF
  struct IStorage *v1298; // [rsp+350h] [rbp+1F0h] BYREF
  wchar_t *Src; // [rsp+358h] [rbp+1F8h]
  char v1300[8]; // [rsp+360h] [rbp+200h] BYREF
  struct IMemHeap *v1301; // [rsp+368h] [rbp+208h]
  SH *v1302; // [rsp+370h] [rbp+210h]
  __int64 v1303; // [rsp+378h] [rbp+218h]
  struct IMsoOLDocument *v1304; // [rsp+380h] [rbp+220h] BYREF
  struct IMemHeap *v1305; // [rsp+388h] [rbp+228h] BYREF
  __int64 v1306; // [rsp+390h] [rbp+230h]
  struct BOOK *v1307; // [rsp+398h] [rbp+238h]
  struct SH *v1308; // [rsp+3A0h] [rbp+240h]
  int v1309; // [rsp+3A8h] [rbp+248h] BYREF
  _BYTE v1310[128]; // [rsp+3B0h] [rbp+250h] BYREF
  struct IStream *v1311; // [rsp+430h] [rbp+2D0h] BYREF
  struct STM *v1312; // [rsp+438h] [rbp+2D8h] BYREF
  unsigned __int64 v1313; // [rsp+440h] [rbp+2E0h]
  char v1314[8]; // [rsp+448h] [rbp+2E8h] BYREF
  char v1315[8]; // [rsp+450h] [rbp+2F0h] BYREF
  __int64 v1316; // [rsp+458h] [rbp+2F8h] BYREF
  struct IStream *v1317; // [rsp+460h] [rbp+300h] BYREF
  _BYTE v1318[40]; // [rsp+468h] [rbp+308h] BYREF
  int v1319; // [rsp+490h] [rbp+330h] BYREF
  int v1320; // [rsp+494h] [rbp+334h]
  int v1321; // [rsp+498h] [rbp+338h]
  int v1322; // [rsp+49Ch] [rbp+33Ch] BYREF
  int v1323; // [rsp+4A0h] [rbp+340h]
  int v1324; // [rsp+4A4h] [rbp+344h] BYREF
  unsigned int v1325; // [rsp+4A8h] [rbp+348h] BYREF
  int v1326; // [rsp+4ACh] [rbp+34Ch] BYREF
  int v1327; // [rsp+4B0h] [rbp+350h]
  int v1328; // [rsp+4B4h] [rbp+354h] BYREF
  int v1329; // [rsp+4B8h] [rbp+358h] BYREF
  int v1330; // [rsp+4BCh] [rbp+35Ch] BYREF
  int v1331; // [rsp+4C0h] [rbp+360h] BYREF
  int v1332; // [rsp+4C4h] [rbp+364h] BYREF
  Api::ReloadContext *v1333; // [rsp+4C8h] [rbp+368h] BYREF
  char v1334[8]; // [rsp+4D0h] [rbp+370h] BYREF
  struct Api::ReloadContext *v1335; // [rsp+4D8h] [rbp+378h] BYREF
  struct WNX *v1336; // [rsp+4E0h] [rbp+380h]
  struct IMsoOLDocument *v1337; // [rsp+4E8h] [rbp+388h] BYREF
  __int64 v1338; // [rsp+4F0h] [rbp+390h]
  int *v1339; // [rsp+4F8h] [rbp+398h]
  int v1340; // [rsp+500h] [rbp+3A0h] BYREF
  _BYTE v1341[24]; // [rsp+508h] [rbp+3A8h] BYREF
  int v1342; // [rsp+520h] [rbp+3C0h] BYREF
  char v1343[8]; // [rsp+528h] [rbp+3C8h] BYREF
  _BYTE v1344[40]; // [rsp+530h] [rbp+3D0h] BYREF
  _BYTE v1345[40]; // [rsp+558h] [rbp+3F8h] BYREF
  unsigned __int64 v1346; // [rsp+580h] [rbp+420h]
  struct CVINFO *v1347; // [rsp+588h] [rbp+428h] BYREF
  char v1348[8]; // [rsp+590h] [rbp+430h] BYREF
  _BYTE v1349[16]; // [rsp+598h] [rbp+438h] BYREF
  struct SHTI *v1350; // [rsp+5A8h] [rbp+448h] BYREF
  struct IMsoOLDocument *v1351; // [rsp+5B0h] [rbp+450h] BYREF
  char v1352[8]; // [rsp+5B8h] [rbp+458h] BYREF
  _BYTE v1353[40]; // [rsp+5C0h] [rbp+460h] BYREF
  struct IMsoOLDocument *v1354; // [rsp+5E8h] [rbp+488h]
  _BYTE v1355[40]; // [rsp+5F0h] [rbp+490h] BYREF
  _BYTE v1356[32]; // [rsp+618h] [rbp+4B8h] BYREF
  char v1357; // [rsp+638h] [rbp+4D8h] BYREF
  char v1358; // [rsp+63Ch] [rbp+4DCh] BYREF
  char v1359; // [rsp+640h] [rbp+4E0h] BYREF
  char v1360; // [rsp+644h] [rbp+4E4h] BYREF
  char v1361; // [rsp+648h] [rbp+4E8h] BYREF
  char v1362[4]; // [rsp+64Ch] [rbp+4ECh] BYREF
  char v1363; // [rsp+650h] [rbp+4F0h] BYREF
  char v1364; // [rsp+654h] [rbp+4F4h] BYREF
  char v1365[4]; // [rsp+658h] [rbp+4F8h] BYREF
  char v1366[4]; // [rsp+65Ch] [rbp+4FCh] BYREF
  char v1367; // [rsp+660h] [rbp+500h] BYREF
  char v1368[4]; // [rsp+664h] [rbp+504h] BYREF
  char v1369; // [rsp+668h] [rbp+508h] BYREF
  char v1370; // [rsp+66Ch] [rbp+50Ch] BYREF
  char v1371[4]; // [rsp+670h] [rbp+510h] BYREF
  char v1372[4]; // [rsp+674h] [rbp+514h] BYREF
  char v1373[4]; // [rsp+678h] [rbp+518h] BYREF
  char v1374[4]; // [rsp+67Ch] [rbp+51Ch] BYREF
  char v1375[4]; // [rsp+680h] [rbp+520h] BYREF
  int v1376; // [rsp+684h] [rbp+524h]
  int v1377; // [rsp+688h] [rbp+528h]
  int v1378; // [rsp+68Ch] [rbp+52Ch]
  char v1379[4]; // [rsp+690h] [rbp+530h] BYREF
  char v1380[4]; // [rsp+694h] [rbp+534h] BYREF
  char v1381[4]; // [rsp+698h] [rbp+538h] BYREF
  char v1382[4]; // [rsp+69Ch] [rbp+53Ch] BYREF
  char v1383[4]; // [rsp+6A0h] [rbp+540h] BYREF
  char v1384[4]; // [rsp+6A4h] [rbp+544h] BYREF
  char v1385[4]; // [rsp+6A8h] [rbp+548h] BYREF
  char v1386[4]; // [rsp+6ACh] [rbp+54Ch] BYREF
  char v1387[4]; // [rsp+6B0h] [rbp+550h] BYREF
  char v1388[4]; // [rsp+6B4h] [rbp+554h] BYREF
  char v1389[4]; // [rsp+6B8h] [rbp+558h] BYREF
  char v1390[4]; // [rsp+6BCh] [rbp+55Ch] BYREF
  char v1391[4]; // [rsp+6C0h] [rbp+560h] BYREF
  char v1392[4]; // [rsp+6C4h] [rbp+564h] BYREF
  char v1393[4]; // [rsp+6C8h] [rbp+568h] BYREF
  char v1394[4]; // [rsp+6CCh] [rbp+56Ch] BYREF
  char v1395[4]; // [rsp+6D0h] [rbp+570h] BYREF
  char v1396[4]; // [rsp+6D4h] [rbp+574h] BYREF
  char v1397[4]; // [rsp+6D8h] [rbp+578h] BYREF
  char v1398[4]; // [rsp+6DCh] [rbp+57Ch] BYREF
  char v1399[4]; // [rsp+6E0h] [rbp+580h] BYREF
  char v1400[4]; // [rsp+6E4h] [rbp+584h] BYREF
  char v1401[4]; // [rsp+6E8h] [rbp+588h] BYREF
  char v1402; // [rsp+6ECh] [rbp+58Ch] BYREF
  char v1403[4]; // [rsp+6F0h] [rbp+590h] BYREF
  char v1404[4]; // [rsp+6F4h] [rbp+594h] BYREF
  char v1405[4]; // [rsp+6F8h] [rbp+598h] BYREF
  char v1406[4]; // [rsp+6FCh] [rbp+59Ch] BYREF
  char v1407[4]; // [rsp+700h] [rbp+5A0h] BYREF
  char v1408[4]; // [rsp+704h] [rbp+5A4h] BYREF
  char v1409[4]; // [rsp+708h] [rbp+5A8h] BYREF
  char v1410[4]; // [rsp+70Ch] [rbp+5ACh] BYREF
  char v1411[4]; // [rsp+710h] [rbp+5B0h] BYREF
  char v1412[4]; // [rsp+714h] [rbp+5B4h] BYREF
  char v1413[4]; // [rsp+718h] [rbp+5B8h] BYREF
  char v1414[4]; // [rsp+71Ch] [rbp+5BCh] BYREF
  char v1415[4]; // [rsp+720h] [rbp+5C0h] BYREF
  char v1416[4]; // [rsp+724h] [rbp+5C4h] BYREF
  char v1417[4]; // [rsp+728h] [rbp+5C8h] BYREF
  char v1418[4]; // [rsp+72Ch] [rbp+5CCh] BYREF
  char v1419[4]; // [rsp+730h] [rbp+5D0h] BYREF
  char v1420[4]; // [rsp+734h] [rbp+5D4h] BYREF
  char v1421[4]; // [rsp+738h] [rbp+5D8h] BYREF
  char v1422[4]; // [rsp+73Ch] [rbp+5DCh] BYREF
  char v1423[4]; // [rsp+740h] [rbp+5E0h] BYREF
  char v1424[4]; // [rsp+744h] [rbp+5E4h] BYREF
  char v1425[4]; // [rsp+748h] [rbp+5E8h] BYREF
  char v1426[4]; // [rsp+74Ch] [rbp+5ECh] BYREF
  char v1427[4]; // [rsp+750h] [rbp+5F0h] BYREF
  char v1428[4]; // [rsp+754h] [rbp+5F4h] BYREF
  char v1429[4]; // [rsp+758h] [rbp+5F8h] BYREF
  char v1430[4]; // [rsp+75Ch] [rbp+5FCh] BYREF
  char v1431[4]; // [rsp+760h] [rbp+600h] BYREF
  char v1432[4]; // [rsp+764h] [rbp+604h] BYREF
  char v1433[4]; // [rsp+768h] [rbp+608h] BYREF
  char v1434[4]; // [rsp+76Ch] [rbp+60Ch] BYREF
  char v1435[4]; // [rsp+770h] [rbp+610h] BYREF
  char v1436[4]; // [rsp+774h] [rbp+614h] BYREF
  void ***v1437; // [rsp+778h] [rbp+618h] BYREF
  char v1438[8]; // [rsp+780h] [rbp+620h] BYREF
  char v1439[8]; // [rsp+788h] [rbp+628h] BYREF
  __int64 v1440; // [rsp+790h] [rbp+630h] BYREF
  struct XLExpressionService *v1441; // [rsp+798h] [rbp+638h] BYREF
  _BYTE *v1442; // [rsp+7A0h] [rbp+640h] BYREF
  char v1443[8]; // [rsp+7A8h] [rbp+648h] BYREF
  struct IMsoOLDocument *v1444; // [rsp+7B0h] [rbp+650h] BYREF
  struct SH *v1445; // [rsp+7B8h] [rbp+658h] BYREF
  struct IMemHeap *v1446; // [rsp+7C0h] [rbp+660h] BYREF
  __int64 v1447; // [rsp+7C8h] [rbp+668h]
  struct ClpLoadContext *Context; // [rsp+7D0h] [rbp+670h]
  __int64 v1449; // [rsp+7D8h] [rbp+678h]
  __int64 v1450; // [rsp+7E0h] [rbp+680h]
  struct IMsoOLDocument *v1451; // [rsp+7E8h] [rbp+688h]
  __int64 v1452; // [rsp+7F0h] [rbp+690h]
  __int64 v1453; // [rsp+7F8h] [rbp+698h]
  struct SH *v1454; // [rsp+800h] [rbp+6A0h]
  _QWORD v1455[2]; // [rsp+808h] [rbp+6A8h] BYREF
  const char *v1456; // [rsp+818h] [rbp+6B8h] BYREF
  struct SHTI *v1457; // [rsp+820h] [rbp+6C0h] BYREF
  char v1458[4]; // [rsp+828h] [rbp+6C8h] BYREF
  char v1459[4]; // [rsp+82Ch] [rbp+6CCh] BYREF
  char v1460[4]; // [rsp+830h] [rbp+6D0h] BYREF
  char v1461[4]; // [rsp+834h] [rbp+6D4h] BYREF
  char v1462; // [rsp+838h] [rbp+6D8h] BYREF
  char v1463; // [rsp+83Ch] [rbp+6DCh] BYREF
  char v1464; // [rsp+840h] [rbp+6E0h] BYREF
  char v1465[4]; // [rsp+844h] [rbp+6E4h] BYREF
  char v1466; // [rsp+848h] [rbp+6E8h] BYREF
  _BYTE v1467[40]; // [rsp+850h] [rbp+6F0h] BYREF
  char v1468; // [rsp+878h] [rbp+718h] BYREF
  int *v1469; // [rsp+880h] [rbp+720h] BYREF
  wchar_t *v1470; // [rsp+888h] [rbp+728h] BYREF
  int v1471; // [rsp+890h] [rbp+730h]
  struct SH *v1472; // [rsp+898h] [rbp+738h]
  int v1473; // [rsp+8A0h] [rbp+740h]
  void *v1474; // [rsp+8A8h] [rbp+748h]
  struct IMsoOLDocument *v1475; // [rsp+8B0h] [rbp+750h]
  BOOL v1476; // [rsp+8B8h] [rbp+758h]
  unsigned int v1477; // [rsp+8BCh] [rbp+75Ch]
  BOOL v1478; // [rsp+8C0h] [rbp+760h]
  int v1479; // [rsp+8C8h] [rbp+768h]
  struct ISlicerView *v1480; // [rsp+8D0h] [rbp+770h]
  wchar_t *v1481; // [rsp+8D8h] [rbp+778h]
  bool v1482; // [rsp+8E0h] [rbp+780h]
  bool v1483; // [rsp+8E1h] [rbp+781h]
  bool v1484; // [rsp+8E2h] [rbp+782h]
  wchar_t *v1485; // [rsp+8E8h] [rbp+788h]
  _BYTE v1486[40]; // [rsp+8F0h] [rbp+790h] BYREF
  _BYTE v1487[40]; // [rsp+918h] [rbp+7B8h] BYREF
  _BYTE v1488[24]; // [rsp+940h] [rbp+7E0h] BYREF
  _BYTE v1489[24]; // [rsp+958h] [rbp+7F8h] BYREF
  _BYTE v1490[56]; // [rsp+970h] [rbp+810h] BYREF
  _BYTE v1491[16]; // [rsp+9A8h] [rbp+848h] BYREF
  _BYTE v1492[24]; // [rsp+9B8h] [rbp+858h] BYREF
  _BYTE v1493[24]; // [rsp+9D0h] [rbp+870h] BYREF
  _BYTE v1494[24]; // [rsp+9E8h] [rbp+888h] BYREF
  _BYTE v1495[24]; // [rsp+A00h] [rbp+8A0h] BYREF
  _BYTE v1496[40]; // [rsp+A18h] [rbp+8B8h] BYREF
  __int128 v1497; // [rsp+A40h] [rbp+8E0h]
  __int128 v1498; // [rsp+A50h] [rbp+8F0h]
  __int128 v1499; // [rsp+A60h] [rbp+900h]
  __int128 v1500; // [rsp+A70h] [rbp+910h]
  __int128 v1501; // [rsp+A80h] [rbp+920h]
  __int128 v1502; // [rsp+A90h] [rbp+930h]
  __int128 v1503; // [rsp+AA0h] [rbp+940h]
  __int128 v1504; // [rsp+AB0h] [rbp+950h]
  int *v1505; // [rsp+AC0h] [rbp+960h]
  char v1506[8]; // [rsp+AC8h] [rbp+968h] BYREF
  _BYTE v1507[24]; // [rsp+AD0h] [rbp+970h] BYREF
  _BYTE v1508[24]; // [rsp+AE8h] [rbp+988h] BYREF
  _BYTE v1509[24]; // [rsp+B00h] [rbp+9A0h] BYREF
  _BYTE v1510[24]; // [rsp+B18h] [rbp+9B8h] BYREF
  wchar_t *v1511; // [rsp+B30h] [rbp+9D0h]
  __int128 v1512; // [rsp+B40h] [rbp+9E0h] BYREF
  _BYTE v1513[16]; // [rsp+B50h] [rbp+9F0h] BYREF
  _BYTE v1514[40]; // [rsp+B60h] [rbp+A00h] BYREF
  _BYTE v1515[40]; // [rsp+B88h] [rbp+A28h] BYREF
  _BYTE v1516[40]; // [rsp+BB0h] [rbp+A50h] BYREF
  _BYTE v1517[48]; // [rsp+BD8h] [rbp+A78h] BYREF
  _OWORD v1518[2]; // [rsp+C08h] [rbp+AA8h] BYREF
  __int64 v1519; // [rsp+C28h] [rbp+AC8h]
  _BYTE v1520[48]; // [rsp+C30h] [rbp+AD0h] BYREF
  _BYTE v1521[64]; // [rsp+C60h] [rbp+B00h] BYREF
  _BYTE v1522[24]; // [rsp+CA0h] [rbp+B40h] BYREF
  _BYTE v1523[24]; // [rsp+CB8h] [rbp+B58h] BYREF
  _BYTE v1524[80]; // [rsp+CD0h] [rbp+B70h] BYREF
  _QWORD v1525[12]; // [rsp+D20h] [rbp+BC0h] BYREF
  _QWORD v1526[12]; // [rsp+D80h] [rbp+C20h] BYREF
  char v1527[16]; // [rsp+DE0h] [rbp+C80h] BYREF
  char v1528[16]; // [rsp+DF0h] [rbp+C90h] BYREF
  _BYTE v1529[160]; // [rsp+E00h] [rbp+CA0h] BYREF
  _BYTE v1530[40]; // [rsp+EA0h] [rbp+D40h] BYREF
  _BYTE v1531[40]; // [rsp+EC8h] [rbp+D68h] BYREF
  _BYTE v1532[40]; // [rsp+EF0h] [rbp+D90h] BYREF
  _BYTE v1533[56]; // [rsp+F18h] [rbp+DB8h] BYREF
  _BYTE v1534[128]; // [rsp+F50h] [rbp+DF0h] BYREF
  _BYTE v1535[48]; // [rsp+FD0h] [rbp+E70h] BYREF
  _OWORD v1536[8]; // [rsp+1000h] [rbp+EA0h] BYREF
  int *v1537; // [rsp+1080h] [rbp+F20h]
  char v1538; // [rsp+1088h] [rbp+F28h]
  char v1539[32]; // [rsp+1090h] [rbp+F30h] BYREF
  char v1540[32]; // [rsp+10B0h] [rbp+F50h] BYREF
  char v1541[32]; // [rsp+10D0h] [rbp+F70h] BYREF
  char v1542[32]; // [rsp+10F0h] [rbp+F90h] BYREF
  _BYTE v1543[1584]; // [rsp+1110h] [rbp+FB0h] BYREF
  _BYTE v1544[8448]; // [rsp+1740h] [rbp+15E0h] BYREF
  _BYTE v1545[2784]; // [rsp+3840h] [rbp+36E0h] BYREF
  int v1546; // [rsp+4320h] [rbp+41C0h] BYREF
  int v1547; // [rsp+4324h] [rbp+41C4h]
  wchar_t v1548[2086]; // [rsp+4330h] [rbp+41D0h] BYREF
  wchar_t v1549[2090]; // [rsp+537Ch] [rbp+521Ch] BYREF
  struct ISlicerView *v1550; // [rsp+63D0h] [rbp+6270h]
  _BYTE v1551[40]; // [rsp+7430h] [rbp+72D0h] BYREF
  _BYTE v1552[24]; // [rsp+7458h] [rbp+72F8h] BYREF
  char v1553[24]; // [rsp+7470h] [rbp+7310h] BYREF
  unsigned int v1554; // [rsp+7488h] [rbp+7328h]
  unsigned int v1555; // [rsp+748Ch] [rbp+732Ch]
  __int64 v1556; // [rsp+74C0h] [rbp+7360h] BYREF
  int v1557; // [rsp+74C8h] [rbp+7368h]
  jmp_buf Buf; // [rsp+74D0h] [rbp+7370h] BYREF
  __int64 v1559; // [rsp+75D0h] [rbp+7470h] BYREF
  int v1560; // [rsp+75D8h] [rbp+7478h]
  jmp_buf v1561; // [rsp+75E0h] [rbp+7480h] BYREF
  __int64 v1562; // [rsp+76E0h] [rbp+7580h] BYREF
  int v1563; // [rsp+76E8h] [rbp+7588h]
  jmp_buf v1564; // [rsp+76F0h] [rbp+7590h] BYREF
  __int64 v1565; // [rsp+77F0h] [rbp+7690h] BYREF
  int v1566; // [rsp+77F8h] [rbp+7698h]
  jmp_buf v1567; // [rsp+7800h] [rbp+76A0h] BYREF
  _DWORD v1568[196]; // [rsp+7900h] [rbp+77A0h] BYREF
  _BYTE v1569[4720]; // [rsp+7C10h] [rbp+7AB0h] BYREF
  _BYTE v1570[336]; // [rsp+8E80h] [rbp+8D20h] BYREF
  wchar_t v1571[16]; // [rsp+8FD0h] [rbp+8E70h] BYREF
  wchar_t v1572; // [rsp+8FF0h] [rbp+8E90h] BYREF
  wchar_t v1573[263]; // [rsp+8FF2h] [rbp+8E92h] BYREF
  wchar_t v1574[16]; // [rsp+9200h] [rbp+90A0h] BYREF
  wchar_t v1575[264]; // [rsp+9220h] [rbp+90C0h] BYREF
  wchar_t v1576[256]; // [rsp+9430h] [rbp+92D0h] BYREF
  _BYTE v1577[528]; // [rsp+9630h] [rbp+94D0h] BYREF
  wchar_t v1578[256]; // [rsp+9840h] [rbp+96E0h] BYREF
  wchar_t v1579[256]; // [rsp+9A40h] [rbp+98E0h] BYREF
  wchar_t v1580[256]; // [rsp+9C40h] [rbp+9AE0h] BYREF
  wchar_t v1581[264]; // [rsp+9E40h] [rbp+9CE0h] BYREF
  wchar_t v1582[256]; // [rsp+A050h] [rbp+9EF0h] BYREF
  wchar_t String1[2088]; // [rsp+A250h] [rbp+A0F0h] BYREF
  char v1584[528]; // [rsp+B2A0h] [rbp+B140h] BYREF
  wchar_t v1585; // [rsp+B4B0h] [rbp+B350h] BYREF
  _BYTE v1586[4174]; // [rsp+B4B2h] [rbp+B352h] BYREF
  wchar_t v1587[2088]; // [rsp+C500h] [rbp+C3A0h] BYREF
  wchar_t v1588[4112]; // [rsp+D550h] [rbp+D3F0h] BYREF

  v21 = a15;
  v22 = a18;
  v23 = a20;
  v1166 = a9;
  v1250 = a9;
  v1275 = a13;
  v1450 = a14;
  v1272 = a17;
  v1278 = a19;
  v1247 = 0;
  v1165 = a1;
  Src = a1;
  v1229 = a2;
  v1196 = 1;
  v1219 = a4;
  v1338 = a6;
  v1279 = a15;
  v1301 = a18;
  v1339 = a20;
  sub_1402DAC5C();
  v1214 = 1;
  v1356[24] = 0;
  v24 = Mso::AB::Optimized::FeatureGate::operator bool(&byte_143FDFC30);
  v25 = a16;
  if ( v24 )
  {
    v1233 = 1;
    v1326 = 0;
    std::optional<XlSecurity::XllTelemetry>::~optional<XlSecurity::XllTelemetry>(v1356);
    std::_Optional_construct_base<XlSecurity::XllTelemetry>::_Construct<enum XlSecurity::XllTelemetry::Entry,bool>(
      v1356,
      &v1326,
      &v1233);
    v26 = (Mso::Telemetry::Activity *)std::optional<XlSecurity::XllTelemetry>::operator->(v1356);
    v27 = Mso::Telemetry::Activity::DataFields(v26);
    Mso::Telemetry::IDataFieldCollection::Add<int>(v27, "LoadReason", v25, 4);
  }
  v1197[1] = 0;
  if ( (unsigned __int8)((__int64 (*)(void))CircularReferenceTailValue::FGetFlagsShadowBag)() )
  {
    std::_Optional_destruct_base<SecuritySettings::ExternalLinks::TrustedLocationCacheScope,0>::~_Optional_destruct_base<SecuritySettings::ExternalLinks::TrustedLocationCacheScope,0>(v1197);
    std::_Optional_construct_base<SecuritySettings::ExternalLinks::TrustedLocationCacheScope>::_Construct<>(v1197);
  }
  v1164 = 0;
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
  v1158 = 0;
  v1175 = 0;
  v1267 = 0;
  v1274 = 0;
  v1174 = 0;
  v1302 = 0;
  v1273 = 0;
  v1280 = 0;
  v1336 = 0;
  v1271 = 0;
  v1228 = 0;
  lp = 0;
  v1193 = 0;
  v1168 = 0;
  v1297 = 0;
  v1237 = 0;
  v1222 = 0;
  v1235 = 0;
  v1556 = 0;
  v1177 = v29;
  v1323 = a10 & 1;
  v1199 = 256;
  v1327 = a10 & 2;
  v1557 = -1;
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
  v1254 = v31;
  if ( (v30 & 0x10) != 0
    || *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1712LL)
    || (v32 = 0, v1177) )
  {
    v32 = FOsrc() == 0;
  }
  v1285 = v32;
  hObject = (HANDLE)-1LL;
  v1178 = 0;
  v1223 = 0;
  v1167 = 0;
  v1186 = 0;
  v1251 = 0;
  v1265 = 0;
  v1190 = 0;
  v1185 = 0;
  v1179 = 0;
  v1304 = 0;
  v1194 = 0;
  v1188 = 0;
  v1206 = 0;
  v1180 = 0;
  memset_0(v1577, 0, 0x202u);
  v1215 = 1;
  v1286 = 0;
  v1269 = 0;
  v1230 = a4 != 0;
  v1216 = 0;
  v1256 = 0;
  v1308 = (struct SH *)65534;
  v1240 = 0;
  v1241 = 0;
  v1242 = 0;
  v1243 = 0;
  v1160 = 0;
  v1200 = 0;
  v1191 = 0;
  v1293 = 0;
  v1170 = 0;
  v1169 = 0;
  v33 = CountBooks();
  LOBYTE(v34) = std::weak_ordering::equivalent;
  v1259 = v33;
  v1255 = -2147467259;
  v1181 = 0;
  v1231 = 0;
  v1226 = 0;
  v1437 = &TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain;
  std::_Deleted_move_assign<std::_Optional_construct_base<CorruptionMetaData>,CorruptionMetaData>::_Deleted_move_assign<std::_Optional_construct_base<CorruptionMetaData>,CorruptionMetaData>(
    v1543,
    v34,
    &v1437);
  v1276 = 0;
  FishbowlTracker::FishbowlTracker((FishbowlTracker *)v1545, 0);
  OpenWorkbooksTracker::OpenWorkbooksTracker((OpenWorkbooksTracker *)v1439);
  v1203 = 1;
  v1198 = 0;
  v1212 = 0;
  v1204 = 0;
  v1189 = 0;
  v1205 = (a10 & 0x100000) != 0;
  OsfOpenScope::OsfOpenScope((OsfOpenScope *)v1490);
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v1303 = 304;
  if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)ThreadLocalStoragePointer + 304LL) + 2024LL) )
    MsoShipAssertTagProc(39198978);
  v36 = FeatureGateCollectionBase<LoadSaveFeatureGates>::Instance();
  dword_143FDFCF8 = (unsigned __int8)Mso::AB::Optimized::FeatureGate::operator bool(v36 + 8) ^ 1;
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
  v1234 = 68;
  v42 = v41 >= 0;
  v1192 = 0;
  v1263 = 0;
  v1347 = 0;
  Dw = iUseSentinelFile;
  v1187 = v42;
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
  if ( !v44 && !(unsigned int)FOpenSentinelFile(v1165, 393226, &hObject) )
  {
    *v23 = 0;
LABEL_137:
    OsfOpenScope::~OsfOpenScope((OsfOpenScope *)v1490);
    FishbowlTracker::~FishbowlTracker((FishbowlTracker *)v1545);
    std::_Optional_destruct_base<CorruptionMetaData,0>::~_Optional_destruct_base<CorruptionMetaData,0>(v1543);
    std::_Optional_destruct_base<SecuritySettings::ExternalLinks::TrustedLocationCacheScope,0>::~_Optional_destruct_base<SecuritySettings::ExternalLinks::TrustedLocationCacheScope,0>(v1197);
    std::optional<XlSecurity::XllTelemetry>::~optional<XlSecurity::XllTelemetry>(v1356);
    if ( v1214 )
      sub_141232FB0();
    if ( v1196 )
      sub_14240D410(&v1195);
    return 0;
  }
  v45 = (wchar_t *)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
  v1163 = v45;
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
    v1238 = v45;
  }
  else
  {
    v45 = 0;
    v1163 = 0;
    v1238 = 0;
  }
  v1305 = 0;
  v1182 = 0;
  v1268 = 0;
  v1524[64] = 0;
  v1346 = 0;
  v1313 = 0;
  if ( v46 )
  {
    memset(v1518, 0, sizeof(v1518));
    v1519 = 0;
    memset_0(v1569, 0, 0x1268u);
    (*(void (__fastcall **)(void *, struct IMemHeap **, _QWORD))(qword_144012CB0 + 8LL))(&qword_144012CB0, &v1305, 0);
    if ( (int)LoadRecovery::HrInit(
                v45,
                v1305,
                *(unsigned int *)(*(_QWORD *)(*(_QWORD *)(v1303 + *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer)
                                            + 872LL)
                                + 104LL),
                v1569,
                v1518) < 0 )
      v45 = 0;
    v1163 = v45;
    v1238 = v45;
  }
  CchStToStz(v1165, &v1585, 2086);
  v1281 = 0;
  MsoHrCreateUrlSimpleFromUser(&v1281, v1586, 0, 0, 0, 0);
  WriteOpenStartPerfEvent(v1281);
  v1184 = 0;
  v1316 = 0;
  v1277 = 0;
  MeasurementsIdFromPath(v1551, v1586);
  if ( v1166 )
    v47 = *v1166;
  else
    v47 = 0;
  v1511 = &v1585;
  v1512 = *(_OWORD *)RgchView::RgchView(v1527, &v1585);
  v48 = OpenTelemetry::SpotEnsureOpenTelemetry(v1438, &TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain, &v1512, v47);
  Mso::TCntPtr<Mso::IRefCounted>::operator=(&v1184, v48);
  Mso::TCntPtr<IWebAddInOptionalProperties>::~TCntPtr<IWebAddInOptionalProperties>(v1438);
  if ( v22 )
  {
    v49 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1184);
    Mso::TCntPtr<OpenFileEventTimings>::operator=<OpenFileEventTimings,void>(
      (char *)v22 + 2824,
      *(_QWORD *)(v49 + 30016));
  }
  v50 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1184);
  v1376 = 520926677;
  v51 = (LXBASE *)(v50 + 576);
  if ( XlDisplayElementInfoAll::FXlClient(v52) && *((_DWORD *)v51 + 7160) == -1 )
    WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v51);
  v53 = (LinkedEntityManager *)Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1184);
  v1218 = LinkedEntityManager::PRefreshManager(v53);
  v1232 = 1;
  v1261 = 1;
  v54 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1184);
  v55 = PAllocateObjectOrNull<Measurements::StartOrContinueCapture,Measurements::Identifier const &,enum Measurements::Scenario,bool>(
          (unsigned int)&TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain,
          0,
          v54 + 328,
          (unsigned int)&v1261,
          (__int64)&v1232);
  std::unique_ptr<Measurements::StartOrContinueCapture,HeapDeleter<Measurements::StartOrContinueCapture>>::reset(
    &v1277,
    v55);
  v56 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1184);
  v1377 = 520926676;
  WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo((LXBASE *)(v56 + 576));
  LODWORD(v1504) = v25;
  *(_QWORD *)&v1497 = &v1277;
  v57 = 128;
  *((_QWORD *)&v1497 + 1) = &lp;
  *(_QWORD *)&v1498 = &v1184;
  *((_QWORD *)&v1498 + 1) = &v1218;
  *(_QWORD *)&v1499 = &v1182;
  *((_QWORD *)&v1499 + 1) = &v1158;
  *(_QWORD *)&v1500 = &v1181;
  *((_QWORD *)&v1500 + 1) = v1551;
  *(_QWORD *)&v1501 = &v1160;
  *((_QWORD *)&v1501 + 1) = v1543;
  *(_QWORD *)&v1502 = &v1276;
  *((_QWORD *)&v1502 + 1) = v1545;
  *(_QWORD *)&v1503 = v1439;
  *((_QWORD *)&v1503 + 1) = &v1203;
  *((_QWORD *)&v1504 + 1) = &a10;
  v1505 = &v1177;
  v1536[0] = v1497;
  v1536[1] = v1498;
  v1536[2] = v1499;
  v1536[3] = v1500;
  v1536[4] = v1501;
  v1536[5] = v1502;
  v1536[6] = v1503;
  v1536[7] = v1504;
  v1537 = &v1177;
  LOBYTE(v57) = std::weak_ordering::equivalent;
  v1538 = 1;
  sub_1402DB1D0(v1529, v57, v1536);
  if ( v1538 )
    sub_140475000(v1536);
  LOBYTE(v58) = std::weak_ordering::equivalent;
  std::_Deleted_move_assign<std::_Optional_construct_base<Measurements::MeasureElapsedTime>,Measurements::MeasureElapsedTime>::_Deleted_move_assign<std::_Optional_construct_base<Measurements::MeasureElapsedTime>,Measurements::MeasureElapsedTime>(
    v1517,
    v58,
    &Measurements::MeasurementId::ExcelFileLoad);
  v1257 = 0;
  if ( (int)MsoCreateOpTimer(1, 1, &v1257) >= 0 )
  {
    v59 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1257);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 32LL))(v59);
  }
  v1544[8440] = 0;
  v1440 = *(_QWORD *)v21;
  std::optional<OlDocFilePath>::~optional<OlDocFilePath>(v1544);
  std::_Optional_construct_base<OlDocFilePath>::_Construct<QuickLoadContext *>(v1544, &v1440);
  v60 = v1303;
  v1573[0] = 0;
  v1572 = 0;
  v61 = 7;
  v62 = *(_QWORD *)(v1303 + *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer);
  if ( (*(_DWORD *)(*(_QWORD *)(v62 + 864) + 24LL) & 0x200000) != 0 && !*(_DWORD *)(*(_QWORD *)(v62 + 872) + 104LL) )
  {
    v63 = v1163;
    v1223 = 1;
    if ( v1163 )
      *((_DWORD *)v1163 + 16) |= 4u;
    v64 = *(_QWORD *)(v60 + *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer);
    *(_DWORD *)(*(_QWORD *)(v64 + 872) + 104LL) = (*(_DWORD *)(*(_QWORD *)(v64 + 864) + 24LL) >> 22) & 7;
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v60 + *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer) + 872LL) + 108LL) = 0;
    if ( OSRH::m_vpxlosrea )
    {
      v65 = *(_DWORD *)(*(_QWORD *)OSRH::m_vpxlosrea + 32LL);
      v1185 = (v65 & 0x20000) != 0;
      if ( (v65 & 0x20000) != 0 )
      {
        v1190 = 4;
        if ( (v65 & 0x40000) != 0 )
          v1190 = 6;
      }
    }
    else if ( !*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v60 + *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer) + 872LL)
                         + 104LL)
           && !v1177 )
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
          if ( v1166 )
          {
            v95 = *v1166;
            v1162 = v95;
            if ( v95 )
            {
              (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v95 + 56LL))(
                v95,
                0xFFFFFFFFLL,
                7);
              v1378 = 594109130;
              OlDocFilePath::FReleaseIOLDoc(&v1162, 1, 1, 0x236962CAu);
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
          std::optional<OlDocFilePath>::~optional<OlDocFilePath>(v1544);
          Mso::TCntPtr<Uxpp::UxppAnnotationsService>::~TCntPtr<Uxpp::UxppAnnotationsService>(&v1257);
          std::_Optional_destruct_base<Measurements::MeasureElapsedTime,0>::~_Optional_destruct_base<Measurements::MeasureElapsedTime,0>(v1517);
          sub_140474FD0(v1529);
          std::pair<enum Osf::ModifierKeyFlags const,std::wstring>::~pair<enum Osf::ModifierKeyFlags const,std::wstring>(v1551);
          std::unique_ptr<Measurements::StartOrContinueCapture,HeapDeleter<Measurements::StartOrContinueCapture>>::~unique_ptr<Measurements::StartOrContinueCapture,HeapDeleter<Measurements::StartOrContinueCapture>>(&v1277);
          std::unique_ptr<XlsActivity::XlsDetachedActivity,HeapDeleter<XlsActivity::XlsDetachedActivity>>::~unique_ptr<XlsActivity::XlsDetachedActivity,HeapDeleter<XlsActivity::XlsDetachedActivity>>(&v1316);
          Mso::TCntPtr<IWebAddInOptionalProperties>::~TCntPtr<IWebAddInOptionalProperties>(&v1184);
          Mso::TCntPtr<Uxpp::UxppAnnotationsService>::~TCntPtr<Uxpp::UxppAnnotationsService>(&v1281);
          std::optional<NumberConversionSettingsOverride>::~optional<NumberConversionSettingsOverride>(v1524);
          goto LABEL_137;
        }
        if ( MsoDwRegGetDw((const struct _msoreg *)&vmsoridExcelExtractDataFormulas) == 1 )
          v91 = CustomTwoAlertSecBtnDefault(262265, 0, -1161035121, -1161035120);
        else
          v91 = CustomTwoAlert(262265, 0, -1161035121, -1161035120);
        v1185 = 1;
        v561 = v91 == 102;
        v92 = 4;
        if ( v561 )
          v92 = 6;
        v1190 = v92;
        v93 = NtCurrentTeb()->ThreadLocalStoragePointer;
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v60 + *v93) + 872LL) + 104LL) = 2;
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v60 + *v93) + 872LL) + 108LL) = 0;
      }
    }
  }
  v68 = v1163;
  v69 = v1165;
  if ( v1163 )
  {
    v70 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v60 + *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer) + 872LL)
                    + 104LL);
    *(_DWORD *)v1163 = v70;
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
  sub_1402DA5D0(&v1546, a6, v61);
  v1354 = vpoldocument;
  MaxPathHolder::MaxPathHolder(
    (MaxPathHolder *)v1345,
    (struct IMemHeap *)&TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain,
    259,
    0);
  MaxPathHolder::MaxPathHolder(
    (MaxPathHolder *)v1467,
    (struct IMemHeap *)&TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain,
    259,
    0);
  MaxPathHolder::MaxPathHolder(
    (MaxPathHolder *)v1344,
    (struct IMemHeap *)&TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain,
    259,
    0);
  MaxPathHolder::MaxPathHolder(
    (MaxPathHolder *)v1487,
    (struct IMemHeap *)&TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain,
    259,
    0);
  MaxPathHolder::MaxPathHolder(
    (MaxPathHolder *)v1353,
    (struct IMemHeap *)&TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain,
    259,
    0);
  MaxPathHolder::MaxPathHolder(
    (MaxPathHolder *)v1355,
    (struct IMemHeap *)&TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain,
    259,
    0);
  FileSource::FileSource((FileSource *)v1310, (struct IMemHeap *)&TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain);
  std::_Optional_construct_base<FutureFunctionLabelCreationTracker>::_Optional_construct_base<FutureFunctionLabelCreationTracker>(v1521);
  AutoConversionParameters::AutoConversionParameters((AutoConversionParameters *)v1523);
  std::optional<AutomaticNumberConversionLoadPasteHelper>::optional<AutomaticNumberConversionLoadPasteHelper>(v1349);
  v72 = sub_1402DB550(v1260, &v1270);
  sub_1402DB470(v1239, v72);
  sub_1402DB490(v1260);
  v73 = 1;
LABEL_79:
  v1236 = 0;
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
  v1183 = 1;
  v75 = *(_QWORD *)(*(_QWORD *)(v60 + *v74) + 1328LL);
  v76 = 0;
  *(_DWORD *)(v75 + 20) = 0;
  if ( *v69 )
    v76 = a7 != 1024;
  v1159 = v76;
  v77 = (struct IMsoOLDocument *)v1166;
  if ( v1166 )
    v77 = *v1166;
  v1162 = v77;
  if ( v1177 || v1160 )
    v1219 = 1;
  v78 = *(TLSW **)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v60);
  v1306 = *((_QWORD *)v78 + 5);
  v1307 = 0;
  v1441 = TLSW::PesExpressionService(v78);
  std::optional<FutureFunctionLabelCreationTracker>::emplace<XLExpressionService *>(v1521, &v1441);
  v79 = FeatureGateCollectionBase<UserVoiceFeatureGates>::Instance();
  if ( (unsigned __int8)FeatureExposure::operator bool(v79 + 56) )
  {
    v1442 = v1523;
    std::optional<AutomaticNumberConversionLoadPasteHelper>::emplace<AutoConversionParameters *>(v1349, &v1442);
  }
  v1156 = 1;
  v80 = *(_QWORD *)(v60 + *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer);
  v1225 = *(struct ENV **)(v80 + 336);
  *(_QWORD *)(v80 + 336) = &v1556;
  v1557 = 36737602;
  v1171 = setjmp(Buf);
  if ( v1171 )
    goto LABEL_1133;
  v81 = (Excel::XlBoot **)NtCurrentTeb()->ThreadLocalStoragePointer;
  if ( !*(_QWORD *)(*(_QWORD *)((char *)*v81 + v60) + 784LL) )
    Excel::XlBoot::InitUserNameCur(*v81);
  v82 = Src;
  v83 = v1229;
  v1165 = Src;
  if ( v1327 && !(unsigned int)FFilenameFromSt(Src, Src, v1229) )
  {
    v1015 = v1238;
    if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL) + 8LL)
        & 1) == 0
      && v1238 )
    {
      LoadRecovery::Destroy((LoadRecovery *)v1238);
      FreeHpst(v1015);
      v1015 = 0;
      v1238 = 0;
    }
    v1158 = 0;
    XlsDiag::LogSetHrCoreTag(-2147024690, 0x17976D4u);
    v1155 = v1339;
    v1153 = v1259;
    v1152 = v1180;
    v1151 = -2147024690;
    v1149 = v1186;
    v1148 = v1307;
    v1146 = v1275;
    v1145 = v1162;
    v1144 = v1164;
    v1143 = v1256;
    v1142 = v1251;
    v1141 = v1200 != 0;
    v1139 = v1225;
    v1137 = v1305;
    v1135 = (struct LoadRecovery *)v1015;
    goto LABEL_2113;
  }
  v68 = v1238;
  v1163 = v1238;
  if ( v1238 )
  {
    v84 = (wchar_t *)XLSBOOK::Plxtab((XLSBOOK *)v1238);
    CchStToSt(v82, v84, 2084);
    MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1467, v82);
  }
  if ( !FileLoad::FProcessDisabledDocument(v82, v1162, v1177 != 0) )
  {
    v114 = -2147024809;
    XlsDiag::LogSetHrCoreTag(-2147024809, 0x17976D5u);
    goto LABEL_2100;
  }
  MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1353, v82);
  v85 = MaxPathHolder::SzPath((MaxPathHolder *)v1353);
  if ( MsoFIsInFileSysWzPersistentName(v85, 0) && wProjLoad != 2 && !(unsigned int)FileExists(v82) )
    FEnsureExtension(v82, v83, 0xFFFFFFFFLL, 50);
  v86 = v1162;
  if ( v1162 )
  {
    (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v1162 + 56LL))(v1162, 1, 9);
    v86 = v1162;
  }
  v87 = v1189;
  v88 = v1219;
  v1173 = v1189;
  v1176 = v1219;
  if ( v1159 )
  {
    v1201 = 2;
    v89 = v86 == 0;
    if ( v86 && (*(unsigned int (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v86 + 208LL))(v86) )
    {
      v1201 = 0;
      v90 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1544);
      OlDocFilePath::IncOpenCount(v90);
    }
    if ( v88 )
    {
      operator|=(&v1201, 1);
    }
    else if ( (a10 & 0x200) != 0 )
    {
      operator|=(&v1201, 8);
    }
    if ( (unsigned int)FFinderFile(v82)
      || vfInstallTemplates
      && *(_DWORD *)(*(_QWORD *)(v60 + *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer) + 1764LL) )
    {
      operator|=(&v1201, 32);
    }
    v98 = FeatureGateCollectionBase<LoadSaveFeatureGates>::Instance();
    if ( (unsigned __int8)Mso::AB::Optimized::FeatureGate::operator bool(v98 + 8) )
    {
      v99 = MaxPathHolder::SzPath((MaxPathHolder *)v1353);
      if ( MsoFIsInFileSysWzPersistentName(v99, 0) )
      {
        v100 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1353);
        if ( (unsigned int)FIsPathAnXll(v100, 1) )
          operator|=(&v1201, 32);
      }
    }
    if ( (a10 & 0x20000) != 0 )
      operator|=(&v1201, 256);
    LODWORD(v1129) = v1201;
    XlsDiag::SendTraceTag(41039177, 187, 100, L"FFileLoadEx: OlDocSetupFlags oldsf = 0x%x", v1129);
    if ( v89 && a16 == 16 && !(unsigned int)FOsrhInTransition() )
      operator|=(&v1201, 512);
    v101 = FeatureGateCollectionBase<ZipItFeatureGates>::Instance();
    if ( (unsigned __int8)Mso::AB::Optimized::FeatureGate::operator bool(v101 + 72) )
      v102 = 1;
    else
      v102 = v87 == 0;
    v103 = v1301;
    if ( v1301 )
    {
      v104 = (ZrtUtility *)MaxPathHolder::SzPath((MaxPathHolder *)v1353);
      if ( ZrtUtility::FCanUseServerOnlyAsyncOpen(v104, v105) && v102 )
        operator|=(&v1201, 1024);
    }
    v106 = TLSW::PesExpressionService(*(TLSW **)(v1303 + *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer));
    v107 = ExpressionService::Pwbkcoll(v106);
    RevisionLatencyOutlierTracker::RevisionLatencyOutlierTracker(v1535, v107, 16);
    v108 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1544);
    v109 = BKORWS::Psh((BKORWS *)&v1184);
    OlDocFilePath::SetOpenTelemetry(v108, v109);
    operator|=(&v1201, 4096);
    v110 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1544);
    v111 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1379, 0x236962C9u);
    v112 = SXVWGEOM::RwFirst(v111);
    v113 = OlDocFilePath::HrSetupAndRetrievePathTitle(
             v110,
             (struct FileSource *)v1310,
             &v1162,
             v82,
             &v1237,
             (enum OlDocSetupFlags *)&v1201,
             v103,
             v112,
             0,
             0);
    v114 = v113;
    if ( v113 < 0 )
      XlsDiag::LogSetHrCoreTag(v113, 0x27C1404u);
    RevisionLatencyOutlierTracker::~RevisionLatencyOutlierTracker((RevisionLatencyOutlierTracker *)v1535);
    v115 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1544);
    if ( (int)OlDocFilePath::COpenCount(v115) > 1 )
      MsoShipAssertTagProc(505205964);
    if ( v1301 )
    {
      v116 = v1162;
      v117 = APPCORE::PmemheapMain((APPCORE *)&vapp);
      v1164 = ZrtUtility::FOpeningAsServerOnlyAsync(v117, v1301, v116, v118);
    }
    if ( v114 < 0 )
    {
      if ( v1162 )
        Mso::DocumentTelemetry::AddAllDocumentTelemetryFieldsToActivity<XlsActivity,IMsoOLDocument,void>(
          v1380,
          v1218,
          v1162,
          0);
    }
    else
    {
      v119 = (ArtUserInterfaceSite *)Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1184);
      v120 = CoauthoringInternals::FCoauthoringFeatureEnabled() && XlAsyncFileIO::FCoauthorableFileIO(v1162);
      ArtUserInterfaceSite::SetCurrentToolLockState(v119, v120);
      v121 = (OpenTelemetry *)Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1184);
      OpenTelemetry::SetPoldoc(v121, v1162);
    }
    v122 = BKORWS::Psh((BKORWS *)&v1184);
    XlFileProtocolManager::SetFallbackReason(v1162, v122);
    if ( v114 < 0
      || (v123 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1544),
          !(unsigned int)OlDocFilePath::CchPath(v123)) )
    {
      if ( v1162 )
      {
        v1337 = v1162;
        (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v1162 + 56LL))(
          v1162,
          0xFFFFFFFFLL,
          7);
        v1021 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1544);
        OlDocFilePath::RecordEventForCloseOldoc(v1021, v1162, 0);
        v1022 = v1250;
        if ( v1250 && *v1250 == v1162 )
        {
          v1023 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1459, 0x236962C8u);
          v1024 = SXVWGEOM::RwFirst(v1023);
          OlDocFilePath::FReleaseIOLDoc(&v1337, 0, 1, v1024);
          *v1022 = v1337;
        }
        else
        {
          v1025 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1460, 0x236962C7u);
          v1026 = SXVWGEOM::RwFirst(v1025);
          OlDocFilePath::FReleaseIOLDoc(&v1337, 0, 1, v1026);
        }
      }
      goto LABEL_2100;
    }
    v124 = (const struct OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1544);
    v125 = FileSource::HrSetOlDocFilePath((FileSource *)v1310, v124);
    v114 = v125;
    if ( v125 < 0 )
    {
      XlsDiag::LogSetHrCoreTag(v125, 0x279F29Cu);
      goto LABEL_2100;
    }
    v126 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1544);
    v127 = OlDocFilePath::StzTitle(v126);
    if ( MaxPathHolder::FExceedsMaxFileName(*v127) )
    {
      Error(655635);
      if ( v1162 )
      {
        (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v1162 + 56LL))(
          v1162,
          0xFFFFFFFFLL,
          7);
        HrRecordEvent(v1162, 0x40000000u, 0);
        v1019 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1458, 0x236962C6u);
        v1020 = SXVWGEOM::RwFirst(v1019);
        OlDocFilePath::FReleaseIOLDoc(&v1162, 1, 1, v1020);
      }
      goto LABEL_2100;
    }
    v128 = XLFileIOMockable::HrSetPoldoc((struct FileSource *)v1310, v1162, v1279, v1218);
    v1157 = v128;
    v114 = v128;
    if ( v128 < 0 )
    {
      XlsDiag::LogSetHrCoreTag(v128, 0x279F29Du);
      goto LABEL_2100;
    }
    v129 = FileSource::StzFilePath((FileSource *)v1310);
    if ( !(unsigned int)FIsPathAnXll(v129, 1) )
    {
      v130 = v1162;
      v131 = APPCORE::PmemheapMain((APPCORE *)&vapp);
      Api::DataLossProtectionSessionManager::NotifyEvent(v131, 0, v130, 0);
    }
    if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 2972LL)
      && v1275
      && *v1275 )
    {
      CchSzToStz(v1275 + 1, &v1572, 257);
    }
    else
    {
      v132 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1544);
      v133 = OlDocFilePath::StzTitle(v132);
      CchStToStz(v133, &v1572, 257);
    }
    MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1353, v82);
    v134 = MaxPathHolder::SzPath((MaxPathHolder *)v1353);
    if ( !MsoFIsInFileSysWzPersistentName(v134, 0) && v1572 > 0xF9u )
    {
      v1572 = 249;
      MakeStStzTruncOK(&v1572, 257);
    }
    v135 = v1162;
    vpoldocument = v1162;
    v1166 = v1250;
    if ( v89 )
    {
      if ( v1250 )
      {
        *v1250 = v1162;
        v135 = v1162;
      }
      else
      {
        v1166 = &v1162;
        v1250 = &v1162;
      }
    }
    if ( v1547 || !(unsigned int)IMsoOLDocument::IsInFileSys(v135) )
    {
      v82 = v1165;
    }
    else
    {
      v1546 |= 0x10u;
      v1262 = 0;
      MaxPathSzPoke::MaxPathSzPoke((MaxPathSzPoke *)v1492, (struct MaxPathHolder *)v1344);
      v1262 = MaxPathSzPoke::CchSzBufferSize((MaxPathSzPoke *)v1492);
      v136 = *(__int64 (__fastcall **)(struct IMsoOLDocument *, const wchar_t *, unsigned int *, __int64))(*(_QWORD *)v1162 + 64LL);
      v137 = AugmentationLoop::TranslateDetectLanguagesArrayAnnotationResponse::SzId((AugmentationLoop::TranslateDetectLanguagesArrayAnnotationResponse *)v1492);
      v138 = v136(v1162, v137, &v1262, 3);
      MaxPathSzPoke::~MaxPathSzPoke((MaxPathSzPoke *)v1492);
      if ( v138 < 0 )
      {
        if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1232LL)
                       + 32LL) )
        {
          v1016 = MaxPathHolder::SzPath((MaxPathHolder *)v1353);
          v1017 = MsoServerErrorTypeGet(0);
          MsoServerErrorAlert(v1017, v1016, 0);
        }
        v114 = v138;
        XlsDiag::LogSetHrCoreTag(v138, 0x26C77DFu);
        goto LABEL_1861;
      }
      v82 = v1165;
      if ( v1262 <= 1 && (int)RootPathWithMph(v1165, (struct MaxPathHolder *)v1344) < 0 )
        MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1344, v82);
    }
    if ( (unsigned __int8)FFlagSet(v1201, 8) )
      v1178 = 1;
  }
  else
  {
    XlsDiag::LogSetHrCoreTag(-2147467259, 0x27C1405u);
    v139 = FileSource::HrSetPoldoc((FileSource *)v1310, v1162, v1279, v1218);
    v1157 = v139;
    v114 = v139;
    if ( v139 < 0 )
      XlsDiag::LogSetHrCoreTag(v139, 0x279F29Eu);
    if ( (unsigned __int8)std::shared_ptr<Mso::ActivityScope::IMsoLoggingScope>::operator bool(&v1184) )
    {
      v140 = (OpenTelemetry *)Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1184);
      OpenTelemetry::SetPoldoc(v140, v1162);
    }
    if ( v114 < 0 )
    {
      OkAlert(196655, v1573);
      v1018 = v1250;
      goto LABEL_2092;
    }
    FileSource::FGetPathname((FileSource *)v1310, v82 + 1, *v82, &v1572, 257);
    v1166 = v1250;
  }
  if ( !(unsigned int)MaxPathHolder::CchLength((MaxPathHolder *)v1344) )
  {
    v141 = FileSource::StzFilePath((FileSource *)v1310);
    MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1344, v141);
  }
  v142 = v1263;
  v1252 = v1263;
  if ( !v1177 )
  {
    if ( (unsigned int)FOsrhInTransition() )
    {
      if ( (a10 & 0x10000) != 0 )
        OSRR::SetFatalOnlyFlag((OSRR *)&v1240);
      goto LABEL_244;
    }
    if ( v1160 )
    {
LABEL_243:
      v1242 = v1577;
      v1243 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                        + 104LL) == 0;
      OSRR::SetCreateNew((OSRR *)&v1240, a10 & 0x400);
      goto LABEL_244;
    }
    v143 = 0;
    CchStToSz(v82, String1, 2084);
    if ( fInIdle && v1162 )
    {
      v144 = 2;
      if ( (int)MsoCchWzLen(String1) <= 2 )
      {
LABEL_229:
        v145 = a10;
        if ( (a10 & 0x80000) != 0 )
        {
          if ( !v1192 || (v146 = (BKORWS *)v1487, v142) )
            v146 = (BKORWS *)v1344;
          v147 = (const wchar_t *)BKORWS::Psh(v146);
          v561 = !FShouldOpenInAppGuard(v147, 0);
          v145 = a10;
          if ( v561 )
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
        XlProtectionMockable::InitOSRR(&v1240, v144, v149, v148);
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
  v150 = v1163;
  if ( v1163 )
  {
    v151 = (const wchar_t *)XLSBOOK::Plxtab((XLSBOOK *)v1163);
    if ( !(unsigned int)FHasPath(v151) )
    {
      v152 = (wchar_t *)XLSBOOK::Plxtab((XLSBOOK *)v150);
      v153 = FileSource::StzFilePath((FileSource *)v1310);
      CchStToSt(v153, v152, 2084);
    }
    if ( !v1285
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
          2 - (v1254 != 0),
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                    + 104LL),
          (struct LoadRecovery *)v150);
      }
    }
  }
  if ( !v1547 )
  {
    CchStToStz(&v1572, v1575, 257);
    v155 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1344);
    MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1345, v155);
  }
  if ( v1162 )
  {
    v1287 = 0;
    v156 = (*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1162 + 80LL))(v1162);
    XlAsyncFileIO::SpOLDocCoauthFromPOLDoc(v1314, v1162);
    if ( v87
      || (v157 = 0, (unsigned __int8)std::shared_ptr<Mso::ActivityScope::IMsoLoggingScope>::operator bool(v1314))
      && (v158 = BKORWS::Psh((BKORWS *)v1314), XlAsyncFileIO::FIsDistributedBlobsFile(v158)) )
    {
      v157 = 1;
      v1173 = 1;
    }
    else
    {
      v1173 = 0;
    }
    v1189 = v157;
    v159 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1381, 0x21C730Du);
    v160 = SXVWGEOM::RwFirst(v159);
    OldocHelper::SetAttrInAttrMask(
      v1162,
      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1232LL) + 32LL) != 0
    ? 0x20000
    : 0,
      0x20000u,
      v160);
    (*(void (__fastcall **)(struct IMsoOLDocument *, struct IMsoPKMClient **))(*(_QWORD *)v1162 + 168LL))(v1162, &v1251);
    v161 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1382, 0x21C730Eu);
    v162 = SXVWGEOM::RwFirst(v161);
    OldocHelper::SetAttrInAttrMask(v1162, v156, 0x20000u, v162);
    if ( v1251 )
      (*(void (__fastcall **)(struct IMsoPKMClient *))(*(_QWORD *)v1251 + 104LL))(v1251);
    if ( (*(int (__fastcall **)(struct IMsoOLDocument *, int *, __int64))(*(_QWORD *)v1162 + 48LL))(v1162, &v1287, 20) >= 0
      && v1287 )
    {
      v114 = -2147467260;
      XlsDiag::LogSetHrCoreTag(-2147467260, 0x17976D7u);
      Mso::TCntPtr<Uxpp::UxppAnnotationsService>::~TCntPtr<Uxpp::UxppAnnotationsService>(v1314);
      goto LABEL_1871;
    }
    Mso::TCntPtr<Uxpp::UxppAnnotationsService>::~TCntPtr<Uxpp::UxppAnnotationsService>(v1314);
  }
  if ( v150 )
  {
    v163 = XLSBOOK::Plxtab((XLSBOOK *)v150);
    CchStToSt(&v1572, (wchar_t *)v163 + 2084, 257);
    v164 = XLSBOOK::Plxtab((XLSBOOK *)v150);
    *((_WORD *)v164 + *((unsigned __int16 *)XLSBOOK::Plxtab((XLSBOOK *)v150) + 2084) + 2085) = 0;
  }
  MaxPathSzPoke::MaxPathSzPoke((MaxPathSzPoke *)v1489, (struct MaxPathHolder *)v1353);
  v165 = 0;
  if ( v1216 )
  {
    v168 = v1176;
  }
  else
  {
    if ( v1162 )
    {
      if ( (unsigned int)IMsoOLDocument::IsInFileSys(v1162) )
        v165 = AugmentationLoop::TranslateDetectLanguagesArrayAnnotationResponse::SzId((AugmentationLoop::TranslateDetectLanguagesArrayAnnotationResponse *)v1489);
      else
        v165 = 0;
    }
    v166 = (wchar_t *)v165;
    v167 = FIsTrue<int>(vgrbitScanload & 2);
    v168 = v1176;
    v169 = sub_1402D97E0(v1162, (struct FileSource *)v1310, v1176 != 0, v167, v166, (struct OSRR *)&v1240);
    v1157 = v169;
    v114 = v169;
    if ( v169 < 0 )
    {
      XlsDiag::LogSetHrCoreTag(v169, 0x1E107807u);
LABEL_1872:
      MaxPathSzPoke::~MaxPathSzPoke((MaxPathSzPoke *)v1489);
      goto LABEL_1871;
    }
    v170 = v1272;
    if ( v1272 )
    {
      v171 = APPCORE::PmemheapMain((APPCORE *)&vapp);
      FileSource::FileSource((FileSource *)v1534, v171);
      v172 = FileSource::HrSetWin32PathSt((FileSource *)v1534, v170);
      if ( v172 < 0 )
        XlsDiag::LogSetHrCoreTag(v172, 0x1E109581u);
      v173 = FIsTrue<int>(vgrbitScanload & 2);
      v174 = sub_1402D97E0(v1162, (struct FileSource *)v1534, v168 != 0, v173, 0, (struct OSRR *)&v1240);
      v1157 = v174;
      v114 = v174;
      if ( v174 < 0 )
      {
        XlsDiag::LogSetHrCoreTag(v174, 0x1E107806u);
        FileSource::~FileSource((FileSource *)v1534);
        goto LABEL_1872;
      }
      FileSource::~FileSource((FileSource *)v1534);
    }
  }
  v1216 = 1;
  MaxPathSzPoke::~MaxPathSzPoke((MaxPathSzPoke *)v1489);
  v175 = PbookFromTitle(v1572, v1573);
  v1202 = v175;
  if ( v175 )
  {
    v176 = BOOK::FFailedToFreeWhileLoading(v175);
    v175 = v1202;
    if ( v176 || !*((_QWORD *)v1202 + 141) )
    {
      if ( !BOOK::FFailedToFreeWhileLoading(v1202) )
        MsoShipAssertTagProc(40981770);
      v175 = 0;
      v1202 = 0;
    }
    if ( v175 )
    {
      if ( (unsigned int)FOsrc() )
      {
        SetLoadForPreviewError(-2147024891);
        v1027 = 24737497;
        v1028 = -2147024891;
        v114 = -2147024891;
        goto LABEL_1874;
      }
      v175 = v1202;
    }
  }
  if ( v1160 && !v175 )
  {
    FixUpFileTitle(&v1572);
    v175 = PbookFromTitle(v1572, v1573);
    v1202 = v175;
  }
  v177 = *(struct SH ***)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
  if ( v177[5] )
  {
    v178 = v177[5];
    if ( (*((_DWORD *)v178 + 221) & 0x200) != 0 )
    {
      v179 = BOOK::Pioldoc(v178);
      v180 = v1162;
      if ( v1162 != v179 )
      {
        MsoShipAssertTagProc(1650811750);
        v180 = v1162;
      }
      if ( !v180 )
        goto LABEL_410;
      HrRecordEvent(v180, 0x40000000u, 0);
      v181 = FeatureGateCollectionBase<ZipItFeatureGates>::Instance();
      v182 = 0;
      if ( (unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(v181 + 424) )
      {
        v185 = v1247;
      }
      else
      {
        v183 = FeatureGateCollectionBase<ZipItFeatureGates>::Instance();
        v184 = Mso::AB::Optimized::ChangeGate::operator bool(v183 + 440);
        v185 = v1247;
        if ( !v184 )
          goto LABEL_306;
        v185 = v1247 | 1;
        v1247 |= 1u;
        v186 = (BKORWS *)XlAsyncFileIO::SpOLDocCoauthFromPOLDoc(v1443, v1162);
        v187 = BKORWS::Psh(v186);
        if ( !XlAsyncFileIO::FIsDistributedBlobsFile(v187) )
          goto LABEL_306;
      }
      v182 = 1;
LABEL_306:
      if ( (v185 & 1) != 0 )
      {
        v1247 = v185 & 0xFFFFFFFE;
        Mso::TCntPtr<Uxpp::UxppAnnotationsService>::~TCntPtr<Uxpp::UxppAnnotationsService>(v1443);
      }
      if ( v182 )
      {
        v1288 = -1;
        if ( (*(int (__fastcall **)(struct IMsoOLDocument *, int *))(*(_QWORD *)v1162 + 200LL))(v1162, &v1288) < 0
          || v1288 <= 0 )
        {
          MsoShipAssertTagProc(504410975);
        }
        if ( v168 )
        {
          MsoShipAssertTagProc(504414753);
          v188 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1383, 0x1E113313u);
          v189 = SXVWGEOM::RwFirst(v188);
          OldocHelper::SetReadOnly(v1162, v189);
        }
        else
        {
          v190 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1384, 0x1E113312u);
          v191 = SXVWGEOM::RwFirst(v190);
          OldocHelper::ClearReadOnly(v1162, v191);
        }
        v192 = v1162;
        v193 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL);
        v194 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1385, 0x1E10B250u);
        v195 = SXVWGEOM::RwFirst(v194);
        LOBYTE(v196) = 33;
        LOBYTE(v197) = 5;
        Mementos::LogObjectLifetimeEvent(v195, 3, v197, v196, v193, v192);
        (*(void (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1162 + 16LL))(v1162);
        if ( !(unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(&qword_144028920) )
        {
          v198 = *(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL);
          v199 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1386, 0x1E113311u);
          v200 = SXVWGEOM::RwFirst(v199);
          BOOK::SetPioldoc(v198, 0, v200);
        }
        v1183 = 0;
      }
      else
      {
        v201 = BOOK::Pioldoc(*(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL));
        v203 = v1162;
        if ( v1162 == v201 )
        {
          LOBYTE(v202) = 1;
          Mso::TRestorer<bool>::TRestorer<bool>(v1513, &XlFileProtocol::s_fInClose, v202);
          v1444 = v1162;
          v204 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1387, 0x236962C5u);
          v205 = SXVWGEOM::RwFirst(v204);
          OlDocFilePath::FReleaseIOLDoc(&v1444, 1, 0, v205);
          v206 = *(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL);
          v207 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1388, 0x236962C4u);
          v208 = SXVWGEOM::RwFirst(v207);
          BOOK::SetPioldoc(v206, 0, v208);
          Mso::TRestorer<bool>::~TRestorer<bool>(v1513);
          v203 = v1162;
        }
        v1183 = FBeginCmdIOLDoc(v203, v168 != 0 ? 4 : 2, 0, &v1237, 0);
      }
      goto LABEL_409;
    }
  }
  if ( !v175 || wProjLoad == 2 )
    goto LABEL_410;
  v561 = v175 == v177[5];
  v1273 = v177[4];
  v209 = !v561;
  v1280 = v177[13];
  if ( v177[13] )
  {
    SH::Pbook(*((SH **)v177[13] + 3));
    v175 = v1202;
  }
  v210 = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)v175 + 205) + 32LL))((__int64)v175 + 1640);
  v211 = 0;
  v212 = 0;
  v213 = BOOK::Pioldoc(v1202);
  if ( v1162 != v213 )
  {
    if ( !v210 )
    {
      v214 = 34146077;
LABEL_335:
      v211 = 1;
      XlsDiag::LogSetHrCoreTag(-2147467260, v214);
      goto LABEL_336;
    }
    if ( !OfficeSharedApiImpl::BusinessBarShowArgs::GetHideCloseButton((OfficeSharedApiImpl::BusinessBarShowArgs *)v1310)
      || (v215 = FileSource::StzFilePath((FileSource *)v1310), (unsigned int)CmpTextHp(v210, v215, 0xFFFFFFFFLL)) )
    {
      v211 = 1;
      XlsDiag::LogSetHrCoreTag(-2147467260, 0x209071Eu);
      v212 = 1;
    }
  }
  if ( !v212 )
  {
    v216 = *((_QWORD *)v1202 + 66);
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
      OkAlert(196753, v1573);
    fCeCanceled = 1;
    v114 = -2147467260;
    XlsDiag::LogSetHrCoreTag(-2147467260, 0x2385704u);
    v1038 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1184);
    v1039 = OpenTelemetry::POpenFileStageModel(v1038);
    v1040 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1461, 0x1F0CB5D3u);
    v1041 = SXVWGEOM::RwFirst(v1040);
    WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v1039, 2214658819LL, v1041);
    goto LABEL_1871;
  }
  if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1232LL) + 80LL) )
  {
    v217 = XLOSRR::FMustUseOsr((XLOSRR *)&v1240);
    if ( (unsigned int)FOsrhBook(v1202) != v217 )
    {
      v1029 = FOsrhBook(v1202);
      OkAlert(589891 - (v1029 != 0), 0);
      v1027 = 24737499;
      goto LABEL_1876;
    }
  }
  if ( (*((_DWORD *)v1202 + 221) & 0x100) != 0
    && *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1836LL) )
  {
    OkAlert(196948, v1573);
    v1030 = 24737500;
    goto LABEL_1878;
  }
  v1289 = 0;
  v218 = HrGroupAction(0, v1202, 9, 0, &v1289);
  if ( v218 < 0 )
  {
    v1171 = v218;
    goto LABEL_1133;
  }
  if ( v1289 )
  {
    v1027 = 24737501;
LABEL_1876:
    v114 = -2147024809;
    v1028 = -2147024809;
LABEL_1874:
    XlsDiag::LogSetHrCoreTag(v1028, v1027);
LABEL_1871:
    v68 = v1163;
LABEL_1861:
    v1018 = v1166;
    goto LABEL_2092;
  }
  if ( !FileSource::FFileExists((FileSource *)v1310) )
  {
    OkAlert(196655, v1573);
    v1031 = -2147319765;
    v1030 = 24737502;
    goto LABEL_1879;
  }
  if ( PcxoFromPbook(v1202) )
  {
    v219 = PcxoFromPbook(v1202);
    if ( (unsigned int)FCxoLocked(v219) )
    {
      if ( (*((_DWORD *)v1202 + 222) & 0x400) == 0 )
        Error(393653);
      v1030 = 24737503;
LABEL_1878:
      v1031 = -2147024809;
LABEL_1879:
      v114 = v1031;
      v1032 = v1031;
      goto LABEL_1880;
    }
  }
  v220 = 2;
  if ( (a3 & 2) == 0 )
  {
    if ( vfPastingHlink )
    {
      v1030 = 24737504;
    }
    else
    {
      if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1232LL)
                     + 32LL) == 2 )
        fCeCanceled = 1;
      if ( (*(_BYTE *)(*((_QWORD *)v1202 + 141) + 3058LL) & 0x18) != 0 )
      {
        v1033 = 1;
      }
      else
      {
        v1034 = FActivatePbook(v1202);
        v1033 = FIsTrue<int>(v1034);
      }
      v1181 = v1033;
      vfLoadAbortedOnActivatedAlreadyOpenedBook = v1033;
      if ( v1033 )
      {
        v1456 = "Unconditionally setting foreground window for already opened book";
        Mso::Diagnostics::SendDiagnosticTrace<>(556414216, 2485, 50, 2, (__int64)&v1456);
        Count = Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection::GetCount(v1202);
        v1036 = WN::Puiframe(*(WN **)(Count + 16));
        v1037 = UIFRAME::HwndFrame(v1036);
        SetForegroundWindow(v1037);
        v1031 = -2147467260;
        v1030 = 37246725;
        goto LABEL_1879;
      }
      v1030 = 24737505;
    }
LABEL_1893:
    v114 = -2146827284;
    goto LABEL_1894;
  }
  if ( UIGLOBALS::UIGLOBALSCONTAINER::m_selection )
  {
    v221 = SH::Pbook(*(SH **)(UIGLOBALS::UIGLOBALSCONTAINER::m_selection + 24LL));
    if ( v221 == v1202
      && (!*(_QWORD *)&UIGLOBALS::UIGLOBALSCONTAINER::m_posi
       || (v222 = *(_QWORD *)(*(_QWORD *)&UIGLOBALS::UIGLOBALSCONTAINER::m_posi + 1568LL)) == 0
       || *(_QWORD *)(v222 + 256))
      && !(unsigned int)FOsrhBook(v1202) )
    {
      inited = HrInitRevert((struct REVARG *)v1570, 336, &v1274);
      v224 = v1175;
      if ( inited >= 0 )
        v224 = 1;
      v1175 = v224;
    }
  }
  Marquee::FreeAllMarqueeTag(0, 20789206, v220);
  DestroyWorkgroup();
  v225 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1389, 0x237630DCu);
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
  LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v228 + 96), v1202, v226);
  if ( Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection::GetCount(*(Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 32LL))
    && *(_QWORD *)(Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection::GetCount(*(Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 32LL))
                 + 16) )
  {
    v230 = (struct WNX *)Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection::GetCount(*(Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 32LL));
    v231 = Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection::GetCount(*(Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 32LL));
    AttachWnxToWn(*(struct WN **)(v231 + 16), v230);
  }
  if ( (unsigned int)FLogRevs(v1202) && (*((_BYTE *)v1202 + 884) & 0x20) == 0 )
    FFreeUsrInfo(v1202, *(_DWORD *)(*((_QWORD *)v1202 + 125) + 16LL), 0, 0, 0);
  HrRecordEvent(v1162, 0x40000000u, 0);
  if ( v209 )
  {
    if ( v1280 )
    {
      v232 = (SH *)*((_QWORD *)v1280 + 3);
      if ( v232 )
      {
        v233 = SH::Pbook(v232);
        if ( v233 == v1202 )
          v209 = 0;
      }
    }
  }
  sub_1416A3CB4();
  v234 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
  if ( *(_QWORD *)(v234 + 992) )
  {
    v235 = *(_QWORD *)(v234 + 992);
    if ( *(_QWORD *)(v235 + 48) )
    {
      v236 = SH::Pbook(*(SH **)(*(_QWORD *)(v235 + 48) + 24LL));
      if ( v236 == v1202 )
        FreeCfr();
    }
  }
  v114 = XlReopenBook::HrCloseBookForReopen(
           &v1202,
           (struct REVERT **)((unsigned __int64)&v1274 & -(__int64)(v1175 != 0)));
  if ( v114 < 0 )
  {
    v1027 = 34174687;
    v1028 = v114;
    goto LABEL_1874;
  }
  v1306 = 0;
  if ( v209 )
  {
    v237 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1390, 0x237630DBu);
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
    LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v240 + 96), v1273, v238);
    v242 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1391, 0x237630DAu);
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
    VIEWCONTEXTDATA::CurWnx(*(VIEWCONTEXTDATA **)(v245 + 16), v1280, v243);
  }
  v168 = v1176;
  v1224 = 2;
  if ( v1176 || (v247 = 2, v1178) )
    v247 = 4;
  v1183 = FBeginCmdIOLDoc(v1162, v247, 0, &v1237, 0);
  if ( (*(unsigned int (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1162 + 208LL))(v1162) )
    v1224 = 0;
  if ( v168 )
  {
    operator|=(&v1224, 1);
  }
  else if ( (a10 & 0x200) != 0 )
  {
    operator|=(&v1224, 8);
  }
  if ( (unsigned int)FFinderFile(v82) )
    operator|=(&v1224, 32);
  if ( (a10 & 0x20000) != 0 )
    operator|=(&v1224, 256);
  LODWORD(v1130) = v1224;
  XlsDiag::SendTraceTag(41039178, 187, 100, L"FFileLoadEx: OlDocSetupFlags oldsf = 0x%x", v1130);
  v248 = TLSW::PesExpressionService(*(TLSW **)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL));
  v249 = ExpressionService::Pwbkcoll(v248);
  RevisionLatencyOutlierTracker::RevisionLatencyOutlierTracker(v1533, v249, 16);
  operator|=(&v1224, 4096);
  v250 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1544);
  v251 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1392, 0x236962C3u);
  v252 = SXVWGEOM::RwFirst(v251);
  v114 = OlDocFilePath::HrSetupAndRetrievePathTitle(
           v250,
           (struct FileSource *)v1310,
           &v1162,
           v82,
           &v1237,
           (enum OlDocSetupFlags *)&v1224,
           0,
           v252,
           0,
           0);
  RevisionLatencyOutlierTracker::~RevisionLatencyOutlierTracker((RevisionLatencyOutlierTracker *)v1533);
  if ( v114 < 0 )
  {
    if ( v1175 && v1274 )
      FreeRevert(v1274);
    v1030 = 24737506;
LABEL_1894:
    v1032 = v114;
LABEL_1880:
    XlsDiag::LogSetHrCoreTag(v1032, v1030);
LABEL_1881:
    v68 = v1163;
LABEL_1882:
    v1018 = v1166;
LABEL_2092:
    if ( v1162 )
    {
      LOBYTE(v259) = v1192 != 0;
      sub_1416B1620(v1162, v1310, v259);
      (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v1162 + 56LL))(
        v1162,
        0xFFFFFFFFLL,
        7);
      if ( v1183 )
      {
        HrRecordEvent(v1162, 0x40000000u, 0);
        if ( v1018 && *v1018 )
        {
          v1114 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1371, 0x236962C2u);
          v1115 = SXVWGEOM::RwFirst(v1114);
          v1116 = 0;
          goto LABEL_2097;
        }
      }
      else
      {
        v1117 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1372, 0x236962C1u);
        v1115 = SXVWGEOM::RwFirst(v1117);
        v1116 = 1;
LABEL_2097:
        OlDocFilePath::FReleaseIOLDoc(v1018, v1116, 1, v1115);
      }
    }
LABEL_1935:
    v82 = v1165;
LABEL_2100:
    if ( v1547 )
    {
      if ( v1304 != v1162 && v1304 )
      {
        (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v1304 + 56LL))(
          v1304,
          0xFFFFFFFFLL,
          7);
        if ( v1194 )
          HrRecordEvent(v1304, 0x40000000u, 0);
        v1118 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1373, 0x236962C0u);
        v1119 = SXVWGEOM::RwFirst(v1118);
        OlDocFilePath::FReleaseIOLDoc(&v1304, 1, 1, v1119);
      }
      v1120 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1467);
      CchStToSt(v1120, v82, v1229);
    }
    XslClear((struct XSL *)&v1546);
    vpoldocument = v1354;
    if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL) + 8LL)
        & 1) == 0 )
    {
      FRemoveLoadAction((struct LoadRecovery *)v68, 0);
      if ( v68 )
      {
        LoadRecovery::Destroy((LoadRecovery *)v68);
        FreeHpst(v68);
        v68 = 0;
        v1238 = 0;
      }
    }
    ResetLoadRecovery();
    v1158 = 0;
    if ( !XlFileProtocolManager::FForceCobaltReopenHr(v114) )
    {
      v114 = -2146827284;
      XlsDiag::LogSetHrCoreTag(-2146827284, 0x2385706u);
    }
    v1155 = v1339;
    v1153 = v1259;
    v1152 = v1180;
    v1151 = v114;
    v1149 = v1186;
    v1148 = v1307;
    v1146 = v1275;
    v1145 = v1162;
    v1144 = v1164;
    v1143 = v1256;
    v1142 = v1251;
    v1141 = v1200 != 0;
    v1139 = v1225;
    v1137 = v1305;
    v1135 = (struct LoadRecovery *)v68;
LABEL_2113:
    v1075 = HrFileCompleteLoadEx(
              v82,
              hObject,
              v1158,
              v1187,
              lp,
              v1181,
              v1170,
              v1135,
              v1137,
              v1139,
              v1141,
              v1142,
              v1143,
              v1144,
              v1145,
              v1146,
              v1148,
              v1149,
              v1151,
              (const struct MaxPathHolder *)v1345,
              v1152,
              v1153,
              (struct OsfOpenScope *)v1490,
              (const struct XLOSRR *)&v1240,
              v1155);
LABEL_1992:
    v606 = v1075;
    goto LABEL_2136;
  }
  v253 = FeatureGateCollectionBase<LoadSaveFeatureGates>::Instance();
  if ( (unsigned __int8)Mso::AB::Optimized::FeatureGate::operator bool(v253 + 8) )
  {
    v257 = (const struct OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1544);
    v258 = FileSource::HrSetOlDocFilePath((FileSource *)v1310, v257);
    v114 = v258;
    if ( v258 < 0 )
    {
      XlsDiag::LogSetHrCoreTag(v258, 0x27D405Fu);
      goto LABEL_1881;
    }
    v1157 = FileSource::HrSetPoldoc((FileSource *)v1310, v1162, v1279, v1218);
    v114 = v1157;
    if ( v1157 >= 0 )
      goto LABEL_408;
    v256 = 41969047;
    goto LABEL_407;
  }
  v254 = std::_Optional_construct_base<OlDocFilePath>::operator*(v1544);
  Target = (const wchar_t *)OfficeExtension::ServerRuntime::RichApiMessageEntry::GetTarget(v254);
  v1157 = FileSource::HrSetWin32PathSt((FileSource *)v1310, Target);
  v114 = v1157;
  if ( v1157 < 0 )
  {
    v256 = 41185885;
LABEL_407:
    XlsDiag::LogSetHrCoreTag(v114, v256);
    if ( v114 < 0 )
      goto LABEL_1881;
  }
LABEL_408:
  v260 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1544);
  v261 = OlDocFilePath::StzTitle(v260);
  CchStToStz(v261, &v1572, 257);
  v142 = v1252;
LABEL_409:
  v150 = v1163;
LABEL_410:
  v262 = NtCurrentTeb()->ThreadLocalStoragePointer;
  vhpstErrPath = v82;
  v263 = *(_QWORD *)(*(_QWORD *)v262 + 304LL);
  *(_DWORD *)(v263 + 2024) = 1;
  *(_DWORD *)(v263 + 2028) = 38879640;
  v1158 = 0;
  v264 = 0;
  v1244 = 0;
  v1220 = 0;
  errDeferred = 0;
  v265 = NtCurrentTeb()->ThreadLocalStoragePointer;
  v1249 = (void *)-1LL;
  if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v265 + 304LL) + 872LL) + 104LL) == 2
    && !(unsigned int)FMetroFileEx((struct FileSource *)v1310, 0)
    && !v1160 )
  {
    v1172 = 0;
    if ( MsoDwRegGetDw((const struct _msoreg *)&vmsoridExcelExtractDataMode) == 1 )
      v1190 |= 1u;
    if ( !v1185 && MsoDwRegGetDw((const struct _msoreg *)&vmsoridExcelExtractDataFormulas) == 1 )
      v1190 |= 2u;
    if ( (v1190 & 1) == 0 )
    {
      v264 = FileSource::HpstgiFileOpen(
               (FileSource *)v1310,
               &v1572,
               (unsigned int)(v168 != 0) + 1056,
               0,
               0,
               0,
               0,
               0,
               v1218);
      v1220 = v264;
      v266 = 0;
      if ( !v1162 )
        goto LABEL_422;
      errDeferred = _IMsoOLDocument_GetDeferredError(v1162);
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
        v1168 = 1;
        v264 = FileSource::HpstgiFileOpen((FileSource *)v1310, &v1572, 0x421u, 0, 0, 0, 0, 0, v1218);
        v1220 = v264;
      }
    }
    if ( (unsigned int)FErrPstgi(v264) )
    {
LABEL_437:
      v1190 |= 1u;
    }
    else
    {
      v1172 = 0;
      v267 = SXVWGEOM::RwFirst(v264);
      STGI::SetSlf(v264, v267 & 0xFFFFFFDF);
      if ( v168 || (v268 = 1152, v1168) )
        v268 = 1153;
      v269 = v268 | SXVWGEOM::RwFirst(v264) & 0x800;
      v270 = STGI::Lpstg(v264);
      v271 = ScStgIdsStreamOpen(v270, v269, 0, v1571, &v1172, -1161035344, 9);
      v272 = v271 == 0;
      if ( !v271 && !(unsigned int)FValidDRDocStream(v1172) )
      {
        StreamClose(v1172);
        v1172 = 0;
        v272 = 0;
      }
      if ( !v272 )
      {
        StgiFileClose(v264);
        v264 = 0;
        v1220 = 0;
        goto LABEL_437;
      }
    }
    if ( (v1190 & 1) == 0 )
      goto LABEL_439;
LABEL_1015:
    v554 = FileSource::StzFileName((FileSource *)v1310);
    if ( (unsigned int)FFinderFile(v554) )
    {
      v168 = 1;
      v1176 = 1;
      v1219 = 1;
      vfPretendNotStg = 1;
    }
    goto LABEL_1038;
  }
  if ( wProjLoad != 2 )
  {
    if ( a7 == 1024 )
    {
      v371 = v1169;
      goto LABEL_658;
    }
    v1217 = 0;
    v278 = 0;
    v279 = APPCORE::PmemheapMain((APPCORE *)&vapp);
    MaxPathHolder::MaxPathHolder((MaxPathHolder *)v1318, v279, 259, 0);
    if ( (unsigned int)FOsrcHostedByExcel() )
    {
      MaxPathStzPoke::MaxPathStzPoke((MaxPathStzPoke *)v1488, (struct MaxPathHolder *)v1318);
      v280 = MaxPathStzPoke::CchStzBufferSize((MaxPathStzPoke *)v1488);
      v281 = (wchar_t *)SlicerViewImpl::PSlicerView((SlicerViewImpl *)v1488);
      CnvTempFile = FileSource::HrGetCnvTempFile((FileSource *)v1310, v281, v280, &v1234, &v1192);
      v278 = CnvTempFile;
      if ( CnvTempFile < 0 )
      {
        v114 = CnvTempFile;
        XlsDiag::LogSetHrCoreTag(CnvTempFile, 0x17976E3u);
        MaxPathStzPoke::~MaxPathStzPoke((MaxPathStzPoke *)v1488);
LABEL_465:
        MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1318);
        goto LABEL_466;
      }
      v283 = (MaxPathStzPoke *)v1488;
    }
    else
    {
      if ( v1160 || v1177 )
      {
LABEL_473:
        if ( v1192 )
        {
          if ( v1162 )
          {
            v142 = IMsoOLDocument::IsInFileSys(v1162) != 0;
            v1252 = v142;
            v1263 = v142;
          }
          v286 = v1176;
          if ( v1234 == 68 )
            v286 = 1;
          v1176 = v286;
          v1219 = v286;
          v287 = FileSource::SzFilePath((FileSource *)v1310);
          MaxPathHolder::CchCopyFromSz((MaxPathHolder *)v1487, v287);
          v288 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1318);
          v289 = FileSource::HrSetWin32PathSt((FileSource *)v1310, v288);
          v1157 = v289;
          v114 = v289;
          if ( v289 < 0 )
          {
            XlsDiag::LogSetHrCoreTag(v289, 0x274139Du);
            goto LABEL_465;
          }
          v290 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL);
          v1254 = 0;
          *(_DWORD *)(v290 + 104) = 0;
          a10 &= ~8u;
          FRemoveLoadAction((struct LoadRecovery *)v150, 0);
          if ( v150 )
          {
            LoadRecovery::Destroy((LoadRecovery *)v150);
            FreeHpst(v150);
            v1163 = 0;
            v1238 = 0;
          }
        }
        v291 = FileSource::StzFileName((FileSource *)v1310);
        if ( (unsigned int)FFinderFile(v291) )
        {
          v1190 |= 1u;
          v1174 = 1;
          v1172 = 0;
          MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1318);
          goto LABEL_1014;
        }
        if ( v1160 )
        {
          if ( !v1173 )
          {
            v293 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1184);
            v294 = (LXBASE *)OpenTelemetry::POpenFileStageModel(v293);
            v295 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1393, 0x1F0CB5D1u);
            SXVWGEOM::RwFirst(v295);
            WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v294);
            v296 = PstgiFromErr(1u);
            v297 = v1192;
            v264 = v296;
            v1220 = v296;
            v298 = v1241;
            v1199 = 5;
            if ( v1192 )
              v298 = v1234;
            v1241 = v298;
            v1469 = 0;
            memset_0(&v1470, 0, 0x58u);
            v1471 = 257;
            v1482 = 0;
            v1483 = 0;
            v1484 = 0;
            v1485 = 0;
            v1470 = &v1572;
            if ( !v297 || (v299 = (BKORWS *)v1487, v142) )
              v299 = (BKORWS *)v1344;
            v300 = BKORWS::Psh(v299);
            v68 = v1163;
            v1472 = v300;
            v1473 = a5;
            v1474 = v1249;
            v1475 = v1162;
            v1469 = &v1240;
            v1485 = v1163;
            MaxPathStzPoke::MaxPathStzPoke((MaxPathStzPoke *)v1507, (struct MaxPathHolder *)v1318);
            v301 = 0;
            if ( v1192 )
              v301 = SlicerViewImpl::PSlicerView((SlicerViewImpl *)v1507);
            v1480 = v301;
            MaxPathStzPoke::~MaxPathStzPoke((MaxPathStzPoke *)v1507);
            v1479 = v1192;
            v1476 = v1185;
            v1477 = v1190 & 2;
            v1478 = v1215 != 1;
            v1481 = v1275;
            v1484 = v1230;
            if ( AppGuard::Config::IsEnabled(v302) )
              v1482 = (a10 & 0x80000) != 0;
            v1483 = v1221 == 1;
            v303 = HrLoadInSecureReader((const struct XLOSRLA *)&v1469, v1218);
            v304 = NtCurrentTeb()->ThreadLocalStoragePointer;
            v1182 = v303;
            v1158 = v303 >= 0;
            v1249 = (void *)-1LL;
            v1228 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v304 + 304LL) + 2924LL);
            if ( v303 >= 0 )
              RenumberWind(*(struct SH **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                         + 32LL));
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1225;
            v1156 = 0;
            v114 = v1182;
            v1157 = v1182;
            if ( v1182 < 0 )
            {
              XlsDiag::LogSetHrCoreTag(v1182, 0x1797700u);
              if ( v1182 < 0 )
              {
                v305 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1184);
                v306 = OpenTelemetry::POpenFileStageModel(v305);
                v307 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1394, 0x1F0CB5D0u);
                v308 = SXVWGEOM::RwFirst(v307);
                WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v306, (unsigned int)v1182, v308);
              }
            }
            MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1318);
            goto LABEL_910;
          }
          v292 = BKORWS::Psh((BKORWS *)&v1184);
          if ( (int)XlFileProtocolManager::HrRequestCobaltReopen(v1162, v1205, -1662189471, v292) < 0 )
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
                 (struct FileSource *)v1310,
                 v311,
                 0,
                 v310,
                 &v1253,
                 v309 == 0,
                 &v1245,
                 &v1217);
        if ( v1217 )
        {
          v313 = 579396827;
          v314 = -2147023673;
LABEL_506:
          XlsDiag::LogSetHrCoreTag(v314, v313);
LABEL_507:
          v315 = (MaxPathHolder *)v1318;
LABEL_508:
          MaxPathHolder::~MaxPathHolder(v315);
          v68 = v1163;
          goto LABEL_815;
        }
        v316 = FeatureGateCollectionBase<LoadSaveFeatureGates>::Instance();
        if ( (unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(v316 + 488) )
        {
          v317 = (CorruptionMetaData *)std::_Optional_construct_base<CorruptionMetaData>::operator*(v1543);
          CorruptionMetaData::SetFEncrypted(v317, v1245 != 0);
          v318 = (CorruptionMetaData *)std::_Optional_construct_base<CorruptionMetaData>::operator*(v1543);
          v319 = sub_1402DFA10(v1544);
          CorruptionMetaData::SetFDrmProtected(v318, v319);
        }
        if ( v1272 && !v312 )
        {
          MsoShipAssertTagProc(504410774);
          v313 = 504410773;
          v314 = -2147467260;
          goto LABEL_506;
        }
        if ( v1192 && (v1253 || !v312) )
        {
          FileSource::HrDeleteTemp((FileSource *)v1310);
          v114 = -2146827284;
          v320 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          *(_DWORD *)(v320 + 2024) = 0;
          *(_DWORD *)(v320 + 2028) = 0;
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1225;
          XlsDiag::LogSetHrCoreTag(-2146827284, 0x1797701u);
          MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1318);
          v68 = v1163;
          goto LABEL_518;
        }
        v68 = v1163;
        if ( v1253 && !LoadRecovery::FRepairPkg((LoadRecovery *)v1163) )
        {
          LoadRecovery::SetRepairPkg((LoadRecovery *)v68);
          v321 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          *(_DWORD *)(v321 + 2024) = 0;
          *(_DWORD *)(v321 + 2028) = 0;
          v114 = -2146827284;
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1225;
          XlsDiag::LogSetHrCoreTag(-2146827284, 0x1797702u);
          MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1318);
LABEL_467:
          v277 = v1165;
          goto LABEL_1664;
        }
        v322 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1184);
        v323 = (LXBASE *)OpenTelemetry::POpenFileStageModel(v322);
        v324 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1395, 0x1F0CB5CFu);
        SXVWGEOM::RwFirst(v324);
        WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v323);
        if ( !v312 )
        {
          MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1318);
          goto LABEL_524;
        }
        v264 = PstgiFromErr(7u);
        v1220 = v264;
        if ( v1177 )
        {
          if ( !(unsigned int)FOsrc() )
          {
            v329 = FileSource::StzFileName((FileSource *)v1310);
            if ( !(unsigned int)sub_14240EB30(v329) )
            {
              SetLoadForPreviewError(-2147467259);
              XlsDiag::LogSetHrCoreTag(-2147467260, 0x1797703u);
              v330 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1184);
              v331 = OpenTelemetry::POpenFileStageModel(v330);
              v332 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1465, 0x1F0CB5CEu);
              v333 = SXVWGEOM::RwFirst(v332);
              WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v331, 2214658820LL, v333);
LABEL_543:
              MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1318);
              goto LABEL_815;
            }
          }
        }
        std::optional<DataLossProtection::NotifyRaiiHintsForPrePostEvents>::optional<DataLossProtection::NotifyRaiiHintsForPrePostEvents>(v1341);
        v334 = v1176;
        if ( !v1176 && !FileSource::FCloud((FileSource *)v1310) )
        {
          v335 = APPCORE::PmemheapMain((APPCORE *)&vapp);
          MaxPathHolder::MaxPathHolder((MaxPathHolder *)v1514, v335, 259, 0);
          if ( IsWin32AppRunningInWdag() )
            v336 = (wchar_t *)FileSource::StzFileName((FileSource *)v1310);
          else
            v336 = v1165;
          MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1514, v336);
          v337 = *(const wchar_t **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 784LL);
          v338 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1514);
          v278 = HrWriteOwnerFile(v1162, v338, v337, &v1249);
          v339 = BKORWS::Psh((BKORWS *)v1514);
          v340 = PbookFromPioldoc(v1162);
          DataLossProtectionHelper::spCreateCustomInfoContext(v1348, v340, v339);
          v1445 = BKORWS::Psh((BKORWS *)v1348);
          v1329 = 5;
          v1328 = 6;
          v1446 = APPCORE::PmemheapMain((APPCORE *)&vapp);
          std::optional<DataLossProtection::NotifyRaiiHintsForPrePostEvents>::emplace<IMemHeap *,IMsoOLDocument * &,enum Mso::Dlp::Event,enum Mso::Dlp::Event,DataLossProtection::XLSInfoContext *>(
            (unsigned int)v1341,
            (unsigned int)&v1446,
            (unsigned int)&v1162,
            (unsigned int)&v1329,
            (__int64)&v1328,
            (__int64)&v1445);
          Mso::TCntPtr<DataLossProtection::XLSInfoContext>::~TCntPtr<DataLossProtection::XLSInfoContext>(v1348);
          MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1514);
        }
        if ( !(unsigned __int8)std::operator==<DataLossProtection::NotifyRaiiHintsForPrePostEvents>(v1341) )
        {
          v341 = sub_140451950(v1528, v1341, &v1182);
          sub_14062191C(v1522, v341);
          sub_14062192C(v1522);
        }
        if ( v278 == -2147024864 )
        {
          v264 = PstgiFromErr(2u);
          v1220 = v264;
LABEL_618:
          if ( (unsigned int)FErrPstgi(v264) )
          {
            v368 = (unsigned __int16)PstgiFromErr((unsigned __int16)v264);
            v369 = v1227;
            v370 = v368;
            if ( v368 == 7 )
            {
              v371 = v1169;
              if ( v1227 == -2147024891 )
                v371 = 1;
              v1169 = v371;
            }
            else
            {
              v371 = v1169;
            }
            v68 = v1163;
            if ( v368 != 7 && v368 != 2 && v1254 && v1163 && LoadRecovery::FRepairPkg((LoadRecovery *)v1163) )
            {
              v1269 = 1;
              LoadRecovery::SetRepairState((LoadRecovery *)v68, -2146827284);
              if ( v370 == 1 && (unsigned int)(v369 + 2134241024) > 1 )
              {
                if ( v369 >= 0 )
                  v369 = -2146827284;
                XlsDiag::LogSetHrCoreTag(v369, 0x1797706u);
                std::_Optional_destruct_base<DataLossProtection::NotifyRaiiHintsForPrePostEvents,0>::reset(v1341);
                MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1318);
                goto LABEL_817;
              }
              if ( v369 >= 0 )
                v369 = -2147467260;
              v372 = 24737543;
              v373 = v369;
              goto LABEL_642;
            }
            if ( v370 == 1 )
            {
              if ( v369 == -2134195936
                && (unsigned int)Mso::Details::ConstexprFunctorBase<Mso::IFunctor<bool,FeaturePropertyValue const &,FeaturePropertyValue const &>>::Release(&vapp) )
              {
                v1182 = v1227;
                ErrorAlert(459071, v1573);
                v373 = v1182;
                if ( v1182 >= 0 )
                {
LABEL_643:
                  std::_Optional_destruct_base<DataLossProtection::NotifyRaiiHintsForPrePostEvents,0>::reset(v1341);
                  goto LABEL_543;
                }
                v372 = 24737544;
LABEL_642:
                XlsDiag::LogSetHrCoreTag(v373, v372);
                goto LABEL_643;
              }
              v114 = -2146827284;
              v1157 = -2146827284;
              XlsDiag::LogSetHrCoreTag(-2146827284, 0x230E1E1u);
              std::_Optional_destruct_base<DataLossProtection::NotifyRaiiHintsForPrePostEvents,0>::reset(v1341);
              MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1318);
LABEL_645:
              v374 = APPCORE::PlocaleinfoUSEN((APPCORE *)&vapp);
              if ( (unsigned int)FMetroFileExt((const struct FileSource *)v1310, v374, 0, 0) )
              {
                v68 = v1163;
                if ( v1163 )
                {
                  if ( LoadRecovery::FRepairPkg((LoadRecovery *)v1163)
                    || (unsigned __int16)PstgiFromErr((unsigned __int16)v264) == 7 )
                  {
                    OkAlert(v371 != 0 ? 262202 : 458868, v1573);
                    XlsDiag::LogSetHrCoreTag(v371 != 0 ? -2147024891 : -2146827284, 0x230E200u);
                    if ( !v371 )
                    {
                      v456 = (CorruptionMetaData *)std::_Optional_construct_base<CorruptionMetaData>::operator*(v1543);
                      CorruptionMetaData::MarkAsCorrupt(v456);
                    }
                    if ( v1177 )
                      SetLoadForPreviewError(v371 != 0 ? -2147024891 : -2042494972);
                    goto LABEL_815;
                  }
                  v1253 = 1;
                  LoadRecovery::SetRepairPkg((LoadRecovery *)v68);
                }
LABEL_817:
                v458 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                *(_DWORD *)(v458 + 2024) = 0;
                *(_DWORD *)(v458 + 2028) = 0;
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1225;
                v1156 = 0;
                if ( (unsigned int)FErrPstgi(v264) && v1249 != (void *)-1LL )
                {
                  CloseSentinelFile(v1249);
                  v1249 = (void *)-1LL;
                }
                v114 = -2146827284;
                XlsDiag::LogSetHrCoreTag(-2146827284, 0x230E201u);
                goto LABEL_821;
              }
LABEL_524:
              v168 = v1176;
              if ( a7 == 1024 )
                goto LABEL_839;
              v325 = 1024;
              v326 = 1024;
              if ( v1176 )
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
              if ( v1177 )
                v326 = v327 | 0x1000000;
              v264 = FileSource::HpstgiFileOpen((FileSource *)v1310, &v1572, v326, 0, &v1248, 0, 0, 0, v1218);
              v1220 = v264;
              v1179 = 1;
              if ( !v1177 || !(unsigned int)FErrPstgi(v264) || (unsigned int)FOsrc() && !MsoFDrmErrorCode(v1248) )
              {
                if ( (unsigned int)FErrPstgi(v264)
                  && (unsigned __int16)PstgiFromErr((unsigned __int16)v264) != 4
                  && !*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                            + 872LL)
                                + 104LL)
                  && v1254
                  && (v1248 == -2147286775 || v1248 == -2147287010) )
                {
                  v1236 = 1;
                }
LABEL_839:
                if ( a7 == 1024
                  || (unsigned int)FErrPstgi(v264) && (unsigned __int16)PstgiFromErr((unsigned __int16)v264) == 4 )
                {
                  goto LABEL_1015;
                }
                v1172 = 0;
                if ( (unsigned int)FErrPstgi(v264) )
                {
                  v467 = 0;
                  if ( v1162 )
                  {
                    errDeferred = _IMsoOLDocument_GetDeferredError(v1162);
                    if ( errDeferred )
                      goto LABEL_853;
                    v467 = 0;
                  }
                  if ( !v168 )
                  {
                    if ( (unsigned int)FErrPstgi(v264) )
                      v467 = (unsigned __int16)PstgiFromErr((unsigned __int16)v264);
                    else
                      v467 = 0;
                  }
                  errDeferred = v467;
                  goto LABEL_852;
                }
                v465 = ((v168 != 0) + 1024) | SXVWGEOM::RwFirst(v264) & 0x800;
                v466 = STGI::Lpstg(v264);
                ScStgIdsStreamOpen(v466, v465, 0, v1571, &v1172, -1161035344, 9);
                v467 = errDeferred;
LABEL_852:
                if ( !v467 )
                  goto LABEL_439;
LABEL_853:
                v1255 = -2147467259;
LABEL_1005:
                v1236 = 0;
                v1168 = 1;
                v550 = v1162
                    && ((*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1162 + 224LL))(v1162) & 1) != 0
                    && errDeferred == 2;
                v551 = FileSource::HpstgiFileOpen((FileSource *)v1310, &v1572, 0x401u, 0, &v1255, 0, 0, v550, v1218);
                v114 = v1255;
                v264 = v551;
                v1220 = v551;
                v1157 = v1255;
                if ( !(unsigned int)FErrPstgi(v551) )
                {
                  v1174 = 0;
                  v552 = SXVWGEOM::RwFirst(v264) & 0x800 | 0x401;
                  v553 = STGI::Lpstg(v264);
                  ScStgIdsStreamOpen(v553, v552, 0, v1571, &v1172, -1161035344, 9);
                  v168 = v1176;
                  goto LABEL_439;
                }
                if ( (unsigned __int16)PstgiFromErr((unsigned __int16)v264) != 4 )
                {
                  if ( v1255 == -2147287010 || v1255 == -2147286775 )
                  {
                    OkAlert(262188, 0);
                  }
                  else if ( v1255 != -2147217391 )
                  {
                    MsoSetLastWAlertHRTag(v1255, 0x376C7370u);
                    MsoShipAssertTagProc(892367981);
                    OkAlert(196657, v1573);
                    MsoResetLastWAlertHR();
                  }
LABEL_1022:
                  v168 = v1176;
                  goto LABEL_439;
                }
                v1174 = 1;
LABEL_1014:
                v168 = v1176;
                goto LABEL_1015;
              }
              if ( MsoFDrmErrorCode(v1248) )
              {
                v114 = -2042494975;
              }
              else if ( (unsigned __int16)PstgiFromErr((unsigned __int16)v264) == 4 )
              {
                v114 = -2042490872;
              }
              else if ( v1248 == -2147286775
                     || (unsigned int)(v1248 + 2147286780) <= 1
                     || v1248 == -2147286960
                     || (v114 = -2147467259, v1248 == -2147287010) )
              {
                v114 = -2042494972;
              }
              SetLoadForPreviewError(v114);
              XlsDiag::LogSetHrCoreTag(v114, 0x179770Eu);
              v459 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1184);
              v460 = OpenTelemetry::POpenFileStageModel(v459);
              v461 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1403, 0x1F0CB5C9u);
              v462 = SXVWGEOM::RwFirst(v461);
              WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v460, (unsigned int)v114, v462);
              v68 = v1163;
              v463 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
              *(_DWORD *)(v463 + 2024) = 0;
              *(_DWORD *)(v463 + 2028) = 0;
              *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1225;
              LOBYTE(v264) = 0;
              if ( v68 )
                goto LABEL_830;
              v277 = v1165;
              goto LABEL_1664;
            }
          }
          else
          {
            v371 = v1169;
          }
          if ( !(unsigned int)FErrPstgi(v264) )
          {
            if ( v1245 )
            {
              if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1836LL) )
              {
                v375 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1544);
                v376 = OlDocFilePath::PClpDocument(v375);
                EncryptedStorage = STGI::GetEncryptedStorage(v264);
                if ( !(unsigned int)FDrmQueryRightsStg(EncryptedStorage, 2u, v376) )
                {
                  StgiFileClose(v264);
                  HandleLockError(327752);
                  v347 = 36757986;
                  v378 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                  *(_DWORD *)(v378 + 2024) = 0;
                  *(_DWORD *)(v378 + 2028) = 0;
                  goto LABEL_589;
                }
              }
            }
          }
          std::_Optional_destruct_base<DataLossProtection::NotifyRaiiHintsForPrePostEvents,0>::reset(v1341);
          MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1318);
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
            if ( v1162 )
            {
              DeferredError = _IMsoOLDocument_GetDeferredError(v1162);
              errDeferred = DeferredError;
              if ( DeferredError )
                goto LABEL_673;
              DeferredError = 0;
            }
            if ( !v1176 )
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
            v68 = v1163;
            goto LABEL_734;
          }
LABEL_673:
          if ( v1249 != (void *)-1LL )
          {
            CloseSentinelFile(v1249);
            DeferredError = errDeferred;
            v1249 = (void *)-1LL;
          }
          if ( v1192 )
          {
            v381 = v1215;
          }
          else
          {
            v380 = FIsShareErr(DeferredError);
            v381 = v1215;
            if ( v380
              && v1215 == 1
              && (int)HrGetRealMetroFileType((struct FileSource *)v1310, (enum FILETYPE *)&v1290) >= 0
              && (v1290 == 54 || v1290 == 17 ? (v382 = 1) : (v382 = 0), v382) )
            {
              DeferredError = 0;
              errDeferred = 0;
            }
            else
            {
              DeferredError = errDeferred;
            }
          }
          if ( (unsigned int)FIsShareErr(DeferredError) && v381 == 1 )
          {
            v383 = APPCORE::PmemheapMain((APPCORE *)&vapp);
            MaxPathHolder::MaxPathHolder((MaxPathHolder *)v1496, v383, 259, 0);
            ENV::ENV((ENV *)&v1559);
            MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1496, v1165);
            FileTemp = FileSource::HrGetFileTemp(v1310, 5);
            v1157 = FileTemp;
            if ( FileTemp < 0 )
            {
              XlsDiag::LogSetHrCoreTag(FileTemp, 0x2806598u);
              XlsDiag::LogSetHrCoreTag(-2146827284, 0x2806599u);
              v315 = (MaxPathHolder *)v1496;
              goto LABEL_508;
            }
            v385 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
            v1447 = *(_QWORD *)(v385 + 336);
            *(_QWORD *)(v385 + 336) = &v1559;
            v1560 = 36737603;
            if ( !setjmp(v1561) )
            {
              v386 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1496);
              if ( (int)HrReadOwnerFile(v386, v1581, 257) < 0 )
              {
                v388 = !v1192 && FileHost::FIsEncryptedMetroFile((FileHost *)v1310, v387);
                v389 = FileSource::StzFilePath((FileSource *)v1310);
                v390 = 0;
              }
              else
              {
                v388 = !v1192 && FileHost::FIsEncryptedMetroFile((FileHost *)v1310, v387);
                v389 = FileSource::StzFilePath((FileSource *)v1310);
                v390 = v1581;
              }
              HrDeferredSRO(&v1572, v390, v389, 0, v388);
            }
            v391 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
            *(_QWORD *)(v391 + 336) = v1447;
            if ( (_QWORD)xmmword_143FE0F90 )
            {
              LOBYTE(v391) = v1188;
              v392 = sub_141224EE0(v1162, v391, &v1200);
              v1215 = v392;
              if ( v392 < 0 )
              {
                errDeferred = 0;
                v1170 = 1;
                XlsDiag::LogSetHrCoreTag(v392, 0x1797709u);
                v393 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1184);
                v394 = OpenTelemetry::POpenFileStageModel(v393);
                v395 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1397, 0x1F0CB5CCu);
                v396 = SXVWGEOM::RwFirst(v395);
                WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v394, 2214658821LL, v396);
                MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1496);
                v68 = v1238;
                v264 = v1220;
                v1165 = Src;
                v1166 = v1250;
                v1176 = v1219;
                goto LABEL_815;
              }
              if ( v1200 )
                OSRR::SetAppAllowed((OSRR *)&v1240, 0);
            }
            MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1496);
            v68 = v1238;
            v114 = v1157;
            v371 = v1169;
            v1173 = v1189;
            v1252 = v1263;
            v1165 = Src;
            v1176 = v1219;
            v1166 = v1250;
            v1163 = v1238;
          }
          else
          {
            v68 = v1163;
          }
          v397 = 0;
          if ( v68 )
            v397 = (int)LoadRecovery::Lrmode(v68) > 0;
          v398 = v397 && LoadRecovery::FRepairPkg((LoadRecovery *)v68);
          v1253 = v398;
          v399 = BKORWS::Psh((BKORWS *)&v1184);
          v1220 = (struct STGI *)FileSource::HpstgiFileOpenEx(
                                   v1310,
                                   2098177,
                                   0,
                                   &v1264,
                                   0,
                                   v1253,
                                   0,
                                   0,
                                   0,
                                   v1577,
                                   &v1256,
                                   &v1572,
                                   0,
                                   0,
                                   0,
                                   0,
                                   v1272,
                                   0,
                                   v1218,
                                   v399);
          v264 = v1220;
          if ( (unsigned int)FErrPstgi(v1220) )
          {
            v114 = -2146827284;
            v1157 = -2146827284;
            XlsDiag::LogSetHrCoreTag(-2146827284, 0x230E1E3u);
          }
          else
          {
            v1191 = 1;
          }
          if ( (unsigned int)FErrPstgi(v264) && (unsigned __int16)PstgiFromErr((unsigned __int16)v264) == 8 )
          {
            v400 = v1264;
LABEL_724:
            if ( v400 == -2147168507 )
            {
              MsoShipAssertTagProc(505156896);
              v400 = v1264;
            }
            v1182 = v400;
            if ( v400 >= 0 )
              v400 = -2147467260;
            XlsDiag::LogSetHrCoreTag(v400, 0x179770Au);
            v401 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1184);
            v402 = OpenTelemetry::POpenFileStageModel(v401);
            v403 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1398, 0x1F0CB5CBu);
            v404 = SXVWGEOM::RwFirst(v403);
            v405 = 2214658821LL;
            if ( v1182 < 0 )
              v405 = (unsigned int)v1182;
            WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v402, v405, v404);
            goto LABEL_815;
          }
          v400 = v1264;
          if ( v1264 == -2147168507 )
            goto LABEL_724;
          if ( !(unsigned int)FErrPstgi(v264) )
          {
            v1168 = 1;
            errDeferred = 0;
          }
LABEL_734:
          if ( !(unsigned int)FErrPstgi(v264) )
          {
            if ( !v1162
              || ((*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1162 + 224LL))(v1162) & 1) == 0
              || (v406 = STGI::Pxpkg(v264), !(unsigned int)FIsSharedWbk(v406)) )
            {
              if ( v68 )
              {
                v412 = PivotOperationBase::PSxview((PivotOperationBase *)v68);
                *((_WORD *)v412 + 18) |= 4u;
              }
              v413 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 2024LL);
              v1203 = v413 != 0;
              if ( !v413 )
                XlsDiag::SendTraceTag(38048668, 187, 50, 4, L"FInLoad expected to be false at that point");
              v414 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1184);
              v415 = (LXBASE *)OpenTelemetry::POpenFileStageModel(v414);
              v416 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1399, 0x1F0CB5CAu);
              SXVWGEOM::RwFirst(v416);
              WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v415);
              MaxPathStPoke::MaxPathStPoke((MaxPathStPoke *)v1494, (struct MaxPathHolder *)v1344);
              v417 = BKORWS::Psh((BKORWS *)&v1184);
              v418 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1544);
              Context = OlDocFilePath::PClpLoadContext(v418);
              v1449 = std::_Optional_construct_base<CorruptionMetaData>::operator*(v1543);
              v1451 = v1162;
              if ( v1192 )
                v419 = BKORWS::Psh((BKORWS *)v1487);
              else
                v419 = 0;
              v420 = v1256;
              v421 = a10 & 0x800;
              v422 = (struct OpenTelemetry *)v1249;
              if ( v1176 || (v423 = 0, v1168) )
                v423 = 1;
              v424 = MaxPathSzPoke::CchSzBufferSize((MaxPathSzPoke *)v1494);
              v425 = SlicerViewImpl::PSlicerView((SlicerViewImpl *)v1494);
              LOBYTE(v1154) = v1164;
              v1150[0] = v1252;
              v1147 = v419;
              v68 = v1163;
              v1140 = v422;
              v264 = v1220;
              LODWORD(v1138) = 0;
              LODWORD(v1136) = a7;
              LODWORD(v1134) = a5;
              LODWORD(v1133) = v423;
              v1182 = HrLoadMetro(
                        0,
                        v1220,
                        &v1572,
                        v1310,
                        v425,
                        v424,
                        v1133,
                        v1134,
                        v1136,
                        v1138,
                        v1140,
                        &v1199,
                        v1163,
                        v1577,
                        v420,
                        v421,
                        v1147,
                        &v1240,
                        *(_QWORD *)v1150,
                        v1451,
                        v1275,
                        v1450,
                        &v1293,
                        v1449,
                        v1154,
                        Context,
                        v1278,
                        v417);
              MaxPathStPoke::~MaxPathStPoke((MaxPathStPoke *)v1494);
              v426 = v1182;
              v1157 = v1182;
              v114 = v1182;
              if ( v1182 < 0 )
              {
                XlsDiag::LogSetHrCoreTag(v1182, 0x17D88D8u);
                v426 = v1182;
                if ( v1182 < 0 )
                {
                  if ( OSRR::FReadyForOsr((OSRR *)&v1240) )
                  {
                    v73 = 1;
                    goto LABEL_764;
                  }
                  v426 = v1182;
                }
              }
              v1158 = v426 >= 0;
              if ( v426 >= 0 )
                v1307 = *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                        + 40LL);
              v427 = NtCurrentTeb()->ThreadLocalStoragePointer;
              v1249 = (void *)-1LL;
              v1228 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v427 + 304LL) + 2924LL);
              if ( v426 < 0 )
              {
                if ( v1192 )
                {
                  FileSource::HrDeleteTemp((FileSource *)v1310);
                  v426 = v1182;
                }
                if ( v68 && (v426 == -2134142954 || v426 == -2134188030) )
                  LoadRecovery::SetRepairState((LoadRecovery *)v68, v426);
                v73 = 1;
              }
              else
              {
                if ( v1192 && v1234 != 68 )
                {
                  v428 = LOCATIONCONTEXTDATA::PWorkbookCur((LOCATIONCONTEXTDATA *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                             + 304LL)
                                                                                 + 8LL));
                  Api::Workbook::SetFt(v428, (unsigned int)v1234, 0);
                }
                v429 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                if ( *(_DWORD *)(*(_QWORD *)(v429 + 872) + 104LL) == 2 && (v1190 & 2) == 0 )
                {
                  v1273 = *(struct SH **)(v429 + 32);
                  v430 = LOCATIONCONTEXTDATA::PWorkbookCur((LOCATIONCONTEXTDATA *)(v429 + 8));
                  v431 = OcsTransitionController::PCoauthTransitionState(v430);
                  v432 = XLSBOOK::Plxtab(v431);
                  v433 = SlicerViewImpl::PSlicerView(v432);
                  v434 = LOCATIONCONTEXTDATA::PWorkbookCur((LOCATIONCONTEXTDATA *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                             + 304LL)
                                                                                 + 8LL));
                  v435 = OcsTransitionController::PCoauthTransitionState(v434);
                  v436 = (TAB *)((char *)v433 + 16 * *((int *)XLSBOOK::Plxtab(v435) + 1));
                  if ( v433 < v436 )
                  {
                    v437 = NtCurrentTeb()->ThreadLocalStoragePointer;
                    do
                    {
                      v438 = TAB::PshDesktopOnly(v433);
                      if ( (*((_BYTE *)v438 + 10) & 4) != 0 )
                        v439 = 0;
                      else
                        v439 = *((_BYTE *)v438 + 8);
                      if ( v439 <= 1u )
                      {
                        v440 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1400, 0x237630D9u);
                        v441 = SXVWGEOM::RwFirst(v440);
                        v442 = TAB::PshDesktopOnly(v433);
                        v443 = *(_QWORD *)(*(_QWORD *)v437 + 304LL);
                        v444 = 0;
                        v445 = *(_QWORD **)(v443 + 128);
                        if ( v445 )
                        {
                          v446 = *(_QWORD **)(v443 + 128);
                          do
                          {
                            v444 = v446[1];
                            if ( v444 )
                              break;
                            v445 = (_QWORD *)*v445;
                            v446 = v445;
                          }
                          while ( v445 );
                        }
                        LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v444 + 96), v442, v441);
                        v447 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v437 + 304LL) + 32LL);
                        if ( !((*(_BYTE *)(v447 + 10) & 4) != 0 ? 0 : *(_BYTE *)(v447 + 8)) )
                        {
                          v275 = HrConvertSheetFmlaToVal();
                          if ( v275 < 0 )
                          {
LABEL_1910:
                            v1171 = v275;
                            goto LABEL_1133;
                          }
                        }
                      }
                      v433 = (TAB *)((char *)v433 + 16);
                    }
                    while ( v433 < v436 );
                    v68 = v1163;
                  }
                  v449 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1401, 0x237630D8u);
                  v450 = SXVWGEOM::RwFirst(v449);
                  v451 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 128LL);
                  v452 = 0;
                  if ( v451 )
                  {
                    v453 = v451;
                    do
                    {
                      v452 = v453[1];
                      if ( v452 )
                        break;
                      v451 = (_QWORD *)*v451;
                      v453 = v451;
                    }
                    while ( v451 );
                  }
                  LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v452 + 96), v1273, v450);
                  v264 = v1220;
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
                v454 = (struct WNX *)UIGLOBALS::UIGLOBALSCONTAINER::m_selection;
                if ( !UIGLOBALS::UIGLOBALSCONTAINER::m_selection )
                {
                  SetWnxSel(*(struct WNX **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                           + 104LL));
                  v454 = (struct WNX *)UIGLOBALS::UIGLOBALSCONTAINER::m_selection;
                }
                v73 = 1;
                FActivateListWnx(v454, 1, 0);
              }
              *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1225;
              v1156 = 0;
              goto LABEL_910;
            }
            StgiFileClose(v264);
            if ( v1249 != (void *)-1LL )
            {
              CloseSentinelFile(v1249);
              v1249 = (void *)-1LL;
            }
            if ( v1183 )
            {
              HrRecordEvent(v1162, 0x40000000u, 0);
              v1183 = 0;
            }
            if ( (*(int (__fastcall **)(struct IMsoOLDocument *, _QWORD, __int64))(*(_QWORD *)v1162 + 232LL))(
                   v1162,
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
              v1042 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
              *(_DWORD *)(v1042 + 2024) = 0;
              *(_DWORD *)(v1042 + 2028) = 0;
              goto LABEL_1882;
            }
LABEL_743:
            v407 = v1166;
            goto LABEL_744;
          }
          if ( (unsigned __int16)PstgiFromErr((unsigned __int16)v264) )
            goto LABEL_645;
          v455 = FileSource::SzFilePath((FileSource *)v1310);
          OkAlert(196758, v455);
          XlsDiag::LogSetHrCoreTag(-2147319765, 0x179770Du);
LABEL_815:
          if ( v68 )
          {
            v457 = PivotOperationBase::PSxview((PivotOperationBase *)v68);
            *((_WORD *)v457 + 18) |= 8u;
          }
          goto LABEL_817;
        }
        v342 = 2098176;
        v343 = 2098176;
        if ( v334 )
        {
          v342 = 2098177;
          v343 = 2098177;
        }
        v344 = v342;
        if ( *(_QWORD *)&UIGLOBALS::UIGLOBALSCONTAINER::m_posi )
        {
          v345 = *(_QWORD *)(*(_QWORD *)&UIGLOBALS::UIGLOBALSCONTAINER::m_posi + 1568LL);
          if ( v345 )
          {
            if ( !*(_QWORD *)(v345 + 256) )
            {
              v343 = v342 | 0x20;
              v344 = v342 | 0x20;
            }
          }
        }
        if ( v1177 )
          v343 = v344 | 0x1000000;
        v346 = v1191;
        if ( v1191 )
          v343 |= 0x20000000u;
        if ( v1272 && FileSource::FCloud((FileSource *)v1310) )
        {
          MsoShipAssertTagProc(504422487);
          v347 = 504422486;
          v348 = -2147467260;
LABEL_567:
          XlsDiag::LogSetHrCoreTag(v348, v347);
          std::_Optional_destruct_base<DataLossProtection::NotifyRaiiHintsForPrePostEvents,0>::reset(v1341);
          goto LABEL_507;
        }
        if ( v1245 )
        {
          v349 = BKORWS::Psh((BKORWS *)&v1184);
          v350 = v1218;
          v351 = v349;
          v352 = (unsigned __int8)v1163;
          if ( v1163 )
            v352 = LoadRecovery::FRepairPkg((LoadRecovery *)v1163);
          v1220 = (struct STGI *)FileSource::HpstgiFileOpenEx(
                                   v1310,
                                   v343,
                                   0,
                                   &v1227,
                                   0,
                                   v352,
                                   0,
                                   0,
                                   0,
                                   v1577,
                                   &v1256,
                                   &v1572,
                                   0,
                                   0,
                                   &v1245,
                                   1,
                                   v1272,
                                   0,
                                   v350,
                                   v351);
          v264 = v1220;
          if ( (unsigned int)FErrPstgi(v1220) )
          {
            v353 = 36757983;
LABEL_579:
            v114 = -2146827284;
            v1157 = -2146827284;
            XlsDiag::LogSetHrCoreTag(-2146827284, v353);
          }
        }
        else
        {
          v354 = BKORWS::Psh((BKORWS *)&v1184);
          v355 = v1218;
          v356 = v354;
          v357 = v1163 && LoadRecovery::FRepairPkg((LoadRecovery *)v1163);
          LOBYTE(v1129) = v357;
          v1220 = (struct STGI *)XLFileIOMockable::PstgiFileOpen(
                                   v1310,
                                   v343,
                                   0,
                                   &v1227,
                                   (_DWORD)v1129,
                                   0,
                                   v1272,
                                   v355,
                                   v356);
          v264 = v1220;
          if ( (unsigned int)FErrPstgi(v1220) )
          {
            v353 = 36757984;
            goto LABEL_579;
          }
        }
        v358 = FErrPstgi(v264);
        v359 = v346;
        if ( !v358 )
          v359 = 1;
        v1191 = v359;
        if ( !(unsigned int)FErrPstgi(v264) && OSRR::IsAppAllowed((OSRR *)&v1240) )
        {
          if ( v1256 )
          {
            OSRR::SetAppAllowed((OSRR *)&v1240, 0);
            if ( (unsigned int)XLOSRR::FMustUseOsr((XLOSRR *)&v1240)
              || OSRR::FHasReasons((OSRR *)&v1240) && (unsigned int)NoYesAlert(589864, &v1572) == 7 )
            {
              StgiFileClose(v264);
              v347 = 24737540;
              v264 = 0;
              v1220 = 0;
LABEL_589:
              v348 = -2146827284;
              goto LABEL_567;
            }
          }
        }
        if ( !v1177 || !(unsigned int)FErrPstgi(v264) )
          goto LABEL_607;
        if ( (unsigned __int16)PstgiFromErr((unsigned __int16)v264) == 7 )
        {
          v361 = APPCORE::PlocaleinfoUSEN((APPCORE *)&vapp);
          if ( !(unsigned int)FMetroFileExt((const struct FileSource *)v1310, v361, 0, 0) )
            goto LABEL_607;
        }
        else
        {
          if ( MsoFDrmErrorCode(v1227) )
          {
            v360 = -2042494975;
LABEL_606:
            SetLoadForPreviewError(v360);
LABEL_607:
            if ( (unsigned int)FErrPstgi(v264) )
            {
              v362 = (unsigned __int16)PstgiFromErr((unsigned __int16)v264);
              v363 = v1227;
              if ( v362 == 8 || v1227 == -2147168507 )
              {
                if ( v1227 == -2147168507 )
                {
                  MsoShipAssertTagProc(505157471);
                  v363 = v1227;
                }
                v1182 = v363;
                v1170 = 1;
                if ( v1192 )
                {
                  FileSource::HrDeleteTemp((FileSource *)v1310);
                  v363 = v1182;
                }
                if ( v363 >= 0 )
                  v363 = -2147467260;
                XlsDiag::LogSetHrCoreTag(v363, 0x1797705u);
                v364 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1184);
                v365 = OpenTelemetry::POpenFileStageModel(v364);
                v366 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1396, 0x1F0CB5CDu);
                v367 = SXVWGEOM::RwFirst(v366);
                WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v365, (unsigned int)v363, v367);
                std::_Optional_destruct_base<DataLossProtection::NotifyRaiiHintsForPrePostEvents,0>::reset(v1341);
                MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1318);
                v68 = v1163;
                goto LABEL_815;
              }
            }
            v1179 = 1;
            goto LABEL_618;
          }
          if ( (unsigned __int16)PstgiFromErr((unsigned __int16)v264) != 4
            && v1227 != -2147286775
            && (unsigned int)(v1227 + 2147286780) > 1
            && v1227 != -2147286960
            && v1227 != -2147287010 )
          {
            if ( (unsigned __int16)PstgiFromErr((unsigned __int16)v264) == 8 )
            {
              v360 = -2147467260;
            }
            else
            {
              if ( (unsigned int)FOsrc() )
                goto LABEL_607;
              v360 = -2147467259;
            }
            goto LABEL_606;
          }
        }
        v360 = -2042494972;
        goto LABEL_606;
      }
      MaxPathStzPoke::MaxPathStzPoke((MaxPathStzPoke *)v1493, (struct MaxPathHolder *)v1318);
      v284 = MaxPathStzPoke::CchStzBufferSize((MaxPathStzPoke *)v1493);
      v285 = (wchar_t *)SlicerViewImpl::PSlicerView((SlicerViewImpl *)v1493);
      v1192 = FHandleConverterFile(
                (struct FileSource *)v1310,
                v285,
                v284,
                (enum FILETYPE *)&v1234,
                &v1347,
                (struct XLOSRR *)&v1240,
                v1165);
      v283 = (MaxPathStzPoke *)v1493;
    }
    MaxPathStzPoke::~MaxPathStzPoke(v283);
    goto LABEL_473;
  }
  v468 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
  if ( *(_QWORD *)(v468 + 40) )
    v1172 = *(struct STM **)(*(_QWORD *)(v468 + 40) + 56LL);
  else
    v1172 = 0;
  do
  {
LABEL_439:
    if ( !SbFromHpCore(v1172) )
    {
      if ( wProjLoad == 1 )
        wProjLoad = 5;
      if ( (unsigned int)FErrPstgi(v264) )
      {
        v68 = v1163;
        if ( !v1163 || v1236 )
        {
LABEL_987:
          v501 = v1166;
          goto LABEL_954;
        }
        v545 = PivotOperationBase::PSxview((PivotOperationBase *)v1163);
        *((_WORD *)v545 + 18) |= 8u;
LABEL_953:
        v501 = v1166;
        goto LABEL_954;
      }
LABEL_969:
      OSRR::SetAppAllowed((OSRR *)&v1240, 0);
      if ( (unsigned int)XLOSRR::FMustUseOsr((XLOSRR *)&v1240) )
      {
        StgiFileClose(v264);
        v114 = -2147024809;
        XlsDiag::LogSetHrCoreTag(-2147024809, 0x1797716u);
        v68 = v1163;
        v1158 = 0;
        errDeferred = 0;
        v581 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        *(_DWORD *)(v581 + 2024) = 0;
        *(_DWORD *)(v581 + 2028) = 0;
LABEL_821:
        LOBYTE(v264) = v1156;
        goto LABEL_518;
      }
      v114 = FileSource::HrGetFileTemp(v1310, 13);
      v1157 = v114;
      if ( v114 >= 0 )
      {
        v277 = v1165;
        if ( (unsigned int)FFinderFile(v1165) )
        {
          vfPretendNotStg = 1;
          StgiFileClose(v264);
          v580 = 1049729;
          if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                         + 104LL) != 2 )
            v580 = 1025;
          v1172 = FileSource::StreamOpen((FileSource *)v1310, v580, 0);
          vhpstm = v1172;
          goto LABEL_1078;
        }
      }
      else
      {
        XlsDiag::LogSetHrCoreTag(v114, 0x27413C0u);
      }
      if ( v1193
        && *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1232LL)
                     + 32LL) )
      {
        v540 = FExecWWWHelp(-1);
        v541 = 0;
        if ( v540 )
        {
          v68 = v1163;
LABEL_977:
          StgiFileClose(v264);
          goto LABEL_953;
        }
      }
      else
      {
        v541 = 0;
      }
      if ( v1572 < 0xFFu )
      {
        v542 = 58;
        v1573[v1572] = 58;
        v543 = 2LL * v1572 + 4;
        if ( v543 >= 0x202 )
          goto LABEL_2137;
        *(wchar_t *)((char *)&v1573[-1] + v543) = 0;
        OkAlert(196665, v1573);
        MakeStStzTruncOK(&v1572, 257);
      }
      v68 = v1163;
      if ( v1163 )
      {
        v544 = PivotOperationBase::PSxview((PivotOperationBase *)v1163);
        *((_WORD *)v544 + 18) |= 8u;
      }
      goto LABEL_977;
    }
    if ( hpFileSelInfo )
    {
      if ( *(int *)hpFileSelInfo >= 21 && !v1177 )
      {
        OSRR::SetAppAllowed((OSRR *)&v1240, 0);
        if ( (unsigned int)XLOSRR::FMustUseOsr((XLOSRR *)&v1240) )
        {
          if ( SbFromHpCore(v1172) )
            StreamClose(v1172);
          v1172 = 0;
          v1158 = 0;
          v114 = -2146827284;
          vhpstm = 0;
          errDeferred = 0;
          v575 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          *(_DWORD *)(v575 + 2024) = 0;
          *(_DWORD *)(v575 + 2028) = 0;
          XlsDiag::LogSetHrCoreTag(-2146827284, 0x1797710u);
LABEL_466:
          v68 = v1163;
          LOBYTE(v264) = v1156;
          goto LABEL_467;
        }
      }
    }
    if ( v1158
      || !SbFromHpCore(v1172)
      || *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                   + 104LL) == 2 )
    {
      if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                     + 104LL) == 2 )
      {
        ENV::ENV((ENV *)&v1562);
        v494 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        v1452 = *(_QWORD *)(v494 + 336);
        *(_QWORD *)(v494 + 336) = &v1562;
        v1563 = 36737604;
        v495 = setjmp(v1564);
        v496 = v1452;
        if ( v495
          || (v497 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1344), (int)HrDeferredSRO(&v1572, 0, v497, 0, 0) < 0) )
        {
          v1157 = -2147467259;
          v114 = -2147467259;
          XlsDiag::LogSetHrCoreTag(-2147467259, 0x279F29Fu);
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v496;
        }
        else
        {
          v114 = v1157;
        }
        v68 = v1238;
        v168 = v1219;
        v498 = *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer;
        v1163 = v1238;
        v1176 = v1219;
        *(_QWORD *)(*(_QWORD *)(v498 + 304) + 336LL) = v496;
        v499 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1304LL);
        *(_WORD *)(v499 + 56) &= ~8u;
        v1173 = v1189;
        v1165 = Src;
        v1166 = v1250;
        v1158 = 2;
      }
      else
      {
        v68 = v1163;
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
        v1292 = 0;
        if ( (unsigned int)FBeginDiskIO(v1172) )
        {
          v1291 = 0;
          v275 = HrWPlatformSpecificFromStream2(&v1291);
          if ( v275 < 0 )
            goto LABEL_1910;
          if ( (v1291 & 0xF1FF) == 9 )
          {
            v276 = v1163;
            v1330 = 0;
            v275 = HrReadBof(v1291, 0, (struct LoadRecovery *)v1163, &v1330);
            if ( v275 < 0 )
              goto LABEL_1910;
            v275 = HrReadFileAccess(v1588, 8224, &v1572, 0, 0, 0, 0, (struct LoadRecovery *)v276, &v1267, &v1292);
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
        if ( !v1292 )
        {
          StreamClose(v1172);
          StgiFileClose(v264);
          v1043 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          v1030 = 40981772;
          *(_DWORD *)(v1043 + 2024) = 0;
          *(_DWORD *)(v1043 + 2028) = 0;
          goto LABEL_1878;
        }
        v277 = v1165;
        LOBYTE(v1133) = 1;
        SafeToLoad::FGatekeep(v1165, v1310, 0, 0, 0, &v1240, (_DWORD)v1133);
        goto LABEL_859;
      }
    }
    v277 = v1165;
LABEL_859:
    if ( v274
      && v1162
      && ((*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1162 + 224LL))(v1162) & 1) != 0 )
    {
      StreamClose(v1172);
      StgiFileClose(v264);
      if ( v1183 )
      {
        HrRecordEvent(v1162, 0x40000000u, 0);
        v1183 = 0;
      }
      if ( (*(int (__fastcall **)(struct IMsoOLDocument *, _QWORD, __int64))(*(_QWORD *)v1162 + 232LL))(v1162, 0, 1) < 0 )
      {
        Error(196658);
        XlsDiag::SendTraceTag(
          18088268,
          187,
          10,
          4,
          L"FFileLoad Failed to disable the RobustifiedUNC behavior on the file.");
        v1044 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        v1030 = 24737554;
        *(_DWORD *)(v1044 + 2024) = 0;
        *(_DWORD *)(v1044 + 2028) = 0;
        goto LABEL_1893;
      }
      goto LABEL_1072;
    }
    v469 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1304LL);
    *(_WORD *)(v469 + 56) &= ~8u;
    *(_WORD *)(v469 + 56) |= 8 * (_WORD)v274;
    v473 = 0;
    if ( !(unsigned int)FErrPstgi(v264) )
    {
      v470 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1544);
      v471 = OlDocFilePath::PClpDocument(v470);
      v472 = STGI::Lpstg(v264);
      if ( !(unsigned int)FDrmQueryRightsStg(v472, 4u, v471) )
        v473 = 1;
    }
    v1188 = v473;
    if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1836LL) )
    {
      if ( !(unsigned int)FErrPstgi(v264) )
      {
        v474 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1544);
        v475 = OlDocFilePath::PClpDocument(v474);
        v476 = STGI::Lpstg(v264);
        if ( !(unsigned int)FDrmQueryRightsStg(v476, 2u, v475) )
        {
          StreamClose(v1172);
          StgiFileClose(v264);
          HandleLockError(327752);
          v1030 = 24737555;
          v1045 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          v114 = -1662124019;
          *(_DWORD *)(v1045 + 2024) = 0;
          *(_DWORD *)(v1045 + 2028) = 0;
          goto LABEL_1894;
        }
      }
    }
    v68 = v1163;
    lp = *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL);
    if ( v1163 )
    {
      v477 = a10 & 0x400;
      v478 = PivotOperationBase::PSxview((PivotOperationBase *)v1163);
      *((_WORD *)v478 + 18) &= ~0x40u;
      *((_WORD *)v478 + 18) |= v477 != 0 ? 0x40 : 0;
    }
    if ( (a10 & 0x8000) != 0 )
      OSRR::SetHasInvalidPivot((OSRR *)&v1240, 1);
    v479 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1344);
    CchStToStz(v479, v1587, 2084);
    v480 = APPCORE::PmemheapMain((APPCORE *)&vapp);
    MaxPathHolder::MaxPathHolder((MaxPathHolder *)v1486, v480, 259, 0);
    v481 = FileSource::HrGetFileTemp(v1310, 10);
    v1157 = v481;
    v114 = v481;
    if ( v481 < 0 )
    {
      XlsDiag::LogSetHrCoreTag(v481, 0x27413A3u);
      StreamClose(v1172);
      StgiFileClose(v264);
      Error(327845);
      MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1486);
      goto LABEL_1861;
    }
    v482 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1184);
    v483 = (LXBASE *)OpenTelemetry::POpenFileStageModel(v482);
    v484 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1404, 0x1F0CB5C7u);
    SXVWGEOM::RwFirst(v484);
    WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v483);
    v485 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1486);
    v486 = HrLoadBiff(
             &v1172,
             &v1572,
             v1587,
             v485,
             v168,
             a5,
             a7,
             v264,
             0,
             &v1199,
             &v1228,
             (struct LoadRecovery *)v68,
             &lp,
             (struct XLOSRR *)&v1240,
             v1275,
             &v1267,
             v1278,
             &v1158);
    if ( v486 < 0 )
    {
      v1171 = v486;
      MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1486);
      goto LABEL_1133;
    }
    MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1344, v1587);
    if ( !v1158 && OSRR::FReadyForOsr((OSRR *)&v1240) )
    {
      XlsDiag::LogSetHrCoreTag(-2147024809, 0x205C2A1u);
      v1160 = 1;
      MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1486);
      v407 = v1166;
      goto LABEL_744;
    }
    if ( lp != *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL)
      && (unsigned int)FResidentBook(lp) )
    {
      v1308 = *(struct SH **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 32LL);
      v487 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1405, 0x2375A798u);
      v488 = SXVWGEOM::RwFirst(v487);
      v489 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 128LL);
      v490 = 0;
      if ( v489 )
      {
        v491 = v489;
        do
        {
          v490 = v491[1];
          if ( v490 )
            break;
          v489 = (_QWORD *)*v489;
          v491 = v489;
        }
        while ( v489 );
      }
      LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v490 + 96), lp, v488);
    }
    if ( v1158 && *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL) )
    {
      if ( !v1177 )
      {
        v492 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1486);
        if ( (unsigned int)HrCheckCollaboration(v277, v492) == -2147467260 )
        {
          errDeferred = 0;
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1225;
          LOBYTE(v264) = 0;
          if ( v68 )
          {
            v576 = PivotOperationBase::PSxview((PivotOperationBase *)v68);
            *((_WORD *)v576 + 18) |= 8u;
          }
          v114 = -2147467260;
          XlsDiag::LogSetHrCoreTag(-2147467260, 0x1797714u);
          v1158 = 0;
          MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1486);
          goto LABEL_1664;
        }
      }
      v493 = (struct WNX *)UIGLOBALS::UIGLOBALSCONTAINER::m_selection;
      v1179 = 1;
      if ( !UIGLOBALS::UIGLOBALSCONTAINER::m_selection )
      {
        SetWnxSel(*(struct WNX **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 104LL));
        v493 = (struct WNX *)UIGLOBALS::UIGLOBALSCONTAINER::m_selection;
      }
      FActivateListWnx(v493, 1, 0);
    }
    MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1486);
LABEL_901:
    if ( v1158 == 16 )
    {
      if ( v168 || (v500 = 1024, v1168) )
        v500 = 1025;
      v264 = FileSource::HpstgiFileOpen((FileSource *)v1310, &v1572, v500, 0, 0, 0, 0, 0, v1218);
      v1220 = v264;
      v1193 = 1;
      v1158 = 0;
      if ( !(unsigned int)FErrPstgi(v264) )
        goto LABEL_969;
      v1157 = -2146827284;
      v114 = -2146827284;
      XlsDiag::LogSetHrCoreTag(-2146827284, 0x230E203u);
    }
    else
    {
      v264 = v1220;
    }
    if ( v1199 == 32 && (unsigned int)OkCancelAlert(196937, 0) == 1 )
    {
      v1172 = FileSource::StreamOpen((FileSource *)v1310, 0x401u, 0);
      vhpstm = v1172;
      goto LABEL_1077;
    }
LABEL_910:
    if ( !v1159 )
      goto LABEL_987;
    if ( !(unsigned int)sub_140486720((unsigned int)v1199, (unsigned int)v1228) || v1158 == 2 )
    {
      v507 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
      if ( *(_QWORD *)(v507 + 40) && (v1158 == 1 || (*(_DWORD *)(*(_QWORD *)(v507 + 40) + 884LL) & 0x200) != 0) )
      {
        if ( (unsigned int)IMsoOLDocument::IsInFileSys(v1162) )
        {
          v508 = (wchar_t **)XLSBOOK::Plxtab(*(XLSBOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                     + 304LL)
                                                         + 40LL));
          FreeHpstTempPath((struct STB *)v508, v509);
          if ( v1192 )
          {
            v510 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1487);
          }
          else if ( FileSource::FCloudStreaming((FileSource *)v1310) )
          {
            v511 = std::_Optional_construct_base<OlDocFilePath>::operator*(v1544);
            v510 = (const wchar_t *)OfficeExtension::ServerRuntime::RichApiMessageEntry::GetTarget(v511);
          }
          else
          {
            v510 = FileSource::StzFilePath((FileSource *)v1310);
          }
          if ( (int)HrStDupSt(v510, v508 + 21) < 0 )
            v508[21] = 0;
        }
        v512 = *(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL);
        v513 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1407, 0x236962A0u);
        v514 = SXVWGEOM::RwFirst(v513);
        BOOK::SetPioldoc(v512, v1162, v514);
        v515 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        if ( *(_QWORD *)(v515 + 40) != v1306
          && (*(_DWORD *)(*(_QWORD *)(v515 + 40) + 1440LL) & 0x8000000) != 0
          && (*(unsigned int (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1162 + 208LL))(v1162) == 2 )
        {
          v516 = v1218;
          XlAsyncFileIO::SpOLDocCoauthFromPOLDoc(v1343, v1162);
          if ( (unsigned __int8)std::shared_ptr<Mso::ActivityScope::IMsoLoggingScope>::operator bool(v1343)
            && (v517 = BKORWS::Psh((BKORWS *)v1343), XlAsyncFileIO::FIsDistributedBlobsFile(v517)) )
          {
            v1204 = 1;
            v518 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1408, 0x1E307684u);
            v519 = SXVWGEOM::RwFirst(v518);
            OldocHelper::SetReadOnly(v1162, v519);
            if ( v516 )
            {
              v520 = Mso::Telemetry::Activity::DataFields(v516);
              Mso::Telemetry::IDataFieldCollection::Add(v520, "SwitchToRO", "ZipItOldocSetReadOnly");
            }
          }
          else
          {
            HrRecordEvent(v1162, 0x40000000u, 0);
            v521 = (*(__int64 (__fastcall **)(struct IMsoOLDocument *, __int64, _QWORD, _QWORD))(*(_QWORD *)v1162 + 104LL))(
                     v1162,
                     4,
                     0,
                     *(int *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                        + 1232LL)
                            + 80LL));
            if ( v521 - 3473424 <= 1 )
              XlFileProtocolManager::TrackOpen(v1162);
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
          Mso::TCntPtr<Uxpp::UxppAnnotationsService>::~TCntPtr<Uxpp::UxppAnnotationsService>(v1343);
        }
        v527 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        if ( *(_QWORD *)(v527 + 40) != v1306 )
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
        if ( v1293 )
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
    if ( (unsigned int)FIsShareErr(errDeferred) && (_QWORD)xmmword_143FE0F90 )
      goto LABEL_987;
    HrRecordEvent(v1162, 0x40000000u, 0);
    v501 = v1166;
    v1183 = 0;
    if ( *v1166 )
      _IMsoOLDocument_SetIReDownload(*v1166, -1);
    v502 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1406, 0x236962A1u);
    v503 = SXVWGEOM::RwFirst(v502);
    v504 = OlDocFilePath::FReleaseIOLDoc(&v1162, 1, 1, v503);
    *v501 = 0;
    if ( v1158 && !v504 )
    {
      errDeferred = 0;
      v505 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
      *(_DWORD *)(v505 + 2024) = 0;
      *(_DWORD *)(v505 + 2028) = 0;
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1225;
      LOBYTE(v264) = 0;
      if ( v68 )
      {
        v506 = PivotOperationBase::PSxview((PivotOperationBase *)v68);
        *((_WORD *)v506 + 18) |= 8u;
      }
      v114 = -2146827284;
      XlsDiag::LogSetHrCoreTag(-2146827284, 0x1797715u);
      goto LABEL_467;
    }
LABEL_954:
    if ( v1159 && v1183 && v1158 != 2 && (!(unsigned int)FIsShareErr(errDeferred) || !(_QWORD)xmmword_143FE0F90) )
    {
      v534 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
      if ( !*(_QWORD *)(v534 + 40) || (*(_DWORD *)(*(_QWORD *)(v534 + 40) + 884LL) & 0x200) == 0 )
      {
        if ( (a10 & 0x100) != 0 )
        {
          v535 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1409, 0x21C730Fu);
          v536 = SXVWGEOM::RwFirst(v535);
          OldocHelper::SetAttrInAttrMask(v1162, 0, 0x100000u, v536);
        }
        if ( v1204 && v1158 )
        {
          v537 = Measurements::Stopwatch::Stopwatch((Measurements::Stopwatch *)v1542);
          LOBYTE(v538) = 1;
          Measurements::MeasureElapsedTime::MeasureElapsedTime(
            v1530,
            Measurements::MeasurementId::ExcelRecordEvent,
            v538,
            v537);
          v1331 = 3473425;
          (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, int *, _QWORD))(*(_QWORD *)v1162 + 112LL))(
            v1162,
            0x40000000,
            &v1331,
            0);
          Measurements::MeasureElapsedTime::~MeasureElapsedTime((Measurements::MeasureElapsedTime *)v1530);
        }
        else
        {
          v546 = BKORWS::Psh((BKORWS *)&v1184);
          if ( (unsigned int)XlFileProtocolManager::HrRecordEvent(v1162, 0x40000000u, v1158 != 0, v1205, v546) == -1662189464 )
          {
            v114 = -1662189464;
            XlsDiag::LogSetHrCoreTag(-1662189464, 0x1E26384Cu);
            v1183 = 0;
            goto LABEL_1882;
          }
        }
        v1183 = 0;
      }
    }
    if ( !(unsigned int)FIsShareErr(errDeferred) || !(_QWORD)xmmword_143FE0F90 )
      goto LABEL_1105;
    v547 = 304;
    if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                   + 104LL) == 2 )
    {
      v590 = v1215;
      if ( v1215 == 1 )
      {
        LOBYTE(v547) = v1188;
        v590 = sub_141224EE0(v1162, v547, &v1200);
        v1215 = v590;
        if ( v1200 )
          OSRR::SetAppAllowed((OSRR *)&v1240, 0);
      }
      else
      {
        sub_1413EF4D0();
      }
      if ( v590 < 0 )
      {
        if ( SbFromHpCore(v1172) )
          StreamClose(v1172);
        if ( !(unsigned int)FErrPstgi(v264) )
          StgiFileClose(v264);
        v1220 = 0;
        v1172 = 0;
        v114 = v590;
        XlsDiag::LogSetHrCoreTag(v590, 0x1797717u);
        v1158 = 0;
LABEL_1093:
        errDeferred = 0;
        v588 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v1170 = 1;
        v589 = *(_QWORD *)(*(_QWORD *)v588 + 304LL);
        *(_DWORD *)(v589 + 2024) = 0;
        *(_DWORD *)(v589 + 2028) = 0;
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1225;
        LOBYTE(v264) = 0;
        if ( v68 )
        {
LABEL_830:
          v464 = PivotOperationBase::PSxview((PivotOperationBase *)v68);
          *((_WORD *)v464 + 18) |= 8u;
        }
LABEL_518:
        v277 = v1165;
LABEL_1664:
        if ( v1547 )
        {
          v922 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1467);
          CchStToSt(v922, v277, v1229);
        }
        XslClear((struct XSL *)&v1546);
        if ( v1175 && v1274 )
          FreeRevert(v1274);
        if ( !OSRR::IsAppAllowed((OSRR *)&v1240) && (unsigned int)XLOSRR::FMustUseOsr((XLOSRR *)&v1240) )
        {
          OkAlert(589889, 0);
          v114 = -2147467260;
          v1222 = -2147467260;
          v1158 = 0;
          XlsDiag::LogSetHrCoreTag(-2147467260, 0x179771Bu);
        }
        v407 = v1166;
        vpoldocument = v1354;
        if ( v1159 && *v1166 && v1244 != -2 )
        {
          if ( v1158
            || (v923 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL), *(_QWORD *)(v923 + 40))
            && (*(_DWORD *)(*(_QWORD *)(v923 + 40) + 884LL) & 0x200) != 0 )
          {
            if ( v1183 )
            {
              v930 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
              if ( *(_QWORD *)(v930 + 40) && (*(_DWORD *)(*(_QWORD *)(v930 + 40) + 884LL) & 0x200) != 0 )
                XlFileProtocolManager::MarkOpenDone(v1162, 1, 0);
              HrRecordEvent(v1162, 0x40000000u, 1);
            }
            (*(void (__fastcall **)(struct IMsoOLDocument *, _QWORD, __int64))(*(_QWORD *)*v407 + 56LL))(*v407, 0, 7);
          }
          else
          {
            if ( v1183 )
            {
              v924 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1544);
              OlDocFilePath::RecordEventForCloseOldoc(v924, v1162, 0);
            }
            _IMsoOLDocument_SetIReDownload(*v407, -1);
            if ( (*(unsigned int (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1162 + 208LL))(v1162) )
              MsoShipAssertTagProc(946484024);
            if ( lp )
            {
              v925 = *v407;
              if ( BOOK::Pioldoc(lp) == v925 && !(unsigned int)FOsrhInTransition() )
              {
                v926 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1435, 0x2369629Bu);
                v927 = SXVWGEOM::RwFirst(v926);
                BOOK::SetPioldoc(lp, 0, v927);
              }
            }
            v928 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1436, 0x2369629Au);
            v929 = SXVWGEOM::RwFirst(v928);
            OlDocFilePath::FReleaseIOLDoc(v407, 0, 1, v929);
            *v407 = 0;
          }
        }
        v931 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1304LL);
        *(_WORD *)(v931 + 56) &= ~8u;
        if ( !v1160 && !*(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 2436LL) )
        {
          if ( v1158 && lp && !(unsigned int)XLSWORKBOOK::FAddin((struct BOOK *)((char *)lp + 1640)) )
          {
            v932 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
            HrRegisterDynamicUdfs(v932, &v1198);
          }
          v933 = Mso::Telemetry::Activity::DataFields(v1218);
          LOBYTE(v934) = v1198;
          Mso::Telemetry::IDataFieldCollection::Add<bool>(v933, "FUdfNeedsRecalc", v934, 4);
        }
        if ( v1158 == 1 && lp && (v1199 != 256 || v1228 == 4) && (v1199 & 0xE80) == 0 )
        {
          VbaLoadRefBegin();
          if ( (sksEvt & 4) == 0 || (v935 = 1, v1323) )
            v935 = 0;
          HrBookLoadComplete(lp, v935, (struct LoadRecovery *)v68, 1, &v1212);
          if ( (unsigned int)FBookHasProject(lp, 1) )
          {
            v936 = HprojectFromPbook(lp);
            HrVbpSetDirty(v936, 0);
          }
          VbaLoadRefEnd();
          if ( !v1200 )
          {
            if ( v1162 )
            {
              v937 = BOOK::Pioldoc(lp);
              if ( v1162 == v937 )
              {
                v938 = XLSWORKBOOK::Pcm((struct BOOK *)((char *)lp + 1640));
                if ( CardView::DataElementRecord::FExpanded(v938) )
                  sub_1412CF650(lp);
              }
            }
          }
        }
        if ( lp )
          XLSWORKBOOK::PostDocumentLoad((char *)lp + 1640, 0, 0);
        if ( v1198 && !v1212 )
        {
          v939 = LOCATIONCONTEXTDATA::PWorkbookCur((LOCATIONCONTEXTDATA *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                     + 304LL)
                                                                         + 8LL));
          v940 = (OcsTransitionController *)PivotMetadataCache::PvMemProps(v939);
          v941 = OcsTransitionController::PCoauthTransitionState(v940);
          Api::RecalcService::HrRecalcAll(v941, 0);
        }
        if ( !v1158 || !lp || v1200 || !BOOK::Pioldoc(lp) || (v942 = BOOK::Pioldoc(lp), v943 = 1, v1162 != v942) )
          v943 = 0;
        if ( v943 )
          XlFileProtocolManager::MarkOpenDone(v1162, 1, 0);
        v944 = v1279;
        if ( !BKORWS::Psh(v1279) || !v943 )
          goto LABEL_1755;
        v945 = XLSWORKBOOK::Pcm((struct BOOK *)((char *)lp + 1640));
        if ( !CardView::DataElementRecord::FExpanded(v945) )
          goto LABEL_1750;
        v1208 = 0;
        v1209 = 0;
        if ( v68 && BOOK::FRepairedBookCloudFile(lp) )
        {
          v946 = BKORWS::Psh(v944);
          v947 = LoadRecovery::StmfOfRepair(v68);
          QuickLoadContext::SetWorkbookRepairStmf(v946, v947);
        }
        v948 = BKORWS::Psh(v944);
        v949 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
        v950 = v948;
        v951 = v1301;
        v952 = XlAsyncFileIO::HrHandlePostLoadTasks(v949, v1301, v950, &v1226, &v1208, &v1209);
        if ( v952 == -2147023673 )
        {
          v1324 = 0;
          Title = Mso::Swagger::Schema::GetTitle(v951);
          LOBYTE(v1053) = std::nullopt;
          v1054 = Title;
          if ( !(unsigned __int8)std::operator==<XlsActivity>(Title, v1053) )
          {
            v1055 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1365, 0x28572D2u);
            v1056 = SXVWGEOM::RwFirst(v1055);
            v1057 = (Mso::Telemetry *)std::_Optional_construct_base<XlsActivity>::operator*(v1054);
            Mso::Telemetry::SetActivityResultHr(v1057, (struct Mso::Telemetry::Activity *)v952, v1056, v1058);
          }
          v1059 = HrDoCloseBookCore(&v1324, 0, 0, 0, 1, 0, 0);
          if ( v1059 < 0 )
            XlsDiag::LogSetHrCoreTag(v1059, 0x280659Bu);
          lp = 0;
          sub_1402DA5D0(&v1546, v1338, v1060);
          fCeCanceled = 1;
          v114 = v952;
          XlsDiag::LogSetHrCoreTag(v952, 0x280659Cu);
          v1158 = 0;
          goto LABEL_1935;
        }
        if ( !v1208 )
        {
          BOOK::StartCoauth(lp, 1);
LABEL_1750:
          v959 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
          v960 = FeatureGateCollectionBase<GuidedReapplyFeatureGates>::Instance(v959);
          if ( (unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(v960 + 40) )
          {
            v961 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
            v1335 = 0;
            v962 = v961;
            Api::ReloadContext::RetrieveRctxFromWorkbook(v961, &v1335);
            if ( v1335 && Api::ReloadContext::FHasData(v1335) )
              Api::ReloadContext::RestoreCoauthPanesPostReload(v1335, v962);
            XlAsyncFileIO::ClearReloadContext(v962);
          }
LABEL_1755:
          if ( (unsigned __int8)CircularReferenceTailValue::FGetFlagsShadowBag(&vapp) && v68 )
          {
            LoadRecovery::StmfOfRepair(v68);
            FormatCh_ProcIds((void *const *)&vapp);
          }
          v964 = v1301;
          v965 = lp;
          if ( v1301 && lp && v1164 )
          {
            ZrtUtility::RenderWindowsPostContentNotification(lp, UIGLOBALS::UIGLOBALSCONTAINER::m_pwnChoEdit, v963);
            v966 = v1182;
            v967 = BOOK::Pioldoc(lp);
            ZrtUtility::LogZrtOpenInformation(v967, v964, (struct XlSyncStateChangeListenerLoad *)v966, v968);
            v965 = lp;
          }
          if ( v1158 == 1 )
          {
            if ( v965 )
            {
              if ( !(unsigned int)FOsrhBook(v965) )
              {
                v1210 = 0;
                v969 = CastOrNull<XLSWORKBOOK,BOOK>(lp);
                CoauthUtil::RunDuplicateUidCheck(v969, 2, &v1210);
                if ( v1210 )
                {
                  v970 = v1279;
                  if ( BKORWS::Psh(v1279) )
                  {
                    v971 = BKORWS::Psh(v970);
                    QuickLoadContext::SetCoauthStateChanged(v971, 1);
                  }
                }
              }
            }
          }
          v972 = L"and force template load";
          v973 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          v561 = *(_DWORD *)(v973 + 1836) == 0;
          v974 = *(const struct BOOK **)(v973 + 40);
          if ( v561 )
            v972 = &WindowName;
          Only = FPioldocReadOnly(v974);
          if ( lp )
            v976 = (*((_DWORD *)lp + 360) >> 1) & 0xF;
          else
            v976 = 0;
          LODWORD(v1133) = Only;
          LODWORD(v1131) = v976;
          XlsDiag::SendTraceTag(
            7091154,
            187,
            50,
            4,
            L"Loading workbook with Auto refresh load status: %d and read only mode: %d %s",
            v1131,
            v1133,
            v972);
          v977 = v1158;
          if ( v1158 && fShowWn )
          {
            v978 = lp;
            if ( lp && (*((_BYTE *)lp + 1440) & 0x10) == 0
              || (v979 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL),
                  *(_QWORD *)(v979 + 40))
              && (*(_DWORD *)(*(_QWORD *)(v979 + 40) + 884LL) & 0x200) != 0 )
            {
              v980 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
              if ( !*(_DWORD *)(v980 + 1836) )
              {
                if ( !lp )
                  v978 = *(struct BOOK **)(v980 + 40);
                v981 = v1178;
                v982 = BOOK::Pioldoc(v978);
                MsoSetReadWriteOnSaveIoldoc(v982, v981);
                LODWORD(v1132) = v1235;
                XlsDiag::SendTraceTag(
                  7091155,
                  187,
                  50,
                  4,
                  L"Check for XML Load Options value: %d prior to displaying business bar",
                  v1132);
                if ( ((v1235 - 1) & 0xFFFFFFFD) != 0 )
                {
                  v983 = 0;
                  if ( (int)sub_14046F680(v978) < 0 )
                  {
                    v984 = FPioldocReadOnly(v978);
                    v983 = (unsigned __int8)FIsTrue<int>(v984) != 0;
                  }
                  v985 = BOOK::Pioldoc(v978);
                  v1178 = MsoFReadWriteOnSaveIoldoc(v985) != 0;
                  if ( !BOOK::FFailedLockTransition(v978)
                    && !AsyncFileLockHandler::FPendingLockTransitionToState(v978, 0)
                    || (*((_DWORD *)v978 + 221) & 0x200) != 0 )
                  {
                    AssistedReading::ResetAssistedReading(v978, 8u, 0);
                  }
                  if ( v983 && Api::Workbook::FHasReadOnlyRecommended((struct BOOK *)((char *)v978 + 1640)) )
                  {
                    v1178 = 0;
                    v986 = BOOK::Pioldoc(v978);
                    MsoSetReadWriteOnSaveIoldoc(v986, 0);
                  }
                }
                FileLoad::ShowVersionFileBusBar(v1165, v978);
                if ( XLSWORKBOOK::Prdsharedmanager((struct BOOK *)((char *)v978 + 1640)) )
                {
                  v987 = XLSWORKBOOK::Prdsharedmanager((struct BOOK *)((char *)v978 + 1640));
                  LinkedEntityFeature = Api::RichDataSharedManager::GetLinkedEntityFeature(v987);
                  if ( Api::LinkedEntityFeature::FShouldShowFinanceBusinessBar(LinkedEntityFeature) )
                  {
                    if ( (unsigned int)FOsrc() )
                    {
                      OsrcSetFEverHadFinanceLinkedEntity(v978);
                    }
                    else
                    {
                      v989 = (RichDataManagerHost *)CastOrNull<XLSWORKBOOK,BOOK>(v978);
                      RichDataManagerHost::FShowFinanceBusinessBar(v989, v990);
                    }
                  }
                }
                v991 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)v978 + 1640));
                CleanupWorkbookStylesBusinessBar::ShowCleanupWorkbookStyleskBusinessBarIfNeeded(v991, v992);
                v977 = v1158;
                goto LABEL_1798;
              }
            }
          }
          else
          {
LABEL_1798:
            v978 = lp;
          }
          v993 = v1313;
          FileLoad::CheckAttemptRepair(
            v978,
            (struct LoadRecovery *)v68,
            v977,
            v1177,
            v1160,
            v1236,
            v1285,
            a10,
            v1313,
            &v1182,
            &v1286,
            &v1269,
            &v1223);
          if ( !v1286 )
          {
            if ( v1269 )
            {
LABEL_1994:
              v1076 = (CorruptionMetaData *)std::_Optional_construct_base<CorruptionMetaData>::operator*(v1543);
              CorruptionMetaData::MarkAsCorrupt(v1076);
              if ( !v68 )
                goto LABEL_2001;
              if ( (unsigned int)OfficeSharedApiImpl::UserFeedbackScreenshotInfo::GetScreenshotSourceType(v68) == -2147418113 )
              {
                v1078 = 459015;
                goto LABEL_2003;
              }
              v1077 = (Mso::History *)(unsigned int)v1182;
              if ( v1182 == -2134188030 || v1182 == -2134142954 )
              {
                v1325 = 256;
                MetroFGetErrorWz(v1182, v1580, &v1325);
                ErrorAlert(459023, v1580);
              }
              else
              {
LABEL_2001:
                if ( !Mso::History::IsVersionCrawlForRepairEnabled(v1077)
                  || (int)FileLoad::HrCheckVersionHistoryRepair(v1165) < 0 )
                {
                  v1078 = 458893;
LABEL_2003:
                  Error(v1078);
                }
              }
LABEL_2038:
              if ( v1158 )
              {
LABEL_2039:
                if ( (a10 & 0x20) != 0 && (unsigned int)FHpshtiFromStt(&v1457, 50) )
                  *((_QWORD *)v1457 + 3) = lp;
              }
              if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                         + 872LL)
                             + 8LL)
                  & 1) == 0
                && v1158
                && lp )
              {
                v1088 = Measurements::Stopwatch::Stopwatch((Measurements::Stopwatch *)v1539);
                LOBYTE(v1089) = 1;
                Measurements::MeasureElapsedTime::MeasureElapsedTime(
                  v1532,
                  Measurements::MeasurementId::ExcelPQEventing,
                  v1089,
                  v1088);
                v1090 = (struct Api::Workbook *)CastOrNull<XLSWORKBOOK,BOOK>(lp);
                XLSEVENTDISPATCHER::HrOnWorkbookOpen(v1090);
                v1211 = 0;
                if ( PowerQueryManager::FPowerQueryIEVersionCheckFailed() )
                {
                  Manager = Api::Workbook::PPowerQueryManager((struct BOOK *)((char *)lp + 1640));
                  if ( (*(int (__fastcall **)(struct IPowerQueryWorkbookManager *, char *))(*(_QWORD *)Manager + 224LL))(
                         Manager,
                         &v1211) >= 0 )
                  {
                    if ( v1211 )
                    {
                      v1092 = BOOK::Pioldoc(*(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                 + 304LL)
                                                     + 40LL));
                      ShowPowerQueryIEBusBar(v1092);
                    }
                  }
                }
                Measurements::MeasureElapsedTime::~MeasureElapsedTime((Measurements::MeasureElapsedTime *)v1532);
                v1093 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL);
                if ( *(_DWORD *)(v1093 + 104) == 1 )
                {
                  *((_DWORD *)lp + 644) |= 0x20u;
                }
                else if ( *(_DWORD *)(v1093 + 104) == 2 )
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
                    v1094 = IdwaFromIds(458968);
                    MsoDoWatsonAlertBegin(v1094, 0, 0, (struct WADD *)v1552);
                  }
                  v1095 = v1190 & 4;
                  if ( (a10 & 0x20) != 0 || (v1096 = FOsrhInTransition(), v1097 = 0, v1096) )
                    v1097 = 1;
                  v1098 = XlUIMockable::HrShowRecoveryErrors2(lp, v1097, v1095, 0);
                  v606 = v1098;
                  if ( (_BYTE)v264 )
                  {
                    if ( v1098 < 0 )
                    {
LABEL_1742:
                      v1171 = v606;
                      goto LABEL_1133;
                    }
                  }
                  else if ( v1098 < 0 )
                  {
                    v805 = 512506015;
                    v806 = (MsoReserveTag *)&v1367;
                    goto LABEL_1925;
                  }
                  if ( *((char *)lp + 892) >= 0 )
                  {
                    std::optional<EditCommandTrackingFreezer>::optional<EditCommandTrackingFreezer>(v1246);
                    v1099 = FeatureGateCollectionBase<CoauthFeatureGates>::Instance();
                    if ( (unsigned __int8)Mso::AB::Optimized::FeatureGate::operator bool(v1099 + 408) )
                      std::optional<EditCommandTrackingFreezer>::emplace<>(v1246);
                    v1100 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1368, 0x231C69Fu);
                    v1101 = SXVWGEOM::RwFirst(v1100);
                    BookDirty(lp, 1, v1101);
                    std::optional<EditCommandTrackingFreezer>::~optional<EditCommandTrackingFreezer>(v1246);
                  }
                  if ( *((_QWORD *)lp + 162) )
                    MsoDoWatsonAlertEnd((struct WADD *)v1552, *((const wchar_t **)lp + 163));
                }
                v1102 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                v1103 = *(_QWORD *)(v1102 + 872);
                if ( *(_DWORD *)(v1103 + 104) != 1 && (*(_BYTE *)(v1103 + 8) & 1) == 0 )
                {
                  v1104 = *(_QWORD *)(v1102 + 1328);
                  if ( *(_DWORD *)(v1104 + 20) )
                  {
                    Sz = 0;
                    if ( wverLastXLSaved < 3 || *(char *)(v1104 + 20) < 0 )
                      Sz = CchLoadSz(v1576, 327873, 256);
                    v1106 = CchLoadSz(&v1576[Sz], 327874, 256 - Sz);
                    v1107 = (__int64 *)NtCurrentTeb()->ThreadLocalStoragePointer;
                    v1108 = v1106 + Sz;
                    v541 = *v1107;
                    v1109 = *(_QWORD *)(*(_QWORD *)(*v1107 + 304) + 1328LL);
                    if ( (*(_DWORD *)(v1109 + 20) & 0x10) == 0 && *(char *)(v1109 + 20) >= 0 )
                      goto LABEL_2080;
                    v1110 = -1161035032;
                    *(_DWORD *)(v1109 + 20) &= (*(_DWORD *)(v1109 + 20) & 0x10) != 0 ? -17 : -129;
                    while ( 1 )
                    {
                      v1108 += CchLoadSz(&v1576[v1108], v1110, 256 - v1108);
LABEL_2080:
                      v1111 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                        + 1328LL);
                      v1112 = *(_DWORD *)(v1111 + 20);
                      if ( (v1112 & 0x20) != 0 )
                      {
                        v1110 = -1161035031;
                        v1113 = v1112 & 0xFFFFFFDF;
                      }
                      else
                      {
                        if ( (v1112 & 0x40) == 0 )
                        {
                          v542 = 512;
                          if ( (unsigned __int64)(2LL * v1108) < 0x200 )
                          {
                            v1576[v1108] = 0;
                            ShowAlert(10, 458968, v1576, 0, 0, 0);
                            goto LABEL_1954;
                          }
LABEL_2137:
                          _report_rangecheckfailure(v542, v541, v539);
                        }
                        v1110 = -1161035030;
                        v1113 = v1112 & 0xFFFFFFBF;
                      }
                      *(_DWORD *)(v1111 + 20) = v1113;
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
                && !v1158 )
              {
                v1079 = v1182;
                if ( v1182 == -2147023673 || v1182 == -2147467260 || *(&vscd + 1) )
                {
                  if ( *(&vscd + 1) )
                  {
                    v114 = -2147467260;
                    v1080 = 33931969;
                    v1079 = -2147467260;
                    goto LABEL_2015;
                  }
                  v114 = v1182;
                  if ( v1182 < 0 )
                  {
                    v1080 = 33931970;
LABEL_2015:
                    XlsDiag::LogSetHrCoreTag(v1079, v1080);
                  }
                  v1081 = 0;
                  v1082 = 458924;
LABEL_2028:
                  OkAlert(v1082, v1081);
                  goto LABEL_2038;
                }
              }
              if ( *((char *)PivotOperationBase::PSxview((PivotOperationBase *)v68) + 36) < 0 )
              {
                if ( v1158 )
                {
                  AffectedProcessSessionId = (ODFROBUSTLOAD *)OfficeSharedApiImpl::UserFeedbackV2Config::GetAffectedProcessSessionId(v68);
                  if ( ODFROBUSTLOAD::FRepairAlertDisplayed(AffectedProcessSessionId) )
                  {
                    CchLoadSz(v1582, -1161035131, 255);
                    v1084 = v1582;
                    v1085 = 467262;
                    goto LABEL_2037;
                  }
                  if ( v1158 )
                    goto LABEL_2039;
                }
                v1086 = (ODFROBUSTLOAD *)OfficeSharedApiImpl::UserFeedbackV2Config::GetAffectedProcessSessionId(v68);
                if ( ODFROBUSTLOAD::FPasswordHashFound(v1086) )
                {
                  v114 = -2147467260;
                  XlsDiag::LogSetHrCoreTag(-2147467260, 0x205C2C3u);
                  v1082 = 459071;
                }
                else
                {
                  if ( v1158 )
                    goto LABEL_2039;
                  v1087 = (ODFROBUSTLOAD *)OfficeSharedApiImpl::UserFeedbackV2Config::GetAffectedProcessSessionId(v68);
                  if ( !ODFROBUSTLOAD::FBadNullDate(v1087) )
                    goto LABEL_2038;
                  v114 = -2147467260;
                  XlsDiag::LogSetHrCoreTag(-2147467260, 0x205C2C4u);
                  v1082 = 459072;
                }
                v1081 = v1573;
                goto LABEL_2028;
              }
            }
            if ( !v1192
              || !(unsigned int)Mso::Details::ConstexprFunctorBase<Mso::IFunctor<bool,FeaturePropertyValue const &,FeaturePropertyValue const &>>::Release(&vapp)
              || (unsigned int)FOsrhInTransition()
              || (unsigned int)FOsrc() )
            {
              goto LABEL_2038;
            }
            CchSzToSt(*((const wchar_t **)v1347 + 3), v1579, 255);
            SuppressStExt(v1579, 255);
            if ( v1158 )
            {
              CchInsert2St(v1578, 459073, &v1572, v1579, 255);
              v1085 = 467265;
            }
            else
            {
              v114 = -2146827284;
              XlsDiag::LogSetHrCoreTag(-2146827284, 0x205C2C5u);
              CchInsert2St(v1578, 459075, &v1572, v1579, 255);
              v1085 = 467267;
            }
            v1084 = v1578;
LABEL_2037:
            OkInfoAlert(v1085, v1084);
            goto LABEL_2038;
          }
          if ( v1269 )
            goto LABEL_1994;
          if ( v1177 && !(unsigned int)FOsrcHostedByExcel() )
          {
            SetLoadForPreviewError(-2042494972);
            v1223 = 0;
            v1167 = 0;
            goto LABEL_1826;
          }
          if ( !v1223 )
          {
            v994 = FOsrhInTransition();
            v1167 = FIsTrue<int>(v994);
            if ( v1167 || (unsigned __int8)CircularReferenceTailValue::FGetFlagsShadowBag(&vapp) || (v995 = 0, v1164) )
              v995 = 1;
            v1167 = v995;
            if ( !v995 )
            {
              if ( v1245 && !MsoFDrmUIEnabled() )
              {
                Error(589882);
                goto LABEL_1826;
              }
              if ( (unsigned int)FOsrc() )
              {
                Osrc = GetOsrc();
                v997 = OSRC::DwPromptUser(Osrc, 0, 0, 0, 0, 0);
                v1167 = v997 != 0;
                if ( !v997 )
                  SetLoadForPreviewError(-2147467260);
                goto LABEL_1826;
              }
              if ( v1278 && VersionHistoryWindowParams::FSkipCorruptVersionOpens(v1278) )
              {
                v998 = 504443348;
LABEL_1822:
                v114 = -2146827284;
                XlsDiag::LogSetHrCoreTag(-2146827284, v998);
                v993 = v1313;
                goto LABEL_1826;
              }
              if ( (unsigned int)Art::IOMHost::GetEnvId((Art::IOMHost *)&vapp) )
              {
                if ( (unsigned int)YesNoAlert(458912, v1573) != 6 )
                {
                  v114 = -2146827284;
                  XlsDiag::LogSetHrCoreTag(-2146827284, 0x230E208u);
                  goto LABEL_1826;
                }
              }
              else if ( (unsigned int)XlUIMockable::NoYesAlert(458912, v1573) != 6 )
              {
                v998 = 36758023;
                goto LABEL_1822;
              }
              v1167 = 1;
            }
          }
LABEL_1826:
          v999 = (CorruptionMetaData *)std::_Optional_construct_base<CorruptionMetaData>::operator*(v1543);
          CorruptionMetaData::MarkAsCorrupt(v999);
          if ( !v1223 && !v1167 )
            goto LABEL_2038;
          if ( v1236 || (*((_BYTE *)PivotOperationBase::PSxview((PivotOperationBase *)v68) + 36) & 2) != 0 )
          {
            BookCorrupt = LoadRecovery::GrbitGetBookCorrupt((LoadRecovery *)v68);
            v1007 = PivotMetadataCache::PvMemProps((PivotMetadataCache *)v68);
            LoadRecovery::HrHandleLoadMode((LoadRecovery *)v68, v1007 == (void *)BookCorrupt);
            LoadRecovery::HrHandleLoadMode((LoadRecovery *)v68, v1236);
            v1008 = LoadRecovery::GrbitGetBookCorrupt((LoadRecovery *)v68);
            LoadRecovery::GrbitSetBookCorruptOld((LoadRecovery *)v68, v1008);
          }
          else
          {
            if ( !v68 || (v44 = (int)LoadRecovery::Lrmode(v68) <= 0, v1000 = 1, v44) )
              v1000 = 0;
            v1001 = (LoadRecovery *)v68;
            if ( v1000 )
            {
              LoadRecovery::IncrementRepairAttemptCount((LoadRecovery *)v68);
              if ( LoadRecovery::CGetPartCount((LoadRecovery *)v68) < v993 )
              {
                v1002 = 1;
                v1001 = (LoadRecovery *)v68;
                goto LABEL_1844;
              }
              if ( v993 )
              {
                if ( LoadRecovery::CGetPartCount((LoadRecovery *)v68) == v993 )
                {
                  v1003 = LoadRecovery::CGetIRTCount((LoadRecovery *)v68);
                  if ( v1003 <= v1346 )
                  {
                    v1004 = v993 - 1;
                    v1005 = LoadRecovery::FNoProgressOnPart((LoadRecovery *)v68, v1004);
                    v1001 = (LoadRecovery *)v68;
                    if ( v1005 )
                    {
                      v1002 = 1;
                      goto LABEL_1844;
                    }
                    if ( !LoadRecovery::FCorruptPart((LoadRecovery *)v68, v1004) )
                    {
                      LoadRecovery::SetCorruptPart((LoadRecovery *)v68, v1004);
                      LoadRecovery::SetFNoProgressOnPart((LoadRecovery *)v68, v1004);
                    }
                  }
                }
              }
            }
            else
            {
              v1002 = 0;
LABEL_1844:
              LoadRecovery::HrHandleLoadMode(v1001, v1002);
            }
            v1346 = LoadRecovery::CGetIRTCount((LoadRecovery *)v68);
            v1313 = LoadRecovery::CGetPartCount((LoadRecovery *)v68);
          }
          ClearStatusString(11);
          if ( (unsigned int)LoadRecovery::Lrmode(v68) == 1 )
          {
            if ( !v1223 )
            {
              v1009 = 1752853862;
              goto LABEL_1851;
            }
          }
          else
          {
            v1009 = 1752853863;
LABEL_1851:
            MsoShipAssertTagProc(v1009);
            v1223 = 1;
          }
          if ( v1164 )
            goto LABEL_744;
          v1010 = LoadRecovery::Lrmode(v68);
          SetLoadRecovery(v1010);
          v1011 = MaxPathHolder::CchMaxPath();
          v1012 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1467);
          v1013 = v1011;
          v69 = v1165;
          CchStToSt(v1012, v1165, v1013);
          v1274 = 0;
          sub_1402DA5D0(&v1546, v1338, v1014);
          goto LABEL_745;
        }
        OsfOpenScope::OpenCompleted((OsfOpenScope *)v1490);
        v1191 = 0;
        (*(void (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1162 + 8LL))(v1162);
        v953 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
        v954 = XlAsyncFileIO::PxlasyncFileIOFromWorkbook(v953);
        if ( v954 )
          XlAsyncFileIO::NotifyWorkbookInClose(v954, 1);
        v955 = FeatureGateCollectionBase<CoauthFeatureGates>::Instance();
        if ( (unsigned __int8)Mso::AB::Optimized::FeatureGate::operator bool(v955 + 472) )
          BOOK::SetFCloseForReopen(lp, 1);
        v956 = HrFreeBook2(lp);
        v606 = v956;
        if ( (_BYTE)v264 )
        {
          if ( v956 < 0 )
            goto LABEL_1742;
        }
        else if ( v956 < 0 )
        {
          v805 = 512506016;
          v806 = (MsoReserveTag *)&v1364;
          goto LABEL_1925;
        }
        lp = 0;
        if ( v1209 )
          (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v1162 + 56LL))(v1162, 1, 7);
        v957 = v1176 != 0;
        v1176 = -v1176;
        FBeginCmdIOLDoc(v1162, v957 ? 4 : 2, 0, &v1237, 0);
        if ( v1251 )
        {
          (*(void (__fastcall **)(struct IMsoPKMClient *))(*(_QWORD *)v1251 + 184LL))(v1251);
          v1251 = 0;
        }
        sub_1402DA5D0(&v1546, v1338, v958);
        XlsActivity::ResetStoredTagData(v1218);
LABEL_744:
        v69 = v1165;
LABEL_745:
        if ( v1164 && (v1160 || v1167) )
        {
          if ( v1162 )
          {
            if ( v1183 )
              HrRecordEvent(v1162, 0x40000000u, 0);
            if ( *v407 )
            {
              v1061 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1366, 0x23696299u);
              v1062 = SXVWGEOM::RwFirst(v1061);
              OlDocFilePath::FReleaseIOLDoc(v407, 1, 1, v1062);
            }
          }
          Mso::TCntPtr<IOfficeSolutionFramework>::TCntPtr<IOfficeSolutionFramework>(v1315);
          v1063 = MaxPathHolder::SzPath((MaxPathHolder *)v1467);
          v1064 = MsoPIOLDocFindWithWzPersistentName(v1063);
          Mso::TCntPtr<IMsoOLDocument>::Attach(v1315, v1064);
          if ( (unsigned __int8)std::shared_ptr<Mso::ActivityScope::IMsoLoggingScope>::operator bool(v1315) )
          {
            v1066 = BKORWS::Psh((BKORWS *)v1315);
            ZrtUtility::OptOutOfServerOnlyAsyncOpen(v1066, v1067);
          }
          if ( v1160 )
            XslClear((struct XSL *)&v1546);
          LOBYTE(v1065) = std::nullopt;
          if ( !(unsigned __int8)sub_14240D208(v1529, v1065) )
          {
            v1068 = sub_14240D3DC(v1529);
            sub_141837FB8(v1068);
          }
          v114 = -1491861503;
          v1158 = -1491861503;
          XlsDiag::LogSetHrCoreTag(-1491861503, 0x300B394u);
          Mso::TCntPtr<Uxpp::UxppAnnotationsService>::~TCntPtr<Uxpp::UxppAnnotationsService>(v1315);
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
                v1069 = (CorruptionMetaData *)std::_Optional_construct_base<CorruptionMetaData>::operator*(v1543);
                CorruptionMetaData::MarkAsCorrupt(v1069);
                Error(327845);
              }
              LoadRecovery::Destroy((LoadRecovery *)v68);
              FreeHpst(v68);
              v68 = 0;
              v1238 = 0;
            }
          }
          if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                         + 8LL)
              & 1) == 0
            && v1158
            && lp
            && !(unsigned int)FBookAddin(lp)
            && (*((_DWORD *)lp + 222) & 0x804000) == 0
            && (a10 & 0x20) == 0
            && (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 864LL)
                          + 24LL)
              & 0x40000) == 0
            && !v1177 )
          {
            XLDRPPERS::XLDRPPERS((XLDRPPERS *)v1568);
            memset_0(v1568, 0, 0x308u);
            v1070 = Api::Workbook::FtFileType((char *)lp + 1640);
            v1071 = 1;
            LOBYTE(v1136) = 0;
            LOBYTE(v1134) = 1;
            v1568[0] = (2 * v1070) | v1568[0] & 0xFFFFFE01;
            if ( v1160 )
              v1071 = 65537;
            if ( (unsigned int)FSaveRecoveryDrp(lp, 0, 0, v1071, 1, v1568, 0, v1134, v1136) )
              *((_DWORD *)lp + 320) = 1;
          }
          if ( lp )
            *((_DWORD *)lp + 222) &= ~0x800000u;
          if ( v1179
            && (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                         + 8LL)
              & 1) == 0
            && v1158
            && lp
            && (v1199 == 5 || v1199 == 16)
            && !v1177 )
          {
            FileLoad::CheckShared(lp);
          }
          v1072 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          if ( (*(_BYTE *)(*(_QWORD *)(v1072 + 872) + 8LL) & 1) == 0 && v1158 && lp && !v1177 )
          {
            if ( !*(_DWORD *)(*(_QWORD *)(v1072 + 1232) + 80LL) && !(unsigned int)FOsrhBook(lp) )
              v73 = 0;
            v1073 = BOOK::Pioldoc(lp);
            MsoHrSimpleOfflineOpenFile(
              v1073,
              (int (__high *)(enum MSOSCA, struct IMsoOLDocument *, unsigned int))&HrSimpleOfflineUser,
              v73);
          }
          ResetLoadRecovery();
          v1074 = lp;
          if ( lp )
          {
            FShowTrustBar(lp);
            *((_DWORD *)lp + 222) &= ~0x8000000u;
            v1074 = lp;
          }
          v1075 = HrFileCompleteLoadEx(
                    v1165,
                    hObject,
                    v1158,
                    v1187,
                    v1074,
                    v1181,
                    v1170,
                    (struct LoadRecovery *)v68,
                    v1305,
                    v1225,
                    v1200 != 0,
                    v1251,
                    v1256,
                    v1164,
                    v1162,
                    v1275,
                    v1307,
                    v1186,
                    v114,
                    (const struct MaxPathHolder *)v1345,
                    v1180,
                    v1259,
                    (struct OsfOpenScope *)v1490,
                    (const struct XLOSRR *)&v1240,
                    v1339);
          goto LABEL_1992;
        }
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1225;
        FRemoveLoadAction((struct LoadRecovery *)v68, 0);
        XlsActivity::SetSuccessful(v1218);
        std::_Optional_destruct_base<CorruptionMetaData,0>::~_Optional_destruct_base<CorruptionMetaData,0>(v1543);
        v1455[0] = APPCORE::PmemheapMain((APPCORE *)&vapp);
        std::optional<CorruptionMetaData>::emplace<IMemHeap *>(v1543, v1455);
        v1455[1] = BKORWS::Psh(v1279);
        std::optional<OlDocFilePath>::emplace<QuickLoadContext *>((OlDocFilePath *)v1544);
        ++v1276;
        v408 = (__int64 *)NtCurrentTeb()->ThreadLocalStoragePointer;
        v60 = v1303;
        v1158 = 0;
        v1199 = 256;
        v1228 = 0;
        lp = 0;
        v1237 = 0;
        v409 = *v408;
        v1174 = 0;
        v1302 = 0;
        v1273 = 0;
        v410 = *(_QWORD *)(v409 + 304);
        v1280 = 0;
        v1336 = 0;
        v1193 = 0;
        v411 = *(_QWORD *)(v410 + 1304);
        v1168 = 0;
        v1169 = 0;
        *(_WORD *)(v411 + 56) &= ~8u;
        if ( v1256 )
        {
          (*(void (__fastcall **)(struct IMsoDocumentEncryptor *))(*(_QWORD *)v1256 + 16LL))(v1256);
          v1256 = 0;
        }
        goto LABEL_79;
      }
LABEL_1105:
      errDeferred = 0;
      v591 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
      if ( *(_QWORD *)(v591 + 40) && (*(_DWORD *)(*(_QWORD *)(v591 + 40) + 884LL) & 0x200) != 0 )
      {
        RenumberWind(*(struct SH **)(v591 + 32));
        v592 = v1302;
        v593 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        *(_DWORD *)(v593 + 2024) = 0;
        *(_DWORD *)(v593 + 2028) = 0;
        v594 = *(const struct BOOK **)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        *((_QWORD *)v594 + 42) = v1225;
        LOBYTE(v264) = 0;
        goto LABEL_1549;
      }
      if ( v1158 != 2 )
      {
LABEL_1360:
        v725 = v1159;
        v407 = v1166;
        goto LABEL_1361;
      }
      if ( *(_DWORD *)(*(_QWORD *)(v591 + 872) + 104LL) == 2 )
      {
        if ( OSRR::FOsrCandidate((OSRR *)&v1240) )
        {
          OSRR::SetAppReady((OSRR *)&v1240, 1);
LABEL_764:
          v1160 = 1;
          goto LABEL_743;
        }
        v595 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1344);
        v596 = HrLoadDataRecover(v1172, v264, &v1572, 257, v595, a5, 0, v1190, (struct LoadRecovery *)v68);
        v1157 = v596;
        v114 = v596;
        if ( v596 < 0 )
          XlsDiag::LogSetHrCoreTag(v596, 0x2156755u);
        v597 = v1159;
        v1158 = v114 >= 0;
        if ( v1159 )
        {
          if ( (unsigned int)IMsoOLDocument::IsInFileSys(v1162) )
          {
            if ( v1158
              || (v598 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL),
                  *(_QWORD *)(v598 + 40))
              && (*(_DWORD *)(*(_QWORD *)(v598 + 40) + 884LL) & 0x200) != 0 )
            {
              v599 = (wchar_t **)XLSBOOK::Plxtab(*(XLSBOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                         + 304LL)
                                                             + 40LL));
              FreeHpstTempPath((struct STB *)v599, v600);
              v601 = FileSource::StzFilePath((FileSource *)v1310);
              if ( (int)HrStDupSt(v601, v599 + 21) < 0 )
                v599[21] = 0;
            }
          }
        }
        v1220 = 0;
LABEL_1272:
        if ( v1158 )
          v1199 = 5;
        if ( v1547 )
        {
          if ( v1162 )
          {
            (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v1162 + 56LL))(
              v1162,
              0xFFFFFFFFLL,
              7);
            if ( v1183 )
              HrRecordEvent(v1162, 0x40000000u, 0);
            v670 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1416, 0x2369629Eu);
            v671 = SXVWGEOM::RwFirst(v670);
            OlDocFilePath::FReleaseIOLDoc(v1166, 1, v1158 == 0, v671);
          }
          v672 = v1304;
          v1183 = v1194;
          v1162 = v1304;
        }
        else
        {
          v672 = v1162;
        }
        if ( v1244 == -2 )
        {
          v68 = v1163;
          goto LABEL_1360;
        }
        v707 = 0;
        v708 = 0;
        v709 = 0;
        v710 = 0;
        if ( v1183 )
        {
          v707 = 0;
          if ( !v1158 )
          {
            v711 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
            if ( !*(_QWORD *)(v711 + 40) || (*(_DWORD *)(*(_QWORD *)(v711 + 40) + 884LL) & 0x200) == 0 )
              v707 = 1;
          }
          HrRecordEvent(v672, 0x40000000u, !v707);
          v708 = v707;
          v1183 = 0;
          v710 = v707;
          v709 = v707;
        }
        v712 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        if ( *(_QWORD *)(v712 + 40) != v1306 )
        {
          v707 = v708;
          v709 = v710;
          if ( v1158 )
          {
            if ( *(_QWORD *)(v712 + 40) )
            {
              if ( v1265 )
              {
                v713 = OLDocFactory::PInstance();
                v1222 = (*(__int64 (__fastcall **)(const struct OLDocFactory *, _QWORD, struct IMsoOLDocument **))(*(_QWORD *)v713 + 56LL))(
                          v713,
                          0,
                          &v1351);
                v1222 = (*(__int64 (__fastcall **)(struct IMsoOLDocument *, __int64, _QWORD))(*(_QWORD *)v1162 + 96LL))(
                          v1162,
                          8,
                          0);
                v1222 = (*(__int64 (__fastcall **)(struct IMsoOLDocument *, __int64, _QWORD, _QWORD))(*(_QWORD *)v1162 + 112LL))(
                          v1162,
                          0x40000000,
                          0,
                          0);
                v1222 = (*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1162 + 16LL))(v1162);
                *v1166 = v1351;
                v1162 = v1351;
              }
              v714 = *(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL);
              v715 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1417, 0x2369629Cu);
              v716 = SXVWGEOM::RwFirst(v715);
              BOOK::SetPioldoc(v714, v1162, v716);
              LOBYTE(v717) = 1;
              if ( (unsigned __int8)FeatureExposure::FRunLicensedFeature(v717) )
              {
                v718 = NtCurrentTeb()->ThreadLocalStoragePointer;
                v1309 = -1;
                v719 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v718 + 304LL) + 32LL);
                v720 = 0;
                if ( (*(_BYTE *)(v719 + 10) & 4) == 0 )
                  v720 = *(_BYTE *)(v719 + 8);
                v721 = FtDefault(v720);
                if ( (unsigned __int8)FShouldShowDataLossBusBar(v721, &v1309) )
                  ShowDataLossBusBarIfNeeded(
                    *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL),
                    v1309);
              }
            }
            v68 = v1163;
            goto LABEL_1360;
          }
        }
        v407 = v1166;
        _IMsoOLDocument_SetIReDownload(*v1166, -1);
        v722 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1418, 0x2369629Du);
        v723 = SXVWGEOM::RwFirst(v722);
        if ( v1158 )
        {
          v724 = 0;
          v707 = v709;
        }
        else
        {
          v724 = 1;
        }
        OlDocFilePath::FReleaseIOLDoc(v407, !v707, v724, v723);
        if ( v597 )
          *v407 = 0;
        v68 = v1163;
        v725 = 0;
        v1159 = 0;
LABEL_1361:
        v726 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1184);
        v727 = (LXBASE *)OpenTelemetry::POpenFileStageModel(v726);
        v728 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1419, 0x1F0CB5C2u);
        SXVWGEOM::RwFirst(v728);
        WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v727);
        v729 = FeatureGateCollectionBase<CoauthFeatureGates>::Instance();
        if ( !(unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(v729 + 1680) || v1158 )
          lp = *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL);
        v730 = NtCurrentTeb()->ThreadLocalStoragePointer;
        vhpstErrPath = 0;
        v731 = *(_QWORD *)(*(_QWORD *)v730 + 304LL);
        *(_DWORD *)(v731 + 2024) = 0;
        *(_DWORD *)(v731 + 2028) = 0;
        v1207 = 0;
        v732 = sub_1404303D0(lp);
        v733 = v1156;
        v606 = v732;
        if ( v1156 )
        {
          if ( v732 < 0 )
          {
LABEL_1132:
            v1171 = v606;
            goto LABEL_1133;
          }
        }
        else if ( v732 < 0 )
        {
          v805 = 512506050;
          v806 = (MsoReserveTag *)&v1370;
          goto LABEL_1925;
        }
        if ( v1207 )
        {
          lp = 0;
          v73 = 1;
          goto LABEL_744;
        }
        if ( v725 )
        {
          sub_14046D500(v1162);
          if ( Mso::DocumentWindow::EventMgr::IsDocumentWindowEventManagerEnabled(v734) )
            sub_1404318C0(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL));
        }
        if ( v1158 )
        {
          if ( lp )
          {
            v735 = (WN *)*((_QWORD *)lp + 53);
            if ( v735 )
            {
              v736 = WN::Puiframe(v735);
              v737 = (struct IMsoOLDocument *)UIFRAME::HwndFrame(v736);
              v738 = BOOK::Pioldoc(lp);
              Excel::XlMso::EmitOpenEventForOLDocument(v738, v737, v739);
            }
          }
          if ( v1158 )
          {
            if ( lp )
            {
              if ( !v1200 )
              {
                if ( BOOK::Pioldoc(lp) )
                {
                  v740 = BOOK::Pioldoc(lp);
                  if ( v1162 == v740 && !(unsigned int)FIsLocalVersionXL(v1165) )
                  {
                    v741 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
                    v742 = Api::Workbook::FtFileType((char *)lp + 1640);
                    if ( (unsigned __int8)CoauthUtil::FValidXluidLoadedFt(v742, v741) )
                      XLSWORKBOOK::SetFValidUidStateLoaded((struct BOOK *)((char *)lp + 1640), 1);
                    if ( !XLSWORKBOOK::FValidUidStateLoaded((struct BOOK *)((char *)lp + 1640)) )
                    {
                      v743 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
                      CoauthUtil::CreateValidUidStateOnLoad(v743);
                    }
                    if ( v1173 )
                    {
                      Protocol = XlFileProtocolManager::GetProtocol(v1162);
                      if ( !Protocol )
                      {
                        MsoShipAssertTagProc(506056966);
                        v1048 = 506056965;
                        v606 = -2147418113;
                        goto LABEL_2135;
                      }
                      v745 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1420, 0x1E1968DCu);
                      XlFileProtocol::TakeZipItScheduler(Protocol, v1352, *(unsigned int *)v745);
                      v746 = lp;
                      v747 = *(_DWORD *)MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1421, 0x1E1968DBu);
                      v748 = BKORWS::Psh((BKORWS *)v1352);
                      XLSWORKBOOK::SetZipItScheduler((char *)v746 + 1640, v748, v747);
                      Mso::TCntPtr<IWebAddInOptionalProperties>::~TCntPtr<IWebAddInOptionalProperties>(v1352);
                    }
                    v749 = FeatureGateCollectionBase<CoauthFeatureGates>::Instance();
                    if ( (unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(v749 + 1264) )
                    {
                      LOBYTE(v750) = std::nullopt;
                      if ( !(unsigned __int8)std::operator==<CoauthoringInternals::RecoveredFileCoauthorableState>(
                                               &CoauthoringInternals::s_optRecoveredFileCoauthorableState,
                                               v750) )
                      {
                        v751 = (_DWORD *)std::optional<CoauthoringInternals::RecoveredFileCoauthorableState>::operator->(&CoauthoringInternals::s_optRecoveredFileCoauthorableState);
                        *((_DWORD *)lp + 320) = *v751;
                        v752 = std::optional<CoauthoringInternals::RecoveredFileCoauthorableState>::operator->(&CoauthoringInternals::s_optRecoveredFileCoauthorableState);
                        *((_QWORD *)lp + 161) = *(_QWORD *)(v752 + 8);
                      }
                    }
                    BOOKO::UpdateCoauth((struct BOOK *)((char *)lp + 1640), 1);
                    v753 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
                    v754 = XlAsyncFileIO::PxlasyncFileIOFromWorkbook(v753);
                    if ( v754 )
                    {
                      v755 = XlAsyncFileIO::Pxlrh(v754);
                      XlRenameHandler::HrCheckForRenameOnFileLoad(v755);
                    }
                    v756 = 0;
                    if ( (unsigned __int8)std::shared_ptr<Mso::ActivityScope::IMsoLoggingScope>::operator bool(&v1257) )
                    {
                      v757 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1257);
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v757 + 48LL))(v757);
                      v758 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1257);
                      v756 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v758 + 128LL))(v758, 0);
                    }
                    v759 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
                    v760 = IMerge::PMergeFromWorkbook(v759);
                    if ( v760 )
                    {
                      v761 = (*(__int64 (__fastcall **)(struct IMerge *))(*(_QWORD *)v760 + 216LL))(v760);
                      v762 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v761 + 288LL))(v761);
                      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v762 + 48LL))(v762, v756);
                    }
                    v1333 = 0;
                    v763 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
                    Api::ReloadContext::RetrieveRctxFromWorkbook(v763, &v1333);
                    if ( v1333 && Api::ReloadContext::FValid(v1333) )
                    {
                      v1186 = 1;
                      v764 = Mso::Telemetry::Activity::DataFields(v1218);
                      refreshed = Api::ReloadContext::RefreshType(v1333);
                      v766 = Api::ReloadContext::SzFromBookRefreshType(refreshed);
                      Mso::Telemetry::IDataFieldCollection::Add(v764, "RefreshType", v766, 4);
                    }
                    if ( BKORWS::Psh((struct BOOK *)((char *)lp + 3088)) )
                    {
                      v767 = BKORWS::Psh((struct BOOK *)((char *)lp + 3088));
                      IEndpointAgent::HrLoadComplete(v767);
                    }
                    v768 = XLSWORKBOOK::ClpManager((struct BOOK *)((char *)lp + 1640));
                    ClassifyLabelProtectManager::OnLoadComplete(v768);
                    if ( IdleLoop::FEnabled(v769) )
                    {
                      v770 = FeatureGateCollectionBase<PerformanceFeatureGates>::Instance();
                      if ( (unsigned __int8)Mso::AB::Optimized::FeatureGate::operator bool(v770 + 416) )
                        UpdateCLPLabelIndicator(lp);
                    }
                    v771 = APPCORE::PautoSaveManager((APPCORE *)&vapp);
                    AutoSaveManager::SetAutoSaveStatusOnFileLoad(v771, lp);
                    Copilot::EvaluatePrerequisitesForBook((struct BOOK *)((char *)lp + 1640), v772);
                  }
                }
              }
            }
          }
        }
        if ( v1175 )
          ApplyRevert(v1274, (const struct REVARG *)v1570, v1158);
        v1274 = 0;
        v773 = HrEnsureChartSheetsAreNonBlank(lp, 1);
        v606 = v773;
        if ( v1156 )
        {
          if ( v773 < 0 )
          {
            v1171 = v773;
            goto LABEL_1133;
          }
        }
        else if ( v773 < 0 )
        {
          v805 = 512506049;
          v806 = (MsoReserveTag *)&v1369;
          goto LABEL_1925;
        }
        if ( fShowWn )
        {
          v592 = *(SH **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 32LL);
          v1302 = v592;
          v774 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1422, 0x2375A797u);
          v775 = SXVWGEOM::RwFirst(v774);
          v776 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          if ( *(_QWORD *)(v776 + 104) )
            v777 = *(struct SH **)(*(_QWORD *)(v776 + 104) + 24LL);
          else
            v777 = 0;
          v778 = *(_QWORD **)(v776 + 128);
          v779 = 0;
          if ( v778 )
          {
            v780 = v778;
            do
            {
              v779 = v780[1];
              if ( v779 )
                break;
              v778 = (_QWORD *)*v778;
              v780 = v778;
            }
            while ( v778 );
          }
          LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v779 + 96), v777, v775);
        }
        else
        {
          v592 = v1302;
        }
        v781 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        v782 = *(struct WNX **)(v781 + 344);
        if ( v782 )
        {
          v783 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v784 = *(struct WNX **)(v781 + 344);
          v785 = v782;
          v786 = v782;
          do
          {
            v787 = *((_DWORD *)v784 + 2);
            if ( v787 == 2 )
            {
              if ( (*(_WORD *)(CastOrNull<CS,SH>(*((_QWORD *)v785 + 3), v786) + 424) & 0x200) != 0 )
              {
                v788 = *(struct SH **)(*(_QWORD *)(*(_QWORD *)v783 + 304LL) + 32LL);
                v789 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1423, 0x237630D7u);
                v790 = SXVWGEOM::RwFirst(v789);
                v791 = *(_QWORD *)(*(_QWORD *)v783 + 304LL);
                v792 = 0;
                v793 = *(_QWORD **)(v791 + 128);
                if ( v793 )
                {
                  v794 = *(_QWORD **)(v791 + 128);
                  do
                  {
                    v792 = v794[1];
                    if ( v792 )
                      break;
                    v793 = (_QWORD *)*v793;
                    v794 = v793;
                  }
                  while ( v793 );
                }
                LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v792 + 96), *((struct SH **)v785 + 3), v790);
                if ( SbFromHpCore(*(const void **)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v783 + 304LL) + 48LL) + 13280LL)) )
                {
                  v606 = HrRecalcCho(0);
                  if ( v1156 )
                  {
                    if ( v606 < 0 )
                      goto LABEL_1185;
                  }
                  else if ( v606 < 0 )
                  {
                    v805 = 512506048;
                    v806 = (MsoReserveTag *)&v1360;
                    goto LABEL_1925;
                  }
                }
                v796 = *(_QWORD *)(*(_QWORD *)v783 + 304LL);
                if ( *(_QWORD *)(v796 + 40) )
                {
                  v797 = *(_QWORD *)(v796 + 40);
                  v795 = 2048;
                  if ( (*(_WORD *)(v797 + 482) & 0x800) != 0 )
                  {
                    if ( *(_QWORD *)(v797 + 528) )
                      *(_WORD *)(*(_QWORD *)(v797 + 528) + 8LL) |= 0x200u;
                  }
                }
                v798 = (struct CS *)CastOrNull<CS,SH>(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v783 + 304LL) + 32LL), v795);
                CheckDdeCh(v798, 1);
                v799 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1424, 0x237630D6u);
                v800 = SXVWGEOM::RwFirst(v799);
                v801 = *(_QWORD *)(*(_QWORD *)v783 + 304LL);
                v802 = 0;
                v803 = *(_QWORD **)(v801 + 128);
                if ( v803 )
                {
                  v804 = *(_QWORD **)(v801 + 128);
                  do
                  {
                    v802 = v804[1];
                    if ( v802 )
                      break;
                    v803 = (_QWORD *)*v803;
                    v804 = v803;
                  }
                  while ( v803 );
                }
                LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v802 + 96), v788, v800);
                v733 = v1156;
              }
            }
            else if ( !v787 )
            {
              if ( (*((_BYTE *)v786 + 216) & 0x10) != 0 )
              {
                v606 = HrDoDeferredLayoutView(v782);
                if ( v733 )
                {
                  if ( v606 < 0 )
                    goto LABEL_1185;
                }
                else if ( v606 < 0 )
                {
                  v805 = 509215971;
                  v806 = (MsoReserveTag *)&v1361;
LABEL_1925:
                  v1046 = MsoReserveTag::MsoReserveTag(v806, v805);
                  v1047 = SXVWGEOM::RwFirst(v1046);
                  XlsDiag::LogFailRetTag(v606, v1047);
                  goto LABEL_2136;
                }
              }
              else if ( (*((_DWORD *)v782 + 54) & 0x100) != 0 )
              {
                v807 = Measurements::Stopwatch::Stopwatch((Measurements::Stopwatch *)v1541);
                LOBYTE(v808) = 1;
                Measurements::MeasureElapsedTime::MeasureElapsedTime(
                  v1520,
                  Measurements::MeasurementId::ExcelDoDeferredPageLayoutView,
                  v808,
                  v807);
                v1340 = 0;
                v809 = HrXlDoDeferredPageLayoutView(v782, 1, &v1340);
                v606 = v809;
                if ( v733 )
                {
                  if ( v809 < 0 )
                  {
                    v1171 = v809;
                    Measurements::MeasureElapsedTime::~MeasureElapsedTime((Measurements::MeasureElapsedTime *)v1520);
                    goto LABEL_1133;
                  }
                }
                else if ( v809 < 0 )
                {
                  v1049 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1362, 0x1E8C38A3u);
                  v1050 = SXVWGEOM::RwFirst(v1049);
                  XlsDiag::LogFailRetTag(v606, v1050);
                  Measurements::MeasureElapsedTime::~MeasureElapsedTime((Measurements::MeasureElapsedTime *)v1520);
                  goto LABEL_2136;
                }
                Measurements::MeasureElapsedTime::~MeasureElapsedTime((Measurements::MeasureElapsedTime *)v1520);
              }
            }
            v782 = *(struct WNX **)v782;
            v784 = v782;
            v785 = v782;
            v786 = v782;
          }
          while ( v782 );
        }
        if ( !wProjLoad )
        {
          if ( fShowWn )
          {
            v810 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
            if ( !*(_DWORD *)(v810 + 2704) && !*(_DWORD *)(v810 + 1888) )
            {
              v811 = Measurements::Stopwatch::Stopwatch((Measurements::Stopwatch *)v1540);
              LOBYTE(v812) = 1;
              Measurements::MeasureElapsedTime::MeasureElapsedTime(
                v1531,
                Measurements::MeasurementId::ExcelNewFmla,
                v812,
                v811);
              NewFmla(0);
              Measurements::MeasureElapsedTime::~MeasureElapsedTime((Measurements::MeasureElapsedTime *)v1531);
            }
          }
        }
        v813 = lp;
        if ( v1158 )
        {
          if ( lp && !v1177 && !v1160 )
          {
            if ( !v1251 )
            {
              if ( BOOK::Pioldoc(lp) )
              {
                v814 = BOOK::Pioldoc(lp);
                if ( !(unsigned int)IMsoOLDocument::IsInFileSys(v814)
                  || (v815 = BOOK::Pioldoc(lp),
                      ((*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v815 + 224LL))(v815) & 1) != 0) )
                {
                  v816 = BOOK::Pioldoc(lp);
                  v817 = 1;
                  v818 = (*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v816 + 80LL))(v816) & 0x20000;
                  if ( !*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                              + 1232LL)
                                  + 32LL) )
                    v817 = 3;
                  v819 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1425, 0x21C7310u);
                  v820 = SXVWGEOM::RwFirst(v819);
                  v821 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                               + 1232LL)
                                   + 32LL) != 0
                       ? 0x20000
                       : 0;
                  v822 = BOOK::Pioldoc(lp);
                  OldocHelper::SetAttrInAttrMask(v822, v821, 0x20000u, v820);
                  v823 = BOOK::Pioldoc(lp);
                  (*(void (__fastcall **)(struct IMsoOLDocument *, _QWORD, struct IMsoPKMClient **))(*(_QWORD *)v823 + 216LL))(
                    v823,
                    v817,
                    &v1251);
                  v824 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1426, 0x21C7311u);
                  v825 = SXVWGEOM::RwFirst(v824);
                  v826 = BOOK::Pioldoc(lp);
                  OldocHelper::SetAttrInAttrMask(v826, v818, 0x20000u, v825);
                }
              }
              v813 = lp;
            }
            v827 = BOOK::Pioldoc(v813);
            MsoHrMetadataEvent(v827, 32);
            v828 = BOOK::Pioldoc(lp);
            MsoHrTaxonomyOnDocOpen(v828);
            v813 = lp;
          }
          if ( v1158 )
          {
            if ( v813 && !v1177 )
            {
              v829 = BOOK::Pioldoc(v813);
              FileLoad::HrHandleSharepointWorkflows(v829);
              v813 = lp;
            }
            if ( v1158 )
            {
              BuildBookWnxSel();
              v813 = lp;
              if ( v1158 )
              {
                if ( v1251 && lp )
                {
                  *((_QWORD *)lp + 172) = v1251;
                  (*(void (__fastcall **)(struct IMsoPKMClient *))(*(_QWORD *)v1251 + 104LL))(v1251);
                  v813 = lp;
                }
                if ( v1158 && v813 && !*((_QWORD *)v813 + 57) )
                {
                  if ( BOOK::Pioldoc(v813) )
                  {
                    v830 = BOOK::Pioldoc(lp);
                    if ( ((*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v830 + 224LL))(v830) & 1) != 0 )
                    {
                      v831 = BOOK::Pioldoc(lp);
                      if ( ((*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v831 + 80LL))(v831) & 0x40) == 0 )
                      {
                        v832 = MaxPathHolder::SzPath((MaxPathHolder *)v1353);
                        if ( !(unsigned int)FFileInOfflineFilesCache(v832) )
                        {
                          v1298 = 0;
                          v833 = BOOK::Pioldoc(lp);
                          if ( (*(int (__fastcall **)(struct IMsoOLDocument *, struct IStorage **, GUID *))(*(_QWORD *)v833 + 32LL))(
                                 v833,
                                 &v1298,
                                 &IID_IStorage) >= 0 )
                          {
                            v1321 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                              + 2924LL);
                            v1320 = rupBuild;
                            v834 = NtCurrentTeb()->ThreadLocalStoragePointer;
                            v1282 = 0;
                            v1454 = *(struct SH **)(*(_QWORD *)(*(_QWORD *)v834 + 304LL) + 32LL);
                            ENV::ENV((ENV *)&v1565);
                            v835 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                            v1453 = *(_QWORD *)(v835 + 336);
                            *(_QWORD *)(v835 + 336) = &v1565;
                            v1566 = 36737605;
                            v836 = setjmp(v1567);
                            v68 = v1238;
                            v1163 = v1238;
                            if ( v836 )
                            {
                              v114 = v1157;
                            }
                            else
                            {
                              v114 = -2147467259;
                              XlsDiag::LogSetHrCoreTag(-2147467259, 0x279F2A0u);
                              v1312 = 0;
                              ScStgIdsStreamOpen(v1298, 0, 0, v1574, &v1312, -1161035344, 9);
                              if ( SbFromHpCore(v1312) )
                              {
                                if ( !(unsigned int)FBeginDiskIO(v1312) )
                                  goto LABEL_1510;
                                v1266 = 0;
                                if ( (int)HrWPlatformSpecificFromStream2(&v1266) >= 0 )
                                {
                                  if ( (v1266 & 0xF1FF) != 9 )
                                    goto LABEL_1509;
                                  v837 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                                  if ( !*(_QWORD *)(v837 + 32) || (v838 = SH::Pbook(*(SH **)(v837 + 32)), v838 != lp) )
                                  {
                                    v839 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1427, 0x2375A796u);
                                    v840 = SXVWGEOM::RwFirst(v839);
                                    v841 = XLSBOOK::Plxtab((struct BOOK *)((char *)lp + 1640));
                                    v842 = (TAB *)LXTYPE<UsedRange>::PFromI(v841, 0);
                                    v843 = TAB::PshDesktopOnly(v842);
                                    v844 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                  + 304LL)
                                                      + 128LL);
                                    v845 = 0;
                                    if ( v844 )
                                    {
                                      v846 = v844;
                                      do
                                      {
                                        v845 = v846[1];
                                        if ( v845 )
                                          break;
                                        v844 = (_QWORD *)*v844;
                                        v846 = v844;
                                      }
                                      while ( v844 );
                                    }
                                    LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v845 + 96), v843, v840);
                                  }
                                  v1319 = 0;
                                  if ( (int)HrReadBof(v1266, 0, (struct LoadRecovery *)v68, &v1319) >= 0 )
                                  {
                                    v847 = v1267;
                                    v848 = MaxPathHolder::SzPath((MaxPathHolder *)v1353);
                                    if ( (int)HrUpdateWriteAccess(v1584, 516, v848, v847, &v1282) >= 0 )
                                    {
LABEL_1509:
                                      if ( (int)HrEndDiskIO2(0) >= 0 )
                                      {
LABEL_1510:
                                        StreamClose(v1312);
                                        goto LABEL_1511;
                                      }
                                    }
                                  }
                                }
                              }
                              else
                              {
LABEL_1511:
                                if ( v1282 )
                                {
                                  ((void (__fastcall *)(struct IStorage *, _QWORD))v1298->lpVtbl->Commit)(v1298, 0);
                                  if ( ((int (__fastcall *)(struct IStorage *, char *, __int64))v1298->lpVtbl->Stat)(
                                         v1298,
                                         v1553,
                                         1) >= 0 )
                                  {
                                    v849 = BOOK::Pioldoc(lp);
                                    (*(void (__fastcall **)(struct IMsoOLDocument *, _QWORD, __int64))(*(_QWORD *)v849 + 56LL))(
                                      v849,
                                      v1554,
                                      16);
                                    v850 = BOOK::Pioldoc(lp);
                                    (*(void (__fastcall **)(struct IMsoOLDocument *, _QWORD, __int64))(*(_QWORD *)v850 + 56LL))(
                                      v850,
                                      v1555,
                                      17);
                                  }
                                  v851 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                               + 304LL)
                                                   + 40LL)
                                       + 1640LL;
                                  v852 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v851 + 32LL))(v851);
                                  if ( FileLoad::FCheckTimeStampOnThisFile(
                                         *(const struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                           + 304LL)
                                                               + 40LL),
                                         v852,
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
                            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1453;
                            v853 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1428, 0x237630D5u);
                            v854 = SXVWGEOM::RwFirst(v853);
                            v855 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                              + 128LL);
                            v856 = 0;
                            if ( v855 )
                            {
                              v857 = v855;
                              do
                              {
                                v856 = v857[1];
                                if ( v856 )
                                  break;
                                v855 = (_QWORD *)*v855;
                                v857 = v855;
                              }
                              while ( v855 );
                            }
                            LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v856 + 96), v1454, v854);
                            rupBuild = v1320;
                            *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                      + 2924LL) = v1321;
                            ((void (__fastcall *)(struct IStorage *))v1298->lpVtbl->Release)(v1298);
                            v592 = v1302;
                            v813 = lp;
                            v1165 = Src;
                            v1176 = v1219;
                            v1166 = v1250;
LABEL_1524:
                            if ( v1158 )
                            {
                              v858 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                              if ( *(_QWORD *)(v858 + 40) )
                              {
                                sub_14046F510(*(_QWORD *)(v858 + 40));
                                v813 = lp;
                              }
                              if ( v1158
                                && v813
                                && !(unsigned int)XlSecurity::FMaaFinal(v813, 5)
                                && !(unsigned int)XlSecurity::FMaaDetected(lp, 5)
                                && !IsWin32AppRunningInWdag() )
                              {
                                EnableMaa(lp, 5);
                                FinalMaa(lp, 5);
                              }
                            }
                            if ( Python::FeatureGates::FEnabledPython(0) && v1158 )
                            {
                              v859 = lp;
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
                              v859 = lp;
                            }
                            if ( CastOrNull<XLSWORKBOOK,BOOK>(v859) )
                            {
                              v860 = (const struct Api::Workbook *)CastOrNull<XLSWORKBOOK,BOOK>(lp);
                              if ( Api::ImportFunctionsManager::FIsFeatureEnabled(v860)
                                && v1158
                                && !(unsigned int)XlSecurity::FMaaFinal(lp, 9)
                                && !(unsigned int)XlSecurity::FMaaDetected(lp, 9)
                                && !IsWin32AppRunningInWdag() )
                              {
                                EnableMaa(lp, 9);
                                FinalMaa(lp, 9);
                              }
                            }
                            LOBYTE(v264) = v1156;
LABEL_1549:
                            v861 = (Excel::AppGuard::Actions **)lp;
                            if ( v1158 )
                            {
                              if ( lp )
                              {
                                if ( !Excel::AppGuard::FTryInitAfterLoad(lp, v594) )
                                {
                                  Error(196663);
                                  v1051 = HrFreeBook2(lp);
                                  v606 = v1051;
                                  if ( (_BYTE)v264 )
                                  {
                                    if ( v1051 < 0 )
                                    {
                                      v1171 = v1051;
                                      goto LABEL_1133;
                                    }
                                  }
                                  else if ( v1051 < 0 )
                                  {
                                    v805 = 512506018;
                                    v806 = (MsoReserveTag *)&v1363;
                                    goto LABEL_1925;
                                  }
                                  lp = 0;
                                  v1158 = 0;
                                  goto LABEL_1935;
                                }
                                v861 = (Excel::AppGuard::Actions **)lp;
                              }
                              if ( v1158 && v861 && (a10 & 0x40000) != 0 )
                              {
                                Excel::AppGuard::Actions::AddTrustPromotionRecord(v861[192], (unsigned __int64)v594);
                                v861 = (Excel::AppGuard::Actions **)lp;
                              }
                            }
                            if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                           + 1440LL)
                              && v861 )
                            {
                              v862 = FBookAddin((const struct BOOK *)v861);
                              v863 = v1165;
                              if ( v862 && (int)AddinManager::HrAddOpenAddin(v1165 + 1, *v1165, &vpoldocument) < 0 )
                              {
                                sub_1411BF070();
                                sub_141232FB0();
                                XlsDiag::LogSetHrCoreTag(-2080308954, 0x1E8C38A1u);
                                v606 = -2080308954;
                                goto LABEL_2136;
                              }
                            }
                            else
                            {
                              v863 = v1165;
                            }
                            v864 = 0;
                            if ( v592 )
                            {
                              v865 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                              v866 = *(_QWORD *)(v865 + 32)
                                   ? SH::Pbook(*(SH **)(v865 + 32))
                                   : *(struct BOOK **)(v865 + 40);
                              if ( v866 != SH::Pbook(v592) )
                              {
                                v864 = 1;
                                v867 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                                v1273 = *(struct SH **)(v867 + 32);
                                v1280 = *(struct WNX **)(v867 + 104);
                                v1336 = (struct WNX *)UIGLOBALS::UIGLOBALSCONTAINER::m_selection;
                                v868 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1429, 0x237630D4u);
                                v869 = SXVWGEOM::RwFirst(v868);
                                v870 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                              + 304LL)
                                                  + 128LL);
                                v871 = 0;
                                if ( v870 )
                                {
                                  v872 = v870;
                                  do
                                  {
                                    v871 = v872[1];
                                    if ( v871 )
                                      break;
                                    v870 = (_QWORD *)*v870;
                                    v872 = v870;
                                  }
                                  while ( v870 );
                                }
                                LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v871 + 96), v592, v869);
                              }
                            }
                            if ( v1158 )
                            {
                              v873 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                              if ( *(_QWORD *)(v873 + 40) )
                              {
                                if ( (*(_BYTE *)(*(_QWORD *)(v873 + 1304) + 56LL) & 8) != 0
                                  && (unsigned int)FAnyListsInBook(*(const struct BOOK **)(v873 + 40)) )
                                {
                                  v561 = (unsigned int)CustomTwoAlert(327820, 0, -282329067, -282329066) == 102;
                                  v874 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                                  if ( v561 )
                                    RemoveBookLists(*(const struct BOOK **)(v874 + 40));
                                  else
                                    *(_WORD *)(*(_QWORD *)(v874 + 1304) + 56LL) &= ~8u;
                                }
                              }
                            }
                            if ( !v1158 )
                              goto LABEL_1630;
                            v875 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                            if ( *(_QWORD *)(v875 + 40) )
                            {
                              if ( (*(_BYTE *)(*(_QWORD *)(v875 + 1304) + 56LL) & 8) != 0 )
                              {
                                if ( !XLSBOOK::Plxtab(*(XLSBOOK **)(v875 + 40))
                                  || (v876 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                   + 304LL)
                                                       + 40LL)
                                           + 1640LL,
                                      !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v876 + 32LL))(v876)) )
                                {
                                  v877 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                                  v878 = *(_QWORD *)(v877 + 40);
                                  if ( *(_DWORD *)(v877 + 1836) )
                                  {
                                    *(_DWORD *)(v878 + 884) |= 0x400000u;
                                    goto LABEL_1587;
                                  }
                                  if ( (*(_DWORD *)(v878 + 884) & 0x100) != 0 )
                                  {
                                    *(_DWORD *)(v878 + 884) |= 0x400000u;
                                    v889 = NtCurrentTeb()->ThreadLocalStoragePointer;
                                    *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v889 + 304LL) + 1304LL) + 16LL) = *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v889 + 304LL) + 1232LL) + 110LL);
                                    v73 = 1;
                                    *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                     + 304LL)
                                                         + 1232LL)
                                             + 110LL) = 0;
                                    fnSave(0, 0, 1);
                                    v890 = NtCurrentTeb()->ThreadLocalStoragePointer;
                                    *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v890 + 304LL) + 1232LL) + 110LL) = *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v890 + 304LL) + 1304LL) + 16LL);
                                    goto LABEL_1588;
                                  }
                                }
                              }
                            }
                            if ( !v1158 )
                              goto LABEL_1630;
                            v891 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                            if ( (*(_BYTE *)(*(_QWORD *)(v891 + 1304) + 56LL) & 8) != 0 )
                            {
                              if ( *(_QWORD *)(v891 + 40) )
                              {
                                if ( XLSBOOK::Plxtab(*(XLSBOOK **)(v891 + 40)) )
                                {
                                  v892 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                               + 304LL)
                                                   + 40LL)
                                       + 1640LL;
                                  if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v892 + 32LL))(v892) )
                                  {
                                    v893 = FileSource::HrGetFileTemp(v1310, 12);
                                    v114 = v893;
                                    if ( v893 < 0 )
                                      XlsDiag::LogSetHrCoreTag(v893, 0x280659Au);
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
                                                v1158,
                                                v863,
                                                v1229,
                                                (struct LoadRecovery *)v68,
                                                &v1322,
                                                &v1268) >= 0 )
                                    {
                                      if ( v1159 )
                                      {
                                        v896 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                                        if ( *(_QWORD *)(v896 + 40) )
                                          v897 = BOOK::Pioldoc(*(BOOK **)(v896 + 40));
                                        else
                                          v897 = 0;
                                        *v1166 = v897;
                                        v1162 = v897;
                                      }
                                    }
                                    else
                                    {
                                      if ( v1268 )
                                      {
                                        *v1166 = 0;
                                        v1162 = 0;
                                      }
                                      else if ( v1159 )
                                      {
                                        v894 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                                        if ( *(_QWORD *)(v894 + 40) )
                                          v895 = BOOK::Pioldoc(*(BOOK **)(v894 + 40));
                                        else
                                          v895 = 0;
                                        *v1166 = v895;
                                        v1162 = v895;
                                      }
                                      if ( v1322 || v1268 )
                                        goto LABEL_1587;
                                    }
                                  }
                                }
                              }
                            }
                            if ( v1158
                              && *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                           + 40LL)
                              && v1272 )
                            {
                              v898 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1430, 0x1E111215u);
                              v899 = SXVWGEOM::RwFirst(v898);
                              v73 = 1;
                              BookDirty(
                                *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                            + 304LL)
                                                + 40LL),
                                1,
                                v899);
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
                            if ( v1158 )
                            {
                              v900 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                              if ( *(_QWORD *)(v900 + 40) )
                              {
                                if ( (unsigned int)FSharedBook(*(const struct BOOK **)(v900 + 40)) )
                                {
                                  v901 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                               + 304LL)
                                                   + 40LL);
                                  if ( (*(_BYTE *)(v901 + 892) & 0x20) != 0 )
                                  {
                                    *(_DWORD *)(v901 + 892) &= ~0x20u;
                                    v902 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1431, 0x231C69Cu);
                                    v903 = SXVWGEOM::RwFirst(v902);
                                    BookDirty(
                                      *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                  + 304LL)
                                                      + 40LL),
                                      1,
                                      v903);
                                    OkAlert(327877, 0);
                                  }
                                }
                              }
                              if ( v1158 )
                              {
                                if ( (unsigned int)FSharedBook(*(const struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                                 + 304LL)
                                                                                     + 40LL)) )
                                {
                                  v904 = LOCATIONCONTEXTDATA::PWorkbookCur((LOCATIONCONTEXTDATA *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                                                                                 + 8LL));
                                  v905 = TLSW::PesExpressionService(*(TLSW **)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                             + 304LL));
                                  ConvertAllDynamicArraystoLegacyArrays(v905, v904);
                                }
                                if ( v1158 )
                                {
                                  if ( *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                             + 304LL)
                                                 + 40LL)
                                    && (unsigned int)sub_14046FA80() )
                                  {
                                    SetAutoRefreshPending(1, 0);
                                  }
                                  if ( v1158
                                    && *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                             + 304LL)
                                                 + 40LL) )
                                  {
                                    v906 = FeatureGateCollectionBase<LoadSaveFeatureGates>::Instance();
                                    v561 = (unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(v906 + 424) == 0;
                                    v907 = NtCurrentTeb()->ThreadLocalStoragePointer;
                                    if ( v561 )
                                    {
                                      v1283 = 0;
                                      v1284 = 0;
                                      v910 = XLSBOOK::Plxtab((XLSBOOK *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v907 + 304LL)
                                                                                   + 40LL)
                                                                       + 1640LL));
                                      XlPng::DyHeight(v910, v1300);
                                      LXContainerContiguousIterators<LXTYPE<TAB>,TAB,LXBASE>::end(v910, v1334);
                                      if ( (unsigned __int8)LXContiguousConstIterator<LXTYPE<TAB>>::operator!=(
                                                              v1300,
                                                              v1334) )
                                      {
                                        do
                                        {
                                          v911 = BKORWS::Psh((BKORWS *)v1300);
                                          v912 = TAB::PshDesktopOnly(v911);
                                          if ( (*((_BYTE *)v912 + 10) & 4) != 0 )
                                            v913 = 0;
                                          else
                                            v913 = *((_BYTE *)v912 + 8);
                                          if ( v913 <= 1u )
                                          {
                                            v914 = TAB::PshDesktopOnly(v911);
                                            GetOartDataForTelemetry(v914, &v1283, &v1284);
                                          }
                                          LXContiguousIterator<LXTYPE<TAB>>::operator++(v1300);
                                        }
                                        while ( (unsigned __int8)LXContiguousConstIterator<LXTYPE<TAB>>::operator!=(
                                                                   v1300,
                                                                   v1334) );
                                        v68 = v1163;
                                      }
                                      LXContiguousIterator<LXTYPE<std::pair<XLUID,DocumentTasks::SharedAuthorMapValue>>>::~LXContiguousIterator<LXTYPE<std::pair<XLUID,DocumentTasks::SharedAuthorMapValue>>>(v1334);
                                      LXContiguousIterator<LXTYPE<std::pair<XLUID,DocumentTasks::SharedAuthorMapValue>>>::~LXContiguousIterator<LXTYPE<std::pair<XLUID,DocumentTasks::SharedAuthorMapValue>>>(v1300);
                                      v915 = Mso::Telemetry::Activity::DataFields(v1218);
                                      Mso::Telemetry::IDataFieldCollection::Add<int>(
                                        v915,
                                        "cMsoShapes",
                                        (unsigned int)v1283,
                                        4);
                                      v916 = Mso::Telemetry::Activity::DataFields(v1218);
                                      Mso::Telemetry::IDataFieldCollection::Add<int>(
                                        v916,
                                        "numShapes",
                                        (unsigned int)v1284,
                                        4);
                                    }
                                    else
                                    {
                                      v908 = v1218;
                                      v909 = LOCATIONCONTEXTDATA::PWorkbookCur((LOCATIONCONTEXTDATA *)(*(_QWORD *)(*(_QWORD *)v907 + 304LL) + 8LL));
                                      ArtUtil::LogOartDataForOpenedWorkbook(v909, v908);
                                    }
                                  }
                                }
                              }
                            }
                            if ( v1231 )
                            {
                              v277 = v1165;
                              CeToggleFileAttr(v1165, v1229, 3, 6u);
                            }
                            else
                            {
LABEL_1588:
                              v277 = v1165;
                            }
                            if ( v864 )
                            {
                              v879 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1432, 0x237630D3u);
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
                                  v882 = v883[1];
                                  if ( v882 )
                                    break;
                                  v881 = (_QWORD *)*v881;
                                  v883 = v881;
                                }
                                while ( v881 );
                              }
                              LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v882 + 96), v1273, v880);
                              v884 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1433, 0x237630D2u);
                              v885 = SXVWGEOM::RwFirst(v884);
                              v886 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                            + 304LL)
                                                + 128LL);
                              v887 = 0;
                              if ( v886 )
                              {
                                v888 = v886;
                                do
                                {
                                  v887 = v888[3];
                                  if ( v887 )
                                    break;
                                  v886 = (_QWORD *)*v886;
                                  v888 = v886;
                                }
                                while ( v886 );
                              }
                              VIEWCONTEXTDATA::CurWnx(*(VIEWCONTEXTDATA **)(v887 + 16), v1280, v885);
                              SetWnxSel(v1336);
                            }
                            else if ( v1308 != (struct SH *)65534 )
                            {
                              v917 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1434, 0x237630D1u);
                              v918 = SXVWGEOM::RwFirst(v917);
                              v919 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                            + 304LL)
                                                + 128LL);
                              v920 = 0;
                              if ( v919 )
                              {
                                v921 = v919;
                                do
                                {
                                  v920 = v921[1];
                                  if ( v920 )
                                    break;
                                  v919 = (_QWORD *)*v919;
                                  v921 = v919;
                                }
                                while ( v919 );
                              }
                              LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v920 + 96), v1308, v918);
                            }
                            goto LABEL_1664;
                          }
                        }
                      }
                    }
                  }
                  v813 = lp;
                }
              }
            }
          }
        }
        v68 = v1163;
        goto LABEL_1524;
      }
      v602 = FileSource::StzFileName((FileSource *)v1310);
      if ( !FForeignFileExtension(v602) && (v1177 || !(unsigned int)FFinderFile(&v1572)) )
      {
        v603 = FileSource::StzFilePath((FileSource *)v1310);
        CchStToStz(v603, v1548, 2086);
        if ( !v1547 )
        {
          MaxPathStzPoke::MaxPathStzPoke((MaxPathStzPoke *)v1508, (struct MaxPathHolder *)v1345);
          v1550 = SlicerViewImpl::PSlicerView((SlicerViewImpl *)v1508);
          MaxPathStzPoke::~MaxPathStzPoke((MaxPathStzPoke *)v1508);
        }
        if ( v1177 && !(unsigned int)FOsrc() )
        {
          v604 = v1222;
LABEL_1130:
          v605 = HrEndDiskIO2(0);
          v606 = v605;
          if ( v1156 )
          {
            if ( v605 < 0 )
              goto LABEL_1132;
          }
          else if ( v605 < 0 )
          {
            v805 = 512506060;
            v806 = (MsoReserveTag *)&v1359;
            goto LABEL_1925;
          }
          StreamClose(v1172);
          if ( (unsigned int)(v604 + 2146697471) <= 1 )
          {
            if ( v68 )
              LoadRecovery::SetRepairState((LoadRecovery *)v68, v604);
            else
              *(&vscd + 1) = 1;
          }
          v114 = -2146827284;
          v1158 = 0;
          v1157 = -2146827284;
          XlsDiag::LogSetHrCoreTag(-2146827284, 0x1797719u);
          v685 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1184);
          v686 = OpenTelemetry::POpenFileStageModel(v685);
          v687 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1414, 0x1F0CB5C5u);
          v688 = SXVWGEOM::RwFirst(v687);
          WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v686, 2214658822LL, v688);
          v597 = v1159;
          goto LABEL_1272;
        }
        v615 = HrDetectWebType(v1162, (enum MSOFF *)&v1221, &v1297, 0, 0);
        v1222 = v615;
        v604 = v615;
        if ( v615 < 0 )
          goto LABEL_1130;
        if ( v615 == 1 )
        {
          if ( (unsigned int)FCmpTextEq(&v1571[v1572 + 13], L".xml", 4, 4)
            || (unsigned int)FCmpTextEq(&v1571[v1572 + 13], L".xsd", 4, 4) )
          {
            v1206 = 1;
            v616 = 3;
          }
          else
          {
            v616 = 0;
          }
          v1221 = v616;
        }
        if ( (unsigned int)FOsrc() && (unsigned int)(v1221 - 1) > 2 )
          goto LABEL_1130;
        v617 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1184);
        v618 = (LXBASE *)OpenTelemetry::POpenFileStageModel(v617);
        v619 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1412, 0x1F0CB5C4u);
        SXVWGEOM::RwFirst(v619);
        WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v618);
        v620 = a11;
        if ( v1221 == 1 || v1221 == 2 )
        {
          v621 = v1163;
          goto LABEL_1288;
        }
        if ( v1221 == 3 )
        {
          v621 = v1163;
          v622 = HrDetectXMLTypeAndPreprocess(a11, (struct XSL *)&v1546, (struct LoadRecovery *)v1163, 0, 1, 1, v1206);
          v1222 = v622;
          v604 = v622;
          if ( v622 != -2147467263 )
          {
            if ( v622 == -2147418113 )
              goto LABEL_1189;
            if ( v622 == -2147352567 )
            {
              v73 = 1;
              if ( v1547 == 1 )
              {
                MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1467, v1165);
                v1194 = v1183 != 0;
                v1304 = v1162;
              }
              else if ( v1162 )
              {
                (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v1162 + 56LL))(
                  v1162,
                  0xFFFFFFFFLL,
                  7);
                if ( v1183 )
                  HrRecordEvent(v1162, 0x40000000u, 0);
                v630 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1413, 0x2369629Fu);
                v631 = SXVWGEOM::RwFirst(v630);
                OlDocFilePath::FReleaseIOLDoc(v501, 1, 1, v631);
              }
              v407 = 0;
              v1166 = 0;
              v1250 = 0;
              CchStToSt(v1549, v1165, v1229);
              v1219 = 1;
              v606 = HrEndDiskIO2(0);
              if ( v1156 )
              {
                if ( v606 < 0 )
                  goto LABEL_1185;
              }
              else if ( v606 < 0 )
              {
                v805 = 512506059;
                v806 = (MsoReserveTag *)&v1462;
                goto LABEL_1925;
              }
              StreamClose(v1172);
              v68 = v1163;
              a11 = 65001;
              goto LABEL_744;
            }
            if ( v622 )
            {
              if ( v622 != 1 )
              {
                if ( v622 == -2146827284 )
                  Error(262267);
                v68 = v1163;
                goto LABEL_1130;
              }
LABEL_1189:
              v1221 = 1;
              (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v1162 + 56LL))(
                v1162,
                1,
                11);
LABEL_1288:
              FSwitchLoadActionType(2, 0, (struct LoadRecovery *)v621);
              v674 = -(v1221 != 2);
              v675 = BKORWS::Psh((BKORWS *)v1345);
              v676 = 0;
              if ( (unsigned __int8)SafeToLoad::FSafeToLoadOnFileExtensionPfilesource(
                                      v675,
                                      v1310,
                                      (unsigned int)(v674 + 44),
                                      &v1240) )
              {
                MaxPathStzPoke::MaxPathStzPoke((MaxPathStzPoke *)v1510, (struct MaxPathHolder *)v1345);
                v677 = v1297;
                v678 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1836LL);
                LOBYTE(v676) = v1221 == 2;
                v679 = (wchar_t *)SlicerViewImpl::PSlicerView((SlicerViewImpl *)v1510);
                BookHtml = HrLoadBookHtml(v1172, 0, v1575, v679, a5, 0, v677, v620, v676, v678, (struct OSRR *)&v1240);
                v1157 = BookHtml;
                v114 = BookHtml;
                if ( BookHtml < 0 )
                  XlsDiag::LogSetHrCoreTag(BookHtml, 0x2156756u);
                MaxPathStzPoke::~MaxPathStzPoke((MaxPathStzPoke *)v1510);
                v1158 = v114 >= 0;
                if ( v114 >= 0 || !OSRR::FReadyForOsr((OSRR *)&v1240) )
                {
                  v597 = v1159;
                  if ( v1159 )
                  {
                    if ( (unsigned int)IMsoOLDocument::IsInFileSys(v1162) )
                    {
                      if ( v1158
                        || (v681 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL),
                            *(_QWORD *)(v681 + 40))
                        && (*(_DWORD *)(*(_QWORD *)(v681 + 40) + 884LL) & 0x200) != 0 )
                      {
                        v682 = (wchar_t **)XLSBOOK::Plxtab(*(XLSBOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                   + 304LL)
                                                                       + 40LL));
                        FreeHpstTempPath((struct STB *)v682, v683);
                        v684 = FileSource::StzFilePath((FileSource *)v1310);
                        if ( (int)HrStDupSt(v684, v682 + 21) < 0 )
                          v682[21] = 0;
                      }
                    }
                  }
                  v1179 = 1;
                  goto LABEL_1272;
                }
                v73 = 1;
LABEL_1168:
                v1160 = 1;
LABEL_1072:
                v68 = v1163;
                goto LABEL_743;
              }
LABEL_1284:
              v68 = v1163;
              goto LABEL_1130;
            }
            v623 = BKORWS::Psh((BKORWS *)v1345);
            if ( !(unsigned __int8)SafeToLoad::FSafeToLoadOnFileExtensionPfilesource(v623, v1310, 45, &v1240) )
              goto LABEL_1284;
            MaxPathStzPoke::MaxPathStzPoke((MaxPathStzPoke *)v1509, (struct MaxPathHolder *)v1345);
            v624 = (wchar_t *)SlicerViewImpl::PSlicerView((SlicerViewImpl *)v1509);
            BookXmlSpreadsheet = HrLoadBookXmlSpreadsheet(v1172, v1575, v624, a5, 0, v620, (struct OSRR *)&v1240);
            v1157 = BookXmlSpreadsheet;
            v114 = BookXmlSpreadsheet;
            if ( BookXmlSpreadsheet < 0 )
              XlsDiag::LogSetHrCoreTag(BookXmlSpreadsheet, 0x2156757u);
            MaxPathStzPoke::~MaxPathStzPoke((MaxPathStzPoke *)v1509);
            v1158 = v114 >= 0;
            if ( v114 < 0 && OSRR::FReadyForOsr((OSRR *)&v1240) )
            {
              v73 = 1;
              goto LABEL_1168;
            }
            v597 = v1159;
            if ( v1159 )
            {
              if ( (unsigned int)IMsoOLDocument::IsInFileSys(v1162) )
              {
                if ( v1158
                  || (v626 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL),
                      *(_QWORD *)(v626 + 40))
                  && (*(_DWORD *)(*(_QWORD *)(v626 + 40) + 884LL) & 0x200) != 0 )
                {
                  v627 = (wchar_t **)XLSBOOK::Plxtab(*(XLSBOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                             + 304LL)
                                                                 + 40LL));
                  FreeHpstTempPath((struct STB *)v627, v628);
                  v629 = FileSource::StzFilePath((FileSource *)v1310);
                  if ( (int)HrStDupSt(v629, v627 + 21) < 0 )
                    v627[21] = 0;
                }
              }
            }
LABEL_1270:
            v668 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
            if ( *(_QWORD *)(v668 + 24) )
            {
              v669 = OcsTransitionController::PCoauthTransitionState(*(OcsTransitionController **)(v668 + 24));
              XLSBOOK::HrEnsureAllSheetXluids(v669);
            }
            goto LABEL_1272;
          }
          v632 = BKORWS::Psh((BKORWS *)v1345);
          if ( !(unsigned __int8)SafeToLoad::FSafeToLoadOnFileExtensionPfilesource(v632, v1310, 48, &v1240) )
            goto LABEL_1284;
          v633 = BKORWS::Psh((BKORWS *)v1344);
          if ( (unsigned int)FBlockOfficeFile(33, v633, 0) )
            OptDialog = 1223;
          else
            OptDialog = HrShowXmlLoadOptDialog((enum XMLLOADOPTIONS *)&v1235, a12);
          if ( OptDialog )
          {
            if ( OptDialog < 0 )
              XlsDiag::LogSetHrCoreTag(OptDialog, 0x2156759u);
            goto LABEL_1284;
          }
          CodeMarker(1124);
          if ( v1235 != 1 )
          {
            if ( v1235 == 2 )
            {
              if ( v1162
                && ((*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1162 + 80LL))(v1162) & 0x40) == 0
                && (int)HrRecordEvent(v1162, 0x40000000u, 0) >= 0 )
              {
                FBeginCmdIOLDoc(v1162, 4u, 0, 0, 0);
              }
              v651 = APPCORE::PmemheapMain((APPCORE *)&vapp);
              MaxPathHolder::MaxPathHolder((MaxPathHolder *)v1515, v651, 259, 0);
              if ( v1547 )
                v652 = (const wchar_t *)((char *)v1172 + 48);
              else
                v652 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1345);
              MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1515, v652);
              v653 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1345);
              v654 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1515);
              Xml = HrLoadXml(v1172, v1575, 257, v654, v653, 0, a5, 1, 1);
              v1157 = Xml;
              v114 = Xml;
              if ( Xml < 0 )
                XlsDiag::LogSetHrCoreTag(Xml, 0x2156758u);
              MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1515);
              v1158 = v114 >= 0;
              if ( v114 < 0 )
                StreamClose(v1172);
            }
            else
            {
              if ( v1235 != 3 )
              {
                if ( v1235 == 4 )
                {
                  if ( SbFromHpCore(v1172) )
                    StreamClose(v1172);
                  v1172 = FileSource::StreamOpen((FileSource *)v1310, 0x401u, 0);
                  if ( SbFromHpCore(v1172) )
                  {
                    v561 = g_fPromptTextFile == 0;
                    g_fPromptTextFile = 0;
                    v635 = !v561;
                    v1295 = 0;
                    v636 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1355);
                    v637 = (wchar_t *)BKORWS::Psh((BKORWS *)v1355);
                    v606 = HrLoadBiff(
                             &v1172,
                             &v1572,
                             v637,
                             v636,
                             1,
                             a5,
                             a7,
                             v1220,
                             0,
                             &v1199,
                             &v1228,
                             (struct LoadRecovery *)v621,
                             &lp,
                             0,
                             0,
                             0,
                             v1278,
                             &v1295);
                    if ( v1156 )
                    {
                      if ( v606 < 0 )
                        goto LABEL_1185;
                    }
                    else if ( v606 < 0 )
                    {
                      v805 = 512506057;
                      v806 = (MsoReserveTag *)&v1463;
                      goto LABEL_1925;
                    }
                    if ( v1295 )
                    {
                      v638 = BKORWS::Psh((BKORWS *)&v1184);
                      v639 = v1162;
                      v640 = v1172;
                      v641 = v638;
                      v642 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1355);
                      v643 = (wchar_t *)BKORWS::Psh((BKORWS *)v1345);
                      v1244 = FLoadForeign(v1575, v643, v642, v640, a5, 2, &v1265, v639, 0, v1278, v641);
                    }
                    g_fPromptTextFile = v635;
                  }
                }
                goto LABEL_1264;
              }
              v1332 = 0;
              if ( v1162
                && ((*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1162 + 80LL))(v1162) & 0x40) == 0
                && (int)HrRecordEvent(v1162, 0x40000000u, 0) >= 0 )
              {
                FBeginCmdIOLDoc(v1162, 4u, 0, 0, 0);
              }
              v644 = NtCurrentTeb()->ThreadLocalStoragePointer;
              v645 = vpoldocument;
              v1525[7] = 0;
              v1525[3] = 0;
              v646 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v644 + 304LL) + 32LL);
              v647 = NtCurrentTeb()->ThreadLocalStoragePointer;
              v1525[0] = v646;
              v1525[1] = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v647 + 304LL) + 104LL);
              v1525[2] = UIGLOBALS::UIGLOBALSCONTAINER::m_selection;
              (*(void (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)vpoldocument + 8LL))(vpoldocument);
              Project2 = HrCreateProject2(0, 0, 5, 7u, 0, 1);
              v606 = Project2;
              if ( v1156 )
              {
                if ( Project2 < 0 )
                  goto LABEL_1215;
              }
              else if ( Project2 < 0 )
              {
                v805 = 512506053;
                v806 = (MsoReserveTag *)&v1466;
                goto LABEL_1925;
              }
              SuspendRecording();
              if ( (unsigned int)HrDesignXMLCore(v645, &v1332) )
              {
                ResumeRecording();
                if ( v1271 )
                  FreePxlxmlmap(v1271);
                HtmlFailed = HrBookLoadHtmlFailed((struct BLG *)v1525);
                v606 = HtmlFailed;
                if ( v1156 )
                {
                  if ( HtmlFailed < 0 )
                    goto LABEL_1215;
                }
                else if ( HtmlFailed < 0 )
                {
                  v805 = 512506051;
                  v806 = (MsoReserveTag *)&v1402;
                  goto LABEL_1925;
                }
                (*(void (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v645 + 16LL))(v645);
                goto LABEL_1284;
              }
              ResumeRecording();
              RenumberWind(*(struct SH **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                         + 32LL));
              v649 = HrEndDiskIO2(0);
              v606 = v649;
              if ( v1156 )
              {
                if ( v649 < 0 )
                  goto LABEL_1132;
              }
              else if ( v649 < 0 )
              {
                v805 = 512506052;
                v806 = (MsoReserveTag *)&v1464;
                goto LABEL_1925;
              }
              StreamClose(v1172);
              v1158 = 1;
              (*(void (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v645 + 16LL))(v645);
              if ( !FVbaEventEnabled() )
                goto LABEL_1264;
LABEL_1223:
              HrVbaEventDoBookOpen(
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL),
                2);
            }
LABEL_1264:
            CodeMarker(1125);
            v666 = v1180;
            if ( v1158 )
              v666 = 1;
            v1180 = v666;
            if ( ((v1235 - 1) & 0xFFFFFFFD) != 0 )
            {
              v597 = v1159;
            }
            else
            {
              v1350 = 0;
              v667 = FHpshtiFromStt(&v1350, 61);
              v597 = v1159;
              if ( v667 )
                *((_DWORD *)v1350 + 6) = v1235;
            }
            goto LABEL_1270;
          }
          v656 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v657 = 0;
          v1342 = 0;
          v1317 = 0;
          v1311 = 0;
          v1526[7] = 0;
          v1526[3] = 0;
          v658 = vpoldocument;
          v1296 = 1;
          v659 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v656 + 304LL) + 32LL);
          v660 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v1526[0] = v659;
          v1526[1] = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v660 + 304LL) + 104LL);
          v1526[2] = UIGLOBALS::UIGLOBALSCONTAINER::m_selection;
          (*(void (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)vpoldocument + 8LL))(vpoldocument);
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 2132LL) = 1;
          v606 = HrCreateProject2(0, 0, 5, 7u, 0, 1);
          if ( v1156 )
          {
            if ( v606 < 0 )
            {
LABEL_1185:
              v1171 = v606;
              goto LABEL_1133;
            }
          }
          else if ( v606 < 0 )
          {
            v805 = 512506056;
            v806 = (MsoReserveTag *)&v1358;
            goto LABEL_1925;
          }
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 2132LL) = 0;
          SetRef((struct REF *)v1491, 0, 0, 0, 0);
          SuspendRecording();
          if ( (unsigned int)FEnsureVpxierrinfo()
            && !(unsigned int)HrXlXmlMapFromOlDocument(v658, &v1271, &v1342, &v1296, &v1317, &v1311, 1) )
          {
            v661 = LOCATIONCONTEXTDATA::PWorkbookCur((LOCATIONCONTEXTDATA *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                       + 304LL)
                                                                           + 8LL));
            v662 = XLSWORKBOOK::Pcm(v661);
            v663 = OcsTransitionController::PCoauthTransitionState(v662);
            CollabManager::FDisableRevisionGeneration(v663, 196, 0);
            v664 = *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer;
            if ( v1296 )
            {
              LOBYTE(v657) = (unsigned int)HrAutoDesignXML(
                                             0,
                                             v1317,
                                             v1311,
                                             *(struct SH **)(*(_QWORD *)(v664 + 304) + 32LL),
                                             (const struct REF *)v1491,
                                             v1271,
                                             0) == 0;
            }
            else if ( !(unsigned int)HrAutoDesignXML(
                                       v658,
                                       0,
                                       0,
                                       *(struct SH **)(*(_QWORD *)(v664 + 304) + 32LL),
                                       (const struct REF *)v1491,
                                       v1271,
                                       0) )
            {
              v657 = 1;
            }
          }
          (*(void (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v658 + 16LL))(v658);
          if ( v1317 )
          {
            ((void (__fastcall *)(struct IStream *))v1317->lpVtbl->Release)(v1317);
            v1317 = 0;
          }
          if ( v1311 )
          {
            ((void (__fastcall *)(struct IStream *))v1311->lpVtbl->Release)(v1311);
            v1311 = 0;
          }
          DisplayCleanupXIErr();
          ResumeRecording();
          if ( !v657 )
          {
            v673 = HrBookLoadHtmlFailed((struct BLG *)v1526);
            v606 = v673;
            if ( v1156 )
            {
              if ( v673 < 0 )
              {
LABEL_1215:
                v1171 = v606;
                goto LABEL_1133;
              }
            }
            else if ( v673 < 0 )
            {
              v805 = 512506054;
              v806 = (MsoReserveTag *)&v1357;
              goto LABEL_1925;
            }
            goto LABEL_1284;
          }
          if ( *((_DWORD *)vpxsl + 1) )
          {
            FreeHpst(*((wchar_t **)v1271 + 14));
            *((_QWORD *)v1271 + 14) = 0;
            *((_DWORD *)v1271 + 24) = 0;
          }
          v665 = HrEndDiskIO2(0);
          v606 = v665;
          if ( v1156 )
          {
            if ( v665 < 0 )
              goto LABEL_1215;
          }
          else if ( v665 < 0 )
          {
            v805 = 512506055;
            v806 = (MsoReserveTag *)&v1468;
            goto LABEL_1925;
          }
          StreamClose(v1172);
          v1158 = 1;
          if ( !FVbaEventEnabled() )
            goto LABEL_1264;
          goto LABEL_1223;
        }
      }
LABEL_1077:
      v277 = v1165;
LABEL_1078:
      if ( !FEnableForeignFileProtectedView() )
      {
        OSRR::SetAppAllowed((OSRR *)&v1240, 0);
        if ( (unsigned int)XLOSRR::FMustUseOsr((XLOSRR *)&v1240) )
        {
          if ( SbFromHpCore(v1172) )
            StreamClose(v1172);
          v577 = (__int64 *)NtCurrentTeb()->ThreadLocalStoragePointer;
          v1172 = 0;
          v1158 = 0;
          v578 = *v577;
          vhpstm = 0;
          errDeferred = 0;
          v579 = *(_QWORD *)(v578 + 304);
          *(_DWORD *)(v579 + 2024) = 0;
          *(_DWORD *)(v579 + 2028) = 0;
          v114 = -2147024809;
          XlsDiag::LogSetHrCoreTag(-2147024809, 0x179771Au);
          v68 = v1163;
          v73 = 1;
LABEL_1083:
          LOBYTE(v264) = v1156;
          goto LABEL_1664;
        }
      }
      v68 = v1163;
      if ( v1163 && (int)LoadRecovery::Lrmode(v1163) > 0 )
      {
        v73 = 1;
        v689 = 1;
      }
      else
      {
        v689 = 0;
        v73 = 1;
      }
      if ( v689 )
      {
        v690 = PivotOperationBase::PSxview((PivotOperationBase *)v68);
        *((_WORD *)v690 + 18) |= 8u;
      }
      FSwitchLoadActionType(2, 0, (struct LoadRecovery *)v68);
      MaxPathStzPoke::MaxPathStzPoke((MaxPathStzPoke *)v1495, (struct MaxPathHolder *)v1345);
      v691 = APPCORE::PmemheapMain((APPCORE *)&vapp);
      MaxPathHolder::MaxPathHolder((MaxPathHolder *)v1516, v691, 259, 0);
      v692 = FileSource::HrGetFileTemp(v1310, 11);
      v1157 = v692;
      v114 = v692;
      if ( v692 < 0 )
        XlsDiag::LogSetHrCoreTag(v692, 0x27413C1u);
      if ( v114 < 0 )
      {
        if ( SbFromHpCore(v1172) )
          StreamClose(v1172);
        v1172 = 0;
        vhpstm = 0;
        Error(327845);
        errDeferred = 0;
        v1158 = 0;
        MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1516);
        MaxPathStzPoke::~MaxPathStzPoke((MaxPathStzPoke *)v1495);
        goto LABEL_1083;
      }
      v693 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1184);
      v694 = (LXBASE *)OpenTelemetry::POpenFileStageModel(v693);
      v695 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1415, 0x1F0CB5C3u);
      SXVWGEOM::RwFirst(v695);
      WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v694);
      v696 = BKORWS::Psh((BKORWS *)&v1184);
      v697 = v1162;
      v698 = v1172;
      v699 = v696;
      v700 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1516);
      v701 = (wchar_t *)SlicerViewImpl::PSlicerView((SlicerViewImpl *)v1495);
      v1244 = FLoadForeign(v1575, v701, v700, v698, a5, a8, &v1265, v697, (struct XLOSRR *)&v1240, v1278, v699);
      v702 = v1244;
      MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1516);
      MaxPathStzPoke::~MaxPathStzPoke((MaxPathStzPoke *)v1495);
      if ( v702 == -2 )
      {
        v1158 = 0;
        goto LABEL_1323;
      }
      v1158 = v1244;
      if ( !v702 )
      {
LABEL_1323:
        if ( OSRR::FReadyForOsr((OSRR *)&v1240) )
        {
          v68 = v1163;
          v407 = v1166;
          v1160 = 1;
          goto LABEL_744;
        }
        v1157 = -2146827284;
        v114 = -2146827284;
        XlsDiag::LogSetHrCoreTag(-2146827284, 0x230E205u);
      }
      v597 = v1159;
      if ( v1159 )
      {
        if ( (unsigned int)IMsoOLDocument::IsInFileSys(v1162) )
        {
          if ( v1158
            || (v703 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL), *(_QWORD *)(v703 + 40))
            && (*(_DWORD *)(*(_QWORD *)(v703 + 40) + 884LL) & 0x200) != 0 )
          {
            v704 = (wchar_t **)XLSBOOK::Plxtab(*(XLSBOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                       + 304LL)
                                                           + 40LL));
            FreeHpstTempPath((struct STB *)v704, v705);
            v706 = FileSource::StzFilePath((FileSource *)v1310);
            if ( (int)HrStDupSt(v706, v704 + 21) < 0 )
              v704[21] = 0;
          }
        }
      }
      goto LABEL_1272;
    }
    v1172 = 0;
    if ( v1215 != 1 )
    {
      sub_1413EF4D0();
      goto LABEL_997;
    }
    LOBYTE(v547) = v1188;
    v548 = sub_141224EE0(v1162, v547, &v1200);
    v1215 = v548;
    if ( v1200 )
    {
      OSRR::SetAppAllowed((OSRR *)&v1240, 0);
LABEL_997:
      v548 = v1215;
    }
    if ( v548 < 0 )
    {
      v114 = v548;
      XlsDiag::LogSetHrCoreTag(v548, 0x1797718u);
      v584 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1184);
      v585 = OpenTelemetry::POpenFileStageModel(v584);
      v586 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1411, 0x1F0CB5C6u);
      v587 = SXVWGEOM::RwFirst(v586);
      WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v585, 2214658821LL, v587);
      goto LABEL_1093;
    }
    if ( v1159 && !vpoldocument )
      vpoldocument = v1162;
    errDeferred = 0;
    if ( !v1174 )
    {
      v549 = BOOKO::Plocaleinfo((BOOKO *)&vapp);
      if ( FStBundled(v549, &v1572) )
        StripProjNameSt(&v1572, 257);
      goto LABEL_1005;
    }
    v555 = BOOKO::Plocaleinfo((BOOKO *)&vapp);
    if ( FStBundled(v555, &v1572) )
      StripProjNameSt(&v1572, 257);
    v168 = v1176;
LABEL_1026:
    v1174 = 1;
    v556 = FileSource::HrGetFileTemp(v1310, 6);
    v1157 = v556;
    v114 = v556;
    if ( v556 < 0 )
    {
      XlsDiag::LogSetHrCoreTag(v556, 0x274139Eu);
      Error(327845);
      goto LABEL_466;
    }
    v557 = 1049729;
    if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                   + 104LL) != 2 )
      v557 = 1025;
    v1172 = FileSource::StreamOpen((FileSource *)v1310, v557, 0);
    while ( 1 )
    {
      if ( a7 == 1024 )
        goto LABEL_1053;
      if ( !SbFromHpCore(v1172) )
        goto LABEL_1053;
      v558 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
      if ( *(_QWORD *)(v558 + 40) )
      {
        if ( (*(_DWORD *)(*(_QWORD *)(v558 + 40) + 884LL) & 0x200) != 0 )
          goto LABEL_1053;
      }
      if ( v168 || !(unsigned int)FIsExecutableFile(*((void **)v1172 + 1)) )
        break;
      v168 = 1;
      v1176 = 1;
      v1219 = 1;
      StreamClose(v1172);
LABEL_1038:
      v559 = 1048704;
      if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                     + 104LL) != 2 )
        v559 = 0;
      v1172 = FileSource::StreamOpen((FileSource *)v1310, ((v168 != 0) + 1024) | (unsigned int)v559, 0);
      v560 = 0;
      if ( !v1162 )
        goto LABEL_1043;
      errDeferred = _IMsoOLDocument_GetDeferredError(v1162);
      v561 = errDeferred == 0;
      if ( !errDeferred )
      {
        v560 = 0;
LABEL_1043:
        if ( !v168 )
        {
          if ( SbFromHpCore(v1172) )
            v560 = 0;
          else
            v560 = (unsigned __int16)v1172;
        }
        errDeferred = v560;
        v561 = v560 == 0;
      }
      if ( !v561 )
        goto LABEL_1026;
    }
    v562 = FileSource::HrGetFileTemp(v1310, 8);
    v1157 = v562;
    v114 = v562;
    if ( v562 < 0 )
    {
      XlsDiag::LogSetHrCoreTag(v562, 0x27413A0u);
      goto LABEL_1088;
    }
    v563 = BKORWS::Psh((BKORWS *)v1355);
    if ( !(unsigned int)sub_140798AF0(v563, (__int64)v1344, (__int64)v1310, a16, (__int64)&v1240) )
    {
LABEL_1089:
      v582 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
      *(_DWORD *)(v582 + 2024) = 0;
      *(_DWORD *)(v582 + 2028) = 0;
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1225;
      LOBYTE(v264) = 0;
      StreamClose(v1172);
      v68 = v1163;
      if ( v1163 )
      {
        v583 = PivotOperationBase::PSxview((PivotOperationBase *)v1163);
        *((_WORD *)v583 + 18) |= 8u;
      }
      v114 = -2146827284;
      XlsDiag::LogSetHrCoreTag(-2146827284, 0x179770Fu);
      goto LABEL_518;
    }
LABEL_1053:
    if ( SbFromHpCore(v1172) )
      goto LABEL_1022;
  }
  while ( (_WORD)v1172 != 2 );
  v564 = FileSource::HrGetFileTemp(v1310, 9);
  v1157 = v564;
  v114 = v564;
  if ( v564 < 0 )
  {
    XlsDiag::LogSetHrCoreTag(v564, 0x27413A1u);
LABEL_1088:
    Error(327845);
    goto LABEL_1089;
  }
  v565 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1184);
  v566 = (LXBASE *)OpenTelemetry::POpenFileStageModel(v565);
  v567 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1410, 0x1F0CB5C8u);
  SXVWGEOM::RwFirst(v567);
  WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v566);
  if ( !XllFlighting::FComponentizedXlls(v568) )
  {
    v1294 = 0;
    v574 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1355);
    v114 = HrRidLoadDLLFile_Deprecated(v574, &v1294, &v1171);
    v1157 = v114;
    if ( v114 < 0 )
      goto LABEL_1133;
    if ( v1294 )
    {
LABEL_1065:
      errDeferred = 0;
      v1158 = 3;
    }
    else
    {
      v573 = 506057947;
      v114 = -2147287008;
      v1157 = -2147287008;
LABEL_1064:
      XlsDiag::LogSetHrCoreTag(-2147287008, v573);
      OkAlert(196759, v1573);
    }
    goto LABEL_439;
  }
  v569 = BKORWS::Psh((BKORWS *)v1355);
  v570 = PcellwGuard::PcellwGuard((PcellwGuard *)v1506, v569);
  LOBYTE(v571) = 1;
  XllFileFromOutsideCalc = XllHost::HrLoadXllFileFromOutsideCalc(*(_QWORD *)v570, v571, 0);
  v1171 = XllFileFromOutsideCalc;
  if ( XllFileFromOutsideCalc >= 0 )
    goto LABEL_1065;
  if ( XllFileFromOutsideCalc == -2080308478 )
  {
    v573 = 36758018;
    v114 = -2147287008;
    v1157 = -2147287008;
    goto LABEL_1064;
  }
LABEL_1133:
  if ( !v1171 )
  {
    MsoShipAssertTagProc(545059735);
    if ( !v1171 )
      v1171 = -2080308954;
  }
  v607 = NtCurrentTeb()->ThreadLocalStoragePointer;
  vfPretendNotStg = 0;
  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v607 + 304LL) + 336LL) = v1225;
  XlsDiag::LogSetHrCoreTag(-2146827284, 0x17976D3u);
  LOBYTE(v608) = std::nullopt;
  std::optional<Measurements::MeasureElapsedTime>::operator=(v1517, v608);
  LOBYTE(v609) = std::nullopt;
  sub_14240D350(v1529, v609);
  OsfOpenScope::Destroy((OsfOpenScope *)v1490);
  XslClear((struct XSL *)&v1546);
  ClearStatusString(11);
  v610 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
  if ( *(_QWORD *)(v610 + 40) != v1306 )
    XlsDiag::SendTraceTag(20509321, 187, 10, 4, L"Jumped during load, global book changed");
  if ( v1307 )
  {
    v610 = 304;
    if ( *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL) == v1307 )
    {
      XlsDiag::SendTraceTag(20509322, 187, 10, 4, L"Jumping after loading a book, possibly corrupt");
      if ( !BOOK::Pioldoc(*(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL)) )
      {
        HrFreeBook(*(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL));
        v611 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1374, 0x237630DEu);
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
  if ( v1308 != (struct SH *)65534 )
  {
    v1121 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1375, 0x237630DDu);
    v1122 = SXVWGEOM::RwFirst(v1121);
    v1123 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 128LL);
    v1124 = 0;
    while ( v1123 )
    {
      v1124 = v1123[1];
      if ( v1124 )
        break;
      v1123 = (_QWORD *)*v1123;
    }
    LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v1124 + 96), v1308, v1122);
  }
  if ( v1187 )
    Mso::PerfScenario::HrEndScenario(
      (Mso::PerfScenario *)&vmsoperfidOfficeXLFileOpen,
      (const struct Mso::PerfScenario::MsoPerfScenarioId *)v610);
  if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL) + 8LL)
      & 1) != 0 )
  {
    CrashAlert(0, "Crash in FFileLoad (ignoreable/informational)");
    if ( v1158 && lp )
      FailBookLoad(lp);
    if ( iUseSentinelFile > 0 && hObject != (HANDLE)-1LL )
    {
      CloseHandle(hObject);
      hObject = (HANDLE)-1LL;
    }
  }
  v1125 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
  *(_DWORD *)(v1125 + 2024) = 0;
  *(_DWORD *)(v1125 + 2028) = 0;
  GLOBALS::GLOBALSCONTAINER::m_fs = 0;
  sub_1411BF070();
  sub_141232FB0();
  LOBYTE(v1126) = std::nullopt;
  std::optional<FutureFunctionLabelCreationTracker>::operator=(v1521, v1126);
  LOBYTE(v1127) = std::nullopt;
  std::optional<AutomaticNumberConversionLoadPasteHelper>::operator=(v1349, v1127);
  LOBYTE(v1128) = std::nullopt;
  sub_14240D390(v1239, v1128);
  std::optional<XlSecurity::XllTelemetry>::~optional<XlSecurity::XllTelemetry>(v1356);
  v606 = v1171;
  if ( v1171 < 0 )
  {
    v1048 = 512506062;
LABEL_2135:
    XlsDiag::LogSetHrCoreTag(v606, v1048);
  }
LABEL_2136:
  sub_140475EA0(v1239);
  std::optional<AutomaticNumberConversionLoadPasteHelper>::~optional<AutomaticNumberConversionLoadPasteHelper>(v1349);
  std::optional<FutureFunctionLabelCreationTracker>::~optional<FutureFunctionLabelCreationTracker>(v1521);
  FileSource::~FileSource((FileSource *)v1310);
  MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1355);
  MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1353);
  MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1487);
  MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1344);
  MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1467);
  MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1345);
  std::optional<OlDocFilePath>::~optional<OlDocFilePath>(v1544);
  Mso::TCntPtr<Uxpp::UxppAnnotationsService>::~TCntPtr<Uxpp::UxppAnnotationsService>(&v1257);
  std::_Optional_destruct_base<Measurements::MeasureElapsedTime,0>::~_Optional_destruct_base<Measurements::MeasureElapsedTime,0>(v1517);
  sub_140474FD0(v1529);
  std::pair<enum Osf::ModifierKeyFlags const,std::wstring>::~pair<enum Osf::ModifierKeyFlags const,std::wstring>(v1551);
  std::unique_ptr<Measurements::StartOrContinueCapture,HeapDeleter<Measurements::StartOrContinueCapture>>::~unique_ptr<Measurements::StartOrContinueCapture,HeapDeleter<Measurements::StartOrContinueCapture>>(&v1277);
  std::unique_ptr<XlsActivity::XlsDetachedActivity,HeapDeleter<XlsActivity::XlsDetachedActivity>>::~unique_ptr<XlsActivity::XlsDetachedActivity,HeapDeleter<XlsActivity::XlsDetachedActivity>>(&v1316);
  Mso::TCntPtr<IWebAddInOptionalProperties>::~TCntPtr<IWebAddInOptionalProperties>(&v1184);
  Mso::TCntPtr<Uxpp::UxppAnnotationsService>::~TCntPtr<Uxpp::UxppAnnotationsService>(&v1281);
  std::optional<NumberConversionSettingsOverride>::~optional<NumberConversionSettingsOverride>(v1524);
  OsfOpenScope::~OsfOpenScope((OsfOpenScope *)v1490);
  FishbowlTracker::~FishbowlTracker((FishbowlTracker *)v1545);
  std::_Optional_destruct_base<CorruptionMetaData,0>::~_Optional_destruct_base<CorruptionMetaData,0>(v1543);
  std::_Optional_destruct_base<SecuritySettings::ExternalLinks::TrustedLocationCacheScope,0>::~_Optional_destruct_base<SecuritySettings::ExternalLinks::TrustedLocationCacheScope,0>(v1197);
  std::optional<XlSecurity::XllTelemetry>::~optional<XlSecurity::XllTelemetry>(v1356);
  sub_140474B60(&v1213);
  sub_140474C80(&v1195);
  return (unsigned int)v606;
}

```

## disassembly

```asm
0x1402eeff0  mov     [rsp-8+arg_10], r8d
0x1402eeff6  push    rbp
0x1402eeff7  push    rbx
0x1402eeff8  push    rsi
0x1402eeff9  push    rdi
0x1402eeffa  push    r12
0x1402eeffc  push    r13
0x1402eeffe  push    r14
0x1402ef000  push    r15
0x1402ef002  lea     rbp, [rsp-0F428h]
0x1402ef00a  mov     eax, 0F588h
0x1402ef00f  call    _alloca_probe
0x1402ef014  sub     rsp, rax
0x1402ef017  mov     rax, cs:__security_cookie
0x1402ef01e  xor     rax, rsp
0x1402ef021  mov     [rbp+0F460h+var_50], rax
0x1402ef028  mov     rax, [rbp+0F460h+arg_40]
0x1402ef02f  mov     ebx, r9d
0x1402ef032  mov     r13, [rbp+0F460h+arg_28]
0x1402ef039  mov     r15, [rbp+0F460h+arg_70]
0x1402ef040  mov     rdi, [rbp+0F460h+arg_88]
0x1402ef047  mov     r14, [rbp+0F460h+arg_98]
0x1402ef04e  mov     [rbp+0F460h+var_F4A8], rax
0x1402ef052  mov     [rbp+0F460h+var_F370], rax
0x1402ef059  mov     rax, [rbp+0F460h+arg_60]
0x1402ef060  mov     [rbp+0F460h+var_F2E8], rax
0x1402ef067  mov     rax, [rbp+0F460h+arg_68]
0x1402ef06e  mov     [rbp+0F460h+var_EDE0], rax
0x1402ef075  mov     rax, [rbp+0F460h+arg_80]
0x1402ef07c  mov     [rbp+0F460h+var_F300], rax
0x1402ef083  mov     rax, [rbp+0F460h+arg_90]
0x1402ef08a  mov     [rbp+0F460h+var_F2D0], rax
0x1402ef091  xor     eax, eax
0x1402ef093  mov     [rbp+0F460h+var_F384], eax
0x1402ef099  mov     [rbp+0F460h+var_F4B0], rcx
0x1402ef09d  mov     [rbp+0F460h+Src], rcx
0x1402ef0a4  lea     esi, [rax+1]
0x1402ef0a7  mov     [rbp+0F460h+var_F3E0], edx
0x1402ef0ad  mov     [rbp+0F460h+var_F457], sil
0x1402ef0b1  mov     [rbp+0F460h+var_F418], ebx
0x1402ef0b4  mov     [rbp+0F460h+var_F0D0], r13
0x1402ef0bb  mov     [rbp+0F460h+var_F2C8], r15
0x1402ef0c2  mov     [rbp+0F460h+var_F258], rdi
0x1402ef0c9  mov     [rbp+0F460h+var_F0C8], r14
0x1402ef0d0  call    sub_1402DAC5C
0x1402ef0d5  xor     eax, eax
0x1402ef0d7  mov     [rbp+0F460h+var_F42B], sil
0x1402ef0db  lea     rcx, byte_143FDFC30
0x1402ef0e2  mov     [rbp+0F460h+var_EF90], al
0x1402ef0e8  call    ??BFeatureGate@Optimized@AB@Mso@@QEGBA_NXZ; Mso::AB::Optimized::FeatureGate::operator bool(void)
0x1402ef0ed  mov     r12d, [rbp+0F460h+arg_78]
0x1402ef0f4  test    al, al
0x1402ef0f6  jz      short loc_1402EF15C
0x1402ef0f8  xor     eax, eax
0x1402ef0fa  mov     [rbp+0F460h+var_F3D5], sil
0x1402ef101  lea     rcx, [rbp+0F460h+var_EFA8]
0x1402ef108  mov     [rbp+0F460h+var_F114], eax
0x1402ef10e  call    ??1?$optional@VXllTelemetry@XlSecurity@@@std@@QEAA@XZ; std::optional<XlSecurity::XllTelemetry>::~optional<XlSecurity::XllTelemetry>(void)
0x1402ef113  lea     r8, [rbp+0F460h+var_F3D5]
0x1402ef11a  lea     rdx, [rbp+0F460h+var_F114]
0x1402ef121  lea     rcx, [rbp+0F460h+var_EFA8]
0x1402ef128  call    ??$_Construct@W4Entry@XllTelemetry@XlSecurity@@_N@?$_Optional_construct_base@VXllTelemetry@XlSecurity@@@std@@QEAAAEAVXllTelemetry@XlSecurity@@$$QEAW4Entry@23@$$QEA_N@Z; std::_Optional_construct_base<XlSecurity::XllTelemetry>::_Construct<XlSecurity::XllTelemetry::Entry,bool>(XlSecurity::XllTelemetry::Entry &&,bool &&)
0x1402ef12d  lea     rcx, [rbp+0F460h+var_EFA8]
0x1402ef134  call    ??C?$optional@VXllTelemetry@XlSecurity@@@std@@QEAAPEAVXllTelemetry@XlSecurity@@XZ; std::optional<XlSecurity::XllTelemetry>::operator->(void)
0x1402ef139  mov     rcx, rax
0x1402ef140  call    cs:__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x1402ef146  lea     r9d, [rsi+3]
0x1402ef14a  mov     r8d, r12d
0x1402ef14d  mov     rcx, rax
0x1402ef150  lea     rdx, aLoadreason; "LoadReason"
0x1402ef157  call    ??$Add@H@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBDHW4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<int>(char const *,int,Mso::Logging::DataClassifications)
0x1402ef15c  xor     eax, eax
0x1402ef15e  mov     [rbp+0F460h+var_F453], al
0x1402ef161  call    ?FGetFlagsShadowBag@CircularReferenceTailValue@@MEBA_NAEAV?$TCntPtr@VShadowBag@Api@@@Mso@@@Z; CircularReferenceTailValue::FGetFlagsShadowBag(Mso::TCntPtr<Api::ShadowBag> &)
0x1402ef166  test    al, al
0x1402ef168  jz      short loc_1402EF17D
0x1402ef16a  lea     rcx, [rbp+0Ch]
0x1402ef16f  call    ??1?$_Optional_destruct_base@VTrustedLocationCacheScope@ExternalLinks@SecuritySettings@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<SecuritySettings::ExternalLinks::TrustedLocationCacheScope,0>::~_Optional_destruct_base<SecuritySettings::ExternalLinks::TrustedLocationCacheScope,0>(void)
0x1402ef174  lea     rcx, [rbp+0F460h+var_F454]
0x1402ef178  call    ??$_Construct@$$V@?$_Optional_construct_base@VTrustedLocationCacheScope@ExternalLinks@SecuritySettings@@@std@@QEAAAEAVTrustedLocationCacheScope@ExternalLinks@SecuritySettings@@XZ; std::_Optional_construct_base<SecuritySettings::ExternalLinks::TrustedLocationCacheScope>::_Construct<>(void)
0x1402ef17d  xor     eax, eax
0x1402ef17f  mov     [rbp+0F460h+var_F4B8], al
0x1402ef182  mov     rax, cs:?m_posi@UIGLOBALSCONTAINER@UIGLOBALS@@0PEAVOSI@@EA; OSI * UIGLOBALS::UIGLOBALSCONTAINER::m_posi
0x1402ef189  test    rax, rax
0x1402ef18c  jz      short loc_1402EF1AD
0x1402ef18e  mov     rcx, [rax+620h]
0x1402ef195  xor     eax, eax
0x1402ef197  test    rcx, rcx
0x1402ef19a  jz      short loc_1402EF1AF
0x1402ef19c  mov     eax, 4000h
0x1402ef1a1  test    [rcx+0Ch], ax
0x1402ef1a5  jz      short loc_1402EF1AD
0x1402ef1a7  mov     edx, esi
0x1402ef1a9  xor     eax, eax
0x1402ef1ab  jmp     short loc_1402EF1B1
0x1402ef1ad  xor     eax, eax
0x1402ef1af  mov     edx, eax
0x1402ef1b1  mov     ecx, [rbp+0F460h+arg_48]
0x1402ef1b7  mov     [rbp+0F460h+var_F4D8], eax
0x1402ef1ba  mov     [rbp+0F460h+var_F48E], al
0x1402ef1bd  mov     [rbp+0F460h+var_F31C], eax
0x1402ef1c3  mov     [rbp+0F460h+var_F2F0], rax
0x1402ef1ca  mov     [rbp+0F460h+var_F48F], al
0x1402ef1cd  mov     [rbp+0F460h+var_F250], rax
0x1402ef1d4  mov     [rbp+0F460h+var_F2F8], rax
0x1402ef1db  mov     [rbp+0F460h+var_F2C0], rax
0x1402ef1e2  mov     [rbp+0F460h+var_F0E0], rax
0x1402ef1e9  mov     [rbp+0F460h+var_F308], rax
0x1402ef1f0  mov     [rbp+0F460h+var_F3E8], eax
0x1402ef1f3  mov     [rbp+0F460h+lp], rax
0x1402ef1f7  mov     [rbp+0F460h+var_F45C], al
0x1402ef1fa  mov     [rbp+0F460h+var_F49F], al
0x1402ef1fd  mov     [rbp+0F460h+var_F274], eax
0x1402ef203  mov     [rbp+0F460h+var_F3C8], eax
0x1402ef209  mov     [rbp+0F460h+var_F404], eax
0x1402ef20c  mov     [rbp+0F460h+var_F4DC], eax
0x1402ef20f  mov     [rbp+0F460h+var_F3D0], eax
0x1402ef215  mov     [rbp+0F460h+var_8100], rax
0x1402ef21c  mov     eax, ecx
0x1402ef21e  and     eax, esi
0x1402ef220  mov     [rbp+0F460h+var_F488], edx
0x1402ef223  mov     [rbp+0F460h+var_F120], eax
0x1402ef229  mov     eax, ecx
0x1402ef22b  and     eax, 2
0x1402ef22e  mov     [rbp+0F460h+var_F44C], 100h
0x1402ef235  mov     [rbp+0F460h+var_F110], eax
0x1402ef23b  mov     eax, 8
0x1402ef240  mov     [rbp+0F460h+var_80F8], 0FFFFFFFFh
0x1402ef24a  test    al, cl
0x1402ef24c  jz      short loc_1402EF25D
0x1402ef24e  xor     eax, eax
0x1402ef250  cmp     cs:?vpoldocument@@3PEAUIMsoOLDocument@@EA, rax; IMsoOLDocument * vpoldocument
0x1402ef257  jnz     short loc_1402EF25D
0x1402ef259  test    edx, edx
0x1402ef25b  jz      short loc_1402EF28B
0x1402ef25d  nop     dword ptr [rax]
0x1402ef260  call    ?FOsrc@@YAHXZ; FOsrc(void)
0x1402ef265  xor     ecx, ecx
0x1402ef267  test    eax, eax
0x1402ef269  jnz     short loc_1402EF285
0x1402ef26b  xor     eax, eax
0x1402ef26d  cmp     cs:?m_vpxlosrea@OSRH@@0PEAUXLOSREA@@EA, rcx; XLOSREA * OSRH::m_vpxlosrea
0x1402ef274  setnz   al
0x1402ef277  test    eax, eax
0x1402ef279  jnz     short loc_1402EF285
0x1402ef27b  mov     ecx, [rbp+0F460h+arg_48]
0x1402ef281  xor     eax, eax
0x1402ef283  jmp     short loc_1402EF28D
0x1402ef285  mov     ecx, [rbp+0F460h+arg_48]
0x1402ef28b  mov     eax, esi
0x1402ef28d  mov     [rbp+0F460h+var_F358], eax
0x1402ef293  mov     eax, 130h
0x1402ef298  test    cl, 10h
0x1402ef29b  jnz     short loc_1402EF2C5
0x1402ef29d  mov     edx, eax
0x1402ef29f  mov     rax, gs:58h
0x1402ef2a8  mov     rcx, [rax]
0x1402ef2ab  mov     rax, [rdx+rcx]
0x1402ef2af  xor     ecx, ecx
0x1402ef2b1  cmp     [rax+6B0h], ecx
0x1402ef2b7  jnz     short loc_1402EF2C5
0x1402ef2b9  xor     eax, eax
0x1402ef2c0  cmp     [rbp+0F460h+var_F488], eax
0x1402ef2c3  jz      short loc_1402EF2D4
0x1402ef2c5  call    ?FOsrc@@YAHXZ; FOsrc(void)
0x1402ef2ca  test    eax, eax
0x1402ef2cc  jnz     short loc_1402EF2D2
0x1402ef2ce  mov     eax, esi
0x1402ef2d0  jmp     short loc_1402EF2D4
0x1402ef2d2  xor     eax, eax
0x1402ef2d4  mov     [rbp+0F460h+var_F2A4], eax
0x1402ef2da  lea     rcx, [rbp+0F460h+var_5F90]; void *
0x1402ef2e1  xor     eax, eax
0x1402ef2e3  mov     [rbp+0F460h+hObject], 0FFFFFFFFFFFFFFFFh
0x1402ef2ee  xor     edx, edx; Val
0x1402ef2f0  mov     [rbp+0F460h+var_F484], al
0x1402ef2f3  mov     r8d, 202h; Size
0x1402ef2f9  mov     [rbp+0F460h+var_F400], eax
0x1402ef2fc  mov     [rbp+0F460h+var_F4A0], al
0x1402ef2ff  mov     [rbp+0F460h+var_F46F], al
0x1402ef302  mov     [rbp+0F460h+var_F368], rax
0x1402ef309  mov     [rbp+0F460h+var_F324], eax
0x1402ef30f  mov     [rbp+0F460h+var_F468], eax
0x1402ef312  mov     [rbp+0F460h+var_F470], al
0x1402ef315  mov     [rbp+0F460h+var_F483], al
0x1402ef318  mov     [rbp+0F460h+var_F240], rax
0x1402ef31f  mov     [rbp+0F460h+var_F45B], al
0x1402ef322  mov     [rbp+0F460h+var_F46D], al
0x1402ef325  mov     [rbp+0F460h+var_F435], al
0x1402ef328  mov     [rbp+0F460h+var_F482], al
0x1402ef32b  call    memset_0
0x1402ef330  xor     eax, eax
0x1402ef332  mov     [rbp+0F460h+var_F428], esi
0x1402ef335  test    ebx, ebx
0x1402ef337  mov     [rbp+0F460h+var_F2A0], eax
0x1402ef33d  mov     [rbp+0F460h+var_F314], eax
0x1402ef343  setnz   [rbp+0F460h+var_F3D8]
0x1402ef34a  mov     [rbp+0F460h+var_F424], al
0x1402ef34d  mov     [rbp+0F460h+var_F350], rax
0x1402ef354  mov     [rbp+0F460h+var_F220], 0FFFEh
0x1402ef35f  mov     [rbp+0F460h+var_F3B0], eax
0x1402ef365  mov     [rbp+0F460h+var_F3A8], eax
0x1402ef36b  mov     [rbp+0F460h+var_F3A0], rax
0x1402ef372  mov     [rbp+0F460h+var_F398], eax
0x1402ef378  mov     [rbp+0F460h+var_F4D3], al
0x1402ef37b  mov     [rbp+0F460h+var_F448], eax
0x1402ef37e  mov     [rbp+0F460h+var_F464], al
0x1402ef381  mov     [rbp+0F460h+var_F284], eax
0x1402ef387  mov     [rbp+0F460h+var_F49D], al
0x1402ef38a  mov     [rbp+0F460h+var_F49E], al
0x1402ef38d  call    ?CountBooks@@YAHXZ; CountBooks(void)
0x1402ef392  mov     dl, cs:?equivalent@weak_ordering@std@@2U12@B; std::weak_ordering const std::weak_ordering::equivalent
0x1402ef398  lea     r8, [rbp+618h]
0x1402ef3a0  mov     [rbp+0F460h+var_F338], eax
0x1402ef3a6  lea     rcx, [rbp+0F460h+var_E4B0]
0x1402ef3ad  xor     eax, eax
0x1402ef3af  mov     [rbp+0F460h+var_F354], 80004005h
0x1402ef3b9  mov     [rbp+0F460h+var_F481], al
0x1402ef3bc  mov     [rbp+0F460h+var_F3D7], al
0x1402ef3c2  mov     [rbp+0F460h+var_F3F0], al
0x1402ef3c5  lea     rax, ?m_memheapMain@TSGLOBALSCONTAINER@TSGLOBALS@@0VCommonMemoryHeap@@A; CommonMemoryHeap TSGLOBALS::TSGLOBALSCONTAINER::m_memheapMain
0x1402ef3cc  mov     [rbp+0F460h+var_EE48], rax
0x1402ef3d3  call    ??$?0PEAVIMemHeap@@@?$_Deleted_move_assign@U?$_Optional_construct_base@VCorruptionMetaData@@@std@@VCorruptionMetaData@@@std@@QEAA@Uin_place_t@1@$$QEAPEAVIMemHeap@@@Z; std::_Deleted_move_assign<std::_Optional_construct_base<CorruptionMetaData>,CorruptionMetaData>::_Deleted_move_assign<std::_Optional_construct_base<CorruptionMetaData>,CorruptionMetaData>(std::in_place_t,IMemHeap * &&)
0x1402ef3d8  xor     eax, eax
0x1402ef3da  lea     rcx, [rbp+0F460h+var_BD80]; this
0x1402ef3e1  xor     edx, edx; bool
0x1402ef3e3  mov     [rbp+0F460h+var_F2E0], eax
0x1402ef3e9  call    ??0FishbowlTracker@@QEAA@_N@Z; FishbowlTracker::FishbowlTracker(bool)
0x1402ef3ee  lea     rcx, [rbp+0F460h+var_EE38]; this
0x1402ef3f5  call    ??0OpenWorkbooksTracker@@QEAA@XZ; OpenWorkbooksTracker::OpenWorkbooksTracker(void)
0x1402ef3fa  xor     eax, eax
0x1402ef3fc  mov     [rbp+0F460h+var_F438], sil
0x1402ef400  mov     [rbp+0F460h+var_F450], al
0x1402ef403  lea     rcx, [rbp+0F460h+var_EC50]; this
0x1402ef40a  mov     [rbp+0F460h+var_F42F], al
0x1402ef40d  mov     [rbp+0F460h+var_F437], al
0x1402ef410  mov     [rbp+0F460h+var_F46C], al
0x1402ef413  mov     eax, [rbp+0F460h+arg_48]
0x1402ef419  shr     eax, 14h
0x1402ef41c  and     al, sil
0x1402ef41f  mov     [rbp+0F460h+var_F436], al
0x1402ef422  call    ??0OsfOpenScope@@QEAA@XZ; OsfOpenScope::OsfOpenScope(void)
0x1402ef427  mov     rax, gs:58h
0x1402ef430  mov     edx, 130h
0x1402ef435  mov     [rbp+0F460h+var_F248], rdx
0x1402ef43c  mov     rcx, [rax]
0x1402ef43f  mov     rax, [rdx+rcx]
0x1402ef443  xor     ecx, ecx
0x1402ef445  cmp     [rax+7E8h], ecx
0x1402ef44b  jz      short loc_1402EF458
0x1402ef44d  mov     ecx, 2562102h
0x1402ef452  call    cs:__imp_MsoShipAssertTagProc
0x1402ef458  call    ?Instance@?$FeatureGateCollectionBase@VLoadSaveFeatureGates@@@@SAAEBVLoadSaveFeatureGates@@XZ; FeatureGateCollectionBase<LoadSaveFeatureGates>::Instance(void)
0x1402ef45d  mov     ecx, 8
0x1402ef462  add     rcx, rax
0x1402ef465  call    ??BFeatureGate@Optimized@AB@Mso@@QEGBA_NXZ; Mso::AB::Optimized::FeatureGate::operator bool(void)
0x1402ef46a  movzx   eax, al
0x1402ef46d  xor     eax, esi
0x1402ef46f  mov     cs:dword_143FDFCF8, eax
0x1402ef475  xor     eax, eax
0x1402ef477  cmp     cs:?vfBootInitStartupFolder@@3HA, eax; int vfBootInitStartupFolder
0x1402ef47d  jnz     short loc_1402EF4C6
0x1402ef47f  cmp     cs:?vfBootInstallAddins@@3HA, eax; int vfBootInstallAddins
0x1402ef485  jnz     short loc_1402EF4C6
0x1402ef487  call    ?Instance@?$FeatureGateCollectionBase@VPerformanceFeatureGates@@@@SAAEBVPerformanceFeatureGates@@XZ; FeatureGateCollectionBase<PerformanceFeatureGates>::Instance(void)
0x1402ef48c  lea     rcx, ?c_cgADO11394021@PerformanceFeatureGates@@2VChangeGate@Optimized@AB@Mso@@B; Mso::AB::Optimized::ChangeGate const PerformanceFeatureGates::c_cgADO11394021
0x1402ef493  call    ??BChangeGate@Optimized@AB@Mso@@QEGBA_NXZ; Mso::AB::Optimized::ChangeGate::operator bool(void)
0x1402ef498  test    al, al
0x1402ef49a  jnz     short loc_1402EF4BA
0x1402ef49c  lea     rcx, ?vmsoperfidOfficeXLBoot@@3UMsoPerfScenarioId@PerfScenario@Mso@@B; Mso::PerfScenario::MsoPerfScenarioId const vmsoperfidOfficeXLBoot
0x1402ef4a3  call    cs:__imp_?FScenarioActive@PerfScenario@Mso@@YA_NPEBUMsoPerfScenarioId@12@@Z; Mso::PerfScenario::FScenarioActive(Mso::PerfScenario::MsoPerfScenarioId const *)
0x1402ef4a9  test    al, al
0x1402ef4ab  jz      short loc_1402EF4BA
0x1402ef4ad  lea     rcx, ?vmsoperfidOfficeXLBoot@@3UMsoPerfScenarioId@PerfScenario@Mso@@B; Mso::PerfScenario::MsoPerfScenarioId const vmsoperfidOfficeXLBoot
0x1402ef4b4  call    cs:__imp_?HrCancelScenario@PerfScenario@Mso@@YAJPEBUMsoPerfScenarioId@12@@Z; Mso::PerfScenario::HrCancelScenario(Mso::PerfScenario::MsoPerfScenarioId const *)
0x1402ef4ba  mov     cl, sil
0x1402ef4c0  call    cs:__imp_?SetActivationKind@BootActivity@Mso@@SAXW4ActivationKind@12@@Z; Mso::BootActivity::SetActivationKind(Mso::BootActivity::ActivationKind)
0x1402ef4c6  lea     rcx, ?vmsoperfidOfficeXLFileOpen@@3UMsoPerfScenarioId@PerfScenario@Mso@@B; Mso::PerfScenario::MsoPerfScenarioId const vmsoperfidOfficeXLFileOpen
0x1402ef4cd  call    cs:__imp_?HrBeginScenario@PerfScenario@Mso@@YAJPEBUMsoPerfScenarioId@12@@Z; Mso::PerfScenario::HrBeginScenario(Mso::PerfScenario::MsoPerfScenarioId const *)
0x1402ef4d3  mov     ebx, eax
0x1402ef4d5  mov     [rbp+0F460h+var_F3D4], 44h ; 'D'
0x1402ef4df  xor     eax, eax
0x1402ef4e1  shr     ebx, 1Fh
0x1402ef4e4  xor     bl, sil
0x1402ef4e7  mov     [rbp+0F460h+var_F460], eax
0x1402ef4ea  mov     [rbp+0F460h+var_F32C], eax
0x1402ef4f0  mov     [rbp+0F460h+var_F038], rax
0x1402ef4f7  mov     eax, cs:?iUseSentinelFile@@3HA; int iUseSentinelFile
0x1402ef4fd  mov     [rbp+0F460h+var_F46E], bl
0x1402ef500  cmp     eax, 0FFFFFFFFh
0x1402ef503  jnz     short loc_1402EF518
0x1402ef505  lea     rcx, ?vmsoridExcelUseSentinelFile@@3U_msoreg@@B; _msoreg const vmsoridExcelUseSentinelFile
0x1402ef50c  call    cs:__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z; MsoDwRegGetDw(_msoreg const *)
0x1402ef512  mov     cs:?iUseSentinelFile@@3HA, eax; int iUseSentinelFile
0x1402ef518  test    eax, eax
0x1402ef51a  jns     short loc_1402EF53B
0x1402ef51c  xor     eax, eax
0x1402ef51e  lea     rcx, ?vmsoridExcelUseSentinelFile@@3U_msoreg@@B; _msoreg const vmsoridExcelUseSentinelFile
0x1402ef525  xor     edx, edx
0x1402ef527  mov     cs:?iUseSentinelFile@@3HA, eax; int iUseSentinelFile
  ... truncated ...
```
