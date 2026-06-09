# CMsoOLDocFile::HrDownloadTempViaRosebud(wchar_t *,int,_MSOSRVERRTYPE *,bool &)

- ea: `0x1806940a0`
- end: `0x180695676`
- name: `?HrDownloadTempViaRosebud@CMsoOLDocFile@@IEAAJPEA_WHPEAW4_MSOSRVERRTYPE@@AEA_N@Z`
- size: `5590`
- prototype: `__int64 __fastcall(CMsoOLDocFile *__hidden this, wchar_t *, int, enum _MSOSRVERRTYPE *, bool *)`
- caller_count: `1`
- callee_count: `51`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1811523d4`

## callees

- `0x180014400`
- `0x180015310`
- `0x180015b94`
- `0x180032d80`
- `0x180032e30`
- `0x180033810`
- `0x18003e4b0`
- `0x180040c70`
- `0x180052610`
- `0x18005273c`
- `0x180052c8c`
- `0x18008a404`
- `0x1800bbe90`
- `0x1800bcb8c`
- `0x1800bcce0`
- `0x1800e8d70`
- `0x1801255bc`
- `0x1801b547c`
- `0x180206350`
- `0x180218220`
- `0x180239aa0`
- `0x18023c2e0`
- `0x18023de48`
- `0x18023e770`
- `0x18023e7b4`
- `0x18023e8d0`
- `0x180262b50`
- `0x18055ce40`
- `0x180693940`
- `0x180693b4c`
- `0x1806940a0`
- `0x180695678`
- `0x180695fec`
- `0x18069d420`
- `0x18082be0c`
- `0x1809e9028`
- `0x180a76188`
- `0x180b045e0`
- `0x180bafb00`
- `0x1811391d0`
- `0x181139260`
- `0x181139400`
- `0x181141bf0`
- `0x181142770`
- `0x1811518e0`
- `0x181151f14`
- `0x1811520f4`
- `0x181153360`
- `0x181153b50`
- `0x181154e50`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x1806953f4`
- `KERNEL32!GetFileAttributesW` at `0x1806953f4`
- `KERNEL32!SetFileAttributesW` at `0x180695424`
- `KERNEL32!SetFileAttributesW` at `0x180695424`
- `Mso98Win32Client!__imp_?FIsURL@@YAHPEB_WPEAH11@Z` at `0x180694205`
- `Mso98Win32Client!__imp_?FIsURL@@YAHPEB_WPEAH11@Z` at `0x180694205`
- `Mso98Win32Client!__imp_?GetWzLeafFromWzPath@@YAJPEA_WHPEB_WHH@Z` at `0x18069501d`
- `Mso98Win32Client!__imp_?GetWzLeafFromWzPath@@YAJPEA_WHPEB_WHH@Z` at `0x18069501d`
- `Mso98Win32Client!__imp_?MsoioloptGet@@YAKXZ` at `0x1806953fc`
- `Mso98Win32Client!__imp_?MsoioloptGet@@YAKXZ` at `0x1806953fc`
- `Mso98Win32Client!__imp_??1CFileFolder@@UEAA@XZ` at `0x180694a8b`
- `Mso98Win32Client!__imp_??1CFileFolder@@UEAA@XZ` at `0x180694e9f`
- `Mso98Win32Client!__imp_??1CFileFolder@@UEAA@XZ` at `0x180695533`
- `Mso98Win32Client!__imp_??1CFileFolder@@UEAA@XZ` at `0x1806955c4`
- `Mso98Win32Client!__imp_??1CFileFolder@@UEAA@XZ` at `0x180694a8b`
- `Mso98Win32Client!__imp_??1CFileFolder@@UEAA@XZ` at `0x180694e9f`
- `Mso98Win32Client!__imp_??1CFileFolder@@UEAA@XZ` at `0x180695533`
- `Mso98Win32Client!__imp_??1CFileFolder@@UEAA@XZ` at `0x1806955c4`
- `Mso98Win32Client!__imp_??0CFile@@QEAA@PEB_WKHH@Z` at `0x180694671`
- `Mso98Win32Client!__imp_??0CFile@@QEAA@PEB_WKHH@Z` at `0x180694671`
- `Mso30Win32Client!__imp_?InsertIntoResourceString@Strings@Mso@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHINSTANCE__@@HV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@4@@Z` at `0x180695108`
- `Mso30Win32Client!__imp_?InsertIntoResourceString@Strings@Mso@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHINSTANCE__@@HV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@4@@Z` at `0x180695108`
- `Mso30Win32Client!__imp_?FormatMSODMGSI@ResourceInfo@Mso@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUMSODMGSI@@@Z` at `0x180694b69`
- `Mso30Win32Client!__imp_?FormatMSODMGSI@ResourceInfo@Mso@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUMSODMGSI@@@Z` at `0x180694b69`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x180695089`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x180695089`
- `Mso30Win32Client!__imp_?GetAlertIdFromMsoIds@Alerts@Mso@@YAHH@Z` at `0x18069512b`
- `Mso30Win32Client!__imp_?GetAlertIdFromMsoIds@Alerts@Mso@@YAHH@Z` at `0x18069512b`
- `Mso30Win32Client!__imp_??1OleJSScopedActivationFilter@ComSecurity@Mso@@QEAA@XZ` at `0x18069563d`
- `Mso30Win32Client!__imp_??1OleJSScopedActivationFilter@ComSecurity@Mso@@QEAA@XZ` at `0x18069563d`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x18069519d`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x18069519d`
- `Mso30Win32Client!__imp_??0OleJSScopedActivationFilter@ComSecurity@Mso@@QEAA@AEBVMsoReserveTag@@_N@Z` at `0x1806941a2`
- `Mso30Win32Client!__imp_??0OleJSScopedActivationFilter@ComSecurity@Mso@@QEAA@AEBVMsoReserveTag@@_N@Z` at `0x1806941a2`
- `Mso30Win32Client!__imp_?GetWatsonAlertIdFromMsoIds@Alerts@Mso@@YAIH@Z` at `0x180695154`
- `Mso30Win32Client!__imp_?GetWatsonAlertIdFromMsoIds@Alerts@Mso@@YAIH@Z` at `0x180695154`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x1806951ba`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x1806951ba`
- `Mso30Win32Client!__imp_?MsoLocLibraryFromAlias@@YAPEAUHINSTANCE__@@K@Z` at `0x1806950dc`
- `Mso30Win32Client!__imp_?MsoLocLibraryFromAlias@@YAPEAUHINSTANCE__@@K@Z` at `0x1806950dc`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x180694392`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x1806943b9`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x180694d4a`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x180694392`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x1806943b9`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x180694d4a`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x18069564b`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x18069564b`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x180694da6`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x180694db3`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x1806951e7`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x1806951fe`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x18069520d`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x180694da6`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x180694db3`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x1806951e7`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x1806951fe`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x18069520d`
- `Mso20Win32Client!__imp_?HrGetDisplayForm@CMsoUrlSimple@@UEBAJPEA_WPEAHW4MsoUrlDisplayFormFlags@@@Z` at `0x18069506a`
- `Mso20Win32Client!__imp_?HrGetDisplayForm@CMsoUrlSimple@@UEBAJPEA_WPEAHW4MsoUrlDisplayFormFlags@@@Z` at `0x18069506a`
- `Mso20Win32Client!__imp_?GetFirstInstance@Instance@Mso@@YAPEAUMSOINST@@XZ` at `0x180694724`
- `Mso20Win32Client!__imp_?GetFirstInstance@Instance@Mso@@YAPEAUMSOINST@@XZ` at `0x18069486b`
- `Mso20Win32Client!__imp_?GetFirstInstance@Instance@Mso@@YAPEAUMSOINST@@XZ` at `0x180694724`
- `Mso20Win32Client!__imp_?GetFirstInstance@Instance@Mso@@YAPEAUMSOINST@@XZ` at `0x18069486b`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x18069425d`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x18069427b`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180694b55`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180694fae`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x18069425d`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x18069427b`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180694b55`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180694fae`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180694240`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180694240`
- `Mso20Win32Client!__imp_?Success@Activity@Telemetry@Mso@@QEAAAEAV?$optional@_N@std@@XZ` at `0x180695600`
- `Mso20Win32Client!__imp_?Success@Activity@Telemetry@Mso@@QEAAAEAV?$optional@_N@std@@XZ` at `0x180695600`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x180694155`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x180694155`
- `Mso20Win32Client!__imp_??0CMsoUrlSimple@@QEAA@XZ` at `0x180694c93`
- `Mso20Win32Client!__imp_??0CMsoUrlSimple@@QEAA@XZ` at `0x180694ca1`
- `Mso20Win32Client!__imp_??0CMsoUrlSimple@@QEAA@XZ` at `0x180694feb`
- `Mso20Win32Client!__imp_??0CMsoUrlSimple@@QEAA@XZ` at `0x180694c93`
- `Mso20Win32Client!__imp_??0CMsoUrlSimple@@QEAA@XZ` at `0x180694ca1`
- `Mso20Win32Client!__imp_??0CMsoUrlSimple@@QEAA@XZ` at `0x180694feb`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x18069562d`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x18069562d`
- `Mso20Win32Client!__imp_??0MeasureElapsedTime@Measurements@@QEAA@UMeasurementIdType@1@_N$$QEAVStopwatch@1@@Z` at `0x1806941d9`
- `Mso20Win32Client!__imp_??0MeasureElapsedTime@Measurements@@QEAA@UMeasurementIdType@1@_N$$QEAVStopwatch@1@@Z` at `0x1806941d9`
- `Mso20Win32Client!__imp_?HrGetFileExt@CMsoUrlSimple@@UEBAJPEA_WPEAH@Z` at `0x180694d0b`
- `Mso20Win32Client!__imp_?HrGetFileExt@CMsoUrlSimple@@UEBAJPEA_WPEAH@Z` at `0x180694d2c`
- `Mso20Win32Client!__imp_?HrGetFileExt@CMsoUrlSimple@@UEBAJPEA_WPEAH@Z` at `0x180694d0b`
- `Mso20Win32Client!__imp_?HrGetFileExt@CMsoUrlSimple@@UEBAJPEA_WPEAH@Z` at `0x180694d2c`
- `Mso20Win32Client!__imp_?MsoWzGetTempFilename@@YAPEA_WPEA_WHPEB_W@Z` at `0x1806952ea`
- `Mso20Win32Client!__imp_?MsoWzGetTempFilename@@YAPEA_WPEA_WHPEB_W@Z` at `0x1806952ea`
- `Mso20Win32Client!__imp_?MsoHrCreateUrlSimpleFromUser@@YAJPEAPEAUIMsoUrl@@PEB_WKPEBU1@W4MsoUrlCreateFlags@@PEAUIMsoMemHeap@@@Z` at `0x180694226`
- `Mso20Win32Client!__imp_?MsoHrCreateUrlSimpleFromUser@@YAJPEAPEAUIMsoUrl@@PEB_WKPEBU1@W4MsoUrlCreateFlags@@PEAUIMsoMemHeap@@@Z` at `0x180694226`
- `Mso20Win32Client!__imp_?GetNamespace@MSO@FileIO@Office@@YAAEBUTelemetryNamespace@Telemetry@Mso@@XZ` at `0x18069415b`
- `Mso20Win32Client!__imp_?GetNamespace@MSO@FileIO@Office@@YAAEBUTelemetryNamespace@Telemetry@Mso@@XZ` at `0x18069415b`
- `OLEAUT32!__imp_SysFreeString` at `0x180694988`
- `OLEAUT32!__imp_SysFreeString` at `0x180694ef8`
- `OLEAUT32!__imp_SysFreeString` at `0x18069558f`
- `OLEAUT32!__imp_SysFreeString` at `0x1806955ea`
- `OLEAUT32!__imp_SysFreeString` at `0x180694988`
- `OLEAUT32!__imp_SysFreeString` at `0x180694ef8`
- `OLEAUT32!__imp_SysFreeString` at `0x18069558f`
- `OLEAUT32!__imp_SysFreeString` at `0x1806955ea`
- `urlmon!CoInternetCreateSecurityManager` at `0x180694dd6`
- `urlmon!CoInternetCreateSecurityManager` at `0x180694dd6`

## string_xrefs

- `0x180694168`: `CMsoOLDocFileHrDownloadTempViaRosebud`
- `0x1806942a9`: `OLDoc:HrDownloadTemp Non-Syncman File not using Http Redir`
- `0x180694552`: `OLDoc:HrDownloadTemp http: URL`
- `0x18069459f`: `OLDoc:HrDownloadTemp ftp: URL`

## pseudocode

```c

```
