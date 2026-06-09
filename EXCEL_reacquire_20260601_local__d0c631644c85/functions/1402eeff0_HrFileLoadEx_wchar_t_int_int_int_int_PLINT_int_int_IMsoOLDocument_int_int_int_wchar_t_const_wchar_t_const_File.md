# HrFileLoadEx(wchar_t *,int,int,int,int,PLINT * *,int,int,IMsoOLDocument * *,int,int,int,wchar_t const *,wchar_t const *,FileLoadContext *,XlLoadReason,wchar_t const *,XlSyncStateChangeListenerLoad *,VersionHistoryWindowParams *,int *)

- ea: `0x1402eeff0`
- end: `0x1402fc7df`
- name: `?HrFileLoadEx@@YAJPEA_WHHHHPEAPEAUPLINT@@HHPEAPEAUIMsoOLDocument@@HHHPEB_W3PEAVFileLoadContext@@W4XlLoadReason@@3PEAVXlSyncStateChangeListenerLoad@@PEAVVersionHistoryWindowParams@@PEAH@Z`
- size: `55279`
- prototype: ``
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
  __int64 v98; // rcx
  __int64 v99; // rax
  const wchar_t *v100; // rax
  const wchar_t *v101; // rax
  __int64 v102; // rax
  bool v103; // bl
  struct IMemHeap *v104; // r15
  ZrtUtility *v105; // rax
  const wchar_t *v106; // rdx
  ExpressionService *v107; // rax
  struct WORKBOOKCOLLECTION *v108; // rax
  OlDocFilePath *v109; // rbx
  struct OpenTelemetry *v110; // rax
  OlDocFilePath *v111; // rbx
  SXVWGEOM *v112; // rax
  unsigned int v113; // eax
  int v114; // eax
  int v115; // r15d
  OlDocFilePath *v116; // rax
  struct IMsoOLDocument *v117; // rbx
  ZrtUtility *v118; // rax
  struct IMsoOLDocument *v119; // r9
  ArtUserInterfaceSite *v120; // rbx
  bool v121; // dl
  OpenTelemetry *v122; // rax
  struct OpenTelemetry *v123; // rax
  OlDocFilePath *v124; // rax
  const struct OlDocFilePath *v125; // rax
  int v126; // eax
  OlDocFilePath *v127; // rax
  const wchar_t *v128; // rax
  int v129; // eax
  const wchar_t *v130; // rax
  struct IMsoOLDocument *v131; // rbx
  struct IMemHeap *v132; // rax
  OlDocFilePath *v133; // rax
  const wchar_t *v134; // rax
  const wchar_t *v135; // rax
  IMsoOLDocument *v136; // rcx
  __int64 (__fastcall *v137)(struct IMsoOLDocument *, const wchar_t *, unsigned int *, __int64); // rbx
  const wchar_t *v138; // rax
  int v139; // edi
  int v140; // eax
  OpenTelemetry *v141; // rax
  const wchar_t *v142; // rax
  BOOL v143; // r14d
  bool v144; // di
  unsigned int v145; // ebx
  unsigned int v146; // eax
  BKORWS *v147; // rcx
  const wchar_t *v148; // rax
  __int64 v149; // r9
  wchar_t *v150; // r8
  wchar_t *v151; // rdi
  const wchar_t *v152; // rax
  wchar_t *v153; // rbx
  const wchar_t *v154; // rax
  __int64 v155; // rcx
  const wchar_t *v156; // rax
  unsigned int v157; // ebx
  char v158; // si
  struct IMsoOLDocumentCoauth *v159; // rax
  SXVWGEOM *v160; // rax
  unsigned int v161; // eax
  SXVWGEOM *v162; // rax
  unsigned int v163; // eax
  struct LXTAB *v164; // rax
  struct LXTAB *v165; // rbx
  const wchar_t *v166; // rax
  wchar_t *v167; // rbx
  char v168; // al
  int v169; // esi
  int v170; // eax
  const wchar_t *v171; // rbx
  struct IMemHeap *v172; // rax
  int v173; // eax
  char v174; // al
  int v175; // eax
  struct BOOK *v176; // r8
  bool v177; // al
  struct SH **v178; // rcx
  BOOK *v179; // rax
  struct IMsoOLDocument *v180; // rax
  struct IMsoOLDocument *v181; // rcx
  __int64 v182; // rax
  char v183; // di
  __int64 v184; // rax
  char v185; // al
  int v186; // ebx
  BKORWS *v187; // rax
  struct IMsoOLDocumentCoauth *v188; // rax
  SXVWGEOM *v189; // rax
  unsigned int v190; // eax
  SXVWGEOM *v191; // rax
  unsigned int v192; // eax
  struct IMsoOLDocument *v193; // rdi
  __int64 v194; // rbx
  SXVWGEOM *v195; // rax
  unsigned int v196; // eax
  __int64 v197; // r9
  __int64 v198; // r8
  BOOK *v199; // rbx
  SXVWGEOM *v200; // rax
  unsigned int v201; // eax
  struct IMsoOLDocument *v202; // rax
  __int64 v203; // r8
  struct IMsoOLDocument *v204; // rcx
  SXVWGEOM *v205; // rax
  unsigned int v206; // eax
  BOOK *v207; // rbx
  SXVWGEOM *v208; // rax
  unsigned int v209; // eax
  bool v210; // r14
  __int64 v211; // rsi
  char v212; // di
  char v213; // bl
  struct IMsoOLDocument *v214; // rax
  unsigned int v215; // edx
  const wchar_t *v216; // rax
  __int64 v217; // rcx
  int v218; // ebx
  int v219; // eax
  const struct CXO *v220; // rax
  unsigned int v221; // r8d
  struct BOOK *v222; // rax
  __int64 v223; // rcx
  int inited; // eax
  char v225; // cl
  SXVWGEOM *v226; // rax
  unsigned int v227; // eax
  _QWORD *v228; // rdx
  __int64 v229; // rcx
  _QWORD *v230; // r8
  struct WNX *v231; // rbx
  unsigned __int64 v232; // rax
  SH *v233; // rcx
  struct BOOK *v234; // rax
  __int64 v235; // r8
  __int64 v236; // rax
  struct BOOK *v237; // rax
  SXVWGEOM *v238; // rax
  unsigned int v239; // eax
  _QWORD *v240; // rdx
  __int64 v241; // rcx
  _QWORD *v242; // r8
  SXVWGEOM *v243; // rax
  unsigned int v244; // eax
  _QWORD *v245; // rdx
  __int64 v246; // rcx
  _QWORD *v247; // r8
  unsigned int v248; // edx
  ExpressionService *v249; // rax
  struct WORKBOOKCOLLECTION *v250; // rax
  OlDocFilePath *v251; // rbx
  SXVWGEOM *v252; // rax
  unsigned int v253; // eax
  __int64 v254; // rax
  __int64 v255; // rax
  const wchar_t *Target; // rax
  unsigned int v257; // edx
  const struct OlDocFilePath *v258; // rax
  int v259; // eax
  __int64 v260; // r8
  OlDocFilePath *v261; // rax
  const wchar_t *v262; // rax
  void *v263; // rax
  __int64 v264; // rax
  struct STGI *v265; // r12
  void *v266; // rax
  int v267; // eax
  int v268; // eax
  int v269; // edi
  unsigned int v270; // ebx
  struct IStorage *v271; // rax
  int v272; // eax
  bool v273; // bl
  struct IStorage *v274; // rax
  int v275; // ebx
  int v276; // eax
  wchar_t *v277; // rdi
  wchar_t *v278; // rdi
  int v279; // esi
  struct IMemHeap *v280; // rax
  int v281; // ebx
  wchar_t *v282; // rax
  int CnvTempFile; // eax
  MaxPathStzPoke *v284; // rcx
  int v285; // ebx
  wchar_t *v286; // rax
  int v287; // eax
  const wchar_t *v288; // rax
  const wchar_t *v289; // rax
  int v290; // eax
  __int64 v291; // rcx
  const wchar_t *v292; // rax
  struct OpenTelemetry *v293; // rax
  __int64 v294; // rax
  LXBASE *v295; // rbx
  SXVWGEOM *v296; // rax
  struct STGI *v297; // rax
  int v298; // ebx
  int v299; // eax
  BKORWS *v300; // rcx
  struct SH *v301; // rax
  struct ISlicerView *v302; // rax
  AppGuard::Config *v303; // rcx
  int v304; // eax
  void *v305; // rcx
  __int64 v306; // rax
  __int64 v307; // rbx
  SXVWGEOM *v308; // rax
  unsigned int v309; // eax
  int v310; // ebx
  struct IMemHeap *v311; // rdi
  const struct ILocaleInfo *v312; // rax
  int v313; // edi
  unsigned int v314; // edx
  int v315; // ecx
  MaxPathHolder *v316; // rcx
  __int64 v317; // rax
  CorruptionMetaData *v318; // rax
  CorruptionMetaData *v319; // rbx
  char v320; // al
  __int64 v321; // rax
  __int64 v322; // rax
  __int64 v323; // rax
  LXBASE *v324; // rbx
  SXVWGEOM *v325; // rax
  int v326; // eax
  unsigned int v327; // r8d
  int v328; // ecx
  __int64 v329; // r9
  const wchar_t *v330; // rax
  __int64 v331; // rax
  __int64 v332; // rbx
  SXVWGEOM *v333; // rax
  unsigned int v334; // eax
  __int64 v335; // rdx
  int v336; // edi
  struct IMemHeap *v337; // rax
  wchar_t *v338; // rax
  const wchar_t *v339; // rbx
  const wchar_t *v340; // rax
  struct SH *v341; // rbx
  struct BOOK *v342; // rax
  __int64 v343; // rax
  int v344; // eax
  unsigned int v345; // ebx
  int v346; // ecx
  __int64 v347; // r8
  char v348; // r14
  unsigned int v349; // edx
  int v350; // ecx
  struct SH *v351; // rax
  XlsActivity *v352; // rsi
  struct SH *v353; // rdi
  unsigned __int8 v354; // al
  unsigned int v355; // edx
  struct SH *v356; // rax
  XlsActivity *v357; // rsi
  struct SH *v358; // rdi
  bool v359; // cl
  int v360; // eax
  char v361; // cl
  int v362; // ecx
  const struct ILocaleInfo *v363; // rax
  unsigned __int16 v364; // ax
  int v365; // edi
  __int64 v366; // rax
  __int64 v367; // rbx
  SXVWGEOM *v368; // rax
  unsigned int v369; // eax
  unsigned __int16 v370; // ax
  int v371; // ebx
  unsigned __int16 v372; // di
  char v373; // si
  unsigned int v374; // edx
  int v375; // ecx
  const struct ILocaleInfo *v376; // rax
  OlDocFilePath *v377; // rax
  const struct Mso::Clp::IClpDocument *v378; // rbx
  struct IStorage *EncryptedStorage; // rax
  __int64 v380; // rax
  int DeferredError; // eax
  int v382; // eax
  int v383; // ebx
  char v384; // al
  struct IMemHeap *v385; // rax
  int FileTemp; // eax
  __int64 v387; // r8
  const wchar_t *v388; // rax
  struct FileSource *v389; // rdx
  bool v390; // bl
  const wchar_t *v391; // rax
  wchar_t *v392; // rdx
  __int64 v393; // rdx
  int v394; // eax
  __int64 v395; // rax
  __int64 v396; // rbx
  SXVWGEOM *v397; // rax
  unsigned int v398; // eax
  bool v399; // al
  BOOL v400; // eax
  struct SH *v401; // rax
  int v402; // ecx
  __int64 v403; // rax
  __int64 v404; // rbx
  SXVWGEOM *v405; // rax
  unsigned int v406; // eax
  __int64 v407; // rdx
  struct XPACKAGE *v408; // rax
  struct IMsoOLDocument **v409; // rsi
  __int64 *v410; // rax
  __int64 v411; // rcx
  __int64 v412; // rax
  __int64 v413; // rcx
  struct SXVIEW *v414; // rax
  int v415; // ecx
  __int64 v416; // rax
  LXBASE *v417; // rbx
  SXVWGEOM *v418; // rax
  struct SH *v419; // r13
  OlDocFilePath *v420; // rax
  struct SH *v421; // r14
  struct IMsoDocumentEncryptor *v422; // r15
  int v423; // edi
  struct OpenTelemetry *v424; // r12
  int v425; // esi
  int v426; // ebx
  struct ISlicerView *v427; // rax
  int v428; // r8d
  void *v429; // rax
  struct Api::Workbook *v430; // rax
  __int64 v431; // rcx
  OcsTransitionController *v432; // rax
  XLSBOOK *v433; // rax
  SlicerViewImpl *v434; // rax
  TAB *v435; // rbx
  OcsTransitionController *v436; // rax
  XLSBOOK *v437; // rax
  TAB *v438; // r12
  void *v439; // r14
  struct SH *v440; // rax
  unsigned __int8 v441; // al
  SXVWGEOM *v442; // rax
  unsigned int v443; // edi
  struct SH *v444; // rax
  __int64 v445; // rdx
  __int64 v446; // rcx
  _QWORD *v447; // r8
  _QWORD *v448; // rdx
  __int64 v449; // rax
  SXVWGEOM *v451; // rax
  unsigned int v452; // eax
  _QWORD *v453; // rdx
  __int64 v454; // rcx
  _QWORD *v455; // r8
  struct WNX *v456; // rcx
  const wchar_t *v457; // rax
  CorruptionMetaData *v458; // rax
  struct SXVIEW *v459; // rax
  __int64 v460; // rax
  __int64 v461; // rax
  __int64 v462; // rbx
  SXVWGEOM *v463; // rax
  unsigned int v464; // eax
  __int64 v465; // rax
  struct SXVIEW *v466; // rax
  unsigned int v467; // edi
  struct IStorage *v468; // rax
  int v469; // eax
  __int64 v470; // rax
  __int64 v471; // rcx
  OlDocFilePath *v472; // rax
  const struct Mso::Clp::IClpDocument *v473; // rbx
  struct IStorage *v474; // rax
  bool v475; // al
  OlDocFilePath *v476; // rax
  const struct Mso::Clp::IClpDocument *v477; // rbx
  struct IStorage *v478; // rax
  int v479; // ebx
  struct SXVIEW *v480; // rax
  const wchar_t *v481; // rax
  struct IMemHeap *v482; // rax
  int v483; // eax
  __int64 v484; // rax
  LXBASE *v485; // rbx
  SXVWGEOM *v486; // rax
  const wchar_t *v487; // rax
  int v488; // eax
  SXVWGEOM *v489; // rax
  unsigned int v490; // eax
  _QWORD *v491; // rdx
  __int64 v492; // rcx
  _QWORD *v493; // r8
  const wchar_t *v494; // rax
  struct WNX *v495; // rcx
  __int64 v496; // r8
  int v497; // eax
  __int64 v498; // rbx
  const wchar_t *v499; // rax
  __int64 v500; // rcx
  __int64 v501; // rcx
  unsigned int v502; // r8d
  struct IMsoOLDocument **v503; // rsi
  SXVWGEOM *v504; // rax
  unsigned int v505; // eax
  bool v506; // al
  __int64 v507; // rax
  struct SXVIEW *v508; // rax
  __int64 v509; // rax
  wchar_t **v510; // rbx
  const wchar_t *v511; // rax
  __int64 v512; // rax
  BOOK *v513; // rbx
  SXVWGEOM *v514; // rax
  unsigned int v515; // eax
  __int64 v516; // r8
  Mso::Telemetry::Activity *v517; // rbx
  struct IMsoOLDocumentCoauth *v518; // rax
  SXVWGEOM *v519; // rax
  unsigned int v520; // eax
  struct Mso::Telemetry::IDataFieldCollection *v521; // rax
  unsigned int v522; // edi
  struct Mso::Telemetry::IDataFieldCollection *v523; // rax
  BOOK *v524; // rcx
  struct IMsoXmlDataStore *v525; // rbx
  struct IMsoOLDocument *v526; // rax
  __int64 v527; // rax
  __int64 v528; // rcx
  struct OfficeSpace::IOutSpace *OutSpace; // rdi
  void (__fastcall *v530)(struct OfficeSpace::IOutSpace *, _QWORD, struct IMsoOLDocument *); // rbx
  struct IMsoOLDocument *v531; // rax
  struct IMsoOLDocument *v532; // rax
  struct IMsoAddInX **v533; // rdx
  struct IMsoOLDocument *v534; // rax
  __int64 v535; // rax
  SXVWGEOM *v536; // rax
  unsigned int v537; // eax
  __int64 v538; // rax
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
  const wchar_t *v600; // rax
  const wchar_t *v601; // rax
  const wchar_t *v602; // rax
  int v603; // r13d
  int v604; // eax
  int v605; // ebx
  void *v606; // rax
  __int64 v607; // rdx
  __int64 v608; // rdx
  __int64 v609; // rdx
  SXVWGEOM *v610; // rax
  unsigned int v611; // eax
  _QWORD *v612; // rdx
  __int64 v613; // rcx
  int v614; // eax
  int v615; // eax
  __int64 v616; // rax
  LXBASE *v617; // rbx
  SXVWGEOM *v618; // rax
  int v619; // r14d
  wchar_t *v620; // rdi
  int v621; // eax
  struct SH *v622; // rax
  wchar_t *v623; // rax
  int BookXmlSpreadsheet; // eax
  __int64 v625; // rax
  wchar_t **v626; // rdi
  const wchar_t *v627; // rax
  SXVWGEOM *v628; // rax
  unsigned int v629; // eax
  struct SH *v630; // rax
  struct SH *v631; // rax
  int OptDialog; // eax
  BOOL v633; // r12d
  const wchar_t *v634; // rbx
  wchar_t *v635; // rax
  struct SH *v636; // rax
  struct IMsoOLDocument *v637; // rdi
  struct STM *v638; // r14
  struct OpenTelemetry *v639; // rbx
  const wchar_t *v640; // rsi
  wchar_t *v641; // rax
  void *v642; // rax
  struct IMsoOLDocument *v643; // rdi
  __int64 v644; // rcx
  void *v645; // rax
  int Project2; // eax
  int v647; // eax
  int HtmlFailed; // eax
  struct IMemHeap *v649; // rax
  const wchar_t *v650; // rdx
  const wchar_t *v651; // rbx
  const wchar_t *v652; // rax
  int Xml; // eax
  void *v654; // rax
  int v655; // edi
  struct IMsoOLDocument *v656; // rsi
  __int64 v657; // rcx
  void *v658; // rax
  XLSWORKBOOK *v659; // rax
  OcsTransitionController *v660; // rax
  struct Api::CoauthTransitionState *v661; // rax
  __int64 v662; // rcx
  int v663; // eax
  bool v664; // al
  int v665; // eax
  __int64 v666; // rcx
  XLSBOOK *v667; // rax
  SXVWGEOM *v668; // rax
  unsigned int v669; // eax
  struct IMsoOLDocument *v670; // r10
  int v671; // eax
  int v672; // ebx
  struct SH *v673; // rax
  int v674; // esi
  int v675; // ebx
  int v676; // edi
  wchar_t *v677; // rax
  int BookHtml; // eax
  __int64 v679; // rax
  wchar_t **v680; // rdi
  const wchar_t *v681; // rax
  __int64 v682; // rax
  __int64 v683; // rbx
  SXVWGEOM *v684; // rax
  unsigned int v685; // eax
  char v686; // al
  struct SXVIEW *v687; // rax
  struct IMemHeap *v688; // rax
  int v689; // eax
  __int64 v690; // rax
  LXBASE *v691; // rbx
  SXVWGEOM *v692; // rax
  struct SH *v693; // rax
  struct IMsoOLDocument *v694; // rdi
  struct STM *v695; // r14
  struct OpenTelemetry *v696; // rbx
  const wchar_t *v697; // rsi
  wchar_t *v698; // rax
  int v699; // ebx
  __int64 v700; // rax
  wchar_t **v701; // rdi
  const wchar_t *v702; // rax
  BOOL v703; // ebx
  BOOL v704; // r8d
  BOOL v705; // edi
  BOOL v706; // r9d
  __int64 v707; // rax
  __int64 v708; // r10
  const struct OLDocFactory *v709; // rax
  BOOK *v710; // rbx
  SXVWGEOM *v711; // rax
  unsigned int v712; // eax
  __int64 v713; // rcx
  void *v714; // rax
  __int64 v715; // rdx
  unsigned __int8 v716; // al
  unsigned int v717; // eax
  SXVWGEOM *v718; // rax
  unsigned int v719; // eax
  bool v720; // r8
  bool v721; // r13
  __int64 v722; // rax
  LXBASE *v723; // rbx
  SXVWGEOM *v724; // rax
  __int64 v725; // rax
  void *v726; // rax
  __int64 v727; // rax
  int v728; // eax
  char v729; // r12
  Mso::DocumentWindow::EventMgr *v730; // rcx
  WN *v731; // rcx
  UIFRAME *v732; // rax
  struct IMsoOLDocument *v733; // rbx
  Excel::XlMso *v734; // rax
  HWND v735; // r8
  struct IMsoOLDocument *v736; // rax
  struct Api::CoauthTransitionState *v737; // rbx
  unsigned int v738; // eax
  struct Api::Workbook *v739; // rax
  struct XlFileProtocol *Protocol; // rbx
  MsoReserveTag *v741; // rax
  struct BOOK *v742; // rdi
  unsigned int v743; // ebx
  struct SH *v744; // rax
  __int64 v745; // rax
  __int64 v746; // rdx
  _DWORD *v747; // rax
  __int64 v748; // rax
  struct Api::Workbook *v749; // rax
  XlAsyncFileIO *v750; // rax
  XlRenameHandler *v751; // rax
  unsigned int v752; // ebx
  __int64 v753; // rax
  __int64 v754; // rax
  struct Api::Workbook *v755; // rax
  struct IMerge *v756; // rax
  __int64 v757; // rax
  __int64 v758; // rax
  struct Api::Workbook *v759; // rax
  struct Mso::Telemetry::IDataFieldCollection *v760; // rbx
  unsigned int refreshed; // eax
  __int64 v762; // rax
  IEndpointAgent *v763; // rax
  ClassifyLabelProtectManager *v764; // rax
  IdleLoop *v765; // rcx
  __int64 v766; // rax
  AutoSaveManager *v767; // rax
  struct BOOKO *v768; // rdx
  int v769; // eax
  SXVWGEOM *v770; // rax
  unsigned int v771; // r10d
  __int64 v772; // rcx
  struct SH *v773; // r9
  _QWORD *v774; // rax
  __int64 v775; // rcx
  _QWORD *v776; // rdx
  __int64 v777; // rax
  struct WNX *v778; // rdi
  void *v779; // r14
  struct WNX *v780; // rax
  struct WNX *v781; // rbx
  struct WNX *v782; // rdx
  int v783; // ecx
  struct SH *v784; // r12
  SXVWGEOM *v785; // rax
  unsigned int v786; // eax
  __int64 v787; // rdx
  __int64 v788; // rcx
  _QWORD *v789; // r8
  _QWORD *v790; // rdx
  __int64 v791; // rdx
  __int64 v792; // rcx
  __int64 v793; // rax
  struct CS *v794; // rax
  SXVWGEOM *v795; // rax
  unsigned int v796; // eax
  __int64 v797; // rdx
  __int64 v798; // rcx
  _QWORD *v799; // r8
  _QWORD *v800; // rdx
  unsigned int v801; // edx
  MsoReserveTag *v802; // rcx
  __int64 v803; // rax
  __int64 v804; // r8
  int v805; // eax
  __int64 v806; // rax
  __int64 v807; // rax
  __int64 v808; // r8
  struct BOOK *v809; // r8
  IMsoOLDocument *v810; // rax
  struct IMsoOLDocument *v811; // rax
  struct IMsoOLDocument *v812; // rax
  unsigned int v813; // esi
  __int64 v814; // r14
  SXVWGEOM *v815; // rax
  unsigned int v816; // edi
  unsigned int v817; // ebx
  struct IMsoOLDocument *v818; // rax
  struct IMsoOLDocument *v819; // rax
  SXVWGEOM *v820; // rax
  unsigned int v821; // ebx
  struct IMsoOLDocument *v822; // rax
  struct IMsoOLDocument *v823; // rax
  struct IMsoOLDocument *v824; // rax
  struct IMsoOLDocument *v825; // rax
  struct IMsoOLDocument *v826; // rax
  struct IMsoOLDocument *v827; // rax
  const wchar_t *v828; // rax
  struct IMsoOLDocument *v829; // rax
  void *v830; // rax
  __int64 v831; // r8
  int v832; // eax
  __int64 v833; // rcx
  struct BOOK *v834; // rax
  SXVWGEOM *v835; // rax
  unsigned int v836; // ebx
  struct LXTAB *v837; // rax
  TAB *v838; // rax
  struct SH *v839; // rax
  _QWORD *v840; // rdx
  __int64 v841; // rcx
  _QWORD *v842; // r8
  int v843; // ebx
  const wchar_t *v844; // rax
  struct IMsoOLDocument *v845; // rax
  struct IMsoOLDocument *v846; // rax
  __int64 v847; // rcx
  const wchar_t *v848; // rax
  SXVWGEOM *v849; // rax
  unsigned int v850; // eax
  _QWORD *v851; // rdx
  __int64 v852; // rcx
  _QWORD *v853; // r8
  __int64 v854; // rcx
  struct BOOK *v855; // rcx
  const struct Api::Workbook *v856; // rax
  Excel::AppGuard::Actions **v857; // r8
  int v858; // eax
  wchar_t *v859; // rdi
  char v860; // si
  __int64 v861; // rcx
  struct BOOK *v862; // rbx
  __int64 v863; // r8
  SXVWGEOM *v864; // rax
  unsigned int v865; // eax
  _QWORD *v866; // r8
  __int64 v867; // rcx
  _QWORD *v868; // rdx
  __int64 v869; // rcx
  __int64 v870; // rax
  __int64 v871; // rcx
  __int64 v872; // rcx
  __int64 v873; // r8
  __int64 v874; // rax
  SXVWGEOM *v875; // rax
  unsigned int v876; // eax
  _QWORD *v877; // rdx
  __int64 v878; // rcx
  _QWORD *v879; // r8
  SXVWGEOM *v880; // rax
  unsigned int v881; // eax
  _QWORD *v882; // rdx
  __int64 v883; // rcx
  _QWORD *v884; // r8
  void *v885; // rax
  void *v886; // rax
  __int64 v887; // rcx
  __int64 v888; // rcx
  int v889; // eax
  __int64 v890; // rcx
  struct IMsoOLDocument *v891; // rax
  __int64 v892; // rcx
  struct IMsoOLDocument *v893; // rax
  SXVWGEOM *v894; // rax
  unsigned int v895; // eax
  __int64 v896; // rcx
  __int64 v897; // rax
  SXVWGEOM *v898; // rax
  unsigned int v899; // eax
  const struct Api::Workbook *v900; // rbx
  struct ExpressionService *v901; // rax
  _QWORD *v902; // rax
  _QWORD *v903; // rax
  __int64 v904; // rax
  void *v905; // rax
  struct XlsActivity *v906; // rbx
  const struct Api::Workbook *v907; // rax
  struct LXTAB *v908; // rbx
  TAB *v909; // rbx
  struct SH *v910; // rax
  unsigned __int8 v911; // cl
  struct SH *v912; // rax
  struct Mso::Telemetry::IDataFieldCollection *v913; // rax
  struct Mso::Telemetry::IDataFieldCollection *v914; // rax
  SXVWGEOM *v915; // rax
  unsigned int v916; // eax
  _QWORD *v917; // rdx
  __int64 v918; // rcx
  _QWORD *v919; // r8
  const wchar_t *v920; // rax
  __int64 v921; // rax
  OlDocFilePath *v922; // rax
  struct IMsoOLDocument *v923; // rbx
  SXVWGEOM *v924; // rax
  unsigned int v925; // eax
  SXVWGEOM *v926; // rax
  unsigned int v927; // eax
  __int64 v928; // rax
  __int64 v929; // rcx
  struct Api::Workbook *v930; // rax
  struct Mso::Telemetry::IDataFieldCollection *v931; // rax
  __int64 v932; // r8
  int v933; // edx
  unsigned __int64 v934; // rax
  struct IMsoOLDocument *v935; // rax
  CardView::DataElementRecord *v936; // rax
  PivotMetadataCache *v937; // rax
  OcsTransitionController *v938; // rax
  struct Api::CoauthTransitionState *v939; // rax
  struct IMsoOLDocument *v940; // rax
  char v941; // bl
  BKORWS *v942; // rdi
  CardView::DataElementRecord *v943; // rax
  struct SH *v944; // rbx
  __int64 v945; // rax
  struct SH *v946; // rbx
  struct Api::Workbook *v947; // rax
  struct QuickLoadContext *v948; // r8
  struct IMemHeap *v949; // rbx
  unsigned int v950; // edi
  struct Api::Workbook *v951; // rax
  XlAsyncFileIO *v952; // rax
  __int64 v953; // rax
  int v954; // eax
  bool v955; // cf
  __int64 v956; // r8
  struct Api::CoauthTransitionState *v957; // rax
  __int64 v958; // rax
  struct Api::Workbook *v959; // rax
  struct Api::Workbook *v960; // rbx
  const struct WN *v961; // r8
  struct IMemHeap *v962; // rdi
  struct BOOK *v963; // rcx
  unsigned int v964; // ebx
  ZrtUtility *v965; // rax
  int v966; // r9d
  __int64 v967; // rax
  BKORWS *v968; // rbx
  QuickLoadContext *v969; // rax
  int v970; // r8d
  struct BOOK *v971; // rdi
  __int64 v972; // rax
  __int64 v973; // rax
  BOOL v974; // ebx
  struct IMsoOLDocument *v975; // rax
  bool v976; // bl
  unsigned int Only; // eax
  struct IMsoOLDocument *v978; // rax
  struct IMsoOLDocument *v979; // rax
  Api::RichDataSharedManager *v980; // rax
  Api::LinkedEntityFeature *LinkedEntityFeature; // rax
  RichDataManagerHost *v982; // rax
  const struct Api::Workbook *v983; // rdx
  CleanupWorkbookStylesBusinessBar *v984; // rax
  struct Api::Workbook *v985; // rdx
  unsigned __int64 v986; // rbx
  unsigned int v987; // eax
  char v988; // al
  struct OSRC *Osrc; // rax
  int v990; // eax
  unsigned int v991; // edx
  CorruptionMetaData *v992; // rax
  char v993; // al
  LoadRecovery *v994; // rcx
  int v995; // edx
  unsigned __int64 v996; // rax
  int v997; // ebx
  bool v998; // al
  unsigned __int64 BookCorrupt; // rbx
  void *v1000; // rax
  unsigned __int64 v1001; // rax
  __int64 v1002; // rcx
  unsigned int v1003; // eax
  int v1004; // ebx
  const wchar_t *v1005; // rax
  int v1006; // r8d
  __int64 v1007; // r8
  wchar_t *v1008; // rbx
  const wchar_t *v1009; // rbx
  unsigned int v1010; // eax
  struct IMsoOLDocument **v1011; // rbx
  SXVWGEOM *v1012; // rax
  unsigned int v1013; // eax
  OlDocFilePath *v1014; // rax
  struct IMsoOLDocument **v1015; // rbx
  SXVWGEOM *v1016; // rax
  unsigned int v1017; // eax
  SXVWGEOM *v1018; // rax
  unsigned int v1019; // eax
  unsigned int v1020; // edx
  int v1021; // ecx
  int v1022; // eax
  unsigned int v1023; // edx
  int v1024; // eax
  int v1025; // ecx
  char v1026; // al
  unsigned int v1027; // eax
  unsigned __int64 Count; // rax
  UIFRAME *v1029; // rax
  HWND v1030; // rax
  __int64 v1031; // rax
  __int64 v1032; // rbx
  SXVWGEOM *v1033; // rax
  unsigned int v1034; // eax
  __int64 v1035; // rax
  __int64 v1036; // rax
  __int64 v1037; // rax
  __int64 v1038; // rax
  SXVWGEOM *v1039; // rax
  unsigned int v1040; // eax
  unsigned int v1041; // edx
  SXVWGEOM *v1042; // rax
  unsigned int v1043; // eax
  int v1044; // eax
  __int64 Title; // rax
  __int64 v1046; // rdx
  __int64 v1047; // rsi
  SXVWGEOM *v1048; // rax
  int v1049; // ebx
  Mso::Telemetry *v1050; // rax
  unsigned int v1051; // r9d
  int v1052; // eax
  __int64 v1053; // r8
  SXVWGEOM *v1054; // rax
  unsigned int v1055; // eax
  const wchar_t *v1056; // rax
  struct IMsoOLDocument *v1057; // rax
  __int64 v1058; // rdx
  ZrtUtility *v1059; // rax
  struct IMsoOLDocument *v1060; // rdx
  __int64 v1061; // rax
  CorruptionMetaData *v1062; // rax
  unsigned __int8 v1063; // al
  __int64 v1064; // r9
  __int64 v1065; // r8
  struct IMsoOLDocument *v1066; // rax
  struct BOOK *v1067; // r8
  int v1068; // eax
  CorruptionMetaData *v1069; // rax
  Mso::History *v1070; // rcx
  int v1071; // ecx
  int v1072; // ecx
  unsigned int v1073; // edx
  wchar_t *v1074; // rdx
  int v1075; // ecx
  ODFROBUSTLOAD *AffectedProcessSessionId; // rax
  wchar_t *v1077; // rdx
  int v1078; // ecx
  ODFROBUSTLOAD *v1079; // rax
  ODFROBUSTLOAD *v1080; // rax
  __int64 v1081; // rax
  __int64 v1082; // r8
  struct Api::Workbook *v1083; // rax
  struct IPowerQueryWorkbookManager *Manager; // rax
  struct IMsoOLDocument *v1085; // rax
  __int64 v1086; // rcx
  unsigned int v1087; // eax
  unsigned int v1088; // ebx
  int v1089; // eax
  int v1090; // edx
  int v1091; // eax
  __int64 v1092; // rax
  SXVWGEOM *v1093; // rax
  unsigned int v1094; // eax
  __int64 v1095; // r8
  __int64 v1096; // rax
  __int64 v1097; // rax
  int Sz; // ebx
  int v1099; // eax
  __int64 *v1100; // rcx
  int v1101; // ebx
  __int64 v1102; // rcx
  int v1103; // edx
  __int64 v1104; // rcx
  int v1105; // eax
  unsigned int v1106; // eax
  SXVWGEOM *v1107; // rax
  unsigned int v1108; // eax
  bool v1109; // dl
  SXVWGEOM *v1110; // rax
  SXVWGEOM *v1111; // rax
  unsigned int v1112; // eax
  const wchar_t *v1113; // rax
  SXVWGEOM *v1114; // rax
  unsigned int v1115; // eax
  _QWORD *v1116; // rdx
  __int64 v1117; // rcx
  __int64 *v1118; // rax
  __int64 v1119; // rcx
  __int64 v1120; // rax
  __int64 v1121; // rcx
  __int64 v1122; // rdx
  __int64 v1123; // rdx
  __int64 v1124; // rdx
  struct IStream **v1125; // [rsp+20h] [rbp-140h]
  struct IStream **v1126; // [rsp+20h] [rbp-140h]
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
  sub_1402DAC5C();
  v1209 = 1;
  v1351[24] = 0;
  v24 = Mso::AB::Optimized::FeatureGate::operator bool(&byte_143FDFC30);
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
  v36 = ((__int64 (*)(void))FeatureGateCollectionBase<LoadSaveFeatureGates>::Instance)();
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
      ((void (*)(void))sub_141232FB0)();
    if ( v1191 )
      sub_14240D410(&v1190);
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
    (*(void (__fastcall **)(void *, struct IMemHeap **, _QWORD))(qword_144012CB0 + 8LL))(&qword_144012CB0, &v1300, 0);
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
  sub_1402DB1D0(v1524, v57, v1531);
  if ( v1533 )
    sub_140475000(v1531);
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
          sub_140474FD0(v1524);
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
        v561 = v91 == 102;
        v92 = 4;
        if ( v561 )
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
  sub_1402DA5D0(&v1541, a6, v61);
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
  v72 = sub_1402DB550(v1255, &v1265);
  sub_1402DB470(v1234, v72);
  sub_1402DB490(v1255);
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
    v1008 = v1233;
    if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL) + 8LL)
        & 1) == 0
      && v1233 )
    {
      LoadRecovery::Destroy((LoadRecovery *)v1233);
      FreeHpst(v1008);
      v1008 = 0;
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
    v1130 = (struct LoadRecovery *)v1008;
    goto LABEL_2108;
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
    v115 = -2147024809;
    XlsDiag::LogSetHrCoreTag(-2147024809, 0x17976D5u);
    goto LABEL_2095;
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
      && (v98 = 0, *(_DWORD *)(*(_QWORD *)(v60 + *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer) + 1764LL)) )
    {
      operator|=(&v1196, 32);
    }
    v99 = FeatureGateCollectionBase<LoadSaveFeatureGates>::Instance(v98);
    if ( (unsigned __int8)Mso::AB::Optimized::FeatureGate::operator bool(v99 + 8) )
    {
      v100 = MaxPathHolder::SzPath((MaxPathHolder *)v1348);
      if ( MsoFIsInFileSysWzPersistentName(v100, 0) )
      {
        v101 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1348);
        if ( (unsigned int)FIsPathAnXll(v101, 1) )
          operator|=(&v1196, 32);
      }
    }
    if ( (a10 & 0x20000) != 0 )
      operator|=(&v1196, 256);
    LODWORD(v1125) = v1196;
    XlsDiag::SendTraceTag(41039177, 187, 100, L"FFileLoadEx: OlDocSetupFlags oldsf = 0x%x", v1125);
    if ( v89 && a16 == 16 && !(unsigned int)FOsrhInTransition() )
      operator|=(&v1196, 512);
    v102 = FeatureGateCollectionBase<ZipItFeatureGates>::Instance();
    if ( (unsigned __int8)Mso::AB::Optimized::FeatureGate::operator bool(v102 + 72) )
      v103 = 1;
    else
      v103 = v87 == 0;
    v104 = v1296;
    if ( v1296 )
    {
      v105 = (ZrtUtility *)MaxPathHolder::SzPath((MaxPathHolder *)v1348);
      if ( ZrtUtility::FCanUseServerOnlyAsyncOpen(v105, v106) && v103 )
        operator|=(&v1196, 1024);
    }
    v107 = TLSW::PesExpressionService(*(TLSW **)(v1298 + *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer));
    v108 = ExpressionService::Pwbkcoll(v107);
    RevisionLatencyOutlierTracker::RevisionLatencyOutlierTracker(v1530, v108, 16);
    v109 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
    v110 = BKORWS::Psh((BKORWS *)&v1179);
    OlDocFilePath::SetOpenTelemetry(v109, v110);
    operator|=(&v1196, 4096);
    v111 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
    v112 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1374, 0x236962C9u);
    v113 = SXVWGEOM::RwFirst(v112);
    v114 = OlDocFilePath::HrSetupAndRetrievePathTitle(
             v111,
             (struct FileSource *)v1305,
             &v1157,
             v82,
             &v1232,
             (enum OlDocSetupFlags *)&v1196,
             v104,
             v113,
             0,
             0);
    v115 = v114;
    if ( v114 < 0 )
      XlsDiag::LogSetHrCoreTag(v114, 0x27C1404u);
    RevisionLatencyOutlierTracker::~RevisionLatencyOutlierTracker((RevisionLatencyOutlierTracker *)v1530);
    v116 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
    if ( (int)OlDocFilePath::COpenCount(v116) > 1 )
      MsoShipAssertTagProc(505205964);
    if ( v1296 )
    {
      v117 = v1157;
      v118 = APPCORE::PmemheapMain((APPCORE *)&vapp);
      v1159 = ZrtUtility::FOpeningAsServerOnlyAsync(v118, v1296, v117, v119);
    }
    if ( v115 < 0 )
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
      v120 = (ArtUserInterfaceSite *)Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
      v121 = CoauthoringInternals::FCoauthoringFeatureEnabled() && XlAsyncFileIO::FCoauthorableFileIO(v1157);
      ArtUserInterfaceSite::SetCurrentToolLockState(v120, v121);
      v122 = (OpenTelemetry *)Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
      OpenTelemetry::SetPoldoc(v122, v1157);
    }
    v123 = BKORWS::Psh((BKORWS *)&v1179);
    XlFileProtocolManager::SetFallbackReason(v1157, v123);
    if ( v115 < 0
      || (v124 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1539),
          !(unsigned int)OlDocFilePath::CchPath(v124)) )
    {
      if ( v1157 )
      {
        v1332 = v1157;
        (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v1157 + 56LL))(
          v1157,
          0xFFFFFFFFLL,
          7);
        v1014 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
        OlDocFilePath::RecordEventForCloseOldoc(v1014, v1157, 0);
        v1015 = v1245;
        if ( v1245 && *v1245 == v1157 )
        {
          v1016 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1454, 0x236962C8u);
          v1017 = SXVWGEOM::RwFirst(v1016);
          OlDocFilePath::FReleaseIOLDoc(&v1332, 0, 1, v1017);
          *v1015 = v1332;
        }
        else
        {
          v1018 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1455, 0x236962C7u);
          v1019 = SXVWGEOM::RwFirst(v1018);
          OlDocFilePath::FReleaseIOLDoc(&v1332, 0, 1, v1019);
        }
      }
      goto LABEL_2095;
    }
    v125 = (const struct OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
    v126 = FileSource::HrSetOlDocFilePath((FileSource *)v1305, v125);
    v115 = v126;
    if ( v126 < 0 )
    {
      XlsDiag::LogSetHrCoreTag(v126, 0x279F29Cu);
      goto LABEL_2095;
    }
    v127 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
    v128 = OlDocFilePath::StzTitle(v127);
    if ( MaxPathHolder::FExceedsMaxFileName(*v128) )
    {
      Error(655635);
      if ( v1157 )
      {
        (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v1157 + 56LL))(
          v1157,
          0xFFFFFFFFLL,
          7);
        HrRecordEvent(v1157, 0x40000000u, 0);
        v1012 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1453, 0x236962C6u);
        v1013 = SXVWGEOM::RwFirst(v1012);
        OlDocFilePath::FReleaseIOLDoc(&v1157, 1, 1, v1013);
      }
      goto LABEL_2095;
    }
    v129 = XLFileIOMockable::HrSetPoldoc((struct FileSource *)v1305, v1157, v1274, v1213);
    v1152 = v129;
    v115 = v129;
    if ( v129 < 0 )
    {
      XlsDiag::LogSetHrCoreTag(v129, 0x279F29Du);
      goto LABEL_2095;
    }
    v130 = FileSource::StzFilePath((FileSource *)v1305);
    if ( !(unsigned int)FIsPathAnXll(v130, 1) )
    {
      v131 = v1157;
      v132 = APPCORE::PmemheapMain((APPCORE *)&vapp);
      Api::DataLossProtectionSessionManager::NotifyEvent(v132, 0, v131, 0);
    }
    if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 2972LL)
      && v1270
      && *v1270 )
    {
      CchSzToStz(v1270 + 1, &v1567, 257);
    }
    else
    {
      v133 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
      v134 = OlDocFilePath::StzTitle(v133);
      CchStToStz(v134, &v1567, 257);
    }
    MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1348, v82);
    v135 = MaxPathHolder::SzPath((MaxPathHolder *)v1348);
    if ( !MsoFIsInFileSysWzPersistentName(v135, 0) && v1567 > 0xF9u )
    {
      v1567 = 249;
      MakeStStzTruncOK(&v1567, 257);
    }
    v136 = v1157;
    vpoldocument = v1157;
    v1161 = v1245;
    if ( v89 )
    {
      if ( v1245 )
      {
        *v1245 = v1157;
        v136 = v1157;
      }
      else
      {
        v1161 = &v1157;
        v1245 = &v1157;
      }
    }
    if ( v1542 || !(unsigned int)IMsoOLDocument::IsInFileSys(v136) )
    {
      v82 = v1160;
    }
    else
    {
      v1541 |= 0x10u;
      v1257 = 0;
      MaxPathSzPoke::MaxPathSzPoke((MaxPathSzPoke *)v1487, (struct MaxPathHolder *)v1339);
      v1257 = MaxPathSzPoke::CchSzBufferSize((MaxPathSzPoke *)v1487);
      v137 = *(__int64 (__fastcall **)(struct IMsoOLDocument *, const wchar_t *, unsigned int *, __int64))(*(_QWORD *)v1157 + 64LL);
      v138 = AugmentationLoop::TranslateDetectLanguagesArrayAnnotationResponse::SzId((AugmentationLoop::TranslateDetectLanguagesArrayAnnotationResponse *)v1487);
      v139 = v137(v1157, v138, &v1257, 3);
      MaxPathSzPoke::~MaxPathSzPoke((MaxPathSzPoke *)v1487);
      if ( v139 < 0 )
      {
        if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1232LL)
                       + 32LL) )
        {
          v1009 = MaxPathHolder::SzPath((MaxPathHolder *)v1348);
          v1010 = MsoServerErrorTypeGet(0);
          MsoServerErrorAlert(v1010, v1009, 0);
        }
        v115 = v139;
        XlsDiag::LogSetHrCoreTag(v139, 0x26C77DFu);
        goto LABEL_1856;
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
    v140 = FileSource::HrSetPoldoc((FileSource *)v1305, v1157, v1274, v1213);
    v1152 = v140;
    v115 = v140;
    if ( v140 < 0 )
      XlsDiag::LogSetHrCoreTag(v140, 0x279F29Eu);
    if ( (unsigned __int8)std::shared_ptr<Mso::ActivityScope::IMsoLoggingScope>::operator bool(&v1179) )
    {
      v141 = (OpenTelemetry *)Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
      OpenTelemetry::SetPoldoc(v141, v1157);
    }
    if ( v115 < 0 )
    {
      OkAlert(196655, v1568);
      v1011 = v1245;
      goto LABEL_2087;
    }
    FileSource::FGetPathname((FileSource *)v1305, v82 + 1, *v82, &v1567, 257);
    v1161 = v1245;
  }
  if ( !(unsigned int)MaxPathHolder::CchLength((MaxPathHolder *)v1339) )
  {
    v142 = FileSource::StzFilePath((FileSource *)v1305);
    MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1339, v142);
  }
  v143 = v1258;
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
    v144 = 0;
    CchStToSz(v82, String1, 2084);
    if ( fInIdle && v1157 )
    {
      v145 = 2;
      if ( (int)MsoCchWzLen(String1) <= 2 )
      {
LABEL_229:
        v146 = a10;
        if ( (a10 & 0x80000) != 0 )
        {
          if ( !v1187 || (v147 = (BKORWS *)v1482, v143) )
            v147 = (BKORWS *)v1339;
          v148 = (const wchar_t *)BKORWS::Psh(v147);
          v561 = !FShouldOpenInAppGuard(v148, 0);
          v146 = a10;
          if ( v561 )
          {
            v146 = a10 & 0xFFFFEFFF;
            a10 &= ~0x1000u;
          }
        }
        if ( (v146 & 0x2000) != 0 )
        {
          v145 = 3;
        }
        else if ( (v146 & 0x10000) == 0 )
        {
          v145 = (v146 & 0x1000) != 0;
        }
        if ( v144 )
        {
          v149 = (unsigned int)MsoCchWzLen(String1);
          v150 = String1;
        }
        else
        {
          v149 = *v82;
          v150 = v82 + 1;
        }
        XlProtectionMockable::InitOSRR(&v1235, v145, v150, v149);
        goto LABEL_243;
      }
      if ( !wcsncmp(String1, L"\\\\", 2u)
        && !MsoFReservedWzPersistentName(String1)
        && FIsHttpRedirFile(String1, 0, 0, 0, 0) )
      {
        v144 = MsoFConvertHttpRedirUNCToHttp(String1, String1, 2084) != 0;
      }
    }
    v145 = 2;
    goto LABEL_229;
  }
LABEL_244:
  v151 = v1158;
  if ( v1158 )
  {
    v152 = (const wchar_t *)XLSBOOK::Plxtab((XLSBOOK *)v1158);
    if ( !(unsigned int)FHasPath(v152) )
    {
      v153 = (wchar_t *)XLSBOOK::Plxtab((XLSBOOK *)v151);
      v154 = FileSource::StzFilePath((FileSource *)v1305);
      CchStToSt(v154, v153, 2084);
    }
    if ( !v1280
      && (*((_BYTE *)PivotOperationBase::PSxview((PivotOperationBase *)v151) + 36) & 8) == 0
      && (unsigned int)ObjectModelState::FInCallback((ObjectModelState *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                    + 304LL)
                                                                        + 1200LL)) != 2 )
    {
      v155 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
      if ( (!*(_DWORD *)(*(_QWORD *)(v155 + 1232) + 80LL)
         || (unsigned int)ObjectModelState::FInCallback((ObjectModelState *)(v155 + 1200)) == 2)
        && !(unsigned int)ObjectModelState::FInCallback((ObjectModelState *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                       + 304LL)
                                                                           + 1200LL)) )
      {
        FStartLoadAction(
          2 - (v1249 != 0),
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                    + 104LL),
          (struct LoadRecovery *)v151);
      }
    }
  }
  if ( !v1542 )
  {
    CchStToStz(&v1567, v1570, 257);
    v156 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1339);
    MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1340, v156);
  }
  if ( v1157 )
  {
    v1282 = 0;
    v157 = (*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1157 + 80LL))(v1157);
    XlAsyncFileIO::SpOLDocCoauthFromPOLDoc(v1309, v1157);
    if ( v87
      || (v158 = 0, (unsigned __int8)std::shared_ptr<Mso::ActivityScope::IMsoLoggingScope>::operator bool(v1309))
      && (v159 = BKORWS::Psh((BKORWS *)v1309), XlAsyncFileIO::FIsDistributedBlobsFile(v159)) )
    {
      v158 = 1;
      v1168 = 1;
    }
    else
    {
      v1168 = 0;
    }
    v1184 = v158;
    v160 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1376, 0x21C730Du);
    v161 = SXVWGEOM::RwFirst(v160);
    OldocHelper::SetAttrInAttrMask(
      v1157,
      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1232LL) + 32LL) != 0
    ? 0x20000
    : 0,
      0x20000u,
      v161);
    (*(void (__fastcall **)(struct IMsoOLDocument *, struct IMsoPKMClient **))(*(_QWORD *)v1157 + 168LL))(v1157, &v1246);
    v162 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1377, 0x21C730Eu);
    v163 = SXVWGEOM::RwFirst(v162);
    OldocHelper::SetAttrInAttrMask(v1157, v157, 0x20000u, v163);
    if ( v1246 )
      (*(void (__fastcall **)(struct IMsoPKMClient *))(*(_QWORD *)v1246 + 104LL))(v1246);
    if ( (*(int (__fastcall **)(struct IMsoOLDocument *, int *, __int64))(*(_QWORD *)v1157 + 48LL))(v1157, &v1282, 20) >= 0
      && v1282 )
    {
      v115 = -2147467260;
      XlsDiag::LogSetHrCoreTag(-2147467260, 0x17976D7u);
      Mso::TCntPtr<Uxpp::UxppAnnotationsService>::~TCntPtr<Uxpp::UxppAnnotationsService>(v1309);
      goto LABEL_1866;
    }
    Mso::TCntPtr<Uxpp::UxppAnnotationsService>::~TCntPtr<Uxpp::UxppAnnotationsService>(v1309);
  }
  if ( v151 )
  {
    v164 = XLSBOOK::Plxtab((XLSBOOK *)v151);
    CchStToSt(&v1567, (wchar_t *)v164 + 2084, 257);
    v165 = XLSBOOK::Plxtab((XLSBOOK *)v151);
    *((_WORD *)v165 + *((unsigned __int16 *)XLSBOOK::Plxtab((XLSBOOK *)v151) + 2084) + 2085) = 0;
  }
  MaxPathSzPoke::MaxPathSzPoke((MaxPathSzPoke *)v1484, (struct MaxPathHolder *)v1348);
  v166 = 0;
  if ( v1211 )
  {
    v169 = v1171;
  }
  else
  {
    if ( v1157 )
    {
      if ( (unsigned int)IMsoOLDocument::IsInFileSys(v1157) )
        v166 = AugmentationLoop::TranslateDetectLanguagesArrayAnnotationResponse::SzId((AugmentationLoop::TranslateDetectLanguagesArrayAnnotationResponse *)v1484);
      else
        v166 = 0;
    }
    v167 = (wchar_t *)v166;
    v168 = FIsTrue<int>(vgrbitScanload & 2);
    v169 = v1171;
    v170 = sub_1402D97E0(v1157, (struct FileSource *)v1305, v1171 != 0, v168, v167, (struct OSRR *)&v1235);
    v1152 = v170;
    v115 = v170;
    if ( v170 < 0 )
    {
      XlsDiag::LogSetHrCoreTag(v170, 0x1E107807u);
LABEL_1867:
      MaxPathSzPoke::~MaxPathSzPoke((MaxPathSzPoke *)v1484);
      goto LABEL_1866;
    }
    v171 = v1267;
    if ( v1267 )
    {
      v172 = APPCORE::PmemheapMain((APPCORE *)&vapp);
      FileSource::FileSource((FileSource *)v1529, v172);
      v173 = FileSource::HrSetWin32PathSt((FileSource *)v1529, v171);
      if ( v173 < 0 )
        XlsDiag::LogSetHrCoreTag(v173, 0x1E109581u);
      v174 = FIsTrue<int>(vgrbitScanload & 2);
      v175 = sub_1402D97E0(v1157, (struct FileSource *)v1529, v169 != 0, v174, 0, (struct OSRR *)&v1235);
      v1152 = v175;
      v115 = v175;
      if ( v175 < 0 )
      {
        XlsDiag::LogSetHrCoreTag(v175, 0x1E107806u);
        FileSource::~FileSource((FileSource *)v1529);
        goto LABEL_1867;
      }
      FileSource::~FileSource((FileSource *)v1529);
    }
  }
  v1211 = 1;
  MaxPathSzPoke::~MaxPathSzPoke((MaxPathSzPoke *)v1484);
  v176 = PbookFromTitle(v1567, v1568);
  v1197 = v176;
  if ( v176 )
  {
    v177 = BOOK::FFailedToFreeWhileLoading(v176);
    v176 = v1197;
    if ( v177 || !*((_QWORD *)v1197 + 141) )
    {
      if ( !BOOK::FFailedToFreeWhileLoading(v1197) )
        MsoShipAssertTagProc(40981770);
      v176 = 0;
      v1197 = 0;
    }
    if ( v176 )
    {
      if ( (unsigned int)FOsrc() )
      {
        SetLoadForPreviewError(-2147024891);
        v1020 = 24737497;
        v1021 = -2147024891;
        v115 = -2147024891;
        goto LABEL_1869;
      }
      v176 = v1197;
    }
  }
  if ( v1155 && !v176 )
  {
    FixUpFileTitle(&v1567);
    v176 = PbookFromTitle(v1567, v1568);
    v1197 = v176;
  }
  v178 = *(struct SH ***)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
  if ( v178[5] )
  {
    v179 = v178[5];
    if ( (*((_DWORD *)v179 + 221) & 0x200) != 0 )
    {
      v180 = BOOK::Pioldoc(v179);
      v181 = v1157;
      if ( v1157 != v180 )
      {
        MsoShipAssertTagProc(1650811750);
        v181 = v1157;
      }
      if ( !v181 )
        goto LABEL_410;
      HrRecordEvent(v181, 0x40000000u, 0);
      v182 = FeatureGateCollectionBase<ZipItFeatureGates>::Instance();
      v183 = 0;
      if ( (unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(v182 + 424) )
      {
        v186 = v1242;
      }
      else
      {
        v184 = FeatureGateCollectionBase<ZipItFeatureGates>::Instance();
        v185 = Mso::AB::Optimized::ChangeGate::operator bool(v184 + 440);
        v186 = v1242;
        if ( !v185 )
          goto LABEL_306;
        v186 = v1242 | 1;
        v1242 |= 1u;
        v187 = (BKORWS *)XlAsyncFileIO::SpOLDocCoauthFromPOLDoc(v1438, v1157);
        v188 = BKORWS::Psh(v187);
        if ( !XlAsyncFileIO::FIsDistributedBlobsFile(v188) )
          goto LABEL_306;
      }
      v183 = 1;
LABEL_306:
      if ( (v186 & 1) != 0 )
      {
        v1242 = v186 & 0xFFFFFFFE;
        Mso::TCntPtr<Uxpp::UxppAnnotationsService>::~TCntPtr<Uxpp::UxppAnnotationsService>(v1438);
      }
      if ( v183 )
      {
        v1283 = -1;
        if ( (*(int (__fastcall **)(struct IMsoOLDocument *, int *))(*(_QWORD *)v1157 + 200LL))(v1157, &v1283) < 0
          || v1283 <= 0 )
        {
          MsoShipAssertTagProc(504410975);
        }
        if ( v169 )
        {
          MsoShipAssertTagProc(504414753);
          v189 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1378, 0x1E113313u);
          v190 = SXVWGEOM::RwFirst(v189);
          OldocHelper::SetReadOnly(v1157, v190);
        }
        else
        {
          v191 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1379, 0x1E113312u);
          v192 = SXVWGEOM::RwFirst(v191);
          OldocHelper::ClearReadOnly(v1157, v192);
        }
        v193 = v1157;
        v194 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL);
        v195 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1380, 0x1E10B250u);
        v196 = SXVWGEOM::RwFirst(v195);
        LOBYTE(v197) = 33;
        LOBYTE(v198) = 5;
        Mementos::LogObjectLifetimeEvent(v196, 3, v198, v197, v194, v193);
        (*(void (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1157 + 16LL))(v1157);
        if ( !(unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(&qword_144028920) )
        {
          v199 = *(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL);
          v200 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1381, 0x1E113311u);
          v201 = SXVWGEOM::RwFirst(v200);
          BOOK::SetPioldoc(v199, 0, v201);
        }
        v1178 = 0;
      }
      else
      {
        v202 = BOOK::Pioldoc(*(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL));
        v204 = v1157;
        if ( v1157 == v202 )
        {
          LOBYTE(v203) = 1;
          Mso::TRestorer<bool>::TRestorer<bool>(v1508, &XlFileProtocol::s_fInClose, v203);
          v1439 = v1157;
          v205 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1382, 0x236962C5u);
          v206 = SXVWGEOM::RwFirst(v205);
          OlDocFilePath::FReleaseIOLDoc(&v1439, 1, 0, v206);
          v207 = *(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL);
          v208 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1383, 0x236962C4u);
          v209 = SXVWGEOM::RwFirst(v208);
          BOOK::SetPioldoc(v207, 0, v209);
          Mso::TRestorer<bool>::~TRestorer<bool>(v1508);
          v204 = v1157;
        }
        v1178 = FBeginCmdIOLDoc(v204, v169 != 0 ? 4 : 2, 0, &v1232, 0);
      }
      goto LABEL_409;
    }
  }
  if ( !v176 || wProjLoad == 2 )
    goto LABEL_410;
  v561 = v176 == v178[5];
  v1268 = v178[4];
  v210 = !v561;
  v1275 = v178[13];
  if ( v178[13] )
  {
    SH::Pbook(*((SH **)v178[13] + 3));
    v176 = v1197;
  }
  v211 = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)v176 + 205) + 32LL))((__int64)v176 + 1640);
  v212 = 0;
  v213 = 0;
  v214 = BOOK::Pioldoc(v1197);
  if ( v1157 != v214 )
  {
    if ( !v211 )
    {
      v215 = 34146077;
LABEL_335:
      v212 = 1;
      XlsDiag::LogSetHrCoreTag(-2147467260, v215);
      goto LABEL_336;
    }
    if ( !OfficeSharedApiImpl::BusinessBarShowArgs::GetHideCloseButton((OfficeSharedApiImpl::BusinessBarShowArgs *)v1305)
      || (v216 = FileSource::StzFilePath((FileSource *)v1305), (unsigned int)CmpTextHp(v211, v216, 0xFFFFFFFFLL)) )
    {
      v212 = 1;
      XlsDiag::LogSetHrCoreTag(-2147467260, 0x209071Eu);
      v213 = 1;
    }
  }
  if ( !v213 )
  {
    v217 = *((_QWORD *)v1197 + 66);
    if ( v217 )
    {
      if ( *(_QWORD *)(v217 + 208) )
      {
        v215 = 34146079;
        goto LABEL_335;
      }
    }
  }
LABEL_336:
  if ( v212 )
  {
    if ( (a3 & 4) == 0 )
      OkAlert(196753, v1568);
    fCeCanceled = 1;
    v115 = -2147467260;
    XlsDiag::LogSetHrCoreTag(-2147467260, 0x2385704u);
    v1031 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
    v1032 = OpenTelemetry::POpenFileStageModel(v1031);
    v1033 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1456, 0x1F0CB5D3u);
    v1034 = SXVWGEOM::RwFirst(v1033);
    WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v1032, 2214658819LL, v1034);
    goto LABEL_1866;
  }
  if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1232LL) + 80LL) )
  {
    v218 = XLOSRR::FMustUseOsr((XLOSRR *)&v1235);
    if ( (unsigned int)FOsrhBook(v1197) != v218 )
    {
      v1022 = FOsrhBook(v1197);
      OkAlert(589891 - (v1022 != 0), 0);
      v1020 = 24737499;
      goto LABEL_1871;
    }
  }
  if ( (*((_DWORD *)v1197 + 221) & 0x100) != 0
    && *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1836LL) )
  {
    OkAlert(196948, v1568);
    v1023 = 24737500;
    goto LABEL_1873;
  }
  v1284 = 0;
  v219 = HrGroupAction(0, v1197, 9, 0, &v1284);
  if ( v219 < 0 )
  {
    v1166 = v219;
    goto LABEL_1133;
  }
  if ( v1284 )
  {
    v1020 = 24737501;
LABEL_1871:
    v115 = -2147024809;
    v1021 = -2147024809;
LABEL_1869:
    XlsDiag::LogSetHrCoreTag(v1021, v1020);
LABEL_1866:
    v68 = v1158;
LABEL_1856:
    v1011 = v1161;
    goto LABEL_2087;
  }
  if ( !FileSource::FFileExists((FileSource *)v1305) )
  {
    OkAlert(196655, v1568);
    v1024 = -2147319765;
    v1023 = 24737502;
    goto LABEL_1874;
  }
  if ( PcxoFromPbook(v1197) )
  {
    v220 = PcxoFromPbook(v1197);
    if ( (unsigned int)FCxoLocked(v220) )
    {
      if ( (*((_DWORD *)v1197 + 222) & 0x400) == 0 )
        Error(393653);
      v1023 = 24737503;
LABEL_1873:
      v1024 = -2147024809;
LABEL_1874:
      v115 = v1024;
      v1025 = v1024;
      goto LABEL_1875;
    }
  }
  v221 = 2;
  if ( (a3 & 2) == 0 )
  {
    if ( vfPastingHlink )
    {
      v1023 = 24737504;
    }
    else
    {
      if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1232LL)
                     + 32LL) == 2 )
        fCeCanceled = 1;
      if ( (*(_BYTE *)(*((_QWORD *)v1197 + 141) + 3058LL) & 0x18) != 0 )
      {
        v1026 = 1;
      }
      else
      {
        v1027 = FActivatePbook(v1197);
        v1026 = FIsTrue<int>(v1027);
      }
      v1176 = v1026;
      vfLoadAbortedOnActivatedAlreadyOpenedBook = v1026;
      if ( v1026 )
      {
        v1451 = "Unconditionally setting foreground window for already opened book";
        Mso::Diagnostics::SendDiagnosticTrace<>(556414216, 2485, 50, 2, (__int64)&v1451);
        Count = Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection::GetCount(v1197);
        v1029 = WN::Puiframe(*(WN **)(Count + 16));
        v1030 = UIFRAME::HwndFrame(v1029);
        SetForegroundWindow(v1030);
        v1024 = -2147467260;
        v1023 = 37246725;
        goto LABEL_1874;
      }
      v1023 = 24737505;
    }
LABEL_1888:
    v115 = -2146827284;
    goto LABEL_1889;
  }
  if ( UIGLOBALS::UIGLOBALSCONTAINER::m_selection )
  {
    v222 = SH::Pbook(*(SH **)(UIGLOBALS::UIGLOBALSCONTAINER::m_selection + 24LL));
    if ( v222 == v1197
      && (!*(_QWORD *)&UIGLOBALS::UIGLOBALSCONTAINER::m_posi
       || (v223 = *(_QWORD *)(*(_QWORD *)&UIGLOBALS::UIGLOBALSCONTAINER::m_posi + 1568LL)) == 0
       || *(_QWORD *)(v223 + 256))
      && !(unsigned int)FOsrhBook(v1197) )
    {
      inited = HrInitRevert((struct REVARG *)v1565, 336, &v1269);
      v225 = v1170;
      if ( inited >= 0 )
        v225 = 1;
      v1170 = v225;
    }
  }
  Marquee::FreeAllMarqueeTag(0, 20789206, v221);
  DestroyWorkgroup();
  v226 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1384, 0x237630DCu);
  v227 = SXVWGEOM::RwFirst(v226);
  v228 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 128LL);
  v229 = 0;
  if ( v228 )
  {
    v230 = v228;
    do
    {
      v229 = v230[1];
      if ( v229 )
        break;
      v228 = (_QWORD *)*v228;
      v230 = v228;
    }
    while ( v228 );
  }
  LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v229 + 96), v1197, v227);
  if ( Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection::GetCount(*(Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 32LL))
    && *(_QWORD *)(Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection::GetCount(*(Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 32LL))
                 + 16) )
  {
    v231 = (struct WNX *)Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection::GetCount(*(Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 32LL));
    v232 = Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection::GetCount(*(Osf::AddinDefinedFunction::MetadataEnumParamInfoCollection **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 32LL));
    AttachWnxToWn(*(struct WN **)(v232 + 16), v231);
  }
  if ( (unsigned int)FLogRevs(v1197) && (*((_BYTE *)v1197 + 884) & 0x20) == 0 )
    FFreeUsrInfo(v1197, *(_DWORD *)(*((_QWORD *)v1197 + 125) + 16LL), 0, 0, 0);
  HrRecordEvent(v1157, 0x40000000u, 0);
  if ( v210 )
  {
    if ( v1275 )
    {
      v233 = (SH *)*((_QWORD *)v1275 + 3);
      if ( v233 )
      {
        v234 = SH::Pbook(v233);
        if ( v234 == v1197 )
          v210 = 0;
      }
    }
  }
  sub_1416A3CB4();
  v235 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
  if ( *(_QWORD *)(v235 + 992) )
  {
    v236 = *(_QWORD *)(v235 + 992);
    if ( *(_QWORD *)(v236 + 48) )
    {
      v237 = SH::Pbook(*(SH **)(*(_QWORD *)(v236 + 48) + 24LL));
      if ( v237 == v1197 )
        FreeCfr();
    }
  }
  v115 = XlReopenBook::HrCloseBookForReopen(
           &v1197,
           (struct REVERT **)((unsigned __int64)&v1269 & -(__int64)(v1170 != 0)));
  if ( v115 < 0 )
  {
    v1020 = 34174687;
    v1021 = v115;
    goto LABEL_1869;
  }
  v1301 = 0;
  if ( v210 )
  {
    v238 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1385, 0x237630DBu);
    v239 = SXVWGEOM::RwFirst(v238);
    v240 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 128LL);
    v241 = 0;
    if ( v240 )
    {
      v242 = v240;
      do
      {
        v241 = v242[1];
        if ( v241 )
          break;
        v240 = (_QWORD *)*v240;
        v242 = v240;
      }
      while ( v240 );
    }
    LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v241 + 96), v1268, v239);
    v243 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1386, 0x237630DAu);
    v244 = SXVWGEOM::RwFirst(v243);
    v245 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 128LL);
    v246 = 0;
    if ( v245 )
    {
      v247 = v245;
      do
      {
        v246 = v247[3];
        if ( v246 )
          break;
        v245 = (_QWORD *)*v245;
        v247 = v245;
      }
      while ( v245 );
    }
    VIEWCONTEXTDATA::CurWnx(*(VIEWCONTEXTDATA **)(v246 + 16), v1275, v244);
  }
  v169 = v1171;
  v1219 = 2;
  if ( v1171 || (v248 = 2, v1173) )
    v248 = 4;
  v1178 = FBeginCmdIOLDoc(v1157, v248, 0, &v1232, 0);
  if ( (*(unsigned int (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1157 + 208LL))(v1157) )
    v1219 = 0;
  if ( v169 )
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
  LODWORD(v1126) = v1219;
  XlsDiag::SendTraceTag(41039178, 187, 100, L"FFileLoadEx: OlDocSetupFlags oldsf = 0x%x", v1126);
  v249 = TLSW::PesExpressionService(*(TLSW **)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL));
  v250 = ExpressionService::Pwbkcoll(v249);
  RevisionLatencyOutlierTracker::RevisionLatencyOutlierTracker(v1528, v250, 16);
  operator|=(&v1219, 4096);
  v251 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
  v252 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1387, 0x236962C3u);
  v253 = SXVWGEOM::RwFirst(v252);
  v115 = OlDocFilePath::HrSetupAndRetrievePathTitle(
           v251,
           (struct FileSource *)v1305,
           &v1157,
           v82,
           &v1232,
           (enum OlDocSetupFlags *)&v1219,
           0,
           v253,
           0,
           0);
  RevisionLatencyOutlierTracker::~RevisionLatencyOutlierTracker((RevisionLatencyOutlierTracker *)v1528);
  if ( v115 < 0 )
  {
    if ( v1170 && v1269 )
      FreeRevert(v1269);
    v1023 = 24737506;
LABEL_1889:
    v1025 = v115;
LABEL_1875:
    XlsDiag::LogSetHrCoreTag(v1025, v1023);
LABEL_1876:
    v68 = v1158;
LABEL_1877:
    v1011 = v1161;
LABEL_2087:
    if ( v1157 )
    {
      LOBYTE(v260) = v1187 != 0;
      sub_1416B1620(v1157, v1305, v260);
      (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v1157 + 56LL))(
        v1157,
        0xFFFFFFFFLL,
        7);
      if ( v1178 )
      {
        HrRecordEvent(v1157, 0x40000000u, 0);
        if ( v1011 && *v1011 )
        {
          v1107 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1366, 0x236962C2u);
          v1108 = SXVWGEOM::RwFirst(v1107);
          v1109 = 0;
          goto LABEL_2092;
        }
      }
      else
      {
        v1110 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1367, 0x236962C1u);
        v1108 = SXVWGEOM::RwFirst(v1110);
        v1109 = 1;
LABEL_2092:
        OlDocFilePath::FReleaseIOLDoc(v1011, v1109, 1, v1108);
      }
    }
LABEL_1930:
    v82 = v1160;
LABEL_2095:
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
        v1111 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1368, 0x236962C0u);
        v1112 = SXVWGEOM::RwFirst(v1111);
        OlDocFilePath::FReleaseIOLDoc(&v1299, 1, 1, v1112);
      }
      v1113 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1462);
      CchStToSt(v1113, v82, v1224);
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
    if ( !XlFileProtocolManager::FForceCobaltReopenHr(v115) )
    {
      v115 = -2146827284;
      XlsDiag::LogSetHrCoreTag(-2146827284, 0x2385706u);
    }
    v1150 = v1334;
    v1148 = v1254;
    v1147 = v1175;
    v1146 = v115;
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
LABEL_2108:
    v1068 = HrFileCompleteLoadEx(
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
LABEL_1987:
    v605 = v1068;
    goto LABEL_2131;
  }
  v254 = ((__int64 (*)(void))FeatureGateCollectionBase<LoadSaveFeatureGates>::Instance)();
  if ( (unsigned __int8)Mso::AB::Optimized::FeatureGate::operator bool(v254 + 8) )
  {
    v258 = (const struct OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
    v259 = FileSource::HrSetOlDocFilePath((FileSource *)v1305, v258);
    v115 = v259;
    if ( v259 < 0 )
    {
      XlsDiag::LogSetHrCoreTag(v259, 0x27D405Fu);
      goto LABEL_1876;
    }
    v1152 = FileSource::HrSetPoldoc((FileSource *)v1305, v1157, v1274, v1213);
    v115 = v1152;
    if ( v1152 >= 0 )
      goto LABEL_408;
    v257 = 41969047;
    goto LABEL_407;
  }
  v255 = std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
  Target = (const wchar_t *)OfficeExtension::ServerRuntime::RichApiMessageEntry::GetTarget(v255);
  v1152 = FileSource::HrSetWin32PathSt((FileSource *)v1305, Target);
  v115 = v1152;
  if ( v1152 < 0 )
  {
    v257 = 41185885;
LABEL_407:
    XlsDiag::LogSetHrCoreTag(v115, v257);
    if ( v115 < 0 )
      goto LABEL_1876;
  }
LABEL_408:
  v261 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
  v262 = OlDocFilePath::StzTitle(v261);
  CchStToStz(v262, &v1567, 257);
  v143 = v1247;
LABEL_409:
  v151 = v1158;
LABEL_410:
  v263 = NtCurrentTeb()->ThreadLocalStoragePointer;
  vhpstErrPath = v82;
  v264 = *(_QWORD *)(*(_QWORD *)v263 + 304LL);
  *(_DWORD *)(v264 + 2024) = 1;
  *(_DWORD *)(v264 + 2028) = 38879640;
  v1153 = 0;
  v265 = 0;
  v1239 = 0;
  v1215 = 0;
  errDeferred = 0;
  v266 = NtCurrentTeb()->ThreadLocalStoragePointer;
  v1244 = (void *)-1LL;
  if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v266 + 304LL) + 872LL) + 104LL) == 2
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
      v265 = FileSource::HpstgiFileOpen(
               (FileSource *)v1305,
               &v1567,
               (unsigned int)(v169 != 0) + 1056,
               0,
               0,
               0,
               0,
               0,
               v1213);
      v1215 = v265;
      v267 = 0;
      if ( !v1157 )
        goto LABEL_422;
      errDeferred = _IMsoOLDocument_GetDeferredError(v1157);
      if ( errDeferred )
        goto LABEL_427;
      v267 = 0;
LABEL_422:
      if ( !v169 )
      {
        if ( (unsigned int)FErrPstgi(v265) )
          v267 = (unsigned __int16)PstgiFromErr((unsigned __int16)v265);
        else
          v267 = 0;
      }
      errDeferred = v267;
      if ( v267 )
      {
LABEL_427:
        v1163 = 1;
        v265 = FileSource::HpstgiFileOpen((FileSource *)v1305, &v1567, 0x421u, 0, 0, 0, 0, 0, v1213);
        v1215 = v265;
      }
    }
    if ( (unsigned int)FErrPstgi(v265) )
    {
LABEL_437:
      v1185 |= 1u;
    }
    else
    {
      v1167 = 0;
      v268 = SXVWGEOM::RwFirst(v265);
      STGI::SetSlf(v265, v268 & 0xFFFFFFDF);
      if ( v169 || (v269 = 1152, v1163) )
        v269 = 1153;
      v270 = v269 | SXVWGEOM::RwFirst(v265) & 0x800;
      v271 = STGI::Lpstg(v265);
      v272 = ScStgIdsStreamOpen(v271, v270, 0, v1566, &v1167, -1161035344, 9);
      v273 = v272 == 0;
      if ( !v272 && !(unsigned int)FValidDRDocStream(v1167) )
      {
        StreamClose(v1167);
        v1167 = 0;
        v273 = 0;
      }
      if ( !v273 )
      {
        StgiFileClose(v265);
        v265 = 0;
        v1215 = 0;
        goto LABEL_437;
      }
    }
    if ( (v1185 & 1) == 0 )
      goto LABEL_439;
LABEL_1015:
    v554 = FileSource::StzFileName((FileSource *)v1305);
    if ( (unsigned int)FFinderFile(v554) )
    {
      v169 = 1;
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
      v373 = v1164;
      goto LABEL_658;
    }
    v1212 = 0;
    v279 = 0;
    v280 = APPCORE::PmemheapMain((APPCORE *)&vapp);
    MaxPathHolder::MaxPathHolder((MaxPathHolder *)v1313, v280, 259, 0);
    if ( (unsigned int)FOsrcHostedByExcel() )
    {
      MaxPathStzPoke::MaxPathStzPoke((MaxPathStzPoke *)v1483, (struct MaxPathHolder *)v1313);
      v281 = MaxPathStzPoke::CchStzBufferSize((MaxPathStzPoke *)v1483);
      v282 = (wchar_t *)SlicerViewImpl::PSlicerView((SlicerViewImpl *)v1483);
      CnvTempFile = FileSource::HrGetCnvTempFile((FileSource *)v1305, v282, v281, &v1229, &v1187);
      v279 = CnvTempFile;
      if ( CnvTempFile < 0 )
      {
        v115 = CnvTempFile;
        XlsDiag::LogSetHrCoreTag(CnvTempFile, 0x17976E3u);
        MaxPathStzPoke::~MaxPathStzPoke((MaxPathStzPoke *)v1483);
LABEL_465:
        MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1313);
        goto LABEL_466;
      }
      v284 = (MaxPathStzPoke *)v1483;
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
            v143 = IMsoOLDocument::IsInFileSys(v1157) != 0;
            v1247 = v143;
            v1258 = v143;
          }
          v287 = v1171;
          if ( v1229 == 68 )
            v287 = 1;
          v1171 = v287;
          v1214 = v287;
          v288 = FileSource::SzFilePath((FileSource *)v1305);
          MaxPathHolder::CchCopyFromSz((MaxPathHolder *)v1482, v288);
          v289 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1313);
          v290 = FileSource::HrSetWin32PathSt((FileSource *)v1305, v289);
          v1152 = v290;
          v115 = v290;
          if ( v290 < 0 )
          {
            XlsDiag::LogSetHrCoreTag(v290, 0x274139Du);
            goto LABEL_465;
          }
          v291 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL);
          v1249 = 0;
          *(_DWORD *)(v291 + 104) = 0;
          a10 &= ~8u;
          FRemoveLoadAction((struct LoadRecovery *)v151, 0);
          if ( v151 )
          {
            LoadRecovery::Destroy((LoadRecovery *)v151);
            FreeHpst(v151);
            v1158 = 0;
            v1233 = 0;
          }
        }
        v292 = FileSource::StzFileName((FileSource *)v1305);
        if ( (unsigned int)FFinderFile(v292) )
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
            v294 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
            v295 = (LXBASE *)OpenTelemetry::POpenFileStageModel(v294);
            v296 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1388, 0x1F0CB5D1u);
            SXVWGEOM::RwFirst(v296);
            WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v295);
            v297 = PstgiFromErr(1u);
            v298 = v1187;
            v265 = v297;
            v1215 = v297;
            v299 = v1236;
            v1194 = 5;
            if ( v1187 )
              v299 = v1229;
            v1236 = v299;
            v1464 = 0;
            memset_0(&v1465, 0, 0x58u);
            v1466 = 257;
            v1477 = 0;
            v1478 = 0;
            v1479 = 0;
            v1480 = 0;
            v1465 = &v1567;
            if ( !v298 || (v300 = (BKORWS *)v1482, v143) )
              v300 = (BKORWS *)v1339;
            v301 = BKORWS::Psh(v300);
            v68 = v1158;
            v1467 = v301;
            v1468 = a5;
            v1469 = v1244;
            v1470 = v1157;
            v1464 = &v1235;
            v1480 = v1158;
            MaxPathStzPoke::MaxPathStzPoke((MaxPathStzPoke *)v1502, (struct MaxPathHolder *)v1313);
            v302 = 0;
            if ( v1187 )
              v302 = SlicerViewImpl::PSlicerView((SlicerViewImpl *)v1502);
            v1475 = v302;
            MaxPathStzPoke::~MaxPathStzPoke((MaxPathStzPoke *)v1502);
            v1474 = v1187;
            v1471 = v1180;
            v1472 = v1185 & 2;
            v1473 = v1210 != 1;
            v1476 = v1270;
            v1479 = v1225;
            if ( AppGuard::Config::IsEnabled(v303) )
              v1477 = (a10 & 0x80000) != 0;
            v1478 = v1216 == 1;
            v304 = HrLoadInSecureReader((const struct XLOSRLA *)&v1464, v1213);
            v305 = NtCurrentTeb()->ThreadLocalStoragePointer;
            v1177 = v304;
            v1153 = v304 >= 0;
            v1244 = (void *)-1LL;
            v1223 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v305 + 304LL) + 2924LL);
            if ( v304 >= 0 )
              RenumberWind(*(struct SH **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                         + 32LL));
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1220;
            v1151 = 0;
            v115 = v1177;
            v1152 = v1177;
            if ( v1177 < 0 )
            {
              XlsDiag::LogSetHrCoreTag(v1177, 0x1797700u);
              if ( v1177 < 0 )
              {
                v306 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
                v307 = OpenTelemetry::POpenFileStageModel(v306);
                v308 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1389, 0x1F0CB5D0u);
                v309 = SXVWGEOM::RwFirst(v308);
                WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v307, (unsigned int)v1177, v309);
              }
            }
            MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1313);
            goto LABEL_910;
          }
          v293 = BKORWS::Psh((BKORWS *)&v1179);
          if ( (int)XlFileProtocolManager::HrRequestCobaltReopen(v1157, v1200, -1662189471, v293) < 0 )
            MsoShipAssertTagProc(506512324);
          v115 = -1662189471;
          XlsDiag::LogSetHrCoreTag(-1662189471, 0x1E30C3C3u);
          goto LABEL_465;
        }
        v310 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                         + 104LL);
        v311 = APPCORE::PmemheapMain((APPCORE *)&vapp);
        v312 = APPCORE::PlocaleinfoUSEN((APPCORE *)&vapp);
        v313 = FSmellsLikeMetroFileCancelable(
                 (struct FileSource *)v1305,
                 v312,
                 0,
                 v311,
                 &v1248,
                 v310 == 0,
                 &v1240,
                 &v1212);
        if ( v1212 )
        {
          v314 = 579396827;
          v315 = -2147023673;
LABEL_506:
          XlsDiag::LogSetHrCoreTag(v315, v314);
LABEL_507:
          v316 = (MaxPathHolder *)v1313;
LABEL_508:
          MaxPathHolder::~MaxPathHolder(v316);
          v68 = v1158;
          goto LABEL_815;
        }
        v317 = ((__int64 (*)(void))FeatureGateCollectionBase<LoadSaveFeatureGates>::Instance)();
        if ( (unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(v317 + 488) )
        {
          v318 = (CorruptionMetaData *)std::_Optional_construct_base<CorruptionMetaData>::operator*(v1538);
          CorruptionMetaData::SetFEncrypted(v318, v1240 != 0);
          v319 = (CorruptionMetaData *)std::_Optional_construct_base<CorruptionMetaData>::operator*(v1538);
          v320 = sub_1402DFA10(v1539);
          CorruptionMetaData::SetFDrmProtected(v319, v320);
        }
        if ( v1267 && !v313 )
        {
          MsoShipAssertTagProc(504410774);
          v314 = 504410773;
          v315 = -2147467260;
          goto LABEL_506;
        }
        if ( v1187 && (v1248 || !v313) )
        {
          FileSource::HrDeleteTemp((FileSource *)v1305);
          v115 = -2146827284;
          v321 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          *(_DWORD *)(v321 + 2024) = 0;
          *(_DWORD *)(v321 + 2028) = 0;
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
          v322 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          *(_DWORD *)(v322 + 2024) = 0;
          *(_DWORD *)(v322 + 2028) = 0;
          v115 = -2146827284;
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1220;
          XlsDiag::LogSetHrCoreTag(-2146827284, 0x1797702u);
          MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1313);
LABEL_467:
          v278 = v1160;
          goto LABEL_1664;
        }
        v323 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
        v324 = (LXBASE *)OpenTelemetry::POpenFileStageModel(v323);
        v325 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1390, 0x1F0CB5CFu);
        SXVWGEOM::RwFirst(v325);
        WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v324);
        if ( !v313 )
        {
          MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1313);
          goto LABEL_524;
        }
        v265 = PstgiFromErr(7u);
        v1215 = v265;
        if ( v1172 )
        {
          if ( !(unsigned int)FOsrc() )
          {
            v330 = FileSource::StzFileName((FileSource *)v1305);
            if ( !(unsigned int)sub_14240EB30(v330) )
            {
              SetLoadForPreviewError(-2147467259);
              XlsDiag::LogSetHrCoreTag(-2147467260, 0x1797703u);
              v331 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
              v332 = OpenTelemetry::POpenFileStageModel(v331);
              v333 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1460, 0x1F0CB5CEu);
              v334 = SXVWGEOM::RwFirst(v333);
              WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v332, 2214658820LL, v334);
LABEL_543:
              MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1313);
              goto LABEL_815;
            }
          }
        }
        std::optional<DataLossProtection::NotifyRaiiHintsForPrePostEvents>::optional<DataLossProtection::NotifyRaiiHintsForPrePostEvents>(v1336);
        v336 = v1171;
        if ( !v1171 && !FileSource::FCloud((FileSource *)v1305) )
        {
          v337 = APPCORE::PmemheapMain((APPCORE *)&vapp);
          MaxPathHolder::MaxPathHolder((MaxPathHolder *)v1509, v337, 259, 0);
          if ( IsWin32AppRunningInWdag() )
            v338 = (wchar_t *)FileSource::StzFileName((FileSource *)v1305);
          else
            v338 = v1160;
          MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1509, v338);
          v339 = *(const wchar_t **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 784LL);
          v340 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1509);
          v279 = HrWriteOwnerFile(v1157, v340, v339, &v1244);
          v341 = BKORWS::Psh((BKORWS *)v1509);
          v342 = PbookFromPioldoc(v1157);
          DataLossProtectionHelper::spCreateCustomInfoContext(v1343, v342, v341);
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
        LOBYTE(v335) = std::nullopt;
        if ( !(unsigned __int8)std::operator==<DataLossProtection::NotifyRaiiHintsForPrePostEvents>(v1336, v335) )
        {
          v343 = sub_140451950(v1523, v1336, &v1177);
          sub_14062191C(v1517, v343);
          sub_14062192C(v1517);
        }
        if ( v279 == -2147024864 )
        {
          v265 = PstgiFromErr(2u);
          v1215 = v265;
LABEL_618:
          if ( (unsigned int)FErrPstgi(v265) )
          {
            v370 = (unsigned __int16)PstgiFromErr((unsigned __int16)v265);
            v371 = v1222;
            v372 = v370;
            if ( v370 == 7 )
            {
              v373 = v1164;
              if ( v1222 == -2147024891 )
                v373 = 1;
              v1164 = v373;
            }
            else
            {
              v373 = v1164;
            }
            v68 = v1158;
            if ( v370 != 7 && v370 != 2 && v1249 && v1158 && LoadRecovery::FRepairPkg((LoadRecovery *)v1158) )
            {
              v1264 = 1;
              LoadRecovery::SetRepairState((LoadRecovery *)v68, -2146827284);
              if ( v372 == 1 && (unsigned int)(v371 + 2134241024) > 1 )
              {
                if ( v371 >= 0 )
                  v371 = -2146827284;
                XlsDiag::LogSetHrCoreTag(v371, 0x1797706u);
                std::_Optional_destruct_base<DataLossProtection::NotifyRaiiHintsForPrePostEvents,0>::reset(v1336);
                MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1313);
                goto LABEL_817;
              }
              if ( v371 >= 0 )
                v371 = -2147467260;
              v374 = 24737543;
              v375 = v371;
              goto LABEL_642;
            }
            if ( v372 == 1 )
            {
              if ( v371 == -2134195936
                && (unsigned int)Mso::Details::ConstexprFunctorBase<Mso::IFunctor<bool,FeaturePropertyValue const &,FeaturePropertyValue const &>>::Release(&vapp) )
              {
                v1177 = v1222;
                ErrorAlert(459071, v1568);
                v375 = v1177;
                if ( v1177 >= 0 )
                {
LABEL_643:
                  std::_Optional_destruct_base<DataLossProtection::NotifyRaiiHintsForPrePostEvents,0>::reset(v1336);
                  goto LABEL_543;
                }
                v374 = 24737544;
LABEL_642:
                XlsDiag::LogSetHrCoreTag(v375, v374);
                goto LABEL_643;
              }
              v115 = -2146827284;
              v1152 = -2146827284;
              XlsDiag::LogSetHrCoreTag(-2146827284, 0x230E1E1u);
              std::_Optional_destruct_base<DataLossProtection::NotifyRaiiHintsForPrePostEvents,0>::reset(v1336);
              MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1313);
LABEL_645:
              v376 = APPCORE::PlocaleinfoUSEN((APPCORE *)&vapp);
              if ( (unsigned int)FMetroFileExt((const struct FileSource *)v1305, v376, 0, 0) )
              {
                v68 = v1158;
                if ( v1158 )
                {
                  if ( LoadRecovery::FRepairPkg((LoadRecovery *)v1158)
                    || (unsigned __int16)PstgiFromErr((unsigned __int16)v265) == 7 )
                  {
                    OkAlert(v373 != 0 ? 262202 : 458868, v1568);
                    XlsDiag::LogSetHrCoreTag(v373 != 0 ? -2147024891 : -2146827284, 0x230E200u);
                    if ( !v373 )
                    {
                      v458 = (CorruptionMetaData *)std::_Optional_construct_base<CorruptionMetaData>::operator*(v1538);
                      CorruptionMetaData::MarkAsCorrupt(v458);
                    }
                    if ( v1172 )
                      SetLoadForPreviewError(v373 != 0 ? -2147024891 : -2042494972);
                    goto LABEL_815;
                  }
                  v1248 = 1;
                  LoadRecovery::SetRepairPkg((LoadRecovery *)v68);
                }
LABEL_817:
                v460 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                *(_DWORD *)(v460 + 2024) = 0;
                *(_DWORD *)(v460 + 2028) = 0;
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1220;
                v1151 = 0;
                if ( (unsigned int)FErrPstgi(v265) && v1244 != (void *)-1LL )
                {
                  CloseSentinelFile(v1244);
                  v1244 = (void *)-1LL;
                }
                v115 = -2146827284;
                XlsDiag::LogSetHrCoreTag(-2146827284, 0x230E201u);
                goto LABEL_821;
              }
LABEL_524:
              v169 = v1171;
              if ( a7 == 1024 )
                goto LABEL_839;
              v326 = 1024;
              v327 = 1024;
              if ( v1171 )
              {
                v326 = 1025;
                v327 = 1025;
              }
              v328 = v326;
              if ( *(_QWORD *)&UIGLOBALS::UIGLOBALSCONTAINER::m_posi )
              {
                v329 = *(_QWORD *)(*(_QWORD *)&UIGLOBALS::UIGLOBALSCONTAINER::m_posi + 1568LL);
                if ( v329 )
                {
                  if ( !*(_QWORD *)(v329 + 256) )
                  {
                    v327 = v326 | 0x20;
                    v328 = v326 | 0x20;
                  }
                }
              }
              if ( v1172 )
                v327 = v328 | 0x1000000;
              v265 = FileSource::HpstgiFileOpen((FileSource *)v1305, &v1567, v327, 0, &v1243, 0, 0, 0, v1213);
              v1215 = v265;
              v1174 = 1;
              if ( !v1172 || !(unsigned int)FErrPstgi(v265) || (unsigned int)FOsrc() && !MsoFDrmErrorCode(v1243) )
              {
                if ( (unsigned int)FErrPstgi(v265)
                  && (unsigned __int16)PstgiFromErr((unsigned __int16)v265) != 4
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
                  || (unsigned int)FErrPstgi(v265) && (unsigned __int16)PstgiFromErr((unsigned __int16)v265) == 4 )
                {
                  goto LABEL_1015;
                }
                v1167 = 0;
                if ( (unsigned int)FErrPstgi(v265) )
                {
                  v469 = 0;
                  if ( v1157 )
                  {
                    errDeferred = _IMsoOLDocument_GetDeferredError(v1157);
                    if ( errDeferred )
                      goto LABEL_853;
                    v469 = 0;
                  }
                  if ( !v169 )
                  {
                    if ( (unsigned int)FErrPstgi(v265) )
                      v469 = (unsigned __int16)PstgiFromErr((unsigned __int16)v265);
                    else
                      v469 = 0;
                  }
                  errDeferred = v469;
                  goto LABEL_852;
                }
                v467 = ((v169 != 0) + 1024) | SXVWGEOM::RwFirst(v265) & 0x800;
                v468 = STGI::Lpstg(v265);
                ScStgIdsStreamOpen(v468, v467, 0, v1566, &v1167, -1161035344, 9);
                v469 = errDeferred;
LABEL_852:
                if ( !v469 )
                  goto LABEL_439;
LABEL_853:
                v1250 = -2147467259;
LABEL_1005:
                v1231 = 0;
                v1163 = 1;
                v550 = v1157
                    && ((*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1157 + 224LL))(v1157) & 1) != 0
                    && errDeferred == 2;
                v551 = FileSource::HpstgiFileOpen((FileSource *)v1305, &v1567, 0x401u, 0, &v1250, 0, 0, v550, v1213);
                v115 = v1250;
                v265 = v551;
                v1215 = v551;
                v1152 = v1250;
                if ( !(unsigned int)FErrPstgi(v551) )
                {
                  v1169 = 0;
                  v552 = SXVWGEOM::RwFirst(v265) & 0x800 | 0x401;
                  v553 = STGI::Lpstg(v265);
                  ScStgIdsStreamOpen(v553, v552, 0, v1566, &v1167, -1161035344, 9);
                  v169 = v1171;
                  goto LABEL_439;
                }
                if ( (unsigned __int16)PstgiFromErr((unsigned __int16)v265) != 4 )
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
                  v169 = v1171;
                  goto LABEL_439;
                }
                v1169 = 1;
LABEL_1014:
                v169 = v1171;
                goto LABEL_1015;
              }
              if ( MsoFDrmErrorCode(v1243) )
              {
                v115 = -2042494975;
              }
              else if ( (unsigned __int16)PstgiFromErr((unsigned __int16)v265) == 4 )
              {
                v115 = -2042490872;
              }
              else if ( v1243 == -2147286775
                     || (unsigned int)(v1243 + 2147286780) <= 1
                     || v1243 == -2147286960
                     || (v115 = -2147467259, v1243 == -2147287010) )
              {
                v115 = -2042494972;
              }
              SetLoadForPreviewError(v115);
              XlsDiag::LogSetHrCoreTag(v115, 0x179770Eu);
              v461 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
              v462 = OpenTelemetry::POpenFileStageModel(v461);
              v463 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1398, 0x1F0CB5C9u);
              v464 = SXVWGEOM::RwFirst(v463);
              WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v462, (unsigned int)v115, v464);
              v68 = v1158;
              v465 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
              *(_DWORD *)(v465 + 2024) = 0;
              *(_DWORD *)(v465 + 2028) = 0;
              *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1220;
              LOBYTE(v265) = 0;
              if ( v68 )
                goto LABEL_830;
              v278 = v1160;
              goto LABEL_1664;
            }
          }
          else
          {
            v373 = v1164;
          }
          if ( !(unsigned int)FErrPstgi(v265) )
          {
            if ( v1240 )
            {
              if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1836LL) )
              {
                v377 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
                v378 = OlDocFilePath::PClpDocument(v377);
                EncryptedStorage = STGI::GetEncryptedStorage(v265);
                if ( !(unsigned int)FDrmQueryRightsStg(EncryptedStorage, 2u, v378) )
                {
                  StgiFileClose(v265);
                  HandleLockError(327752);
                  v349 = 36757986;
                  v380 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                  *(_DWORD *)(v380 + 2024) = 0;
                  *(_DWORD *)(v380 + 2028) = 0;
                  goto LABEL_589;
                }
              }
            }
          }
          std::_Optional_destruct_base<DataLossProtection::NotifyRaiiHintsForPrePostEvents,0>::reset(v1336);
          MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1313);
LABEL_658:
          if ( a7 == 1024
            || (unsigned int)FErrPstgi(v265) && (unsigned __int16)PstgiFromErr((unsigned __int16)v265) == 7 )
          {
            goto LABEL_645;
          }
          if ( !(unsigned int)FErrPstgi(v265) || (unsigned __int16)PstgiFromErr((unsigned __int16)v265) == 8 )
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
              if ( (unsigned int)FErrPstgi(v265) )
              {
                DeferredError = (unsigned __int16)PstgiFromErr((unsigned __int16)v265);
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
            v383 = v1210;
          }
          else
          {
            v382 = FIsShareErr(DeferredError);
            v383 = v1210;
            if ( v382
              && v1210 == 1
              && (int)HrGetRealMetroFileType((struct FileSource *)v1305, (enum FILETYPE *)&v1285) >= 0
              && (v1285 == 54 || v1285 == 17 ? (v384 = 1) : (v384 = 0), v384) )
            {
              DeferredError = 0;
              errDeferred = 0;
            }
            else
            {
              DeferredError = errDeferred;
            }
          }
          if ( (unsigned int)FIsShareErr(DeferredError) && v383 == 1 )
          {
            v385 = APPCORE::PmemheapMain((APPCORE *)&vapp);
            MaxPathHolder::MaxPathHolder((MaxPathHolder *)v1491, v385, 259, 0);
            ENV::ENV((ENV *)&v1554);
            MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1491, v1160);
            FileTemp = FileSource::HrGetFileTemp(v1305, 5);
            v1152 = FileTemp;
            if ( FileTemp < 0 )
            {
              XlsDiag::LogSetHrCoreTag(FileTemp, 0x2806598u);
              XlsDiag::LogSetHrCoreTag(-2146827284, 0x2806599u);
              v316 = (MaxPathHolder *)v1491;
              goto LABEL_508;
            }
            v387 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
            v1442 = *(_QWORD *)(v387 + 336);
            *(_QWORD *)(v387 + 336) = &v1554;
            v1555 = 36737603;
            if ( !setjmp(v1556) )
            {
              v388 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1491);
              if ( (int)HrReadOwnerFile(v388, v1576, 257) < 0 )
              {
                v390 = !v1187 && FileHost::FIsEncryptedMetroFile((FileHost *)v1305, v389);
                v391 = FileSource::StzFilePath((FileSource *)v1305);
                v392 = 0;
              }
              else
              {
                v390 = !v1187 && FileHost::FIsEncryptedMetroFile((FileHost *)v1305, v389);
                v391 = FileSource::StzFilePath((FileSource *)v1305);
                v392 = v1576;
              }
              HrDeferredSRO(&v1567, v392, v391, 0, v390);
            }
            v393 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
            *(_QWORD *)(v393 + 336) = v1442;
            if ( (_QWORD)xmmword_143FE0F90 )
            {
              LOBYTE(v393) = v1183;
              v394 = sub_141224EE0(v1157, v393, &v1195);
              v1210 = v394;
              if ( v394 < 0 )
              {
                errDeferred = 0;
                v1165 = 1;
                XlsDiag::LogSetHrCoreTag(v394, 0x1797709u);
                v395 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
                v396 = OpenTelemetry::POpenFileStageModel(v395);
                v397 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1392, 0x1F0CB5CCu);
                v398 = SXVWGEOM::RwFirst(v397);
                WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v396, 2214658821LL, v398);
                MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1491);
                v68 = v1233;
                v265 = v1215;
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
            v115 = v1152;
            v373 = v1164;
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
          v399 = 0;
          if ( v68 )
            v399 = (int)LoadRecovery::Lrmode(v68) > 0;
          v400 = v399 && LoadRecovery::FRepairPkg((LoadRecovery *)v68);
          v1248 = v400;
          v401 = BKORWS::Psh((BKORWS *)&v1179);
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
                                   v401);
          v265 = v1215;
          if ( (unsigned int)FErrPstgi(v1215) )
          {
            v115 = -2146827284;
            v1152 = -2146827284;
            XlsDiag::LogSetHrCoreTag(-2146827284, 0x230E1E3u);
          }
          else
          {
            v1186 = 1;
          }
          if ( (unsigned int)FErrPstgi(v265) && (unsigned __int16)PstgiFromErr((unsigned __int16)v265) == 8 )
          {
            v402 = v1259;
LABEL_724:
            if ( v402 == -2147168507 )
            {
              MsoShipAssertTagProc(505156896);
              v402 = v1259;
            }
            v1177 = v402;
            if ( v402 >= 0 )
              v402 = -2147467260;
            XlsDiag::LogSetHrCoreTag(v402, 0x179770Au);
            v403 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
            v404 = OpenTelemetry::POpenFileStageModel(v403);
            v405 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1393, 0x1F0CB5CBu);
            v406 = SXVWGEOM::RwFirst(v405);
            v407 = 2214658821LL;
            if ( v1177 < 0 )
              v407 = (unsigned int)v1177;
            WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v404, v407, v406);
            goto LABEL_815;
          }
          v402 = v1259;
          if ( v1259 == -2147168507 )
            goto LABEL_724;
          if ( !(unsigned int)FErrPstgi(v265) )
          {
            v1163 = 1;
            errDeferred = 0;
          }
LABEL_734:
          if ( !(unsigned int)FErrPstgi(v265) )
          {
            if ( !v1157
              || ((*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1157 + 224LL))(v1157) & 1) == 0
              || (v408 = STGI::Pxpkg(v265), !(unsigned int)FIsSharedWbk(v408)) )
            {
              if ( v68 )
              {
                v414 = PivotOperationBase::PSxview((PivotOperationBase *)v68);
                *((_WORD *)v414 + 18) |= 4u;
              }
              v415 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 2024LL);
              v1198 = v415 != 0;
              if ( !v415 )
                XlsDiag::SendTraceTag(38048668, 187, 50);
              v416 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
              v417 = (LXBASE *)OpenTelemetry::POpenFileStageModel(v416);
              v418 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1394, 0x1F0CB5CAu);
              SXVWGEOM::RwFirst(v418);
              WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v417);
              MaxPathStPoke::MaxPathStPoke((MaxPathStPoke *)v1489, (struct MaxPathHolder *)v1339);
              v419 = BKORWS::Psh((BKORWS *)&v1179);
              v420 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
              Context = OlDocFilePath::PClpLoadContext(v420);
              v1444 = std::_Optional_construct_base<CorruptionMetaData>::operator*(v1538);
              v1446 = v1157;
              if ( v1187 )
                v421 = BKORWS::Psh((BKORWS *)v1482);
              else
                v421 = 0;
              v422 = v1251;
              v423 = a10 & 0x800;
              v424 = (struct OpenTelemetry *)v1244;
              if ( v1171 || (v425 = 0, v1163) )
                v425 = 1;
              v426 = MaxPathSzPoke::CchSzBufferSize((MaxPathSzPoke *)v1489);
              v427 = SlicerViewImpl::PSlicerView((SlicerViewImpl *)v1489);
              LOBYTE(v1149) = v1159;
              v1145[0] = v1247;
              v1142 = v421;
              v68 = v1158;
              v1135 = v424;
              v265 = v1215;
              LODWORD(v1133) = 0;
              LODWORD(v1131) = a7;
              LODWORD(v1129) = a5;
              LODWORD(v1128) = v425;
              LODWORD(v1127) = v426;
              v1177 = HrLoadMetro(
                        0,
                        v1215,
                        &v1567,
                        v1305,
                        v427,
                        v1127,
                        v1128,
                        v1129,
                        v1131,
                        v1133,
                        v1135,
                        &v1194,
                        v1158,
                        v1572,
                        v422,
                        v423,
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
                        v419);
              MaxPathStPoke::~MaxPathStPoke((MaxPathStPoke *)v1489);
              v428 = v1177;
              v1152 = v1177;
              v115 = v1177;
              if ( v1177 < 0 )
              {
                XlsDiag::LogSetHrCoreTag(v1177, 0x17D88D8u);
                v428 = v1177;
                if ( v1177 < 0 )
                {
                  if ( OSRR::FReadyForOsr((OSRR *)&v1235) )
                  {
                    v73 = 1;
                    goto LABEL_764;
                  }
                  v428 = v1177;
                }
              }
              v1153 = v428 >= 0;
              if ( v428 >= 0 )
                v1302 = *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                        + 40LL);
              v429 = NtCurrentTeb()->ThreadLocalStoragePointer;
              v1244 = (void *)-1LL;
              v1223 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v429 + 304LL) + 2924LL);
              if ( v428 < 0 )
              {
                if ( v1187 )
                {
                  FileSource::HrDeleteTemp((FileSource *)v1305);
                  v428 = v1177;
                }
                if ( v68 && (v428 == -2134142954 || v428 == -2134188030) )
                  LoadRecovery::SetRepairState((LoadRecovery *)v68, v428);
                v73 = 1;
              }
              else
              {
                if ( v1187 && v1229 != 68 )
                {
                  v430 = LOCATIONCONTEXTDATA::PWorkbookCur((LOCATIONCONTEXTDATA *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                             + 304LL)
                                                                                 + 8LL));
                  Api::Workbook::SetFt(v430, (unsigned int)v1229, 0);
                }
                v431 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                if ( *(_DWORD *)(*(_QWORD *)(v431 + 872) + 104LL) == 2 && (v1185 & 2) == 0 )
                {
                  v1268 = *(struct SH **)(v431 + 32);
                  v432 = LOCATIONCONTEXTDATA::PWorkbookCur((LOCATIONCONTEXTDATA *)(v431 + 8));
                  v433 = OcsTransitionController::PCoauthTransitionState(v432);
                  v434 = XLSBOOK::Plxtab(v433);
                  v435 = SlicerViewImpl::PSlicerView(v434);
                  v436 = LOCATIONCONTEXTDATA::PWorkbookCur((LOCATIONCONTEXTDATA *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                             + 304LL)
                                                                                 + 8LL));
                  v437 = OcsTransitionController::PCoauthTransitionState(v436);
                  v438 = (TAB *)((char *)v435 + 16 * *((int *)XLSBOOK::Plxtab(v437) + 1));
                  if ( v435 < v438 )
                  {
                    v439 = NtCurrentTeb()->ThreadLocalStoragePointer;
                    do
                    {
                      v440 = TAB::PshDesktopOnly(v435);
                      if ( (*((_BYTE *)v440 + 10) & 4) != 0 )
                        v441 = 0;
                      else
                        v441 = *((_BYTE *)v440 + 8);
                      if ( v441 <= 1u )
                      {
                        v442 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1395, 0x237630D9u);
                        v443 = SXVWGEOM::RwFirst(v442);
                        v444 = TAB::PshDesktopOnly(v435);
                        v445 = *(_QWORD *)(*(_QWORD *)v439 + 304LL);
                        v446 = 0;
                        v447 = *(_QWORD **)(v445 + 128);
                        if ( v447 )
                        {
                          v448 = *(_QWORD **)(v445 + 128);
                          do
                          {
                            v446 = v448[1];
                            if ( v446 )
                              break;
                            v447 = (_QWORD *)*v447;
                            v448 = v447;
                          }
                          while ( v447 );
                        }
                        LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v446 + 96), v444, v443);
                        v449 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v439 + 304LL) + 32LL);
                        if ( !((*(_BYTE *)(v449 + 10) & 4) != 0 ? 0 : *(_BYTE *)(v449 + 8)) )
                        {
                          v276 = HrConvertSheetFmlaToVal();
                          if ( v276 < 0 )
                          {
LABEL_1905:
                            v1166 = v276;
                            goto LABEL_1133;
                          }
                        }
                      }
                      v435 = (TAB *)((char *)v435 + 16);
                    }
                    while ( v435 < v438 );
                    v68 = v1158;
                  }
                  v451 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1396, 0x237630D8u);
                  v452 = SXVWGEOM::RwFirst(v451);
                  v453 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 128LL);
                  v454 = 0;
                  if ( v453 )
                  {
                    v455 = v453;
                    do
                    {
                      v454 = v455[1];
                      if ( v454 )
                        break;
                      v453 = (_QWORD *)*v453;
                      v455 = v453;
                    }
                    while ( v453 );
                  }
                  LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v454 + 96), v1268, v452);
                  v265 = v1215;
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
                v456 = (struct WNX *)UIGLOBALS::UIGLOBALSCONTAINER::m_selection;
                if ( !UIGLOBALS::UIGLOBALSCONTAINER::m_selection )
                {
                  SetWnxSel(*(struct WNX **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                           + 104LL));
                  v456 = (struct WNX *)UIGLOBALS::UIGLOBALSCONTAINER::m_selection;
                }
                v73 = 1;
                FActivateListWnx(v456, 1, 0);
              }
              *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1220;
              v1151 = 0;
              goto LABEL_910;
            }
            StgiFileClose(v265);
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
              XlsDiag::SendTraceTag(18088267, 187, 10);
              v115 = -2146827284;
              XlsDiag::LogSetHrCoreTag(-2146827284, 0x179770Bu);
              v1035 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
              *(_DWORD *)(v1035 + 2024) = 0;
              *(_DWORD *)(v1035 + 2028) = 0;
              goto LABEL_1877;
            }
LABEL_743:
            v409 = v1161;
            goto LABEL_744;
          }
          if ( (unsigned __int16)PstgiFromErr((unsigned __int16)v265) )
            goto LABEL_645;
          v457 = FileSource::SzFilePath((FileSource *)v1305);
          OkAlert(196758, v457);
          XlsDiag::LogSetHrCoreTag(-2147319765, 0x179770Du);
LABEL_815:
          if ( v68 )
          {
            v459 = PivotOperationBase::PSxview((PivotOperationBase *)v68);
            *((_WORD *)v459 + 18) |= 8u;
          }
          goto LABEL_817;
        }
        v344 = 2098176;
        v345 = 2098176;
        if ( v336 )
        {
          v344 = 2098177;
          v345 = 2098177;
        }
        v346 = v344;
        if ( *(_QWORD *)&UIGLOBALS::UIGLOBALSCONTAINER::m_posi )
        {
          v347 = *(_QWORD *)(*(_QWORD *)&UIGLOBALS::UIGLOBALSCONTAINER::m_posi + 1568LL);
          if ( v347 )
          {
            if ( !*(_QWORD *)(v347 + 256) )
            {
              v345 = v344 | 0x20;
              v346 = v344 | 0x20;
            }
          }
        }
        if ( v1172 )
          v345 = v346 | 0x1000000;
        v348 = v1186;
        if ( v1186 )
          v345 |= 0x20000000u;
        if ( v1267 && FileSource::FCloud((FileSource *)v1305) )
        {
          MsoShipAssertTagProc(504422487);
          v349 = 504422486;
          v350 = -2147467260;
LABEL_567:
          XlsDiag::LogSetHrCoreTag(v350, v349);
          std::_Optional_destruct_base<DataLossProtection::NotifyRaiiHintsForPrePostEvents,0>::reset(v1336);
          goto LABEL_507;
        }
        if ( v1240 )
        {
          v351 = BKORWS::Psh((BKORWS *)&v1179);
          v352 = v1213;
          v353 = v351;
          v354 = (unsigned __int8)v1158;
          if ( v1158 )
            v354 = LoadRecovery::FRepairPkg((LoadRecovery *)v1158);
          v1215 = (struct STGI *)FileSource::HpstgiFileOpenEx(
                                   v1305,
                                   v345,
                                   0,
                                   &v1222,
                                   0,
                                   v354,
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
                                   v352,
                                   v353);
          v265 = v1215;
          if ( (unsigned int)FErrPstgi(v1215) )
          {
            v355 = 36757983;
LABEL_579:
            v115 = -2146827284;
            v1152 = -2146827284;
            XlsDiag::LogSetHrCoreTag(-2146827284, v355);
          }
        }
        else
        {
          v356 = BKORWS::Psh((BKORWS *)&v1179);
          v357 = v1213;
          v358 = v356;
          v359 = v1158 && LoadRecovery::FRepairPkg((LoadRecovery *)v1158);
          LOBYTE(v1125) = v359;
          v1215 = (struct STGI *)XLFileIOMockable::PstgiFileOpen(
                                   v1305,
                                   v345,
                                   0,
                                   &v1222,
                                   (_DWORD)v1125,
                                   0,
                                   v1267,
                                   v357,
                                   v358);
          v265 = v1215;
          if ( (unsigned int)FErrPstgi(v1215) )
          {
            v355 = 36757984;
            goto LABEL_579;
          }
        }
        v360 = FErrPstgi(v265);
        v361 = v348;
        if ( !v360 )
          v361 = 1;
        v1186 = v361;
        if ( !(unsigned int)FErrPstgi(v265) && OSRR::IsAppAllowed((OSRR *)&v1235) )
        {
          if ( v1251 )
          {
            OSRR::SetAppAllowed((OSRR *)&v1235, 0);
            if ( (unsigned int)XLOSRR::FMustUseOsr((XLOSRR *)&v1235)
              || OSRR::FHasReasons((OSRR *)&v1235) && (unsigned int)NoYesAlert(589864, &v1567) == 7 )
            {
              StgiFileClose(v265);
              v349 = 24737540;
              v265 = 0;
              v1215 = 0;
LABEL_589:
              v350 = -2146827284;
              goto LABEL_567;
            }
          }
        }
        if ( !v1172 || !(unsigned int)FErrPstgi(v265) )
          goto LABEL_607;
        if ( (unsigned __int16)PstgiFromErr((unsigned __int16)v265) == 7 )
        {
          v363 = APPCORE::PlocaleinfoUSEN((APPCORE *)&vapp);
          if ( !(unsigned int)FMetroFileExt((const struct FileSource *)v1305, v363, 0, 0) )
            goto LABEL_607;
        }
        else
        {
          if ( MsoFDrmErrorCode(v1222) )
          {
            v362 = -2042494975;
LABEL_606:
            SetLoadForPreviewError(v362);
LABEL_607:
            if ( (unsigned int)FErrPstgi(v265) )
            {
              v364 = (unsigned __int16)PstgiFromErr((unsigned __int16)v265);
              v365 = v1222;
              if ( v364 == 8 || v1222 == -2147168507 )
              {
                if ( v1222 == -2147168507 )
                {
                  MsoShipAssertTagProc(505157471);
                  v365 = v1222;
                }
                v1177 = v365;
                v1165 = 1;
                if ( v1187 )
                {
                  FileSource::HrDeleteTemp((FileSource *)v1305);
                  v365 = v1177;
                }
                if ( v365 >= 0 )
                  v365 = -2147467260;
                XlsDiag::LogSetHrCoreTag(v365, 0x1797705u);
                v366 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
                v367 = OpenTelemetry::POpenFileStageModel(v366);
                v368 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1391, 0x1F0CB5CDu);
                v369 = SXVWGEOM::RwFirst(v368);
                WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v367, (unsigned int)v365, v369);
                std::_Optional_destruct_base<DataLossProtection::NotifyRaiiHintsForPrePostEvents,0>::reset(v1336);
                MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1313);
                v68 = v1158;
                goto LABEL_815;
              }
            }
            v1174 = 1;
            goto LABEL_618;
          }
          if ( (unsigned __int16)PstgiFromErr((unsigned __int16)v265) != 4
            && v1222 != -2147286775
            && (unsigned int)(v1222 + 2147286780) > 1
            && v1222 != -2147286960
            && v1222 != -2147287010 )
          {
            if ( (unsigned __int16)PstgiFromErr((unsigned __int16)v265) == 8 )
            {
              v362 = -2147467260;
            }
            else
            {
              if ( (unsigned int)FOsrc() )
                goto LABEL_607;
              v362 = -2147467259;
            }
            goto LABEL_606;
          }
        }
        v362 = -2042494972;
        goto LABEL_606;
      }
      MaxPathStzPoke::MaxPathStzPoke((MaxPathStzPoke *)v1488, (struct MaxPathHolder *)v1313);
      v285 = MaxPathStzPoke::CchStzBufferSize((MaxPathStzPoke *)v1488);
      v286 = (wchar_t *)SlicerViewImpl::PSlicerView((SlicerViewImpl *)v1488);
      v1187 = FHandleConverterFile(
                (struct FileSource *)v1305,
                v286,
                v285,
                (enum FILETYPE *)&v1229,
                &v1342,
                (struct XLOSRR *)&v1235,
                v1160);
      v284 = (MaxPathStzPoke *)v1488;
    }
    MaxPathStzPoke::~MaxPathStzPoke(v284);
    goto LABEL_473;
  }
  v470 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
  if ( *(_QWORD *)(v470 + 40) )
    v1167 = *(struct STM **)(*(_QWORD *)(v470 + 40) + 56LL);
  else
    v1167 = 0;
  do
  {
LABEL_439:
    if ( !SbFromHpCore(v1167) )
    {
      if ( wProjLoad == 1 )
        wProjLoad = 5;
      if ( (unsigned int)FErrPstgi(v265) )
      {
        v68 = v1158;
        if ( !v1158 || v1231 )
        {
LABEL_987:
          v503 = v1161;
          goto LABEL_954;
        }
        v545 = PivotOperationBase::PSxview((PivotOperationBase *)v1158);
        *((_WORD *)v545 + 18) |= 8u;
LABEL_953:
        v503 = v1161;
        goto LABEL_954;
      }
LABEL_969:
      OSRR::SetAppAllowed((OSRR *)&v1235, 0);
      if ( (unsigned int)XLOSRR::FMustUseOsr((XLOSRR *)&v1235) )
      {
        StgiFileClose(v265);
        v115 = -2147024809;
        XlsDiag::LogSetHrCoreTag(-2147024809, 0x1797716u);
        v68 = v1158;
        v1153 = 0;
        errDeferred = 0;
        v581 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        *(_DWORD *)(v581 + 2024) = 0;
        *(_DWORD *)(v581 + 2028) = 0;
LABEL_821:
        LOBYTE(v265) = v1151;
        goto LABEL_518;
      }
      v115 = FileSource::HrGetFileTemp(v1305, 13);
      v1152 = v115;
      if ( v115 >= 0 )
      {
        v278 = v1160;
        if ( (unsigned int)FFinderFile(v1160) )
        {
          vfPretendNotStg = 1;
          StgiFileClose(v265);
          v580 = 1049729;
          if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                         + 104LL) != 2 )
            v580 = 1025;
          v1167 = FileSource::StreamOpen((FileSource *)v1305, v580, 0);
          vhpstm = v1167;
          goto LABEL_1078;
        }
      }
      else
      {
        XlsDiag::LogSetHrCoreTag(v115, 0x27413C0u);
      }
      if ( v1188
        && *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1232LL)
                     + 32LL) )
      {
        v540 = FExecWWWHelp(-1);
        v541 = 0;
        if ( v540 )
        {
          v68 = v1158;
LABEL_977:
          StgiFileClose(v265);
          goto LABEL_953;
        }
      }
      else
      {
        v541 = 0;
      }
      if ( v1567 < 0xFFu )
      {
        v542 = 58;
        v1568[v1567] = 58;
        v543 = 2LL * v1567 + 4;
        if ( v543 >= 0x202 )
          goto LABEL_2132;
        *(wchar_t *)((char *)&v1568[-1] + v543) = 0;
        OkAlert(196665, v1568);
        MakeStStzTruncOK(&v1567, 257);
      }
      v68 = v1158;
      if ( v1158 )
      {
        v544 = PivotOperationBase::PSxview((PivotOperationBase *)v1158);
        *((_WORD *)v544 + 18) |= 8u;
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
          v115 = -2146827284;
          vhpstm = 0;
          errDeferred = 0;
          v575 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          *(_DWORD *)(v575 + 2024) = 0;
          *(_DWORD *)(v575 + 2028) = 0;
          XlsDiag::LogSetHrCoreTag(-2146827284, 0x1797710u);
LABEL_466:
          v68 = v1158;
          LOBYTE(v265) = v1151;
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
        v496 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        v1447 = *(_QWORD *)(v496 + 336);
        *(_QWORD *)(v496 + 336) = &v1557;
        v1558 = 36737604;
        v497 = setjmp(v1559);
        v498 = v1447;
        if ( v497
          || (v499 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1339), (int)HrDeferredSRO(&v1567, 0, v499, 0, 0) < 0) )
        {
          v1152 = -2147467259;
          v115 = -2147467259;
          XlsDiag::LogSetHrCoreTag(-2147467259, 0x279F29Fu);
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v498;
        }
        else
        {
          v115 = v1152;
        }
        v68 = v1233;
        v169 = v1214;
        v500 = *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer;
        v1158 = v1233;
        v1171 = v1214;
        *(_QWORD *)(*(_QWORD *)(v500 + 304) + 336LL) = v498;
        v501 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1304LL);
        *(_WORD *)(v501 + 56) &= ~8u;
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
    if ( (unsigned int)FErrPstgi(v265) || (v274 = STGI::Lpstg(v265), !(unsigned int)FMultiUsrStg(v274)) )
    {
      v275 = 0;
    }
    else
    {
      v275 = 1;
      if ( vgkr == -1 && MsoFShouldGatekeep((const struct _msoreg *)&vmsoridEnableExcelGKOnLoad) )
      {
        v1287 = 0;
        if ( (unsigned int)FBeginDiskIO(v1167) )
        {
          v1286 = 0;
          v276 = HrWPlatformSpecificFromStream2(&v1286);
          if ( v276 < 0 )
            goto LABEL_1905;
          if ( (v1286 & 0xF1FF) == 9 )
          {
            v277 = v1158;
            v1325 = 0;
            v276 = HrReadBof(v1286, 0, (struct LoadRecovery *)v1158, &v1325);
            if ( v276 < 0 )
              goto LABEL_1905;
            v276 = HrReadFileAccess(v1583, 8224, &v1567, 0, 0, 0, 0, (struct LoadRecovery *)v277, &v1262, &v1287);
            if ( v276 < 0 )
              goto LABEL_1905;
          }
          v276 = HrStreamSetPos2(0);
          if ( v276 < 0 )
            goto LABEL_1905;
          v276 = HrEndDiskIO2(0);
          if ( v276 < 0 )
            goto LABEL_1905;
        }
        if ( !v1287 )
        {
          StreamClose(v1167);
          StgiFileClose(v265);
          v1036 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          v1023 = 40981772;
          *(_DWORD *)(v1036 + 2024) = 0;
          *(_DWORD *)(v1036 + 2028) = 0;
          goto LABEL_1873;
        }
        v278 = v1160;
        LOBYTE(v1128) = 1;
        LODWORD(v1125) = 0;
        SafeToLoad::FGatekeep(v1160, v1305, 0, 0, v1125, &v1235, (_DWORD)v1128);
        goto LABEL_859;
      }
    }
    v278 = v1160;
LABEL_859:
    if ( v275
      && v1157
      && ((*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1157 + 224LL))(v1157) & 1) != 0 )
    {
      StreamClose(v1167);
      StgiFileClose(v265);
      if ( v1178 )
      {
        HrRecordEvent(v1157, 0x40000000u, 0);
        v1178 = 0;
      }
      if ( (*(int (__fastcall **)(struct IMsoOLDocument *, _QWORD, __int64))(*(_QWORD *)v1157 + 232LL))(v1157, 0, 1) < 0 )
      {
        Error(196658);
        XlsDiag::SendTraceTag(18088268, 187, 10);
        v1037 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        v1023 = 24737554;
        *(_DWORD *)(v1037 + 2024) = 0;
        *(_DWORD *)(v1037 + 2028) = 0;
        goto LABEL_1888;
      }
      goto LABEL_1072;
    }
    v471 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1304LL);
    *(_WORD *)(v471 + 56) &= ~8u;
    *(_WORD *)(v471 + 56) |= 8 * (_WORD)v275;
    v475 = 0;
    if ( !(unsigned int)FErrPstgi(v265) )
    {
      v472 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
      v473 = OlDocFilePath::PClpDocument(v472);
      v474 = STGI::Lpstg(v265);
      if ( !(unsigned int)FDrmQueryRightsStg(v474, 4u, v473) )
        v475 = 1;
    }
    v1183 = v475;
    if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1836LL) )
    {
      if ( !(unsigned int)FErrPstgi(v265) )
      {
        v476 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
        v477 = OlDocFilePath::PClpDocument(v476);
        v478 = STGI::Lpstg(v265);
        if ( !(unsigned int)FDrmQueryRightsStg(v478, 2u, v477) )
        {
          StreamClose(v1167);
          StgiFileClose(v265);
          HandleLockError(327752);
          v1023 = 24737555;
          v1038 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          v115 = -1662124019;
          *(_DWORD *)(v1038 + 2024) = 0;
          *(_DWORD *)(v1038 + 2028) = 0;
          goto LABEL_1889;
        }
      }
    }
    v68 = v1158;
    lp = *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL);
    if ( v1158 )
    {
      v479 = a10 & 0x400;
      v480 = PivotOperationBase::PSxview((PivotOperationBase *)v1158);
      *((_WORD *)v480 + 18) &= ~0x40u;
      *((_WORD *)v480 + 18) |= v479 != 0 ? 0x40 : 0;
    }
    if ( (a10 & 0x8000) != 0 )
      OSRR::SetHasInvalidPivot((OSRR *)&v1235, 1);
    v481 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1339);
    CchStToStz(v481, v1582, 2084);
    v482 = APPCORE::PmemheapMain((APPCORE *)&vapp);
    MaxPathHolder::MaxPathHolder((MaxPathHolder *)v1481, v482, 259, 0);
    v483 = FileSource::HrGetFileTemp(v1305, 10);
    v1152 = v483;
    v115 = v483;
    if ( v483 < 0 )
    {
      XlsDiag::LogSetHrCoreTag(v483, 0x27413A3u);
      StreamClose(v1167);
      StgiFileClose(v265);
      Error(327845);
      MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1481);
      goto LABEL_1856;
    }
    v484 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
    v485 = (LXBASE *)OpenTelemetry::POpenFileStageModel(v484);
    v486 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1399, 0x1F0CB5C7u);
    SXVWGEOM::RwFirst(v486);
    WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v485);
    v487 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1481);
    v488 = HrLoadBiff(
             &v1167,
             &v1567,
             v1582,
             v487,
             v169,
             a5,
             a7,
             v265,
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
    if ( v488 < 0 )
    {
      v1166 = v488;
      MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1481);
      goto LABEL_1133;
    }
    MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1339, v1582);
    if ( !v1153 && OSRR::FReadyForOsr((OSRR *)&v1235) )
    {
      XlsDiag::LogSetHrCoreTag(-2147024809, 0x205C2A1u);
      v1155 = 1;
      MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1481);
      v409 = v1161;
      goto LABEL_744;
    }
    if ( lp != *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL)
      && (unsigned int)FResidentBook(lp) )
    {
      v1303 = *(struct SH **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 32LL);
      v489 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1400, 0x2375A798u);
      v490 = SXVWGEOM::RwFirst(v489);
      v491 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 128LL);
      v492 = 0;
      if ( v491 )
      {
        v493 = v491;
        do
        {
          v492 = v493[1];
          if ( v492 )
            break;
          v491 = (_QWORD *)*v491;
          v493 = v491;
        }
        while ( v491 );
      }
      LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v492 + 96), lp, v490);
    }
    if ( v1153 && *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL) )
    {
      if ( !v1172 )
      {
        v494 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1481);
        if ( (unsigned int)HrCheckCollaboration(v278, v494) == -2147467260 )
        {
          errDeferred = 0;
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1220;
          LOBYTE(v265) = 0;
          if ( v68 )
          {
            v576 = PivotOperationBase::PSxview((PivotOperationBase *)v68);
            *((_WORD *)v576 + 18) |= 8u;
          }
          v115 = -2147467260;
          XlsDiag::LogSetHrCoreTag(-2147467260, 0x1797714u);
          v1153 = 0;
          MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1481);
          goto LABEL_1664;
        }
      }
      v495 = (struct WNX *)UIGLOBALS::UIGLOBALSCONTAINER::m_selection;
      v1174 = 1;
      if ( !UIGLOBALS::UIGLOBALSCONTAINER::m_selection )
      {
        SetWnxSel(*(struct WNX **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 104LL));
        v495 = (struct WNX *)UIGLOBALS::UIGLOBALSCONTAINER::m_selection;
      }
      FActivateListWnx(v495, 1, 0);
    }
    MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1481);
LABEL_901:
    if ( v1153 == 16 )
    {
      if ( v169 || (v502 = 1024, v1163) )
        v502 = 1025;
      v265 = FileSource::HpstgiFileOpen((FileSource *)v1305, &v1567, v502, 0, 0, 0, 0, 0, v1213);
      v1215 = v265;
      v1188 = 1;
      v1153 = 0;
      if ( !(unsigned int)FErrPstgi(v265) )
        goto LABEL_969;
      v1152 = -2146827284;
      v115 = -2146827284;
      XlsDiag::LogSetHrCoreTag(-2146827284, 0x230E203u);
    }
    else
    {
      v265 = v1215;
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
    if ( !(unsigned int)sub_140486720((unsigned int)v1194, (unsigned int)v1223) || v1153 == 2 )
    {
      v509 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
      if ( *(_QWORD *)(v509 + 40) && (v1153 == 1 || (*(_DWORD *)(*(_QWORD *)(v509 + 40) + 884LL) & 0x200) != 0) )
      {
        if ( (unsigned int)IMsoOLDocument::IsInFileSys(v1157) )
        {
          v510 = (wchar_t **)XLSBOOK::Plxtab(*(XLSBOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                     + 304LL)
                                                         + 40LL));
          FreeHpstTempPath((struct STB *)v510);
          if ( v1187 )
          {
            v511 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1482);
          }
          else if ( FileSource::FCloudStreaming((FileSource *)v1305) )
          {
            v512 = std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
            v511 = (const wchar_t *)OfficeExtension::ServerRuntime::RichApiMessageEntry::GetTarget(v512);
          }
          else
          {
            v511 = FileSource::StzFilePath((FileSource *)v1305);
          }
          if ( (int)HrStDupSt(v511, v510 + 21) < 0 )
            v510[21] = 0;
        }
        v513 = *(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL);
        v514 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1402, 0x236962A0u);
        v515 = SXVWGEOM::RwFirst(v514);
        BOOK::SetPioldoc(v513, v1157, v515);
        v516 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        if ( *(_QWORD *)(v516 + 40) != v1301
          && (*(_DWORD *)(*(_QWORD *)(v516 + 40) + 1440LL) & 0x8000000) != 0
          && (*(unsigned int (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1157 + 208LL))(v1157) == 2 )
        {
          v517 = v1213;
          XlAsyncFileIO::SpOLDocCoauthFromPOLDoc(v1338, v1157);
          if ( (unsigned __int8)std::shared_ptr<Mso::ActivityScope::IMsoLoggingScope>::operator bool(v1338)
            && (v518 = BKORWS::Psh((BKORWS *)v1338), XlAsyncFileIO::FIsDistributedBlobsFile(v518)) )
          {
            v1199 = 1;
            v519 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1403, 0x1E307684u);
            v520 = SXVWGEOM::RwFirst(v519);
            OldocHelper::SetReadOnly(v1157, v520);
            if ( v517 )
            {
              v521 = Mso::Telemetry::Activity::DataFields(v517);
              Mso::Telemetry::IDataFieldCollection::Add(v521, "SwitchToRO", "ZipItOldocSetReadOnly");
            }
          }
          else
          {
            HrRecordEvent(v1157, 0x40000000u, 0);
            v522 = (*(__int64 (__fastcall **)(struct IMsoOLDocument *, __int64, _QWORD, _QWORD))(*(_QWORD *)v1157 + 104LL))(
                     v1157,
                     4,
                     0,
                     *(int *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                        + 1232LL)
                            + 80LL));
            if ( v522 - 3473424 <= 1 )
              XlFileProtocolManager::TrackOpen(v1157);
            if ( v517 )
            {
              v523 = Mso::Telemetry::Activity::DataFields(v517);
              Mso::Telemetry::IDataFieldCollection::Add<int>(v523, "SwitchToRO", v522, 4);
            }
          }
          v524 = *(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL);
          v525 = (struct IMsoXmlDataStore *)*((_QWORD *)v524 + 604);
          v526 = BOOK::Pioldoc(v524);
          XlMsoMockable::MsoHrCreateMetadataProfile(v526, v525, 0);
          v527 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          *(_DWORD *)(*(_QWORD *)(v527 + 40) + 1440LL) &= ~0x8000000u;
          Mso::TCntPtr<Uxpp::UxppAnnotationsService>::~TCntPtr<Uxpp::UxppAnnotationsService>(v1338);
        }
        v528 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        if ( *(_QWORD *)(v528 + 40) != v1301 )
        {
          OutSpace = BOOK::GetOutSpace(*(BOOK **)(v528 + 40));
          if ( OutSpace )
          {
            v530 = *(void (__fastcall **)(struct OfficeSpace::IOutSpace *, _QWORD, struct IMsoOLDocument *))(*(_QWORD *)OutSpace + 312LL);
            v531 = BOOK::Pioldoc(*(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                          + 40LL));
            v530(OutSpace, 0, v531);
          }
        }
        if ( v1288 )
        {
          v532 = BOOK::Pioldoc(*(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                        + 40LL));
          ShowOdsRegexBusBar(v532);
        }
        if ( (unsigned int)FContainPowerView(*(const struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                               + 304LL)
                                                                   + 40LL))
          && !(unsigned int)Excel::Addins::FPowerViewAddinEnabled(0, v533) )
        {
          v534 = BOOK::Pioldoc(*(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                        + 40LL));
          ShowPowerBiBusBar(v534);
        }
      }
      goto LABEL_953;
    }
    if ( (unsigned int)FIsShareErr(errDeferred) && (_QWORD)xmmword_143FE0F90 )
      goto LABEL_987;
    HrRecordEvent(v1157, 0x40000000u, 0);
    v503 = v1161;
    v1178 = 0;
    if ( *v1161 )
      _IMsoOLDocument_SetIReDownload(*v1161, -1);
    v504 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1401, 0x236962A1u);
    v505 = SXVWGEOM::RwFirst(v504);
    v506 = OlDocFilePath::FReleaseIOLDoc(&v1157, 1, 1, v505);
    *v503 = 0;
    if ( v1153 && !v506 )
    {
      errDeferred = 0;
      v507 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
      *(_DWORD *)(v507 + 2024) = 0;
      *(_DWORD *)(v507 + 2028) = 0;
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1220;
      LOBYTE(v265) = 0;
      if ( v68 )
      {
        v508 = PivotOperationBase::PSxview((PivotOperationBase *)v68);
        *((_WORD *)v508 + 18) |= 8u;
      }
      v115 = -2146827284;
      XlsDiag::LogSetHrCoreTag(-2146827284, 0x1797715u);
      goto LABEL_467;
    }
LABEL_954:
    if ( v1154 && v1178 && v1153 != 2 && (!(unsigned int)FIsShareErr(errDeferred) || !(_QWORD)xmmword_143FE0F90) )
    {
      v535 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
      if ( !*(_QWORD *)(v535 + 40) || (*(_DWORD *)(*(_QWORD *)(v535 + 40) + 884LL) & 0x200) == 0 )
      {
        if ( (a10 & 0x100) != 0 )
        {
          v536 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1404, 0x21C730Fu);
          v537 = SXVWGEOM::RwFirst(v536);
          OldocHelper::SetAttrInAttrMask(v1157, 0, 0x100000u, v537);
        }
        if ( v1199 && v1153 )
        {
          v538 = Measurements::Stopwatch::Stopwatch((Measurements::Stopwatch *)v1537);
          LOBYTE(v539) = 1;
          Measurements::MeasureElapsedTime::MeasureElapsedTime(
            v1525,
            Measurements::MeasurementId::ExcelRecordEvent,
            v539,
            v538);
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
          v546 = BKORWS::Psh((BKORWS *)&v1179);
          if ( (unsigned int)XlFileProtocolManager::HrRecordEvent(v1157, 0x40000000u, v1153 != 0, v1200, v546) == -1662189464 )
          {
            v115 = -1662189464;
            XlsDiag::LogSetHrCoreTag(-1662189464, 0x1E26384Cu);
            v1178 = 0;
            goto LABEL_1877;
          }
        }
        v1178 = 0;
      }
    }
    if ( !(unsigned int)FIsShareErr(errDeferred) || !(_QWORD)xmmword_143FE0F90 )
      goto LABEL_1105;
    v547 = 304;
    if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                   + 104LL) == 2 )
    {
      v590 = v1210;
      if ( v1210 == 1 )
      {
        LOBYTE(v547) = v1183;
        v590 = sub_141224EE0(v1157, v547, &v1195);
        v1210 = v590;
        if ( v1195 )
          OSRR::SetAppAllowed((OSRR *)&v1235, 0);
      }
      else
      {
        sub_1413EF4D0();
      }
      if ( v590 < 0 )
      {
        if ( SbFromHpCore(v1167) )
          StreamClose(v1167);
        if ( !(unsigned int)FErrPstgi(v265) )
          StgiFileClose(v265);
        v1215 = 0;
        v1167 = 0;
        v115 = v590;
        XlsDiag::LogSetHrCoreTag(v590, 0x1797717u);
        v1153 = 0;
LABEL_1093:
        errDeferred = 0;
        v588 = NtCurrentTeb()->ThreadLocalStoragePointer;
        v1165 = 1;
        v589 = *(_QWORD *)(*(_QWORD *)v588 + 304LL);
        *(_DWORD *)(v589 + 2024) = 0;
        *(_DWORD *)(v589 + 2028) = 0;
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1220;
        LOBYTE(v265) = 0;
        if ( v68 )
        {
LABEL_830:
          v466 = PivotOperationBase::PSxview((PivotOperationBase *)v68);
          *((_WORD *)v466 + 18) |= 8u;
        }
LABEL_518:
        v278 = v1160;
LABEL_1664:
        if ( v1542 )
        {
          v920 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1462);
          CchStToSt(v920, v278, v1224);
        }
        XslClear((struct XSL *)&v1541);
        if ( v1170 && v1269 )
          FreeRevert(v1269);
        if ( !OSRR::IsAppAllowed((OSRR *)&v1235) && (unsigned int)XLOSRR::FMustUseOsr((XLOSRR *)&v1235) )
        {
          OkAlert(589889, 0);
          v115 = -2147467260;
          v1217 = -2147467260;
          v1153 = 0;
          XlsDiag::LogSetHrCoreTag(-2147467260, 0x179771Bu);
        }
        v409 = v1161;
        vpoldocument = v1349;
        if ( v1154 && *v1161 && v1239 != -2 )
        {
          if ( v1153
            || (v921 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL), *(_QWORD *)(v921 + 40))
            && (*(_DWORD *)(*(_QWORD *)(v921 + 40) + 884LL) & 0x200) != 0 )
          {
            if ( v1178 )
            {
              v928 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
              if ( *(_QWORD *)(v928 + 40) && (*(_DWORD *)(*(_QWORD *)(v928 + 40) + 884LL) & 0x200) != 0 )
                XlFileProtocolManager::MarkOpenDone(v1157, 1, 0);
              HrRecordEvent(v1157, 0x40000000u, 1);
            }
            (*(void (__fastcall **)(struct IMsoOLDocument *, _QWORD, __int64))(*(_QWORD *)*v409 + 56LL))(*v409, 0, 7);
          }
          else
          {
            if ( v1178 )
            {
              v922 = (OlDocFilePath *)std::_Optional_construct_base<OlDocFilePath>::operator*(v1539);
              OlDocFilePath::RecordEventForCloseOldoc(v922, v1157, 0);
            }
            _IMsoOLDocument_SetIReDownload(*v409, -1);
            if ( (*(unsigned int (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1157 + 208LL))(v1157) )
              MsoShipAssertTagProc(946484024);
            if ( lp )
            {
              v923 = *v409;
              if ( BOOK::Pioldoc(lp) == v923 && !(unsigned int)FOsrhInTransition() )
              {
                v924 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1430, 0x2369629Bu);
                v925 = SXVWGEOM::RwFirst(v924);
                BOOK::SetPioldoc(lp, 0, v925);
              }
            }
            v926 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1431, 0x2369629Au);
            v927 = SXVWGEOM::RwFirst(v926);
            OlDocFilePath::FReleaseIOLDoc(v409, 0, 1, v927);
            *v409 = 0;
          }
        }
        v929 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1304LL);
        *(_WORD *)(v929 + 56) &= ~8u;
        if ( !v1155 && !*(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 2436LL) )
        {
          if ( v1153 && lp && !(unsigned int)XLSWORKBOOK::FAddin((struct BOOK *)((char *)lp + 1640)) )
          {
            v930 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
            HrRegisterDynamicUdfs(v930, &v1193);
          }
          v931 = Mso::Telemetry::Activity::DataFields(v1213);
          LOBYTE(v932) = v1193;
          Mso::Telemetry::IDataFieldCollection::Add<bool>(v931, "FUdfNeedsRecalc", v932, 4);
        }
        if ( v1153 == 1 && lp && (v1194 != 256 || v1223 == 4) && (v1194 & 0xE80) == 0 )
        {
          VbaLoadRefBegin();
          if ( (sksEvt & 4) == 0 || (v933 = 1, v1318) )
            v933 = 0;
          HrBookLoadComplete(lp, v933, (struct LoadRecovery *)v68, 1, &v1207);
          if ( (unsigned int)FBookHasProject(lp, 1) )
          {
            v934 = HprojectFromPbook(lp);
            HrVbpSetDirty(v934, 0);
          }
          VbaLoadRefEnd();
          if ( !v1195 )
          {
            if ( v1157 )
            {
              v935 = BOOK::Pioldoc(lp);
              if ( v1157 == v935 )
              {
                v936 = XLSWORKBOOK::Pcm((struct BOOK *)((char *)lp + 1640));
                if ( CardView::DataElementRecord::FExpanded(v936) )
                  sub_1412CF650(lp);
              }
            }
          }
        }
        if ( lp )
          XLSWORKBOOK::PostDocumentLoad((char *)lp + 1640, 0, 0);
        if ( v1193 && !v1207 )
        {
          v937 = LOCATIONCONTEXTDATA::PWorkbookCur((LOCATIONCONTEXTDATA *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                     + 304LL)
                                                                         + 8LL));
          v938 = (OcsTransitionController *)PivotMetadataCache::PvMemProps(v937);
          v939 = OcsTransitionController::PCoauthTransitionState(v938);
          Api::RecalcService::HrRecalcAll(v939, 0);
        }
        if ( !v1153 || !lp || v1195 || !BOOK::Pioldoc(lp) || (v940 = BOOK::Pioldoc(lp), v941 = 1, v1157 != v940) )
          v941 = 0;
        if ( v941 )
          XlFileProtocolManager::MarkOpenDone(v1157, 1, 0);
        v942 = v1274;
        if ( !BKORWS::Psh(v1274) || !v941 )
          goto LABEL_1755;
        v943 = XLSWORKBOOK::Pcm((struct BOOK *)((char *)lp + 1640));
        if ( !CardView::DataElementRecord::FExpanded(v943) )
          goto LABEL_1750;
        v1203 = 0;
        v1204 = 0;
        if ( v68 && BOOK::FRepairedBookCloudFile(lp) )
        {
          v944 = BKORWS::Psh(v942);
          v945 = LoadRecovery::StmfOfRepair(v68);
          QuickLoadContext::SetWorkbookRepairStmf(v944, v945);
        }
        v946 = BKORWS::Psh(v942);
        v947 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
        v948 = v946;
        v949 = v1296;
        v950 = XlAsyncFileIO::HrHandlePostLoadTasks(v947, v1296, v948, &v1221, &v1203, &v1204);
        if ( v950 == -2147023673 )
        {
          v1319 = 0;
          Title = Mso::Swagger::Schema::GetTitle(v949);
          LOBYTE(v1046) = std::nullopt;
          v1047 = Title;
          if ( !(unsigned __int8)std::operator==<XlsActivity>(Title, v1046) )
          {
            v1048 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1360, 0x28572D2u);
            v1049 = SXVWGEOM::RwFirst(v1048);
            v1050 = (Mso::Telemetry *)std::_Optional_construct_base<XlsActivity>::operator*(v1047);
            Mso::Telemetry::SetActivityResultHr(v1050, (struct Mso::Telemetry::Activity *)v950, v1049, v1051);
          }
          v1052 = HrDoCloseBookCore(&v1319, 0, 0, 0, 1, 0, 0);
          if ( v1052 < 0 )
            XlsDiag::LogSetHrCoreTag(v1052, 0x280659Bu);
          lp = 0;
          sub_1402DA5D0(&v1541, v1333, v1053);
          fCeCanceled = 1;
          v115 = v950;
          XlsDiag::LogSetHrCoreTag(v950, 0x280659Cu);
          v1153 = 0;
          goto LABEL_1930;
        }
        if ( !v1203 )
        {
          BOOK::StartCoauth(lp, 1);
LABEL_1750:
          v957 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
          v958 = FeatureGateCollectionBase<GuidedReapplyFeatureGates>::Instance(v957);
          if ( (unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(v958 + 40) )
          {
            v959 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
            v1330 = 0;
            v960 = v959;
            Api::ReloadContext::RetrieveRctxFromWorkbook(v959, &v1330);
            if ( v1330 && Api::ReloadContext::FHasData(v1330) )
              Api::ReloadContext::RestoreCoauthPanesPostReload(v1330, v960);
            XlAsyncFileIO::ClearReloadContext(v960);
          }
LABEL_1755:
          if ( (unsigned __int8)CircularReferenceTailValue::FGetFlagsShadowBag(&vapp) && v68 )
          {
            LoadRecovery::StmfOfRepair(v68);
            FormatCh_ProcIds((void *const *)&vapp);
          }
          v962 = v1296;
          v963 = lp;
          if ( v1296 && lp && v1159 )
          {
            ZrtUtility::RenderWindowsPostContentNotification(lp, UIGLOBALS::UIGLOBALSCONTAINER::m_pwnChoEdit, v961);
            v964 = v1177;
            v965 = BOOK::Pioldoc(lp);
            ZrtUtility::LogZrtOpenInformation(v965, v962, (struct XlSyncStateChangeListenerLoad *)v964, v966);
            v963 = lp;
          }
          if ( v1153 == 1 )
          {
            if ( v963 )
            {
              if ( !(unsigned int)FOsrhBook(v963) )
              {
                v1205 = 0;
                v967 = CastOrNull<XLSWORKBOOK,BOOK>(lp);
                CoauthUtil::RunDuplicateUidCheck(v967, 2, &v1205);
                if ( v1205 )
                {
                  v968 = v1274;
                  if ( BKORWS::Psh(v1274) )
                  {
                    v969 = BKORWS::Psh(v968);
                    QuickLoadContext::SetCoauthStateChanged(v969, 1);
                  }
                }
              }
            }
          }
          FPioldocReadOnly(*(const struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                             + 304LL)
                                                 + 40LL));
          XlsDiag::SendTraceTag(7091154, 187, 50);
          v970 = v1153;
          if ( v1153 && fShowWn )
          {
            v971 = lp;
            if ( lp && (*((_BYTE *)lp + 1440) & 0x10) == 0
              || (v972 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL),
                  *(_QWORD *)(v972 + 40))
              && (*(_DWORD *)(*(_QWORD *)(v972 + 40) + 884LL) & 0x200) != 0 )
            {
              v973 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
              if ( !*(_DWORD *)(v973 + 1836) )
              {
                if ( !lp )
                  v971 = *(struct BOOK **)(v973 + 40);
                v974 = v1173;
                v975 = BOOK::Pioldoc(v971);
                MsoSetReadWriteOnSaveIoldoc(v975, v974);
                XlsDiag::SendTraceTag(7091155, 187, 50);
                if ( ((v1230 - 1) & 0xFFFFFFFD) != 0 )
                {
                  v976 = 0;
                  if ( (int)sub_14046F680(v971) < 0 )
                  {
                    Only = FPioldocReadOnly(v971);
                    v976 = (unsigned __int8)FIsTrue<int>(Only) != 0;
                  }
                  v978 = BOOK::Pioldoc(v971);
                  v1173 = MsoFReadWriteOnSaveIoldoc(v978) != 0;
                  if ( !BOOK::FFailedLockTransition(v971)
                    && !AsyncFileLockHandler::FPendingLockTransitionToState(v971, 0)
                    || (*((_DWORD *)v971 + 221) & 0x200) != 0 )
                  {
                    AssistedReading::ResetAssistedReading(v971, 8u, 0);
                  }
                  if ( v976 && Api::Workbook::FHasReadOnlyRecommended((struct BOOK *)((char *)v971 + 1640)) )
                  {
                    v1173 = 0;
                    v979 = BOOK::Pioldoc(v971);
                    MsoSetReadWriteOnSaveIoldoc(v979, 0);
                  }
                }
                FileLoad::ShowVersionFileBusBar(v1160, v971);
                if ( XLSWORKBOOK::Prdsharedmanager((struct BOOK *)((char *)v971 + 1640)) )
                {
                  v980 = XLSWORKBOOK::Prdsharedmanager((struct BOOK *)((char *)v971 + 1640));
                  LinkedEntityFeature = Api::RichDataSharedManager::GetLinkedEntityFeature(v980);
                  if ( Api::LinkedEntityFeature::FShouldShowFinanceBusinessBar(LinkedEntityFeature) )
                  {
                    if ( (unsigned int)FOsrc() )
                    {
                      OsrcSetFEverHadFinanceLinkedEntity(v971);
                    }
                    else
                    {
                      v982 = (RichDataManagerHost *)CastOrNull<XLSWORKBOOK,BOOK>(v971);
                      RichDataManagerHost::FShowFinanceBusinessBar(v982, v983);
                    }
                  }
                }
                v984 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)v971 + 1640));
                CleanupWorkbookStylesBusinessBar::ShowCleanupWorkbookStyleskBusinessBarIfNeeded(v984, v985);
                v970 = v1153;
                goto LABEL_1793;
              }
            }
          }
          else
          {
LABEL_1793:
            v971 = lp;
          }
          v986 = v1308;
          FileLoad::CheckAttemptRepair(
            v971,
            (struct LoadRecovery *)v68,
            v970,
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
LABEL_1989:
              v1069 = (CorruptionMetaData *)std::_Optional_construct_base<CorruptionMetaData>::operator*(v1538);
              CorruptionMetaData::MarkAsCorrupt(v1069);
              if ( !v68 )
                goto LABEL_1996;
              if ( (unsigned int)OfficeSharedApiImpl::UserFeedbackScreenshotInfo::GetScreenshotSourceType(v68) == -2147418113 )
              {
                v1071 = 459015;
                goto LABEL_1998;
              }
              v1070 = (Mso::History *)(unsigned int)v1177;
              if ( v1177 == -2134188030 || v1177 == -2134142954 )
              {
                v1320 = 256;
                MetroFGetErrorWz(v1177, v1575, &v1320);
                ErrorAlert(459023, v1575);
              }
              else
              {
LABEL_1996:
                if ( !Mso::History::IsVersionCrawlForRepairEnabled(v1070)
                  || (int)FileLoad::HrCheckVersionHistoryRepair(v1160) < 0 )
                {
                  v1071 = 458893;
LABEL_1998:
                  Error(v1071);
                }
              }
LABEL_2033:
              if ( v1153 )
              {
LABEL_2034:
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
                v1081 = Measurements::Stopwatch::Stopwatch((Measurements::Stopwatch *)v1534);
                LOBYTE(v1082) = 1;
                Measurements::MeasureElapsedTime::MeasureElapsedTime(
                  v1527,
                  Measurements::MeasurementId::ExcelPQEventing,
                  v1082,
                  v1081);
                v1083 = (struct Api::Workbook *)CastOrNull<XLSWORKBOOK,BOOK>(lp);
                XLSEVENTDISPATCHER::HrOnWorkbookOpen(v1083);
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
                      v1085 = BOOK::Pioldoc(*(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                 + 304LL)
                                                     + 40LL));
                      ShowPowerQueryIEBusBar(v1085);
                    }
                  }
                }
                Measurements::MeasureElapsedTime::~MeasureElapsedTime((Measurements::MeasureElapsedTime *)v1527);
                v1086 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL);
                if ( *(_DWORD *)(v1086 + 104) == 1 )
                {
                  *((_DWORD *)lp + 644) |= 0x20u;
                }
                else if ( *(_DWORD *)(v1086 + 104) == 2 )
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
                    v1087 = IdwaFromIds(458968);
                    MsoDoWatsonAlertBegin(v1087, 0, 0, (struct WADD *)v1547);
                  }
                  v1088 = v1185 & 4;
                  if ( (a10 & 0x20) != 0 || (v1089 = FOsrhInTransition(), v1090 = 0, v1089) )
                    v1090 = 1;
                  v1091 = XlUIMockable::HrShowRecoveryErrors2(lp, v1090, v1088, 0);
                  v605 = v1091;
                  if ( (_BYTE)v265 )
                  {
                    if ( v1091 < 0 )
                    {
LABEL_1742:
                      v1166 = v605;
                      goto LABEL_1133;
                    }
                  }
                  else if ( v1091 < 0 )
                  {
                    v801 = 512506015;
                    v802 = (MsoReserveTag *)&v1362;
                    goto LABEL_1920;
                  }
                  if ( *((char *)lp + 892) >= 0 )
                  {
                    std::optional<EditCommandTrackingFreezer>::optional<EditCommandTrackingFreezer>(v1241);
                    v1092 = FeatureGateCollectionBase<CoauthFeatureGates>::Instance();
                    if ( (unsigned __int8)Mso::AB::Optimized::FeatureGate::operator bool(v1092 + 408) )
                      std::optional<EditCommandTrackingFreezer>::emplace<>(v1241);
                    v1093 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1363, 0x231C69Fu);
                    v1094 = SXVWGEOM::RwFirst(v1093);
                    BookDirty(lp, 1, v1094);
                    std::optional<EditCommandTrackingFreezer>::~optional<EditCommandTrackingFreezer>(v1241);
                  }
                  if ( *((_QWORD *)lp + 162) )
                    MsoDoWatsonAlertEnd((struct WADD *)v1547, *((const wchar_t **)lp + 163));
                }
                v1095 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                v1096 = *(_QWORD *)(v1095 + 872);
                if ( *(_DWORD *)(v1096 + 104) != 1 && (*(_BYTE *)(v1096 + 8) & 1) == 0 )
                {
                  v1097 = *(_QWORD *)(v1095 + 1328);
                  if ( *(_DWORD *)(v1097 + 20) )
                  {
                    Sz = 0;
                    if ( wverLastXLSaved < 3 || *(char *)(v1097 + 20) < 0 )
                      Sz = CchLoadSz(v1571, 327873, 256);
                    v1099 = CchLoadSz(&v1571[Sz], 327874, 256 - Sz);
                    v1100 = (__int64 *)NtCurrentTeb()->ThreadLocalStoragePointer;
                    v1101 = v1099 + Sz;
                    v541 = *v1100;
                    v1102 = *(_QWORD *)(*(_QWORD *)(*v1100 + 304) + 1328LL);
                    if ( (*(_DWORD *)(v1102 + 20) & 0x10) == 0 && *(char *)(v1102 + 20) >= 0 )
                      goto LABEL_2075;
                    v1103 = -1161035032;
                    *(_DWORD *)(v1102 + 20) &= (*(_DWORD *)(v1102 + 20) & 0x10) != 0 ? -17 : -129;
                    while ( 1 )
                    {
                      v1101 += CchLoadSz(&v1571[v1101], v1103, 256 - v1101);
LABEL_2075:
                      v1104 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                        + 1328LL);
                      v1105 = *(_DWORD *)(v1104 + 20);
                      if ( (v1105 & 0x20) != 0 )
                      {
                        v1103 = -1161035031;
                        v1106 = v1105 & 0xFFFFFFDF;
                      }
                      else
                      {
                        if ( (v1105 & 0x40) == 0 )
                        {
                          v542 = 512;
                          if ( (unsigned __int64)(2LL * v1101) < 0x200 )
                          {
                            v1571[v1101] = 0;
                            ShowAlert(10, 458968, v1571, 0, 0, 0);
                            goto LABEL_1949;
                          }
LABEL_2132:
                          _report_rangecheckfailure(v542, v541);
                        }
                        v1103 = -1161035030;
                        v1106 = v1105 & 0xFFFFFFBF;
                      }
                      *(_DWORD *)(v1104 + 20) = v1106;
                    }
                  }
                }
              }
              goto LABEL_1949;
            }
            if ( v68 )
            {
              if ( (int)LoadRecovery::Lrmode(v68) > 0
                && (*((_BYTE *)PivotOperationBase::PSxview((PivotOperationBase *)v68) + 36) & 8) == 0
                && !v1153 )
              {
                v1072 = v1177;
                if ( v1177 == -2147023673 || v1177 == -2147467260 || *(&vscd + 1) )
                {
                  if ( *(&vscd + 1) )
                  {
                    v115 = -2147467260;
                    v1073 = 33931969;
                    v1072 = -2147467260;
                    goto LABEL_2010;
                  }
                  v115 = v1177;
                  if ( v1177 < 0 )
                  {
                    v1073 = 33931970;
LABEL_2010:
                    XlsDiag::LogSetHrCoreTag(v1072, v1073);
                  }
                  v1074 = 0;
                  v1075 = 458924;
LABEL_2023:
                  OkAlert(v1075, v1074);
                  goto LABEL_2033;
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
                    v1077 = v1577;
                    v1078 = 467262;
                    goto LABEL_2032;
                  }
                  if ( v1153 )
                    goto LABEL_2034;
                }
                v1079 = (ODFROBUSTLOAD *)OfficeSharedApiImpl::UserFeedbackV2Config::GetAffectedProcessSessionId(v68);
                if ( ODFROBUSTLOAD::FPasswordHashFound(v1079) )
                {
                  v115 = -2147467260;
                  XlsDiag::LogSetHrCoreTag(-2147467260, 0x205C2C3u);
                  v1075 = 459071;
                }
                else
                {
                  if ( v1153 )
                    goto LABEL_2034;
                  v1080 = (ODFROBUSTLOAD *)OfficeSharedApiImpl::UserFeedbackV2Config::GetAffectedProcessSessionId(v68);
                  if ( !ODFROBUSTLOAD::FBadNullDate(v1080) )
                    goto LABEL_2033;
                  v115 = -2147467260;
                  XlsDiag::LogSetHrCoreTag(-2147467260, 0x205C2C4u);
                  v1075 = 459072;
                }
                v1074 = v1568;
                goto LABEL_2023;
              }
            }
            if ( !v1187
              || !(unsigned int)Mso::Details::ConstexprFunctorBase<Mso::IFunctor<bool,FeaturePropertyValue const &,FeaturePropertyValue const &>>::Release(&vapp)
              || (unsigned int)FOsrhInTransition()
              || (unsigned int)FOsrc() )
            {
              goto LABEL_2033;
            }
            CchSzToSt(*((const wchar_t **)v1342 + 3), v1574, 255);
            SuppressStExt(v1574, 255);
            if ( v1153 )
            {
              CchInsert2St(v1573, 459073, &v1567, v1574, 255);
              v1078 = 467265;
            }
            else
            {
              v115 = -2146827284;
              XlsDiag::LogSetHrCoreTag(-2146827284, 0x205C2C5u);
              CchInsert2St(v1573, 459075, &v1567, v1574, 255);
              v1078 = 467267;
            }
            v1077 = v1573;
LABEL_2032:
            OkInfoAlert(v1078, v1077);
            goto LABEL_2033;
          }
          if ( v1264 )
            goto LABEL_1989;
          if ( v1172 && !(unsigned int)FOsrcHostedByExcel() )
          {
            SetLoadForPreviewError(-2042494972);
            v1218 = 0;
            v1162 = 0;
            goto LABEL_1821;
          }
          if ( !v1218 )
          {
            v987 = FOsrhInTransition();
            v1162 = FIsTrue<int>(v987);
            if ( v1162 || (unsigned __int8)CircularReferenceTailValue::FGetFlagsShadowBag(&vapp) || (v988 = 0, v1159) )
              v988 = 1;
            v1162 = v988;
            if ( !v988 )
            {
              if ( v1240 && !MsoFDrmUIEnabled() )
              {
                Error(589882);
                goto LABEL_1821;
              }
              if ( (unsigned int)FOsrc() )
              {
                Osrc = GetOsrc();
                v990 = OSRC::DwPromptUser(Osrc, 0, 0, 0, 0, 0);
                v1162 = v990 != 0;
                if ( !v990 )
                  SetLoadForPreviewError(-2147467260);
                goto LABEL_1821;
              }
              if ( v1273 && VersionHistoryWindowParams::FSkipCorruptVersionOpens(v1273) )
              {
                v991 = 504443348;
LABEL_1817:
                v115 = -2146827284;
                XlsDiag::LogSetHrCoreTag(-2146827284, v991);
                v986 = v1308;
                goto LABEL_1821;
              }
              if ( (unsigned int)Art::IOMHost::GetEnvId((Art::IOMHost *)&vapp) )
              {
                if ( (unsigned int)YesNoAlert(458912, v1568) != 6 )
                {
                  v115 = -2146827284;
                  XlsDiag::LogSetHrCoreTag(-2146827284, 0x230E208u);
                  goto LABEL_1821;
                }
              }
              else if ( (unsigned int)XlUIMockable::NoYesAlert(458912, v1568) != 6 )
              {
                v991 = 36758023;
                goto LABEL_1817;
              }
              v1162 = 1;
            }
          }
LABEL_1821:
          v992 = (CorruptionMetaData *)std::_Optional_construct_base<CorruptionMetaData>::operator*(v1538);
          CorruptionMetaData::MarkAsCorrupt(v992);
          if ( !v1218 && !v1162 )
            goto LABEL_2033;
          if ( v1231 || (*((_BYTE *)PivotOperationBase::PSxview((PivotOperationBase *)v68) + 36) & 2) != 0 )
          {
            BookCorrupt = LoadRecovery::GrbitGetBookCorrupt((LoadRecovery *)v68);
            v1000 = PivotMetadataCache::PvMemProps((PivotMetadataCache *)v68);
            LoadRecovery::HrHandleLoadMode((LoadRecovery *)v68, v1000 == (void *)BookCorrupt);
            LoadRecovery::HrHandleLoadMode((LoadRecovery *)v68, v1231);
            v1001 = LoadRecovery::GrbitGetBookCorrupt((LoadRecovery *)v68);
            LoadRecovery::GrbitSetBookCorruptOld((LoadRecovery *)v68, v1001);
          }
          else
          {
            if ( !v68 || (v44 = (int)LoadRecovery::Lrmode(v68) <= 0, v993 = 1, v44) )
              v993 = 0;
            v994 = (LoadRecovery *)v68;
            if ( v993 )
            {
              LoadRecovery::IncrementRepairAttemptCount((LoadRecovery *)v68);
              if ( LoadRecovery::CGetPartCount((LoadRecovery *)v68) < v986 )
              {
                v995 = 1;
                v994 = (LoadRecovery *)v68;
                goto LABEL_1839;
              }
              if ( v986 )
              {
                if ( LoadRecovery::CGetPartCount((LoadRecovery *)v68) == v986 )
                {
                  v996 = LoadRecovery::CGetIRTCount((LoadRecovery *)v68);
                  if ( v996 <= v1341 )
                  {
                    v997 = v986 - 1;
                    v998 = LoadRecovery::FNoProgressOnPart((LoadRecovery *)v68, v997);
                    v994 = (LoadRecovery *)v68;
                    if ( v998 )
                    {
                      v995 = 1;
                      goto LABEL_1839;
                    }
                    if ( !LoadRecovery::FCorruptPart((LoadRecovery *)v68, v997) )
                    {
                      LoadRecovery::SetCorruptPart((LoadRecovery *)v68, v997);
                      LoadRecovery::SetFNoProgressOnPart((LoadRecovery *)v68, v997);
                    }
                  }
                }
              }
            }
            else
            {
              v995 = 0;
LABEL_1839:
              LoadRecovery::HrHandleLoadMode(v994, v995);
            }
            v1341 = LoadRecovery::CGetIRTCount((LoadRecovery *)v68);
            v1308 = LoadRecovery::CGetPartCount((LoadRecovery *)v68);
          }
          ClearStatusString(11);
          if ( (unsigned int)LoadRecovery::Lrmode(v68) == 1 )
          {
            if ( !v1218 )
            {
              v1002 = 1752853862;
              goto LABEL_1846;
            }
          }
          else
          {
            v1002 = 1752853863;
LABEL_1846:
            MsoShipAssertTagProc(v1002);
            v1218 = 1;
          }
          if ( v1159 )
            goto LABEL_744;
          v1003 = LoadRecovery::Lrmode(v68);
          SetLoadRecovery(v1003);
          v1004 = MaxPathHolder::CchMaxPath();
          v1005 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1462);
          v1006 = v1004;
          v69 = v1160;
          CchStToSt(v1005, v1160, v1006);
          v1269 = 0;
          sub_1402DA5D0(&v1541, v1333, v1007);
          goto LABEL_745;
        }
        OsfOpenScope::OpenCompleted((OsfOpenScope *)v1485);
        v1186 = 0;
        (*(void (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v1157 + 8LL))(v1157);
        v951 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
        v952 = XlAsyncFileIO::PxlasyncFileIOFromWorkbook(v951);
        if ( v952 )
          XlAsyncFileIO::NotifyWorkbookInClose(v952, 1);
        v953 = FeatureGateCollectionBase<CoauthFeatureGates>::Instance();
        if ( (unsigned __int8)Mso::AB::Optimized::FeatureGate::operator bool(v953 + 472) )
          BOOK::SetFCloseForReopen(lp, 1);
        v954 = HrFreeBook2(lp);
        v605 = v954;
        if ( (_BYTE)v265 )
        {
          if ( v954 < 0 )
            goto LABEL_1742;
        }
        else if ( v954 < 0 )
        {
          v801 = 512506016;
          v802 = (MsoReserveTag *)&v1359;
          goto LABEL_1920;
        }
        lp = 0;
        if ( v1204 )
          (*(void (__fastcall **)(struct IMsoOLDocument *, __int64, __int64))(*(_QWORD *)v1157 + 56LL))(v1157, 1, 7);
        v955 = v1171 != 0;
        v1171 = -v1171;
        FBeginCmdIOLDoc(v1157, v955 ? 4 : 2, 0, &v1232, 0);
        if ( v1246 )
        {
          (*(void (__fastcall **)(struct IMsoPKMClient *))(*(_QWORD *)v1246 + 184LL))(v1246);
          v1246 = 0;
        }
        sub_1402DA5D0(&v1541, v1333, v956);
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
            if ( *v409 )
            {
              v1054 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1361, 0x23696299u);
              v1055 = SXVWGEOM::RwFirst(v1054);
              OlDocFilePath::FReleaseIOLDoc(v409, 1, 1, v1055);
            }
          }
          Mso::TCntPtr<IOfficeSolutionFramework>::TCntPtr<IOfficeSolutionFramework>(v1310);
          v1056 = MaxPathHolder::SzPath((MaxPathHolder *)v1462);
          v1057 = MsoPIOLDocFindWithWzPersistentName(v1056);
          Mso::TCntPtr<IMsoOLDocument>::Attach(v1310, v1057);
          if ( (unsigned __int8)std::shared_ptr<Mso::ActivityScope::IMsoLoggingScope>::operator bool(v1310) )
          {
            v1059 = BKORWS::Psh((BKORWS *)v1310);
            ZrtUtility::OptOutOfServerOnlyAsyncOpen(v1059, v1060);
          }
          if ( v1155 )
            XslClear((struct XSL *)&v1541);
          LOBYTE(v1058) = std::nullopt;
          if ( !(unsigned __int8)sub_14240D208(v1524, v1058) )
          {
            v1061 = sub_14240D3DC(v1524);
            sub_141837FB8(v1061);
          }
          v115 = -1491861503;
          v1153 = -1491861503;
          XlsDiag::LogSetHrCoreTag(-1491861503, 0x300B394u);
          Mso::TCntPtr<Uxpp::UxppAnnotationsService>::~TCntPtr<Uxpp::UxppAnnotationsService>(v1310);
LABEL_1949:
          if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                         + 8LL)
              & 1) == 0 )
          {
            FRemoveLoadAction((struct LoadRecovery *)v68, 0);
            if ( v68 )
            {
              if ( (*((_BYTE *)PivotOperationBase::PSxview((PivotOperationBase *)v68) + 36) & 0x20) != 0 )
              {
                v115 = -2146827284;
                XlsDiag::LogSetHrCoreTag(-2146827284, 0x23404CEu);
                v1062 = (CorruptionMetaData *)std::_Optional_construct_base<CorruptionMetaData>::operator*(v1538);
                CorruptionMetaData::MarkAsCorrupt(v1062);
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
            v1063 = Api::Workbook::FtFileType((char *)lp + 1640);
            v1064 = 1;
            LOBYTE(v1131) = 0;
            LOBYTE(v1129) = 1;
            v1563[0] = (2 * v1063) | v1563[0] & 0xFFFFFE01;
            if ( v1155 )
              v1064 = 65537;
            LODWORD(v1125) = 1;
            if ( (unsigned int)FSaveRecoveryDrp(lp, 0, 0, v1064, v1125, v1563, 0, v1129, v1131) )
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
          v1065 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          if ( (*(_BYTE *)(*(_QWORD *)(v1065 + 872) + 8LL) & 1) == 0 && v1153 && lp && !v1172 )
          {
            if ( !*(_DWORD *)(*(_QWORD *)(v1065 + 1232) + 80LL) && !(unsigned int)FOsrhBook(lp) )
              v73 = 0;
            v1066 = BOOK::Pioldoc(lp);
            MsoHrSimpleOfflineOpenFile(
              v1066,
              (int (__high *)(enum MSOSCA, struct IMsoOLDocument *, unsigned int))&HrSimpleOfflineUser,
              v73);
          }
          ResetLoadRecovery();
          v1067 = lp;
          if ( lp )
          {
            FShowTrustBar(lp);
            *((_DWORD *)lp + 222) &= ~0x8000000u;
            v1067 = lp;
          }
          v1068 = HrFileCompleteLoadEx(
                    v1160,
                    hObject,
                    v1153,
                    v1182,
                    v1067,
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
                    v115,
                    (const struct MaxPathHolder *)v1340,
                    v1175,
                    v1254,
                    (struct OsfOpenScope *)v1485,
                    (const struct XLOSRR *)&v1235,
                    v1334);
          goto LABEL_1987;
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
        v410 = (__int64 *)NtCurrentTeb()->ThreadLocalStoragePointer;
        v60 = v1298;
        v1153 = 0;
        v1194 = 256;
        v1223 = 0;
        lp = 0;
        v1232 = 0;
        v411 = *v410;
        v1169 = 0;
        v1297 = 0;
        v1268 = 0;
        v412 = *(_QWORD *)(v411 + 304);
        v1275 = 0;
        v1331 = 0;
        v1188 = 0;
        v413 = *(_QWORD *)(v412 + 1304);
        v1163 = 0;
        v1164 = 0;
        *(_WORD *)(v413 + 56) &= ~8u;
        if ( v1251 )
        {
          (*(void (__fastcall **)(struct IMsoDocumentEncryptor *))(*(_QWORD *)v1251 + 16LL))(v1251);
          v1251 = 0;
        }
        goto LABEL_79;
      }
LABEL_1105:
      errDeferred = 0;
      v591 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
      if ( *(_QWORD *)(v591 + 40) && (*(_DWORD *)(*(_QWORD *)(v591 + 40) + 884LL) & 0x200) != 0 )
      {
        RenumberWind(*(struct SH **)(v591 + 32));
        v592 = v1297;
        v593 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        *(_DWORD *)(v593 + 2024) = 0;
        *(_DWORD *)(v593 + 2028) = 0;
        v594 = *(const struct BOOK **)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        *((_QWORD *)v594 + 42) = v1220;
        LOBYTE(v265) = 0;
        goto LABEL_1549;
      }
      if ( v1153 != 2 )
      {
LABEL_1360:
        v721 = v1154;
        v409 = v1161;
        goto LABEL_1361;
      }
      if ( *(_DWORD *)(*(_QWORD *)(v591 + 872) + 104LL) == 2 )
      {
        if ( OSRR::FOsrCandidate((OSRR *)&v1235) )
        {
          OSRR::SetAppReady((OSRR *)&v1235, 1);
LABEL_764:
          v1155 = 1;
          goto LABEL_743;
        }
        v595 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1339);
        v596 = HrLoadDataRecover(v1167, v265, &v1567, 257, v595, a5, 0, v1185, (struct LoadRecovery *)v68);
        v1152 = v596;
        v115 = v596;
        if ( v596 < 0 )
          XlsDiag::LogSetHrCoreTag(v596, 0x2156755u);
        v597 = v1154;
        v1153 = v115 >= 0;
        if ( v1154 )
        {
          if ( (unsigned int)IMsoOLDocument::IsInFileSys(v1157) )
          {
            if ( v1153
              || (v598 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL),
                  *(_QWORD *)(v598 + 40))
              && (*(_DWORD *)(*(_QWORD *)(v598 + 40) + 884LL) & 0x200) != 0 )
            {
              v599 = (wchar_t **)XLSBOOK::Plxtab(*(XLSBOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                         + 304LL)
                                                             + 40LL));
              FreeHpstTempPath((struct STB *)v599);
              v600 = FileSource::StzFilePath((FileSource *)v1305);
              if ( (int)HrStDupSt(v600, v599 + 21) < 0 )
                v599[21] = 0;
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
            v668 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1411, 0x2369629Eu);
            v669 = SXVWGEOM::RwFirst(v668);
            OlDocFilePath::FReleaseIOLDoc(v1161, 1, v1153 == 0, v669);
          }
          v670 = v1299;
          v1178 = v1189;
          v1157 = v1299;
        }
        else
        {
          v670 = v1157;
        }
        if ( v1239 == -2 )
        {
          v68 = v1158;
          goto LABEL_1360;
        }
        v703 = 0;
        v704 = 0;
        v705 = 0;
        v706 = 0;
        if ( v1178 )
        {
          v703 = 0;
          if ( !v1153 )
          {
            v707 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
            if ( !*(_QWORD *)(v707 + 40) || (*(_DWORD *)(*(_QWORD *)(v707 + 40) + 884LL) & 0x200) == 0 )
              v703 = 1;
          }
          HrRecordEvent(v670, 0x40000000u, !v703);
          v704 = v703;
          v1178 = 0;
          v706 = v703;
          v705 = v703;
        }
        v708 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        if ( *(_QWORD *)(v708 + 40) != v1301 )
        {
          v703 = v704;
          v705 = v706;
          if ( v1153 )
          {
            if ( *(_QWORD *)(v708 + 40) )
            {
              if ( v1260 )
              {
                v709 = OLDocFactory::PInstance();
                v1217 = (*(__int64 (__fastcall **)(const struct OLDocFactory *, _QWORD, struct IMsoOLDocument **))(*(_QWORD *)v709 + 56LL))(
                          v709,
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
              v710 = *(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL);
              v711 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1412, 0x2369629Cu);
              v712 = SXVWGEOM::RwFirst(v711);
              BOOK::SetPioldoc(v710, v1157, v712);
              LOBYTE(v713) = 1;
              if ( (unsigned __int8)FeatureExposure::FRunLicensedFeature(v713) )
              {
                v714 = NtCurrentTeb()->ThreadLocalStoragePointer;
                v1304 = -1;
                v715 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v714 + 304LL) + 32LL);
                v716 = 0;
                if ( (*(_BYTE *)(v715 + 10) & 4) == 0 )
                  v716 = *(_BYTE *)(v715 + 8);
                v717 = FtDefault(v716);
                if ( (unsigned __int8)FShouldShowDataLossBusBar(v717, &v1304) )
                  ShowDataLossBusBarIfNeeded(
                    *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL),
                    v1304);
              }
            }
            v68 = v1158;
            goto LABEL_1360;
          }
        }
        v409 = v1161;
        _IMsoOLDocument_SetIReDownload(*v1161, -1);
        v718 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1413, 0x2369629Du);
        v719 = SXVWGEOM::RwFirst(v718);
        if ( v1153 )
        {
          v720 = 0;
          v703 = v705;
        }
        else
        {
          v720 = 1;
        }
        OlDocFilePath::FReleaseIOLDoc(v409, !v703, v720, v719);
        if ( v597 )
          *v409 = 0;
        v68 = v1158;
        v721 = 0;
        v1154 = 0;
LABEL_1361:
        v722 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
        v723 = (LXBASE *)OpenTelemetry::POpenFileStageModel(v722);
        v724 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1414, 0x1F0CB5C2u);
        SXVWGEOM::RwFirst(v724);
        WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v723);
        v725 = FeatureGateCollectionBase<CoauthFeatureGates>::Instance();
        if ( !(unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(v725 + 1680) || v1153 )
          lp = *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL);
        v726 = NtCurrentTeb()->ThreadLocalStoragePointer;
        vhpstErrPath = 0;
        v727 = *(_QWORD *)(*(_QWORD *)v726 + 304LL);
        *(_DWORD *)(v727 + 2024) = 0;
        *(_DWORD *)(v727 + 2028) = 0;
        v1202 = 0;
        v728 = sub_1404303D0(lp);
        v729 = v1151;
        v605 = v728;
        if ( v1151 )
        {
          if ( v728 < 0 )
          {
LABEL_1132:
            v1166 = v605;
            goto LABEL_1133;
          }
        }
        else if ( v728 < 0 )
        {
          v801 = 512506050;
          v802 = (MsoReserveTag *)&v1365;
          goto LABEL_1920;
        }
        if ( v1202 )
        {
          lp = 0;
          v73 = 1;
          goto LABEL_744;
        }
        if ( v721 )
        {
          sub_14046D500(v1157);
          if ( Mso::DocumentWindow::EventMgr::IsDocumentWindowEventManagerEnabled(v730) )
            sub_1404318C0(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL));
        }
        if ( v1153 )
        {
          if ( lp )
          {
            v731 = (WN *)*((_QWORD *)lp + 53);
            if ( v731 )
            {
              v732 = WN::Puiframe(v731);
              v733 = (struct IMsoOLDocument *)UIFRAME::HwndFrame(v732);
              v734 = BOOK::Pioldoc(lp);
              Excel::XlMso::EmitOpenEventForOLDocument(v734, v733, v735);
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
                  v736 = BOOK::Pioldoc(lp);
                  if ( v1157 == v736 && !(unsigned int)FIsLocalVersionXL(v1160) )
                  {
                    v737 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
                    v738 = Api::Workbook::FtFileType((char *)lp + 1640);
                    if ( (unsigned __int8)CoauthUtil::FValidXluidLoadedFt(v738, v737) )
                      XLSWORKBOOK::SetFValidUidStateLoaded((struct BOOK *)((char *)lp + 1640), 1);
                    if ( !XLSWORKBOOK::FValidUidStateLoaded((struct BOOK *)((char *)lp + 1640)) )
                    {
                      v739 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
                      CoauthUtil::CreateValidUidStateOnLoad(v739);
                    }
                    if ( v1168 )
                    {
                      Protocol = XlFileProtocolManager::GetProtocol(v1157);
                      if ( !Protocol )
                      {
                        MsoShipAssertTagProc(506056966);
                        v1041 = 506056965;
                        v605 = -2147418113;
                        goto LABEL_2130;
                      }
                      v741 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1415, 0x1E1968DCu);
                      XlFileProtocol::TakeZipItScheduler(Protocol, v1347, *(unsigned int *)v741);
                      v742 = lp;
                      v743 = *(_DWORD *)MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1416, 0x1E1968DBu);
                      v744 = BKORWS::Psh((BKORWS *)v1347);
                      XLSWORKBOOK::SetZipItScheduler((char *)v742 + 1640, v744, v743);
                      Mso::TCntPtr<IWebAddInOptionalProperties>::~TCntPtr<IWebAddInOptionalProperties>(v1347);
                    }
                    v745 = FeatureGateCollectionBase<CoauthFeatureGates>::Instance();
                    if ( (unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(v745 + 1264) )
                    {
                      LOBYTE(v746) = std::nullopt;
                      if ( !(unsigned __int8)std::operator==<CoauthoringInternals::RecoveredFileCoauthorableState>(
                                               &CoauthoringInternals::s_optRecoveredFileCoauthorableState,
                                               v746) )
                      {
                        v747 = (_DWORD *)std::optional<CoauthoringInternals::RecoveredFileCoauthorableState>::operator->(&CoauthoringInternals::s_optRecoveredFileCoauthorableState);
                        *((_DWORD *)lp + 320) = *v747;
                        v748 = std::optional<CoauthoringInternals::RecoveredFileCoauthorableState>::operator->(&CoauthoringInternals::s_optRecoveredFileCoauthorableState);
                        *((_QWORD *)lp + 161) = *(_QWORD *)(v748 + 8);
                      }
                    }
                    BOOKO::UpdateCoauth((struct BOOK *)((char *)lp + 1640), 1);
                    v749 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
                    v750 = XlAsyncFileIO::PxlasyncFileIOFromWorkbook(v749);
                    if ( v750 )
                    {
                      v751 = XlAsyncFileIO::Pxlrh(v750);
                      XlRenameHandler::HrCheckForRenameOnFileLoad(v751);
                    }
                    v752 = 0;
                    if ( (unsigned __int8)std::shared_ptr<Mso::ActivityScope::IMsoLoggingScope>::operator bool(&v1252) )
                    {
                      v753 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1252);
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v753 + 48LL))(v753);
                      v754 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1252);
                      v752 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v754 + 128LL))(v754, 0);
                    }
                    v755 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
                    v756 = IMerge::PMergeFromWorkbook(v755);
                    if ( v756 )
                    {
                      v757 = (*(__int64 (__fastcall **)(struct IMerge *))(*(_QWORD *)v756 + 216LL))(v756);
                      v758 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v757 + 288LL))(v757);
                      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v758 + 48LL))(v758, v752);
                    }
                    v1328 = 0;
                    v759 = OcsTransitionController::PCoauthTransitionState((struct BOOK *)((char *)lp + 1640));
                    Api::ReloadContext::RetrieveRctxFromWorkbook(v759, &v1328);
                    if ( v1328 && Api::ReloadContext::FValid(v1328) )
                    {
                      v1181 = 1;
                      v760 = Mso::Telemetry::Activity::DataFields(v1213);
                      refreshed = Api::ReloadContext::RefreshType(v1328);
                      v762 = Api::ReloadContext::SzFromBookRefreshType(refreshed);
                      Mso::Telemetry::IDataFieldCollection::Add(v760, "RefreshType", v762, 4);
                    }
                    if ( BKORWS::Psh((struct BOOK *)((char *)lp + 3088)) )
                    {
                      v763 = BKORWS::Psh((struct BOOK *)((char *)lp + 3088));
                      IEndpointAgent::HrLoadComplete(v763);
                    }
                    v764 = XLSWORKBOOK::ClpManager((struct BOOK *)((char *)lp + 1640));
                    ClassifyLabelProtectManager::OnLoadComplete(v764);
                    if ( IdleLoop::FEnabled(v765) )
                    {
                      v766 = FeatureGateCollectionBase<PerformanceFeatureGates>::Instance();
                      if ( (unsigned __int8)Mso::AB::Optimized::FeatureGate::operator bool(v766 + 416) )
                        UpdateCLPLabelIndicator(lp);
                    }
                    v767 = APPCORE::PautoSaveManager((APPCORE *)&vapp);
                    AutoSaveManager::SetAutoSaveStatusOnFileLoad(v767, lp);
                    Copilot::EvaluatePrerequisitesForBook((struct BOOK *)((char *)lp + 1640), v768);
                  }
                }
              }
            }
          }
        }
        if ( v1170 )
          ApplyRevert(v1269, (const struct REVARG *)v1565, v1153);
        v1269 = 0;
        v769 = HrEnsureChartSheetsAreNonBlank(lp, 1);
        v605 = v769;
        if ( v1151 )
        {
          if ( v769 < 0 )
          {
            v1166 = v769;
            goto LABEL_1133;
          }
        }
        else if ( v769 < 0 )
        {
          v801 = 512506049;
          v802 = (MsoReserveTag *)&v1364;
          goto LABEL_1920;
        }
        if ( fShowWn )
        {
          v592 = *(SH **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 32LL);
          v1297 = v592;
          v770 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1417, 0x2375A797u);
          v771 = SXVWGEOM::RwFirst(v770);
          v772 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
          if ( *(_QWORD *)(v772 + 104) )
            v773 = *(struct SH **)(*(_QWORD *)(v772 + 104) + 24LL);
          else
            v773 = 0;
          v774 = *(_QWORD **)(v772 + 128);
          v775 = 0;
          if ( v774 )
          {
            v776 = v774;
            do
            {
              v775 = v776[1];
              if ( v775 )
                break;
              v774 = (_QWORD *)*v774;
              v776 = v774;
            }
            while ( v774 );
          }
          LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v775 + 96), v773, v771);
        }
        else
        {
          v592 = v1297;
        }
        v777 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
        v778 = *(struct WNX **)(v777 + 344);
        if ( v778 )
        {
          v779 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v780 = *(struct WNX **)(v777 + 344);
          v781 = v778;
          v782 = v778;
          do
          {
            v783 = *((_DWORD *)v780 + 2);
            if ( v783 == 2 )
            {
              if ( (*(_WORD *)(CastOrNull<CS,SH>(*((_QWORD *)v781 + 3), v782) + 424) & 0x200) != 0 )
              {
                v784 = *(struct SH **)(*(_QWORD *)(*(_QWORD *)v779 + 304LL) + 32LL);
                v785 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1418, 0x237630D7u);
                v786 = SXVWGEOM::RwFirst(v785);
                v787 = *(_QWORD *)(*(_QWORD *)v779 + 304LL);
                v788 = 0;
                v789 = *(_QWORD **)(v787 + 128);
                if ( v789 )
                {
                  v790 = *(_QWORD **)(v787 + 128);
                  do
                  {
                    v788 = v790[1];
                    if ( v788 )
                      break;
                    v789 = (_QWORD *)*v789;
                    v790 = v789;
                  }
                  while ( v789 );
                }
                LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v788 + 96), *((struct SH **)v781 + 3), v786);
                if ( SbFromHpCore(*(const void **)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v779 + 304LL) + 48LL) + 13280LL)) )
                {
                  v605 = HrRecalcCho(0);
                  if ( v1151 )
                  {
                    if ( v605 < 0 )
                      goto LABEL_1185;
                  }
                  else if ( v605 < 0 )
                  {
                    v801 = 512506048;
                    v802 = (MsoReserveTag *)&v1355;
                    goto LABEL_1920;
                  }
                }
                v792 = *(_QWORD *)(*(_QWORD *)v779 + 304LL);
                if ( *(_QWORD *)(v792 + 40) )
                {
                  v793 = *(_QWORD *)(v792 + 40);
                  v791 = 2048;
                  if ( (*(_WORD *)(v793 + 482) & 0x800) != 0 )
                  {
                    if ( *(_QWORD *)(v793 + 528) )
                      *(_WORD *)(*(_QWORD *)(v793 + 528) + 8LL) |= 0x200u;
                  }
                }
                v794 = (struct CS *)CastOrNull<CS,SH>(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v779 + 304LL) + 32LL), v791);
                CheckDdeCh(v794, 1);
                v795 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1419, 0x237630D6u);
                v796 = SXVWGEOM::RwFirst(v795);
                v797 = *(_QWORD *)(*(_QWORD *)v779 + 304LL);
                v798 = 0;
                v799 = *(_QWORD **)(v797 + 128);
                if ( v799 )
                {
                  v800 = *(_QWORD **)(v797 + 128);
                  do
                  {
                    v798 = v800[1];
                    if ( v798 )
                      break;
                    v799 = (_QWORD *)*v799;
                    v800 = v799;
                  }
                  while ( v799 );
                }
                LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v798 + 96), v784, v796);
                v729 = v1151;
              }
            }
            else if ( !v783 )
            {
              if ( (*((_BYTE *)v782 + 216) & 0x10) != 0 )
              {
                v605 = HrDoDeferredLayoutView(v778);
                if ( v729 )
                {
                  if ( v605 < 0 )
                    goto LABEL_1185;
                }
                else if ( v605 < 0 )
                {
                  v801 = 509215971;
                  v802 = (MsoReserveTag *)&v1356;
LABEL_1920:
                  v1039 = MsoReserveTag::MsoReserveTag(v802, v801);
                  v1040 = SXVWGEOM::RwFirst(v1039);
                  XlsDiag::LogFailRetTag(v605, v1040);
                  goto LABEL_2131;
                }
              }
              else if ( (*((_DWORD *)v778 + 54) & 0x100) != 0 )
              {
                v803 = Measurements::Stopwatch::Stopwatch((Measurements::Stopwatch *)v1536);
                LOBYTE(v804) = 1;
                Measurements::MeasureElapsedTime::MeasureElapsedTime(
                  v1515,
                  Measurements::MeasurementId::ExcelDoDeferredPageLayoutView,
                  v804,
                  v803);
                v1335 = 0;
                v805 = HrXlDoDeferredPageLayoutView(v778, 1, &v1335);
                v605 = v805;
                if ( v729 )
                {
                  if ( v805 < 0 )
                  {
                    v1166 = v805;
                    Measurements::MeasureElapsedTime::~MeasureElapsedTime((Measurements::MeasureElapsedTime *)v1515);
                    goto LABEL_1133;
                  }
                }
                else if ( v805 < 0 )
                {
                  v1042 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1357, 0x1E8C38A3u);
                  v1043 = SXVWGEOM::RwFirst(v1042);
                  XlsDiag::LogFailRetTag(v605, v1043);
                  Measurements::MeasureElapsedTime::~MeasureElapsedTime((Measurements::MeasureElapsedTime *)v1515);
                  goto LABEL_2131;
                }
                Measurements::MeasureElapsedTime::~MeasureElapsedTime((Measurements::MeasureElapsedTime *)v1515);
              }
            }
            v778 = *(struct WNX **)v778;
            v780 = v778;
            v781 = v778;
            v782 = v778;
          }
          while ( v778 );
        }
        if ( !wProjLoad )
        {
          if ( fShowWn )
          {
            v806 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
            if ( !*(_DWORD *)(v806 + 2704) && !*(_DWORD *)(v806 + 1888) )
            {
              v807 = Measurements::Stopwatch::Stopwatch((Measurements::Stopwatch *)v1535);
              LOBYTE(v808) = 1;
              Measurements::MeasureElapsedTime::MeasureElapsedTime(
                v1526,
                Measurements::MeasurementId::ExcelNewFmla,
                v808,
                v807);
              NewFmla(0);
              Measurements::MeasureElapsedTime::~MeasureElapsedTime((Measurements::MeasureElapsedTime *)v1526);
            }
          }
        }
        v809 = lp;
        if ( v1153 )
        {
          if ( lp && !v1172 && !v1155 )
          {
            if ( !v1246 )
            {
              if ( BOOK::Pioldoc(lp) )
              {
                v810 = BOOK::Pioldoc(lp);
                if ( !(unsigned int)IMsoOLDocument::IsInFileSys(v810)
                  || (v811 = BOOK::Pioldoc(lp),
                      ((*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v811 + 224LL))(v811) & 1) != 0) )
                {
                  v812 = BOOK::Pioldoc(lp);
                  v813 = 1;
                  v814 = (*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v812 + 80LL))(v812) & 0x20000;
                  if ( !*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                              + 1232LL)
                                  + 32LL) )
                    v813 = 3;
                  v815 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1420, 0x21C7310u);
                  v816 = SXVWGEOM::RwFirst(v815);
                  v817 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                               + 1232LL)
                                   + 32LL) != 0
                       ? 0x20000
                       : 0;
                  v818 = BOOK::Pioldoc(lp);
                  OldocHelper::SetAttrInAttrMask(v818, v817, 0x20000u, v816);
                  v819 = BOOK::Pioldoc(lp);
                  (*(void (__fastcall **)(struct IMsoOLDocument *, _QWORD, struct IMsoPKMClient **))(*(_QWORD *)v819 + 216LL))(
                    v819,
                    v813,
                    &v1246);
                  v820 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1421, 0x21C7311u);
                  v821 = SXVWGEOM::RwFirst(v820);
                  v822 = BOOK::Pioldoc(lp);
                  OldocHelper::SetAttrInAttrMask(v822, v814, 0x20000u, v821);
                }
              }
              v809 = lp;
            }
            v823 = BOOK::Pioldoc(v809);
            MsoHrMetadataEvent(v823, 32);
            v824 = BOOK::Pioldoc(lp);
            MsoHrTaxonomyOnDocOpen(v824);
            v809 = lp;
          }
          if ( v1153 )
          {
            if ( v809 && !v1172 )
            {
              v825 = BOOK::Pioldoc(v809);
              FileLoad::HrHandleSharepointWorkflows(v825);
              v809 = lp;
            }
            if ( v1153 )
            {
              BuildBookWnxSel();
              v809 = lp;
              if ( v1153 )
              {
                if ( v1246 && lp )
                {
                  *((_QWORD *)lp + 172) = v1246;
                  (*(void (__fastcall **)(struct IMsoPKMClient *))(*(_QWORD *)v1246 + 104LL))(v1246);
                  v809 = lp;
                }
                if ( v1153 && v809 && !*((_QWORD *)v809 + 57) )
                {
                  if ( BOOK::Pioldoc(v809) )
                  {
                    v826 = BOOK::Pioldoc(lp);
                    if ( ((*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v826 + 224LL))(v826) & 1) != 0 )
                    {
                      v827 = BOOK::Pioldoc(lp);
                      if ( ((*(__int64 (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v827 + 80LL))(v827) & 0x40) == 0 )
                      {
                        v828 = MaxPathHolder::SzPath((MaxPathHolder *)v1348);
                        if ( !(unsigned int)FFileInOfflineFilesCache(v828) )
                        {
                          v1293 = 0;
                          v829 = BOOK::Pioldoc(lp);
                          if ( (*(int (__fastcall **)(struct IMsoOLDocument *, struct IStorage **, GUID *))(*(_QWORD *)v829 + 32LL))(
                                 v829,
                                 &v1293,
                                 &IID_IStorage) >= 0 )
                          {
                            v1316 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                              + 2924LL);
                            v1315 = rupBuild;
                            v830 = NtCurrentTeb()->ThreadLocalStoragePointer;
                            v1277 = 0;
                            v1449 = *(struct SH **)(*(_QWORD *)(*(_QWORD *)v830 + 304LL) + 32LL);
                            ENV::ENV((ENV *)&v1560);
                            v831 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                            v1448 = *(_QWORD *)(v831 + 336);
                            *(_QWORD *)(v831 + 336) = &v1560;
                            v1561 = 36737605;
                            v832 = setjmp(v1562);
                            v68 = v1233;
                            v1158 = v1233;
                            if ( v832 )
                            {
                              v115 = v1152;
                            }
                            else
                            {
                              v115 = -2147467259;
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
                                  v833 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                                  if ( !*(_QWORD *)(v833 + 32) || (v834 = SH::Pbook(*(SH **)(v833 + 32)), v834 != lp) )
                                  {
                                    v835 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1422, 0x2375A796u);
                                    v836 = SXVWGEOM::RwFirst(v835);
                                    v837 = XLSBOOK::Plxtab((struct BOOK *)((char *)lp + 1640));
                                    v838 = (TAB *)LXTYPE<UsedRange>::PFromI(v837, 0);
                                    v839 = TAB::PshDesktopOnly(v838);
                                    v840 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                  + 304LL)
                                                      + 128LL);
                                    v841 = 0;
                                    if ( v840 )
                                    {
                                      v842 = v840;
                                      do
                                      {
                                        v841 = v842[1];
                                        if ( v841 )
                                          break;
                                        v840 = (_QWORD *)*v840;
                                        v842 = v840;
                                      }
                                      while ( v840 );
                                    }
                                    LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v841 + 96), v839, v836);
                                  }
                                  v1314 = 0;
                                  if ( (int)HrReadBof(v1261, 0, (struct LoadRecovery *)v68, &v1314) >= 0 )
                                  {
                                    v843 = v1262;
                                    v844 = MaxPathHolder::SzPath((MaxPathHolder *)v1348);
                                    if ( (int)HrUpdateWriteAccess(v1579, 516, v844, v843, &v1277) >= 0 )
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
                                    v845 = BOOK::Pioldoc(lp);
                                    (*(void (__fastcall **)(struct IMsoOLDocument *, _QWORD, __int64))(*(_QWORD *)v845 + 56LL))(
                                      v845,
                                      v1549,
                                      16);
                                    v846 = BOOK::Pioldoc(lp);
                                    (*(void (__fastcall **)(struct IMsoOLDocument *, _QWORD, __int64))(*(_QWORD *)v846 + 56LL))(
                                      v846,
                                      v1550,
                                      17);
                                  }
                                  v847 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                               + 304LL)
                                                   + 40LL)
                                       + 1640LL;
                                  v848 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v847 + 32LL))(v847);
                                  if ( FileLoad::FCheckTimeStampOnThisFile(
                                         *(const struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                           + 304LL)
                                                               + 40LL),
                                         v848,
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
                            v849 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1423, 0x237630D5u);
                            v850 = SXVWGEOM::RwFirst(v849);
                            v851 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                              + 128LL);
                            v852 = 0;
                            if ( v851 )
                            {
                              v853 = v851;
                              do
                              {
                                v852 = v853[1];
                                if ( v852 )
                                  break;
                                v851 = (_QWORD *)*v851;
                                v853 = v851;
                              }
                              while ( v851 );
                            }
                            LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v852 + 96), v1449, v850);
                            rupBuild = v1315;
                            *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                      + 2924LL) = v1316;
                            ((void (__fastcall *)(struct IStorage *))v1293->lpVtbl->Release)(v1293);
                            v592 = v1297;
                            v809 = lp;
                            v1160 = Src;
                            v1171 = v1214;
                            v1161 = v1245;
LABEL_1524:
                            if ( v1153 )
                            {
                              v854 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                              if ( *(_QWORD *)(v854 + 40) )
                              {
                                sub_14046F510(*(_QWORD *)(v854 + 40));
                                v809 = lp;
                              }
                              if ( v1153
                                && v809
                                && !(unsigned int)XlSecurity::FMaaFinal(v809, 5)
                                && !(unsigned int)XlSecurity::FMaaDetected(lp, 5)
                                && !IsWin32AppRunningInWdag() )
                              {
                                EnableMaa(lp, 5);
                                FinalMaa(lp, 5);
                              }
                            }
                            if ( Python::FeatureGates::FEnabledPython(0) && v1153 )
                            {
                              v855 = lp;
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
                              v855 = lp;
                            }
                            if ( CastOrNull<XLSWORKBOOK,BOOK>(v855) )
                            {
                              v856 = (const struct Api::Workbook *)CastOrNull<XLSWORKBOOK,BOOK>(lp);
                              if ( Api::ImportFunctionsManager::FIsFeatureEnabled(v856)
                                && v1153
                                && !(unsigned int)XlSecurity::FMaaFinal(lp, 9)
                                && !(unsigned int)XlSecurity::FMaaDetected(lp, 9)
                                && !IsWin32AppRunningInWdag() )
                              {
                                EnableMaa(lp, 9);
                                FinalMaa(lp, 9);
                              }
                            }
                            LOBYTE(v265) = v1151;
LABEL_1549:
                            v857 = (Excel::AppGuard::Actions **)lp;
                            if ( v1153 )
                            {
                              if ( lp )
                              {
                                if ( !Excel::AppGuard::FTryInitAfterLoad(lp, v594) )
                                {
                                  Error(196663);
                                  v1044 = HrFreeBook2(lp);
                                  v605 = v1044;
                                  if ( (_BYTE)v265 )
                                  {
                                    if ( v1044 < 0 )
                                    {
                                      v1166 = v1044;
                                      goto LABEL_1133;
                                    }
                                  }
                                  else if ( v1044 < 0 )
                                  {
                                    v801 = 512506018;
                                    v802 = (MsoReserveTag *)&v1358;
                                    goto LABEL_1920;
                                  }
                                  lp = 0;
                                  v1153 = 0;
                                  goto LABEL_1930;
                                }
                                v857 = (Excel::AppGuard::Actions **)lp;
                              }
                              if ( v1153 && v857 && (a10 & 0x40000) != 0 )
                              {
                                Excel::AppGuard::Actions::AddTrustPromotionRecord(v857[192], (unsigned __int64)v594);
                                v857 = (Excel::AppGuard::Actions **)lp;
                              }
                            }
                            if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                           + 1440LL)
                              && v857 )
                            {
                              v858 = FBookAddin((const struct BOOK *)v857);
                              v859 = v1160;
                              if ( v858 && (int)AddinManager::HrAddOpenAddin(v1160 + 1, *v1160, &vpoldocument) < 0 )
                              {
                                ((void (*)(void))sub_1411BF070)();
                                ((void (*)(void))sub_141232FB0)();
                                XlsDiag::LogSetHrCoreTag(-2080308954, 0x1E8C38A1u);
                                v605 = -2080308954;
                                goto LABEL_2131;
                              }
                            }
                            else
                            {
                              v859 = v1160;
                            }
                            v860 = 0;
                            if ( v592 )
                            {
                              v861 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                              v862 = *(_QWORD *)(v861 + 32)
                                   ? SH::Pbook(*(SH **)(v861 + 32))
                                   : *(struct BOOK **)(v861 + 40);
                              if ( v862 != SH::Pbook(v592) )
                              {
                                v860 = 1;
                                v863 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                                v1268 = *(struct SH **)(v863 + 32);
                                v1275 = *(struct WNX **)(v863 + 104);
                                v1331 = (struct WNX *)UIGLOBALS::UIGLOBALSCONTAINER::m_selection;
                                v864 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1424, 0x237630D4u);
                                v865 = SXVWGEOM::RwFirst(v864);
                                v866 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                              + 304LL)
                                                  + 128LL);
                                v867 = 0;
                                if ( v866 )
                                {
                                  v868 = v866;
                                  do
                                  {
                                    v867 = v868[1];
                                    if ( v867 )
                                      break;
                                    v866 = (_QWORD *)*v866;
                                    v868 = v866;
                                  }
                                  while ( v866 );
                                }
                                LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v867 + 96), v592, v865);
                              }
                            }
                            if ( v1153 )
                            {
                              v869 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                              if ( *(_QWORD *)(v869 + 40) )
                              {
                                if ( (*(_BYTE *)(*(_QWORD *)(v869 + 1304) + 56LL) & 8) != 0
                                  && (unsigned int)FAnyListsInBook(*(const struct BOOK **)(v869 + 40)) )
                                {
                                  v561 = (unsigned int)CustomTwoAlert(327820, 0, -282329067, -282329066) == 102;
                                  v870 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                                  if ( v561 )
                                    RemoveBookLists(*(const struct BOOK **)(v870 + 40));
                                  else
                                    *(_WORD *)(*(_QWORD *)(v870 + 1304) + 56LL) &= ~8u;
                                }
                              }
                            }
                            if ( !v1153 )
                              goto LABEL_1630;
                            v871 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                            if ( *(_QWORD *)(v871 + 40) )
                            {
                              if ( (*(_BYTE *)(*(_QWORD *)(v871 + 1304) + 56LL) & 8) != 0 )
                              {
                                if ( !XLSBOOK::Plxtab(*(XLSBOOK **)(v871 + 40))
                                  || (v872 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                   + 304LL)
                                                       + 40LL)
                                           + 1640LL,
                                      !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v872 + 32LL))(v872)) )
                                {
                                  v873 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                                  v874 = *(_QWORD *)(v873 + 40);
                                  if ( *(_DWORD *)(v873 + 1836) )
                                  {
                                    *(_DWORD *)(v874 + 884) |= 0x400000u;
                                    goto LABEL_1587;
                                  }
                                  if ( (*(_DWORD *)(v874 + 884) & 0x100) != 0 )
                                  {
                                    *(_DWORD *)(v874 + 884) |= 0x400000u;
                                    v885 = NtCurrentTeb()->ThreadLocalStoragePointer;
                                    *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v885 + 304LL) + 1304LL) + 16LL) = *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v885 + 304LL) + 1232LL) + 110LL);
                                    v73 = 1;
                                    *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                     + 304LL)
                                                         + 1232LL)
                                             + 110LL) = 0;
                                    fnSave(0, 0, 1);
                                    v886 = NtCurrentTeb()->ThreadLocalStoragePointer;
                                    *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v886 + 304LL) + 1232LL) + 110LL) = *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v886 + 304LL) + 1304LL) + 16LL);
                                    goto LABEL_1588;
                                  }
                                }
                              }
                            }
                            if ( !v1153 )
                              goto LABEL_1630;
                            v887 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                            if ( (*(_BYTE *)(*(_QWORD *)(v887 + 1304) + 56LL) & 8) != 0 )
                            {
                              if ( *(_QWORD *)(v887 + 40) )
                              {
                                if ( XLSBOOK::Plxtab(*(XLSBOOK **)(v887 + 40)) )
                                {
                                  v888 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                               + 304LL)
                                                   + 40LL)
                                       + 1640LL;
                                  if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v888 + 32LL))(v888) )
                                  {
                                    v889 = FileSource::HrGetFileTemp(v1305, 12);
                                    v115 = v889;
                                    if ( v889 < 0 )
                                      XlsDiag::LogSetHrCoreTag(v889, 0x280659Au);
                                    if ( v115 < 0 )
                                    {
                                      v115 = -2147467260;
LABEL_1587:
                                      v73 = 1;
                                      goto LABEL_1588;
                                    }
                                    if ( (int)HrStartSharingWbk(
                                                *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                            + 304LL)
                                                                + 40LL),
                                                v1153,
                                                v859,
                                                v1224,
                                                (struct LoadRecovery *)v68,
                                                &v1317,
                                                &v1263) >= 0 )
                                    {
                                      if ( v1154 )
                                      {
                                        v892 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                                        if ( *(_QWORD *)(v892 + 40) )
                                          v893 = BOOK::Pioldoc(*(BOOK **)(v892 + 40));
                                        else
                                          v893 = 0;
                                        *v1161 = v893;
                                        v1157 = v893;
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
                                        v890 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                                        if ( *(_QWORD *)(v890 + 40) )
                                          v891 = BOOK::Pioldoc(*(BOOK **)(v890 + 40));
                                        else
                                          v891 = 0;
                                        *v1161 = v891;
                                        v1157 = v891;
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
                              v894 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1425, 0x1E111215u);
                              v895 = SXVWGEOM::RwFirst(v894);
                              v73 = 1;
                              BookDirty(
                                *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                            + 304LL)
                                                + 40LL),
                                1,
                                v895);
                              XlsDiag::SendTraceTag(504410769, 187, 50);
                            }
                            else
                            {
LABEL_1630:
                              v73 = 1;
                            }
                            if ( v1153 )
                            {
                              v896 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
                              if ( *(_QWORD *)(v896 + 40) )
                              {
                                if ( (unsigned int)FSharedBook(*(const struct BOOK **)(v896 + 40)) )
                                {
                                  v897 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                               + 304LL)
                                                   + 40LL);
                                  if ( (*(_BYTE *)(v897 + 892) & 0x20) != 0 )
                                  {
                                    *(_DWORD *)(v897 + 892) &= ~0x20u;
                                    v898 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1426, 0x231C69Cu);
                                    v899 = SXVWGEOM::RwFirst(v898);
                                    BookDirty(
                                      *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                  + 304LL)
                                                      + 40LL),
                                      1,
                                      v899);
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
                                  v900 = LOCATIONCONTEXTDATA::PWorkbookCur((LOCATIONCONTEXTDATA *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                                                                                 + 8LL));
                                  v901 = TLSW::PesExpressionService(*(TLSW **)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                             + 304LL));
                                  ConvertAllDynamicArraystoLegacyArrays(v901, v900);
                                }
                                if ( v1153 )
                                {
                                  v902 = NtCurrentTeb()->ThreadLocalStoragePointer;
                                  if ( *(_QWORD *)(*(_QWORD *)(*v902 + 304LL) + 40LL)
                                    && (unsigned int)sub_14046FA80(*v902) )
                                  {
                                    SetAutoRefreshPending(1, 0);
                                  }
                                  if ( v1153 )
                                  {
                                    v903 = NtCurrentTeb()->ThreadLocalStoragePointer;
                                    if ( *(_QWORD *)(*(_QWORD *)(*v903 + 304LL) + 40LL) )
                                    {
                                      v904 = FeatureGateCollectionBase<LoadSaveFeatureGates>::Instance(*v903);
                                      v561 = (unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(v904 + 424) == 0;
                                      v905 = NtCurrentTeb()->ThreadLocalStoragePointer;
                                      if ( v561 )
                                      {
                                        v1278 = 0;
                                        v1279 = 0;
                                        v908 = XLSBOOK::Plxtab((XLSBOOK *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v905
                                                                                                 + 304LL)
                                                                                     + 40LL)
                                                                         + 1640LL));
                                        XlPng::DyHeight(v908, v1295);
                                        LXContainerContiguousIterators<LXTYPE<TAB>,TAB,LXBASE>::end(v908, v1329);
                                        if ( (unsigned __int8)LXContiguousConstIterator<LXTYPE<TAB>>::operator!=(
                                                                v1295,
                                                                v1329) )
                                        {
                                          do
                                          {
                                            v909 = BKORWS::Psh((BKORWS *)v1295);
                                            v910 = TAB::PshDesktopOnly(v909);
                                            if ( (*((_BYTE *)v910 + 10) & 4) != 0 )
                                              v911 = 0;
                                            else
                                              v911 = *((_BYTE *)v910 + 8);
                                            if ( v911 <= 1u )
                                            {
                                              v912 = TAB::PshDesktopOnly(v909);
                                              GetOartDataForTelemetry(v912, &v1278, &v1279);
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
                                        v913 = Mso::Telemetry::Activity::DataFields(v1213);
                                        Mso::Telemetry::IDataFieldCollection::Add<int>(
                                          v913,
                                          "cMsoShapes",
                                          (unsigned int)v1278,
                                          4);
                                        v914 = Mso::Telemetry::Activity::DataFields(v1213);
                                        Mso::Telemetry::IDataFieldCollection::Add<int>(
                                          v914,
                                          "numShapes",
                                          (unsigned int)v1279,
                                          4);
                                      }
                                      else
                                      {
                                        v906 = v1213;
                                        v907 = LOCATIONCONTEXTDATA::PWorkbookCur((LOCATIONCONTEXTDATA *)(*(_QWORD *)(*(_QWORD *)v905 + 304LL) + 8LL));
                                        ArtUtil::LogOartDataForOpenedWorkbook(v907, v906);
                                      }
                                    }
                                  }
                                }
                              }
                            }
                            if ( v1226 )
                            {
                              v278 = v1160;
                              CeToggleFileAttr(v1160, v1224, 3, 6u);
                            }
                            else
                            {
LABEL_1588:
                              v278 = v1160;
                            }
                            if ( v860 )
                            {
                              v875 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1427, 0x237630D3u);
                              v876 = SXVWGEOM::RwFirst(v875);
                              v877 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                            + 304LL)
                                                + 128LL);
                              v878 = 0;
                              if ( v877 )
                              {
                                v879 = v877;
                                do
                                {
                                  v878 = v879[1];
                                  if ( v878 )
                                    break;
                                  v877 = (_QWORD *)*v877;
                                  v879 = v877;
                                }
                                while ( v877 );
                              }
                              LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v878 + 96), v1268, v876);
                              v880 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1428, 0x237630D2u);
                              v881 = SXVWGEOM::RwFirst(v880);
                              v882 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                            + 304LL)
                                                + 128LL);
                              v883 = 0;
                              if ( v882 )
                              {
                                v884 = v882;
                                do
                                {
                                  v883 = v884[3];
                                  if ( v883 )
                                    break;
                                  v882 = (_QWORD *)*v882;
                                  v884 = v882;
                                }
                                while ( v882 );
                              }
                              VIEWCONTEXTDATA::CurWnx(*(VIEWCONTEXTDATA **)(v883 + 16), v1275, v881);
                              SetWnxSel(v1331);
                            }
                            else if ( v1303 != (struct SH *)65534 )
                            {
                              v915 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1429, 0x237630D1u);
                              v916 = SXVWGEOM::RwFirst(v915);
                              v917 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                            + 304LL)
                                                + 128LL);
                              v918 = 0;
                              if ( v917 )
                              {
                                v919 = v917;
                                do
                                {
                                  v918 = v919[1];
                                  if ( v918 )
                                    break;
                                  v917 = (_QWORD *)*v917;
                                  v919 = v917;
                                }
                                while ( v917 );
                              }
                              LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v918 + 96), v1303, v916);
                            }
                            goto LABEL_1664;
                          }
                        }
                      }
                    }
                  }
                  v809 = lp;
                }
              }
            }
          }
        }
        v68 = v1158;
        goto LABEL_1524;
      }
      v601 = FileSource::StzFileName((FileSource *)v1305);
      if ( !FForeignFileExtension(v601) && (v1172 || !(unsigned int)FFinderFile(&v1567)) )
      {
        v602 = FileSource::StzFilePath((FileSource *)v1305);
        CchStToStz(v602, v1543, 2086);
        if ( !v1542 )
        {
          MaxPathStzPoke::MaxPathStzPoke((MaxPathStzPoke *)v1503, (struct MaxPathHolder *)v1340);
          v1545 = SlicerViewImpl::PSlicerView((SlicerViewImpl *)v1503);
          MaxPathStzPoke::~MaxPathStzPoke((MaxPathStzPoke *)v1503);
        }
        if ( v1172 && !(unsigned int)FOsrc() )
        {
          v603 = v1217;
LABEL_1130:
          v604 = HrEndDiskIO2(0);
          v605 = v604;
          if ( v1151 )
          {
            if ( v604 < 0 )
              goto LABEL_1132;
          }
          else if ( v604 < 0 )
          {
            v801 = 512506060;
            v802 = (MsoReserveTag *)&v1354;
            goto LABEL_1920;
          }
          StreamClose(v1167);
          if ( (unsigned int)(v603 + 2146697471) <= 1 )
          {
            if ( v68 )
              LoadRecovery::SetRepairState((LoadRecovery *)v68, v603);
            else
              *(&vscd + 1) = 1;
          }
          v115 = -2146827284;
          v1153 = 0;
          v1152 = -2146827284;
          XlsDiag::LogSetHrCoreTag(-2146827284, 0x1797719u);
          v682 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
          v683 = OpenTelemetry::POpenFileStageModel(v682);
          v684 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1409, 0x1F0CB5C5u);
          v685 = SXVWGEOM::RwFirst(v684);
          WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v683, 2214658822LL, v685);
          v597 = v1154;
          goto LABEL_1272;
        }
        v614 = HrDetectWebType(v1157, (enum MSOFF *)&v1216, &v1292, 0, 0);
        v1217 = v614;
        v603 = v614;
        if ( v614 < 0 )
          goto LABEL_1130;
        if ( v614 == 1 )
        {
          if ( (unsigned int)FCmpTextEq(&v1566[v1567 + 13], L".xml", 4, 4)
            || (unsigned int)FCmpTextEq(&v1566[v1567 + 13], L".xsd", 4, 4) )
          {
            v1201 = 1;
            v615 = 3;
          }
          else
          {
            v615 = 0;
          }
          v1216 = v615;
        }
        if ( (unsigned int)FOsrc() && (unsigned int)(v1216 - 1) > 2 )
          goto LABEL_1130;
        v616 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
        v617 = (LXBASE *)OpenTelemetry::POpenFileStageModel(v616);
        v618 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1407, 0x1F0CB5C4u);
        SXVWGEOM::RwFirst(v618);
        WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v617);
        v619 = a11;
        if ( v1216 == 1 || v1216 == 2 )
        {
          v620 = v1158;
          goto LABEL_1288;
        }
        if ( v1216 == 3 )
        {
          v620 = v1158;
          v621 = HrDetectXMLTypeAndPreprocess(a11, (struct XSL *)&v1541, (struct LoadRecovery *)v1158, 0, 1, 1, v1201);
          v1217 = v621;
          v603 = v621;
          if ( v621 != -2147467263 )
          {
            if ( v621 == -2147418113 )
              goto LABEL_1189;
            if ( v621 == -2147352567 )
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
                v628 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1408, 0x2369629Fu);
                v629 = SXVWGEOM::RwFirst(v628);
                OlDocFilePath::FReleaseIOLDoc(v503, 1, 1, v629);
              }
              v409 = 0;
              v1161 = 0;
              v1245 = 0;
              CchStToSt(v1544, v1160, v1224);
              v1214 = 1;
              v605 = HrEndDiskIO2(0);
              if ( v1151 )
              {
                if ( v605 < 0 )
                  goto LABEL_1185;
              }
              else if ( v605 < 0 )
              {
                v801 = 512506059;
                v802 = (MsoReserveTag *)&v1457;
                goto LABEL_1920;
              }
              StreamClose(v1167);
              v68 = v1158;
              a11 = 65001;
              goto LABEL_744;
            }
            if ( v621 )
            {
              if ( v621 != 1 )
              {
                if ( v621 == -2146827284 )
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
              FSwitchLoadActionType(2, 0, (struct LoadRecovery *)v620);
              v672 = -(v1216 != 2);
              v673 = BKORWS::Psh((BKORWS *)v1340);
              v674 = 0;
              if ( (unsigned __int8)SafeToLoad::FSafeToLoadOnFileExtensionPfilesource(
                                      v673,
                                      v1305,
                                      (unsigned int)(v672 + 44),
                                      &v1235) )
              {
                MaxPathStzPoke::MaxPathStzPoke((MaxPathStzPoke *)v1505, (struct MaxPathHolder *)v1340);
                v675 = v1292;
                v676 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 1836LL);
                LOBYTE(v674) = v1216 == 2;
                v677 = (wchar_t *)SlicerViewImpl::PSlicerView((SlicerViewImpl *)v1505);
                BookHtml = HrLoadBookHtml(v1167, 0, v1570, v677, a5, 0, v675, v619, v674, v676, (struct OSRR *)&v1235);
                v1152 = BookHtml;
                v115 = BookHtml;
                if ( BookHtml < 0 )
                  XlsDiag::LogSetHrCoreTag(BookHtml, 0x2156756u);
                MaxPathStzPoke::~MaxPathStzPoke((MaxPathStzPoke *)v1505);
                v1153 = v115 >= 0;
                if ( v115 >= 0 || !OSRR::FReadyForOsr((OSRR *)&v1235) )
                {
                  v597 = v1154;
                  if ( v1154 )
                  {
                    if ( (unsigned int)IMsoOLDocument::IsInFileSys(v1157) )
                    {
                      if ( v1153
                        || (v679 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL),
                            *(_QWORD *)(v679 + 40))
                        && (*(_DWORD *)(*(_QWORD *)(v679 + 40) + 884LL) & 0x200) != 0 )
                      {
                        v680 = (wchar_t **)XLSBOOK::Plxtab(*(XLSBOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                   + 304LL)
                                                                       + 40LL));
                        FreeHpstTempPath((struct STB *)v680);
                        v681 = FileSource::StzFilePath((FileSource *)v1305);
                        if ( (int)HrStDupSt(v681, v680 + 21) < 0 )
                          v680[21] = 0;
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
            v622 = BKORWS::Psh((BKORWS *)v1340);
            if ( !(unsigned __int8)SafeToLoad::FSafeToLoadOnFileExtensionPfilesource(v622, v1305, 45, &v1235) )
              goto LABEL_1284;
            MaxPathStzPoke::MaxPathStzPoke((MaxPathStzPoke *)v1504, (struct MaxPathHolder *)v1340);
            v623 = (wchar_t *)SlicerViewImpl::PSlicerView((SlicerViewImpl *)v1504);
            BookXmlSpreadsheet = HrLoadBookXmlSpreadsheet(v1167, v1570, v623, a5, 0, v619, (struct OSRR *)&v1235);
            v1152 = BookXmlSpreadsheet;
            v115 = BookXmlSpreadsheet;
            if ( BookXmlSpreadsheet < 0 )
              XlsDiag::LogSetHrCoreTag(BookXmlSpreadsheet, 0x2156757u);
            MaxPathStzPoke::~MaxPathStzPoke((MaxPathStzPoke *)v1504);
            v1153 = v115 >= 0;
            if ( v115 < 0 && OSRR::FReadyForOsr((OSRR *)&v1235) )
            {
              v73 = 1;
              goto LABEL_1168;
            }
            v597 = v1154;
            if ( v1154 )
            {
              if ( (unsigned int)IMsoOLDocument::IsInFileSys(v1157) )
              {
                if ( v1153
                  || (v625 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL),
                      *(_QWORD *)(v625 + 40))
                  && (*(_DWORD *)(*(_QWORD *)(v625 + 40) + 884LL) & 0x200) != 0 )
                {
                  v626 = (wchar_t **)XLSBOOK::Plxtab(*(XLSBOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                             + 304LL)
                                                                 + 40LL));
                  FreeHpstTempPath((struct STB *)v626);
                  v627 = FileSource::StzFilePath((FileSource *)v1305);
                  if ( (int)HrStDupSt(v627, v626 + 21) < 0 )
                    v626[21] = 0;
                }
              }
            }
LABEL_1270:
            v666 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
            if ( *(_QWORD *)(v666 + 24) )
            {
              v667 = OcsTransitionController::PCoauthTransitionState(*(OcsTransitionController **)(v666 + 24));
              XLSBOOK::HrEnsureAllSheetXluids(v667);
            }
            goto LABEL_1272;
          }
          v630 = BKORWS::Psh((BKORWS *)v1340);
          if ( !(unsigned __int8)SafeToLoad::FSafeToLoadOnFileExtensionPfilesource(v630, v1305, 48, &v1235) )
            goto LABEL_1284;
          v631 = BKORWS::Psh((BKORWS *)v1339);
          if ( (unsigned int)FBlockOfficeFile(33, v631, 0) )
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
              v649 = APPCORE::PmemheapMain((APPCORE *)&vapp);
              MaxPathHolder::MaxPathHolder((MaxPathHolder *)v1510, v649, 259, 0);
              if ( v1542 )
                v650 = (const wchar_t *)((char *)v1167 + 48);
              else
                v650 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1340);
              MaxPathHolder::CchCopyFromSt((MaxPathHolder *)v1510, v650);
              v651 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1340);
              v652 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1510);
              Xml = HrLoadXml(v1167, v1570, 257, v652, v651, 0, a5, 1, 1);
              v1152 = Xml;
              v115 = Xml;
              if ( Xml < 0 )
                XlsDiag::LogSetHrCoreTag(Xml, 0x2156758u);
              MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1510);
              v1153 = v115 >= 0;
              if ( v115 < 0 )
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
                    v561 = g_fPromptTextFile == 0;
                    g_fPromptTextFile = 0;
                    v633 = !v561;
                    v1290 = 0;
                    v634 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1350);
                    v635 = (wchar_t *)BKORWS::Psh((BKORWS *)v1350);
                    v605 = HrLoadBiff(
                             &v1167,
                             &v1567,
                             v635,
                             v634,
                             1,
                             a5,
                             a7,
                             v1215,
                             0,
                             &v1194,
                             &v1223,
                             (struct LoadRecovery *)v620,
                             &lp,
                             0,
                             0,
                             0,
                             v1273,
                             &v1290);
                    if ( v1151 )
                    {
                      if ( v605 < 0 )
                        goto LABEL_1185;
                    }
                    else if ( v605 < 0 )
                    {
                      v801 = 512506057;
                      v802 = (MsoReserveTag *)&v1458;
                      goto LABEL_1920;
                    }
                    if ( v1290 )
                    {
                      v636 = BKORWS::Psh((BKORWS *)&v1179);
                      v637 = v1157;
                      v638 = v1167;
                      v639 = v636;
                      v640 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1350);
                      v641 = (wchar_t *)BKORWS::Psh((BKORWS *)v1340);
                      v1239 = FLoadForeign(v1570, v641, v640, v638, a5, 2, &v1260, v637, 0, v1273, v639);
                    }
                    g_fPromptTextFile = v633;
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
              v642 = NtCurrentTeb()->ThreadLocalStoragePointer;
              v643 = vpoldocument;
              v1520[7] = 0;
              v1520[3] = 0;
              v644 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v642 + 304LL) + 32LL);
              v645 = NtCurrentTeb()->ThreadLocalStoragePointer;
              v1520[0] = v644;
              v1520[1] = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v645 + 304LL) + 104LL);
              v1520[2] = UIGLOBALS::UIGLOBALSCONTAINER::m_selection;
              (*(void (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)vpoldocument + 8LL))(vpoldocument);
              Project2 = HrCreateProject2(0, 0, 5, 7u, 0, 1);
              v605 = Project2;
              if ( v1151 )
              {
                if ( Project2 < 0 )
                  goto LABEL_1215;
              }
              else if ( Project2 < 0 )
              {
                v801 = 512506053;
                v802 = (MsoReserveTag *)&v1461;
                goto LABEL_1920;
              }
              SuspendRecording();
              if ( (unsigned int)HrDesignXMLCore(v643, &v1327) )
              {
                ResumeRecording();
                if ( v1266 )
                  FreePxlxmlmap(v1266);
                HtmlFailed = HrBookLoadHtmlFailed((struct BLG *)v1520);
                v605 = HtmlFailed;
                if ( v1151 )
                {
                  if ( HtmlFailed < 0 )
                    goto LABEL_1215;
                }
                else if ( HtmlFailed < 0 )
                {
                  v801 = 512506051;
                  v802 = (MsoReserveTag *)&v1397;
                  goto LABEL_1920;
                }
                (*(void (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v643 + 16LL))(v643);
                goto LABEL_1284;
              }
              ResumeRecording();
              RenumberWind(*(struct SH **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL)
                                         + 32LL));
              v647 = HrEndDiskIO2(0);
              v605 = v647;
              if ( v1151 )
              {
                if ( v647 < 0 )
                  goto LABEL_1132;
              }
              else if ( v647 < 0 )
              {
                v801 = 512506052;
                v802 = (MsoReserveTag *)&v1459;
                goto LABEL_1920;
              }
              StreamClose(v1167);
              v1153 = 1;
              (*(void (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v643 + 16LL))(v643);
              if ( !FVbaEventEnabled() )
                goto LABEL_1264;
LABEL_1223:
              HrVbaEventDoBookOpen(
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL),
                2);
            }
LABEL_1264:
            CodeMarker(1125);
            v664 = v1175;
            if ( v1153 )
              v664 = 1;
            v1175 = v664;
            if ( ((v1230 - 1) & 0xFFFFFFFD) != 0 )
            {
              v597 = v1154;
            }
            else
            {
              v1345 = 0;
              v665 = FHpshtiFromStt(&v1345, 61);
              v597 = v1154;
              if ( v665 )
                *((_DWORD *)v1345 + 6) = v1230;
            }
            goto LABEL_1270;
          }
          v654 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v655 = 0;
          v1337 = 0;
          v1312 = 0;
          v1306 = 0;
          v1521[7] = 0;
          v1521[3] = 0;
          v656 = vpoldocument;
          v1291 = 1;
          v657 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v654 + 304LL) + 32LL);
          v658 = NtCurrentTeb()->ThreadLocalStoragePointer;
          v1521[0] = v657;
          v1521[1] = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v658 + 304LL) + 104LL);
          v1521[2] = UIGLOBALS::UIGLOBALSCONTAINER::m_selection;
          (*(void (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)vpoldocument + 8LL))(vpoldocument);
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 2132LL) = 1;
          v605 = HrCreateProject2(0, 0, 5, 7u, 0, 1);
          if ( v1151 )
          {
            if ( v605 < 0 )
            {
LABEL_1185:
              v1166 = v605;
              goto LABEL_1133;
            }
          }
          else if ( v605 < 0 )
          {
            v801 = 512506056;
            v802 = (MsoReserveTag *)&v1353;
            goto LABEL_1920;
          }
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 2132LL) = 0;
          SetRef((struct REF *)v1486, 0, 0, 0, 0);
          SuspendRecording();
          if ( (unsigned int)FEnsureVpxierrinfo()
            && !(unsigned int)HrXlXmlMapFromOlDocument(v656, &v1266, &v1337, &v1291, &v1312, &v1306, 1) )
          {
            v659 = LOCATIONCONTEXTDATA::PWorkbookCur((LOCATIONCONTEXTDATA *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                                       + 304LL)
                                                                           + 8LL));
            v660 = XLSWORKBOOK::Pcm(v659);
            v661 = OcsTransitionController::PCoauthTransitionState(v660);
            CollabManager::FDisableRevisionGeneration(v661, 196, 0);
            v662 = *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer;
            if ( v1291 )
            {
              LOBYTE(v655) = (unsigned int)HrAutoDesignXML(
                                             0,
                                             v1312,
                                             v1306,
                                             *(struct SH **)(*(_QWORD *)(v662 + 304) + 32LL),
                                             (const struct REF *)v1486,
                                             v1266,
                                             0) == 0;
            }
            else if ( !(unsigned int)HrAutoDesignXML(
                                       v656,
                                       0,
                                       0,
                                       *(struct SH **)(*(_QWORD *)(v662 + 304) + 32LL),
                                       (const struct REF *)v1486,
                                       v1266,
                                       0) )
            {
              v655 = 1;
            }
          }
          (*(void (__fastcall **)(struct IMsoOLDocument *))(*(_QWORD *)v656 + 16LL))(v656);
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
          if ( !v655 )
          {
            v671 = HrBookLoadHtmlFailed((struct BLG *)v1521);
            v605 = v671;
            if ( v1151 )
            {
              if ( v671 < 0 )
              {
LABEL_1215:
                v1166 = v605;
                goto LABEL_1133;
              }
            }
            else if ( v671 < 0 )
            {
              v801 = 512506054;
              v802 = (MsoReserveTag *)&v1352;
              goto LABEL_1920;
            }
            goto LABEL_1284;
          }
          if ( *((_DWORD *)vpxsl + 1) )
          {
            FreeHpst(*((wchar_t **)v1266 + 14));
            *((_QWORD *)v1266 + 14) = 0;
            *((_DWORD *)v1266 + 24) = 0;
          }
          v663 = HrEndDiskIO2(0);
          v605 = v663;
          if ( v1151 )
          {
            if ( v663 < 0 )
              goto LABEL_1215;
          }
          else if ( v663 < 0 )
          {
            v801 = 512506055;
            v802 = (MsoReserveTag *)&v1463;
            goto LABEL_1920;
          }
          StreamClose(v1167);
          v1153 = 1;
          if ( !FVbaEventEnabled() )
            goto LABEL_1264;
          goto LABEL_1223;
        }
      }
LABEL_1077:
      v278 = v1160;
LABEL_1078:
      if ( !FEnableForeignFileProtectedView() )
      {
        OSRR::SetAppAllowed((OSRR *)&v1235, 0);
        if ( (unsigned int)XLOSRR::FMustUseOsr((XLOSRR *)&v1235) )
        {
          if ( SbFromHpCore(v1167) )
            StreamClose(v1167);
          v577 = (__int64 *)NtCurrentTeb()->ThreadLocalStoragePointer;
          v1167 = 0;
          v1153 = 0;
          v578 = *v577;
          vhpstm = 0;
          errDeferred = 0;
          v579 = *(_QWORD *)(v578 + 304);
          *(_DWORD *)(v579 + 2024) = 0;
          *(_DWORD *)(v579 + 2028) = 0;
          v115 = -2147024809;
          XlsDiag::LogSetHrCoreTag(-2147024809, 0x179771Au);
          v68 = v1158;
          v73 = 1;
LABEL_1083:
          LOBYTE(v265) = v1151;
          goto LABEL_1664;
        }
      }
      v68 = v1158;
      if ( v1158 && (int)LoadRecovery::Lrmode(v1158) > 0 )
      {
        v73 = 1;
        v686 = 1;
      }
      else
      {
        v686 = 0;
        v73 = 1;
      }
      if ( v686 )
      {
        v687 = PivotOperationBase::PSxview((PivotOperationBase *)v68);
        *((_WORD *)v687 + 18) |= 8u;
      }
      FSwitchLoadActionType(2, 0, (struct LoadRecovery *)v68);
      MaxPathStzPoke::MaxPathStzPoke((MaxPathStzPoke *)v1490, (struct MaxPathHolder *)v1340);
      v688 = APPCORE::PmemheapMain((APPCORE *)&vapp);
      MaxPathHolder::MaxPathHolder((MaxPathHolder *)v1511, v688, 259, 0);
      v689 = FileSource::HrGetFileTemp(v1305, 11);
      v1152 = v689;
      v115 = v689;
      if ( v689 < 0 )
        XlsDiag::LogSetHrCoreTag(v689, 0x27413C1u);
      if ( v115 < 0 )
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
      v690 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
      v691 = (LXBASE *)OpenTelemetry::POpenFileStageModel(v690);
      v692 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1410, 0x1F0CB5C3u);
      SXVWGEOM::RwFirst(v692);
      WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v691);
      v693 = BKORWS::Psh((BKORWS *)&v1179);
      v694 = v1157;
      v695 = v1167;
      v696 = v693;
      v697 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1511);
      v698 = (wchar_t *)SlicerViewImpl::PSlicerView((SlicerViewImpl *)v1490);
      v1239 = FLoadForeign(v1570, v698, v697, v695, a5, a8, &v1260, v694, (struct XLOSRR *)&v1235, v1273, v696);
      v699 = v1239;
      MaxPathHolder::~MaxPathHolder((MaxPathHolder *)v1511);
      MaxPathStzPoke::~MaxPathStzPoke((MaxPathStzPoke *)v1490);
      if ( v699 == -2 )
      {
        v1153 = 0;
        goto LABEL_1323;
      }
      v1153 = v1239;
      if ( !v699 )
      {
LABEL_1323:
        if ( OSRR::FReadyForOsr((OSRR *)&v1235) )
        {
          v68 = v1158;
          v409 = v1161;
          v1155 = 1;
          goto LABEL_744;
        }
        v1152 = -2146827284;
        v115 = -2146827284;
        XlsDiag::LogSetHrCoreTag(-2146827284, 0x230E205u);
      }
      v597 = v1154;
      if ( v1154 )
      {
        if ( (unsigned int)IMsoOLDocument::IsInFileSys(v1157) )
        {
          if ( v1153
            || (v700 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL), *(_QWORD *)(v700 + 40))
            && (*(_DWORD *)(*(_QWORD *)(v700 + 40) + 884LL) & 0x200) != 0 )
          {
            v701 = (wchar_t **)XLSBOOK::Plxtab(*(XLSBOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                       + 304LL)
                                                           + 40LL));
            FreeHpstTempPath((struct STB *)v701);
            v702 = FileSource::StzFilePath((FileSource *)v1305);
            if ( (int)HrStDupSt(v702, v701 + 21) < 0 )
              v701[21] = 0;
          }
        }
      }
      goto LABEL_1272;
    }
    v1167 = 0;
    if ( v1210 != 1 )
    {
      sub_1413EF4D0();
      goto LABEL_997;
    }
    LOBYTE(v547) = v1183;
    v548 = sub_141224EE0(v1157, v547, &v1195);
    v1210 = v548;
    if ( v1195 )
    {
      OSRR::SetAppAllowed((OSRR *)&v1235, 0);
LABEL_997:
      v548 = v1210;
    }
    if ( v548 < 0 )
    {
      v115 = v548;
      XlsDiag::LogSetHrCoreTag(v548, 0x1797718u);
      v584 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
      v585 = OpenTelemetry::POpenFileStageModel(v584);
      v586 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1406, 0x1F0CB5C6u);
      v587 = SXVWGEOM::RwFirst(v586);
      WorkflowStageModelDriver<OpenFileWorkflowStageModel>::LogHr(v585, 2214658821LL, v587);
      goto LABEL_1093;
    }
    if ( v1154 && !vpoldocument )
      vpoldocument = v1157;
    errDeferred = 0;
    if ( !v1169 )
    {
      v549 = BOOKO::Plocaleinfo((BOOKO *)&vapp);
      if ( FStBundled(v549, &v1567) )
        StripProjNameSt(&v1567, 257);
      goto LABEL_1005;
    }
    v555 = BOOKO::Plocaleinfo((BOOKO *)&vapp);
    if ( FStBundled(v555, &v1567) )
      StripProjNameSt(&v1567, 257);
    v169 = v1171;
LABEL_1026:
    v1169 = 1;
    v556 = FileSource::HrGetFileTemp(v1305, 6);
    v1152 = v556;
    v115 = v556;
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
    v1167 = FileSource::StreamOpen((FileSource *)v1305, v557, 0);
    while ( 1 )
    {
      if ( a7 == 1024 )
        goto LABEL_1053;
      if ( !SbFromHpCore(v1167) )
        goto LABEL_1053;
      v558 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
      if ( *(_QWORD *)(v558 + 40) )
      {
        if ( (*(_DWORD *)(*(_QWORD *)(v558 + 40) + 884LL) & 0x200) != 0 )
          goto LABEL_1053;
      }
      if ( v169 || !(unsigned int)FIsExecutableFile(*((void **)v1167 + 1)) )
        break;
      v169 = 1;
      v1171 = 1;
      v1214 = 1;
      StreamClose(v1167);
LABEL_1038:
      v559 = 1048704;
      if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 872LL)
                     + 104LL) != 2 )
        v559 = 0;
      v1167 = FileSource::StreamOpen((FileSource *)v1305, ((v169 != 0) + 1024) | (unsigned int)v559, 0);
      v560 = 0;
      if ( !v1157 )
        goto LABEL_1043;
      errDeferred = _IMsoOLDocument_GetDeferredError(v1157);
      v561 = errDeferred == 0;
      if ( !errDeferred )
      {
        v560 = 0;
LABEL_1043:
        if ( !v169 )
        {
          if ( SbFromHpCore(v1167) )
            v560 = 0;
          else
            v560 = (unsigned __int16)v1167;
        }
        errDeferred = v560;
        v561 = v560 == 0;
      }
      if ( !v561 )
        goto LABEL_1026;
    }
    v562 = FileSource::HrGetFileTemp(v1305, 8);
    v1152 = v562;
    v115 = v562;
    if ( v562 < 0 )
    {
      XlsDiag::LogSetHrCoreTag(v562, 0x27413A0u);
      goto LABEL_1088;
    }
    v563 = BKORWS::Psh((BKORWS *)v1350);
    if ( !(unsigned int)sub_140798AF0(v563, (__int64)v1339, (__int64)v1305, a16, (__int64)&v1235) )
    {
LABEL_1089:
      v582 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
      *(_DWORD *)(v582 + 2024) = 0;
      *(_DWORD *)(v582 + 2028) = 0;
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 336LL) = v1220;
      LOBYTE(v265) = 0;
      StreamClose(v1167);
      v68 = v1158;
      if ( v1158 )
      {
        v583 = PivotOperationBase::PSxview((PivotOperationBase *)v1158);
        *((_WORD *)v583 + 18) |= 8u;
      }
      v115 = -2146827284;
      XlsDiag::LogSetHrCoreTag(-2146827284, 0x179770Fu);
      goto LABEL_518;
    }
LABEL_1053:
    if ( SbFromHpCore(v1167) )
      goto LABEL_1022;
  }
  while ( (_WORD)v1167 != 2 );
  v564 = FileSource::HrGetFileTemp(v1305, 9);
  v1152 = v564;
  v115 = v564;
  if ( v564 < 0 )
  {
    XlsDiag::LogSetHrCoreTag(v564, 0x27413A1u);
LABEL_1088:
    Error(327845);
    goto LABEL_1089;
  }
  v565 = Mso::TCntPtr<Osf::IOsfAutorunManager>::operator->(&v1179);
  v566 = (LXBASE *)OpenTelemetry::POpenFileStageModel(v565);
  v567 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1405, 0x1F0CB5C8u);
  SXVWGEOM::RwFirst(v567);
  WorkflowStageModelDriver<OpenFileWorkflowStageModel>::TransitionTo(v566);
  if ( !XllFlighting::FComponentizedXlls(v568) )
  {
    v1289 = 0;
    v574 = (const wchar_t *)BKORWS::Psh((BKORWS *)v1350);
    v115 = HrRidLoadDLLFile_Deprecated(v574, &v1289, &v1166);
    v1152 = v115;
    if ( v115 < 0 )
      goto LABEL_1133;
    if ( v1289 )
    {
LABEL_1065:
      errDeferred = 0;
      v1153 = 3;
    }
    else
    {
      v573 = 506057947;
      v115 = -2147287008;
      v1152 = -2147287008;
LABEL_1064:
      XlsDiag::LogSetHrCoreTag(-2147287008, v573);
      OkAlert(196759, v1568);
    }
    goto LABEL_439;
  }
  v569 = BKORWS::Psh((BKORWS *)v1350);
  v570 = PcellwGuard::PcellwGuard((PcellwGuard *)v1501, v569);
  LOBYTE(v571) = 1;
  XllFileFromOutsideCalc = XllHost::HrLoadXllFileFromOutsideCalc(*(_QWORD *)v570, v571, 0);
  v1166 = XllFileFromOutsideCalc;
  if ( XllFileFromOutsideCalc >= 0 )
    goto LABEL_1065;
  if ( XllFileFromOutsideCalc == -2080308478 )
  {
    v573 = 36758018;
    v115 = -2147287008;
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
  v606 = NtCurrentTeb()->ThreadLocalStoragePointer;
  vfPretendNotStg = 0;
  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v606 + 304LL) + 336LL) = v1220;
  XlsDiag::LogSetHrCoreTag(-2146827284, 0x17976D3u);
  LOBYTE(v607) = std::nullopt;
  std::optional<Measurements::MeasureElapsedTime>::operator=(v1512, v607);
  LOBYTE(v608) = std::nullopt;
  sub_14240D350(v1524, v608);
  OsfOpenScope::Destroy((OsfOpenScope *)v1485);
  XslClear((struct XSL *)&v1541);
  ClearStatusString(11);
  v609 = *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL);
  if ( *(_QWORD *)(v609 + 40) != v1301 )
    XlsDiag::SendTraceTag(20509321, 187, 10);
  if ( v1302 )
  {
    v609 = 304;
    if ( *(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL) == v1302 )
    {
      XlsDiag::SendTraceTag(20509322, 187, 10);
      if ( !BOOK::Pioldoc(*(BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL)) )
      {
        HrFreeBook(*(struct BOOK **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 40LL));
        v610 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1369, 0x237630DEu);
        v611 = SXVWGEOM::RwFirst(v610);
        v612 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 128LL);
        v613 = 0;
        while ( v612 )
        {
          v613 = v612[1];
          if ( v613 )
            break;
          v612 = (_QWORD *)*v612;
        }
        LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v613 + 96), 0, v611);
      }
    }
  }
  if ( v1303 != (struct SH *)65534 )
  {
    v1114 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)v1370, 0x237630DDu);
    v1115 = SXVWGEOM::RwFirst(v1114);
    v1116 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 304LL) + 128LL);
    v1117 = 0;
    while ( v1116 )
    {
      v1117 = v1116[1];
      if ( v1117 )
        break;
      v1116 = (_QWORD *)*v1116;
    }
    LOCATIONCONTEXTDATA::CurSh(*(LOCATIONCONTEXTDATA **)(v1117 + 96), v1303, v1115);
  }
  if ( v1182 )
    Mso::PerfScenario::HrEndScenario(
      (Mso::PerfScenario *)&vmsoperfidOfficeXLFileOpen,
      (const struct Mso::PerfScenario::MsoPerfScenarioId *)v609);
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
  v1118 = (__int64 *)NtCurrentTeb()->ThreadLocalStoragePointer;
  v1119 = *v1118;
  v1120 = *(_QWORD *)(*v1118 + 304);
  *(_DWORD *)(v1120 + 2024) = 0;
  *(_DWORD *)(v1120 + 2028) = 0;
  GLOBALS::GLOBALSCONTAINER::m_fs = 0;
  sub_1411BF070(v1119);
  sub_141232FB0(v1121);
  LOBYTE(v1122) = std::nullopt;
  std::optional<FutureFunctionLabelCreationTracker>::operator=(v1516, v1122);
  LOBYTE(v1123) = std::nullopt;
  std::optional<AutomaticNumberConversionLoadPasteHelper>::operator=(v1344, v1123);
  LOBYTE(v1124) = std::nullopt;
  sub_14240D390(v1234, v1124);
  std::optional<XlSecurity::XllTelemetry>::~optional<XlSecurity::XllTelemetry>(v1351);
  v605 = v1166;
  if ( v1166 < 0 )
  {
    v1041 = 512506062;
LABEL_2130:
    XlsDiag::LogSetHrCoreTag(v605, v1041);
  }
LABEL_2131:
  sub_140475EA0(v1234);
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
  sub_140474FD0(v1524);
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
  sub_140474B60(&v1208);
  sub_140474C80(&v1190);
  return (unsigned int)v605;
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
