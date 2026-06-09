# Osf::OsfEwsProxy::TryHandleAuthenticationResult(Osf::OsfEwsProxySettings const *,int,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,Mso::Http::IRequest const &)

- ea: `0x1413265a0`
- end: `0x14132701d`
- name: `?TryHandleAuthenticationResult@OsfEwsProxy@Osf@@SA_NPEBUOsfEwsProxySettings@2@HAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVIRequest@Http@Mso@@@Z`
- size: `2685`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140fae6e0`

## callees

- `0x140054a50`
- `0x140075f40`
- `0x140076020`
- `0x14007f1a0`
- `0x14018e9f0`
- `0x1401e9be0`
- `0x1402c8d30`
- `0x1402fd330`
- `0x1408cc550`
- `0x1408cfed0`
- `0x140c4fe20`
- `0x140d1d840`
- `0x140dcb350`
- `0x140dceebc`
- `0x1411e1b80`
- `0x1413265a0`
- `0x141383480`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x141326b95`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x141326b95`
- `Mso98Win32Client!__imp_?MsoPrimeFromIRequestWithoutPrompting@@YAJAEAVIRequest@Http@Mso@@AEBUResult@23@PEAUIOfficeIdentity@Authentication@3@PEB_W33PEAPEAU563@@Z` at `0x141326a2a`
- `Mso98Win32Client!__imp_?MsoPrimeFromIRequestWithoutPrompting@@YAJAEAVIRequest@Http@Mso@@AEBUResult@23@PEAUIOfficeIdentity@Authentication@3@PEB_W33PEAPEAU563@@Z` at `0x141326a2a`
- `Mso98Win32Client!__imp_?MsoPromptForCredsFromIRequest@@YAJAEBUUIExecutionContext@Authentication@Mso@@AEAVIRequest@Http@3@AEBUResult@53@PEAUIOfficeIdentity@23@PEB_W44444PEAUHBITMAP__@@_N66AEA_NPEAPEAU723@@Z` at `0x141326996`
- `Mso98Win32Client!__imp_?MsoPromptForCredsFromIRequest@@YAJAEBUUIExecutionContext@Authentication@Mso@@AEAVIRequest@Http@3@AEBUResult@53@PEAUIOfficeIdentity@23@PEB_W44444PEAUHBITMAP__@@_N66AEA_NPEAPEAU723@@Z` at `0x141326996`
- `Mso30Win32Client!__imp_?GetLastAuthErrorDetails@Authentication@Mso@@YA?AV?$optional@UAuthErrorDetails@Authentication@Mso@@@std@@AEBUIMsoUrl@@@Z` at `0x141326b60`
- `Mso30Win32Client!__imp_?GetLastAuthErrorDetails@Authentication@Mso@@YA?AV?$optional@UAuthErrorDetails@Authentication@Mso@@@std@@AEBUIMsoUrl@@@Z` at `0x141326b60`
- `Mso30Win32Client!__imp_?GetAuthSchemeFromIRequest@CCredHelperUtils@@YA?AW4AUTHSCHEME@@PEB_WAEAVIRequest@Http@Mso@@@Z` at `0x141326620`
- `Mso30Win32Client!__imp_?GetAuthSchemeFromIRequest@CCredHelperUtils@@YA?AW4AUTHSCHEME@@PEB_WAEAVIRequest@Http@Mso@@@Z` at `0x141326620`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141326fb9`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141326fb9`
- `Mso20Win32Client!__imp_?ThreadCurrent@Activity@Telemetry@Mso@@SAPEAU123@XZ` at `0x1413266e0`
- `Mso20Win32Client!__imp_?ThreadCurrent@Activity@Telemetry@Mso@@SAPEAU123@XZ` at `0x1413266e0`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x141326fee`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x14132700a`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x141326fee`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x14132700a`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1413265f7`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141326659`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1413266b9`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x14132672d`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1413265f7`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141326659`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1413266b9`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x14132672d`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326780`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1413267c9`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326809`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326855`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326894`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326a59`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326ab8`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326b00`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326b73`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326bb9`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326be0`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326c18`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326c50`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326c89`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326cc1`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326cf9`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326d31`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326d69`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326da1`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326dd9`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326e14`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326e60`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326e80`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326ea0`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326ec0`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326ee3`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326f09`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326780`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1413267c9`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326809`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326855`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326894`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326a59`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326ab8`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326b00`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326b73`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326bb9`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326be0`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326c18`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326c50`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326c89`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326cc1`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326cf9`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326d31`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326d69`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326da1`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326dd9`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326e14`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326e60`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326e80`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326ea0`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326ec0`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326ee3`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141326f09`
- `Mso20Win32Client!__imp_??0Activity@Telemetry@Mso@@QEAA@AEBUEventName@12@AEBUIActivityParenter@12@UActivityAggregation@12@AEBUEventFlags@12@@Z` at `0x141326715`
- `Mso20Win32Client!__imp_??0Activity@Telemetry@Mso@@QEAA@AEBUEventName@12@AEBUIActivityParenter@12@UActivityAggregation@12@AEBUEventFlags@12@@Z` at `0x141326715`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x1413266a1`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x1413266a1`
- `Mso20Win32Client!__imp_?GetEventSamplingMetadata@Activity@Telemetry@Mso@@QEAAAEAV?$optional@VEventSamplingMetadata@Telemetry@Mso@@@std@@XZ` at `0x141326740`
- `Mso20Win32Client!__imp_?GetEventSamplingMetadata@Activity@Telemetry@Mso@@QEAAAEAV?$optional@VEventSamplingMetadata@Telemetry@Mso@@@std@@XZ` at `0x141326740`
- `Mso20Win32Client!__imp_?UseParenter@Activity@Telemetry@Mso@@QEBAAEAUIActivityParenter@23@XZ` at `0x1413266ee`
- `Mso20Win32Client!__imp_?UseParenter@Activity@Telemetry@Mso@@QEBAAEAUIActivityParenter@23@XZ` at `0x1413266ee`
- `Mso20Win32Client!__imp_?UseRoot@IActivityParenter@Telemetry@Mso@@SAAEAU123@XZ` at `0x1413266f6`
- `Mso20Win32Client!__imp_?UseRoot@IActivityParenter@Telemetry@Mso@@SAAEAU123@XZ` at `0x1413266f6`

## string_xrefs

- `0x141326ae7`: `End_TokenIsValid`
- `0x1413267b6`: `Start_TokenIsValid`

## pseudocode

```c

```
