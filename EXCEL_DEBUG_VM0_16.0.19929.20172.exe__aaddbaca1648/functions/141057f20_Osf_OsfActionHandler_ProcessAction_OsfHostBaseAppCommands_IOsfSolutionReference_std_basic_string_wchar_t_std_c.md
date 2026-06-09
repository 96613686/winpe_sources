# Osf::OsfActionHandler::ProcessAction(OsfHostBaseAppCommands *,IOsfSolutionReference *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,IWebAddInOptionalProperties *,SDX::SDK::IExtensionInstance * *)

- ea: `0x141057f20`
- end: `0x141058f9b`
- name: `?ProcessAction@OsfActionHandler@Osf@@UEAAJPEAVOsfHostBaseAppCommands@@PEAUIOsfSolutionReference@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2PEAUIWebAddInOptionalProperties@@PEAPEAUIExtensionInstance@SDK@SDX@@@Z`
- size: `4219`
- prototype: `__int64 __usercall@<rax>(Osf::OsfActionHandler *this@<rcx>, __int64, struct IWebAddInOptionalProperties *, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1435fb160`

## callees

- `0x140075f40`
- `0x140078720`
- `0x14007e4a0`
- `0x1400cb570`
- `0x1400d6840`
- `0x14016a310`
- `0x1408cc550`
- `0x1408cfed0`
- `0x140ed01b0`
- `0x141057f20`
- `0x14127bf70`
- `0x1412cb840`
- `0x1413ff4a0`
- `0x1414613d0`
- `0x141770a10`
- `0x1435a6e00`
- `0x1435fab90`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x14105852e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x14105866a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x141058ea0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x14105852e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x14105866a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x141058ea0`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x141058cf9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x141058e19`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x141058ef7`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x141058cf9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x141058e19`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x141058ef7`
- `OLEAUT32!__imp_VariantInit` at `0x141058777`
- `OLEAUT32!__imp_VariantInit` at `0x141058777`
- `OLEAUT32!__imp_VariantClear` at `0x1410587a9`
- `OLEAUT32!__imp_VariantClear` at `0x1410588b9`
- `OLEAUT32!__imp_VariantClear` at `0x14105896a`
- `OLEAUT32!__imp_VariantClear` at `0x1410589d2`
- `OLEAUT32!__imp_VariantClear` at `0x141058a67`
- `OLEAUT32!__imp_VariantClear` at `0x141058aac`
- `OLEAUT32!__imp_VariantClear` at `0x1410587a9`
- `OLEAUT32!__imp_VariantClear` at `0x1410588b9`
- `OLEAUT32!__imp_VariantClear` at `0x14105896a`
- `OLEAUT32!__imp_VariantClear` at `0x1410589d2`
- `OLEAUT32!__imp_VariantClear` at `0x141058a67`
- `OLEAUT32!__imp_VariantClear` at `0x141058aac`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1410587e0`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1410587e0`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x141058888`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1410588af`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x141058960`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1410589c8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x141058888`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1410588af`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x141058960`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1410589c8`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x141058800`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x141058800`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x141058820`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x141058898`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x141058946`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1410589af`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x141058a54`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x141058a99`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x141058820`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x141058898`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x141058946`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1410589af`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x141058a54`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x141058a99`
- `osfshared!?SerializeSolutionReferenceToAddinId@Osf@@YAJPEBUIOsfSolutionReference@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x1410584d6`
- `osfshared!?SerializeSolutionReferenceToAddinId@Osf@@YAJPEBUIOsfSolutionReference@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x1410584d6`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141058296`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141058d6a`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141058f71`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141058296`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141058d6a`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141058f71`
- `Mso20Win32Client!__imp_?ThreadCurrent@Activity@Telemetry@Mso@@SAPEAU123@XZ` at `0x1410580ac`
- `Mso20Win32Client!__imp_?ThreadCurrent@Activity@Telemetry@Mso@@SAPEAU123@XZ` at `0x1410580ac`
- `Mso20Win32Client!__imp_??0Activity@Telemetry@Mso@@QEAA@AEBUIDetachedActivity@12@@Z` at `0x141058d31`
- `Mso20Win32Client!__imp_??0Activity@Telemetry@Mso@@QEAA@AEBUIDetachedActivity@12@@Z` at `0x141058d31`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x14105880f`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x14105880f`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141057fc9`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141057fc9`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141058496`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141058b13`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141058496`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141058b13`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x141058472`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1410585ac`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x141058bc5`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x141058472`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1410585ac`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x141058bc5`
- `Mso20Win32Client!__imp_??0Activity@Telemetry@Mso@@QEAA@AEBUEventName@12@AEBUIActivityParenter@12@UActivityAggregation@12@AEBUEventFlags@12@@Z` at `0x1410580e9`
- `Mso20Win32Client!__imp_??0Activity@Telemetry@Mso@@QEAA@AEBUEventName@12@AEBUIActivityParenter@12@UActivityAggregation@12@AEBUEventFlags@12@@Z` at `0x1410580e9`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x141058c10`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x141058c10`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x1410587c1`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x1410588cf`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x141058980`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x1410589ef`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x141058a78`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x141058ac0`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x1410587c1`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x1410588cf`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x141058980`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x1410589ef`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x141058a78`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x141058ac0`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x141058063`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x141058063`
- `Mso20Win32Client!__imp_?Detach@Activity@Telemetry@Mso@@QEAA?AV?$TCntPtr@UIDetachedActivity@Telemetry@Mso@@@3@XZ` at `0x141058bb2`
- `Mso20Win32Client!__imp_?Detach@Activity@Telemetry@Mso@@QEAA?AV?$TCntPtr@UIDetachedActivity@Telemetry@Mso@@@3@XZ` at `0x141058bb2`
- `Mso20Win32Client!__imp_MsoGetSingleProcessHostApp` at `0x1410582aa`
- `Mso20Win32Client!__imp_MsoGetSingleProcessHostApp` at `0x1410582aa`
- `Mso20Win32Client!__imp_?UseParenter@Activity@Telemetry@Mso@@QEBAAEAUIActivityParenter@23@XZ` at `0x1410580c0`
- `Mso20Win32Client!__imp_?UseParenter@Activity@Telemetry@Mso@@QEBAAEAUIActivityParenter@23@XZ` at `0x1410580c0`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x141058c00`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x141058c00`
- `Mso20Win32Client!__imp_?UseRoot@IActivityParenter@Telemetry@Mso@@SAAEAU123@XZ` at `0x1410580c8`
- `Mso20Win32Client!__imp_?UseRoot@IActivityParenter@Telemetry@Mso@@SAAEAU123@XZ` at `0x1410580c8`

## string_xrefs

- `0x1410584a5`: `addinScriptReady`

## pseudocode

```c

```
