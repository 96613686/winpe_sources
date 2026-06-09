# Microsoft.ReportingServices.Common.RSPerfCounterInstallUtil::InstallSharePointServicePerfCounters

- ea: `0x2530`
- end: `0x2553`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterInstallUtil::InstallSharePointServicePerfCounters`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1580`
- `0x1fd0`
- `0x2530`

## string_xrefs

- `0x2530`: `ReportServerSharePoint:Service`

## pseudocode

```c

```

## disassembly

```asm
0x2530  ldstr    aReportserversh// "ReportServerSharePoint:Service"
0x2535  stloc.0
0x2536  ldloc.0
0x2537  call     bool [System]System.Diagnostics.PerformanceCounterCategory::Exists(string)
0x253c  brtrue.s loc_2552
0x253e  call     class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::GetSharePointServicePerfCounters()
0x2543  stloc.1
0x2544  ldloc.0
0x2545  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_SharePointService()
0x254a  ldc.i4.1
0x254b  ldloc.1
0x254c  call     class [System]System.Diagnostics.PerformanceCounterCategory [System]System.Diagnostics.PerformanceCounterCategory::Create(string, string, valuetype [System]System.Diagnostics.PerformanceCounterCategoryType, class [System]System.Diagnostics.CounterCreationDataCollection)
0x2551  pop
0x2552  ret
```
