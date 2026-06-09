# FSaveRecoveryDrp(BOOK *,wchar_t const *,wchar_t const *,uint,MSOPE,XLDRPPERS const *,xldrpdisc const *,bool,bool)

- ea: `0x14043f7e0`
- end: `0x1404408c6`
- name: `?FSaveRecoveryDrp@@YAHPEAVBOOK@@PEB_W1IW4MSOPE@@PEBUXLDRPPERS@@PEBUxldrpdisc@@_N5@Z`
- size: `4326`
- prototype: ``
- caller_count: `4`
- callee_count: `38`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1402eeff0`
- `0x1405358f0`
- `0x14118f350`
- `0x1413dde80`

## callees

- `0x140052478`
- `0x1400524c0`
- `0x140052580`
- `0x140052640`
- `0x140056330`
- `0x14007ed80`
- `0x14007f5c0`
- `0x140099510`
- `0x1400da330`
- `0x1401d4100`
- `0x14020a150`
- `0x140212d30`
- `0x1402552b0`
- `0x1402c8cb0`
- `0x1402fceb0`
- `0x1402fd290`
- `0x140306d60`
- `0x140377a10`
- `0x14043f7e0`
- `0x1404518e0`
- `0x140494e80`
- `0x140496010`
- `0x1404aaed0`
- `0x1404ab1a0`
- `0x140748ba0`
- `0x1407785c0`
- `0x1408c6c70`
- `0x1408c6cd0`
- `0x1408cc010`
- `0x1408cc450`
- `0x1408cc4b0`
- `0x1408cfe50`
- `0x140f45640`
- `0x141010f20`
- `0x1410fded0`
- `0x1411bfe60`
- `0x1420152b0`
- `0x1429bda60`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x140440426`
- `KERNEL32!GetSystemTime` at `0x140440426`
- `KERNEL32!SystemTimeToFileTime` at `0x140440437`
- `KERNEL32!SystemTimeToFileTime` at `0x140440437`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1404400ec`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1404400ec`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1404400e0`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1404400e0`
- `ole32!CoCreateGuid` at `0x140440260`
- `ole32!CoCreateGuid` at `0x140440260`
- `MSO!__imp_?MsoGetLastModifiedTimeOnServerForDrp@@YAXPEBUIMsoOLDocument@@PEAU_FILETIME@@@Z` at `0x14044038c`
- `MSO!__imp_?MsoGetLastModifiedTimeOnServerForDrp@@YAXPEBUIMsoOLDocument@@PEAU_FILETIME@@@Z` at `0x14044038c`
- `MSO!__imp_?MsoNotifyOnAutosave@@YAXPEBUtagMSODRP@@PEB_W@Z` at `0x1404406c8`
- `MSO!__imp_?MsoNotifyOnAutosave@@YAXPEBUtagMSODRP@@PEB_W@Z` at `0x1404406c8`
- `Mso98Win32Client!__imp_?MsoHrModifyDrp@@YAJPEAUtagMSODRP@@@Z` at `0x140440520`
- `Mso98Win32Client!__imp_?MsoHrModifyDrp@@YAJPEAUtagMSODRP@@@Z` at `0x140440520`
- `Mso98Win32Client!__imp_?MsoHrCopyDrp@@YAJPEAUtagMSODRP@@PEAPEAU1@@Z` at `0x14043f963`
- `Mso98Win32Client!__imp_?MsoHrCopyDrp@@YAJPEAUtagMSODRP@@PEAPEAU1@@Z` at `0x1404404eb`
- `Mso98Win32Client!__imp_?MsoHrCopyDrp@@YAJPEAUtagMSODRP@@PEAPEAU1@@Z` at `0x14043f963`
- `Mso98Win32Client!__imp_?MsoHrCopyDrp@@YAJPEAUtagMSODRP@@PEAPEAU1@@Z` at `0x1404404eb`
- `Mso98Win32Client!__imp_?MsoHrCreateDrp@@YAJPEAUtagMSODRP@@PEAK1@Z` at `0x14043f9ac`
- `Mso98Win32Client!__imp_?MsoHrCreateDrp@@YAJPEAUtagMSODRP@@PEAK1@Z` at `0x140440480`
- `Mso98Win32Client!__imp_?MsoHrCreateDrp@@YAJPEAUtagMSODRP@@PEAK1@Z` at `0x14043f9ac`
- `Mso98Win32Client!__imp_?MsoHrCreateDrp@@YAJPEAUtagMSODRP@@PEAK1@Z` at `0x140440480`
- `Mso98Win32Client!__imp_?MsoHrGetDrpFlavor@@YAJKIPEAPEAUtagMSODRP@@@Z` at `0x14043f8f7`
- `Mso98Win32Client!__imp_?MsoHrGetDrpFlavor@@YAJKIPEAPEAUtagMSODRP@@@Z` at `0x14043f920`
- `Mso98Win32Client!__imp_?MsoHrGetDrpFlavor@@YAJKIPEAPEAUtagMSODRP@@@Z` at `0x14043f8f7`
- `Mso98Win32Client!__imp_?MsoHrGetDrpFlavor@@YAJKIPEAPEAUtagMSODRP@@@Z` at `0x14043f920`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x1404408a9`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x1404408a9`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x14043f9d4`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x140440500`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x140440554`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x14043f9d4`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x140440500`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x140440554`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1404401c0`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x140440200`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x140440820`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x140440863`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1404401c0`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x140440200`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x140440820`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x140440863`
- `Mso20Win32Client!__imp_?IsSharePointPoundPercentSupportEnabled@Experiment@Document@Mso@@YA_NXZ` at `0x14043fb29`
- `Mso20Win32Client!__imp_?IsSharePointPoundPercentSupportEnabled@Experiment@Document@Mso@@YA_NXZ` at `0x14043fd45`
- `Mso20Win32Client!__imp_?IsSharePointPoundPercentSupportEnabled@Experiment@Document@Mso@@YA_NXZ` at `0x14043fb29`
- `Mso20Win32Client!__imp_?IsSharePointPoundPercentSupportEnabled@Experiment@Document@Mso@@YA_NXZ` at `0x14043fd45`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140440780`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1404407a9`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1404407e9`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x14044082e`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140440871`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140440780`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1404407a9`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1404407e9`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x14044082e`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x140440871`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x140440720`
- `Mso20Win32Client!__imp_??0EventFlags@Telemetry@Mso@@QEAA@AEBV?$optional@W4SamplingPolicy@Telemetry@Mso@@@std@@AEBV?$optional@W4PersistencePriority@Telemetry@Mso@@@4@AEBV?$optional@W4CostPriority@Telemetry@Mso@@@4@AEBV?$optional@W4DataCategories@Telemetry@Mso@@@4@AEBV?$optional@W4DiagnosticLevel@Telemetry@Mso@@@4@@Z` at `0x140440720`
- `Mso20Win32Client!__imp_MsoRaiseException` at `0x14043fdf2`
- `Mso20Win32Client!__imp_MsoRaiseException` at `0x140440646`
- `Mso20Win32Client!__imp_MsoRaiseException` at `0x14043fdf2`
- `Mso20Win32Client!__imp_MsoRaiseException` at `0x140440646`
- `Mso20Win32Client!__imp_?MsoHrResolveFullPath@@YAJPEB_WPEA_WH_N@Z` at `0x14043fd84`
- `Mso20Win32Client!__imp_?MsoHrResolveFullPath@@YAJPEB_WPEA_WH_N@Z` at `0x14043fd84`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x14043fa0a`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x14043fa53`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x14043fe66`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x14043fee0`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x140440038`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x140440122`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1404402a3`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x14043fa0a`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x14043fa53`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x14043fe66`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x14043fee0`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x140440038`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x140440122`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1404402a3`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x14043fa68`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1404402b8`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1404402c1`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1404402d0`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1404402d9`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x14043fa68`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1404402b8`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1404402c1`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1404402d0`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1404402d9`
- `Mso20Win32Client!__imp_?MsoHrGetDisplayNameFromFullUrl@@YAJPEB_WPEA_WH@Z` at `0x14043fc0e`
- `Mso20Win32Client!__imp_?MsoHrGetDisplayNameFromFullUrl@@YAJPEB_WPEA_WH@Z` at `0x14043fc0e`

## pseudocode

```c

```
