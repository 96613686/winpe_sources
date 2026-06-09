# CMsoOLDocFile::FCsiGetFile(bool,bool,bool,IMsoTask *,MsoCF::IError * *,bool *)

- ea: `0x180c2d878`
- end: `0x180c2febf`
- name: `?FCsiGetFile@CMsoOLDocFile@@IEAAH_N00PEAUIMsoTask@@PEAPEAUIError@MsoCF@@PEA_N@Z`
- size: `9799`
- prototype: `__int64 __fastcall(CMsoOLDocFile *__hidden this, bool, bool, bool, struct IMsoTask *, struct MsoCF::IError **, bool *)`
- caller_count: `1`
- callee_count: `101`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180696854`

## callees

- `0x180014180`
- `0x180014fb0`
- `0x180015b94`
- `0x18002af10`
- `0x18002fa60`
- `0x180032680`
- `0x1800326a8`
- `0x180032d80`
- `0x180032e30`
- `0x180033348`
- `0x180036a80`
- `0x18003e070`
- `0x18003e4b0`
- `0x18003e628`
- `0x18003e7a8`
- `0x18003f348`
- `0x180040d80`
- `0x180040e00`
- `0x180040e90`
- `0x1800433c0`
- `0x18004378c`
- `0x1800437fc`
- `0x180044110`
- `0x180052610`
- `0x18005273c`
- `0x180052c8c`
- `0x180052ce0`
- `0x1800530e0`
- `0x180088640`
- `0x1800ba08c`
- `0x1800bbe50`
- `0x1800bbe90`
- `0x1800e8d70`
- `0x1800f6c60`
- `0x1800f6f70`
- `0x1800f7280`
- `0x1800f9a68`
- `0x18011f9e8`
- `0x1801639d0`
- `0x180188330`
- `0x18019a5fc`
- `0x1801ffba8`
- `0x180226b5c`
- `0x18022d2b8`
- `0x180239ab0`
- `0x18023c2e0`
- `0x18023ddcc`
- `0x18023de48`
- `0x18023e770`
- `0x18023e8d0`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x180c2fd78`
- `KERNEL32!GetFileAttributesW` at `0x180c2fd78`
- `KERNEL32!SetFileAttributesW` at `0x180c2fd8a`
- `KERNEL32!SetFileAttributesW` at `0x180c2fd8a`
- `Mso98Win32Client!__imp_?CreateThirdPartyCallback@ServiceManagerCallback@Mso@@YA?AV?$TCntPtr@VIThirdPartyServiceManagerCallback@ServiceManagerCallback@Mso@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x180c2f055`
- `Mso98Win32Client!__imp_?CreateThirdPartyCallback@ServiceManagerCallback@Mso@@YA?AV?$TCntPtr@VIThirdPartyServiceManagerCallback@ServiceManagerCallback@Mso@@@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x180c2f055`
- `Mso98Win32Client!__imp_?GetInstance@OfficeServicesManager@Mso@@YAPEAUIOfficeServicesManager@12@XZ` at `0x180c2dea1`
- `Mso98Win32Client!__imp_?GetInstance@OfficeServicesManager@Mso@@YAPEAUIOfficeServicesManager@12@XZ` at `0x180c2e0a7`
- `Mso98Win32Client!__imp_?GetInstance@OfficeServicesManager@Mso@@YAPEAUIOfficeServicesManager@12@XZ` at `0x180c2efcd`
- `Mso98Win32Client!__imp_?GetInstance@OfficeServicesManager@Mso@@YAPEAUIOfficeServicesManager@12@XZ` at `0x180c2dea1`
- `Mso98Win32Client!__imp_?GetInstance@OfficeServicesManager@Mso@@YAPEAUIOfficeServicesManager@12@XZ` at `0x180c2e0a7`
- `Mso98Win32Client!__imp_?GetInstance@OfficeServicesManager@Mso@@YAPEAUIOfficeServicesManager@12@XZ` at `0x180c2efcd`
- `Mso98Win32Client!__imp_?SetEnableBHO@MsoServerInfoUtils@@YAXPEBUIMsoUrl@@_N@Z` at `0x180c2fd9a`
- `Mso98Win32Client!__imp_?SetEnableBHO@MsoServerInfoUtils@@YAXPEBUIMsoUrl@@_N@Z` at `0x180c2fd9a`
- `Mso98Win32Client!__imp_?PromptForWopiCreds@MsoServerInfoUtils@@YAJAEBUIMsoUrl@@PEB_WAEBUUIExecutionContext@Authentication@Mso@@@Z` at `0x180c2f0b3`
- `Mso98Win32Client!__imp_?PromptForWopiCreds@MsoServerInfoUtils@@YAJAEBUIMsoUrl@@PEB_WAEBUUIExecutionContext@Authentication@Mso@@@Z` at `0x180c2f0b3`
- `mso40uiWin32Client!__imp_?HwndParentForDmEx@@YAPEAUHWND__@@_N@Z` at `0x180c2dc06`
- `mso40uiWin32Client!__imp_?HwndParentForDmEx@@YAPEAUHWND__@@_N@Z` at `0x180c2dc06`
- `Mso30Win32Client!__imp_?CreateCsiError@Csi@@YAXVCsiErrorCode@1@PEAPEAUIError@MsoCF@@@Z` at `0x180c2ecae`
- `Mso30Win32Client!__imp_?CreateCsiError@Csi@@YAXVCsiErrorCode@1@PEAPEAUIError@MsoCF@@@Z` at `0x180c2ecae`
- `Mso30Win32Client!__imp_?IsWopiPromptingOnOpenEnabled@ResourceInfo@Mso@@YA_NXZ` at `0x180c2dd9b`
- `Mso30Win32Client!__imp_?IsWopiPromptingOnOpenEnabled@ResourceInfo@Mso@@YA_NXZ` at `0x180c2dd9b`
- `Mso30Win32Client!__imp_?ExtractAllWopiPropertiesFromWopiUrl@Url@Mso@@YA?AW4WopiResult@12@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@111_N@Z` at `0x180c2de97`
- `Mso30Win32Client!__imp_?ExtractAllWopiPropertiesFromWopiUrl@Url@Mso@@YA?AW4WopiResult@12@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@111_N@Z` at `0x180c2e099`
- `Mso30Win32Client!__imp_?ExtractAllWopiPropertiesFromWopiUrl@Url@Mso@@YA?AW4WopiResult@12@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@111_N@Z` at `0x180c2efbf`
- `Mso30Win32Client!__imp_?ExtractAllWopiPropertiesFromWopiUrl@Url@Mso@@YA?AW4WopiResult@12@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@111_N@Z` at `0x180c2de97`
- `Mso30Win32Client!__imp_?ExtractAllWopiPropertiesFromWopiUrl@Url@Mso@@YA?AW4WopiResult@12@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@111_N@Z` at `0x180c2e099`
- `Mso30Win32Client!__imp_?ExtractAllWopiPropertiesFromWopiUrl@Url@Mso@@YA?AW4WopiResult@12@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@111_N@Z` at `0x180c2efbf`
- `Mso30Win32Client!__imp_?CreateHRESULTError@MsoCF@@YAXJPEAPEAUIError@1@@Z` at `0x180c2e583`
- `Mso30Win32Client!__imp_?CreateHRESULTError@MsoCF@@YAXJPEAPEAUIError@1@@Z` at `0x180c2e583`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x180c2deff`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x180c2e0f0`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x180c2e1b7`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x180c2e300`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x180c2e3c4`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x180c2ed7c`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x180c2f32f`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x180c2f489`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x180c2f540`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x180c2deff`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x180c2e0f0`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x180c2e1b7`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x180c2e300`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x180c2e3c4`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x180c2ed7c`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x180c2f32f`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x180c2f489`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x180c2f540`
- `Mso30Win32Client!__imp_?GetAlertIdFromMsoIds@Alerts@Mso@@YAHH@Z` at `0x180c2edcd`
- `Mso30Win32Client!__imp_?GetAlertIdFromMsoIds@Alerts@Mso@@YAHH@Z` at `0x180c2edcd`
- `Mso30Win32Client!__imp_?CreateHRESULTErrorTag@MsoCF@@YAXJPEAPEAUIError@1@K@Z` at `0x180c2fa0f`
- `Mso30Win32Client!__imp_?CreateHRESULTErrorTag@MsoCF@@YAXJPEAPEAUIError@1@K@Z` at `0x180c2fa0f`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x180c2df6d`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x180c2e167`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x180c2e267`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x180c2e36e`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x180c2e43d`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x180c2ee0c`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x180c2f3df`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x180c2f504`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x180c2f5ae`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x180c2df6d`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x180c2e167`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x180c2e267`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x180c2e36e`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x180c2e43d`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x180c2ee0c`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x180c2f3df`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x180c2f504`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x180c2f5ae`
- `Mso30Win32Client!__imp_?FNetworkExists@NetCost@Mso@@YA_NXZ` at `0x180c2e665`
- `Mso30Win32Client!__imp_?FNetworkExists@NetCost@Mso@@YA_NXZ` at `0x180c2e665`
- `Mso30Win32Client!__imp_?GetWatsonAlertIdFromMsoIds@Alerts@Mso@@YAIH@Z` at `0x180c2edea`
- `Mso30Win32Client!__imp_?GetWatsonAlertIdFromMsoIds@Alerts@Mso@@YAIH@Z` at `0x180c2edea`
- `Mso30Win32Client!__imp_?CreateCsiErrorTag@Csi@@YAXVCsiErrorCode@1@PEAPEAUIError@MsoCF@@K@Z` at `0x180c2dcfc`
- `Mso30Win32Client!__imp_?CreateCsiErrorTag@Csi@@YAXVCsiErrorCode@1@PEAPEAUIError@MsoCF@@K@Z` at `0x180c2dfcd`
- `Mso30Win32Client!__imp_?CreateCsiErrorTag@Csi@@YAXVCsiErrorCode@1@PEAPEAUIError@MsoCF@@K@Z` at `0x180c2eef6`
- `Mso30Win32Client!__imp_?CreateCsiErrorTag@Csi@@YAXVCsiErrorCode@1@PEAPEAUIError@MsoCF@@K@Z` at `0x180c2f83a`
- `Mso30Win32Client!__imp_?CreateCsiErrorTag@Csi@@YAXVCsiErrorCode@1@PEAPEAUIError@MsoCF@@K@Z` at `0x180c2f97c`
- `Mso30Win32Client!__imp_?CreateCsiErrorTag@Csi@@YAXVCsiErrorCode@1@PEAPEAUIError@MsoCF@@K@Z` at `0x180c2dcfc`
- `Mso30Win32Client!__imp_?CreateCsiErrorTag@Csi@@YAXVCsiErrorCode@1@PEAPEAUIError@MsoCF@@K@Z` at `0x180c2dfcd`
- `Mso30Win32Client!__imp_?CreateCsiErrorTag@Csi@@YAXVCsiErrorCode@1@PEAPEAUIError@MsoCF@@K@Z` at `0x180c2eef6`
- `Mso30Win32Client!__imp_?CreateCsiErrorTag@Csi@@YAXVCsiErrorCode@1@PEAPEAUIError@MsoCF@@K@Z` at `0x180c2f83a`
- `Mso30Win32Client!__imp_?CreateCsiErrorTag@Csi@@YAXVCsiErrorCode@1@PEAPEAUIError@MsoCF@@K@Z` at `0x180c2f97c`
- `Mso30Win32Client!__imp_MsoFLoadWz` at `0x180c2ed72`
- `Mso30Win32Client!__imp_MsoFLoadWz` at `0x180c2ed72`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x180c2df8a`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x180c2e181`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x180c2e284`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x180c2e38b`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x180c2e45a`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x180c2ee26`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x180c2f3fc`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x180c2f51e`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x180c2f5cb`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x180c2df8a`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x180c2e181`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x180c2e284`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x180c2e38b`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x180c2e45a`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x180c2ee26`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x180c2f3fc`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x180c2f51e`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x180c2f5cb`
- `Mso30Win32Client!__imp_?MsoLocLibraryFromAlias@@YAPEAUHINSTANCE__@@K@Z` at `0x180c2ed55`
- `Mso30Win32Client!__imp_?MsoLocLibraryFromAlias@@YAPEAUHINSTANCE__@@K@Z` at `0x180c2ed55`
- `Mso30Win32Client!__imp_?GetAlertMessageFromMsoIds@Alerts@Mso@@YA?AUAlertMessage@12@HAEBV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@Z` at `0x180c2df45`
- `Mso30Win32Client!__imp_?GetAlertMessageFromMsoIds@Alerts@Mso@@YA?AUAlertMessage@12@HAEBV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@Z` at `0x180c2e13b`
- `Mso30Win32Client!__imp_?GetAlertMessageFromMsoIds@Alerts@Mso@@YA?AUAlertMessage@12@HAEBV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@Z` at `0x180c2e234`
- `Mso30Win32Client!__imp_?GetAlertMessageFromMsoIds@Alerts@Mso@@YA?AUAlertMessage@12@HAEBV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@Z` at `0x180c2e346`
- `Mso30Win32Client!__imp_?GetAlertMessageFromMsoIds@Alerts@Mso@@YA?AUAlertMessage@12@HAEBV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@Z` at `0x180c2e40a`
- `Mso30Win32Client!__imp_?GetAlertMessageFromMsoIds@Alerts@Mso@@YA?AUAlertMessage@12@HAEBV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@Z` at `0x180c2f3ac`
- `Mso30Win32Client!__imp_?GetAlertMessageFromMsoIds@Alerts@Mso@@YA?AUAlertMessage@12@HAEBV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@Z` at `0x180c2f4d4`
- `Mso30Win32Client!__imp_?GetAlertMessageFromMsoIds@Alerts@Mso@@YA?AUAlertMessage@12@HAEBV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@Z` at `0x180c2f586`
- `Mso30Win32Client!__imp_?GetAlertMessageFromMsoIds@Alerts@Mso@@YA?AUAlertMessage@12@HAEBV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@Z` at `0x180c2df45`
- `Mso30Win32Client!__imp_?GetAlertMessageFromMsoIds@Alerts@Mso@@YA?AUAlertMessage@12@HAEBV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@Z` at `0x180c2e13b`
- `Mso30Win32Client!__imp_?GetAlertMessageFromMsoIds@Alerts@Mso@@YA?AUAlertMessage@12@HAEBV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@Z` at `0x180c2e234`
- `Mso30Win32Client!__imp_?GetAlertMessageFromMsoIds@Alerts@Mso@@YA?AUAlertMessage@12@HAEBV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@Z` at `0x180c2e346`
- `Mso30Win32Client!__imp_?GetAlertMessageFromMsoIds@Alerts@Mso@@YA?AUAlertMessage@12@HAEBV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@Z` at `0x180c2e40a`
- `Mso30Win32Client!__imp_?GetAlertMessageFromMsoIds@Alerts@Mso@@YA?AUAlertMessage@12@HAEBV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@Z` at `0x180c2f3ac`
- `Mso30Win32Client!__imp_?GetAlertMessageFromMsoIds@Alerts@Mso@@YA?AUAlertMessage@12@HAEBV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@Z` at `0x180c2f4d4`
- `Mso30Win32Client!__imp_?GetAlertMessageFromMsoIds@Alerts@Mso@@YA?AUAlertMessage@12@HAEBV?$initializer_list@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@std@@@Z` at `0x180c2f586`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180c2dabf`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180c2fcaf`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180c2fe02`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180c2dabf`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180c2fcaf`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180c2fe02`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x180c2eb24`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x180c2f1f4`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x180c2fc81`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x180c2fdd5`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x180c2eb24`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x180c2f1f4`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x180c2fc81`
- `Mso20Win32Client!__imp_??1CMsoUrlSimple@@UEAA@XZ` at `0x180c2fdd5`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180c2fe47`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180c2fe81`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180c2fea6`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180c2fe47`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180c2fe81`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180c2fea6`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180c2e95f`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180c2e95f`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2d978`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2d996`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2db1b`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2db3c`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2db5d`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2db91`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2dbc9`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2e6a1`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2e6c6`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2e6fa`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2e738`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2e75d`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2ea1e`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2ea73`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2eb82`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2f6a7`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2f93b`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2faf7`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2fb95`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2d978`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2d996`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2db1b`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2db3c`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2db5d`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2db91`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2dbc9`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2e6a1`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2e6c6`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2e6fa`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2e738`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2e75d`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2ea1e`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2ea73`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2eb82`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2f6a7`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2f93b`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2faf7`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x180c2fb95`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180c2fe59`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180c2fe67`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180c2fe75`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180c2feb8`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180c2fe59`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180c2fe67`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180c2fe75`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180c2feb8`
- `Mso20Win32Client!__imp_??0CMsoUrlSimple@@QEAA@XZ` at `0x180c2e54c`
- `Mso20Win32Client!__imp_??0CMsoUrlSimple@@QEAA@XZ` at `0x180c2e54c`
- `Mso20Win32Client!__imp_?UseCurrentExecutionContext@ApplicationModel@Mso@@YAAEAUIExecutionContext@12@XZ` at `0x180c2f012`
- `Mso20Win32Client!__imp_?UseCurrentExecutionContext@ApplicationModel@Mso@@YAAEAUIExecutionContext@12@XZ` at `0x180c2f012`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x180c2dab4`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x180c2fca4`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x180c2fdf7`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x180c2dab4`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x180c2fca4`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x180c2fdf7`

## string_xrefs

- `0x180c2ea34`: `AsyncOpenKind`
- `0x180c2f2ad`: `csierrWopi_InvalidUrl on open, could not prompt for creds`
- `0x180c2e84d`: `CsiCacheFileSessionBegunWithClosedFile`
- `0x180c2eb91`: `HrEnsureDownloadTaskDidNotRun`
- `0x180c2ea8b`: `CsiGetFileFromCacheMetaData`
- `0x180c2f6bf`: `CsiGetFileFromCacheMetaData`
- `0x180c2f107`: `csierrWopi_InvalidUrl on open, prompted for creds`
- `0x180c2e76e`: `OpenOffline`
- `0x180c2e70b`: `updatedRecoveryMode`
- `0x180c2e6d5`: `isFileCachedBeforeOpen`
- `0x180c2d982`: `OpenFileState_Requested`
- `0x180c2dbd3`: `OpenFileState_LegacyFallback`
- `0x180c2fba1`: `TempFileGenerated`
- `0x180c2db28`: `Protocol`

## pseudocode

```c
__int64 __fastcall CMsoOLDocFile::FCsiGetFile(
        const wchar_t **this,
        char a2,
        __int64 a3,
        char a4,
        struct IMsoTask *a5,
        struct MsoCF::IError **a6,
        bool *a7)
{
  char v7; // bl
  bool v8; // di
  CMsoOLDocFile *v10; // rsi
  char v11; // r12
  unsigned int v12; // r14d
  const struct Mso::Telemetry::EventFlags *v13; // rbx
  const struct Mso::Telemetry::EventName *v14; // rax
  __int64 v15; // r13
  struct Mso::Telemetry::IDataFieldCollection *v16; // rax
  __int64 v17; // r8
  struct Mso::Telemetry::IDataFieldCollection *v18; // rbx
  unsigned int FBlockNetworkCalls; // eax
  int v20; // r9d
  __int64 v21; // rax
  __int64 v22; // r8
  unsigned int v23; // r9d
  struct Mso::Telemetry::IDataFieldCollection *v25; // rax
  struct Mso::Telemetry::IDataFieldCollection *v26; // rax
  __int64 v27; // r8
  __int64 v28; // r10
  struct Mso::Telemetry::IDataFieldCollection *v29; // rax
  __int64 v30; // r8
  struct Mso::Telemetry::IDataFieldCollection *v31; // rax
  __int64 v32; // r8
  HWND v33; // rbx
  const struct MsoCF::IError *v34; // rdx
  const struct MsoCF::IError *v35; // rdx
  unsigned int v36; // r9d
  __int64 v37; // r8
  unsigned int v38; // r9d
  Mso::ResourceInfo *v39; // rcx
  struct MsoCF::IError *v40; // rdx
  unsigned int v41; // r9d
  Mso::OfficeServicesManager *v42; // rcx
  struct Mso::OfficeServicesManager::IOfficeServicesManager *v43; // rax
  struct Mso::OfficeServicesManager::IOfficeServicesManager *v44; // rcx
  __int64 v45; // rax
  __int128 *v46; // r8
  const WCHAR *v47; // rbx
  const WCHAR *v48; // rax
  __int64 v49; // rax
  Mso::Alerts *v50; // rcx
  const struct MsoReserveTag *v51; // rax
  const struct Mso::Alerts::AlertParam *v52; // r9
  Csi *v53; // rcx
  unsigned int v54; // r9d
  Mso::OfficeServicesManager *v55; // rcx
  struct Mso::OfficeServicesManager::IOfficeServicesManager *Instance; // rax
  struct Mso::OfficeServicesManager::IOfficeServicesManager *v57; // rcx
  __int64 v58; // rax
  __int128 *v59; // r8
  WCHAR *v60; // rax
  __int64 v61; // rax
  Mso::Alerts *v62; // rcx
  const struct MsoReserveTag *v63; // rax
  const struct Mso::Alerts::AlertParam *v64; // r9
  _BYTE *v65; // rcx
  __int64 v66; // rax
  __int64 v67; // rbx
  __int128 *v68; // rax
  const WCHAR *v69; // rax
  __int64 v70; // rax
  Mso::Alerts *v71; // rcx
  const struct MsoReserveTag *v72; // rax
  const struct Mso::Alerts::AlertParam *v73; // r9
  __int128 *v74; // rcx
  const WCHAR *v75; // rbx
  const WCHAR *v76; // rax
  __int64 AlertMessageFromMsoIds; // rax
  Mso::Alerts *v78; // rcx
  const struct MsoReserveTag *TelemetryNamespace; // rax
  const struct Mso::Alerts::AlertParam *v80; // r9
  __int64 v81; // rax
  __int64 v82; // rbx
  const WCHAR *v83; // rax
  __int64 v84; // rax
  Mso::Alerts *v85; // rcx
  const struct MsoReserveTag *v86; // rax
  const struct Mso::Alerts::AlertParam *v87; // r9
  struct MsoCF::IError **v88; // rbx
  int v89; // eax
  struct MsoCF::IError **v90; // r8
  unsigned int v91; // r9d
  Mso::NetCost *v92; // rcx
  __int64 v93; // rax
  __int64 v94; // rax
  __int64 v95; // r8
  __int64 v96; // rdx
  __int64 v97; // rax
  __int64 v98; // r8
  char IsFileCached; // bl
  struct Mso::Telemetry::IDataFieldCollection *v100; // rax
  __int64 v101; // r8
  struct Mso::Telemetry::IDataFieldCollection *v102; // rax
  __int64 v103; // r8
  bool v104; // al
  struct Mso::Telemetry::IDataFieldCollection *v105; // rax
  __int64 v106; // r8
  bool v107; // zf
  bool v108; // al
  struct Mso::Telemetry::IDataFieldCollection *v109; // rax
  __int64 v110; // r8
  struct Mso::Telemetry::IDataFieldCollection *v111; // rax
  __int64 v112; // r8
  int v113; // r9d
  wchar_t *v114; // rax
  __int64 v115; // r8
  __int64 v116; // rsi
  __int64 v117; // rdi
  __int64 v118; // rbx
  __int64 v119; // rax
  bool v120; // al
  bool v121; // al
  Csi *v122; // rbx
  Csi *v123; // rcx
  __int64 v124; // rax
  struct Mso::Telemetry::IDataFieldCollection *v125; // rbx
  unsigned int *v126; // rax
  Mso::Telemetry::IDataFieldCollection *v127; // rbx
  bool v128; // dl
  const struct Mso::Telemetry::IDataContract *FileFromCacheMetaData; // rax
  const struct Mso::Telemetry::ISingleDataField *v130; // rax
  bool v131; // r8
  struct MsoCF::IError *v132; // rax
  unsigned int v133; // r9d
  struct Csi::IDocumentProperties *v134; // rcx
  struct IMsoOLDocumentAsyncDownloadParams *v135; // rbx
  struct Mso::Telemetry::IDataFieldCollection *v136; // rax
  __int64 v137; // r8
  struct IUnknown *v138; // rcx
  unsigned __int64 v139; // rcx
  const unsigned __int8 *v140; // rdx
  unsigned __int64 appended; // rbx
  __int64 v142; // rdx
  __int64 v143; // rdx
  __int64 v144; // r8
  __int64 v145; // rcx
  unsigned int v146; // r9d
  HINSTANCE v147; // rax
  __int64 v148; // r8
  int v149; // edx
  int v150; // edx
  Mso::Alerts *v151; // rcx
  const struct MsoReserveTag *v152; // rax
  const struct Mso::Alerts::AlertParam *v153; // r9
  __int64 v154; // r8
  struct Mso::Telemetry::Activity *v155; // rdx
  struct Csi::IDocumentProperties *v156; // rcx
  struct MsoCF::IError *v157; // rdx
  Csi *v158; // rcx
  unsigned int v159; // r9d
  __m128i v160; // xmm6
  Mso::OfficeServicesManager *v161; // rcx
  struct Mso::OfficeServicesManager::IOfficeServicesManager *v162; // rax
  struct Mso::OfficeServicesManager::IOfficeServicesManager *v163; // rcx
  __int64 v164; // rax
  __int128 *v165; // r8
  Mso::ApplicationModel *v166; // rcx
  __int64 v167; // rax
  const struct Mso::Authentication::UIExecutionContext *v168; // r9
  const struct IMsoUrl *v169; // rdx
  int v170; // ebx
  int v171; // r9d
  WCHAR **v172; // rcx
  struct Csi::IDocumentProperties *v173; // rcx
  char v174; // al
  __int64 v175; // rax
  __int64 v176; // rbx
  void **v177; // rax
  const WCHAR *v178; // rax
  __int64 v179; // rax
  Mso::Alerts *v180; // rcx
  const struct MsoReserveTag *v181; // rax
  const struct Mso::Alerts::AlertParam *v182; // r9
  WCHAR **v183; // rcx
  WCHAR *v184; // rax
  __int64 v185; // rax
  Mso::Alerts *v186; // rcx
  const struct MsoReserveTag *v187; // rax
  const struct Mso::Alerts::AlertParam *v188; // r9
  const WCHAR *v189; // rbx
  const WCHAR *v190; // rax
  __int64 v191; // rax
  Mso::Alerts *v192; // rcx
  const struct MsoReserveTag *v193; // rax
  const struct Mso::Alerts::AlertParam *v194; // r9
  char *v195; // rbx
  struct MsoCF::IError *v196; // rdx
  char v197; // r13
  __int64 v198; // rdx
  __int64 v199; // r8
  Mso::Telemetry::IDataFieldCollection *v200; // rbx
  bool v201; // dl
  const struct Mso::Telemetry::IDataContract *v202; // rax
  const struct Mso::Telemetry::ISingleDataField *v203; // rax
  Csi *v204; // rbx
  struct IMsoOLDocument *v205; // rdx
  struct IMsoOLDocument *v206; // rdx
  WCHAR **v207; // rbx
  struct Mso::Telemetry::IDataFieldCollection *v208; // rax
  __int64 v209; // r8
  Csi *v210; // rdi
  __int64 v211; // r9
  __int64 v212; // r8
  unsigned int v213; // r9d
  __int64 v214; // rax
  struct MsoCF::IError *v215; // rax
  const wchar_t **Controller; // rax
  const wchar_t *v217; // rdx
  const wchar_t *v218; // rcx
  const char *v219; // rcx
  int v220; // edi
  struct Mso::Telemetry::IDataFieldCollection *v221; // rax
  __int64 v222; // r8
  unsigned int v223; // r9d
  __int64 v224; // r8
  struct Mso::Telemetry::IDataFieldCollection *v225; // rax
  __int64 v226; // r8
  __int64 v227; // rax
  const wchar_t *v228; // rax
  const struct IMsoUrl *v229; // rdx
  bool v230; // r8
  bool v231; // bl
  bool v232; // cf
  DWORD FileAttributesW; // eax
  int v234; // [rsp+20h] [rbp-E0h]
  int v235; // [rsp+28h] [rbp-D8h]
  int v236; // [rsp+28h] [rbp-D8h]
  bool v237; // [rsp+40h] [rbp-C0h] BYREF
  Csi *v238; // [rsp+48h] [rbp-B8h] BYREF
  bool v239; // [rsp+50h] [rbp-B0h] BYREF
  char v240; // [rsp+51h] [rbp-AFh]
  char v241; // [rsp+52h] [rbp-AEh]
  bool v242; // [rsp+53h] [rbp-ADh] BYREF
  _BYTE v243[4]; // [rsp+54h] [rbp-ACh] BYREF
  const char *v244; // [rsp+58h] [rbp-A8h] BYREF
  struct Csi::IDocumentProperties *v245; // [rsp+60h] [rbp-A0h] BYREF
  struct IUnknown *v246; // [rsp+68h] [rbp-98h] BYREF
  struct MsoCF::IError **v247; // [rsp+70h] [rbp-90h] BYREF
  bool v248[16]; // [rsp+78h] [rbp-88h] BYREF
  bool v249; // [rsp+88h] [rbp-78h]
  unsigned int v250; // [rsp+8Ch] [rbp-74h] BYREF
  __int64 v251; // [rsp+90h] [rbp-70h] BYREF
  WCHAR *v252; // [rsp+98h] [rbp-68h] BYREF
  struct MsoCF::IError ***v253; // [rsp+A0h] [rbp-60h]
  bool v254; // [rsp+A8h] [rbp-58h] BYREF
  char v255; // [rsp+A9h] [rbp-57h]
  const char *v256; // [rsp+B0h] [rbp-50h] BYREF
  bool *v257; // [rsp+B8h] [rbp-48h]
  WCHAR **v258; // [rsp+C0h] [rbp-40h] BYREF
  bool *v259; // [rsp+C8h] [rbp-38h]
  __int64 v260; // [rsp+D0h] [rbp-30h] BYREF
  int v261; // [rsp+D8h] [rbp-28h]
  __int64 v262; // [rsp+E0h] [rbp-20h]
  _BYTE v263[40]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v264[32]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v265[32]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v266[32]; // [rsp+150h] [rbp+50h] BYREF
  int AlertIdFromMsoIds; // [rsp+170h] [rbp+70h]
  char v268; // [rsp+174h] [rbp+74h]
  __int16 v269; // [rsp+175h] [rbp+75h]
  char v270; // [rsp+177h] [rbp+77h]
  unsigned int WatsonAlertIdFromMsoIds; // [rsp+178h] [rbp+78h]
  char v272; // [rsp+17Ch] [rbp+7Ch]
  __int16 v273; // [rsp+17Dh] [rbp+7Dh]
  char v274; // [rsp+17Fh] [rbp+7Fh]
  char v275; // [rsp+188h] [rbp+88h]
  void *v276; // [rsp+1C8h] [rbp+C8h]
  _BYTE v277[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v278[88]; // [rsp+200h] [rbp+100h] BYREF
  char v279; // [rsp+258h] [rbp+158h]
  const char *v280; // [rsp+298h] [rbp+198h]
  __int128 v281; // [rsp+2B0h] [rbp+1B0h] BYREF
  struct MsoCF::IError ***v282; // [rsp+2C0h] [rbp+1C0h]
  unsigned __int64 v283; // [rsp+2C8h] [rbp+1C8h]
  __int128 v284; // [rsp+2D0h] [rbp+1D0h] BYREF
  __m128i v285; // [rsp+2E0h] [rbp+1E0h]
  unsigned __int8 *v286[2]; // [rsp+2F0h] [rbp+1F0h] BYREF
  __m128i v287; // [rsp+300h] [rbp+200h]
  void **v288; // [rsp+310h] [rbp+210h] BYREF
  const char *v289; // [rsp+318h] [rbp+218h]
  _BYTE v290[24]; // [rsp+320h] [rbp+220h] BYREF
  __m128i v291; // [rsp+338h] [rbp+238h] BYREF
  Csi **v292; // [rsp+348h] [rbp+248h]
  __int64 v293; // [rsp+350h] [rbp+250h]
  __int128 v294; // [rsp+370h] [rbp+270h] BYREF
  __m128i si128; // [rsp+380h] [rbp+280h]
  __int128 v296; // [rsp+390h] [rbp+290h] BYREF
  __m128i v297; // [rsp+3A0h] [rbp+2A0h]
  void **v298; // [rsp+3B0h] [rbp+2B0h] BYREF
  const char *v299; // [rsp+3B8h] [rbp+2B8h]
  const WCHAR *v300; // [rsp+3C0h] [rbp+2C0h]
  _OWORD v301[4]; // [rsp+3C8h] [rbp+2C8h] BYREF
  _BYTE v302[16]; // [rsp+410h] [rbp+310h] BYREF
  _BYTE v303[288]; // [rsp+420h] [rbp+320h] BYREF
  __int64 v304; // [rsp+540h] [rbp+440h] BYREF
  __int64 v305; // [rsp+548h] [rbp+448h]
  __int64 v306; // [rsp+550h] [rbp+450h]
  int v307; // [rsp+558h] [rbp+458h]
  __int64 v308; // [rsp+15A4h] [rbp+14A4h]
  char v309; // [rsp+15BCh] [rbp+14BCh]
  char v310; // [rsp+15C8h] [rbp+14C8h]
  _WORD v311[16]; // [rsp+15D0h] [rbp+14D0h] BYREF
  _BYTE v312[88]; // [rsp+15F0h] [rbp+14F0h] BYREF
  char v313; // [rsp+1648h] [rbp+1548h]
  WCHAR FileName[264]; // [rsp+19D0h] [rbp+18D0h] BYREF

  v255 = a4;
  v7 = a3;
  v249 = a3;
  v8 = a2;
  v241 = a2;
  v247 = a6;
  v258 = (WCHAR **)a7;
  v10 = (CMsoOLDocFile *)(this + 193);
  v11 = 1;
  v12 = 0;
  if ( a2 || CMsoOLDocFile::IsCobaltVersion((CMsoOLDocFile *)(this + 193)) )
    v250 = 6;
  else
    v250 = (v7 != 0) + 1;
  v240 = 0;
  LOBYTE(a3) = 110;
  v13 = (const struct Mso::Telemetry::EventFlags *)Mso::Telemetry::EventFlags::EventFlags(&v246, 2, a3);
  v256 = "FCsiGetFile";
  v14 = (const struct Mso::Telemetry::EventName *)Office::FileIO::MSO::EventName(&v252, &v256);
  Mso::Telemetry::Activity::Activity((Mso::Telemetry::Activity *)v248, v14, v13);
  v15 = -1;
  Mso::DocumentTelemetry::AddDocumentTelemetryToActivity<Mso::Telemetry::Activity,CMsoOLDocFile *,void>(
    &v244,
    v248,
    this,
    -1);
  v16 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v248);
  LOBYTE(v17) = v250;
  Mso::Telemetry::IDataFieldCollection::Add<unsigned char>(v16, "OpenFileState_Requested", v17);
  v18 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v248);
  FBlockNetworkCalls = CMsoOLDocBase::GetFBlockNetworkCalls((CMsoOLDocBase *)this);
  Mso::Telemetry::IDataFieldCollection::Add<int>(v18, "BlockNetworkCalls", FBlockNetworkCalls);
  v288 = &Mso::Diagnostics::ClassifiedStructuredObject<_GUID>::`vftable';
  v289 = "DocumentUniqueId";
  *(_OWORD *)v290 = *((_OWORD *)this + 15);
  *(_WORD *)&v290[16] = 256;
  v291 = 0;
  v292 = 0;
  v293 = 7;
  v291.m128i_i16[0] = 0;
  v256 = "OLDoc:FCsiGetFile";
  Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
    594334803,
    836,
    50,
    v20,
    (__int64)&v256,
    (__int64)&v288);
  std::basic_string<char16_t>::~basic_string<char16_t>(&v291);
  v21 = Measurements::Stopwatch::Stopwatch((Measurements::Stopwatch *)&v298);
  LOBYTE(v22) = 1;
  Measurements::MeasureElapsedTime::MeasureElapsedTime(v263, Measurements::MeasurementId::OLDocFCsiGetFile, v22, v21);
  *(_BYTE *)v258 = 0;
  if ( !*((_BYTE *)this + 1808) && !(unsigned int)CMsoOLDocFile::FInitCsiFileIO(v10, v247) )
  {
    Csi::SetActivityResultIErrorTag((Csi *)v248, *v247, (const struct MsoCF::IError *)0x15923E1, v23);
LABEL_8:
    Measurements::MeasureElapsedTime::~MeasureElapsedTime((Measurements::MeasureElapsedTime *)v263);
    Mso::Telemetry::Activity::~Activity((Mso::Telemetry::Activity *)v248);
    return 0;
  }
  v304 = 1;
  v305 = 0;
  v306 = 0;
  v307 = 0;
  v308 = 0;
  v309 = 0;
  v310 = 0;
  CMsoOLDocFile::GetCsiServerInfo(v10, (struct Csi::CsiServerInfo *)&v304, 0, 0);
  v25 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v248);
  Mso::Telemetry::IDataFieldCollection::Add<int>(v25, "Protocol", HIDWORD(v305));
  v26 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v248);
  Mso::Telemetry::IDataFieldCollection::Add<int>(v26, "ServerType", (unsigned int)v305);
  Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v248);
  LOBYTE(v27) = Csi::CsiServerInfo::IsCloudCollabEnabled((Csi::CsiServerInfo *)&v304);
  Mso::Telemetry::IDataFieldCollection::Add<bool>(v28, "CloudCollab", v27, 4);
  v29 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v248);
  LOBYTE(v30) = (_DWORD)v308 == 0;
  Mso::Telemetry::IDataFieldCollection::Add<bool>(v29, "IsWebUrlEmpty", v30, 4);
  if ( HIDWORD(v304) == 1 )
  {
    v250 = 6;
    v31 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v248);
    LOBYTE(v32) = v250;
    Mso::Telemetry::IDataFieldCollection::Add<unsigned char>(v31, "OpenFileState_LegacyFallback", v32);
    *((_DWORD *)this + 377) = 25236365;
    Mso::ReadOnlyReasonTracker::SetNonDownloadProtocolReadOnlyReason((char *)this + 1508, 34);
    v8 = 1;
    v241 = 1;
    v240 = 1;
  }
  v33 = HwndParentForDmEx(0);
  v256 = (const char *)v33;
  v238 = 0;
  BYTE1(v244) = 0;
  if ( (unsigned int)CMsoOLDocFile::FInitCsiFile(
                       (_DWORD)v10,
                       (unsigned int)&v238,
                       v250,
                       (unsigned int)&v304,
                       (unsigned __int8)v244) )
    goto LABEL_18;
  if ( !Csi::IsFileOpenForEditTakenError(v238, v34) )
  {
    if ( Csi::IsExpectedEdpError(v238, v35) )
    {
      MsoCF::CIPtr<MsoCF::IError,MsoCF::IError>::CopyTo(&v238, v247);
      v37 = 22619107;
      goto LABEL_16;
    }
    if ( (unsigned __int8)Csi::IsCsiError(v238, 141) )
    {
      MsoCF::CIPtr<MsoCF::IError,MsoCF::IError>::CopyTo(&v238, v247);
      Csi::SetActivityResultIErrorTag((Csi *)v248, *v247, (const struct MsoCF::IError *)0x2336260A, v38);
      ShowStorageOutOfCapacityAlert();
      goto LABEL_298;
    }
    if ( (v304 & 0x1000000000LL) == 0 )
      goto LABEL_327;
    if ( (unsigned __int8)Csi::IsCsiError(v238, 3526)
      || Mso::ResourceInfo::IsWopiPromptingOnOpenEnabled(v39) && Csi::IsWopiAuthenticationError(v238, v40) )
    {
      v53 = v238;
      v238 = 0;
      if ( v53 )
        (*(void (__fastcall **)(Csi *))(*(_QWORD *)v53 + 16LL))(v53);
      Csi::CreateCsiErrorTag(5600, &v238, 541909526);
      MsoCF::CIPtr<MsoCF::IError,MsoCF::IError>::CopyTo(&v238, v247);
      Csi::SetActivityResultIErrorTag((Csi *)v248, *v247, (const struct MsoCF::IError *)0x204CE215, v54);
      v294 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v294) = 0;
      v284 = 0;
      v285 = si128;
      LOWORD(v284) = 0;
      *(_OWORD *)v286 = 0;
      v287 = si128;
      LOWORD(v286[0]) = 0;
      v281 = 0;
      v282 = 0;
      v283 = 7;
      LOWORD(v281) = 0;
      LOBYTE(v235) = 0;
      if ( (unsigned int)Mso::Url::ExtractAllWopiPropertiesFromWopiUrl(this[36], &v294, &v284, v286, &v281, v235) )
      {
        v75 = this[36];
        Mso::Alerts::CreateDefaultAlertParam(v311);
        v76 = &ShortName;
        if ( v75 )
          v76 = v75;
        v252 = (WCHAR *)v76;
        do
          ++v15;
        while ( v76[v15] );
        v253 = (struct MsoCF::IError ***)v15;
        v256 = (const char *)&v252;
        v257 = &v254;
        AlertMessageFromMsoIds = Mso::Alerts::GetAlertMessageFromMsoIds(&v288, 38601128, &v256);
        Mso::Alerts::AlertMessage::operator=(v312, AlertMessageFromMsoIds);
        Mso::Help::Core::AuthInfo::~AuthInfo((Mso::Help::Core::AuthInfo *)&v288);
        v313 = 3;
        TelemetryNamespace = Mso::Alerts::GetTelemetryNamespace(v78);
        LODWORD(v244) = 509354626;
        Mso::Alerts::ShowAlert(
          (Mso::Alerts *)&v244,
          TelemetryNamespace,
          (const struct Mso::Telemetry::TelemetryNamespace *)v311,
          v80);
        std::pair<std::wstring const,Mso::History::FileInfo>::~pair<std::wstring const,Mso::History::FileInfo>(v311);
      }
      else
      {
        Instance = Mso::OfficeServicesManager::GetInstance(v55);
        v57 = Instance;
        if ( !Instance )
        {
LABEL_321:
          CrashWithRecovery(0x204CE214u, 0);
          goto LABEL_322;
        }
        v58 = *(_QWORD *)Instance;
        v59 = &v284;
        if ( v285.m128i_i64[1] > 7uLL )
          v59 = (__int128 *)v284;
        (*(void (__fastcall **)(struct Mso::OfficeServicesManager::IOfficeServicesManager *, struct IUnknown **, __int128 *))(v58 + 8))(
          v57,
          &v246,
          v59);
        if ( v246 )
        {
          v66 = Mso::TCntPtr<Mso::Sharing::SharingResult<Mso::Sharing::MsoGetUserAttributesResponse>>::operator->(&v246);
          v67 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v66 + 128LL))(v66);
          Mso::Alerts::CreateDefaultAlertParam(v277);
          v68 = &v281;
          if ( v283 > 7 )
            v68 = (__int128 *)v281;
          *(_QWORD *)&v296 = v68;
          *((_QWORD *)&v296 + 1) = v282;
          v69 = &ShortName;
          if ( v67 )
            v69 = (const WCHAR *)v67;
          v297.m128i_i64[0] = (__int64)v69;
          do
            ++v15;
          while ( v69[v15] );
          v297.m128i_i64[1] = v15;
          v252 = (WCHAR *)&v296;
          v253 = (struct MsoCF::IError ***)&v298;
          v70 = Mso::Alerts::GetAlertMessageFromMsoIds(&v288, 39819150, &v252);
          Mso::Alerts::AlertMessage::operator=(v278, v70);
          Mso::Help::Core::AuthInfo::~AuthInfo((Mso::Help::Core::AuthInfo *)&v288);
          v279 = 1;
          v280 = v256;
          v72 = Mso::Alerts::GetTelemetryNamespace(v71);
          LODWORD(v244) = 509354628;
          Mso::Alerts::ShowAlert(
            (Mso::Alerts *)&v244,
            v72,
            (const struct Mso::Telemetry::TelemetryNamespace *)v277,
            v73);
          v65 = v277;
        }
        else
        {
          Mso::Alerts::CreateDefaultAlertParam(v264);
          v60 = (WCHAR *)&v281;
          if ( v283 > 7 )
            v60 = (WCHAR *)v281;
          v252 = v60;
          v253 = v282;
          v256 = (const char *)&v252;
          v257 = &v254;
          v61 = Mso::Alerts::GetAlertMessageFromMsoIds(&v288, 3391383533LL, &v256);
          Mso::Alerts::AlertMessage::operator=(v265, v61);
          Mso::Help::Core::AuthInfo::~AuthInfo((Mso::Help::Core::AuthInfo *)&v288);
          v275 = 1;
          v276 = v33;
          v63 = Mso::Alerts::GetTelemetryNamespace(v62);
          LODWORD(v244) = 509354627;
          Mso::Alerts::ShowAlert(
            (Mso::Alerts *)&v244,
            v63,
            (const struct Mso::Telemetry::TelemetryNamespace *)v264,
            v64);
          v65 = v264;
        }
        std::pair<std::wstring const,Mso::History::FileInfo>::~pair<std::wstring const,Mso::History::FileInfo>(v65);
        Mso::TCntPtr<CBackgroundPullNetDocCycle>::~TCntPtr<CBackgroundPullNetDocCycle>(&v246);
      }
      std::basic_string<char16_t>::~basic_string<char16_t>(&v281);
      std::basic_string<char16_t>::~basic_string<char16_t>(v286);
      std::basic_string<char16_t>::~basic_string<char16_t>(&v284);
      v74 = &v294;
      goto LABEL_60;
    }
    if ( (v304 & 0x1000000000LL) == 0 || !(unsigned __int8)Csi::IsCsiError(v238, 5630) )
    {
LABEL_327:
      if ( (unsigned __int8)Csi::IsCsiError(v238, 1930) )
      {
        MsoCF::CIPtr<MsoCF::IError,MsoCF::IError>::CopyTo(&v238, v247);
        v37 = 537190478;
        goto LABEL_16;
      }
      if ( (unsigned __int8)Csi::IsCsiError(v238, 7209) )
      {
        MsoCF::CIPtr<MsoCF::IError,MsoCF::IError>::CopyTo(&v238, v247);
        v37 = 526513741;
        goto LABEL_16;
      }
LABEL_322:
      MsoShipAssertTagProc(22619136);
      MsoCF::CIPtr<MsoCF::IError,MsoCF::IError>::CopyTo(&v238, v247);
      v37 = 22619137;
      goto LABEL_16;
    }
    MsoCF::CIPtr<MsoCF::IError,MsoCF::IError>::CopyTo(&v238, v247);
    Csi::SetActivityResultIErrorTag((Csi *)v248, *v247, (const struct MsoCF::IError *)0x1E24D682, v41);
    v296 = 0;
    v297 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v296) = 0;
    v284 = 0;
    v285 = v297;
    LOWORD(v284) = 0;
    v294 = 0;
    si128 = v297;
    LOWORD(v294) = 0;
    *(_OWORD *)v286 = 0;
    v287 = v297;
    LOWORD(v286[0]) = 0;
    LOBYTE(v235) = 0;
    if ( !(unsigned int)Mso::Url::ExtractAllWopiPropertiesFromWopiUrl(this[36], &v296, &v284, &v294, v286, v235) )
    {
      v43 = Mso::OfficeServicesManager::GetInstance(v42);
      v44 = v43;
      if ( !v43 )
      {
LABEL_320:
        CrashWithRecovery(0x1E24D681u, 0);
        goto LABEL_321;
      }
      v45 = *(_QWORD *)v43;
      v46 = &v284;
      if ( v285.m128i_i64[1] > 7uLL )
        v46 = (__int128 *)v284;
      (*(void (__fastcall **)(struct Mso::OfficeServicesManager::IOfficeServicesManager *, struct IUnknown **, __int128 *))(v45 + 8))(
        v44,
        &v246,
        v46);
      if ( v246 )
      {
        v81 = Mso::TCntPtr<Mso::Sharing::SharingResult<Mso::Sharing::MsoGetUserAttributesResponse>>::operator->(&v246);
        v82 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v81 + 128LL))(v81);
        Mso::Alerts::CreateDefaultAlertParam(v277);
        v83 = &ShortName;
        if ( v82 )
          v83 = (const WCHAR *)v82;
        v252 = (WCHAR *)v83;
        do
          ++v15;
        while ( v83[v15] );
        v253 = (struct MsoCF::IError ***)v15;
        v258 = &v252;
        v259 = &v254;
        v84 = Mso::Alerts::GetAlertMessageFromMsoIds(&v288, 3713772944LL, &v258);
        Mso::Alerts::AlertMessage::operator=(v278, v84);
        Mso::Help::Core::AuthInfo::~AuthInfo((Mso::Help::Core::AuthInfo *)&v288);
        v279 = 1;
        v280 = v256;
        v86 = Mso::Alerts::GetTelemetryNamespace(v85);
        LODWORD(v244) = 505730688;
        Mso::Alerts::ShowAlert((Mso::Alerts *)&v244, v86, (const struct Mso::Telemetry::TelemetryNamespace *)v277, v87);
        std::pair<std::wstring const,Mso::History::FileInfo>::~pair<std::wstring const,Mso::History::FileInfo>(v277);
        Mso::TCntPtr<CBackgroundPullNetDocCycle>::~TCntPtr<CBackgroundPullNetDocCycle>(&v246);
        goto LABEL_73;
      }
      Mso::TCntPtr<CBackgroundPullNetDocCycle>::~TCntPtr<CBackgroundPullNetDocCycle>(&v246);
    }
    v47 = this[36];
    Mso::Alerts::CreateDefaultAlertParam(v311);
    v48 = &ShortName;
    if ( v47 )
      v48 = v47;
    v252 = (WCHAR *)v48;
    do
      ++v15;
    while ( v48[v15] );
    v253 = (struct MsoCF::IError ***)v15;
    v256 = (const char *)&v252;
    v257 = &v254;
    v49 = Mso::Alerts::GetAlertMessageFromMsoIds(&v288, 38601128, &v256);
    Mso::Alerts::AlertMessage::operator=(v312, v49);
    Mso::Help::Core::AuthInfo::~AuthInfo((Mso::Help::Core::AuthInfo *)&v288);
    v313 = 3;
    v51 = Mso::Alerts::GetTelemetryNamespace(v50);
    LODWORD(v244) = 505730659;
    Mso::Alerts::ShowAlert((Mso::Alerts *)&v244, v51, (const struct Mso::Telemetry::TelemetryNamespace *)v311, v52);
    std::pair<std::wstring const,Mso::History::FileInfo>::~pair<std::wstring const,Mso::History::FileInfo>(v311);
LABEL_73:
    std::basic_string<char16_t>::~basic_string<char16_t>(v286);
    std::basic_string<char16_t>::~basic_string<char16_t>(&v294);
    std::basic_string<char16_t>::~basic_string<char16_t>(&v284);
    v74 = &v296;
LABEL_60:
    std::basic_string<char16_t>::~basic_string<char16_t>(v74);
LABEL_61:
    if ( v238 )
      (*(void (__fastcall **)(Csi *))(*(_QWORD *)v238 + 16LL))(v238);
    goto LABEL_8;
  }
  if ( !CMsoOLDocFile::TryFallbackToReadOnly(
          (CMsoOLDocFile *)this,
          &v238,
          (enum CAOpenFileState *)&v250,
          (const struct Csi::CsiServerInfo *)&v304) )
  {
    if ( v238 )
    {
      MsoCF::CIPtr<MsoCF::IError,MsoCF::IError>::CopyTo(&v238, v247);
      v37 = 22619106;
LABEL_16:
      Csi::SetActivityResultIErrorTag((Csi *)v248, *v247, (const struct MsoCF::IError *)v37, v36);
      goto LABEL_298;
    }
    CrashWithRecovery(0x20507C6u, 0);
    goto LABEL_320;
  }
  v8 = 1;
  v241 = 1;
  v240 = 1;
  CMsoOLDocBase::SetReadOnly(this, 25236366, 35);
  CMsoOLDocBase::SetAttrInAttrMask((CMsoOLDocBase *)this, 0, 0x4000u);
LABEL_18:
  if ( CMsoOLDocBase::IsCachedAsDistributedBlobsFile((CMsoOLDocBase *)this) )
  {
    Csi::CreateCsiErrorTag(2073, v247, 508072783);
    v37 = 524301536;
    goto LABEL_16;
  }
  LODWORD(v244) = 505448525;
  if ( !(unsigned __int8)CMsoOLDocFile::UpdateReadWriteMode(this, &v244, v250, v247) )
  {
    v37 = 22619138;
    goto LABEL_16;
  }
  CMsoOLDocBase::SetIsOpeningOfflineCopy((CMsoOLDocBase *)this, 0);
  CMsoUrlSimple::CMsoUrlSimple((CMsoUrlSimple *)v302);
  v88 = v247;
  v89 = CMsoUrlSimple::HrSetFromUser(v303, this[36], 0, 0, 0);
  if ( v89 < 0 )
  {
    if ( v88 )
      MsoCF::CreateHRESULTError((MsoCF *)(unsigned int)v89, (_DWORD)v88, v90);
    Mso::Telemetry::SetActivityResultHr(
      (Mso::Telemetry *)v248,
      (struct Mso::Telemetry::Activity *)0x804D000ELL,
      41947792,
      v91);
LABEL_297:
    CMsoUrlSimple::~CMsoUrlSimple((CMsoUrlSimple *)v302);
LABEL_298:
    if ( v238 )
      (*(void (__fastcall **)(Csi *))(*(_QWORD *)v238 + 16LL))(v238);
LABEL_300:
    Measurements::MeasureElapsedTime::~MeasureElapsedTime((Measurements::MeasureElapsedTime *)v263);
    Mso::Telemetry::Activity::~Activity((Mso::Telemetry::Activity *)v248);
    return v12;
  }
  v245 = 0;
  LODWORD(v244) = 560567331;
  CMsoOLDocBase::GetProperties((CMsoOLDocBase *)this, &v245, (const struct MsoReserveTag *)&v244);
  if ( v245 )
  {
    v93 = Mso::TCntPtr<Mso::Sharing::SharingResult<Mso::Sharing::MsoGetUserAttributesResponse>>::operator->(&v245);
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v93 + 224LL))(v93, *((unsigned int *)this + 336));
    if ( Mso::TitleBarSaveUi::AutoSaveAppSettingApi::IsAutoSaveDisabledByGroupPolicy() )
    {
      v94 = Mso::TCntPtr<Mso::Sharing::SharingResult<Mso::Sharing::MsoGetUserAttributesResponse>>::operator->(&v245);
      v95 = 0;
      v96 = 589882179;
    }
    else
    {
      if ( !*((_BYTE *)this + 1348) )
      {
LABEL_90:
        v97 = Mso::TCntPtr<Mso::Sharing::SharingResult<Mso::Sharing::MsoGetUserAttributesResponse>>::operator->(&v245);
        LOBYTE(v98) = *((_BYTE *)this + 1349);
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v97 + 456LL))(v97, 571802018, v98);
        goto LABEL_91;
      }
      v94 = Mso::TCntPtr<Mso::Sharing::SharingResult<Mso::Sharing::MsoGetUserAttributesResponse>>::operator->(&v245);
      LOBYTE(v95) = 1;
      v96 = 39171597;
    }
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v94 + 352LL))(v94, v96, v95);
    goto LABEL_90;
  }
LABEL_91:
  v242 = !Mso::NetCost::FNetworkExists(v92);
  v239 = (unsigned int)sub_180A53190(this[36]) != 0;
  IsFileCached = CMsoOLDocFile::IsFileCached(this + 196, 559257443);
  LOBYTE(v244) = IsFileCached;
  v100 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v248);
  LOBYTE(v101) = v239;
  Mso::Telemetry::IDataFieldCollection::Add<bool>(v100, "recoveryMode", v101, 4);
  v102 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v248);
  LOBYTE(v103) = IsFileCached;
  Mso::Telemetry::IDataFieldCollection::Add<bool>(v102, "isFileCachedBeforeOpen", v103, 4);
  v104 = v239;
  if ( v239 && !IsFileCached )
  {
    v239 = 0;
    v105 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v248);
    LOBYTE(v106) = v239;
    Mso::Telemetry::IDataFieldCollection::Add<bool>(v105, "updatedRecoveryMode", v106, 4);
    v104 = v239;
  }
  if ( v242 || (v107 = !v104, v108 = 1, !v107) )
    v108 = 0;
  v237 = v108;
  v109 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v248);
  LOBYTE(v110) = v237;
  Mso::Telemetry::IDataFieldCollection::Add<bool>(v109, "AsyncDownload", v110, 4);
  v111 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v248);
  LOBYTE(v112) = v242;
  Mso::Telemetry::IDataFieldCollection::Add<bool>(v111, "OpenOffline", v112, 4);
  v114 = (wchar_t *)L"true";
  if ( !v237 )
    v114 = (wchar_t *)L"false";
  v246 = (struct IUnknown *)v114;
  Mso::Logging::MsoSendTraceTag<wchar_t const *>(
    24162526,
    677,
    50,
    v113,
    (__int64)L"CMsoOLDocFile::FCsiGetFile: fAsyncDownload = %s",
    &v246);
  this[227] = 0;
  v251 = 0;
  if ( (int)CMsoOLDocBase::COpenGet((CMsoOLDocBase *)this) <= 0 )
  {
    v243[0] = 0;
    v246 = (struct IUnknown *)"IsDBF";
    v116 = Mso::Telemetry::DataField<bool>::DataField<bool>(&v288, &v246, v243, 4);
    v246 = (struct IUnknown *)"DocumentUniqueId";
    v117 = Mso::Telemetry::DataField<_GUID>::DataField<_GUID>(&v298, &v246, this + 30, 256);
    v118 = Mso::Telemetry::EventFlags::EventFlags(&v252, 2);
    v246 = (struct IUnknown *)"CsiCacheFileSessionBegunWithClosedFile";
    v119 = Office::FileIO::MSO::EventName(&v260, &v246);
    Mso::Telemetry::SendTelemetryEvent<Mso::Telemetry::DataField<_GUID>,Mso::Telemetry::DataField<bool>>(
      v119,
      v118,
      v117,
      v116);
    v10 = (CMsoOLDocFile *)(this + 193);
    v8 = v241;
    IsFileCached = (char)v244;
  }
  v254 = v242;
  v288 = (void **)this;
  v289 = (const char *)&v242;
  *(_QWORD *)v290 = &v239;
  *(_QWORD *)&v290[8] = &a5;
  *(_QWORD *)&v290[16] = &v250;
  v291.m128i_i64[0] = (__int64)&v254;
  v291.m128i_i64[1] = (__int64)&v237;
  v292 = &v238;
  v293 = (__int64)&v251;
  v243[0] = sub_18094144C(this + 136, &v288, v115, 558404548);
  if ( v237 )
  {
    if ( IsFileCached )
    {
      v246 = 0;
      if ( (int)CMsoOLDocFile::HrGetLastFileModifiedTime(this + 196, &v246, 559257441) >= 0 )
        this[87] = (const wchar_t *)v246;
    }
  }
  if ( byte_1822F3C70[0] < 0 )
    v120 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)byte_1822F3C70);
  else
    v120 = byte_1822F3C70[0] != 0;
  if ( v120 )
  {
    if ( !v237 )
    {
LABEL_122:
      if ( *((_DWORD *)this + 268) == 2 )
        CMsoOLDocFile::UpdateSyncBackedPropertiesFromIDocument((CMsoOLDocFile *)this);
      goto LABEL_124;
    }
    if ( v243[0] && v251 )
    {
LABEL_121:
      if ( v237 )
        goto LABEL_124;
      goto LABEL_122;
    }
    v237 = 0;
LABEL_117:
    v122 = (Csi *)this[232];
    if ( v122 )
      (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v122 + 8LL))(this[232]);
    v123 = v238;
    v107 = v238 == 0;
    v238 = v122;
    if ( !v107 )
      (*(void (__fastcall **)(Csi *))(*(_QWORD *)v123 + 16LL))(v123);
    goto LABEL_121;
  }
  if ( !v243[0] || (v121 = 1, !v251) )
    v121 = 0;
  v237 = v121;
  if ( !v121 )
    goto LABEL_117;
LABEL_124:
  v124 = Mso::TCntPtr<Mso::Sharing::SharingResult<Mso::Sharing::MsoGetUserAttributesResponse>>::operator->(&v245);
  (*(void (__fastcall **)(__int64, struct IUnknown **))(*(_QWORD *)v124 + 344LL))(v124, &v246);
  if ( BYTE4(v246) )
  {
    v125 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v248);
    v126 = (unsigned int *)std::_Optional_construct_base<unsigned int>::operator*(&v246);
    Mso::Telemetry::IDataFieldCollection::Add<unsigned int>(v125, "AsyncOpenKind", *v126);
  }
  if ( v243[0] )
  {
    CMsoOLDocFile::PrepareToShowSyncProgressUI((CMsoOLDocFile *)this, v8, v237, v245);
    if ( v237 )
    {
      v127 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v248);
      FileFromCacheMetaData = (const struct Mso::Telemetry::IDataContract *)Office::FileIO::MSO::CsiGetFileFromCacheMetaData::CsiGetFileFromCacheMetaData(
                                                                              (Office::FileIO::MSO::CsiGetFileFromCacheMetaData *)&v288,
                                                                              v128);
      v130 = (const struct Mso::Telemetry::ISingleDataField *)Mso::Telemetry::DataContractField::DataContractField(
                                                                (Mso::Telemetry::DataContractField *)&v298,
                                                                "CsiGetFileFromCacheMetaData",
                                                                FileFromCacheMetaData);
      Mso::Telemetry::IDataFieldCollection::Add(v127, v130);
      if ( this[232] && (unsigned __int8)Csi::IsCsiError(this[232], 4790) )
      {
        v132 = (struct MsoCF::IError *)Mso::TCntPtr<IMsoXmlSchema>::Copy(this + 232);
        *v247 = v132;
        Csi::SetActivityResultIErrorTag((Csi *)v248, v132, (const struct MsoCF::IError *)0x21112501, v133);
        if ( v251 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v251 + 16LL))(v251);
        v134 = v245;
        if ( v245 )
        {
          v245 = 0;
          (*(void (__fastcall **)(struct Csi::IDocumentProperties *))(*(_QWORD *)v134 + 16LL))(v134);
        }
        CMsoUrlSimple::~CMsoUrlSimple((CMsoUrlSimple *)v302);
        goto LABEL_61;
      }
      v135 = CMsoOLDocumentAsyncDownloadParams::CreateInstance(v242, v239, v131, v249);
      v246 = 0;
      if ( (**(int (__fastcall ***)(__int64, GUID *, struct IUnknown **))v251)(v251, &IID_IUnknown, &v246) < 0 )
      {
        v136 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v248);
        LOBYTE(v137) = 1;
        Mso::Telemetry::IDataFieldCollection::Add<bool>(v136, "HrEnsureDownloadTaskDidNotRun", v137, 4);
        *((_BYTE *)this + 1890) = 0;
      }
      else
      {
        CMsoOLDocFile::HrEnsureDownloadTask((CMsoOLDocFile *)this, v246, v135, 0);
      }
      v138 = v246;
      if ( v246 )
      {
        v246 = 0;
        ((void (__fastcall *)(struct IUnknown *))v138->lpVtbl->Release)(v138);
      }
      if ( v135 )
        (*(void (__fastcall **)(struct IMsoOLDocumentAsyncDownloadParams *))(*(_QWORD *)v135 + 16LL))(v135);
    }
    else
    {
      *((_BYTE *)this + 1890) = 0;
    }
  }
  std::wstring::wstring(v286, this[36]);
  v140 = (const unsigned __int8 *)v286;
  if ( v287.m128i_i64[1] > 7uLL )
    v140 = v286[0];
  appended = std::_Fnv1a_append_bytes(v139, v140, 2 * v287.m128i_i64[0]);
  v142 = *(_QWORD *)(std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
                       &Mso::OLDocumentApi::NetworkToggler::s_synchronousOpenURLs,
                       &v260,
                       v286,
                       appended)
                   + 8);
  if ( v142 )
  {
    std::_Hash<std::_Umap_traits<unsigned int,std::shared_ptr<FastAcc::Abstract::Object>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::shared_ptr<FastAcc::Abstract::Object>>>,0>>::_Erase_bucket(
      &Mso::OLDocumentApi::NetworkToggler::s_synchronousOpenURLs,
      v142,
      appended & qword_1822DCAF0);
    std::list<std::wstring>::_Unchecked_erase(&qword_1822DCAC8);
  }
  std::basic_string<char16_t>::~basic_string<char16_t>(v286);
  CMsoOLDocBase::DoUpdateServerReachability((CMsoOLDocBase *)this, (const struct IMsoUrl *)v303);
  if ( v237 )
    goto LABEL_271;
  if ( v243[0] )
  {
    if ( v242 )
    {
      v145 = 1601;
    }
    else
    {
      if ( !v239 )
      {
        *((_DWORD *)this + 244) = (_DWORD)this[122] & 0xFFFFFFEF | (16 * !v249);
        goto LABEL_157;
      }
      v145 = 1530;
    }
    Csi::CreateCsiError(v145, &v238);
  }
  else if ( !v238 )
  {
    MsoShipAssertTagProc(22619144);
  }
LABEL_157:
  if ( (v250 & 4) != 0 && !v8 )
  {
    v241 = 1;
    v240 = 1;
    *((_DWORD *)this + 377) = 25236367;
  }
  if ( !v238 )
  {
    Mso::TCntPtr<Mso::DocumentActivities::Common::TaskReassignment>::Clear(this + 232);
    goto LABEL_271;
  }
  MsoCF::CIPtr<MsoCF::IError,MsoCF::IError>::CopyTo(&v238, v247);
  if ( (unsigned __int8)Csi::IsCsiError(v238, 2007) )
  {
    if ( (CMsoOLDocBase::AttrGet((CMsoOLDocBase *)this) & 0x20000) != 0 || (*((_BYTE *)this + 516) & 4) != 0 )
    {
      v147 = MsoLocLibraryFromAlias(0xF902F7ED);
      MsoFLoadWz(v147, 1508070867, v311, 512);
      Mso::Alerts::CreateDefaultAlertParam(v264);
      v148 = -1;
      do
        ++v148;
      while ( v311[v148] );
      std::wstring::assign(v265);
      do
        ++v15;
      while ( v311[v15] );
      std::wstring::assign(v266);
      AlertIdFromMsoIds = Mso::Alerts::GetAlertIdFromMsoIds((Mso::Alerts *)0x59E355D3, v149);
      v268 = 1;
      v269 = *(_WORD *)((char *)&v256 + 5);
      v270 = HIBYTE(v256);
      WatsonAlertIdFromMsoIds = Mso::Alerts::GetWatsonAlertIdFromMsoIds((Mso::Alerts *)0x59E355D3, v150);
      v272 = 1;
      v273 = *(_WORD *)((char *)&v256 + 5);
      v274 = HIBYTE(v256);
      v275 = 3;
      v152 = Mso::Alerts::GetTelemetryNamespace(v151);
      LODWORD(v244) = 509354625;
      Mso::Alerts::ShowAlert((Mso::Alerts *)&v244, v152, (const struct Mso::Telemetry::TelemetryNamespace *)v264, v153);
      std::pair<std::wstring const,Mso::History::FileInfo>::~pair<std::wstring const,Mso::History::FileInfo>(v264);
    }
    v154 = 22619145;
    goto LABEL_170;
  }
  if ( (unsigned __int8)Csi::IsCsiError(v238, 1515) )
  {
    v154 = 22619146;
LABEL_178:
    v155 = v238;
    goto LABEL_171;
  }
  if ( (v304 & 0x2000000000LL) != 0 && Csi::IsWopiAuthenticationError(v238, v157) )
  {
    v158 = v238;
    v238 = 0;
    if ( v158 )
      (*(void (__fastcall **)(Csi *))(*(_QWORD *)v158 + 16LL))(v158);
    Csi::CreateCsiErrorTag(5600, &v238, 541909523);
    MsoCF::CIPtr<MsoCF::IError,MsoCF::IError>::CopyTo(&v238, v247);
    Csi::SetActivityResultIErrorTag((Csi *)v248, v238, (const struct MsoCF::IError *)0x204CE212, v159);
    *(_OWORD *)v286 = 0;
    v160 = _mm_load_si128((const __m128i *)&_xmm);
    v287 = v160;
    LOWORD(v286[0]) = 0;
    v284 = 0;
    v285 = v160;
    LOWORD(v284) = 0;
    v294 = 0;
    si128 = v160;
    LOWORD(v294) = 0;
    v281 = 0;
    v282 = 0;
    v283 = 7;
    LOWORD(v281) = 0;
    LOBYTE(v236) = 0;
    if ( (unsigned int)Mso::Url::ExtractAllWopiPropertiesFromWopiUrl(this[36], v286, &v284, &v294, &v281, v236) )
    {
      v189 = this[36];
      Mso::Alerts::CreateDefaultAlertParam(v311);
      v190 = &ShortName;
      if ( v189 )
        v190 = v189;
      v252 = (WCHAR *)v190;
      do
        ++v15;
      while ( v190[v15] );
      v253 = (struct MsoCF::IError ***)v15;
      v256 = (const char *)&v252;
      v257 = &v254;
      v191 = Mso::Alerts::GetAlertMessageFromMsoIds(&v288, 38601128, &v256);
      Mso::Alerts::AlertMessage::operator=(v312, v191);
      Mso::Help::Core::AuthInfo::~AuthInfo((Mso::Help::Core::AuthInfo *)&v288);
      v313 = 3;
      v193 = Mso::Alerts::GetTelemetryNamespace(v192);
      LODWORD(v244) = 509354594;
      Mso::Alerts::ShowAlert((Mso::Alerts *)&v244, v193, (const struct Mso::Telemetry::TelemetryNamespace *)v311, v194);
      std::pair<std::wstring const,Mso::History::FileInfo>::~pair<std::wstring const,Mso::History::FileInfo>(v311);
      goto LABEL_216;
    }
    v162 = Mso::OfficeServicesManager::GetInstance(v161);
    v163 = v162;
    if ( !v162 )
    {
      CrashWithRecovery(0x204CE211u, 0);
      JUMPOUT(0x180C2FEBELL);
    }
    v164 = *(_QWORD *)v162;
    v165 = &v284;
    if ( v285.m128i_i64[1] > 7uLL )
      v165 = (__int128 *)v284;
    (*(void (__fastcall **)(struct Mso::OfficeServicesManager::IOfficeServicesManager *, struct IUnknown **, __int128 *))(v164 + 8))(
      v163,
      &v246,
      v165);
    if ( !v246 )
    {
      Mso::Alerts::CreateDefaultAlertParam(v264);
      v184 = (WCHAR *)&v281;
      if ( v283 > 7 )
        v184 = (WCHAR *)v281;
      v252 = v184;
      v253 = v282;
      v258 = &v252;
      v259 = &v254;
      v185 = Mso::Alerts::GetAlertMessageFromMsoIds(&v288, 3391383533LL, &v258);
      Mso::Alerts::AlertMessage::operator=(v265, v185);
      Mso::Help::Core::AuthInfo::~AuthInfo((Mso::Help::Core::AuthInfo *)&v288);
      v275 = 1;
      v276 = (void *)v256;
      v187 = Mso::Alerts::GetTelemetryNamespace(v186);
      LODWORD(v244) = 509354595;
      Mso::Alerts::ShowAlert((Mso::Alerts *)&v244, v187, (const struct Mso::Telemetry::TelemetryNamespace *)v264, v188);
      std::pair<std::wstring const,Mso::History::FileInfo>::~pair<std::wstring const,Mso::History::FileInfo>(v264);
      goto LABEL_215;
    }
    v244 = (const char *)Mso::ApplicationModel::UseCurrentExecutionContext(v166);
    Mso::Details::TCntPtrAddRefStrategyImpl<0>::CheckedAddRefOnNewlyAssignedPtr<OInk::TextPen::CIntelligenceProxy>(&v244);
    Mso::TCntPtr<SDX::MSO::Adapter>::TCntPtr<SDX::MSO::Adapter>(&v260, &v244);
    v262 = 0;
    v261 = 509646159;
    Mso::TCntPtr<CBackgroundPullNetDocCycle>::~TCntPtr<CBackgroundPullNetDocCycle>(&v244);
    Mso::ServiceManagerCallback::CreateThirdPartyCallback(&v258, &v284);
    v167 = Mso::TCntPtr<Mso::Sharing::SharingResult<Mso::Sharing::MsoGetUserAttributesResponse>>::operator->(&v258);
    (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v167 + 32LL))(v167, &v296);
    if ( v297.m128i_i64[0] )
    {
      if ( v260 )
      {
        v169 = (const struct IMsoUrl *)&v296;
        if ( v297.m128i_i64[1] > 7uLL )
          v169 = (const struct IMsoUrl *)v296;
        v170 = MsoServerInfoUtils::PromptForWopiCreds((MsoServerInfoUtils *)v303, v169, (const wchar_t *)&v260, v168);
        v289 = "HResult";
        *(_DWORD *)v290 = v170;
        *(_OWORD *)&v290[8] = 0;
        v291.m128i_i64[0] = 0;
        v291.m128i_i64[1] = 7;
        *(_WORD *)&v290[8] = 0;
        LOWORD(v292) = 4;
        v288 = &Mso::Diagnostics::ClassifiedStructuredHr::`vftable';
        v244 = "csierrWopi_InvalidUrl on open, prompted for creds";
        Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
          509646158,
          836,
          15,
          v171,
          (__int64)&v244,
          (__int64)&v288);
        std::basic_string<char16_t>::~basic_string<char16_t>(&v290[8]);
        if ( v170 >= 0 )
        {
          std::basic_string<char16_t>::~basic_string<char16_t>(&v296);
          v172 = v258;
          if ( v258 )
          {
            v258 = 0;
            (*((void (__fastcall **)(WCHAR **))*v172 + 1))(v172);
          }
          Mso::TCntPtr<CBackgroundPullNetDocCycle>::~TCntPtr<CBackgroundPullNetDocCycle>(&v260);
          Mso::TCntPtr<CBackgroundPullNetDocCycle>::~TCntPtr<CBackgroundPullNetDocCycle>(&v246);
          std::basic_string<char16_t>::~basic_string<char16_t>(&v281);
          std::basic_string<char16_t>::~basic_string<char16_t>(&v294);
          std::basic_string<char16_t>::~basic_string<char16_t>(&v284);
          std::basic_string<char16_t>::~basic_string<char16_t>(v286);
          if ( v251 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v251 + 16LL))(v251);
          v173 = v245;
          if ( v245 )
          {
            v245 = 0;
            (*(void (__fastcall **)(struct Csi::IDocumentProperties *))(*(_QWORD *)v173 + 16LL))(v173);
          }
          CMsoUrlSimple::~CMsoUrlSimple((CMsoUrlSimple *)v302);
          if ( v238 )
            (*(void (__fastcall **)(Csi *))(*(_QWORD *)v238 + 16LL))(v238);
          v12 = 1;
          goto LABEL_300;
        }
        goto LABEL_206;
      }
    }
    else if ( v260 )
    {
      v174 = 1;
      goto LABEL_205;
    }
    v174 = 0;
LABEL_205:
    v288 = &Mso::Diagnostics::ClassifiedStructuredObject<bool>::`vftable';
    v289 = "HasExecutionContext";
    v290[0] = v174;
    *(_WORD *)&v290[2] = 4;
    *(_OWORD *)&v290[8] = 0;
    v291 = v160;
    *(_WORD *)&v290[8] = 0;
    v298 = &Mso::Diagnostics::ClassifiedStructuredObject<bool>::`vftable';
    v299 = "ConnectionId";
    LOBYTE(v300) = v297.m128i_i64[0] == 0;
    WORD1(v300) = 4;
    v301[0] = 0;
    v301[1] = v160;
    LOWORD(v301[0]) = 0;
    v244 = "csierrWopi_InvalidUrl on open, could not prompt for creds";
    Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>,Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>>(
      509646040,
      836,
      15,
      (_DWORD)v168,
      (__int64)&v244,
      (__int64)&v298,
      (__int64)&v288);
    std::basic_string<char16_t>::~basic_string<char16_t>(v301);
    std::basic_string<char16_t>::~basic_string<char16_t>(&v290[8]);
LABEL_206:
    v175 = Mso::TCntPtr<Mso::Sharing::SharingResult<Mso::Sharing::MsoGetUserAttributesResponse>>::operator->(&v246);
    v176 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v175 + 128LL))(v175);
    Mso::Alerts::CreateDefaultAlertParam(v277);
    v177 = (void **)&v281;
    if ( v283 > 7 )
      v177 = (void **)v281;
    v298 = v177;
    v299 = (const char *)v282;
    v178 = &ShortName;
    if ( v176 )
      v178 = (const WCHAR *)v176;
    v300 = v178;
    do
      ++v15;
    while ( v178[v15] );
    *(_QWORD *)&v301[0] = v15;
    v252 = (WCHAR *)&v298;
    v253 = (struct MsoCF::IError ***)v301 + 1;
    v179 = Mso::Alerts::GetAlertMessageFromMsoIds(&v288, 39819150, &v252);
    Mso::Alerts::AlertMessage::operator=(v278, v179);
    Mso::Help::Core::AuthInfo::~AuthInfo((Mso::Help::Core::AuthInfo *)&v288);
    v279 = 1;
    v280 = v256;
    v181 = Mso::Alerts::GetTelemetryNamespace(v180);
    LODWORD(v244) = 509354624;
    Mso::Alerts::ShowAlert((Mso::Alerts *)&v244, v181, (const struct Mso::Telemetry::TelemetryNamespace *)v277, v182);
    std::pair<std::wstring const,Mso::History::FileInfo>::~pair<std::wstring const,Mso::History::FileInfo>(v277);
    std::basic_string<char16_t>::~basic_string<char16_t>(&v296);
    v183 = v258;
    if ( v258 )
    {
      v258 = 0;
      (*((void (__fastcall **)(WCHAR **))*v183 + 1))(v183);
    }
    Mso::TCntPtr<CBackgroundPullNetDocCycle>::~TCntPtr<CBackgroundPullNetDocCycle>(&v260);
LABEL_215:
    Mso::TCntPtr<CBackgroundPullNetDocCycle>::~TCntPtr<CBackgroundPullNetDocCycle>(&v246);
LABEL_216:
    std::basic_string<char16_t>::~basic_string<char16_t>(&v281);
    std::basic_string<char16_t>::~basic_string<char16_t>(&v294);
    std::basic_string<char16_t>::~basic_string<char16_t>(&v284);
    std::basic_string<char16_t>::~basic_string<char16_t>(v286);
    goto LABEL_172;
  }
  v195 = (char *)(this + 196);
  if ( !(unsigned __int8)CMsoOLDocFile::IsFileCached(this + 196, 559257440) )
  {
    if ( v255 && Csi::IsInAppDownloadAuthenticationError(v238, v196) || (unsigned __int8)sub_18114DC34(v238) )
      v11 = 0;
    v207 = v258;
    *(_BYTE *)v258 = v11;
    v208 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v248);
    LOBYTE(v209) = *(_BYTE *)v207;
    Mso::Telemetry::IDataFieldCollection::Add<bool>(v208, "AllowFallbackOnFailure", v209, 4);
    if ( (unsigned __int8)Csi::IsCsiError(v238, 4705) )
    {
      Csi::CreateCsiErrorTag(4788, &v238, 38073427);
      MsoCF::CIPtr<MsoCF::IError,MsoCF::IError>::CopyTo(&v238, v247);
    }
    v154 = 22619150;
    goto LABEL_178;
  }
  if ( (unsigned __int8)Csi::IsCsiError(v238, 4710) )
  {
    v240 = 1;
    v197 = 1;
    *((_DWORD *)this + 377) = 25236368;
    goto LABEL_272;
  }
  if ( (unsigned __int8)Csi::IsCsiError(v238, 4795) )
  {
    v240 = 1;
    v197 = 1;
    *((_DWORD *)this + 377) = 521286297;
    goto LABEL_272;
  }
  if ( (unsigned __int8)Csi::IsCsiError(v238, 1660) )
  {
    v240 = 1;
    v197 = 1;
    *((_DWORD *)this + 377) = 25236369;
    goto LABEL_272;
  }
  if ( (unsigned __int8)sub_180BCD920(v10, v238) || v239 )
  {
    CMsoOLDocBase::SetIsOpeningOfflineCopy((CMsoOLDocBase *)this, 1);
    v200 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v248);
    v202 = (const struct Mso::Telemetry::IDataContract *)Office::FileIO::MSO::CsiGetFileFromCacheMetaData::CsiGetFileFromCacheMetaData(
                                                           (Office::FileIO::MSO::CsiGetFileFromCacheMetaData *)&v288,
                                                           v201);
    v203 = (const struct Mso::Telemetry::ISingleDataField *)Mso::Telemetry::DataContractField::DataContractField(
                                                              (Mso::Telemetry::DataContractField *)&v298,
                                                              "CsiGetFileFromCacheMetaData",
                                                              v202);
    Mso::Telemetry::IDataFieldCollection::Add(v200, v203);
    if ( *((_BYTE *)this + 1552) )
    {
      v154 = 22619147;
LABEL_170:
      v155 = *v247;
LABEL_171:
      Csi::SetActivityResultIErrorTag((Csi *)v248, v155, (const struct MsoCF::IError *)v154, v146);
LABEL_172:
      if ( v251 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v251 + 16LL))(v251);
      v156 = v245;
      if ( v245 )
      {
        v245 = 0;
        (*(void (__fastcall **)(struct Csi::IDocumentProperties *))(*(_QWORD *)v156 + 16LL))(v156);
      }
      goto LABEL_297;
    }
    v195 = (char *)(this + 196);
  }
  if ( (unsigned __int8)sub_18069AACC(this + 136, v198, v199, 560567330) )
  {
    if ( (unsigned __int8)Csi::IsCsiError(v238, 2053) )
    {
      Mso::TCntPtr<IDGCContext>::operator=<DGCCDocument,void>(this + 232);
      LODWORD(v244) = 505701859;
      CMsoOLDocBase::SetFIsANewlyCreatedFile((CMsoOLDocBase *)this, (const struct MsoReserveTag *)&v244, 1);
    }
    goto LABEL_271;
  }
  Mso::TCntPtr<IDGCContext>::operator=<DGCCDocument,void>(this + 232);
  if ( (unsigned __int8)Csi::IsCsiError(v238, 902)
    || (unsigned __int8)Csi::IsCsiError(v238, 906)
    || (unsigned __int8)Csi::IsCsiError(v238, 915) )
  {
    CMsoOLDocBaseImpIOLDoc2::SetWTdi(v10, -2147287008, 5u);
LABEL_254:
    v240 = 1;
    goto LABEL_255;
  }
  if ( (unsigned __int8)Csi::IsCsiError(v238, 1657)
    || (unsigned __int8)Csi::IsCsiError(v238, 910)
    || (unsigned __int8)Csi::IsCsiError(v238, 1673) )
  {
    goto LABEL_254;
  }
  if ( !(unsigned __int8)sub_180BCD920(v10, v238) && !(unsigned __int8)Csi::IsCsiError(v238, 2019) && !v239 )
  {
    v204 = v238;
    if ( !(unsigned __int8)Csi::IsCsiError(v238, Csi::csierrWebService_AuthenticationNeeded)
      && !(unsigned __int8)Csi::IsCsiError(v204, Csi::csierrWebService_ProxyAuthenticationNeeded) )
    {
      v11 = 0;
    }
    *(_BYTE *)v258 = v11;
    if ( (unsigned __int8)Csi::IsCsiError(v238, 4705) )
    {
      Csi::CreateCsiErrorTag(4788, &v238, 38073426);
      MsoCF::CIPtr<MsoCF::IError,MsoCF::IError>::CopyTo(&v238, v247);
    }
    v154 = 22619149;
    goto LABEL_178;
  }
LABEL_255:
  if ( !(unsigned int)MsoFOfflineCachedFile(v10)
    && !Mso::DocumentError::DocErrorProviderUtils::IsFileInPerFileOffline(v10, v205)
    && !Mso::DocumentError::DocErrorProviderUtils::IsFileInUnrecoverablePerFileOffline(v10, v206)
    && !v239
    || !(unsigned int)CMsoOLDocFile::FIsAutoMergable(v195, 560567329) )
  {
    v197 = 1;
    *((_DWORD *)this + 377) = 25236370;
    goto LABEL_272;
  }
LABEL_271:
  v197 = v241;
LABEL_272:
  v210 = v238;
  LOBYTE(v234) = v250 == 6;
  LOBYTE(v211) = sub_18069AACC(this + 136, v143, v144, 560567328);
  LOBYTE(v212) = v237;
  if ( (unsigned int)Mso::ClpIncapableUX::OnGetFileComplete(v10, v245, v212, v211, v234, v210) == 1 )
  {
    Mso::TCntPtr<Mso::DocumentActivities::Common::TaskReassignment>::Clear(this + 232);
    MsoCF::CreateHRESULTErrorTag((MsoCF *)0x804D000CLL, (_DWORD)this + 1856, (struct MsoCF::IError **)0x2205D0D5, v213);
    v214 = Mso::TCntPtr<Mso::Sharing::SharingResult<Mso::Sharing::MsoGetUserAttributesResponse>>::operator->(this + 232);
    (*(void (__fastcall **)(__int64, Csi *))(*(_QWORD *)v214 + 32LL))(v214, v238);
    if ( v247 )
    {
      if ( *v247 )
        (*(void (__fastcall **)(struct MsoCF::IError *))(*(_QWORD *)*v247 + 16LL))(*v247);
      v215 = (struct MsoCF::IError *)Mso::TCntPtr<IMsoXmlSchema>::Copy(this + 232);
      *v247 = v215;
    }
    v154 = 570806484;
    v155 = (struct Mso::Telemetry::Activity *)this[232];
    goto LABEL_171;
  }
  Controller = (const wchar_t **)Mso::PerpetualRedirectUX::TryMakeController(&v256, v10);
  v217 = *Controller;
  *Controller = 0;
  v218 = this[192];
  this[192] = v217;
  if ( v218 )
    (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v218 + 8LL))(v218);
  v219 = v256;
  if ( v256 )
  {
    v256 = 0;
    (*(void (__fastcall **)(const char *))(*(_QWORD *)v219 + 8LL))(v219);
  }
  CMsoOLDocBase::SetAttr2InAttr2Mask((CMsoOLDocBase *)this, 0x400u, 0x400u);
  CMsoOLDocFile::SetStreamAvailableMask((CMsoOLDocFile *)this);
  CodeMarker(3139);
  FileName[0] = 0;
  v220 = CMsoOLDocFile::FIsStreamAvailable((CMsoOLDocFile *)this);
  v221 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v248);
  LOBYTE(v222) = v220 != 0;
  Mso::Telemetry::IDataFieldCollection::Add<bool>(v221, "UseStream", v222, 4);
  if ( !v220 )
  {
    if ( !(unsigned int)CMsoOLDocFile::FGenerateTempFile((CMsoOLDocFile *)this, FileName, 260, this[36]) )
    {
      Mso::Telemetry::SetActivityResultHr(
        (Mso::Telemetry *)v248,
        (struct Mso::Telemetry::Activity *)0x804D0017LL,
        41947793,
        v223);
      if ( v251 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v251 + 16LL))(v251);
      Mso::TCntPtr<Mso::DocumentActivities::Common::TaskReassignment>::Clear(&v245);
      goto LABEL_297;
    }
    v256 = 0;
    if ( (unsigned int)CMsoOLDocBase::GetSyncBackedType(this) != 1 )
    {
      v252 = FileName;
      v253 = &v247;
      if ( (unsigned __int8)sub_1811480E4(this + 136, &v252, v224, 558404547) )
      {
        v154 = 22619152;
        goto LABEL_170;
      }
    }
    v225 = Mso::Telemetry::Activity::DataFields((Mso::Telemetry::Activity *)v248);
    LOBYTE(v226) = 1;
    Mso::Telemetry::IDataFieldCollection::Add<bool>(v225, "TempFileGenerated", v226, 4);
    if ( CMsoOLDocFile::IsCobaltVersion(v10) )
    {
      v227 = Mso::TCntPtr<Mso::Sharing::SharingResult<Mso::Sharing::MsoGetUserAttributesResponse>>::operator->(this + 242);
      v228 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v227 + 48LL))(v227);
      if ( (int)MsoHrSetLocalSavedVersion(v228, FileName) < 0 )
        MsoShipAssertTagProc(22619153);
    }
    Mso::TCntPtr<Mso::DocumentActivities::Common::TaskReassignment>::Clear(&v256);
  }
  CodeMarker(3140);
  if ( v220 )
  {
    CMsoOLDocBase::SetWzI((CMsoOLDocBase *)this, 0, 4);
  }
  else
  {
    CMsoOLDocBase::SetWzI((CMsoOLDocBase *)this, FileName, 4);
    if ( (unsigned int)CMsoOLDocBase::GetSyncBackedType(this) != 1 )
      CMsoOLDocBase::SetAttrInAttrMask((CMsoOLDocBase *)this, 0x10000u, 0x10000u);
  }
  if ( !v237 && v197 )
  {
    if ( *((_DWORD *)this + 152) == 2 )
    {
      LODWORD(v244) = -2147467259;
      v231 = CMsoOLDocBase::FIsOpen((CMsoOLDocBase *)this);
      *((_DWORD *)this + 254) = 1;
      CMsoOLDocBaseImpIOLDoc2::RecordEvent(v10, 0x40000000u, &v244, 0);
      CMsoOLDocBaseImpIOLDoc2::BeginCmd(v10, 4u, 0);
      if ( v231 )
        CMsoOLDocBase::SetReadOnly(this, 25236371, 0);
      *((_DWORD *)this + 254) = 0;
    }
    else
    {
      CMsoOLDocBase::SetReadOnly(this, 25236372, 0);
    }
  }
  if ( v220 )
  {
    v232 = v240 != 0;
    v240 = -v240;
    CMsoOLDocBase::SetAttr2InAttr2Mask((CMsoOLDocBase *)this, v232 ? 0x80000 : 0, 0x80000u);
  }
  else if ( v240 && !(unsigned int)CMsoOLDocBase::GetSyncBackedType(this) )
  {
    FileAttributesW = GetFileAttributesW(FileName);
    SetFileAttributesW(FileName, FileAttributesW | 1);
  }
  LOBYTE(v229) = 1;
  MsoServerInfoUtils::SetEnableBHO((MsoServerInfoUtils *)v303, v229, v230);
  Mso::Telemetry::Activity::SetSuccess((Mso::Telemetry::Activity *)v248, 1);
  if ( v251 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v251 + 16LL))(v251);
  Mso::TCntPtr<Mso::DocumentActivities::Common::TaskReassignment>::Clear(&v245);
  CMsoUrlSimple::~CMsoUrlSimple((CMsoUrlSimple *)v302);
  if ( v238 )
    (*(void (__fastcall **)(Csi *))(*(_QWORD *)v238 + 16LL))(v238);
  Measurements::MeasureElapsedTime::~MeasureElapsedTime((Measurements::MeasureElapsedTime *)v263);
  Mso::Telemetry::Activity::~Activity((Mso::Telemetry::Activity *)v248);
  return 1;
}

```

## disassembly

```asm
0x180c2d878  mov     [rsp-8+arg_8], rbx
0x180c2d87d  push    rbp
0x180c2d87e  push    rsi
0x180c2d87f  push    rdi
0x180c2d880  push    r12
0x180c2d882  push    r13
0x180c2d884  push    r14
0x180c2d886  push    r15
0x180c2d888  lea     rbp, [rsp-1B00h]
0x180c2d890  mov     eax, 1C00h
0x180c2d895  call    _alloca_probe
0x180c2d89a  sub     rsp, rax
0x180c2d89d  movaps  [rsp+1C30h+var_40], xmm6
0x180c2d8a5  mov     rax, cs:__security_cookie
0x180c2d8ac  xor     rax, rsp
0x180c2d8af  mov     [rbp+1B30h+var_50], rax
0x180c2d8b6  mov     [rbp+1B30h+var_1B87], r9b
0x180c2d8ba  mov     bl, r8b
0x180c2d8bd  mov     [rbp+1B30h+var_1BA8], bl
0x180c2d8c0  mov     dil, dl
0x180c2d8c3  mov     [rsp+1C30h+var_1BDE], dl
0x180c2d8c7  mov     r15, rcx
0x180c2d8ca  mov     rax, [rbp+1B30h+arg_28]
0x180c2d8d1  mov     [rsp+1C30h+var_1BC0], rax
0x180c2d8d6  mov     rax, [rbp+1B30h+arg_30]
0x180c2d8dd  mov     [rbp+1B30h+var_1B70], rax
0x180c2d8e1  lea     rsi, [rcx+608h]
0x180c2d8e8  mov     r12d, 1
0x180c2d8ee  xor     r14d, r14d
0x180c2d8f1  test    dl, dl
0x180c2d8f3  jnz     short loc_180C2D911
0x180c2d8f5  mov     rcx, rsi; this
0x180c2d8f8  call    ?IsCobaltVersion@CMsoOLDocFile@@UEBA_NXZ; CMsoOLDocFile::IsCobaltVersion(void)
0x180c2d8fd  test    al, al
0x180c2d8ff  jnz     short loc_180C2D911
0x180c2d901  mov     al, bl
0x180c2d903  neg     al
0x180c2d905  sbb     ecx, ecx
0x180c2d907  neg     ecx
0x180c2d909  add     ecx, r12d
0x180c2d90c  mov     [rbp+1B30h+var_1BA4], ecx
0x180c2d90f  jmp     short loc_180C2D918
0x180c2d911  mov     [rbp+1B30h+var_1BA4], 6
0x180c2d918  mov     [rsp+1C30h+var_1BDF], r14b
0x180c2d91d  mov     edx, 2
0x180c2d922  mov     r8b, 6Eh ; 'n'
0x180c2d925  lea     rcx, [rsp+1C30h+var_1BC8]
0x180c2d92a  call    ??0EventFlags@Telemetry@Mso@@QEAA@W4DataCategories@12@W4DiagnosticLevel@12@@Z; Mso::Telemetry::EventFlags::EventFlags(Mso::Telemetry::DataCategories,Mso::Telemetry::DiagnosticLevel)
0x180c2d92f  mov     rbx, rax
0x180c2d932  lea     rax, aFcsigetfile; "FCsiGetFile"
0x180c2d939  mov     [rbp+1B30h+var_1B80], rax
0x180c2d93d  lea     rdx, [rbp+1B30h+var_1B80]
0x180c2d941  lea     rcx, [rbp+1B30h+var_1B98]
0x180c2d945  call    ?EventName@MSO@FileIO@Office@@YA?AU0Telemetry@Mso@@AEBUValidEventName@45@@Z; Office::FileIO::MSO::EventName(Mso::Telemetry::ValidEventName const &)
0x180c2d94a  mov     r8, rbx; struct Mso::Telemetry::EventFlags *
0x180c2d94d  mov     rdx, rax; struct Mso::Telemetry::EventName *
0x180c2d950  lea     rcx, [rsp+1C30h+var_1BB8]; this
0x180c2d955  call    ??0Activity@Telemetry@Mso@@QEAA@AEBUEventName@12@AEBUEventFlags@12@@Z; Mso::Telemetry::Activity::Activity(Mso::Telemetry::EventName const &,Mso::Telemetry::EventFlags const &)
0x180c2d95a  or      r13, 0FFFFFFFFFFFFFFFFh
0x180c2d95e  mov     r9, r13
0x180c2d961  mov     r8, r15
0x180c2d964  lea     rdx, [rsp+1C30h+var_1BB8]
0x180c2d969  lea     rcx, [rsp+1C30h+var_1BD8]
0x180c2d96e  call    ??$AddDocumentTelemetryToActivity@UActivity@Telemetry@Mso@@PEAVCMsoOLDocFile@@X@DocumentTelemetry@Mso@@YA?AVCAddDocumentTelemetryToActivityResult@01@AEAUActivity@Telemetry@1@QEAVCMsoOLDocFile@@W4DocumentFields@01@PEBD@Z; Mso::DocumentTelemetry::AddDocumentTelemetryToActivity<Mso::Telemetry::Activity,CMsoOLDocFile *,void>(Mso::Telemetry::Activity &,CMsoOLDocFile * const,Mso::DocumentTelemetry::DocumentFields,char const *)
0x180c2d973  lea     rcx, [rsp+1C30h+var_1BB8]
0x180c2d978  call    cs:__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180c2d97e  mov     r8b, byte ptr [rbp+1B30h+var_1BA4]
0x180c2d982  lea     rdx, aOpenfilestateR; "OpenFileState_Requested"
0x180c2d989  mov     rcx, rax
0x180c2d98c  call    ??$Add@E@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBDEW4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<uchar>(char const *,uchar,Mso::Logging::DataClassifications)
0x180c2d991  lea     rcx, [rsp+1C30h+var_1BB8]
0x180c2d996  call    cs:__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180c2d99c  mov     rbx, rax
0x180c2d99f  mov     rcx, r15; this
0x180c2d9a2  call    ?GetFBlockNetworkCalls@CMsoOLDocBase@@UEAAHXZ; CMsoOLDocBase::GetFBlockNetworkCalls(void)
0x180c2d9a7  mov     r8d, eax
0x180c2d9aa  lea     rdx, aBlocknetworkca; "BlockNetworkCalls"
0x180c2d9b1  mov     rcx, rbx
0x180c2d9b4  call    ??$Add@H@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBDHW4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<int>(char const *,int,Mso::Logging::DataClassifications)
0x180c2d9b9  lea     rcx, ??_7?$ClassifiedStructuredObject@U_GUID@@@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<_GUID>::`vftable'
0x180c2d9c0  mov     [rbp+1B30h+var_1920], rcx
0x180c2d9c7  lea     rcx, aDocumentunique; "DocumentUniqueId"
0x180c2d9ce  mov     [rbp+1B30h+var_1918], rcx
0x180c2d9d5  movups  xmm0, xmmword ptr [r15+0F0h]
0x180c2d9dd  movdqu  [rbp+1B30h+var_1910], xmm0
0x180c2d9e5  mov     eax, 100h
0x180c2d9ea  mov     word ptr [rbp+1B30h+var_1900], ax
0x180c2d9f1  xorps   xmm0, xmm0
0x180c2d9f4  movups  [rbp+1B30h+var_18F8], xmm0
0x180c2d9fb  mov     [rbp+1B30h+var_18E8], r14
0x180c2da02  mov     [rbp+1B30h+var_18E0], 7
0x180c2da0d  mov     word ptr [rbp+1B30h+var_18F8], r14w
0x180c2da15  lea     rax, aOldocFcsigetfi; "OLDoc:FCsiGetFile"
0x180c2da1c  mov     [rbp+1B30h+var_1B80], rax
0x180c2da20  lea     rax, [rbp+1B30h+var_1920]
0x180c2da27  mov     [rsp+1C30h+var_1C08], rax
0x180c2da2c  lea     rax, [rbp+1B30h+var_1B80]
0x180c2da30  mov     [rsp+1C30h+var_1C10], rax
0x180c2da35  mov     edx, 344h
0x180c2da3a  mov     ecx, 236CD453h
0x180c2da3f  lea     r8d, [r13+33h]
0x180c2da43  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@PEB_W@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> &&)
0x180c2da48  lea     rcx, [rbp+1B30h+var_18F8]; void *
0x180c2da4f  call    ??1?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAA@XZ; std::basic_string<char16_t>::~basic_string<char16_t>(void)
0x180c2da54  lea     rcx, [rbp+1B30h+var_1880]; this
0x180c2da5b  call    ??0Stopwatch@Measurements@@QEAA@XZ; Measurements::Stopwatch::Stopwatch(void)
0x180c2da60  mov     r9, rax
0x180c2da63  mov     r8b, r12b
0x180c2da66  mov     edx, cs:?OLDocFCsiGetFile@MeasurementId@Measurements@@3UMeasurementIdType@2@B; Measurements::MeasurementIdType const Measurements::MeasurementId::OLDocFCsiGetFile
0x180c2da6c  lea     rcx, [rbp+1B30h+var_1B48]
0x180c2da70  call    cs:__imp_??0MeasureElapsedTime@Measurements@@QEAA@UMeasurementIdType@1@_N$$QEAVStopwatch@1@@Z; Measurements::MeasureElapsedTime::MeasureElapsedTime(Measurements::MeasurementIdType,bool,Measurements::Stopwatch &&)
0x180c2da76  mov     rax, [rbp+1B30h+var_1B70]
0x180c2da7a  mov     [rax], r14b
0x180c2da7d  cmp     [r15+710h], r14b
0x180c2da84  jnz     short loc_180C2DACC
0x180c2da86  mov     rdx, [rsp+1C30h+var_1BC0]; struct MsoCF::IError **
0x180c2da8b  mov     rcx, rsi; this
0x180c2da8e  call    ?FInitCsiFileIO@CMsoOLDocFile@@MEAAHPEAPEAUIError@MsoCF@@@Z; CMsoOLDocFile::FInitCsiFileIO(MsoCF::IError * *)
0x180c2da93  test    eax, eax
0x180c2da95  jnz     short loc_180C2DACC
0x180c2da97  mov     rax, [rsp+1C30h+var_1BC0]
0x180c2da9c  mov     r8d, 15923E1h; struct MsoCF::IError *
0x180c2daa2  mov     rdx, [rax]; struct Mso::Telemetry::Activity *
0x180c2daa5  lea     rcx, [rsp+1C30h+var_1BB8]; this
0x180c2daaa  call    ?SetActivityResultIErrorTag@Csi@@YAXAEAUActivity@Telemetry@Mso@@AEBUIError@MsoCF@@I@Z; Csi::SetActivityResultIErrorTag(Mso::Telemetry::Activity &,MsoCF::IError const &,uint)
0x180c2daaf  nop
0x180c2dab0  lea     rcx, [rbp+1B30h+var_1B48]
0x180c2dab4  call    cs:__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ; Measurements::MeasureElapsedTime::~MeasureElapsedTime(void)
0x180c2daba  lea     rcx, [rsp+1C30h+var_1BB8]
0x180c2dabf  call    cs:__imp_??1Activity@Telemetry@Mso@@QEAA@XZ; Mso::Telemetry::Activity::~Activity(void)
0x180c2dac5  xor     eax, eax
0x180c2dac7  jmp     loc_180C2FE13
0x180c2dacc  mov     [rbp+1B30h+var_16F0], 1
0x180c2dad7  mov     [rbp+1B30h+var_16E8], r14
0x180c2dade  mov     [rbp+1B30h+var_16E0], r14
0x180c2dae5  mov     [rbp+1B30h+var_16D8], r14d
0x180c2daec  mov     [rbp+1B30h+var_68C], r14
0x180c2daf3  mov     [rbp+1B30h+var_674], r14b
0x180c2dafa  mov     [rbp+1B30h+var_668], r14b
0x180c2db01  xor     r9d, r9d; bool
0x180c2db04  xor     r8d, r8d; struct MSODMGSI *
0x180c2db07  lea     rdx, [rbp+1B30h+var_16F0]; struct Csi::CsiServerInfo *
0x180c2db0e  mov     rcx, rsi; this
0x180c2db11  call    ?GetCsiServerInfo@CMsoOLDocFile@@UEAAXPEAUCsiServerInfo@Csi@@PEAUMSODMGSI@@_N@Z; CMsoOLDocFile::GetCsiServerInfo(Csi::CsiServerInfo *,MSODMGSI *,bool)
0x180c2db16  lea     rcx, [rsp+1C30h+var_1BB8]
0x180c2db1b  call    cs:__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180c2db21  mov     r8d, dword ptr [rbp+1B30h+var_16E8+4]
0x180c2db28  lea     rdx, aProtocol; "Protocol"
0x180c2db2f  mov     rcx, rax
0x180c2db32  call    ??$Add@H@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBDHW4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<int>(char const *,int,Mso::Logging::DataClassifications)
0x180c2db37  lea     rcx, [rsp+1C30h+var_1BB8]
0x180c2db3c  call    cs:__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180c2db42  mov     r8d, dword ptr [rbp+1B30h+var_16E8]
0x180c2db49  lea     rdx, aServertype; "ServerType"
0x180c2db50  mov     rcx, rax
0x180c2db53  call    ??$Add@H@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBDHW4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<int>(char const *,int,Mso::Logging::DataClassifications)
0x180c2db58  lea     rcx, [rsp+1C30h+var_1BB8]
0x180c2db5d  call    cs:__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180c2db63  mov     r10, rax
0x180c2db66  lea     rcx, [rbp+1B30h+var_16F0]; this
0x180c2db6d  call    ?IsCloudCollabEnabled@CsiServerInfo@Csi@@QEBA_NXZ; Csi::CsiServerInfo::IsCloudCollabEnabled(void)
0x180c2db72  mov     ebx, 4
0x180c2db77  mov     r9d, ebx
0x180c2db7a  mov     r8b, al
0x180c2db7d  lea     rdx, aCloudcollab; "CloudCollab"
0x180c2db84  mov     rcx, r10
0x180c2db87  call    ??$Add@_N@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBD_NW4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<bool>(char const *,bool,Mso::Logging::DataClassifications)
0x180c2db8c  lea     rcx, [rsp+1C30h+var_1BB8]
0x180c2db91  call    cs:__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180c2db97  cmp     dword ptr [rbp+1B30h+var_68C], r14d
0x180c2db9e  setbe   r8b
0x180c2dba2  mov     r9d, ebx
0x180c2dba5  lea     rdx, aIsweburlempty; "IsWebUrlEmpty"
0x180c2dbac  mov     rcx, rax
0x180c2dbaf  call    ??$Add@_N@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBD_NW4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<bool>(char const *,bool,Mso::Logging::DataClassifications)
0x180c2dbb4  cmp     dword ptr [rbp+1B30h+var_16F0+4], r12d
0x180c2dbbb  jnz     short loc_180C2DC04
0x180c2dbbd  mov     [rbp+1B30h+var_1BA4], 6
0x180c2dbc4  lea     rcx, [rsp+1C30h+var_1BB8]
0x180c2dbc9  call    cs:__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ; Mso::Telemetry::Activity::DataFields(void)
0x180c2dbcf  mov     r8b, byte ptr [rbp+1B30h+var_1BA4]
0x180c2dbd3  lea     rdx, aOpenfilestateL; "OpenFileState_LegacyFallback"
0x180c2dbda  mov     rcx, rax
0x180c2dbdd  call    ??$Add@E@IDataFieldCollection@Telemetry@Mso@@QEAAXPEBDEW4DataClassifications@Logging@2@@Z; Mso::Telemetry::IDataFieldCollection::Add<uchar>(char const *,uchar,Mso::Logging::DataClassifications)
0x180c2dbe2  lea     rcx, [r15+5E4h]
0x180c2dbe9  mov     dword ptr [rcx], 181138Dh
0x180c2dbef  lea     edx, [rbx+1Eh]
0x180c2dbf2  call    ?SetNonDownloadProtocolReadOnlyReason@ReadOnlyReasonTracker@Mso@@QEAAXW4ReadOnlyReason@Csi@@@Z; Mso::ReadOnlyReasonTracker::SetNonDownloadProtocolReadOnlyReason(Csi::ReadOnlyReason)
0x180c2dbf7  mov     dil, r12b
0x180c2dbfa  mov     [rsp+1C30h+var_1BDE], r12b
0x180c2dbff  mov     [rsp+1C30h+var_1BDF], r12b
0x180c2dc04  xor     ecx, ecx
0x180c2dc06  call    cs:__imp_?HwndParentForDmEx@@YAPEAUHWND__@@_N@Z; HwndParentForDmEx(bool)
0x180c2dc0c  mov     rbx, rax
0x180c2dc0f  mov     [rbp+1B30h+var_1B80], rax
0x180c2dc13  mov     [rsp+1C30h+var_1BE8], r14
0x180c2dc18  mov     byte ptr [rsp+1C30h+var_1BD8+1], r14b
0x180c2dc1d  movzx   eax, word ptr [rsp+1C30h+var_1BD8]
0x180c2dc22  mov     word ptr [rsp+1C30h+var_1C10], ax
0x180c2dc27  lea     r9, [rbp+1B30h+var_16F0]
0x180c2dc2e  mov     r8d, [rbp+1B30h+var_1BA4]
0x180c2dc32  lea     rdx, [rsp+1C30h+var_1BE8]
0x180c2dc37  mov     rcx, rsi
0x180c2dc3a  call    ?FInitCsiFile@CMsoOLDocFile@@MEAAHPEAPEAUIError@MsoCF@@W4CAOpenFileState@@PEBUCsiServerInfo@Csi@@V?$optional@_N@std@@@Z; CMsoOLDocFile::FInitCsiFile(MsoCF::IError * *,CAOpenFileState,Csi::CsiServerInfo const *,std::optional<bool>)
0x180c2dc3f  test    eax, eax
0x180c2dc41  jnz     loc_180C2DCDC
0x180c2dc47  mov     rcx, [rsp+1C30h+var_1BE8]; this
0x180c2dc4c  call    ?IsFileOpenForEditTakenError@Csi@@YA_NPEBUIError@MsoCF@@@Z; Csi::IsFileOpenForEditTakenError(MsoCF::IError const *)
0x180c2dc51  test    al, al
0x180c2dc53  jz      loc_180C2DD0A
0x180c2dc59  lea     r9, [rbp+1B30h+var_16F0]; struct Csi::CsiServerInfo *
0x180c2dc60  lea     r8, [rbp+1B30h+var_1BA4]; enum CAOpenFileState *
0x180c2dc64  lea     rdx, [rsp+1C30h+var_1BE8]; struct MsoCF::IError **
0x180c2dc69  mov     rcx, r15; this
0x180c2dc6c  call    ?TryFallbackToReadOnly@CMsoOLDocFile@@IEAA_NPEAPEAUIError@MsoCF@@AEAW4CAOpenFileState@@AEBUCsiServerInfo@Csi@@@Z; CMsoOLDocFile::TryFallbackToReadOnly(MsoCF::IError * *,CAOpenFileState &,Csi::CsiServerInfo const &)
0x180c2dc71  test    al, al
0x180c2dc73  jnz     short loc_180C2DCAC
0x180c2dc75  cmp     [rsp+1C30h+var_1BE8], r14
0x180c2dc7a  jz      loc_180C2FE52
0x180c2dc80  mov     rdx, [rsp+1C30h+var_1BC0]
0x180c2dc85  lea     rcx, [rsp+1C30h+var_1BE8]
0x180c2dc8a  call    ?CopyTo@?$CIPtr@UIError@MsoCF@@U12@@MsoCF@@QEBA_NPEAPEAUIError@2@@Z; MsoCF::CIPtr<MsoCF::IError,MsoCF::IError>::CopyTo(MsoCF::IError * *)
0x180c2dc8f  mov     r8d, 15923E2h; struct MsoCF::IError *
0x180c2dc95  mov     rax, [rsp+1C30h+var_1BC0]
0x180c2dc9a  mov     rdx, [rax]; struct Mso::Telemetry::Activity *
0x180c2dc9d  lea     rcx, [rsp+1C30h+var_1BB8]; this
0x180c2dca2  call    ?SetActivityResultIErrorTag@Csi@@YAXAEAUActivity@Telemetry@Mso@@AEBUIError@MsoCF@@I@Z; Csi::SetActivityResultIErrorTag(Mso::Telemetry::Activity &,MsoCF::IError const &,uint)
0x180c2dca7  jmp     loc_180C2FC88
0x180c2dcac  mov     dil, r12b
0x180c2dcaf  mov     [rsp+1C30h+var_1BDE], r12b
0x180c2dcb4  mov     [rsp+1C30h+var_1BDF], r12b
0x180c2dcb9  mov     edx, 181138Eh
0x180c2dcbe  mov     r8d, 23h ; '#'
0x180c2dcc4  mov     rcx, r15
0x180c2dcc7  call    ?SetReadOnly@CMsoOLDocBase@@QEAAJKW4ReadOnlyReason@Csi@@@Z; CMsoOLDocBase::SetReadOnly(ulong,Csi::ReadOnlyReason)
0x180c2dccc  xor     edx, edx; unsigned int
0x180c2dcce  mov     r8d, 4000h; unsigned int
0x180c2dcd4  mov     rcx, r15; this
0x180c2dcd7  call    ?SetAttrInAttrMask@CMsoOLDocBase@@UEAAJKK@Z; CMsoOLDocBase::SetAttrInAttrMask(ulong,ulong)
0x180c2dcdc  mov     rcx, r15; this
0x180c2dcdf  call    ?IsCachedAsDistributedBlobsFile@CMsoOLDocBase@@IEBA_NXZ; CMsoOLDocBase::IsCachedAsDistributedBlobsFile(void)
0x180c2dce4  test    al, al
0x180c2dce6  jz      loc_180C2E50E
0x180c2dcec  mov     r8d, 1E48934Fh
0x180c2dcf2  mov     rdx, [rsp+1C30h+var_1BC0]
0x180c2dcf7  mov     ecx, 819h
0x180c2dcfc  call    cs:__imp_?CreateCsiErrorTag@Csi@@YAXVCsiErrorCode@1@PEAPEAUIError@MsoCF@@K@Z; Csi::CreateCsiErrorTag(Csi::CsiErrorCode,MsoCF::IError * *,ulong)
0x180c2dd02  mov     r8d, 1F4034E0h
0x180c2dd08  jmp     short loc_180C2DC95
0x180c2dd0a  mov     rcx, [rsp+1C30h+var_1BE8]; this
0x180c2dd0f  call    ?IsExpectedEdpError@Csi@@YA_NPEBUIError@MsoCF@@@Z; Csi::IsExpectedEdpError(MsoCF::IError const *)
0x180c2dd14  test    al, al
0x180c2dd16  jz      short loc_180C2DD32
0x180c2dd18  mov     rdx, [rsp+1C30h+var_1BC0]
0x180c2dd1d  lea     rcx, [rsp+1C30h+var_1BE8]
0x180c2dd22  call    ?CopyTo@?$CIPtr@UIError@MsoCF@@U12@@MsoCF@@QEBA_NPEAPEAUIError@2@@Z; MsoCF::CIPtr<MsoCF::IError,MsoCF::IError>::CopyTo(MsoCF::IError * *)
0x180c2dd27  mov     r8d, 15923E3h
0x180c2dd2d  jmp     loc_180C2DC95
0x180c2dd32  mov     edx, 8Dh
0x180c2dd37  mov     rcx, [rsp+1C30h+var_1BE8]
0x180c2dd3c  call    ?IsCsiError@Csi@@YA_NPEBUIError@MsoCF@@VCsiErrorCode@1@@Z; Csi::IsCsiError(MsoCF::IError const *,Csi::CsiErrorCode)
0x180c2dd41  test    al, al
0x180c2dd43  jz      short loc_180C2DD76
0x180c2dd45  mov     rdx, [rsp+1C30h+var_1BC0]
0x180c2dd4a  lea     rcx, [rsp+1C30h+var_1BE8]
0x180c2dd4f  call    ?CopyTo@?$CIPtr@UIError@MsoCF@@U12@@MsoCF@@QEBA_NPEAPEAUIError@2@@Z; MsoCF::CIPtr<MsoCF::IError,MsoCF::IError>::CopyTo(MsoCF::IError * *)
0x180c2dd54  mov     rax, [rsp+1C30h+var_1BC0]
0x180c2dd59  mov     r8d, 2336260Ah; struct MsoCF::IError *
0x180c2dd5f  mov     rdx, [rax]; struct Mso::Telemetry::Activity *
0x180c2dd62  lea     rcx, [rsp+1C30h+var_1BB8]; this
0x180c2dd67  call    ?SetActivityResultIErrorTag@Csi@@YAXAEAUActivity@Telemetry@Mso@@AEBUIError@MsoCF@@I@Z; Csi::SetActivityResultIErrorTag(Mso::Telemetry::Activity &,MsoCF::IError const &,uint)
0x180c2dd6c  call    ?ShowStorageOutOfCapacityAlert@@YAXXZ; ShowStorageOutOfCapacityAlert(void)
0x180c2dd71  jmp     loc_180C2FC88
0x180c2dd76  mov     eax, dword ptr [rbp+1B30h+var_16F0+4]
0x180c2dd7c  test    al, 10h
0x180c2dd7e  jz      loc_180C2E4B0
0x180c2dd84  mov     edx, 0DC6h
0x180c2dd89  mov     rcx, [rsp+1C30h+var_1BE8]
0x180c2dd8e  call    ?IsCsiError@Csi@@YA_NPEBUIError@MsoCF@@VCsiErrorCode@1@@Z; Csi::IsCsiError(MsoCF::IError const *,Csi::CsiErrorCode)
0x180c2dd93  test    al, al
0x180c2dd95  jnz     loc_180C2DFA1
0x180c2dd9b  call    cs:__imp_?IsWopiPromptingOnOpenEnabled@ResourceInfo@Mso@@YA_NXZ; Mso::ResourceInfo::IsWopiPromptingOnOpenEnabled(void)
0x180c2dda1  test    al, al
0x180c2dda3  jz      short loc_180C2DDB7
0x180c2dda5  mov     rcx, [rsp+1C30h+var_1BE8]; this
0x180c2ddaa  call    ?IsWopiAuthenticationError@Csi@@YA_NPEAUIError@MsoCF@@@Z; Csi::IsWopiAuthenticationError(MsoCF::IError *)
0x180c2ddaf  test    al, al
0x180c2ddb1  jnz     loc_180C2DFA1
0x180c2ddb7  mov     eax, dword ptr [rbp+1B30h+var_16F0+4]
0x180c2ddbd  test    al, 10h
0x180c2ddbf  jz      loc_180C2E4B0
0x180c2ddc5  mov     edx, 15FEh
0x180c2ddca  mov     rcx, [rsp+1C30h+var_1BE8]
0x180c2ddcf  call    ?IsCsiError@Csi@@YA_NPEBUIError@MsoCF@@VCsiErrorCode@1@@Z; Csi::IsCsiError(MsoCF::IError const *,Csi::CsiErrorCode)
0x180c2ddd4  test    al, al
0x180c2ddd6  jz      loc_180C2E4B0
0x180c2dddc  mov     rdx, [rsp+1C30h+var_1BC0]
0x180c2dde1  lea     rcx, [rsp+1C30h+var_1BE8]
0x180c2dde6  call    ?CopyTo@?$CIPtr@UIError@MsoCF@@U12@@MsoCF@@QEBA_NPEAPEAUIError@2@@Z; MsoCF::CIPtr<MsoCF::IError,MsoCF::IError>::CopyTo(MsoCF::IError * *)
0x180c2ddeb  mov     rax, [rsp+1C30h+var_1BC0]
  ... truncated ...
```
