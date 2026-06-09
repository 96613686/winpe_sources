# FSaveRecoveryDrp(BOOK *,wchar_t const *,wchar_t const *,uint,MSOPE,XLDRPPERS const *,xldrpdisc const *,bool,bool)

- ea: `0x140455560`
- end: `0x140456646`
- name: `?FSaveRecoveryDrp@@YAHPEAVBOOK@@PEB_W1IW4MSOPE@@PEBUXLDRPPERS@@PEBUxldrpdisc@@_N5@Z`
- size: `4326`
- prototype: ``
- caller_count: `4`
- callee_count: `38`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1402fa361`
- `0x140540aa0`
- `0x14119a960`
- `0x1413c3860`

## callees

- `0x140052b78`
- `0x140052bc0`
- `0x140052c80`
- `0x140052d40`
- `0x140056ad0`
- `0x14007f7c0`
- `0x140080000`
- `0x14009a050`
- `0x1400dad50`
- `0x1401bfdd0`
- `0x1401d3b90`
- `0x14020dbf0`
- `0x14026bda0`
- `0x1402f9030`
- `0x140307f80`
- `0x140308ad0`
- `0x140337080`
- `0x140376b20`
- `0x140455560`
- `0x14046db20`
- `0x1404a5c00`
- `0x1404a6aa0`
- `0x1404b4e80`
- `0x1404b57f0`
- `0x140704020`
- `0x140781810`
- `0x1408ce6a0`
- `0x1408ce700`
- `0x1408d2410`
- `0x1408d2b50`
- `0x1408d2bb0`
- `0x1408d6570`
- `0x140f547a0`
- `0x1410244d0`
- `0x14110f520`
- `0x1411c8bc0`
- `0x1420086d0`
- `0x1429e0f10`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x1404561a6`
- `KERNEL32!GetSystemTime` at `0x1404561a6`
- `KERNEL32!SystemTimeToFileTime` at `0x1404561b7`
- `KERNEL32!SystemTimeToFileTime` at `0x1404561b7`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x140455e60`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x140455e60`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x140455e6c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x140455e6c`
- `ole32!CoCreateGuid` at `0x140455fe0`
- `ole32!CoCreateGuid` at `0x140455fe0`
- `MSO!__imp_?MsoGetLastModifiedTimeOnServerForDrp@@YAXPEBUIMsoOLDocument@@PEAU_FILETIME@@@Z` at `0x14045610c`
- `MSO!__imp_?MsoGetLastModifiedTimeOnServerForDrp@@YAXPEBUIMsoOLDocument@@PEAU_FILETIME@@@Z` at `0x14045610c`
- `MSO!__imp_?MsoNotifyOnAutosave@@YAXPEBUtagMSODRP@@PEB_W@Z` at `0x140456448`
- `MSO!__imp_?MsoNotifyOnAutosave@@YAXPEBUtagMSODRP@@PEB_W@Z` at `0x140456448`
- `Mso98Win32Client!__imp_?MsoHrModifyDrp@@YAJPEAUtagMSODRP@@@Z` at `0x1404562a0`
- `Mso98Win32Client!__imp_?MsoHrModifyDrp@@YAJPEAUtagMSODRP@@@Z` at `0x1404562a0`
- `Mso98Win32Client!__imp_?MsoHrCopyDrp@@YAJPEAUtagMSODRP@@PEAPEAU1@@Z` at `0x1404556e3`
- `Mso98Win32Client!__imp_?MsoHrCopyDrp@@YAJPEAUtagMSODRP@@PEAPEAU1@@Z` at `0x14045626b`
- `Mso98Win32Client!__imp_?MsoHrCopyDrp@@YAJPEAUtagMSODRP@@PEAPEAU1@@Z` at `0x1404556e3`
- `Mso98Win32Client!__imp_?MsoHrCopyDrp@@YAJPEAUtagMSODRP@@PEAPEAU1@@Z` at `0x14045626b`
- `Mso98Win32Client!__imp_?MsoHrCreateDrp@@YAJPEAUtagMSODRP@@PEAK1@Z` at `0x14045572c`
- `Mso98Win32Client!__imp_?MsoHrCreateDrp@@YAJPEAUtagMSODRP@@PEAK1@Z` at `0x140456200`
- `Mso98Win32Client!__imp_?MsoHrCreateDrp@@YAJPEAUtagMSODRP@@PEAK1@Z` at `0x14045572c`
- `Mso98Win32Client!__imp_?MsoHrCreateDrp@@YAJPEAUtagMSODRP@@PEAK1@Z` at `0x140456200`
- `Mso98Win32Client!__imp_?MsoHrGetDrpFlavor@@YAJKIPEAPEAUtagMSODRP@@@Z` at `0x140455677`
- `Mso98Win32Client!__imp_?MsoHrGetDrpFlavor@@YAJKIPEAPEAUtagMSODRP@@@Z` at `0x1404556a0`
- `Mso98Win32Client!__imp_?MsoHrGetDrpFlavor@@YAJKIPEAPEAUtagMSODRP@@@Z` at `0x140455677`
- `Mso98Win32Client!__imp_?MsoHrGetDrpFlavor@@YAJKIPEAPEAUtagMSODRP@@@Z` at `0x1404556a0`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x140456629`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x140456629`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x140455754`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x140456280`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1404562d4`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x140455754`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x140456280`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1404562d4`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x140455f40`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x140455f80`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1404565a0`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1404565e3`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x140455f40`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x140455f80`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1404565a0`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1404565e3`
- `Mso20Win32Client!__imp_?IsSharePointPoundPercentSupportEnabled@Experiment@Document@Mso@@YA_NXZ` at `0x1404558a9`
- `Mso20Win32Client!__imp_?IsSharePointPoundPercentSupportEnabled@Experiment@Document@Mso@@YA_NXZ` at `0x140455ac5`
- `Mso20Win32Client!__imp_?IsSharePointPoundPercentSupportEnabled@Experiment@Document@Mso@@YA_NXZ` at `0x1404558a9`
- `Mso20Win32Client!__imp_?IsSharePointPoundPercentSupportEnabled@Experiment@Document@Mso@@YA_NXZ` at `0x140455ac5`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140456500`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140456529`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140456569`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1404565ae`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1404565f1`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140456500`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140456529`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140456569`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1404565ae`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1404565f1`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x1404564a0`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x1404564a0`
- `Mso20Win32Client!__imp_MsoRaiseException` at `0x140455b72`
- `Mso20Win32Client!__imp_MsoRaiseException` at `0x1404563c6`
- `Mso20Win32Client!__imp_MsoRaiseException` at `0x140455b72`
- `Mso20Win32Client!__imp_MsoRaiseException` at `0x1404563c6`
- `Mso20Win32Client!__imp_?MsoHrResolveFullPath@@YAJPEB_WPEA_WH_N@Z` at `0x140455b04`
- `Mso20Win32Client!__imp_?MsoHrResolveFullPath@@YAJPEB_WPEA_WH_N@Z` at `0x140455b04`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x14045578a`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1404557d3`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x140455be6`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x140455c60`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x140455db8`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x140455ea2`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x140456023`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x14045578a`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1404557d3`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x140455be6`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x140455c60`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x140455db8`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x140455ea2`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x140456023`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1404557e8`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x140456038`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x140456041`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x140456050`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x140456059`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1404557e8`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x140456038`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x140456041`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x140456050`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x140456059`
- `Mso20Win32Client!__imp_?MsoHrGetDisplayNameFromFullUrl@@YAJPEB_WPEA_WH@Z` at `0x14045598e`
- `Mso20Win32Client!__imp_?MsoHrGetDisplayNameFromFullUrl@@YAJPEB_WPEA_WH@Z` at `0x14045598e`

## pseudocode

```c

```
