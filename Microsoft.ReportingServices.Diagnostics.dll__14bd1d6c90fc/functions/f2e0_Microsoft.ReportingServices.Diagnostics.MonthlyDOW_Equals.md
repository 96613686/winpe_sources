# Microsoft.ReportingServices.Diagnostics.MonthlyDOW::Equals

- ea: `0xf2e0`
- end: `0xf31f`
- name: `Microsoft.ReportingServices.Diagnostics.MonthlyDOW::Equals`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0xf210`
- `0xf230`
- `0xf250`
- `0xf2e0`

## pseudocode

```c

```

## disassembly

```asm
0xf2e0  ldc.i4.0
0xf2e1  stloc.0
0xf2e2  ldarg.1
0xf2e3  isinst   Microsoft.ReportingServices.Diagnostics.MonthlyDOW
0xf2e8  brfalse.s loc_F31D
0xf2ea  ldarg.1
0xf2eb  castclass Microsoft.ReportingServices.Diagnostics.MonthlyDOW
0xf2f0  stloc.1
0xf2f1  ldloc.1
0xf2f2  callvirt instance unsigned int32 Microsoft.ReportingServices.Diagnostics.MonthlyDOW::get_DaysOfWeek()
0xf2f7  ldarg.0
0xf2f8  call     instance unsigned int32 Microsoft.ReportingServices.Diagnostics.MonthlyDOW::get_DaysOfWeek()
0xf2fd  bne.un.s loc_F31D
0xf2ff  ldloc.1
0xf300  callvirt instance unsigned int32 Microsoft.ReportingServices.Diagnostics.MonthlyDOW::get_Months()
0xf305  ldarg.0
0xf306  call     instance unsigned int32 Microsoft.ReportingServices.Diagnostics.MonthlyDOW::get_Months()
0xf30b  bne.un.s loc_F31D
0xf30d  ldloc.1
0xf30e  callvirt instance unsigned int32 Microsoft.ReportingServices.Diagnostics.MonthlyDOW::get_Week()
0xf313  ldarg.0
0xf314  call     instance unsigned int32 Microsoft.ReportingServices.Diagnostics.MonthlyDOW::get_Week()
0xf319  bne.un.s loc_F31D
0xf31b  ldc.i4.1
0xf31c  stloc.0
0xf31d  ldloc.0
0xf31e  ret
```
