# Python::ExecutorImpl::HrExecuteCode_OnAppThread(Mso::SharedFuture<OfficePy::ExecuteResultState> &,Python::PythonCallContext *,Python::ReturnType,wchar_t const *,LXHolder<XstrHolder,LxhClonerCopyCtor<XstrHolder>,0> const *,XLSOPER const *,int,Api::AsyncCall,Mso::CancellationToken const &)

- ea: `0x143410300`
- end: `0x143412045`
- name: `?HrExecuteCode_OnAppThread@ExecutorImpl@Python@@UEAAJAEAV?$SharedFuture@UExecuteResultState@OfficePy@@@Mso@@PEAUPythonCallContext@2@W4ReturnType@2@PEB_WPEBV?$LXHolder@VXstrHolder@@V?$LxhClonerCopyCtor@VXstrHolder@@@@$0A@@@PEBVXLSOPER@@HVAsyncCall@Api@@AEBVCancellationToken@4@@Z`
- size: `7493`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, __int64, int, Api::AnyTimeToolbox *, __int64, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, char, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, char)`
- caller_count: `1`
- callee_count: `58`
- tags: ``

## callers

- `0x143412050`

## callees

- `0x1400548a0`
- `0x140058110`
- `0x14006fa10`
- `0x14007878c`
- `0x14007d410`
- `0x14007f0f0`
- `0x14007f280`
- `0x1400999d0`
- `0x1400cfc18`
- `0x14014a7d0`
- `0x1401bc1e4`
- `0x1402039d0`
- `0x1404d85c0`
- `0x1405e278c`
- `0x1405f6fb0`
- `0x1408c5c00`
- `0x1408c69e0`
- `0x1408cc550`
- `0x1408cfed0`
- `0x1408d2770`
- `0x140a27af0`
- `0x140a57cb0`
- `0x140a6e940`
- `0x1411c1120`
- `0x14127a200`
- `0x141307250`
- `0x1414dcd00`
- `0x1414f28c0`
- `0x1416ab350`
- `0x141735430`
- `0x141757440`
- `0x1417cac80`
- `0x14183f358`
- `0x142af2530`
- `0x142d06d10`
- `0x142d06df0`
- `0x142d071a0`
- `0x142d07390`
- `0x142d07410`
- `0x142d0a9e0`
- `0x1431b3a20`
- `0x1431b4350`
- `0x1431b44f0`
- `0x1431b62d0`
- `0x1431b73c0`
- `0x1431b7650`
- `0x1431b76b0`
- `0x143409a60`
- `0x143409bf0`
- `0x143409cf0`

## import_xrefs

- `MSVCP140!_Xtime_get_ticks` at `0x143411cb1`
- `MSVCP140!_Xtime_get_ticks` at `0x143411cb1`
- `MSVCP140!_Thrd_id` at `0x1434103b7`
- `MSVCP140!_Thrd_id` at `0x1434104a3`
- `MSVCP140!_Thrd_id` at `0x1434105b6`
- `MSVCP140!_Thrd_id` at `0x143410700`
- `MSVCP140!_Thrd_id` at `0x143410900`
- `MSVCP140!_Thrd_id` at `0x143410a6d`
- `MSVCP140!_Thrd_id` at `0x143410b56`
- `MSVCP140!_Thrd_id` at `0x143411b37`
- `MSVCP140!_Thrd_id` at `0x143411c80`
- `MSVCP140!_Thrd_id` at `0x1434103b7`
- `MSVCP140!_Thrd_id` at `0x1434104a3`
- `MSVCP140!_Thrd_id` at `0x1434105b6`
- `MSVCP140!_Thrd_id` at `0x143410700`
- `MSVCP140!_Thrd_id` at `0x143410900`
- `MSVCP140!_Thrd_id` at `0x143410a6d`
- `MSVCP140!_Thrd_id` at `0x143410b56`
- `MSVCP140!_Thrd_id` at `0x143411b37`
- `MSVCP140!_Thrd_id` at `0x143411c80`
- `officescr!??0DefaultFutureExecutor@OfficePy@@QEAA@AEBVCancellationToken@Mso@@@Z` at `0x143411d89`
- `officescr!??0DefaultFutureExecutor@OfficePy@@QEAA@AEBVCancellationToken@Mso@@@Z` at `0x143411e09`
- `officescr!??0DefaultFutureExecutor@OfficePy@@QEAA@AEBVCancellationToken@Mso@@@Z` at `0x143411d89`
- `officescr!??0DefaultFutureExecutor@OfficePy@@QEAA@AEBVCancellationToken@Mso@@@Z` at `0x143411e09`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1434103c9`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1434104b2`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1434105c9`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x14341070f`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x14341090f`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x143410a80`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x143410b69`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x143411b49`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x143411c8f`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1434103c9`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1434104b2`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1434105c9`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x14341070f`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x14341090f`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x143410a80`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x143410b69`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x143411b49`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x143411c8f`
- `Mso20Win32Client!__imp_??0ManualMeasureElapsedTime@Measurements@@QEAA@AEAVManualCapture@1@UMeasurementIdType@1@_N$$QEAVStopwatch@1@@Z` at `0x1434106d0`
- `Mso20Win32Client!__imp_??0ManualMeasureElapsedTime@Measurements@@QEAA@AEAVManualCapture@1@UMeasurementIdType@1@_N$$QEAVStopwatch@1@@Z` at `0x1434106d0`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1434108e0`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1434108e0`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143410481`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143410744`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143410840`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14341126c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14341138c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1434114cc`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14341150c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1434115d3`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143411783`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1434117c0`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143411822`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14341184c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143411884`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143411899`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1434119d1`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1434119f7`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143411a31`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143411a4a`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143410481`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143410744`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143410840`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14341126c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14341138c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1434114cc`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14341150c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1434115d3`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143411783`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1434117c0`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143411822`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14341184c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143411884`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143411899`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1434119d1`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1434119f7`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143411a31`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143411a4a`
- `Mso20Win32Client!__imp_?CreateReportAndDump@ShipAsserts@Mso@@YAXK_N@Z` at `0x1434117e6`
- `Mso20Win32Client!__imp_?CreateReportAndDump@ShipAsserts@Mso@@YAXK_N@Z` at `0x143411990`
- `Mso20Win32Client!__imp_?CreateReportAndDump@ShipAsserts@Mso@@YAXK_N@Z` at `0x1434117e6`
- `Mso20Win32Client!__imp_?CreateReportAndDump@ShipAsserts@Mso@@YAXK_N@Z` at `0x143411990`
- `Mso20Win32Client!__imp_??1ManualMeasureElapsedTime@Measurements@@QEAA@XZ` at `0x143410779`
- `Mso20Win32Client!__imp_??1ManualMeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1434107d5`
- `Mso20Win32Client!__imp_??1ManualMeasureElapsedTime@Measurements@@QEAA@XZ` at `0x143410779`
- `Mso20Win32Client!__imp_??1ManualMeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1434107d5`

## string_xrefs

- `0x143410f7d`: `Request created`

## pseudocode

```c

```
