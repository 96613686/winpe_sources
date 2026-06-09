# Microsoft.ReportingServices.Diagnostics.Utilities.SystemResourcePackageException::.ctor

- ea: `0xfee0`
- end: `0xfefd`
- name: `Microsoft.ReportingServices.Diagnostics.Utilities.SystemResourcePackageException::.ctor`
- size: `29`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xff90`
- `0xffc0`
- `0xfff0`
- `0x10050`
- `0x100a0`

## callees

- `0xfee0`

## pseudocode

```c

```

## disassembly

```asm
0xfee0  ldarg.0
0xfee1  ldarg.1
0xfee2  ldarg.2
0xfee3  ldarg.3
0xfee4  call     bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_IsTraceInitialized()
0xfee9  brtrue.s loc_FEEE
0xfeeb  ldnull
0xfeec  br.s     loc_FEF3
0xfeee  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0xfef3  ldarg.s  4
0xfef5  ldarg.s  5
0xfef7  call     instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException::.ctor(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode, string, class [mscorlib]System.Exception, class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace, string, object[])
0xfefc  ret
```
