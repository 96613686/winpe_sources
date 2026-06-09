# Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::Stop

- ea: `0x1430`
- end: `0x144b`
- name: `Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::Stop`
- size: `27`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x4d0`
- `0x1290`

## callees

- `0x12c0`
- `0x1430`

## pseudocode

```c

```

## disassembly

```asm
0x1430  ldarg.0
0x1431  call     instance bool Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::get_IsRunning()
0x1436  brfalse.s loc_144A
0x1438  ldarg.0
0x1439  ldfld    class [mscorlib]System.IDisposable Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::_webAppDisposable
0x143e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1443  ldarg.0
0x1444  ldnull
0x1445  stfld    class [mscorlib]System.IDisposable Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::_webAppDisposable
0x144a  ret
```
