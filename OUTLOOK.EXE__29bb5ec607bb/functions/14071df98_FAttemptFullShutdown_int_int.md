# FAttemptFullShutdown(int,int)

- ea: `0x14071df98`
- end: `0x14071eca2`
- name: `?FAttemptFullShutdown@@YAHHH@Z`
- size: `3338`
- prototype: `__int64 __fastcall(int, int)`
- caller_count: `4`
- callee_count: `169`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x14034a340`
- `0x140710d60`
- `0x14071911c`
- `0x14142a630`

## callees

- `0x14001dd7c`
- `0x140031560`
- `0x1400495ac`
- `0x140049730`
- `0x140049770`
- `0x1400572bc`
- `0x14005a2c0`
- `0x14006154c`
- `0x1400712cc`
- `0x140073adc`
- `0x1400da630`
- `0x1400db970`
- `0x1400dd630`
- `0x14010ab1c`
- `0x1401106a4`
- `0x140110e14`
- `0x140116050`
- `0x14013dc30`
- `0x140171920`
- `0x140173f58`
- `0x140175b98`
- `0x14017a18c`
- `0x14017e380`
- `0x14019b2d8`
- `0x1401aed8c`
- `0x1401b6b70`
- `0x1401fb0f4`
- `0x1401fc034`
- `0x140212414`
- `0x140228cd0`
- `0x14023d170`
- `0x14024b8a0`
- `0x1402532c8`
- `0x140280cac`
- `0x1402bcd30`
- `0x1402bdeec`
- `0x1402bdf80`
- `0x1402be200`
- `0x1402beb20`
- `0x140349694`
- `0x14034ae00`
- `0x14034d058`
- `0x14037f6e8`
- `0x140420ba8`
- `0x140445028`
- `0x140482570`
- `0x1404825c8`
- `0x140482fb0`
- `0x14048ff40`
- `0x1404976f4`

## import_xrefs

- `MSVCP140!_Mtx_unlock` at `0x14071e2f9`
- `MSVCP140!_Mtx_unlock` at `0x14071e333`
- `MSVCP140!_Mtx_unlock` at `0x14071e66a`
- `MSVCP140!_Mtx_unlock` at `0x14071eb77`
- `MSVCP140!_Mtx_unlock` at `0x14071e2f9`
- `MSVCP140!_Mtx_unlock` at `0x14071e333`
- `MSVCP140!_Mtx_unlock` at `0x14071e66a`
- `MSVCP140!_Mtx_unlock` at `0x14071eb77`
- `KERNEL32!GetModuleHandleA` at `0x14071e223`
- `KERNEL32!GetModuleHandleA` at `0x14071e223`
- `KERNEL32!LeaveCriticalSection` at `0x14071ea57`
- `KERNEL32!LeaveCriticalSection` at `0x14071ea57`
- `KERNEL32!GetProcAddress` at `0x14071e238`
- `KERNEL32!GetProcAddress` at `0x14071e238`
- `OLMAPI32!HrCreateOlkAsyncTask` at `0x14071e26d`
- `OLMAPI32!HrCreateOlkAsyncTask` at `0x14071e26d`
- `OLMAPI32!FIsFeatureEnabled` at `0x14071e2bb`
- `OLMAPI32!FIsFeatureEnabled` at `0x14071e347`
- `OLMAPI32!FIsFeatureEnabled` at `0x14071e579`
- `OLMAPI32!FIsFeatureEnabled` at `0x14071e5b4`
- `OLMAPI32!FIsFeatureEnabled` at `0x14071e7bc`
- `OLMAPI32!FIsFeatureEnabled` at `0x14071e7cb`
- `OLMAPI32!FIsFeatureEnabled` at `0x14071eab8`
- `OLMAPI32!FIsFeatureEnabled` at `0x14071ead8`
- `OLMAPI32!FIsFeatureEnabled` at `0x14071eb34`
- `OLMAPI32!FIsFeatureEnabled` at `0x14071e2bb`
- `OLMAPI32!FIsFeatureEnabled` at `0x14071e347`
- `OLMAPI32!FIsFeatureEnabled` at `0x14071e579`
- `OLMAPI32!FIsFeatureEnabled` at `0x14071e5b4`
- `OLMAPI32!FIsFeatureEnabled` at `0x14071e7bc`
- `OLMAPI32!FIsFeatureEnabled` at `0x14071e7cb`
- `OLMAPI32!FIsFeatureEnabled` at `0x14071eab8`
- `OLMAPI32!FIsFeatureEnabled` at `0x14071ead8`
- `OLMAPI32!FIsFeatureEnabled` at `0x14071eb34`
- `OLMAPI32!EtwTraceErrorTag` at `0x14071e876`
- `OLMAPI32!EtwTraceErrorTag` at `0x14071e876`
- `OLMAPI32!__imp_MAPIUninitialize` at `0x14071e4bd`
- `OLMAPI32!__imp_MAPIUninitialize` at `0x14071e4bd`
- `USER32!ShutdownBlockReasonCreate` at `0x14071e200`
- `USER32!ShutdownBlockReasonCreate` at `0x14071e200`
- `MSO!__imp_?MsoDrmReleaseDocumentCache@@YAXXZ` at `0x14071e8e0`
- `MSO!__imp_?MsoDrmReleaseDocumentCache@@YAXXZ` at `0x14071e8e0`
- `MSO!__imp_?GetDiagnosticPaneManager@DiagnosticPane@Diagsys@@YA?AV?$shared_ptr@UIDiagnosticPaneManager@DiagnosticPane@Diagsys@@@std@@XZ` at `0x14071e587`
- `MSO!__imp_?GetDiagnosticPaneManager@DiagnosticPane@Diagsys@@YA?AV?$shared_ptr@UIDiagnosticPaneManager@DiagnosticPane@Diagsys@@@std@@XZ` at `0x14071e587`
- `MSO!__imp_?MsoStartShutdown@@YAXXZ` at `0x14071e1a3`
- `MSO!__imp_?MsoStartShutdown@@YAXXZ` at `0x14071e1a3`
- `Mso98Win32Client!__imp_?MsoHrPrepareForIMShutdown@@YAJXZ` at `0x14071e678`
- `Mso98Win32Client!__imp_?MsoHrPrepareForIMShutdown@@YAJXZ` at `0x14071e678`
- `Mso98Win32Client!__imp_?MsoSetIMShutdownMode@@YAXH@Z` at `0x14071e19d`
- `Mso98Win32Client!__imp_?MsoSetIMShutdownMode@@YAXH@Z` at `0x14071e40a`
- `Mso98Win32Client!__imp_?MsoSetIMShutdownMode@@YAXH@Z` at `0x14071e672`
- `Mso98Win32Client!__imp_?MsoSetIMShutdownMode@@YAXH@Z` at `0x14071e19d`
- `Mso98Win32Client!__imp_?MsoSetIMShutdownMode@@YAXH@Z` at `0x14071e40a`
- `Mso98Win32Client!__imp_?MsoSetIMShutdownMode@@YAXH@Z` at `0x14071e672`
- `Mso98Win32Client!__imp_?MsoPrepareForIMFastShutdown@@YAXXZ` at `0x14071e076`
- `Mso98Win32Client!__imp_?MsoPrepareForIMFastShutdown@@YAXXZ` at `0x14071e076`
- `mso40uiWin32Client!__imp_?MsoUninitShrGlobals@@YAXXZ` at `0x14071e4df`
- `mso40uiWin32Client!__imp_?MsoUninitShrGlobals@@YAXXZ` at `0x14071e4df`
- `Mso30Win32Client!__imp_?UnregisterLibletInitStartupAction@Resiliency@Mso@@YAXXZ` at `0x14071e4cd`
- `Mso30Win32Client!__imp_?UnregisterLibletInitStartupAction@Resiliency@Mso@@YAXXZ` at `0x14071e4cd`
- `Mso30Win32Client!__imp_?GetApi@ITelemetryApi@Telemetry@Mso@@SAAEAU123@XZ` at `0x14071e4ef`
- `Mso30Win32Client!__imp_?GetApi@ITelemetryApi@Telemetry@Mso@@SAAEAU123@XZ` at `0x14071e4ef`
- `Mso30Win32Client!__imp_?IsM365BrowserLinkOpeningEnabled@Hyperlink@Mso@@YA_NW4TeamEnum@AB@2@@Z` at `0x14071eb45`
- `Mso30Win32Client!__imp_?IsM365BrowserLinkOpeningEnabled@Hyperlink@Mso@@YA_NW4TeamEnum@AB@2@@Z` at `0x14071eb45`
- `Mso30Win32Client!__imp_?IsAvailable@ITelemetryApi@Telemetry@Mso@@SA_NXZ` at `0x14071e4e5`
- `Mso30Win32Client!__imp_?IsAvailable@ITelemetryApi@Telemetry@Mso@@SA_NXZ` at `0x14071e4e5`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x14071e070`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x14071e070`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x14071e00b`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x14071e00b`
- `Mso20Win32Client!__imp_?HrCancelScenario@PerfScenario@Mso@@YAJPEBUMsoPerfScenarioId@12@@Z` at `0x14071dfea`
- `Mso20Win32Client!__imp_?HrCancelScenario@PerfScenario@Mso@@YAJPEBUMsoPerfScenarioId@12@@Z` at `0x14071dfea`
- `Mso20Win32Client!__imp_?FScenarioActive@PerfScenario@Mso@@YA_NPEBUMsoPerfScenarioId@12@@Z` at `0x14071dfd9`
- `Mso20Win32Client!__imp_?FScenarioActive@PerfScenario@Mso@@YA_NPEBUMsoPerfScenarioId@12@@Z` at `0x14071dfd9`
- `Mso20Win32Client!__imp_?HrEndScenario@PerfScenario@Mso@@YAJPEBUMsoPerfScenarioId@12@@Z` at `0x14071e523`
- `Mso20Win32Client!__imp_?HrEndScenario@PerfScenario@Mso@@YAJPEBUMsoPerfScenarioId@12@@Z` at `0x14071e523`
- `Mso20Win32Client!__imp_?SetGracefulExit@Details@GracefulExit@Telemetry@Mso@@YAXXZ` at `0x14071e4d3`
- `Mso20Win32Client!__imp_?SetGracefulExit@Details@GracefulExit@Telemetry@Mso@@YAXXZ` at `0x14071e4d3`
- `Mso20Win32Client!__imp_?HrSwitchToScenario@PerfScenario@Mso@@YAJPEBUMsoPerfScenarioId@12@0@Z` at `0x14071e516`
- `Mso20Win32Client!__imp_?HrSwitchToScenario@PerfScenario@Mso@@YAJPEBUMsoPerfScenarioId@12@0@Z` at `0x14071e516`
- `Mso20Win32Client!__imp_?UninitializeAndSetGracefulExit@Details@Persistence@Crash@Mso@@YAXXZ` at `0x14071e4d9`
- `Mso20Win32Client!__imp_?UninitializeAndSetGracefulExit@Details@Persistence@Crash@Mso@@YAXXZ` at `0x14071e4d9`

## string_xrefs

- `0x14071e21c`: `outlmime.dll`
- `0x14071e7a4`: `EnsureSectionRegistry`
- `0x14071e837`: `novmal::HrLaunchNewOutlookSideBySide`

## pseudocode

```c

```
