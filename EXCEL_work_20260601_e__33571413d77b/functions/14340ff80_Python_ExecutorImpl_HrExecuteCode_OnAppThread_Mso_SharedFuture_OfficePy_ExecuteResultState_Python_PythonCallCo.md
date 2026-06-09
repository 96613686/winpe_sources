# Python::ExecutorImpl::HrExecuteCode_OnAppThread(Mso::SharedFuture<OfficePy::ExecuteResultState> &,Python::PythonCallContext *,Python::ReturnType,wchar_t const *,LXHolder<XstrHolder,LxhClonerCopyCtor<XstrHolder>,0> const *,XLSOPER const *,int,Api::AsyncCall,Mso::CancellationToken const &)

- ea: `0x14340ff80`
- end: `0x143411cc5`
- name: `?HrExecuteCode_OnAppThread@ExecutorImpl@Python@@UEAAJAEAV?$SharedFuture@UExecuteResultState@OfficePy@@@Mso@@PEAUPythonCallContext@2@W4ReturnType@2@PEB_WPEBV?$LXHolder@VXstrHolder@@V?$LxhClonerCopyCtor@VXstrHolder@@@@$0A@@@PEBVXLSOPER@@HVAsyncCall@Api@@AEBVCancellationToken@4@@Z`
- size: `7493`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, __int64, int, Api::AnyTimeToolbox *, __int64, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, char, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, int, char)`
- caller_count: `1`
- callee_count: `58`
- tags: ``

## callers

- `0x143411cd0`

## callees

- `0x140054840`
- `0x1400580b0`
- `0x14006f9b0`
- `0x14007872c`
- `0x14007d3b0`
- `0x14007f090`
- `0x14007f220`
- `0x140099970`
- `0x1400cfbb8`
- `0x14014a770`
- `0x1401bc184`
- `0x140203970`
- `0x1404d8520`
- `0x1405e26ec`
- `0x1405f6f10`
- `0x1408c5b60`
- `0x1408c6940`
- `0x1408cc4b0`
- `0x1408cfe50`
- `0x1408d26f0`
- `0x140a27a70`
- `0x140a57c30`
- `0x140a6e8c0`
- `0x1411c1680`
- `0x14127a760`
- `0x1413078d0`
- `0x1414dd380`
- `0x1414f2f40`
- `0x1416ab9d0`
- `0x141736990`
- `0x1417589a0`
- `0x1417cc1e0`
- `0x1418408b8`
- `0x142af21b0`
- `0x142d06990`
- `0x142d06a70`
- `0x142d06e20`
- `0x142d07010`
- `0x142d07090`
- `0x142d0a660`
- `0x1431b36a0`
- `0x1431b3fd0`
- `0x1431b4170`
- `0x1431b5f50`
- `0x1431b7040`
- `0x1431b72d0`
- `0x1431b7330`
- `0x1434096e0`
- `0x143409870`
- `0x143409970`

## import_xrefs

- `MSVCP140!_Xtime_get_ticks` at `0x143411931`
- `MSVCP140!_Xtime_get_ticks` at `0x143411931`
- `MSVCP140!_Thrd_id` at `0x143410037`
- `MSVCP140!_Thrd_id` at `0x143410123`
- `MSVCP140!_Thrd_id` at `0x143410236`
- `MSVCP140!_Thrd_id` at `0x143410380`
- `MSVCP140!_Thrd_id` at `0x143410580`
- `MSVCP140!_Thrd_id` at `0x1434106ed`
- `MSVCP140!_Thrd_id` at `0x1434107d6`
- `MSVCP140!_Thrd_id` at `0x1434117b7`
- `MSVCP140!_Thrd_id` at `0x143411900`
- `MSVCP140!_Thrd_id` at `0x143410037`
- `MSVCP140!_Thrd_id` at `0x143410123`
- `MSVCP140!_Thrd_id` at `0x143410236`
- `MSVCP140!_Thrd_id` at `0x143410380`
- `MSVCP140!_Thrd_id` at `0x143410580`
- `MSVCP140!_Thrd_id` at `0x1434106ed`
- `MSVCP140!_Thrd_id` at `0x1434107d6`
- `MSVCP140!_Thrd_id` at `0x1434117b7`
- `MSVCP140!_Thrd_id` at `0x143411900`
- `officescr!??0DefaultFutureExecutor@OfficePy@@QEAA@AEBVCancellationToken@Mso@@@Z` at `0x143411a09`
- `officescr!??0DefaultFutureExecutor@OfficePy@@QEAA@AEBVCancellationToken@Mso@@@Z` at `0x143411a89`
- `officescr!??0DefaultFutureExecutor@OfficePy@@QEAA@AEBVCancellationToken@Mso@@@Z` at `0x143411a09`
- `officescr!??0DefaultFutureExecutor@OfficePy@@QEAA@AEBVCancellationToken@Mso@@@Z` at `0x143411a89`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x143410049`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x143410132`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x143410249`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x14341038f`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x14341058f`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x143410700`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1434107e9`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1434117c9`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x14341190f`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x143410049`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x143410132`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x143410249`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x14341038f`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x14341058f`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x143410700`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1434107e9`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1434117c9`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x14341190f`
- `Mso20Win32Client!__imp_??0ManualMeasureElapsedTime@Measurements@@QEAA@AEAVManualCapture@1@UMeasurementIdType@1@_N$$QEAVStopwatch@1@@Z` at `0x143410350`
- `Mso20Win32Client!__imp_??0ManualMeasureElapsedTime@Measurements@@QEAA@AEAVManualCapture@1@UMeasurementIdType@1@_N$$QEAVStopwatch@1@@Z` at `0x143410350`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x143410560`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x143410560`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143410101`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1434103c4`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1434104c0`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143410eec`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14341100c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14341114c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14341118c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143411253`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143411403`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143411440`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1434114a2`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1434114cc`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143411504`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143411519`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143411651`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143411677`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1434116b1`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1434116ca`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143410101`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1434103c4`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1434104c0`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143410eec`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14341100c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14341114c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14341118c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143411253`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143411403`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143411440`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1434114a2`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1434114cc`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143411504`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143411519`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143411651`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x143411677`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1434116b1`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1434116ca`
- `Mso20Win32Client!__imp_?CreateReportAndDump@ShipAsserts@Mso@@YAXK_N@Z` at `0x143411466`
- `Mso20Win32Client!__imp_?CreateReportAndDump@ShipAsserts@Mso@@YAXK_N@Z` at `0x143411610`
- `Mso20Win32Client!__imp_?CreateReportAndDump@ShipAsserts@Mso@@YAXK_N@Z` at `0x143411466`
- `Mso20Win32Client!__imp_?CreateReportAndDump@ShipAsserts@Mso@@YAXK_N@Z` at `0x143411610`
- `Mso20Win32Client!__imp_??1ManualMeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1434103f9`
- `Mso20Win32Client!__imp_??1ManualMeasureElapsedTime@Measurements@@QEAA@XZ` at `0x143410455`
- `Mso20Win32Client!__imp_??1ManualMeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1434103f9`
- `Mso20Win32Client!__imp_??1ManualMeasureElapsedTime@Measurements@@QEAA@XZ` at `0x143410455`

## string_xrefs

- `0x143410bfd`: `Request created`

## pseudocode

```c

```
