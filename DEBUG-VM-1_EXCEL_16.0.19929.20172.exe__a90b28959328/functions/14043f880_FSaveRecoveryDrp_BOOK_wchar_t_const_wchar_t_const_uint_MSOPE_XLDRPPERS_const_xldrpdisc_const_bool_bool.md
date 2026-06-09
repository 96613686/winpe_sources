# FSaveRecoveryDrp(BOOK *,wchar_t const *,wchar_t const *,uint,MSOPE,XLDRPPERS const *,xldrpdisc const *,bool,bool)

- ea: `0x14043f880`
- end: `0x140440966`
- name: `?FSaveRecoveryDrp@@YAHPEAVBOOK@@PEB_W1IW4MSOPE@@PEBUXLDRPPERS@@PEBUxldrpdisc@@_N5@Z`
- size: `4326`
- prototype: ``
- caller_count: `4`
- callee_count: `38`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1402ef090`
- `0x140535990`
- `0x14118edf0`
- `0x1413dd800`

## callees

- `0x1400524d8`
- `0x140052520`
- `0x1400525e0`
- `0x1400526a0`
- `0x140056390`
- `0x14007ede0`
- `0x14007f620`
- `0x140099570`
- `0x1400da390`
- `0x1401d4160`
- `0x14020a1b0`
- `0x140212d90`
- `0x140255310`
- `0x1402c8d30`
- `0x1402fcf50`
- `0x1402fd330`
- `0x140306e00`
- `0x140377ab0`
- `0x14043f880`
- `0x140451980`
- `0x140494f20`
- `0x1404960b0`
- `0x1404aaf70`
- `0x1404ab240`
- `0x140748c40`
- `0x140778660`
- `0x1408c6d10`
- `0x1408c6d70`
- `0x1408cc0b0`
- `0x1408cc4f0`
- `0x1408cc550`
- `0x1408cfed0`
- `0x140f455a0`
- `0x141010e80`
- `0x1410fd970`
- `0x1411bf900`
- `0x1420154d0`
- `0x1429bdc80`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x1404404c6`
- `KERNEL32!GetSystemTime` at `0x1404404c6`
- `KERNEL32!SystemTimeToFileTime` at `0x1404404d7`
- `KERNEL32!SystemTimeToFileTime` at `0x1404404d7`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x14044018c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x14044018c`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x140440180`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x140440180`
- `ole32!CoCreateGuid` at `0x140440300`
- `ole32!CoCreateGuid` at `0x140440300`
- `MSO!__imp_?MsoGetLastModifiedTimeOnServerForDrp@@YAXPEBUIMsoOLDocument@@PEAU_FILETIME@@@Z` at `0x14044042c`
- `MSO!__imp_?MsoGetLastModifiedTimeOnServerForDrp@@YAXPEBUIMsoOLDocument@@PEAU_FILETIME@@@Z` at `0x14044042c`
- `MSO!__imp_?MsoNotifyOnAutosave@@YAXPEBUtagMSODRP@@PEB_W@Z` at `0x140440768`
- `MSO!__imp_?MsoNotifyOnAutosave@@YAXPEBUtagMSODRP@@PEB_W@Z` at `0x140440768`
- `Mso98Win32Client!__imp_?MsoHrModifyDrp@@YAJPEAUtagMSODRP@@@Z` at `0x1404405c0`
- `Mso98Win32Client!__imp_?MsoHrModifyDrp@@YAJPEAUtagMSODRP@@@Z` at `0x1404405c0`
- `Mso98Win32Client!__imp_?MsoHrCopyDrp@@YAJPEAUtagMSODRP@@PEAPEAU1@@Z` at `0x14043fa03`
- `Mso98Win32Client!__imp_?MsoHrCopyDrp@@YAJPEAUtagMSODRP@@PEAPEAU1@@Z` at `0x14044058b`
- `Mso98Win32Client!__imp_?MsoHrCopyDrp@@YAJPEAUtagMSODRP@@PEAPEAU1@@Z` at `0x14043fa03`
- `Mso98Win32Client!__imp_?MsoHrCopyDrp@@YAJPEAUtagMSODRP@@PEAPEAU1@@Z` at `0x14044058b`
- `Mso98Win32Client!__imp_?MsoHrCreateDrp@@YAJPEAUtagMSODRP@@PEAK1@Z` at `0x14043fa4c`
- `Mso98Win32Client!__imp_?MsoHrCreateDrp@@YAJPEAUtagMSODRP@@PEAK1@Z` at `0x140440520`
- `Mso98Win32Client!__imp_?MsoHrCreateDrp@@YAJPEAUtagMSODRP@@PEAK1@Z` at `0x14043fa4c`
- `Mso98Win32Client!__imp_?MsoHrCreateDrp@@YAJPEAUtagMSODRP@@PEAK1@Z` at `0x140440520`
- `Mso98Win32Client!__imp_?MsoHrGetDrpFlavor@@YAJKIPEAPEAUtagMSODRP@@@Z` at `0x14043f997`
- `Mso98Win32Client!__imp_?MsoHrGetDrpFlavor@@YAJKIPEAPEAUtagMSODRP@@@Z` at `0x14043f9c0`
- `Mso98Win32Client!__imp_?MsoHrGetDrpFlavor@@YAJKIPEAPEAUtagMSODRP@@@Z` at `0x14043f997`
- `Mso98Win32Client!__imp_?MsoHrGetDrpFlavor@@YAJKIPEAPEAUtagMSODRP@@@Z` at `0x14043f9c0`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x140440949`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x140440949`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x14043fa74`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1404405a0`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1404405f4`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x14043fa74`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1404405a0`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1404405f4`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x140440260`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1404402a0`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1404408c0`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x140440903`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x140440260`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1404402a0`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1404408c0`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x140440903`
- `Mso20Win32Client!__imp_?IsSharePointPoundPercentSupportEnabled@Experiment@Document@Mso@@YA_NXZ` at `0x14043fbc9`
- `Mso20Win32Client!__imp_?IsSharePointPoundPercentSupportEnabled@Experiment@Document@Mso@@YA_NXZ` at `0x14043fde5`
- `Mso20Win32Client!__imp_?IsSharePointPoundPercentSupportEnabled@Experiment@Document@Mso@@YA_NXZ` at `0x14043fbc9`
- `Mso20Win32Client!__imp_?IsSharePointPoundPercentSupportEnabled@Experiment@Document@Mso@@YA_NXZ` at `0x14043fde5`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140440820`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140440849`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140440889`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1404408ce`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140440911`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140440820`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140440849`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140440889`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1404408ce`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140440911`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x1404407c0`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x1404407c0`
- `Mso20Win32Client!__imp_MsoRaiseException` at `0x14043fe92`
- `Mso20Win32Client!__imp_MsoRaiseException` at `0x1404406e6`
- `Mso20Win32Client!__imp_MsoRaiseException` at `0x14043fe92`
- `Mso20Win32Client!__imp_MsoRaiseException` at `0x1404406e6`
- `Mso20Win32Client!__imp_?MsoHrResolveFullPath@@YAJPEB_WPEA_WH_N@Z` at `0x14043fe24`
- `Mso20Win32Client!__imp_?MsoHrResolveFullPath@@YAJPEB_WPEA_WH_N@Z` at `0x14043fe24`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x14043faaa`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x14043faf3`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x14043ff06`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x14043ff80`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1404400d8`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1404401c2`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x140440343`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x14043faaa`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x14043faf3`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x14043ff06`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x14043ff80`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1404400d8`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1404401c2`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x140440343`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x14043fb08`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x140440358`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x140440361`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x140440370`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x140440379`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x14043fb08`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x140440358`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x140440361`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x140440370`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x140440379`
- `Mso20Win32Client!__imp_?MsoHrGetDisplayNameFromFullUrl@@YAJPEB_WPEA_WH@Z` at `0x14043fcae`
- `Mso20Win32Client!__imp_?MsoHrGetDisplayNameFromFullUrl@@YAJPEB_WPEA_WH@Z` at `0x14043fcae`

## pseudocode

```c

```
