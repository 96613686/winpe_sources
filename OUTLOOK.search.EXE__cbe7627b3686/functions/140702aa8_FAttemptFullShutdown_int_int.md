# FAttemptFullShutdown(int,int)

- ea: `0x140702aa8`
- end: `0x1407037b2`
- name: `?FAttemptFullShutdown@@YAHHH@Z`
- size: `3338`
- prototype: `__int64 __fastcall(int, int)`
- caller_count: `4`
- callee_count: `169`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x14034ac70`
- `0x140700db0`
- `0x140702974`
- `0x14142a6f0`

## callees

- `0x14001dd7c`
- `0x140031560`
- `0x14004956c`
- `0x1400496f0`
- `0x140049730`
- `0x14005727c`
- `0x14005a280`
- `0x14006159c`
- `0x14007131c`
- `0x140073b2c`
- `0x1400da620`
- `0x1400db960`
- `0x1400dd620`
- `0x14010abac`
- `0x140110734`
- `0x140110ea4`
- `0x1401160e0`
- `0x14013dc70`
- `0x140171960`
- `0x140173f98`
- `0x140175bd8`
- `0x14017a20c`
- `0x14017e400`
- `0x14019b2f8`
- `0x1401aedac`
- `0x1401b6b90`
- `0x1401fb8d4`
- `0x1401fc814`
- `0x140212bf4`
- `0x1402294b0`
- `0x14023d950`
- `0x14024c080`
- `0x140253ab8`
- `0x1402814bc`
- `0x1402bd5d0`
- `0x1402be78c`
- `0x1402be820`
- `0x1402beaa0`
- `0x1402bf3c0`
- `0x140349fc4`
- `0x14034b730`
- `0x14034d988`
- `0x140380008`
- `0x1404215b8`
- `0x140445a48`
- `0x1404830d0`
- `0x140483128`
- `0x140483b10`
- `0x140490aa0`
- `0x140498274`

## import_xrefs

- `MSVCP140!_Mtx_unlock` at `0x140702e09`
- `MSVCP140!_Mtx_unlock` at `0x140702e43`
- `MSVCP140!_Mtx_unlock` at `0x14070317a`
- `MSVCP140!_Mtx_unlock` at `0x140703687`
- `MSVCP140!_Mtx_unlock` at `0x140702e09`
- `MSVCP140!_Mtx_unlock` at `0x140702e43`
- `MSVCP140!_Mtx_unlock` at `0x14070317a`
- `MSVCP140!_Mtx_unlock` at `0x140703687`
- `KERNEL32!GetModuleHandleA` at `0x140702d33`
- `KERNEL32!GetModuleHandleA` at `0x140702d33`
- `KERNEL32!LeaveCriticalSection` at `0x140703567`
- `KERNEL32!LeaveCriticalSection` at `0x140703567`
- `KERNEL32!GetProcAddress` at `0x140702d48`
- `KERNEL32!GetProcAddress` at `0x140702d48`
- `OLMAPI32!HrCreateOlkAsyncTask` at `0x140702d7d`
- `OLMAPI32!HrCreateOlkAsyncTask` at `0x140702d7d`
- `OLMAPI32!FIsFeatureEnabled` at `0x140702dcb`
- `OLMAPI32!FIsFeatureEnabled` at `0x140702e57`
- `OLMAPI32!FIsFeatureEnabled` at `0x140703089`
- `OLMAPI32!FIsFeatureEnabled` at `0x1407030c4`
- `OLMAPI32!FIsFeatureEnabled` at `0x1407032cc`
- `OLMAPI32!FIsFeatureEnabled` at `0x1407032db`
- `OLMAPI32!FIsFeatureEnabled` at `0x1407035c8`
- `OLMAPI32!FIsFeatureEnabled` at `0x1407035e8`
- `OLMAPI32!FIsFeatureEnabled` at `0x140703644`
- `OLMAPI32!FIsFeatureEnabled` at `0x140702dcb`
- `OLMAPI32!FIsFeatureEnabled` at `0x140702e57`
- `OLMAPI32!FIsFeatureEnabled` at `0x140703089`
- `OLMAPI32!FIsFeatureEnabled` at `0x1407030c4`
- `OLMAPI32!FIsFeatureEnabled` at `0x1407032cc`
- `OLMAPI32!FIsFeatureEnabled` at `0x1407032db`
- `OLMAPI32!FIsFeatureEnabled` at `0x1407035c8`
- `OLMAPI32!FIsFeatureEnabled` at `0x1407035e8`
- `OLMAPI32!FIsFeatureEnabled` at `0x140703644`
- `OLMAPI32!EtwTraceErrorTag` at `0x140703386`
- `OLMAPI32!EtwTraceErrorTag` at `0x140703386`
- `OLMAPI32!__imp_MAPIUninitialize` at `0x140702fcd`
- `OLMAPI32!__imp_MAPIUninitialize` at `0x140702fcd`
- `USER32!ShutdownBlockReasonCreate` at `0x140702d10`
- `USER32!ShutdownBlockReasonCreate` at `0x140702d10`
- `MSO!__imp_?MsoDrmReleaseDocumentCache@@YAXXZ` at `0x1407033f0`
- `MSO!__imp_?MsoDrmReleaseDocumentCache@@YAXXZ` at `0x1407033f0`
- `MSO!__imp_?GetDiagnosticPaneManager@DiagnosticPane@Diagsys@@YA?AV?$shared_ptr@UIDiagnosticPaneManager@DiagnosticPane@Diagsys@@@std@@XZ` at `0x140703097`
- `MSO!__imp_?GetDiagnosticPaneManager@DiagnosticPane@Diagsys@@YA?AV?$shared_ptr@UIDiagnosticPaneManager@DiagnosticPane@Diagsys@@@std@@XZ` at `0x140703097`
- `MSO!__imp_?MsoStartShutdown@@YAXXZ` at `0x140702cb3`
- `MSO!__imp_?MsoStartShutdown@@YAXXZ` at `0x140702cb3`
- `Mso98Win32Client!__imp_?MsoHrPrepareForIMShutdown@@YAJXZ` at `0x140703188`
- `Mso98Win32Client!__imp_?MsoHrPrepareForIMShutdown@@YAJXZ` at `0x140703188`
- `Mso98Win32Client!__imp_?MsoSetIMShutdownMode@@YAXH@Z` at `0x140702cad`
- `Mso98Win32Client!__imp_?MsoSetIMShutdownMode@@YAXH@Z` at `0x140702f1a`
- `Mso98Win32Client!__imp_?MsoSetIMShutdownMode@@YAXH@Z` at `0x140703182`
- `Mso98Win32Client!__imp_?MsoSetIMShutdownMode@@YAXH@Z` at `0x140702cad`
- `Mso98Win32Client!__imp_?MsoSetIMShutdownMode@@YAXH@Z` at `0x140702f1a`
- `Mso98Win32Client!__imp_?MsoSetIMShutdownMode@@YAXH@Z` at `0x140703182`
- `Mso98Win32Client!__imp_?MsoPrepareForIMFastShutdown@@YAXXZ` at `0x140702b86`
- `Mso98Win32Client!__imp_?MsoPrepareForIMFastShutdown@@YAXXZ` at `0x140702b86`
- `mso40uiWin32Client!__imp_?MsoUninitShrGlobals@@YAXXZ` at `0x140702fef`
- `mso40uiWin32Client!__imp_?MsoUninitShrGlobals@@YAXXZ` at `0x140702fef`
- `Mso30Win32Client!__imp_?UnregisterLibletInitStartupAction@Resiliency@Mso@@YAXXZ` at `0x140702fdd`
- `Mso30Win32Client!__imp_?UnregisterLibletInitStartupAction@Resiliency@Mso@@YAXXZ` at `0x140702fdd`
- `Mso30Win32Client!__imp_?GetApi@ITelemetryApi@Telemetry@Mso@@SAAEAU123@XZ` at `0x140702fff`
- `Mso30Win32Client!__imp_?GetApi@ITelemetryApi@Telemetry@Mso@@SAAEAU123@XZ` at `0x140702fff`
- `Mso30Win32Client!__imp_?IsM365BrowserLinkOpeningEnabled@Hyperlink@Mso@@YA_NW4TeamEnum@AB@2@@Z` at `0x140703655`
- `Mso30Win32Client!__imp_?IsM365BrowserLinkOpeningEnabled@Hyperlink@Mso@@YA_NW4TeamEnum@AB@2@@Z` at `0x140703655`
- `Mso30Win32Client!__imp_?IsAvailable@ITelemetryApi@Telemetry@Mso@@SA_NXZ` at `0x140702ff5`
- `Mso30Win32Client!__imp_?IsAvailable@ITelemetryApi@Telemetry@Mso@@SA_NXZ` at `0x140702ff5`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x140702b80`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x140702b80`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x140702b1b`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x140702b1b`
- `Mso20Win32Client!__imp_?HrCancelScenario@PerfScenario@Mso@@YAJPEBUMsoPerfScenarioId@12@@Z` at `0x140702afa`
- `Mso20Win32Client!__imp_?HrCancelScenario@PerfScenario@Mso@@YAJPEBUMsoPerfScenarioId@12@@Z` at `0x140702afa`
- `Mso20Win32Client!__imp_?FScenarioActive@PerfScenario@Mso@@YA_NPEBUMsoPerfScenarioId@12@@Z` at `0x140702ae9`
- `Mso20Win32Client!__imp_?FScenarioActive@PerfScenario@Mso@@YA_NPEBUMsoPerfScenarioId@12@@Z` at `0x140702ae9`
- `Mso20Win32Client!__imp_?HrEndScenario@PerfScenario@Mso@@YAJPEBUMsoPerfScenarioId@12@@Z` at `0x140703033`
- `Mso20Win32Client!__imp_?HrEndScenario@PerfScenario@Mso@@YAJPEBUMsoPerfScenarioId@12@@Z` at `0x140703033`
- `Mso20Win32Client!__imp_?SetGracefulExit@Details@GracefulExit@Telemetry@Mso@@YAXXZ` at `0x140702fe3`
- `Mso20Win32Client!__imp_?SetGracefulExit@Details@GracefulExit@Telemetry@Mso@@YAXXZ` at `0x140702fe3`
- `Mso20Win32Client!__imp_?HrSwitchToScenario@PerfScenario@Mso@@YAJPEBUMsoPerfScenarioId@12@0@Z` at `0x140703026`
- `Mso20Win32Client!__imp_?HrSwitchToScenario@PerfScenario@Mso@@YAJPEBUMsoPerfScenarioId@12@0@Z` at `0x140703026`
- `Mso20Win32Client!__imp_?UninitializeAndSetGracefulExit@Details@Persistence@Crash@Mso@@YAXXZ` at `0x140702fe9`
- `Mso20Win32Client!__imp_?UninitializeAndSetGracefulExit@Details@Persistence@Crash@Mso@@YAXXZ` at `0x140702fe9`

## string_xrefs

- `0x1407032b4`: `EnsureSectionRegistry`
- `0x140702d2c`: `outlmime.dll`
- `0x140703347`: `novmal::HrLaunchNewOutlookSideBySide`

## pseudocode

```c

```
