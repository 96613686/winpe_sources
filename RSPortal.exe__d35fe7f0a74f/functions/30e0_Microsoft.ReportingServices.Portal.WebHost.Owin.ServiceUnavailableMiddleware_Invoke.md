# Microsoft.ReportingServices.Portal.WebHost.Owin.ServiceUnavailableMiddleware::Invoke

- ea: `0x30e0`
- end: `0x30e9`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.ServiceUnavailableMiddleware::Invoke`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x30f0`

## pseudocode

```c

```

## disassembly

```asm
0x30e0  ldarg.0
0x30e1  ldarg.1
0x30e2  ldc.i4.5
0x30e3  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.ReportingServices.Portal.WebHost.Owin.ServiceUnavailableMiddleware::ReturnResult(class [Microsoft.Owin]Microsoft.Owin.IOwinContext context, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorReason errorState)
0x30e8  ret
```
