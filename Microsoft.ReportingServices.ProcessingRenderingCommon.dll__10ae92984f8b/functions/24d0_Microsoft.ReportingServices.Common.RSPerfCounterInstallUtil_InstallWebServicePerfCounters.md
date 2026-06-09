# Microsoft.ReportingServices.Common.RSPerfCounterInstallUtil::InstallWebServicePerfCounters

- ea: `0x24d0`
- end: `0x24fe`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterInstallUtil::InstallWebServicePerfCounters`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1570`
- `0x1a10`
- `0x24d0`

## string_xrefs

- `0x24d3`: `MSRS 2017 Web Service`
- `0x24da`: `MSRS 2017 Web Service SharePoint Mode`

## pseudocode

```c

```

## disassembly

```asm
0x24d0  ldarg.1
0x24d1  brtrue.s loc_24DA
0x24d3  ldstr    aMsrs2017WebSer// "MSRS 2017 Web Service"
0x24d8  br.s     loc_24DF
0x24da  ldstr    aMsrs2017WebSer_0// "MSRS 2017 Web Service SharePoint Mode"
0x24df  stloc.0
0x24e0  ldloc.0
0x24e1  call     bool [System]System.Diagnostics.PerformanceCounterCategory::Exists(string)
0x24e6  brtrue.s loc_24FD
0x24e8  ldarg.0
0x24e9  call     class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::GetWebServiceCounterInfo(bool defaultOnly)
0x24ee  stloc.1
0x24ef  ldloc.0
0x24f0  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_WebService()
0x24f5  ldc.i4.1
0x24f6  ldloc.1
0x24f7  call     class [System]System.Diagnostics.PerformanceCounterCategory [System]System.Diagnostics.PerformanceCounterCategory::Create(string, string, valuetype [System]System.Diagnostics.PerformanceCounterCategoryType, class [System]System.Diagnostics.CounterCreationDataCollection)
0x24fc  pop
0x24fd  ret
```
