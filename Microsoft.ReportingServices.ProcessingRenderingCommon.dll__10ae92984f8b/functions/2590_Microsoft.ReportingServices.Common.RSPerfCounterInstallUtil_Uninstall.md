# Microsoft.ReportingServices.Common.RSPerfCounterInstallUtil::Uninstall

- ea: `0x2590`
- end: `0x2619`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterInstallUtil::Uninstall`
- size: `137`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x2590`

## string_xrefs

- `0x25ec`: `MSRS 2017 Web Service`
- `0x25f8`: `MSRS 2017 Web Service`
- `0x2593`: `MSRS 2017 Web Service SharePoint Mode`
- `0x259f`: `MSRS 2017 Web Service SharePoint Mode`
- `0x2602`: `MSRS 2017 Windows Service`
- `0x260e`: `MSRS 2017 Windows Service`
- `0x25a9`: `MSRS 2017 Windows Service SharePoint Mode`
- `0x25b5`: `MSRS 2017 Windows Service SharePoint Mode`
- `0x25bf`: `ReportServerSharePoint:Service`
- `0x25cb`: `ReportServerSharePoint:Service`

## pseudocode

```c

```

## disassembly

```asm
0x2590  ldarg.0
0x2591  brfalse.s loc_25EC
0x2593  ldstr    aMsrs2017WebSer_0// "MSRS 2017 Web Service SharePoint Mode"
0x2598  call     bool [System]System.Diagnostics.PerformanceCounterCategory::Exists(string)
0x259d  brfalse.s loc_25A9
0x259f  ldstr    aMsrs2017WebSer_0// "MSRS 2017 Web Service SharePoint Mode"
0x25a4  call     void [System]System.Diagnostics.PerformanceCounterCategory::Delete(string)
0x25a9  ldstr    aMsrs2017Window_0// "MSRS 2017 Windows Service SharePoint Mo"...
0x25ae  call     bool [System]System.Diagnostics.PerformanceCounterCategory::Exists(string)
0x25b3  brfalse.s loc_25BF
0x25b5  ldstr    aMsrs2017Window_0// "MSRS 2017 Windows Service SharePoint Mo"...
0x25ba  call     void [System]System.Diagnostics.PerformanceCounterCategory::Delete(string)
0x25bf  ldstr    aReportserversh// "ReportServerSharePoint:Service"
0x25c4  call     bool [System]System.Diagnostics.PerformanceCounterCategory::Exists(string)
0x25c9  brfalse.s loc_25D5
0x25cb  ldstr    aReportserversh// "ReportServerSharePoint:Service"
0x25d0  call     void [System]System.Diagnostics.PerformanceCounterCategory::Delete(string)
0x25d5  ldstr    aReportserverPo// "ReportServer.Power View"
0x25da  call     bool [System]System.Diagnostics.PerformanceCounterCategory::Exists(string)
0x25df  brfalse.s loc_2618
0x25e1  ldstr    aReportserverPo// "ReportServer.Power View"
0x25e6  call     void [System]System.Diagnostics.PerformanceCounterCategory::Delete(string)
0x25eb  ret
0x25ec  ldstr    aMsrs2017WebSer// "MSRS 2017 Web Service"
0x25f1  call     bool [System]System.Diagnostics.PerformanceCounterCategory::Exists(string)
0x25f6  brfalse.s loc_2602
0x25f8  ldstr    aMsrs2017WebSer// "MSRS 2017 Web Service"
0x25fd  call     void [System]System.Diagnostics.PerformanceCounterCategory::Delete(string)
0x2602  ldstr    aMsrs2017Window// "MSRS 2017 Windows Service"
0x2607  call     bool [System]System.Diagnostics.PerformanceCounterCategory::Exists(string)
0x260c  brfalse.s loc_2618
0x260e  ldstr    aMsrs2017Window// "MSRS 2017 Windows Service"
0x2613  call     void [System]System.Diagnostics.PerformanceCounterCategory::Delete(string)
0x2618  ret
```
