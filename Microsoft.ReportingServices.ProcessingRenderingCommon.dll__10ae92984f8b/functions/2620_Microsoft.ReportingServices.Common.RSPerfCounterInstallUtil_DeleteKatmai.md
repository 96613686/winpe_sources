# Microsoft.ReportingServices.Common.RSPerfCounterInstallUtil::DeleteKatmai

- ea: `0x2620`
- end: `0x2635`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterInstallUtil::DeleteKatmai`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x2620`: `MSRS 2008 Web Service`
- `0x262a`: `MSRS 2008 Windows Service`

## pseudocode

```c

```

## disassembly

```asm
0x2620  ldstr    aMsrs2008WebSer// "MSRS 2008 Web Service"
0x2625  call     void [System]System.Diagnostics.PerformanceCounterCategory::Delete(string)
0x262a  ldstr    aMsrs2008Window// "MSRS 2008 Windows Service"
0x262f  call     void [System]System.Diagnostics.PerformanceCounterCategory::Delete(string)
0x2634  ret
```
