# Microsoft.ReportingServices.Diagnostics.Globals::get_CurrentApplicationHasCatalogAccess

- ea: `0xaae0`
- end: `0xab04`
- name: `Microsoft.ReportingServices.Diagnostics.Globals::get_CurrentApplicationHasCatalogAccess`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x3ba0`
- `0xa930`
- `0xa960`
- `0xaae0`

## pseudocode

```c

```

## disassembly

```asm
0xaae0  call     valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.Globals::get_CurrentApplication()
0xaae5  brfalse.s loc_AAF7
0xaae7  call     valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.Globals::get_CurrentApplication()
0xaaec  ldc.i4.1
0xaaed  beq.s    loc_AAF7
0xaaef  call     valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.Globals::get_CurrentApplication()
0xaaf4  ldc.i4.3
0xaaf5  bne.un.s loc_AB02
0xaaf7  call     class Microsoft.ReportingServices.Diagnostics.RSConfiguration Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0xaafc  callvirt instance bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_ConnectionStringSet()
0xab01  ret
0xab02  ldc.i4.0
0xab03  ret
```
