# Microsoft.ReportingServices.Common.RSPerfCounterInstallUtil::DeleteKatmai

- ea: `0x772f0`
- end: `0x77305`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterInstallUtil::DeleteKatmai`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x772f0`: `MSRS 2008 Web Service`
- `0x772fa`: `MSRS 2008 Windows Service`

## pseudocode

```c

```

## disassembly

```asm
0x772f0  ldstr    aMsrs2008WebSer// "MSRS 2008 Web Service"
0x772f5  call     void [System]System.Diagnostics.PerformanceCounterCategory::Delete(string)
0x772fa  ldstr    aMsrs2008Window// "MSRS 2008 Windows Service"
0x772ff  call     void [System]System.Diagnostics.PerformanceCounterCategory::Delete(string)
0x77304  ret
```
