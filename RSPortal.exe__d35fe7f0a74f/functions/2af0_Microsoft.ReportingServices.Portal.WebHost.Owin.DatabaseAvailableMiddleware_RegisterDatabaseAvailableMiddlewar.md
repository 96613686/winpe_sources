# Microsoft.ReportingServices.Portal.WebHost.Owin.DatabaseAvailableMiddleware::RegisterDatabaseAvailableMiddleware

- ea: `0x2af0`
- end: `0x2b11`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.DatabaseAvailableMiddleware::RegisterDatabaseAvailableMiddleware`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3660`

## callees

- `0x2af0`

## pseudocode

```c

```

## disassembly

```asm
0x2af0  ldarg.1
0x2af1  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IDatabaseService::Init()
0x2af6  leave.s  loc_2AFB
0x2af8  pop
0x2af9  leave.s  loc_2AFB
0x2afb  ldarg.0
0x2afc  ldc.i4.2
0x2afd  newarr   [mscorlib]System.Object
0x2b02  dup
0x2b03  ldc.i4.0
0x2b04  ldarg.1
0x2b05  stelem.ref
0x2b06  dup
0x2b07  ldc.i4.1
0x2b08  ldarg.2
0x2b09  stelem.ref
0x2b0a  call     T0x2B00000C
0x2b0f  pop
0x2b10  ret
```
