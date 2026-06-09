# Osf::OsfActionHandler::ProcessAction(OsfHostBaseAppCommands *,IOsfSolutionReference *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,IWebAddInOptionalProperties *,SDX::SDK::IExtensionInstance * *)

- ea: `0x141057fc0`
- end: `0x14105903b`
- name: `?ProcessAction@OsfActionHandler@Osf@@UEAAJPEAVOsfHostBaseAppCommands@@PEAUIOsfSolutionReference@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2PEAUIWebAddInOptionalProperties@@PEAPEAUIExtensionInstance@SDK@SDX@@@Z`
- size: `4219`
- prototype: `__int64 __usercall@<rax>(Osf::OsfActionHandler *this@<rcx>, __int64, struct IWebAddInOptionalProperties *, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1435fade0`

## callees

- `0x140075ee0`
- `0x1400786c0`
- `0x14007e440`
- `0x1400cb510`
- `0x1400d67e0`
- `0x14016a2b0`
- `0x1408cc4b0`
- `0x1408cfe50`
- `0x140ed0130`
- `0x141057fc0`
- `0x14127c4d0`
- `0x1412cbec0`
- `0x1413ffb20`
- `0x141461a50`
- `0x141771f70`
- `0x1435a6a80`
- `0x1435fa810`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x1410585ce`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x14105870a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x141058f40`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1410585ce`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x14105870a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x141058f40`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x141058d99`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x141058eb9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x141058f97`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x141058d99`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x141058eb9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x141058f97`
- `OLEAUT32!__imp_VariantInit` at `0x141058817`
- `OLEAUT32!__imp_VariantInit` at `0x141058817`
- `OLEAUT32!__imp_VariantClear` at `0x141058849`
- `OLEAUT32!__imp_VariantClear` at `0x141058959`
- `OLEAUT32!__imp_VariantClear` at `0x141058a0a`
- `OLEAUT32!__imp_VariantClear` at `0x141058a72`
- `OLEAUT32!__imp_VariantClear` at `0x141058b07`
- `OLEAUT32!__imp_VariantClear` at `0x141058b4c`
- `OLEAUT32!__imp_VariantClear` at `0x141058849`
- `OLEAUT32!__imp_VariantClear` at `0x141058959`
- `OLEAUT32!__imp_VariantClear` at `0x141058a0a`
- `OLEAUT32!__imp_VariantClear` at `0x141058a72`
- `OLEAUT32!__imp_VariantClear` at `0x141058b07`
- `OLEAUT32!__imp_VariantClear` at `0x141058b4c`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x141058880`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x141058880`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x141058928`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14105894f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x141058a00`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x141058a68`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x141058928`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14105894f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x141058a00`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x141058a68`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1410588a0`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1410588a0`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1410588c0`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x141058938`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1410589e6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x141058a4f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x141058af4`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x141058b39`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1410588c0`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x141058938`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1410589e6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x141058a4f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x141058af4`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x141058b39`
- `osfshared!?SerializeSolutionReferenceToAddinId@Osf@@YAJPEBUIOsfSolutionReference@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x141058576`
- `osfshared!?SerializeSolutionReferenceToAddinId@Osf@@YAJPEBUIOsfSolutionReference@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x141058576`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141058336`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141058e0a`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141059011`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141058336`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141058e0a`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141059011`
- `Mso20Win32Client!__imp_?ThreadCurrent@Activity@Telemetry@Mso@@SAPEAU123@XZ` at `0x14105814c`
- `Mso20Win32Client!__imp_?ThreadCurrent@Activity@Telemetry@Mso@@SAPEAU123@XZ` at `0x14105814c`
- `Mso20Win32Client!__imp_??0Activity@Telemetry@Mso@@QEAA@AEBUIDetachedActivity@12@@Z` at `0x141058dd1`
- `Mso20Win32Client!__imp_??0Activity@Telemetry@Mso@@QEAA@AEBUIDetachedActivity@12@@Z` at `0x141058dd1`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1410588af`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1410588af`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141058069`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x141058069`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141058536`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141058bb3`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141058536`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x141058bb3`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x141058512`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14105864c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x141058c65`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x141058512`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14105864c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x141058c65`
- `Mso20Win32Client!__imp_??0Activity@Telemetry@Mso@@QEAA@AEBUEventName@12@AEBUIActivityParenter@12@UActivityAggregation@12@AEBUEventFlags@12@@Z` at `0x141058189`
- `Mso20Win32Client!__imp_??0Activity@Telemetry@Mso@@QEAA@AEBUEventName@12@AEBUIActivityParenter@12@UActivityAggregation@12@AEBUEventFlags@12@@Z` at `0x141058189`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x141058cb0`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x141058cb0`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x141058861`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x14105896f`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x141058a20`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x141058a8f`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x141058b18`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x141058b60`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x141058861`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x14105896f`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x141058a20`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x141058a8f`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x141058b18`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x141058b60`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x141058103`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x141058103`
- `Mso20Win32Client!__imp_?Detach@Activity@Telemetry@Mso@@QEAA?AV?$TCntPtr@UIDetachedActivity@Telemetry@Mso@@@3@XZ` at `0x141058c52`
- `Mso20Win32Client!__imp_?Detach@Activity@Telemetry@Mso@@QEAA?AV?$TCntPtr@UIDetachedActivity@Telemetry@Mso@@@3@XZ` at `0x141058c52`
- `Mso20Win32Client!__imp_MsoGetSingleProcessHostApp` at `0x14105834a`
- `Mso20Win32Client!__imp_MsoGetSingleProcessHostApp` at `0x14105834a`
- `Mso20Win32Client!__imp_?UseParenter@Activity@Telemetry@Mso@@QEBAAEAUIActivityParenter@23@XZ` at `0x141058160`
- `Mso20Win32Client!__imp_?UseParenter@Activity@Telemetry@Mso@@QEBAAEAUIActivityParenter@23@XZ` at `0x141058160`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x141058ca0`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x141058ca0`
- `Mso20Win32Client!__imp_?UseRoot@IActivityParenter@Telemetry@Mso@@SAAEAU123@XZ` at `0x141058168`
- `Mso20Win32Client!__imp_?UseRoot@IActivityParenter@Telemetry@Mso@@SAAEAU123@XZ` at `0x141058168`

## string_xrefs

- `0x141058545`: `addinScriptReady`

## pseudocode

```c

```
