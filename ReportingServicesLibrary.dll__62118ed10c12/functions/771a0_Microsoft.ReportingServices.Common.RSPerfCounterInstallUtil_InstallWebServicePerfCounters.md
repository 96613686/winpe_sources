# Microsoft.ReportingServices.Common.RSPerfCounterInstallUtil::InstallWebServicePerfCounters

- ea: `0x771a0`
- end: `0x771ce`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterInstallUtil::InstallWebServicePerfCounters`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xff60`

## callees

- `0x766e0`
- `0x771a0`
- `0x78d30`

## string_xrefs

- `0x771a3`: `MSRS 2022 Web Service`
- `0x771aa`: `MSRS 2022 Web Service SharePoint Mode`

## pseudocode

```c

```

## disassembly

```asm
0x771a0  ldarg.1
0x771a1  brtrue.s loc_771AA
0x771a3  ldstr    aMsrs2022WebSer// "MSRS 2022 Web Service"
0x771a8  br.s     loc_771AF
0x771aa  ldstr    aMsrs2022WebSer_0// "MSRS 2022 Web Service SharePoint Mode"
0x771af  stloc.0
0x771b0  ldloc.0
0x771b1  call     bool [System]System.Diagnostics.PerformanceCounterCategory::Exists(string)
0x771b6  brtrue.s loc_771CD
0x771b8  ldarg.0
0x771b9  call     class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::GetWebServiceCounterInfo(bool defaultOnly)
0x771be  stloc.1
0x771bf  ldloc.0
0x771c0  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_WebService()
0x771c5  ldc.i4.1
0x771c6  ldloc.1
0x771c7  call     class [System]System.Diagnostics.PerformanceCounterCategory [System]System.Diagnostics.PerformanceCounterCategory::Create(string, string, valuetype [System]System.Diagnostics.PerformanceCounterCategoryType, class [System]System.Diagnostics.CounterCreationDataCollection)
0x771cc  pop
0x771cd  ret
```
