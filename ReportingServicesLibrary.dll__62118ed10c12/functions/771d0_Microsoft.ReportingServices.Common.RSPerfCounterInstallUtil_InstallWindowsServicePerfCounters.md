# Microsoft.ReportingServices.Common.RSPerfCounterInstallUtil::InstallWindowsServicePerfCounters

- ea: `0x771d0`
- end: `0x771ff`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterInstallUtil::InstallWindowsServicePerfCounters`
- size: `47`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xff60`

## callees

- `0x76bc0`
- `0x771d0`
- `0x78d20`

## string_xrefs

- `0x771d3`: `MSRS 2022 Windows Service`
- `0x771da`: `MSRS 2022 Windows Service SharePoint Mode`

## pseudocode

```c

```

## disassembly

```asm
0x771d0  ldarg.1
0x771d1  brtrue.s loc_771DA
0x771d3  ldstr    aMsrs2022Window// "MSRS 2022 Windows Service"
0x771d8  br.s     loc_771DF
0x771da  ldstr    aMsrs2022Window_0// "MSRS 2022 Windows Service SharePoint Mo"...
0x771df  stloc.0
0x771e0  ldloc.0
0x771e1  call     bool [System]System.Diagnostics.PerformanceCounterCategory::Exists(string)
0x771e6  brtrue.s loc_771FE
0x771e8  ldarg.0
0x771e9  ldarg.1
0x771ea  call     class [System]System.Diagnostics.CounterCreationDataCollection Microsoft.ReportingServices.Common.RSPerfCounterInfo::GetWindowsServiceCounterInfo(bool defaultOnly, bool isSharePointMode)
0x771ef  stloc.1
0x771f0  ldloc.0
0x771f1  call     string Microsoft.ReportingServices.Common.RSPerfCounterRes::get_WinService()
0x771f6  ldc.i4.1
0x771f7  ldloc.1
0x771f8  call     class [System]System.Diagnostics.PerformanceCounterCategory [System]System.Diagnostics.PerformanceCounterCategory::Create(string, string, valuetype [System]System.Diagnostics.PerformanceCounterCategoryType, class [System]System.Diagnostics.CounterCreationDataCollection)
0x771fd  pop
0x771fe  ret
```
