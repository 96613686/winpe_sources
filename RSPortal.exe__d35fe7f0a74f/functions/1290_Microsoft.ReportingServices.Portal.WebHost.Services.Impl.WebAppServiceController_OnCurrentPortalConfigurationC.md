# Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::OnCurrentPortalConfigurationChanged

- ea: `0x1290`
- end: `0x12b6`
- name: `Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::OnCurrentPortalConfigurationChanged`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1290`
- `0x12c0`
- `0x12d0`
- `0x1430`

## string_xrefs

- `0x129f`: `Configuration changed. Restarting ReportServerWebApp`

## pseudocode

```c

```

## disassembly

```asm
0x1290  ldarg.0
0x1291  call     instance bool Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::get_IsRunning()
0x1296  brfalse.s loc_12B5
0x1298  ldarg.0
0x1299  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::_logger
0x129e  ldc.i4.3
0x129f  ldstr    aConfigurationC// "Configuration changed. Restarting Repor"...
0x12a4  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x12a9  ldarg.0
0x12aa  call     instance void Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::Stop()
0x12af  ldarg.0
0x12b0  call     instance void Microsoft.ReportingServices.Portal.WebHost.Services.Impl.WebAppServiceController::Start()
0x12b5  ret
```
