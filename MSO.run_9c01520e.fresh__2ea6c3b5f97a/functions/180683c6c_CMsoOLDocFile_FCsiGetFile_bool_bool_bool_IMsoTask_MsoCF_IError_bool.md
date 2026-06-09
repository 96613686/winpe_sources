# CMsoOLDocFile::FCsiGetFile(bool,bool,bool,IMsoTask *,MsoCF::IError * *,bool *)

- ea: `0x180683c6c`
- end: `0x18068652d`
- name: `?FCsiGetFile@CMsoOLDocFile@@IEAAH_N00PEAUIMsoTask@@PEAPEAUIError@MsoCF@@PEA_N@Z`
- size: `10433`
- prototype: `__int64 __fastcall(CMsoOLDocFile *__hidden this, bool, bool, bool, struct IMsoTask *, struct MsoCF::IError **, bool *)`
- caller_count: `1`
- callee_count: `105`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1804d9acc`

## callees

- `0x18000f540`
- `0x180010020`
- `0x180014160`
- `0x180014c5c`
- `0x180015d0c`
- `0x180015d60`
- `0x1800182e8`
- `0x18001c9e0`
- `0x18001d460`
- `0x180028630`
- `0x180029700`
- `0x18002b13c`
- `0x18002c44c`
- `0x18002fae0`
- `0x180054140`
- `0x18005eab0`
- `0x18005f6a4`
- `0x18006b370`
- `0x18006b850`
- `0x18006cf38`
- `0x18006d0f8`
- `0x180070018`
- `0x1800707d0`
- `0x180071a90`
- `0x180071e54`
- `0x180071ec4`
- `0x180071fb0`
- `0x180073db0`
- `0x180073e90`
- `0x180073ff0`
- `0x180074410`
- `0x180077bc0`
- `0x180077ce4`
- `0x180077f1c`
- `0x18008b6d0`
- `0x180096ca4`
- `0x1800ae184`
- `0x1800e0730`
- `0x1800e8948`
- `0x1800f4240`
- `0x1800f4274`
- `0x18012dd70`
- `0x18016eca0`
- `0x18018506c`
- `0x18018635c`
- `0x1801a8944`
- `0x180251fc0`
- `0x1802c10c0`
- `0x180308174`
- `0x18034af54`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x18068650f`
- `KERNEL32!GetFileAttributesW` at `0x18068650f`
- `KERNEL32!SetFileAttributesW` at `0x180686521`
- `KERNEL32!SetFileAttributesW` at `0x180686521`
- `KERNEL32!SetEvent` at `0x180684768`
- `KERNEL32!SetEvent` at `0x180684768`
- `Mso98Win32Client!__imp_?CreateThirdPartyCallback@ServiceManagerCallback@Mso@@YA?AV?$TCntPtr@VIThirdPartyServiceManagerCallback@ServiceManagerCallback@Mso@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x1806859bb`
- `Mso98Win32Client!__imp_?CreateThirdPartyCallback@ServiceManagerCallback@Mso@@YA?AV?$TCntPtr@VIThirdPartyServiceManagerCallback@ServiceManagerCallback@Mso@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x1806859bb`
- `Mso98Win32Client!__imp_?GetInstance@OfficeServicesManager@Mso@@YAPEAUIOfficeServicesManager@12@XZ` at `0x180684dec`
- `Mso98Win32Client!__imp_?GetInstance@OfficeServicesManager@Mso@@YAPEAUIOfficeServicesManager@12@XZ` at `0x180684f12`
- `Mso98Win32Client!__imp_?GetInstance@OfficeServicesManager@Mso@@YAPEAUIOfficeServicesManager@12@XZ` at `0x180685923`
- `Mso98Win32Client!__imp_?GetInstance@OfficeServicesManager@Mso@@YAPEAUIOfficeServicesManager@12@XZ` at `0x180684dec`
- `Mso98Win32Client!__imp_?GetInstance@OfficeServicesManager@Mso@@YAPEAUIOfficeServicesManager@12@XZ` at `0x180684f12`
- `Mso98Win32Client!__imp_?GetInstance@OfficeServicesManager@Mso@@YAPEAUIOfficeServicesManager@12@XZ` at `0x180685923`
- `Mso98Win32Client!__imp_?SetEnableBHO@MsoServerInfoUtils@@YAXPEBUIMsoUrl@@_N@Z` at `0x180684794`
- `Mso98Win32Client!__imp_?SetEnableBHO@MsoServerInfoUtils@@YAXPEBUIMsoUrl@@_N@Z` at `0x180684794`
- `Mso98Win32Client!__imp_?PromptForWopiCreds@MsoServerInfoUtils@@YAJAEBUIMsoUrl@@PEB_WAEBUUIExecutionContext@Authentication@Mso@@@Z` at `0x180685a18`
- `Mso98Win32Client!__imp_?PromptForWopiCreds@MsoServerInfoUtils@@YAJAEBUIMsoUrl@@PEB_WAEBUUIExecutionContext@Authentication@Mso@@@Z` at `0x180685a18`
- `mso40uiWin32Client!__imp_?HwndParentForDmEx@@YAPEAUHWND__@@_N@Z` at `0x180684008`
- `mso40uiWin32Client!__imp_?HwndParentForDmEx@@YAPEAUHWND__@@_N@Z` at `0x180684008`
- `Mso30Win32Client!__imp_?CreateCsiError@Csi@@YAXVCsiErrorCode@1@PEAPEAUIError@MsoCF@@@Z` at `0x18068565e`
- `Mso30Win32Client!__imp_?CreateCsiError@Csi@@YAXVCsiErrorCode@1@PEAPEAUIError@MsoCF@@@Z` at `0x18068565e`
- `Mso30Win32Client!__imp_?IsWopiPromptingOnOpenEnabled@ResourceInfo@Mso@@YA_NXZ` at `0x180684ce2`
- `Mso30Win32Client!__imp_?IsWopiPromptingOnOpenEnabled@ResourceInfo@Mso@@YA_NXZ` at `0x180684ce2`
- `Mso30Win32Client!__imp_?ExtractAllWopiPropertiesFromWopiUrl@Url@Mso@@YA?AW4WopiResult@12@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@111_N@Z` at `0x180684dde`
- `Mso30Win32Client!__imp_?ExtractAllWopiPropertiesFromWopiUrl@Url@Mso@@YA?AW4WopiResult@12@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@111_N@Z` at `0x180684f04`
- `Mso30Win32Client!__imp_?ExtractAllWopiPropertiesFromWopiUrl@Url@Mso@@YA?AW4WopiResult@12@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@111_N@Z` at `0x180685915`
- `Mso30Win32Client!__imp_?ExtractAllWopiPropertiesFromWopiUrl@Url@Mso@@YA?AW4WopiResult@12@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@111_N@Z` at `0x180684dde`
- `Mso30Win32Client!__imp_?ExtractAllWopiPropertiesFromWopiUrl@Url@Mso@@YA?AW4WopiResult@12@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@111_N@Z` at `0x180684f04`
- `Mso30Win32Client!__imp_?ExtractAllWopiPropertiesFromWopiUrl@Url@Mso@@YA?AW4WopiResult@12@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@111_N@Z` at `0x180685915`
- `Mso30Win32Client!__imp_?CreateHRESULTError@MsoCF@@YAXJPEAPEAUIError@1@@Z` at `0x180685485`
- `Mso30Win32Client!__imp_?CreateHRESULTError@MsoCF@@YAXJPEAPEAUIError@1@@Z` at `0x180685485`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x180684f63`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x180685027`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x180685282`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x1806852f2`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x1806853b4`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x18068572a`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x180685c84`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x180685d84`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x180685f24`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x180684f63`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x180685027`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x180685282`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x1806852f2`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x1806853b4`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x18068572a`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x180685c84`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x180685d84`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x180685f24`
- `Mso30Win32Client!__imp_?GetAlertIdFromMsoIds@Alerts@Mso@@YAHH@Z` at `0x18068577a`
- `Mso30Win32Client!__imp_?GetAlertIdFromMsoIds@Alerts@Mso@@YAHH@Z` at `0x18068577a`
- `Mso30Win32Client!__imp_?CreateHRESULTErrorTag@MsoCF@@YAXJPEAPEAUIError@1@K@Z` at `0x180684521`
- `Mso30Win32Client!__imp_?CreateHRESULTErrorTag@MsoCF@@YAXJPEAPEAUIError@1@K@Z` at `0x180684521`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x180684fda`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x1806850d3`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x180685157`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x180685208`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x180685360`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x1806857d1`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x180685d1c`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x180685dea`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x180685e68`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x180684fda`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x1806850d3`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x180685157`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x180685208`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x180685360`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x1806857d1`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x180685d1c`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x180685dea`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x180685e68`
- `Mso30Win32Client!__imp_?FNetworkExists@NetCost@Mso@@YA_NXZ` at `0x1806840df`
- `Mso30Win32Client!__imp_?FNetworkExists@NetCost@Mso@@YA_NXZ` at `0x1806840df`
- `Mso30Win32Client!__imp_?GetWatsonAlertIdFromMsoIds@Alerts@Mso@@YAIH@Z` at `0x1806857a3`
- `Mso30Win32Client!__imp_?GetWatsonAlertIdFromMsoIds@Alerts@Mso@@YAIH@Z` at `0x1806857a3`
- `Mso30Win32Client!__imp_?CreateCsiErrorTag@Csi@@YAXVCsiErrorCode@1@PEAPEAUIError@MsoCF@@K@Z` at `0x180684e38`
- `Mso30Win32Client!__imp_?CreateCsiErrorTag@Csi@@YAXVCsiErrorCode@1@PEAPEAUIError@MsoCF@@K@Z` at `0x18068546a`
- `Mso30Win32Client!__imp_?CreateCsiErrorTag@Csi@@YAXVCsiErrorCode@1@PEAPEAUIError@MsoCF@@K@Z` at `0x180685857`
- `Mso30Win32Client!__imp_?CreateCsiErrorTag@Csi@@YAXVCsiErrorCode@1@PEAPEAUIError@MsoCF@@K@Z` at `0x18068606e`
- `Mso30Win32Client!__imp_?CreateCsiErrorTag@Csi@@YAXVCsiErrorCode@1@PEAPEAUIError@MsoCF@@K@Z` at `0x1806862df`
- `Mso30Win32Client!__imp_?CreateCsiErrorTag@Csi@@YAXVCsiErrorCode@1@PEAPEAUIError@MsoCF@@K@Z` at `0x180684e38`
- `Mso30Win32Client!__imp_?CreateCsiErrorTag@Csi@@YAXVCsiErrorCode@1@PEAPEAUIError@MsoCF@@K@Z` at `0x18068546a`
- `Mso30Win32Client!__imp_?CreateCsiErrorTag@Csi@@YAXVCsiErrorCode@1@PEAPEAUIError@MsoCF@@K@Z` at `0x180685857`
- `Mso30Win32Client!__imp_?CreateCsiErrorTag@Csi@@YAXVCsiErrorCode@1@PEAPEAUIError@MsoCF@@K@Z` at `0x18068606e`
- `Mso30Win32Client!__imp_?CreateCsiErrorTag@Csi@@YAXVCsiErrorCode@1@PEAPEAUIError@MsoCF@@K@Z` at `0x1806862df`
- `Mso30Win32Client!__imp_MsoFLoadWz` at `0x180685720`
- `Mso30Win32Client!__imp_MsoFLoadWz` at `0x180685720`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x180684ff2`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x1806850ee`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x180685172`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x180685223`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x18068537b`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x1806857e9`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x180685d37`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x180685e02`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x180685e83`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x180684ff2`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x1806850ee`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x180685172`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x180685223`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x18068537b`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x1806857e9`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x180685d37`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x180685e02`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x180685e83`
- `Mso30Win32Client!__imp_?MsoLocLibraryFromAlias@@YAPEAUHINSTANCE__@@K@Z` at `0x180685703`
- `Mso30Win32Client!__imp_?MsoLocLibraryFromAlias@@YAPEAUHINSTANCE__@@K@Z` at `0x180685703`
- `Mso30Win32Client!__imp_?GetAlertMessageFromMsoIds@Alerts@Mso@@YA?AUAlertMessage@12@HAEBV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@Z` at `0x180684fae`
- `Mso30Win32Client!__imp_?GetAlertMessageFromMsoIds@Alerts@Mso@@YA?AUAlertMessage@12@HAEBV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@Z` at `0x1806850a4`
- `Mso30Win32Client!__imp_?GetAlertMessageFromMsoIds@Alerts@Mso@@YA?AUAlertMessage@12@HAEBV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@Z` at `0x18068512f`
- `Mso30Win32Client!__imp_?GetAlertMessageFromMsoIds@Alerts@Mso@@YA?AUAlertMessage@12@HAEBV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@Z` at `0x1806851d9`
- `Mso30Win32Client!__imp_?GetAlertMessageFromMsoIds@Alerts@Mso@@YA?AUAlertMessage@12@HAEBV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@Z` at `0x180685338`
- `Mso30Win32Client!__imp_?GetAlertMessageFromMsoIds@Alerts@Mso@@YA?AUAlertMessage@12@HAEBV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@Z` at `0x180685ce9`
- `Mso30Win32Client!__imp_?GetAlertMessageFromMsoIds@Alerts@Mso@@YA?AUAlertMessage@12@HAEBV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@Z` at `0x180685dba`
- `Mso30Win32Client!__imp_?GetAlertMessageFromMsoIds@Alerts@Mso@@YA?AUAlertMessage@12@HAEBV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@Z` at `0x180685e40`
- `Mso30Win32Client!__imp_?GetAlertMessageFromMsoIds@Alerts@Mso@@YA?AUAlertMessage@12@HAEBV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@Z` at `0x180684fae`
- `Mso30Win32Client!__imp_?GetAlertMessageFromMsoIds@Alerts@Mso@@YA?AUAlertMessage@12@HAEBV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@Z` at `0x1806850a4`
- `Mso30Win32Client!__imp_?GetAlertMessageFromMsoIds@Alerts@Mso@@YA?AUAlertMessage@12@HAEBV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@Z` at `0x18068512f`
- `Mso30Win32Client!__imp_?GetAlertMessageFromMsoIds@Alerts@Mso@@YA?AUAlertMessage@12@HAEBV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@Z` at `0x1806851d9`
- `Mso30Win32Client!__imp_?GetAlertMessageFromMsoIds@Alerts@Mso@@YA?AUAlertMessage@12@HAEBV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@Z` at `0x180685338`
- `Mso30Win32Client!__imp_?GetAlertMessageFromMsoIds@Alerts@Mso@@YA?AUAlertMessage@12@HAEBV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@Z` at `0x180685ce9`
- `Mso30Win32Client!__imp_?GetAlertMessageFromMsoIds@Alerts@Mso@@YA?AUAlertMessage@12@HAEBV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@Z` at `0x180685dba`
- `Mso30Win32Client!__imp_?GetAlertMessageFromMsoIds@Alerts@Mso@@YA?AUAlertMessage@12@HAEBV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@Z` at `0x180685e40`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x18068444d`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x1806845ce`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x18068481d`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x18068444d`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x1806845ce`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x18068481d`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x1806845a1`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x1806847f0`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x1806854a8`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x180685b49`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x1806845a1`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x1806847f0`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x1806854a8`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x180685b49`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18068543a`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180685691`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18068640c`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18068543a`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180685691`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18068640c`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180684389`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180684389`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180683db7`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180683dd5`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180683f3a`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180683f5b`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180683f7c`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180683fd6`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x18068411b`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180684142`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180684180`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1806841a2`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1806846f4`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1806849ed`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180684abd`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180684b7d`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x18068551d`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180685606`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x18068600f`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1806862a1`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1806863ad`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180683db7`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180683dd5`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180683f3a`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180683f5b`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180683f7c`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180683fd6`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x18068411b`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180684142`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180684180`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1806841a2`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1806846f4`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1806849ed`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180684abd`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180684b7d`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x18068551d`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180685606`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x18068600f`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1806862a1`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1806863ad`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1806843d7`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1806843fa`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180684b2f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180684bfb`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180684e05`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180684f27`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180685938`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1806843d7`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1806843fa`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180684b2f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180684bfb`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180684e05`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180684f27`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180685938`
- `Mso20Win32Client!__imp_?Success@Activity@Telemetry@Mso@@QEAAAEAV?$optional@_N@std@@XZ` at `0x1806847a5`
- `Mso20Win32Client!__imp_?Success@Activity@Telemetry@Mso@@QEAAAEAV?$optional@_N@std@@XZ` at `0x1806847a5`

## string_xrefs

- `0x18068561b`: `AsyncOpenKind`
- `0x180683f47`: `Protocol`
- `0x180683dc1`: `OpenFileState_Requested`
- `0x1806841b0`: `OpenOffline`
- `0x18068414e`: `isFileCachedBeforeOpen`
- `0x180684284`: `CsiCacheFileSessionBegunWithClosedFile`
- `0x180684a1a`: `CsiGetFileFromCacheMetaData`
- `0x180686027`: `CsiGetFileFromCacheMetaData`
- `0x180684acc`: `HrEnsureDownloadTaskDidNotRun`
- `0x180685c05`: `csierrWopi_InvalidUrl on open, could not prompt for creds`
- `0x180684b87`: `OpenFileState_LegacyFallback`
- `0x180685a6d`: `csierrWopi_InvalidUrl on open, prompted for creds`
- `0x18068552b`: `updatedRecoveryMode`
- `0x1806863b9`: `TempFileGenerated`

## pseudocode

```c
__int64 __fastcall CMsoOLDocFile::FCsiGetFile(
        CMsoOLDocFile *this,
        char a2,
        bool a3,
        char a4,
        struct IMsoTask *a5,
        struct MsoCF::IError **a6,
        bool *a7)
{
  struct MsoCF::IError **v7; // rbx
  bool v8; // si
  __int64 v10; // rdi
  char v11; // r12
  unsigned int v12; // r14d
  Office::FileIO::MSO *v13; // rcx
  __int64 v14; // r13
  struct IUnknown *v15; // rcx
  struct Mso::Telemetry::IDataFieldCollection *v16; // rax
  __int64 v17; // r8
  struct Mso::Telemetry::IDataFieldCollection *v18; // rbx
  unsigned int FBlockNetworkCalls; // eax
  int v20; // r9d
  __int64 v21; // rcx
  __int64 v22; // r8
  struct Mso::Telemetry::IDataFieldCollection *v23; // rax
  struct Mso::Telemetry::IDataFieldCollection *v24; // rax
  struct Mso::Telemetry::IDataFieldCollection *v25; // rax
  __int64 v26; // r8
  struct Mso::Telemetry::IDataFieldCollection *v27; // rax
  __int64 v28; // r8
  const struct MsoCF::IError *v29; // rdx
  unsigned int v30; // r9d
  int v31; // eax
  struct MsoCF::IError **v32; // r8
  unsigned int v33; // r9d
  struct Csi::IDocumentProperties *v34; // rcx
  char IsFileCached; // bl
  struct Mso::Telemetry::IDataFieldCollection *v36; // rax
  __int64 v37; // r8
  struct Mso::Telemetry::IDataFieldCollection *v38; // rax
  __int64 v39; // r8
  bool v40; // al
  bool v41; // al
  struct Mso::Telemetry::IDataFieldCollection *v42; // rax
  __int64 v43; // r8
  struct Mso::Telemetry::IDataFieldCollection *v44; // rax
  __int64 v45; // r8
  int v46; // r9d
  wchar_t *v47; // rax
  __int64 v48; // r8
  __int64 v49; // rsi
  __int64 v50; // rbx
  __int64 v51; // rax
  bool v52; // al
  __int64 v53; // r8
  struct Csi::IDocumentProperties *v54; // rcx
  unsigned int v55; // r9d
  unsigned __int64 appended; // rax
  const char *v58; // rbx
  __int64 v59; // rdx
  __int64 v60; // r8
  __int64 v61; // r9
  char v62; // r13
  char v63; // si
  Csi *v64; // rdi
  __int64 v65; // r9
  __int64 v66; // r8
  unsigned int v67; // r9d
  __int64 v68; // rax
  unsigned int v69; // r9d
  __int64 v70; // r8
  struct MsoCF::IError *v71; // rdx
  struct Csi::IDocumentProperties *v72; // rcx
  Csi *v73; // rbx
  struct MsoCF::IError **v74; // rdi
  struct MsoCF::IError *v75; // rdx
  __int64 *Controller; // rax
  __int64 v77; // rdx
  __int64 v78; // rcx
  const char *v79; // rcx
  int v80; // edi
  struct Mso::Telemetry::IDataFieldCollection *v81; // rax
  __int64 v82; // r8
  const struct IMsoUrl *v83; // rdx
  bool v84; // r8
  __int16 *v85; // rax
  struct Csi::IDocumentProperties *v86; // rcx
  unsigned int v87; // r9d
  __int64 v88; // r8
  __int64 v89; // rdx
  __int64 v90; // r8
  unsigned __int64 v91; // rcx
  wchar_t **v92; // rdx
  wchar_t *v93; // rdi
  unsigned __int64 v94; // rsi
  size_t v95; // r11
  __int64 v96; // rcx
  const char *v97; // rax
  const wchar_t *v98; // rdx
  wchar_t **v99; // rcx
  Mso::Telemetry::IDataFieldCollection *v100; // rbx
  bool v101; // dl
  __int64 FileFromCacheMetaData; // rax
  bool v103; // r8
  struct IMsoOLDocumentAsyncDownloadParams *v104; // rbx
  struct Mso::Telemetry::IDataFieldCollection *v105; // rax
  __int64 v106; // r8
  struct IUnknown *v107; // rcx
  bool v108; // zf
  struct Mso::Telemetry::IDataFieldCollection *v109; // rax
  __int64 v110; // r8
  const struct MsoCF::IError *v111; // rdx
  unsigned int v112; // r9d
  Mso::ResourceInfo *v113; // rcx
  struct MsoCF::IError *v114; // rdx
  unsigned int v115; // r9d
  Mso::OfficeServicesManager *v116; // rcx
  struct Mso::OfficeServicesManager::IOfficeServicesManager *v117; // rax
  struct Mso::OfficeServicesManager::IOfficeServicesManager *v118; // rcx
  Csi *v119; // rcx
  unsigned int v120; // r9d
  Mso::OfficeServicesManager *v121; // rcx
  struct Mso::OfficeServicesManager::IOfficeServicesManager *Instance; // rax
  struct Mso::OfficeServicesManager::IOfficeServicesManager *v123; // rcx
  __int64 v124; // rax
  __int128 *v125; // r8
  wchar_t **v126; // rax
  __int64 v127; // rax
  Mso::Alerts *v128; // rcx
  const struct MsoReserveTag *v129; // rax
  const struct Mso::Alerts::AlertParam *v130; // r9
  _BYTE *v131; // rcx
  __int64 v132; // rax
  __int64 v133; // rbx
  wchar_t **v134; // rax
  const OLECHAR *v135; // rax
  __int64 v136; // rax
  Mso::Alerts *v137; // rcx
  const struct MsoReserveTag *v138; // rax
  const struct Mso::Alerts::AlertParam *v139; // r9
  __int64 AlertMessageFromMsoIds; // rax
  Mso::Alerts *v141; // rcx
  const struct MsoReserveTag *TelemetryNamespace; // rax
  const struct Mso::Alerts::AlertParam *v143; // r9
  __int128 *v144; // rcx
  __int64 v145; // rax
  Mso::Alerts *v146; // rcx
  const struct MsoReserveTag *v147; // rax
  const struct Mso::Alerts::AlertParam *v148; // r9
  const OLECHAR *v149; // rbx
  const OLECHAR *v150; // rax
  __int64 v151; // rax
  __int128 *v152; // r8
  const OLECHAR *v153; // rbx
  const OLECHAR *v154; // rax
  __int64 v155; // rax
  Mso::Alerts *v156; // rcx
  const struct MsoReserveTag *v157; // rax
  const struct Mso::Alerts::AlertParam *v158; // r9
  __int64 v159; // rax
  __int64 v160; // rbx
  const OLECHAR *v161; // rax
  __int64 v162; // rdx
  __int64 v163; // r8
  __int64 v164; // r9
  __int64 v165; // rax
  __int64 v166; // rdx
  struct Mso::Telemetry::IDataFieldCollection *v167; // rax
  __int64 v168; // r8
  bool v169; // al
  Csi *v170; // rbx
  Csi *v171; // rcx
  struct Mso::Telemetry::IDataFieldCollection *v172; // rbx
  unsigned int *v173; // rax
  __int64 v174; // rcx
  HINSTANCE v175; // rax
  __int64 v176; // r8
  int v177; // edx
  int v178; // edx
  Mso::Alerts *v179; // rcx
  const struct MsoReserveTag *v180; // rax
  const struct Mso::Alerts::AlertParam *v181; // r9
  Csi *v182; // rcx
  unsigned int v183; // r9d
  __m128i v184; // xmm6
  Mso::OfficeServicesManager *v185; // rcx
  struct Mso::OfficeServicesManager::IOfficeServicesManager *v186; // rax
  struct Mso::OfficeServicesManager::IOfficeServicesManager *v187; // rcx
  __int64 v188; // rax
  __int128 *v189; // r8
  Mso::ApplicationModel *v190; // rcx
  struct Mso::ApplicationModel::IExecutionContext *v191; // rax
  __int64 v192; // r8
  __int64 v193; // rax
  int v194; // r9d
  const struct IMsoUrl *v195; // rax
  const struct Mso::Authentication::UIExecutionContext *v196; // r9
  int v197; // ebx
  int v198; // r9d
  __int64 v199; // rcx
  char v200; // al
  __int64 v201; // rax
  __int64 v202; // rbx
  const OLECHAR *v203; // rax
  __int64 v204; // rax
  Mso::Alerts *v205; // rcx
  const struct MsoReserveTag *v206; // rax
  const struct Mso::Alerts::AlertParam *v207; // r9
  __int64 v208; // rcx
  __int64 v209; // rax
  Mso::Alerts *v210; // rcx
  const struct MsoReserveTag *v211; // rax
  const struct Mso::Alerts::AlertParam *v212; // r9
  __int64 v213; // rax
  Mso::Alerts *v214; // rcx
  const struct MsoReserveTag *v215; // rax
  const struct Mso::Alerts::AlertParam *v216; // r9
  const OLECHAR *v217; // rbx
  const OLECHAR *v218; // rax
  struct MsoCF::IError *v219; // rdx
  __int64 v220; // rdx
  __int64 v221; // r8
  Mso::Telemetry::IDataFieldCollection *v222; // rbx
  bool v223; // dl
  const struct Mso::Telemetry::IDataContract *v224; // rax
  const struct Mso::Telemetry::ISingleDataField *v225; // rax
  unsigned int v226; // r9d
  __int64 v227; // r8
  struct Mso::Telemetry::Activity *v228; // rdx
  struct MsoCF::IError *v229; // rdx
  bool IsFallbackToHttpError; // al
  struct IMsoOLDocument *v231; // rdx
  struct IMsoOLDocument *v232; // rdx
  WCHAR *v233; // rbx
  struct Mso::Telemetry::IDataFieldCollection *v234; // rax
  __int64 v235; // r8
  struct MsoCF::IError *v236; // rax
  __int64 v237; // r8
  unsigned int v238; // r9d
  struct Mso::Telemetry::IDataFieldCollection *v239; // rax
  __int64 v240; // r8
  __int64 v241; // rax
  const wchar_t *v242; // rax
  __int64 v243; // rdx
  __int64 v244; // r8
  __int64 v245; // r9
  bool v246; // bl
  DWORD FileAttributesW; // eax
  int v248; // [rsp+20h] [rbp-E0h]
  int v249; // [rsp+28h] [rbp-D8h]
  bool v250; // [rsp+40h] [rbp-C0h] BYREF
  Csi *v251; // [rsp+48h] [rbp-B8h] BYREF
  bool v252; // [rsp+50h] [rbp-B0h] BYREF
  char v253; // [rsp+51h] [rbp-AFh]
  char v254; // [rsp+52h] [rbp-AEh]
  bool v255; // [rsp+53h] [rbp-ADh] BYREF
  struct MsoCF::IError **v256; // [rsp+58h] [rbp-A8h] BYREF
  struct Csi::IDocumentProperties *v257; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v258; // [rsp+68h] [rbp-98h] BYREF
  bool v259[16]; // [rsp+70h] [rbp-90h] BYREF
  bool v260; // [rsp+80h] [rbp-80h]
  const char *v261; // [rsp+88h] [rbp-78h] BYREF
  char *v262; // [rsp+90h] [rbp-70h]
  unsigned int v263; // [rsp+98h] [rbp-68h] BYREF
  const char *v264; // [rsp+A0h] [rbp-60h] BYREF
  void ***v265; // [rsp+A8h] [rbp-58h]
  __int16 v266; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v267; // [rsp+B8h] [rbp-48h] BYREF
  struct IUnknown *Namespace; // [rsp+C0h] [rbp-40h] BYREF
  __int16 *v269; // [rsp+C8h] [rbp-38h]
  _BYTE v270[2]; // [rsp+D0h] [rbp-30h] BYREF
  bool v271; // [rsp+D2h] [rbp-2Eh] BYREF
  WCHAR *v272; // [rsp+D8h] [rbp-28h] BYREF
  struct MsoCF::IError ***v273; // [rsp+E0h] [rbp-20h]
  _BYTE v274[2]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v275[6]; // [rsp+EAh] [rbp-16h] BYREF
  _QWORD v276[2]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v277[48]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v278[32]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v279[32]; // [rsp+150h] [rbp+50h] BYREF
  char v280[32]; // [rsp+170h] [rbp+70h] BYREF
  int AlertIdFromMsoIds; // [rsp+190h] [rbp+90h]
  char v282; // [rsp+194h] [rbp+94h]
  __int16 v283; // [rsp+195h] [rbp+95h]
  char v284; // [rsp+197h] [rbp+97h]
  unsigned int WatsonAlertIdFromMsoIds; // [rsp+198h] [rbp+98h]
  char v286; // [rsp+19Ch] [rbp+9Ch]
  __int16 v287; // [rsp+19Dh] [rbp+9Dh]
  char v288; // [rsp+19Fh] [rbp+9Fh]
  char v289; // [rsp+1A8h] [rbp+A8h]
  __int64 v290; // [rsp+1E8h] [rbp+E8h]
  _BYTE v291[32]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v292[88]; // [rsp+220h] [rbp+120h] BYREF
  char v293; // [rsp+278h] [rbp+178h]
  __int64 v294; // [rsp+2B8h] [rbp+1B8h]
  wchar_t *S1[2]; // [rsp+2D0h] [rbp+1D0h] BYREF
  size_t v296; // [rsp+2E0h] [rbp+1E0h]
  unsigned __int64 v297; // [rsp+2E8h] [rbp+1E8h]
  __int128 v298; // [rsp+2F0h] [rbp+1F0h] BYREF
  __m128i v299; // [rsp+300h] [rbp+200h]
  __int128 v300; // [rsp+310h] [rbp+210h] BYREF
  __m128i v301; // [rsp+320h] [rbp+220h]
  void **v302; // [rsp+330h] [rbp+230h] BYREF
  char Destination[8]; // [rsp+338h] [rbp+238h] BYREF
  _BYTE v304[24]; // [rsp+340h] [rbp+240h] BYREF
  __m128i v305; // [rsp+358h] [rbp+258h] BYREF
  Csi **v306; // [rsp+368h] [rbp+268h]
  __int64 v307; // [rsp+370h] [rbp+270h]
  __int64 v308; // [rsp+380h] [rbp+280h]
  __int128 v309; // [rsp+390h] [rbp+290h] BYREF
  __m128i si128; // [rsp+3A0h] [rbp+2A0h]
  __int128 v311; // [rsp+3B0h] [rbp+2B0h] BYREF
  __m128i v312; // [rsp+3C0h] [rbp+2C0h]
  _QWORD v313[2]; // [rsp+3D0h] [rbp+2D0h] BYREF
  __int64 v314; // [rsp+3E0h] [rbp+2E0h]
  char v315; // [rsp+3E8h] [rbp+2E8h]
  _QWORD v316[2]; // [rsp+3F0h] [rbp+2F0h] BYREF
  const OLECHAR *v317; // [rsp+400h] [rbp+300h]
  _OWORD v318[4]; // [rsp+408h] [rbp+308h] BYREF
  _BYTE v319[16]; // [rsp+450h] [rbp+350h] BYREF
  _BYTE v320[288]; // [rsp+460h] [rbp+360h] BYREF
  __int64 v321; // [rsp+580h] [rbp+480h] BYREF
  __int64 v322; // [rsp+588h] [rbp+488h]
  __int64 v323; // [rsp+590h] [rbp+490h]
  int v324; // [rsp+598h] [rbp+498h]
  __int64 v325; // [rsp+15E4h] [rbp+14E4h]
  char v326; // [rsp+15FCh] [rbp+14FCh]
  char v327; // [rsp+1608h] [rbp+1508h]
  _WORD v328[16]; // [rsp+1610h] [rbp+1510h] BYREF
  _BYTE v329[88]; // [rsp+1630h] [rbp+1530h] BYREF
  char v330; // [rsp+1688h] [rbp+1588h]
  WCHAR FileName[264]; // [rsp+1A10h] [rbp+1910h] BYREF

  LOBYTE(v266) = a4;
  LOBYTE(v7) = a3;
  v260 = a3;
  v8 = a2;
  v254 = a2;
  v256 = a6;
  v272 = (WCHAR *)a7;
  v10 = (__int64)this + 1544;
  v11 = 1;
  v12 = 0;
  if ( !a2 )
    goto LABEL_133;
LABEL_2:
  v263 = 6;
LABEL_3:
  v253 = 0;
  v258 = 366;
  LOWORD(v261) = 2;
  BYTE2(v261) = 1;
  v270[1] = 0;
  v275[1] = 0;
  v274[1] = 0;
  Mso::Telemetry::EventFlags::EventFlags(&v264, v274, v275, v270, &v261, &v258);
  Namespace = (struct IUnknown *)Office::FileIO::MSO::GetNamespace(v13);
  v269 = (__int16 *)"FCsiGetFile";
  Mso::Telemetry::Activity::Activity(
    (Mso::Telemetry::Activity *)v259,
    (const struct Mso::Telemetry::EventName *)&Namespace,
    (const struct Mso::Telemetry::EventFlags *)&v264);
  v14 = -1;
  if ( this )
  {
    Mso::DocumentTelemetry::FindDocumentTelemetryForDocument<CMsoOLDocFile,void>(&Namespace, this);
    if ( Namespace )
    {
      Mso::DocumentTelemetry::AddDocumentTelemetryToActivity<Mso::Telemetry::Activity>(&v261, v259, Namespace, -1);
      v15 = Namespace;
      if ( Namespace )
      {
        Namespace = 0;
        ((void (__fastcall *)(struct IUnknown *))v15->lpVtbl->Release)(v15);
      }
    }
  }
  v16 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v259);
  LOBYTE(v17) = v263;
  Mso::Telemetry::IDataFieldCollection::Add<unsigned char>(v16, "OpenFileState_Requested", v17);
  v18 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v259);
  FBlockNetworkCalls = CMsoOLDocBase::GetFBlockNetworkCalls(this);
  Mso::Telemetry::IDataFieldCollection::Add<int>(v18, "BlockNetworkCalls", FBlockNetworkCalls);
  v302 = &Mso::Diagnostics::ClassifiedStructuredObject<_GUID>::`vftable';
  *(_QWORD *)Destination = "DocumentUniqueId";
  *(_OWORD *)v304 = *((_OWORD *)this + 15);
  *(_WORD *)&v304[16] = 256;
  v305 = 0;
  v306 = 0;
  v307 = 7;
  v305.m128i_i16[0] = 0;
  v264 = "OLDoc:FCsiGetFile";
  Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
    594334803,
    836,
    50,
    v20,
    (__int64)&v264,
    (__int64)&v302);
  std::basic_string<char16_t>::~basic_string<char16_t>(&v305);
  v21 = *(_QWORD *)std::chrono::steady_clock::now(&v264);
  v313[0] = 0;
  v313[1] = v21;
  v314 = v21;
  v315 = 1;
  LOBYTE(v22) = 1;
  Measurements::MeasureElapsedTime::MeasureElapsedTime(v277, Measurements::MeasurementId::OLDocFCsiGetFile, v22, v313);
  *(_BYTE *)v272 = 0;
  if ( !*((_BYTE *)this + 1800) )
    goto LABEL_45;
  while ( 1 )
  {
    v321 = 1;
    v322 = 0;
    v323 = 0;
    v324 = 0;
    v325 = 0;
    v326 = 0;
    v327 = 0;
    CMsoOLDocFile::GetCsiServerInfo((CMsoOLDocFile *)v10, (struct Csi::CsiServerInfo *)&v321, 0, 0);
    v23 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v259);
    Mso::Telemetry::IDataFieldCollection::Add<int>(v23, "Protocol", HIDWORD(v322));
    v24 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v259);
    Mso::Telemetry::IDataFieldCollection::Add<int>(v24, "ServerType", (unsigned int)v322);
    v25 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v259);
    if ( (_DWORD)v322 == 5 )
    {
      v108 = HIBYTE(v325) == 0;
    }
    else
    {
      if ( (unsigned __int8)v324 > 1u || (_BYTE)v324 == 1 && BYTE1(v324) >= 3u )
        goto LABEL_15;
      if ( (_DWORD)v322 != 10 )
        goto LABEL_13;
      v108 = (v321 & 0x2000000000LL) == 0;
    }
    if ( v108 )
    {
LABEL_13:
      LOBYTE(v26) = 0;
      goto LABEL_16;
    }
LABEL_15:
    LOBYTE(v26) = 1;
LABEL_16:
    Mso::Telemetry::IDataFieldCollection::Add<bool>(v25, "CloudCollab", v26, 4);
    v27 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v259);
    LOBYTE(v28) = (_DWORD)v325 == 0;
    Mso::Telemetry::IDataFieldCollection::Add<bool>(v27, "IsWebUrlEmpty", v28, 4);
    if ( HIDWORD(v321) == 1 )
    {
      v263 = 6;
      v109 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v259);
      LOBYTE(v110) = v263;
      Mso::Telemetry::IDataFieldCollection::Add<unsigned char>(v109, "OpenFileState_LegacyFallback", v110);
      *((_DWORD *)this + 377) = 25236365;
      Mso::ReadOnlyReasonTracker::SetNonDownloadProtocolReadOnlyReason((char *)this + 1508, 34);
      v8 = 1;
      v254 = 1;
      v253 = 1;
    }
    v10 = (__int64)HwndParentForDmEx(0);
    v264 = (const char *)v10;
    v251 = 0;
    if ( !(unsigned int)CMsoOLDocFile::FInitCsiFile((char *)this + 1544, &v251, v263, &v321) )
    {
      if ( !Csi::IsFileOpenForEditTakenError(v251, v29) )
      {
        if ( Csi::IsExpectedEdpError(v251, v111) )
        {
          MsoCF::CIPtr<MsoCF::IError,MsoCF::IError>::CopyTo(&v251, v256);
          v88 = 22619107;
LABEL_97:
          Csi::SetActivityResultIErrorTag((Csi *)v259, *v256, (const struct MsoCF::IError *)v88, v30);
          goto LABEL_98;
        }
        if ( (unsigned __int8)Csi::IsCsiError(v251, 141) )
        {
          MsoCF::CIPtr<MsoCF::IError,MsoCF::IError>::CopyTo(&v251, v256);
          Csi::SetActivityResultIErrorTag((Csi *)v259, *v256, (const struct MsoCF::IError *)0x2336260A, v112);
          ShowStorageOutOfCapacityAlert();
          goto LABEL_98;
        }
        if ( (v321 & 0x1000000000LL) != 0 )
        {
          if ( (unsigned __int8)Csi::IsCsiError(v251, 3526)
            || Mso::ResourceInfo::IsWopiPromptingOnOpenEnabled(v113) && Csi::IsWopiAuthenticationError(v251, v114) )
          {
LABEL_156:
            v119 = v251;
            v251 = 0;
            if ( v119 )
              (*(void (__fastcall **)(Csi *))(*(_QWORD *)v119 + 16LL))(v119);
            Csi::CreateCsiErrorTag(5600, &v251, 541909526);
            MsoCF::CIPtr<MsoCF::IError,MsoCF::IError>::CopyTo(&v251, v256);
            Csi::SetActivityResultIErrorTag((Csi *)v259, *v256, (const struct MsoCF::IError *)0x204CE215, v120);
            v309 = 0;
            si128 = _mm_load_si128((const __m128i *)&_xmm);
            LOWORD(v309) = 0;
            v298 = 0;
            v299 = si128;
            LOWORD(v298) = 0;
            v311 = 0;
            v312 = si128;
            LOWORD(v311) = 0;
            *(_OWORD *)S1 = 0;
            v296 = 0;
            v297 = 7;
            LOWORD(S1[0]) = 0;
            LOBYTE(v249) = 0;
            if ( (unsigned int)Mso::Url::ExtractAllWopiPropertiesFromWopiUrl(
                                 *((_QWORD *)this + 36),
                                 &v309,
                                 &v298,
                                 &v311,
                                 S1,
                                 v249) )
            {
              v149 = (const OLECHAR *)*((_QWORD *)this + 36);
              Mso::Alerts::CreateDefaultAlertParam(v328);
              v150 = &WindowName;
              if ( v149 )
                v150 = v149;
              v264 = (const char *)v150;
              do
                ++v14;
              while ( v150[v14] );
              v265 = (void ***)v14;
              Namespace = (struct IUnknown *)&v264;
              v269 = &v266;
              AlertMessageFromMsoIds = Mso::Alerts::GetAlertMessageFromMsoIds(&v302, 38601128, &Namespace);
              Mso::Alerts::AlertMessage::operator=(v329, AlertMessageFromMsoIds);
              Mso::Help::Core::AuthInfo::~AuthInfo((Mso::Help::Core::AuthInfo *)&v302);
              v330 = 3;
              TelemetryNamespace = Mso::Alerts::GetTelemetryNamespace(v141);
              LODWORD(v261) = 509354626;
              Mso::Alerts::ShowAlert(
                (Mso::Alerts *)&v261,
                TelemetryNamespace,
                (const struct Mso::Telemetry::TelemetryNamespace *)v328,
                v143);
              std::pair<std::wstring const,Mso::History::FileInfo>::~pair<std::wstring const,Mso::History::FileInfo>(v328);
            }
            else
            {
              Instance = Mso::OfficeServicesManager::GetInstance(v121);
              v123 = Instance;
              if ( !Instance )
              {
                CrashWithRecovery(0x204CE214u, 0);
                __debugbreak();
              }
              v124 = *(_QWORD *)Instance;
              v125 = &v298;
              if ( v299.m128i_i64[1] > 7uLL )
                v125 = (__int128 *)v298;
              (*(void (__fastcall **)(struct Mso::OfficeServicesManager::IOfficeServicesManager *, WCHAR **, __int128 *))(v124 + 8))(
                v123,
                &v272,
                v125);
              if ( v272 )
              {
                v132 = Mso::TCntPtr<Mso::Sharing::SharingResult<Mso::Sharing::MsoGetUserAttributesResponse>>::operator->(&v272);
                v133 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v132 + 128LL))(v132);
                Mso::Alerts::CreateDefaultAlertParam(v291);
                v134 = S1;
                if ( v297 > 7 )
                  v134 = (wchar_t **)S1[0];
                *(_QWORD *)&v300 = v134;
                *((_QWORD *)&v300 + 1) = v296;
                v135 = &WindowName;
                if ( v133 )
                  v135 = (const OLECHAR *)v133;
                v301.m128i_i64[0] = (__int64)v135;
                do
                  ++v14;
                while ( v135[v14] );
                v301.m128i_i64[1] = v14;
                v264 = (const char *)&v300;
                v265 = &v302;
                v136 = Mso::Alerts::GetAlertMessageFromMsoIds(&v302, 39819150, &v264);
                Mso::Alerts::AlertMessage::operator=(v292, v136);
                Mso::Help::Core::AuthInfo::~AuthInfo((Mso::Help::Core::AuthInfo *)&v302);
                v293 = 1;
                v294 = v10;
                v138 = Mso::Alerts::GetTelemetryNamespace(v137);
                LODWORD(v261) = 509354628;
                Mso::Alerts::ShowAlert(
                  (Mso::Alerts *)&v261,
                  v138,
                  (const struct Mso::Telemetry::TelemetryNamespace *)v291,
                  v139);
                v131 = v291;
              }
              else
              {
                Mso::Alerts::CreateDefaultAlertParam(v278);
                v126 = S1;
                if ( v297 > 7 )
                  v126 = (wchar_t **)S1[0];
                v264 = (const char *)v126;
                v265 = (void ***)v296;
                Namespace = (struct IUnknown *)&v264;
                v269 = &v266;
                v127 = Mso::Alerts::GetAlertMessageFromMsoIds(&v302, 3391383533LL, &Namespace);
                Mso::Alerts::AlertMessage::operator=(v279, v127);
                Mso::Help::Core::AuthInfo::~AuthInfo((Mso::Help::Core::AuthInfo *)&v302);
                v289 = 1;
                v290 = v10;
                v129 = Mso::Alerts::GetTelemetryNamespace(v128);
                LODWORD(v261) = 509354627;
                Mso::Alerts::ShowAlert(
                  (Mso::Alerts *)&v261,
                  v129,
                  (const struct Mso::Telemetry::TelemetryNamespace *)v278,
                  v130);
                v131 = v278;
              }
              std::pair<std::wstring const,Mso::History::FileInfo>::~pair<std::wstring const,Mso::History::FileInfo>(v131);
              Mso::TCntPtr<Mso::IMsoDocEnterpriseProtection>::Clear(&v272);
            }
            std::basic_string<char16_t>::~basic_string<char16_t>(S1);
            std::basic_string<char16_t>::~basic_string<char16_t>(&v311);
            std::basic_string<char16_t>::~basic_string<char16_t>(&v298);
            v144 = &v309;
            goto LABEL_177;
          }
          if ( (v321 & 0x1000000000LL) != 0 && (unsigned __int8)Csi::IsCsiError(v251, 5630) )
          {
            MsoCF::CIPtr<MsoCF::IError,MsoCF::IError>::CopyTo(&v251, v256);
            Csi::SetActivityResultIErrorTag((Csi *)v259, *v256, (const struct MsoCF::IError *)0x1E24D682, v115);
            v298 = 0;
            v299 = _mm_load_si128((const __m128i *)&_xmm);
            LOWORD(v298) = 0;
            v300 = 0;
            v301 = v299;
            LOWORD(v300) = 0;
            v309 = 0;
            si128 = v299;
            LOWORD(v309) = 0;
            v311 = 0;
            v312 = v299;
            LOWORD(v311) = 0;
            LOBYTE(v249) = 0;
            if ( (unsigned int)Mso::Url::ExtractAllWopiPropertiesFromWopiUrl(
                                 *((_QWORD *)this + 36),
                                 &v298,
                                 &v300,
                                 &v309,
                                 &v311,
                                 v249) )
              goto LABEL_187;
            v117 = Mso::OfficeServicesManager::GetInstance(v116);
            v118 = v117;
            if ( !v117 )
            {
              CrashWithRecovery(0x1E24D681u, 0);
              goto LABEL_156;
            }
            v151 = *(_QWORD *)v117;
            v152 = &v300;
            if ( v301.m128i_i64[1] > 7uLL )
              v152 = (__int128 *)v300;
            (*(void (__fastcall **)(struct Mso::OfficeServicesManager::IOfficeServicesManager *, WCHAR **, __int128 *))(v151 + 8))(
              v118,
              &v272,
              v152);
            if ( v272 )
            {
              v159 = Mso::TCntPtr<Mso::Sharing::SharingResult<Mso::Sharing::MsoGetUserAttributesResponse>>::operator->(&v272);
              v160 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v159 + 128LL))(v159);
              Mso::Alerts::CreateDefaultAlertParam(v291);
              v161 = &WindowName;
              if ( v160 )
                v161 = (const OLECHAR *)v160;
              v264 = (const char *)v161;
              do
                ++v14;
              while ( v161[v14] );
              v265 = (void ***)v14;
              Namespace = (struct IUnknown *)&v264;
              v269 = &v266;
              v145 = Mso::Alerts::GetAlertMessageFromMsoIds(&v302, 3713772944LL, &Namespace);
              Mso::Alerts::AlertMessage::operator=(v292, v145);
              Mso::Help::Core::AuthInfo::~AuthInfo((Mso::Help::Core::AuthInfo *)&v302);
              v293 = 1;
              v294 = v10;
              v147 = Mso::Alerts::GetTelemetryNamespace(v146);
              LODWORD(v261) = 505730688;
              Mso::Alerts::ShowAlert(
                (Mso::Alerts *)&v261,
                v147,
                (const struct Mso::Telemetry::TelemetryNamespace *)v291,
                v148);
              std::pair<std::wstring const,Mso::History::FileInfo>::~pair<std::wstring const,Mso::History::FileInfo>(v291);
              Mso::TCntPtr<Mso::IMsoDocEnterpriseProtection>::Clear(&v272);
            }
            else
            {
              Mso::TCntPtr<Mso::IMsoDocEnterpriseProtection>::Clear(&v272);
LABEL_187:
              v153 = (const OLECHAR *)*((_QWORD *)this + 36);
              Mso::Alerts::CreateDefaultAlertParam(v328);
              v154 = &WindowName;
              if ( v153 )
                v154 = v153;
              v264 = (const char *)v154;
              do
                ++v14;
              while ( v154[v14] );
              v265 = (void ***)v14;
              Namespace = (struct IUnknown *)&v264;
              v269 = &v266;
              v155 = Mso::Alerts::GetAlertMessageFromMsoIds(&v302, 38601128, &Namespace);
              Mso::Alerts::AlertMessage::operator=(v329, v155);
              Mso::Help::Core::AuthInfo::~AuthInfo((Mso::Help::Core::AuthInfo *)&v302);
              v330 = 3;
              v157 = Mso::Alerts::GetTelemetryNamespace(v156);
              LODWORD(v261) = 505730659;
              Mso::Alerts::ShowAlert(
                (Mso::Alerts *)&v261,
                v157,
                (const struct Mso::Telemetry::TelemetryNamespace *)v328,
                v158);
              std::pair<std::wstring const,Mso::History::FileInfo>::~pair<std::wstring const,Mso::History::FileInfo>(v328);
            }
            std::basic_string<char16_t>::~basic_string<char16_t>(&v311);
            std::basic_string<char16_t>::~basic_string<char16_t>(&v309);
            std::basic_string<char16_t>::~basic_string<char16_t>(&v300);
            v144 = &v298;
LABEL_177:
            std::basic_string<char16_t>::~basic_string<char16_t>(v144);
            goto LABEL_98;
          }
        }
        if ( (unsigned __int8)Csi::IsCsiError(v251, 1930) )
        {
          MsoCF::CIPtr<MsoCF::IError,MsoCF::IError>::CopyTo(&v251, v256);
          v88 = 537190478;
        }
        else if ( (unsigned __int8)Csi::IsCsiError(v251, 7209) )
        {
          MsoCF::CIPtr<MsoCF::IError,MsoCF::IError>::CopyTo(&v251, v256);
          v88 = 526513741;
        }
        else
        {
          MsoShipAssertTagProc(22619136, v162, v163, v164);
          MsoCF::CIPtr<MsoCF::IError,MsoCF::IError>::CopyTo(&v251, v256);
          v88 = 22619137;
        }
        goto LABEL_97;
      }
      if ( !CMsoOLDocFile::TryFallbackToReadOnly(
              this,
              &v251,
              (enum CAOpenFileState *)&v263,
              (const struct Csi::CsiServerInfo *)&v321) )
      {
        if ( !v251 )
        {
          CrashWithRecovery(0x20507C6u, 0);
          __debugbreak();
        }
        MsoCF::CIPtr<MsoCF::IError,MsoCF::IError>::CopyTo(&v251, v256);
        v88 = 22619106;
        goto LABEL_97;
      }
      v8 = 1;
      v254 = 1;
      v253 = 1;
      CMsoOLDocBase::SetReadOnly(this, 25236366, 35);
      CMsoOLDocBase::SetAttrInAttrMask(this, 0, 0x4000u);
    }
    if ( CMsoOLDocBase::IsCachedAsDistributedBlobsFile(this) )
    {
      Csi::CreateCsiErrorTag(2073, v256, 508072783);
      v88 = 524301536;
      goto LABEL_97;
    }
    LODWORD(v261) = 505448525;
    if ( !(unsigned __int8)CMsoOLDocFile::UpdateReadWriteMode(this, &v261, v263, v256) )
    {
      v88 = 22619138;
      goto LABEL_97;
    }
    CMsoOLDocBase::SetIsOpeningOfflineCopy(this, 0);
    CMsoUrlSimple::CMsoUrlSimple((CMsoUrlSimple *)v319);
    v7 = v256;
    v31 = CMsoUrlSimple::HrSetFromUser(v320, *((_QWORD *)this + 36), 0, 0, 0);
    if ( v31 < 0 )
    {
      if ( v7 )
        MsoCF::CreateHRESULTError((MsoCF *)(unsigned int)v31, (_DWORD)v7, v32);
      Mso::Telemetry::SetActivityResultHr(
        (Mso::Telemetry *)v259,
        (struct Mso::Telemetry::Activity *)0x804D000ELL,
        41947792,
        v33);
      CMsoUrlSimple::~CMsoUrlSimple((CMsoUrlSimple *)v319);
LABEL_98:
      if ( v251 )
        (*(void (__fastcall **)(Csi *))(*(_QWORD *)v251 + 16LL))(v251);
LABEL_47:
      Measurements::MeasureElapsedTime::~MeasureElapsedTime((Measurements::MeasureElapsedTime *)v277);
      Mso::Telemetry::Activity::~Activity((Mso::Telemetry::Activity *)v259);
      return 0;
    }
    v257 = 0;
    LODWORD(v261) = 560567331;
    CMsoOLDocBase::GetProperties(this, &v257, (const struct MsoReserveTag *)&v261);
    v34 = v257;
    if ( !v257 )
      goto LABEL_23;
    (*(void (__fastcall **)(struct Csi::IDocumentProperties *, _QWORD))(*(_QWORD *)v257 + 224LL))(
      v257,
      *((unsigned int *)this + 336));
    if ( Mso::TitleBarSaveUi::AutoSaveAppSettingApi::IsAutoSaveDisabledByGroupPolicy() )
    {
      v54 = (struct Csi::IDocumentProperties *)Mso::TCntPtr<Mso::Sharing::SharingResult<Mso::Sharing::MsoGetUserAttributesResponse>>::operator->(&v257);
      v165 = *(_QWORD *)v54;
      v53 = 0;
      v166 = 589882179;
LABEL_208:
      (*(void (__fastcall **)(struct Csi::IDocumentProperties *, __int64, __int64))(v165 + 352))(v54, v166, v53);
      goto LABEL_131;
    }
    if ( *((_BYTE *)this + 1348) )
    {
      v54 = v257;
      if ( !v257 )
      {
        CrashWithRecovery(0x1E3C3840u, 0);
        goto LABEL_42;
      }
      v165 = *(_QWORD *)v257;
      LOBYTE(v53) = 1;
      v166 = 39171597;
      goto LABEL_208;
    }
LABEL_131:
    if ( !v257 )
    {
      CrashWithRecovery(0x1E3C3840u, 0);
LABEL_133:
      if ( CMsoOLDocFile::IsCobaltVersion((CMsoOLDocFile *)v10) )
        goto LABEL_2;
      v263 = ((_BYTE)v7 != 0) + 1;
      goto LABEL_3;
    }
    LOBYTE(v53) = *((_BYTE *)this + 1349);
    (*(void (__fastcall **)(struct Csi::IDocumentProperties *, __int64, __int64))(*(_QWORD *)v257 + 456LL))(
      v257,
      571802018,
      v53);
LABEL_23:
    v255 = !Mso::NetCost::FNetworkExists(v34);
    v252 = (unsigned int)sub_180A9FD48(*((_QWORD *)this + 36)) != 0;
    IsFileCached = CMsoOLDocFile::IsFileCached((char *)this + 1568, 559257443);
    LOBYTE(v258) = IsFileCached;
    v36 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v259);
    v10 = 4;
    LOBYTE(v37) = v252;
    Mso::Telemetry::IDataFieldCollection::Add<bool>(v36, "recoveryMode", v37, 4);
    v38 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v259);
    LOBYTE(v39) = IsFileCached;
    Mso::Telemetry::IDataFieldCollection::Add<bool>(v38, "isFileCachedBeforeOpen", v39, 4);
    v40 = v252;
    if ( v252 && !IsFileCached )
    {
      v252 = 0;
      v167 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v259);
      LOBYTE(v168) = v252;
      Mso::Telemetry::IDataFieldCollection::Add<bool>(v167, "updatedRecoveryMode", v168, 4);
      v40 = v252;
    }
    if ( v255 || (v108 = !v40, v41 = 1, !v108) )
      v41 = 0;
    v250 = v41;
    v42 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v259);
    LOBYTE(v43) = v250;
    Mso::Telemetry::IDataFieldCollection::Add<bool>(v42, "AsyncDownload", v43, 4);
    v44 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v259);
    LOBYTE(v45) = v255;
    Mso::Telemetry::IDataFieldCollection::Add<bool>(v44, "OpenOffline", v45, 4);
    v47 = (wchar_t *)L"true";
    if ( !v250 )
      v47 = (wchar_t *)L"false";
    Namespace = (struct IUnknown *)v47;
    Mso::Logging::MsoSendTraceTag<wchar_t const *>(
      24162526,
      677,
      50,
      v46,
      (__int64)L"CMsoOLDocFile::FCsiGetFile: fAsyncDownload = %s",
      &Namespace);
    *((_QWORD *)this + 226) = 0;
    v267 = 0;
    if ( (int)CMsoOLDocBase::COpenGet(this) <= 0 )
    {
      v270[0] = 0;
      Namespace = (struct IUnknown *)"IsDBF";
      v49 = Mso::Telemetry::DataField<bool>::DataField<bool>(&v302, &Namespace, v270, 4);
      Namespace = (struct IUnknown *)"DocumentUniqueId";
      v10 = Mso::Telemetry::DataField<_GUID>::DataField<_GUID>(v316, &Namespace, (char *)this + 240, 256);
      v50 = Mso::Telemetry::EventFlags::EventFlags(v276, 2);
      Namespace = (struct IUnknown *)"CsiCacheFileSessionBegunWithClosedFile";
      v51 = Office::FileIO::MSO::EventName(&v261, &Namespace);
      Mso::Telemetry::SendTelemetryEvent<Mso::Telemetry::DataField<_GUID>,Mso::Telemetry::DataField<bool>>(
        v51,
        v50,
        v10,
        v49);
      IsFileCached = v258;
      v8 = v254;
    }
    v271 = v255;
    v302 = (void **)this;
    *(_QWORD *)Destination = &v255;
    *(_QWORD *)v304 = &v252;
    *(_QWORD *)&v304[8] = &a5;
    *(_QWORD *)&v304[16] = &v263;
    v305.m128i_i64[0] = (__int64)&v271;
    v305.m128i_i64[1] = (__int64)&v250;
    v306 = &v251;
    v307 = (__int64)&v267;
    LOBYTE(v10) = sub_1809F47E0((char *)this + 1088, &v302, v48, 558404548);
    LOBYTE(v258) = v10;
    if ( v250 )
    {
      if ( IsFileCached )
      {
        Namespace = 0;
        if ( (int)CMsoOLDocFile::HrGetLastFileModifiedTime((char *)this + 1568, &Namespace, 559257441) >= 0 )
          *((_QWORD *)this + 87) = Namespace;
      }
    }
    if ( byte_1822A24B8 < 0 )
      v52 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_1822A24B8);
    else
      v52 = byte_1822A24B8 != 0;
    if ( v52 )
    {
      if ( !v250 )
      {
LABEL_35:
        if ( *((_DWORD *)this + 268) == 2 )
          CMsoOLDocFile::UpdateSyncBackedPropertiesFromIDocument(this);
        goto LABEL_43;
      }
      if ( !(_BYTE)v10 || !v267 )
      {
        v250 = 0;
LABEL_224:
        v170 = (Csi *)*((_QWORD *)this + 231);
        if ( v170 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v170 + 8LL))(*((_QWORD *)this + 231));
        v171 = v251;
        v108 = v251 == 0;
        v251 = v170;
        if ( !v108 )
          (*(void (__fastcall **)(Csi *))(*(_QWORD *)v171 + 16LL))(v171);
      }
LABEL_42:
      if ( v250 )
        goto LABEL_43;
      goto LABEL_35;
    }
    if ( !(_BYTE)v10 || (v169 = 1, !v267) )
      v169 = 0;
    v250 = v169;
    if ( !v169 )
      goto LABEL_224;
LABEL_43:
    if ( v257 )
      break;
    CrashWithRecovery(0x1E3C3840u, 0);
LABEL_45:
    if ( !(unsigned int)CMsoOLDocFile::FInitCsiFileIO((CMsoOLDocFile *)v10, v256) )
    {
      Csi::SetActivityResultIErrorTag((Csi *)v259, *v256, (const struct MsoCF::IError *)0x15923E1, v55);
      goto LABEL_47;
    }
  }
  (*(void (__fastcall **)(struct Csi::IDocumentProperties *, struct IUnknown **))(*(_QWORD *)v257 + 344LL))(
    v257,
    &Namespace);
  if ( BYTE4(Namespace) )
  {
    v172 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v259);
    v173 = (unsigned int *)std::_Optional_construct_base<enum Mso::DocumentTelemetry::DocumentLocationDetails>::operator*(&Namespace);
    Mso::Telemetry::IDataFieldCollection::Add<unsigned int>(v172, "AsyncOpenKind", *v173);
  }
  if ( (_BYTE)v10 )
  {
    CMsoOLDocFile::PrepareToShowSyncProgressUI(this, v8, v250, v257);
    if ( !v250 )
    {
      *((_BYTE *)this + 1882) = 0;
      goto LABEL_105;
    }
    v100 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v259);
    FileFromCacheMetaData = Office::FileIO::MSO::CsiGetFileFromCacheMetaData::CsiGetFileFromCacheMetaData(
                              (Office::FileIO::MSO::CsiGetFileFromCacheMetaData *)v316,
                              v101);
    v302 = &Mso::Telemetry::DataContractField::`vftable';
    v308 = FileFromCacheMetaData;
    strncpy_s(Destination, 0x41u, "CsiGetFileFromCacheMetaData", 0xFFFFFFFFFFFFFFFFuLL);
    Mso::Telemetry::IDataFieldCollection::Add(v100, (const struct Mso::Telemetry::ISingleDataField *)&v302);
    if ( *((_QWORD *)this + 231) && (unsigned __int8)Csi::IsCsiError(*((_QWORD *)this + 231), 4790) )
    {
      v71 = (struct MsoCF::IError *)Mso::TCntPtr<IMsoXmlSchema>::Copy((char *)this + 1848);
      *v256 = v71;
      v70 = 554771713;
      goto LABEL_58;
    }
    v104 = CMsoOLDocumentAsyncDownloadParams::CreateInstance(v255, v252, v103, v260);
    Namespace = 0;
    if ( (**(int (__fastcall ***)(__int64, GUID *, struct IUnknown **))v267)(v267, &IID_IUnknown, &Namespace) >= 0 )
    {
      CMsoOLDocFile::HrEnsureDownloadTask(this, Namespace, v104, 0);
    }
    else
    {
      v105 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v259);
      LOBYTE(v106) = 1;
      Mso::Telemetry::IDataFieldCollection::Add<bool>(v105, "HrEnsureDownloadTaskDidNotRun", v106, 4);
      *((_BYTE *)this + 1882) = 0;
    }
    v107 = Namespace;
    if ( Namespace )
    {
      Namespace = 0;
      ((void (__fastcall *)(struct IUnknown *))v107->lpVtbl->Release)(v107);
    }
    if ( v104 )
      (*(void (__fastcall **)(struct IMsoOLDocumentAsyncDownloadParams *))(*(_QWORD *)v104 + 16LL))(v104);
  }
LABEL_105:
  v89 = *((_QWORD *)this + 36);
  *(_OWORD *)S1 = 0;
  v296 = 0;
  v297 = 0;
  v90 = -1;
  do
    ++v90;
  while ( *(_WORD *)(v89 + 2 * v90) );
  std::basic_string<char16_t>::_Construct<1,char16_t const *>(S1, v89, v90);
  v92 = S1;
  v93 = S1[0];
  v94 = v297;
  if ( v297 > 7 )
    v92 = (wchar_t **)S1[0];
  appended = std::_Fnv1a_append_bytes(v91, (const unsigned __int8 *const)v92, 2 * v296);
  v276[0] = appended;
  v96 = 2 * (appended & qword_18228B8C0);
  v58 = *(const char **)(qword_18228B8A8 + 16 * (appended & qword_18228B8C0) + 8);
  if ( v58 == (const char *)qword_18228B898 )
  {
LABEL_49:
    v58 = 0;
    goto LABEL_50;
  }
  v97 = *(const char **)(qword_18228B8A8 + 16 * (appended & qword_18228B8C0));
  v261 = *(const char **)(qword_18228B8A8 + 8 * v96);
  while ( 2 )
  {
    v98 = (const wchar_t *)(v58 + 16);
    if ( *((_QWORD *)v58 + 5) > 7u )
      v98 = *(const wchar_t **)v98;
    v99 = S1;
    if ( v94 > 7 )
      v99 = (wchar_t **)v93;
    if ( v95 != *((_QWORD *)v58 + 4) )
    {
LABEL_119:
      if ( v58 == v97 )
      {
        appended = v276[0];
        goto LABEL_49;
      }
      v58 = (const char *)*((_QWORD *)v58 + 1);
      continue;
    }
    break;
  }
  if ( v95 && wmemcmp((const wchar_t *)v99, v98, v95) )
  {
    v94 = v297;
    v95 = v296;
    v93 = S1[0];
    v97 = v261;
    goto LABEL_119;
  }
  appended = v276[0];
LABEL_50:
  if ( v58 )
  {
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Erase_bucket(
      &Mso::OLDocumentApi::NetworkToggler::s_synchronousOpenURLs,
      v58,
      appended & qword_18228B8C0);
    std::list<std::wstring>::_Unchecked_erase(&qword_18228B898);
  }
  std::basic_string<char16_t>::_Tidy_deallocate(S1);
  CMsoOLDocBase::DoUpdateServerReachability(this, (const struct IMsoUrl *)v320);
  if ( v250 )
  {
LABEL_53:
    v62 = v253;
    goto LABEL_54;
  }
  if ( (_BYTE)v258 )
  {
    if ( v255 )
    {
      v174 = 1601;
    }
    else
    {
      if ( !v252 )
      {
        *((_DWORD *)this + 244) = *((_DWORD *)this + 244) & 0xFFFFFFEF | (16 * !v260);
        goto LABEL_236;
      }
      v174 = 1530;
    }
    Csi::CreateCsiError(v174, &v251);
LABEL_236:
    v73 = v251;
    goto LABEL_68;
  }
  v73 = v251;
  if ( !v251 )
  {
    MsoShipAssertTagProc(22619144, v59, v60, v61);
    goto LABEL_236;
  }
LABEL_68:
  if ( (v263 & 4) != 0 && !v254 )
  {
    v254 = 1;
    v253 = 1;
    *((_DWORD *)this + 377) = 25236367;
  }
  if ( !v73 )
  {
    Mso::TCntPtr<Mso::DocumentActivities::Common::TaskReassignment>::Clear((char *)this + 1848);
    goto LABEL_53;
  }
  v74 = v256;
  if ( v256 )
  {
    (*(void (__fastcall **)(Csi *))(*(_QWORD *)v73 + 8LL))(v73);
    *v74 = v73;
    v73 = v251;
  }
  if ( (unsigned __int8)Csi::IsCsiError(v73, 2007) )
  {
    if ( (CMsoOLDocBase::AttrGet(this) & 0x20000) != 0 || (*((_BYTE *)this + 516) & 4) != 0 )
    {
      v175 = MsoLocLibraryFromAlias(0xF902F7ED);
      MsoFLoadWz(v175, 1508070867, v328, 512);
      Mso::Alerts::CreateDefaultAlertParam(v278);
      v176 = -1;
      do
        ++v176;
      while ( v328[v176] );
      std::wstring::assign(v279);
      do
        ++v14;
      while ( v328[v14] );
      std::wstring::assign(v280);
      AlertIdFromMsoIds = Mso::Alerts::GetAlertIdFromMsoIds((Mso::Alerts *)0x59E355D3, v177);
      v282 = 1;
      v283 = *(_WORD *)((char *)&v264 + 5);
      v284 = HIBYTE(v264);
      WatsonAlertIdFromMsoIds = Mso::Alerts::GetWatsonAlertIdFromMsoIds((Mso::Alerts *)0x59E355D3, v178);
      v286 = 1;
      v287 = *(_WORD *)((char *)&v264 + 5);
      v288 = HIBYTE(v264);
      v289 = 3;
      v180 = Mso::Alerts::GetTelemetryNamespace(v179);
      LODWORD(v261) = 509354625;
      Mso::Alerts::ShowAlert((Mso::Alerts *)&v261, v180, (const struct Mso::Telemetry::TelemetryNamespace *)v278, v181);
      std::pair<std::wstring const,Mso::History::FileInfo>::~pair<std::wstring const,Mso::History::FileInfo>(v278);
    }
    v70 = 22619145;
    v71 = *v256;
    goto LABEL_58;
  }
  if ( (unsigned __int8)Csi::IsCsiError(v251, 1515) )
  {
    v70 = 22619146;
    v71 = v251;
    goto LABEL_58;
  }
  if ( (v321 & 0x2000000000LL) == 0 || !Csi::IsWopiAuthenticationError(v251, v75) )
  {
    if ( !(unsigned __int8)CMsoOLDocFile::IsFileCached((char *)this + 1568, 559257440) )
    {
      if ( (_BYTE)v266 && Csi::IsInAppDownloadAuthenticationError(v251, v219) || (unsigned __int8)sub_1810DAC94(v251) )
        v11 = 0;
      v233 = v272;
      *(_BYTE *)v272 = v11;
      v234 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v259);
      LOBYTE(v235) = *(_BYTE *)v233;
      Mso::Telemetry::IDataFieldCollection::Add<bool>(v234, "AllowFallbackOnFailure", v235, 4);
      if ( (unsigned __int8)Csi::IsCsiError(v251, 4705) )
      {
        Csi::CreateCsiErrorTag(4788, &v251, 38073427);
        MsoCF::CIPtr<MsoCF::IError,MsoCF::IError>::CopyTo(&v251, v256);
      }
      v227 = 22619150;
      goto LABEL_302;
    }
    if ( (unsigned __int8)Csi::IsCsiError(v251, 4710) )
    {
      v62 = 1;
      v63 = 1;
      *((_DWORD *)this + 377) = 25236368;
LABEL_55:
      v64 = v251;
      LOBYTE(v248) = v263 == 6;
      LOBYTE(v65) = sub_1804D906C((char *)this + 1088, v59, v60, 560567328);
      LOBYTE(v66) = v250;
      if ( (unsigned int)Mso::ClpIncapableUX::OnGetFileComplete((char *)this + 1544, v257, v66, v65, v248, v64) != 1 )
      {
        Controller = (__int64 *)Mso::PerpetualRedirectUX::TryMakeController(&v264, (char *)this + 1544);
        v77 = *Controller;
        *Controller = 0;
        v78 = *((_QWORD *)this + 192);
        *((_QWORD *)this + 192) = v77;
        if ( v78 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 8LL))(v78);
        v79 = v264;
        if ( v264 )
        {
          v264 = 0;
          (*(void (__fastcall **)(const char *))(*(_QWORD *)v79 + 8LL))(v79);
        }
        CMsoOLDocBase::SetAttr2InAttr2Mask(this, 0x400u, 0x400u);
        CMsoOLDocFile::SetStreamAvailableMask(this);
        CodeMarker(3139);
        FileName[0] = 0;
        v80 = CMsoOLDocFile::FIsStreamAvailable(this);
        v81 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v259);
        LOBYTE(v82) = v80 != 0;
        Mso::Telemetry::IDataFieldCollection::Add<bool>(v81, "UseStream", v82, 4);
        if ( !v80 )
        {
          if ( !(unsigned int)CMsoOLDocFile::FGenerateTempFile(this, FileName, 260, *((const wchar_t **)this + 36)) )
          {
            Mso::Telemetry::SetActivityResultHr(
              (Mso::Telemetry *)v259,
              (struct Mso::Telemetry::Activity *)0x804D0017LL,
              41947793,
              v87);
            goto LABEL_59;
          }
          v264 = 0;
          if ( (unsigned int)CMsoOLDocBase::GetSyncBackedType(this) != 1 )
          {
            v272 = FileName;
            v273 = &v256;
            if ( (unsigned __int8)sub_1810D78F0((char *)this + 1088, &v272, v237, 558404547) )
            {
              Csi::SetActivityResultIErrorTag((Csi *)v259, *v256, (const struct MsoCF::IError *)0x1592410, v238);
              Mso::TCntPtr<Mso::DocumentActivities::Common::TaskReassignment>::Clear(&v264);
              goto LABEL_282;
            }
          }
          v239 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v259);
          LOBYTE(v240) = 1;
          Mso::Telemetry::IDataFieldCollection::Add<bool>(v239, "TempFileGenerated", v240, 4);
          if ( CMsoOLDocFile::IsCobaltVersion((CMsoOLDocFile *)((char *)this + 1544)) )
          {
            v241 = Mso::TCntPtr<Mso::Sharing::SharingResult<Mso::Sharing::MsoGetUserAttributesResponse>>::operator->((char *)this + 1928);
            v242 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v241 + 48LL))(v241);
            if ( (int)MsoHrSetLocalSavedVersion(v242, FileName) < 0 )
              MsoShipAssertTagProc(22619153, v243, v244, v245);
          }
          Mso::TCntPtr<Mso::DocumentActivities::Common::TaskReassignment>::Clear(&v264);
        }
        CodeMarker(3140);
        if ( v80 )
        {
          CMsoOLDocBase::Lock(this, 0);
          std::pair<Mso::MemoryPtr<unsigned char,0>,unsigned __int64>::~pair<Mso::MemoryPtr<unsigned char,0>,unsigned __int64>((char *)this + 296);
          if ( *((_DWORD *)this + 161) )
          {
            v108 = (*((_DWORD *)this + 164))-- == 1;
            if ( v108 )
            {
              *((_DWORD *)this + 165) = 0;
              SetEvent(*((HANDLE *)this + 81));
            }
          }
        }
        else
        {
          CMsoOLDocBase::SetWzI(this, FileName, 4);
          if ( (unsigned int)CMsoOLDocBase::GetSyncBackedType(this) != 1 )
            CMsoOLDocBase::SetAttrInAttrMask(this, 0x10000u, 0x10000u);
        }
        if ( !v250 && v63 )
        {
          if ( *((_DWORD *)this + 152) == 2 )
          {
            LODWORD(v261) = -2147467259;
            v246 = CMsoOLDocBase::FIsOpen(this);
            *((_DWORD *)this + 254) = 1;
            CMsoOLDocBaseImpIOLDoc2::RecordEvent((CMsoOLDocFile *)((char *)this + 1544), 0x40000000u, &v261, 0);
            CMsoOLDocBaseImpIOLDoc2::BeginCmd((CMsoOLDocFile *)((char *)this + 1544), 4u, 0);
            if ( v246 )
              CMsoOLDocBase::SetReadOnly(this, 25236371, 0);
            *((_DWORD *)this + 254) = 0;
          }
          else
          {
            CMsoOLDocBase::SetReadOnly(this, 25236372, 0);
          }
        }
        if ( v80 )
        {
          CMsoOLDocBase::SetAttr2InAttr2Mask(this, v62 != 0 ? 0x80000 : 0, 0x80000u);
        }
        else if ( v62 && !(unsigned int)CMsoOLDocBase::GetSyncBackedType(this) )
        {
          FileAttributesW = GetFileAttributesW(FileName);
          SetFileAttributesW(FileName, FileAttributesW | 1);
        }
        LOBYTE(v83) = 1;
        MsoServerInfoUtils::SetEnableBHO((MsoServerInfoUtils *)v320, v83, v84);
        v266 = 257;
        v85 = (__int16 *)Mso::Telemetry::Activity::Success(v259);
        *v85 = v266;
        if ( v267 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v267 + 16LL))(v267);
        v86 = v257;
        if ( v257 )
        {
          v257 = 0;
          (*(void (__fastcall **)(struct Csi::IDocumentProperties *))(*(_QWORD *)v86 + 16LL))(v86);
        }
        CMsoUrlSimple::~CMsoUrlSimple((CMsoUrlSimple *)v319);
        if ( v251 )
          (*(void (__fastcall **)(Csi *))(*(_QWORD *)v251 + 16LL))(v251);
        Measurements::MeasureElapsedTime::~MeasureElapsedTime((Measurements::MeasureElapsedTime *)v277);
        Mso::Telemetry::Activity::~Activity((Mso::Telemetry::Activity *)v259);
        return 1;
      }
      Mso::TCntPtr<Mso::DocumentActivities::Common::TaskReassignment>::Clear((char *)this + 1848);
      MsoCF::CreateHRESULTErrorTag((MsoCF *)0x804D000CLL, (_DWORD)this + 1848, (struct MsoCF::IError **)0x2205D0D5, v67);
      v68 = Mso::TCntPtr<Mso::Sharing::SharingResult<Mso::Sharing::MsoGetUserAttributesResponse>>::operator->((char *)this + 1848);
      (*(void (__fastcall **)(__int64, Csi *))(*(_QWORD *)v68 + 32LL))(v68, v251);
      if ( v256 )
      {
        if ( *v256 )
          (*(void (__fastcall **)(struct MsoCF::IError *))(*(_QWORD *)*v256 + 16LL))(*v256);
        v236 = (struct MsoCF::IError *)Mso::TCntPtr<IMsoXmlSchema>::Copy((char *)this + 1848);
        *v256 = v236;
      }
      v70 = 570806484;
      v71 = (struct MsoCF::IError *)*((_QWORD *)this + 231);
LABEL_58:
      Csi::SetActivityResultIErrorTag((Csi *)v259, v71, (const struct MsoCF::IError *)v70, v69);
LABEL_59:
      if ( v267 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v267 + 16LL))(v267);
      v72 = v257;
      if ( v257 )
      {
        v257 = 0;
        (*(void (__fastcall **)(struct Csi::IDocumentProperties *))(*(_QWORD *)v72 + 16LL))(v72);
      }
LABEL_63:
      CMsoUrlSimple::~CMsoUrlSimple((CMsoUrlSimple *)v319);
      if ( v251 )
        (*(void (__fastcall **)(Csi *))(*(_QWORD *)v251 + 16LL))(v251);
      goto LABEL_65;
    }
    if ( (unsigned __int8)Csi::IsCsiError(v251, 4795) )
    {
      v62 = 1;
      v63 = 1;
      *((_DWORD *)this + 377) = 521286297;
      goto LABEL_55;
    }
    if ( (unsigned __int8)Csi::IsCsiError(v251, 1660) )
    {
      v62 = 1;
      v63 = 1;
      *((_DWORD *)this + 377) = 25236369;
      goto LABEL_55;
    }
    if ( (unsigned __int8)sub_180BED830((char *)this + 1544, v251) || v252 )
    {
      CMsoOLDocBase::SetIsOpeningOfflineCopy(this, 1);
      v222 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v259);
      v224 = (const struct Mso::Telemetry::IDataContract *)Office::FileIO::MSO::CsiGetFileFromCacheMetaData::CsiGetFileFromCacheMetaData(
                                                             (Office::FileIO::MSO::CsiGetFileFromCacheMetaData *)&v302,
                                                             v223);
      v225 = (const struct Mso::Telemetry::ISingleDataField *)Mso::Telemetry::DataContractField::DataContractField(
                                                                (Mso::Telemetry::DataContractField *)v316,
                                                                "CsiGetFileFromCacheMetaData",
                                                                v224);
      Mso::Telemetry::IDataFieldCollection::Add(v222, v225);
      if ( *((_BYTE *)this + 1552) )
      {
        v227 = 22619147;
        v228 = *v256;
LABEL_303:
        Csi::SetActivityResultIErrorTag((Csi *)v259, v228, (const struct MsoCF::IError *)v227, v226);
        goto LABEL_282;
      }
    }
    if ( (unsigned __int8)sub_1804D906C((char *)this + 1088, v220, v221, 560567330) )
    {
      if ( (unsigned __int8)Csi::IsCsiError(v251, 2053) )
      {
        Mso::TCntPtr<IDGCContext>::operator=<DGCCDocument,void>((char *)this + 1848);
        LODWORD(v261) = 505701859;
        CMsoOLDocBase::SetFIsANewlyCreatedFile(this, (const struct MsoReserveTag *)&v261, 1);
      }
      goto LABEL_53;
    }
    Mso::TCntPtr<IDGCContext>::operator=<DGCCDocument,void>((char *)this + 1848);
    if ( (unsigned __int8)Csi::IsCsiError(v251, 902)
      || (unsigned __int8)Csi::IsCsiError(v251, 906)
      || (unsigned __int8)Csi::IsCsiError(v251, 915) )
    {
      CMsoOLDocBaseImpIOLDoc2::SetWTdi((CMsoOLDocFile *)((char *)this + 1544), -2147287008, 5u);
    }
    else if ( !(unsigned __int8)Csi::IsCsiError(v251, 1657)
           && !(unsigned __int8)Csi::IsCsiError(v251, 910)
           && !(unsigned __int8)Csi::IsCsiError(v251, 1673) )
    {
      if ( !(unsigned __int8)sub_180BED830((char *)this + 1544, v251)
        && !(unsigned __int8)Csi::IsCsiError(v251, 2019)
        && !v252 )
      {
        IsFallbackToHttpError = Csi::IsFallbackToHttpError(v251, v229);
        *(_BYTE *)v272 = IsFallbackToHttpError;
        if ( (unsigned __int8)Csi::IsCsiError(v251, 4705) )
        {
          Csi::CreateCsiErrorTag(4788, &v251, 38073426);
          MsoCF::CIPtr<MsoCF::IError,MsoCF::IError>::CopyTo(&v251, v256);
        }
        v227 = 22619149;
LABEL_302:
        v228 = v251;
        goto LABEL_303;
      }
      v62 = v253;
LABEL_319:
      if ( ((unsigned int)MsoFOfflineCachedFile((CMsoOLDocFile *)((char *)this + 1544))
         || Mso::DocumentError::DocErrorProviderUtils::IsFileInPerFileOffline(
              (CMsoOLDocFile *)((char *)this + 1544),
              v231)
         || Mso::DocumentError::DocErrorProviderUtils::IsFileInUnrecoverablePerFileOffline(
              (CMsoOLDocFile *)((char *)this + 1544),
              v232)
         || v252)
        && (unsigned int)CMsoOLDocFile::FIsAutoMergable((char *)this + 1568, 560567329) )
      {
LABEL_54:
        v63 = v254;
      }
      else
      {
        v63 = 1;
        *((_DWORD *)this + 377) = 25236370;
      }
      goto LABEL_55;
    }
    v62 = 1;
    goto LABEL_319;
  }
  v182 = v251;
  v251 = 0;
  if ( v182 )
    (*(void (__fastcall **)(Csi *))(*(_QWORD *)v182 + 16LL))(v182);
  Csi::CreateCsiErrorTag(5600, &v251, 541909523);
  MsoCF::CIPtr<MsoCF::IError,MsoCF::IError>::CopyTo(&v251, v256);
  Csi::SetActivityResultIErrorTag((Csi *)v259, v251, (const struct MsoCF::IError *)0x204CE212, v183);
  v311 = 0;
  v184 = _mm_load_si128((const __m128i *)&_xmm);
  v312 = v184;
  LOWORD(v311) = 0;
  v298 = 0;
  v299 = v184;
  LOWORD(v298) = 0;
  v309 = 0;
  si128 = v184;
  LOWORD(v309) = 0;
  v300 = 0;
  v301 = v184;
  LOWORD(v300) = 0;
  LOBYTE(v249) = 0;
  if ( (unsigned int)Mso::Url::ExtractAllWopiPropertiesFromWopiUrl(
                       *((_QWORD *)this + 36),
                       &v311,
                       &v298,
                       &v309,
                       &v300,
                       v249) )
  {
    v217 = (const OLECHAR *)*((_QWORD *)this + 36);
    Mso::Alerts::CreateDefaultAlertParam(v328);
    v218 = &WindowName;
    if ( v217 )
      v218 = v217;
    v264 = (const char *)v218;
    do
      ++v14;
    while ( v218[v14] );
    v265 = (void ***)v14;
    v272 = (WCHAR *)&v264;
    v273 = (struct MsoCF::IError ***)&v266;
    v213 = Mso::Alerts::GetAlertMessageFromMsoIds(&v302, 38601128, &v272);
    Mso::Alerts::AlertMessage::operator=(v329, v213);
    Mso::Help::Core::AuthInfo::~AuthInfo((Mso::Help::Core::AuthInfo *)&v302);
    v330 = 3;
    v215 = Mso::Alerts::GetTelemetryNamespace(v214);
    LODWORD(v261) = 509354594;
    Mso::Alerts::ShowAlert((Mso::Alerts *)&v261, v215, (const struct Mso::Telemetry::TelemetryNamespace *)v328, v216);
    std::pair<std::wstring const,Mso::History::FileInfo>::~pair<std::wstring const,Mso::History::FileInfo>(v328);
    goto LABEL_280;
  }
  v186 = Mso::OfficeServicesManager::GetInstance(v185);
  v187 = v186;
  if ( !v186 )
  {
    CrashWithRecovery(0x204CE211u, 0);
    __debugbreak();
  }
  v188 = *(_QWORD *)v186;
  v189 = &v298;
  if ( v299.m128i_i64[1] > 7uLL )
    v189 = (__int128 *)v298;
  (*(void (__fastcall **)(struct Mso::OfficeServicesManager::IOfficeServicesManager *, WCHAR **, __int128 *))(v188 + 8))(
    v187,
    &v272,
    v189);
  if ( !v272 )
  {
    Mso::Alerts::CreateDefaultAlertParam(v278);
    std::wstring::operator std::wstring_view(&v300, v276);
    v261 = (const char *)v276;
    v262 = v277;
    v209 = Mso::Alerts::GetAlertMessageFromMsoIds(&v302, 3391383533LL, &v261);
    Mso::Alerts::AlertMessage::operator=(v279, v209);
    Mso::Help::Core::AuthInfo::~AuthInfo((Mso::Help::Core::AuthInfo *)&v302);
    v289 = 1;
    v290 = (__int64)v264;
    v211 = Mso::Alerts::GetTelemetryNamespace(v210);
    LODWORD(v261) = 509354595;
    Mso::Alerts::ShowAlert((Mso::Alerts *)&v261, v211, (const struct Mso::Telemetry::TelemetryNamespace *)v278, v212);
    std::pair<std::wstring const,Mso::History::FileInfo>::~pair<std::wstring const,Mso::History::FileInfo>(v278);
LABEL_279:
    Mso::TCntPtr<Mso::IMsoDocEnterpriseProtection>::Clear(&v272);
LABEL_280:
    std::basic_string<char16_t>::~basic_string<char16_t>(&v300);
    std::basic_string<char16_t>::~basic_string<char16_t>(&v309);
    std::basic_string<char16_t>::~basic_string<char16_t>(&v298);
    std::basic_string<char16_t>::~basic_string<char16_t>(&v311);
LABEL_282:
    if ( v267 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v267 + 16LL))(v267);
    Mso::TCntPtr<Mso::DocumentActivities::Common::TaskReassignment>::Clear(&v257);
    goto LABEL_63;
  }
  v191 = Mso::ApplicationModel::UseCurrentExecutionContext(v190);
  LOBYTE(v192) = 1;
  Mso::TCntPtr<Mso::ApplicationModel::IExecutionContext>::TCntPtr<Mso::ApplicationModel::IExecutionContext>(
    &v261,
    v191,
    v192);
  Mso::TCntPtr<SDX::MSO::Adapter>::TCntPtr<SDX::MSO::Adapter>(S1, &v261);
  v296 = 0;
  LODWORD(S1[1]) = 509646159;
  Mso::TCntPtr<Mso::IMsoDocEnterpriseProtection>::Clear(&v261);
  Mso::ServiceManagerCallback::CreateThirdPartyCallback(v276, &v298);
  v193 = Mso::TCntPtr<Mso::Sharing::SharingResult<Mso::Sharing::MsoGetUserAttributesResponse>>::operator->(v276);
  (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v193 + 32LL))(v193, v313);
  if ( !v314 )
  {
    if ( S1[0] )
    {
      v200 = 1;
LABEL_270:
      v302 = &Mso::Diagnostics::ClassifiedStructuredObject<bool>::`vftable';
      *(_QWORD *)Destination = "HasExecutionContext";
      v304[0] = v200;
      *(_WORD *)&v304[2] = 4;
      *(_OWORD *)&v304[8] = 0;
      v305 = v184;
      *(_WORD *)&v304[8] = 0;
      v316[0] = &Mso::Diagnostics::ClassifiedStructuredObject<bool>::`vftable';
      v316[1] = "ConnectionId";
      LOBYTE(v317) = v314 == 0;
      WORD1(v317) = 4;
      v318[0] = 0;
      v318[1] = v184;
      LOWORD(v318[0]) = 0;
      v261 = "csierrWopi_InvalidUrl on open, could not prompt for creds";
      Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>,Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>>(
        509646040,
        836,
        15,
        v194,
        (__int64)&v261,
        (__int64)v316,
        (__int64)&v302);
      std::basic_string<char16_t>::~basic_string<char16_t>(v318);
      std::basic_string<char16_t>::~basic_string<char16_t>(&v304[8]);
      goto LABEL_271;
    }
LABEL_269:
    v200 = 0;
    goto LABEL_270;
  }
  if ( !S1[0] )
    goto LABEL_269;
  v195 = (const struct IMsoUrl *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v313);
  v197 = MsoServerInfoUtils::PromptForWopiCreds((MsoServerInfoUtils *)v320, v195, (const wchar_t *)S1, v196);
  *(_QWORD *)Destination = "HResult";
  *(_DWORD *)v304 = v197;
  *(_OWORD *)&v304[8] = 0;
  v305.m128i_i64[0] = 0;
  v305.m128i_i64[1] = 7;
  *(_WORD *)&v304[8] = 0;
  LOWORD(v306) = 4;
  v302 = &Mso::Diagnostics::ClassifiedStructuredHr::`vftable';
  v261 = "csierrWopi_InvalidUrl on open, prompted for creds";
  Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
    509646158,
    836,
    15,
    v198,
    (__int64)&v261,
    (__int64)&v302);
  std::basic_string<char16_t>::~basic_string<char16_t>(&v304[8]);
  if ( v197 < 0 )
  {
LABEL_271:
    v201 = Mso::TCntPtr<Mso::Sharing::SharingResult<Mso::Sharing::MsoGetUserAttributesResponse>>::operator->(&v272);
    v202 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v201 + 128LL))(v201);
    Mso::Alerts::CreateDefaultAlertParam(v291);
    std::wstring::operator std::wstring_view(&v300, v316);
    v203 = &WindowName;
    if ( v202 )
      v203 = (const OLECHAR *)v202;
    v317 = v203;
    do
      ++v14;
    while ( v203[v14] );
    *(_QWORD *)&v318[0] = v14;
    v261 = (const char *)v316;
    v262 = (char *)v318 + 8;
    v204 = Mso::Alerts::GetAlertMessageFromMsoIds(&v302, 39819150, &v261);
    Mso::Alerts::AlertMessage::operator=(v292, v204);
    Mso::Help::Core::AuthInfo::~AuthInfo((Mso::Help::Core::AuthInfo *)&v302);
    v293 = 1;
    v294 = (__int64)v264;
    v206 = Mso::Alerts::GetTelemetryNamespace(v205);
    LODWORD(v261) = 509354624;
    Mso::Alerts::ShowAlert((Mso::Alerts *)&v261, v206, (const struct Mso::Telemetry::TelemetryNamespace *)v291, v207);
    std::pair<std::wstring const,Mso::History::FileInfo>::~pair<std::wstring const,Mso::History::FileInfo>(v291);
    std::basic_string<char16_t>::~basic_string<char16_t>(v313);
    v208 = v276[0];
    if ( v276[0] )
    {
      v276[0] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v208 + 8LL))(v208);
    }
    Mso::TCntPtr<Mso::IMsoDocEnterpriseProtection>::Clear(S1);
    goto LABEL_279;
  }
  std::basic_string<char16_t>::~basic_string<char16_t>(v313);
  v199 = v276[0];
  if ( v276[0] )
  {
    v276[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v199 + 8LL))(v199);
  }
  Mso::TCntPtr<Mso::IMsoDocEnterpriseProtection>::Clear(S1);
  Mso::TCntPtr<Mso::IMsoDocEnterpriseProtection>::Clear(&v272);
  std::basic_string<char16_t>::~basic_string<char16_t>(&v300);
  std::basic_string<char16_t>::~basic_string<char16_t>(&v309);
  std::basic_string<char16_t>::~basic_string<char16_t>(&v298);
  std::basic_string<char16_t>::~basic_string<char16_t>(&v311);
  if ( v267 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v267 + 16LL))(v267);
  Mso::TCntPtr<Mso::DocumentActivities::Common::TaskReassignment>::Clear(&v257);
  CMsoUrlSimple::~CMsoUrlSimple((CMsoUrlSimple *)v319);
  if ( v251 )
    (*(void (__fastcall **)(Csi *))(*(_QWORD *)v251 + 16LL))(v251);
  v12 = 1;
LABEL_65:
  Measurements::MeasureElapsedTime::~MeasureElapsedTime((Measurements::MeasureElapsedTime *)v277);
  Mso::Telemetry::Activity::~Activity((Mso::Telemetry::Activity *)v259);
  return v12;
}

```

## disassembly

```asm
0x180683c6c  mov     [rsp-8+arg_8], rbx
0x180683c71  push    rbp
0x180683c72  push    rsi
0x180683c73  push    rdi
0x180683c74  push    r12
0x180683c76  push    r13
0x180683c78  push    r14
0x180683c7a  push    r15
0x180683c7c  lea     rbp, [rsp-1B40h]
0x180683c84  mov     eax, 1C40h
0x180683c89  call    _alloca_probe
0x180683c8e  sub     rsp, rax
0x180683c91  movaps  [rsp+1C70h+var_40], xmm6
0x180683c99  mov     rax, cs:__security_cookie
0x180683ca0  xor     rax, rsp
0x180683ca3  mov     [rbp+1B70h+var_50], rax
0x180683caa  mov     byte ptr [rbp+1B70h+var_1BC0], r9b
0x180683cae  mov     bl, r8b
0x180683cb1  mov     [rbp+1B70h+var_1BF0], bl
0x180683cb4  mov     sil, dl
0x180683cb7  mov     [rsp+1C70h+var_1C1E], dl
0x180683cbb  mov     r15, rcx
0x180683cbe  mov     rax, [rbp+1B70h+arg_28]
0x180683cc5  mov     [rsp+1C70h+var_1C18], rax
0x180683cca  mov     rax, [rbp+1B70h+arg_30]
0x180683cd1  mov     [rbp+1B70h+var_1B98], rax
0x180683cd5  lea     rdi, [rcx+608h]
0x180683cdc  mov     r12d, 1
0x180683ce2  xor     r14d, r14d
0x180683ce5  test    dl, dl
0x180683ce7  jz      loc_180684B36
0x180683ced  mov     [rbp+1B70h+var_1BD8], 6
0x180683cf4  mov     [rsp+1C70h+var_1C1F], r14b
0x180683cf9  mov     [rsp+1C70h+var_1C08], 16Eh
0x180683d00  mov     eax, 2
0x180683d05  mov     word ptr [rbp+1B70h+var_1BE8], ax
0x180683d09  mov     byte ptr [rbp+1B70h+var_1BE8+2], r12b
0x180683d0d  mov     [rbp+1B70h+var_1B9F], r14b
0x180683d11  mov     [rbp+1B70h+var_1B85], r14b
0x180683d15  mov     [rbp+1B70h+var_1B87], r14b
0x180683d19  lea     rax, [rsp+1C70h+var_1C08]
0x180683d1e  mov     [rsp+1C70h+var_1C48], rax
0x180683d23  lea     rax, [rbp+1B70h+var_1BE8]
0x180683d27  mov     [rsp+1C70h+var_1C50], rax
0x180683d2c  lea     r9, [rbp+1B70h+var_1BA0]
0x180683d30  lea     r8, [rbp+1B70h+var_1B86]
0x180683d34  lea     rdx, [rbp+1B70h+var_1B88]
0x180683d38  lea     rcx, [rbp+1B70h+var_1BD0]
0x180683d3c  call    cs:__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z; Mso::Telemetry::EventFlags::EventFlags(std::optional<Mso::Telemetry::SamplingPolicy> const &,std::optional<Mso::Telemetry::PersistencePriority> const &,std::optional<Mso::Telemetry::CostPriority> const &,std::optional<Mso::Telemetry::DataCategories> const &,std::optional<Mso::Telemetry::DiagnosticLevel> const &)
0x180683d42  call    cs:__imp_?GetNamespace@MSO@FileIO@Office@@YAAEBUTelemetryNamespace@Telemetry@Mso@@XZ; Office::FileIO::MSO::GetNamespace(void)
0x180683d48  mov     [rbp+1B70h+var_1BB0], rax
0x180683d4c  lea     rax, aFcsigetfile; "FCsiGetFile"
0x180683d53  mov     [rbp+1B70h+var_1BA8], rax
0x180683d57  lea     r8, [rbp+1B70h+var_1BD0]; struct Mso::Telemetry::EventFlags *
0x180683d5b  lea     rdx, [rbp+1B70h+var_1BB0]; struct Mso::Telemetry::EventName *
0x180683d5f  lea     rcx, [rsp+1C70h+var_1C00]; this
0x180683d64  call    ??0Activity@Telemetry@Mso@@QEAA@AEBUEventName@12@AEBUEventFlags@12@@Z; Mso::Telemetry::Activity::Activity(Mso::Telemetry::EventName const &,Mso::Telemetry::EventFlags const &)
0x180683d69  or      r13, 0FFFFFFFFFFFFFFFFh
0x180683d6d  test    r15, r15
0x180683d70  jz      short loc_180683DB2
0x180683d72  mov     rdx, r15
0x180683d75  lea     rcx, [rbp+1B70h+var_1BB0]
0x180683d79  call    ??$FindDocumentTelemetryForDocument@VCMsoOLDocFile@@X@DocumentTelemetry@Mso@@YA?AV?$TCntPtr@UIDocumentTelemetry@DocumentTelemetry@Mso@@@1@AEBVCMsoOLDocFile@@@Z; Mso::DocumentTelemetry::FindDocumentTelemetryForDocument<CMsoOLDocFile,void>(CMsoOLDocFile const &)
0x180683d7e  mov     r8, [rbp+1B70h+var_1BB0]
0x180683d82  test    r8, r8
0x180683d85  jz      short loc_180683DB2
0x180683d87  mov     r9, r13
0x180683d8a  lea     rdx, [rsp+1C70h+var_1C00]
0x180683d8f  lea     rcx, [rbp+1B70h+var_1BE8]
0x180683d93  call    ??$AddDocumentTelemetryToActivity@UActivity@Telemetry@Mso@@@DocumentTelemetry@Mso@@YA?AVCAddDocumentTelemetryToActivityResult@01@AEAUActivity@Telemetry@1@AEBUIDocumentTelemetry@01@W4DocumentFields@01@PEBD@Z; Mso::DocumentTelemetry::AddDocumentTelemetryToActivity<Mso::Telemetry::Activity>(Mso::Telemetry::Activity &,Mso::DocumentTelemetry::IDocumentTelemetry const &,Mso::DocumentTelemetry::DocumentFields,char const *)
0x180683d98  mov     rcx, [rbp+1B70h+var_1BB0]
0x180683d9c  test    rcx, rcx
0x180683d9f  jz      short loc_180683DB2
0x180683da1  mov     [rbp+1B70h+var_1BB0], r14
0x180683da5  mov     rax, [rcx]
0x180683da8  mov     rax, [rax+10h]
0x180683dac  call    cs:__guard_dispatch_icall_fptr
0x180683db2  lea     rcx, [rsp+1C70h+var_1C00]
0x180683db7  call    cs:__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180683dbd  mov     r8b, byte ptr [rbp+1B70h+var_1BD8]
0x180683dc1  lea     rdx, aOpenfilestateR; "OpenFileState_Requested"
0x180683dc8  mov     rcx, rax
0x180683dcb  call    ??$Add@E@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBDEW4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<uchar>(char const *,uchar,Mso::Logging::DataClassifications)
0x180683dd0  lea     rcx, [rsp+1C70h+var_1C00]
0x180683dd5  call    cs:__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180683ddb  mov     rbx, rax
0x180683dde  mov     rcx, r15; this
0x180683de1  call    ?GetFBlockNetworkCalls@CMsoOLDocBase@@UEAAHXZ; CMsoOLDocBase::GetFBlockNetworkCalls(void)
0x180683de6  mov     r8d, eax
0x180683de9  lea     rdx, aBlocknetworkca; "BlockNetworkCalls"
0x180683df0  mov     rcx, rbx
0x180683df3  call    ??$Add@H@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBDHW4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<int>(char const *,int,Mso::Logging::DataClassifications)
0x180683df8  lea     rax, ??_7?$ClassifiedStructuredObject@U_GUID@@@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<_GUID>::`vftable'
0x180683dff  mov     [rbp+1B70h+var_1940], rax
0x180683e06  lea     rax, aDocumentunique; "DocumentUniqueId"
0x180683e0d  mov     qword ptr [rbp+1B70h+Destination], rax
0x180683e14  movups  xmm0, xmmword ptr [r15+0F0h]
0x180683e1c  movdqu  [rbp+1B70h+var_1930], xmm0
0x180683e24  mov     eax, 100h
0x180683e29  mov     word ptr [rbp+1B70h+var_1920], ax
0x180683e30  xorps   xmm0, xmm0
0x180683e33  movups  [rbp+1B70h+var_1918], xmm0
0x180683e3a  mov     [rbp+1B70h+var_1908], r14
0x180683e41  mov     [rbp+1B70h+var_1900], 7
0x180683e4c  mov     word ptr [rbp+1B70h+var_1918], r14w
0x180683e54  lea     rax, aOldocFcsigetfi; "OLDoc:FCsiGetFile"
0x180683e5b  mov     [rbp+1B70h+var_1BD0], rax
0x180683e5f  lea     rax, [rbp+1B70h+var_1940]
0x180683e66  mov     [rsp+1C70h+var_1C48], rax
0x180683e6b  lea     rax, [rbp+1B70h+var_1BD0]
0x180683e6f  mov     [rsp+1C70h+var_1C50], rax
0x180683e74  mov     edx, 344h
0x180683e79  mov     ecx, 236CD453h
0x180683e7e  mov     r8d, 32h ; '2'
0x180683e84  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@PEB_W@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> &&)
0x180683e89  lea     rcx, [rbp+1B70h+var_1918]; void *
0x180683e90  call    ??1?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAA@XZ; std::basic_string<char16_t>::~basic_string<char16_t>(void)
0x180683e95  lea     rcx, [rbp+1B70h+var_1BD0]
0x180683e99  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x180683e9e  mov     rcx, [rax]
0x180683ea1  mov     [rbp+1B70h+var_18A0], r14
0x180683ea8  mov     [rbp+1B70h+var_1898], rcx
0x180683eaf  mov     [rbp+1B70h+var_1890], rcx
0x180683eb6  mov     [rbp+1B70h+var_1888], r12b
0x180683ebd  lea     r9, [rbp+1B70h+var_18A0]
0x180683ec4  mov     r8b, r12b
0x180683ec7  mov     edx, cs:?OLDocFCsiGetFile@MeasurementId@Measurements@@3UMeasurementIdType@2@B; Measurements::MeasurementIdType const Measurements::MeasurementId::OLDocFCsiGetFile
0x180683ecd  lea     rcx, [rbp+1B70h+var_1B70]
0x180683ed1  call    cs:__imp_??0MeasureElapsedTime@Measurements@@QEAA@UMeasurementIdType@1@_N$$QEAVStopwatch@1@@Z; Measurements::MeasureElapsedTime::MeasureElapsedTime(Measurements::MeasurementIdType,bool,Measurements::Stopwatch &&)
0x180683ed7  mov     rax, [rbp+1B70h+var_1B98]
0x180683edb  mov     [rax], r14b
0x180683ede  cmp     [r15+708h], r14b
0x180683ee5  jz      loc_180684410
0x180683eeb  mov     [rbp+1B70h+var_16F0], 1
0x180683ef6  mov     [rbp+1B70h+var_16E8], r14
0x180683efd  mov     [rbp+1B70h+var_16E0], r14
0x180683f04  mov     [rbp+1B70h+var_16D8], r14d
0x180683f0b  mov     [rbp+1B70h+var_68C], r14
0x180683f12  mov     [rbp+1B70h+var_674], r14b
0x180683f19  mov     [rbp+1B70h+var_668], r14b
0x180683f20  xor     r9d, r9d; bool
0x180683f23  xor     r8d, r8d; struct MSODMGSI *
0x180683f26  lea     rdx, [rbp+1B70h+var_16F0]; struct Csi::CsiServerInfo *
0x180683f2d  mov     rcx, rdi; this
0x180683f30  call    ?GetCsiServerInfo@CMsoOLDocFile@@UEAAXPEAUCsiServerInfo@Csi@@PEAUMSODMGSI@@_N@Z; CMsoOLDocFile::GetCsiServerInfo(Csi::CsiServerInfo *,MSODMGSI *,bool)
0x180683f35  lea     rcx, [rsp+1C70h+var_1C00]
0x180683f3a  call    cs:__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180683f40  mov     r8d, dword ptr [rbp+1B70h+var_16E8+4]
0x180683f47  lea     rdx, aProtocol; "Protocol"
0x180683f4e  mov     rcx, rax
0x180683f51  call    ??$Add@H@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBDHW4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<int>(char const *,int,Mso::Logging::DataClassifications)
0x180683f56  lea     rcx, [rsp+1C70h+var_1C00]
0x180683f5b  call    cs:__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180683f61  mov     r8d, dword ptr [rbp+1B70h+var_16E8]
0x180683f68  lea     rdx, aServertype; "ServerType"
0x180683f6f  mov     rcx, rax
0x180683f72  call    ??$Add@H@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBDHW4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<int>(char const *,int,Mso::Logging::DataClassifications)
0x180683f77  lea     rcx, [rsp+1C70h+var_1C00]
0x180683f7c  call    cs:__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180683f82  cmp     dword ptr [rbp+1B70h+var_16E8], 5
0x180683f89  jz      loc_180684B59
0x180683f8f  cmp     byte ptr [rbp+1B70h+var_16D8], r12b
0x180683f96  ja      short loc_180683FB7
0x180683f98  jnz     short loc_180683FA3
0x180683f9a  cmp     byte ptr [rbp+1B70h+var_16D8+1], 3
0x180683fa1  jnb     short loc_180683FB7
0x180683fa3  cmp     dword ptr [rbp+1B70h+var_16E8], 0Ah
0x180683faa  jz      loc_180684B65
0x180683fb0  mov     r8b, r14b
0x180683fb3  jmp     short loc_180683FBA
0x180683fb5  jz      short loc_180683FB0
0x180683fb7  mov     r8b, r12b
0x180683fba  mov     ebx, 4
0x180683fbf  mov     r9d, ebx
0x180683fc2  lea     rdx, aCloudcollab; "CloudCollab"
0x180683fc9  mov     rcx, rax
0x180683fcc  call    ??$Add@_N@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBD_NW4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<bool>(char const *,bool,Mso::Logging::DataClassifications)
0x180683fd1  lea     rcx, [rsp+1C70h+var_1C00]
0x180683fd6  call    cs:__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180683fdc  cmp     dword ptr [rbp+1B70h+var_68C], r14d
0x180683fe3  setbe   r8b
0x180683fe7  mov     r9d, ebx
0x180683fea  lea     rdx, aIsweburlempty; "IsWebUrlEmpty"
0x180683ff1  mov     rcx, rax
0x180683ff4  call    ??$Add@_N@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBD_NW4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<bool>(char const *,bool,Mso::Logging::DataClassifications)
0x180683ff9  cmp     dword ptr [rbp+1B70h+var_16F0+4], r12d
0x180684000  jz      loc_180684B71
0x180684006  xor     ecx, ecx
0x180684008  call    cs:__imp_?HwndParentForDmEx@@YAPEAUHWND__@@_N@Z; HwndParentForDmEx(bool)
0x18068400e  mov     rdi, rax
0x180684011  mov     [rbp+1B70h+var_1BD0], rax
0x180684015  mov     [rsp+1C70h+var_1C28], r14
0x18068401a  lea     rcx, [r15+608h]
0x180684021  lea     r9, [rbp+1B70h+var_16F0]
0x180684028  mov     r8d, [rbp+1B70h+var_1BD8]
0x18068402c  lea     rdx, [rsp+1C70h+var_1C28]
0x180684031  call    ?FInitCsiFile@CMsoOLDocFile@@MEAAHPEAPEAUIError@MsoCF@@W4CAOpenFileState@@PEBUCsiServerInfo@Csi@@@Z; CMsoOLDocFile::FInitCsiFile(MsoCF::IError * *,CAOpenFileState,Csi::CsiServerInfo const *)
0x180684036  test    eax, eax
0x180684038  jz      loc_180684BBF
0x18068403e  mov     rcx, r15; this
0x180684041  call    ?IsCachedAsDistributedBlobsFile@CMsoOLDocBase@@IEBA_NXZ; CMsoOLDocBase::IsCachedAsDistributedBlobsFile(void)
0x180684046  test    al, al
0x180684048  jnz     loc_18068545A
0x18068404e  mov     dword ptr [rbp+1B70h+var_1BE8], 1E20884Dh
0x180684055  mov     r9, [rsp+1C70h+var_1C18]
0x18068405a  mov     r8d, [rbp+1B70h+var_1BD8]
0x18068405e  lea     rdx, [rbp+1B70h+var_1BE8]
0x180684062  mov     rcx, r15
0x180684065  call    ?UpdateReadWriteMode@CMsoOLDocFile@@AEAA_NAEBVMsoReserveTag@@W4CAOpenFileState@@PEAPEAUIError@MsoCF@@@Z; CMsoOLDocFile::UpdateReadWriteMode(MsoReserveTag const &,CAOpenFileState,MsoCF::IError * *)
0x18068406a  test    al, al
0x18068406c  jz      loc_180684869
0x180684072  xor     edx, edx; bool
0x180684074  mov     rcx, r15; this
0x180684077  call    ?SetIsOpeningOfflineCopy@CMsoOLDocBase@@QEAAX_N@Z; CMsoOLDocBase::SetIsOpeningOfflineCopy(bool)
0x18068407c  lea     rcx, [rbp+1B70h+var_1820]
0x180684083  call    cs:__imp_??0CMsoUrlSimple@@QEAA@XZ; CMsoUrlSimple::CMsoUrlSimple(void)
0x180684089  mov     rbx, [rsp+1C70h+var_1C18]
0x18068408e  mov     [rsp+1C70h+var_1C50], r14
0x180684093  xor     r9d, r9d
0x180684096  xor     r8d, r8d
0x180684099  mov     rdx, [r15+120h]
0x1806840a0  lea     rcx, [rbp+1B70h+var_1810]
0x1806840a7  call    ?HrSetFromUser@CMsoUrlSimple@@UEAAJPEB_WKPEBUIMsoUrl@@W4MsoUrlCreateFlags@@@Z; CMsoUrlSimple::HrSetFromUser(wchar_t const *,ulong,IMsoUrl const *,MsoUrlCreateFlags)
0x1806840ac  test    eax, eax
0x1806840ae  js      loc_18068547B
0x1806840b4  mov     [rsp+1C70h+var_1C10], r14
0x1806840b9  mov     dword ptr [rbp+1B70h+var_1BE8], 21699423h
0x1806840c0  lea     r8, [rbp+1B70h+var_1BE8]; struct MsoReserveTag *
0x1806840c4  lea     rdx, [rsp+1C70h+var_1C10]; struct Csi::IDocumentProperties **
0x1806840c9  mov     rcx, r15; this
0x1806840cc  call    ?GetProperties@CMsoOLDocBase@@IEBAXPEAPEAUIDocumentProperties@Csi@@AEBVMsoReserveTag@@@Z; CMsoOLDocBase::GetProperties(Csi::IDocumentProperties * *,MsoReserveTag const &)
0x1806840d1  mov     rcx, [rsp+1C70h+var_1C10]
0x1806840d6  test    rcx, rcx
0x1806840d9  jnz     loc_180684391
0x1806840df  call    cs:__imp_?FNetworkExists@NetCost@Mso@@YA_NXZ; Mso::NetCost::FNetworkExists(void)
0x1806840e5  xor     al, r12b
0x1806840e8  mov     [rsp+1C70h+var_1C1D], al
0x1806840ec  mov     rcx, [r15+120h]
0x1806840f3  call    sub_180A9FD48
0x1806840f8  test    eax, eax
0x1806840fa  setnz   [rsp+1C70h+var_1C20]
0x1806840ff  lea     rcx, [r15+620h]
0x180684106  mov     edx, 21559763h
0x18068410b  call    ?IsFileCached@CMsoOLDocFile@@UEAA_NVMsoReserveTag@@@Z; CMsoOLDocFile::IsFileCached(MsoReserveTag)
0x180684110  mov     bl, al
0x180684112  mov     byte ptr [rsp+1C70h+var_1C08], al
0x180684116  lea     rcx, [rsp+1C70h+var_1C00]
0x18068411b  call    cs:__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180684121  mov     edi, 4
0x180684126  mov     r9d, edi
0x180684129  mov     r8b, [rsp+1C70h+var_1C20]
0x18068412e  lea     rdx, aRecoverymode; "recoveryMode"
0x180684135  mov     rcx, rax
0x180684138  call    ??$Add@_N@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBD_NW4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<bool>(char const *,bool,Mso::Logging::DataClassifications)
0x18068413d  lea     rcx, [rsp+1C70h+var_1C00]
0x180684142  call    cs:__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180684148  mov     r9d, edi
0x18068414b  mov     r8b, bl
0x18068414e  lea     rdx, aIsfilecachedbe; "isFileCachedBeforeOpen"
0x180684155  mov     rcx, rax
0x180684158  call    ??$Add@_N@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBD_NW4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<bool>(char const *,bool,Mso::Logging::DataClassifications)
0x18068415d  mov     al, [rsp+1C70h+var_1C20]
0x180684161  test    al, al
0x180684163  jnz     loc_18068550B
0x180684169  cmp     [rsp+1C70h+var_1C1D], r14b
0x18068416e  jz      loc_180685543
0x180684174  mov     al, r14b
0x180684177  mov     [rsp+1C70h+var_1C30], al
0x18068417b  lea     rcx, [rsp+1C70h+var_1C00]
0x180684180  call    cs:__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180684186  mov     r9d, edi
0x180684189  mov     r8b, [rsp+1C70h+var_1C30]
0x18068418e  lea     rdx, aAsyncdownload; "AsyncDownload"
0x180684195  mov     rcx, rax
0x180684198  call    ??$Add@_N@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBD_NW4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<bool>(char const *,bool,Mso::Logging::DataClassifications)
0x18068419d  lea     rcx, [rsp+1C70h+var_1C00]
0x1806841a2  call    cs:__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x1806841a8  mov     r9d, edi
0x1806841ab  mov     r8b, [rsp+1C70h+var_1C1D]
0x1806841b0  lea     rdx, aOpenoffline; "OpenOffline"
0x1806841b7  mov     rcx, rax
0x1806841ba  call    ??$Add@_N@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBD_NW4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<bool>(char const *,bool,Mso::Logging::DataClassifications)
0x1806841bf  lea     rax, aTrue_0; "true"
0x1806841c6  lea     rcx, aFalse_0; "false"
0x1806841cd  cmp     [rsp+1C70h+var_1C30], r14b
0x1806841d2  cmovz   rax, rcx
0x1806841d6  mov     [rbp+1B70h+var_1BB0], rax
0x1806841da  lea     rax, [rbp+1B70h+var_1BB0]
0x1806841de  mov     [rsp+1C70h+var_1C48], rax
0x1806841e3  lea     rax, aCmsooldocfileF_0; "CMsoOLDocFile::FCsiGetFile: fAsyncDownl"...
0x1806841ea  mov     [rsp+1C70h+var_1C50], rax
0x1806841ef  mov     edx, 2A5h
0x1806841f4  mov     ecx, 170B0DEh
0x1806841f9  mov     r8d, 32h ; '2'
0x1806841ff  call    ??$MsoSendTraceTag@PEB_W@Logging@Mso@@YAXKW4Category@01@W4Severity@01@W4DataCategories@01@PEB_WAEBQEB_W@Z; Mso::Logging::MsoSendTraceTag<wchar_t const *>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories,wchar_t const *,wchar_t const * const &)
0x180684204  mov     [r15+710h], r14
0x18068420b  mov     [rbp+1B70h+var_1BB8], r14
0x18068420f  mov     rcx, r15; this
0x180684212  call    ?COpenGet@CMsoOLDocBase@@QEBAHXZ; CMsoOLDocBase::COpenGet(void)
0x180684217  test    eax, eax
  ... truncated ...
```
