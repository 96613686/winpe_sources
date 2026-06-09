# Microsoft.ReportingServices.Diagnostics.Extension::Equals

- ea: `0x50b0`
- end: `0x5100`
- name: `Microsoft.ReportingServices.Diagnostics.Extension::Equals`
- size: `80`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x4e50`
- `0x4f30`

## callees

- `0x4fc0`
- `0x4fe0`
- `0x5000`
- `0x50b0`

## pseudocode

```c

```

## disassembly

```asm
0x50b0  ldc.i4.1
0x50b1  stloc.0
0x50b2  ldarg.1
0x50b3  isinst   Microsoft.ReportingServices.Diagnostics.Extension
0x50b8  brtrue.s loc_50BC
0x50ba  ldc.i4.0
0x50bb  ret
0x50bc  ldarg.1
0x50bd  castclass Microsoft.ReportingServices.Diagnostics.Extension
0x50c2  stloc.1
0x50c3  ldarg.0
0x50c4  call     instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Assembly()
0x50c9  ldloc.1
0x50ca  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Assembly()
0x50cf  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x50d4  brtrue.s loc_50FC
0x50d6  ldarg.0
0x50d7  call     instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Class()
0x50dc  ldloc.1
0x50dd  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Class()
0x50e2  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x50e7  brtrue.s loc_50FC
0x50e9  ldarg.0
0x50ea  call     instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Configuration()
0x50ef  ldloc.1
0x50f0  callvirt instance string Microsoft.ReportingServices.Diagnostics.Extension::get_Configuration()
0x50f5  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x50fa  brfalse.s loc_50FE
0x50fc  ldc.i4.0
0x50fd  stloc.0
0x50fe  ldloc.0
0x50ff  ret
```
