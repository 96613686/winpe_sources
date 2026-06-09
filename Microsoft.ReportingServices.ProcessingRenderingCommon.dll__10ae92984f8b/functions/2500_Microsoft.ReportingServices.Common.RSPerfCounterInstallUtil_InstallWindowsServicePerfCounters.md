# Microsoft.ReportingServices.Common.RSPerfCounterInstallUtil::InstallWindowsServicePerfCounters

- ea: `0x2500`
- end: `0x252f`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterInstallUtil::InstallWindowsServicePerfCounters`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1560`
- `0x1ef0`
- `0x2500`

## string_xrefs

- `0x2503`: `MSRS 2017 Windows Service`
- `0x250a`: `MSRS 2017 Windows Service SharePoint Mode`

## pseudocode

```c

```

## disassembly

```asm
0x2500  ldarg.1
0x2501  brtrue.s loc_250A
0x2503  ldstr    aMsrs2017Window// "MSRS 2017 Windows Service"
0x2508  br.s     loc_250F
0x250a  ldstr    aMsrs2017Window_0// "MSRS 2017 Windows Service SharePoint Mo"...
0x250f  stloc.0
0x2510  ldloc.0
0x2511  call     bool [System]System.Diagnostics.PerformanceCounterCategory::Exists(string)
0x2516  brtrue.s loc_252E
0x2518  ldarg.0
0x2519  ldarg.1
0x251a  call     class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::GetWindowsServiceCounterInfo(bool defaultOnly, bool isSharePointMode)
0x251f  stloc.1
0x2520  ldloc.0
0x2521  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_WinService()
0x2526  ldc.i4.1
0x2527  ldloc.1
0x2528  call     class [System]System.Diagnostics.PerformanceCounterCategory [System]System.Diagnostics.PerformanceCounterCategory::Create(string, string, valuetype [System]System.Diagnostics.PerformanceCounterCategoryType, class [System]System.Diagnostics.CounterCreationDataCollection)
0x252d  pop
0x252e  ret
```
