# Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::get_IsRunning

- ea: `0x12c0`
- end: `0x12ca`
- name: `Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::get_IsRunning`
- size: `10`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1290`
- `0x12d0`
- `0x1430`

## pseudocode

```c

```

## disassembly

```asm
0x12c0  ldarg.0
0x12c1  ldfld    class [mscorlib]System.IDisposable Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::_webAppDisposable
0x12c6  ldnull
0x12c7  cgt.un
0x12c9  ret
```
