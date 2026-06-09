# Microsoft.ReportingServices.Diagnostics.Utilities.SystemResourcePackageValidationException::.ctor

- ea: `0x10050`
- end: `0x1005e`
- name: `Microsoft.ReportingServices.Diagnostics.Utilities.SystemResourcePackageValidationException::.ctor`
- size: `14`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xff10`
- `0xff50`
- `0x10020`
- `0x10070`

## callees

- `0xfee0`

## pseudocode

```c

```

## disassembly

```asm
0x10050  ldarg.0
0x10051  ldarg.1
0x10052  ldarg.2
0x10053  ldarg.3
0x10054  ldarg.s  4
0x10056  ldarg.s  5
0x10058  call     instance void Microsoft.ReportingServices.Diagnostics.Utilities.SystemResourcePackageException::.ctor(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode errorCode, string localizedMessage, class [mscorlib]System.Exception innerException, string additionalTraceMessage, object[] exceptionData)
0x1005d  ret
```
