# Microsoft.ReportingServices.Common.RSPerfCounterInstallUtil::Uninstall

- ea: `0x77260`
- end: `0x772e9`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterInstallUtil::Uninstall`
- size: `137`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xff80`

## callees

- `0x77260`

## string_xrefs

- `0x772bc`: `MSRS 2022 Web Service`
- `0x772c8`: `MSRS 2022 Web Service`
- `0x77263`: `MSRS 2022 Web Service SharePoint Mode`
- `0x7726f`: `MSRS 2022 Web Service SharePoint Mode`
- `0x772d2`: `MSRS 2022 Windows Service`
- `0x772de`: `MSRS 2022 Windows Service`
- `0x77279`: `MSRS 2022 Windows Service SharePoint Mode`
- `0x77285`: `MSRS 2022 Windows Service SharePoint Mode`
- `0x7728f`: `ReportServerSharePoint:Service`
- `0x7729b`: `ReportServerSharePoint:Service`

## pseudocode

```c

```

## disassembly

```asm
0x77260  ldarg.0
0x77261  brfalse.s loc_772BC
0x77263  ldstr    aMsrs2022WebSer_0// "MSRS 2022 Web Service SharePoint Mode"
0x77268  call     bool [System]System.Diagnostics.PerformanceCounterCategory::Exists(string)
0x7726d  brfalse.s loc_77279
0x7726f  ldstr    aMsrs2022WebSer_0// "MSRS 2022 Web Service SharePoint Mode"
0x77274  call     void [System]System.Diagnostics.PerformanceCounterCategory::Delete(string)
0x77279  ldstr    aMsrs2022Window_0// "MSRS 2022 Windows Service SharePoint Mo"...
0x7727e  call     bool [System]System.Diagnostics.PerformanceCounterCategory::Exists(string)
0x77283  brfalse.s loc_7728F
0x77285  ldstr    aMsrs2022Window_0// "MSRS 2022 Windows Service SharePoint Mo"...
0x7728a  call     void [System]System.Diagnostics.PerformanceCounterCategory::Delete(string)
0x7728f  ldstr    aReportserversh// "ReportServerSharePoint:Service"
0x77294  call     bool [System]System.Diagnostics.PerformanceCounterCategory::Exists(string)
0x77299  brfalse.s loc_772A5
0x7729b  ldstr    aReportserversh// "ReportServerSharePoint:Service"
0x772a0  call     void [System]System.Diagnostics.PerformanceCounterCategory::Delete(string)
0x772a5  ldstr    aReportserverPo// "ReportServer.Power View"
0x772aa  call     bool [System]System.Diagnostics.PerformanceCounterCategory::Exists(string)
0x772af  brfalse.s loc_772E8
0x772b1  ldstr    aReportserverPo// "ReportServer.Power View"
0x772b6  call     void [System]System.Diagnostics.PerformanceCounterCategory::Delete(string)
0x772bb  ret
0x772bc  ldstr    aMsrs2022WebSer// "MSRS 2022 Web Service"
0x772c1  call     bool [System]System.Diagnostics.PerformanceCounterCategory::Exists(string)
0x772c6  brfalse.s loc_772D2
0x772c8  ldstr    aMsrs2022WebSer// "MSRS 2022 Web Service"
0x772cd  call     void [System]System.Diagnostics.PerformanceCounterCategory::Delete(string)
0x772d2  ldstr    aMsrs2022Window// "MSRS 2022 Windows Service"
0x772d7  call     bool [System]System.Diagnostics.PerformanceCounterCategory::Exists(string)
0x772dc  brfalse.s loc_772E8
0x772de  ldstr    aMsrs2022Window// "MSRS 2022 Windows Service"
0x772e3  call     void [System]System.Diagnostics.PerformanceCounterCategory::Delete(string)
0x772e8  ret
```
