# Osf::OsfActionHandler::ProcessAction(OsfHostBaseAppCommands *,IOsfSolutionReference *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,IWebAddInOptionalProperties *,SDX::SDK::IExtensionInstance * *)

- ea: `0x14106f300`
- end: `0x14107037b`
- name: `?ProcessAction@OsfActionHandler@Osf@@UEAAJPEAVOsfHostBaseAppCommands@@PEAUIOsfSolutionReference@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2PEAUIWebAddInOptionalProperties@@PEAPEAUIExtensionInstance@SDK@SDX@@@Z`
- size: `4219`
- prototype: `__int64 __usercall@<rax>(Osf::OsfActionHandler *this@<rcx>, __int64, struct IWebAddInOptionalProperties *, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1436620a0`

## callees

- `0x1400768c0`
- `0x1400790a0`
- `0x14007ee80`
- `0x1400cbfa4`
- `0x1400d71fc`
- `0x140160480`
- `0x1408d2bb0`
- `0x1408d6570`
- `0x140e890e0`
- `0x14106f300`
- `0x141131160`
- `0x141283ba0`
- `0x1413c6df0`
- `0x14143fbd0`
- `0x14178cd10`
- `0x14360e140`
- `0x143661ad0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x14106f90e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x14106fa4a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x141070280`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x14106f90e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x14106fa4a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x141070280`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1410700d9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1410701f9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1410702d7`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1410700d9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1410701f9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1410702d7`
- `OLEAUT32!__imp_VariantInit` at `0x14106fb57`
- `OLEAUT32!__imp_VariantInit` at `0x14106fb57`
- `OLEAUT32!__imp_VariantClear` at `0x14106fb89`
- `OLEAUT32!__imp_VariantClear` at `0x14106fc99`
- `OLEAUT32!__imp_VariantClear` at `0x14106fd4a`
- `OLEAUT32!__imp_VariantClear` at `0x14106fdb2`
- `OLEAUT32!__imp_VariantClear` at `0x14106fe47`
- `OLEAUT32!__imp_VariantClear` at `0x14106fe8c`
- `OLEAUT32!__imp_VariantClear` at `0x14106fb89`
- `OLEAUT32!__imp_VariantClear` at `0x14106fc99`
- `OLEAUT32!__imp_VariantClear` at `0x14106fd4a`
- `OLEAUT32!__imp_VariantClear` at `0x14106fdb2`
- `OLEAUT32!__imp_VariantClear` at `0x14106fe47`
- `OLEAUT32!__imp_VariantClear` at `0x14106fe8c`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x14106fbc0`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x14106fbc0`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14106fc68`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14106fc8f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14106fd40`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14106fda8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14106fc68`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14106fc8f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14106fd40`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14106fda8`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x14106fbe0`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x14106fbe0`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14106fc00`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14106fc78`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14106fd26`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14106fd8f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14106fe34`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14106fe79`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14106fc00`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14106fc78`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14106fd26`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14106fd8f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14106fe34`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14106fe79`
- `osfshared!?SerializeSolutionReferenceToAddinId@Osf@@YAJPEBUIOsfSolutionReference@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x14106f8b6`
- `osfshared!?SerializeSolutionReferenceToAddinId@Osf@@YAJPEBUIOsfSolutionReference@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z` at `0x14106f8b6`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x14106f676`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x14107014a`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141070351`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x14106f676`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x14107014a`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141070351`
- `Mso20Win32Client!__imp_?ThreadCurrent@Activity@Telemetry@Mso@@SAPEAU123@XZ` at `0x14106f48c`
- `Mso20Win32Client!__imp_?ThreadCurrent@Activity@Telemetry@Mso@@SAPEAU123@XZ` at `0x14106f48c`
- `Mso20Win32Client!__imp_??0Activity@Telemetry@Mso@@QEAA@AEBUIDetachedActivity@12@@Z` at `0x141070111`
- `Mso20Win32Client!__imp_??0Activity@Telemetry@Mso@@QEAA@AEBUIDetachedActivity@12@@Z` at `0x141070111`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x14106fbef`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x14106fbef`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x14106f3a9`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x14106f3a9`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x14106f876`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x14106fef3`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x14106f876`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x14106fef3`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14106f852`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14106f98c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14106ffa5`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14106f852`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14106f98c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14106ffa5`
- `Mso20Win32Client!__imp_??0Activity@Telemetry@Mso@@QEAA@AEBUEventName@12@AEBUIActivityParenter@12@UActivityAggregation@12@AEBUEventFlags@12@@Z` at `0x14106f4c9`
- `Mso20Win32Client!__imp_??0Activity@Telemetry@Mso@@QEAA@AEBUEventName@12@AEBUIActivityParenter@12@UActivityAggregation@12@AEBUEventFlags@12@@Z` at `0x14106f4c9`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x14106fff0`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x14106fff0`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x14106fba1`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x14106fcaf`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x14106fd60`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x14106fdcf`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x14106fe58`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x14106fea0`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x14106fba1`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x14106fcaf`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x14106fd60`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x14106fdcf`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x14106fe58`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x14106fea0`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x14106f443`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x14106f443`
- `Mso20Win32Client!__imp_?Detach@Activity@Telemetry@Mso@@QEAA?AV?$TCntPtr@UIDetachedActivity@Telemetry@Mso@@@3@XZ` at `0x14106ff92`
- `Mso20Win32Client!__imp_?Detach@Activity@Telemetry@Mso@@QEAA?AV?$TCntPtr@UIDetachedActivity@Telemetry@Mso@@@3@XZ` at `0x14106ff92`
- `Mso20Win32Client!__imp_MsoGetSingleProcessHostApp` at `0x14106f68a`
- `Mso20Win32Client!__imp_MsoGetSingleProcessHostApp` at `0x14106f68a`
- `Mso20Win32Client!__imp_?UseParenter@Activity@Telemetry@Mso@@QEBAAEAUIActivityParenter@23@XZ` at `0x14106f4a0`
- `Mso20Win32Client!__imp_?UseParenter@Activity@Telemetry@Mso@@QEBAAEAUIActivityParenter@23@XZ` at `0x14106f4a0`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x14106ffe0`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x14106ffe0`
- `Mso20Win32Client!__imp_?UseRoot@IActivityParenter@Telemetry@Mso@@SAAEAU123@XZ` at `0x14106f4a8`
- `Mso20Win32Client!__imp_?UseRoot@IActivityParenter@Telemetry@Mso@@SAAEAU123@XZ` at `0x14106f4a8`

## string_xrefs

- `0x14106f885`: `addinScriptReady`

## pseudocode

```c

```
