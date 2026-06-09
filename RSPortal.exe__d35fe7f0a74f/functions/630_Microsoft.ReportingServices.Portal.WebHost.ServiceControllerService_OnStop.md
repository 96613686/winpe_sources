# Microsoft.ReportingServices.Portal.WebHost.ServiceControllerService::OnStop

- ea: `0x630`
- end: `0x658`
- name: `Microsoft.ReportingServices.Portal.WebHost.ServiceControllerService::OnStop`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x630`
- `0x8b0`

## string_xrefs

- `0x645`: `Unhandled exception during shutdown: {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x630  ldarg.0
0x631  ldfld    class Microsoft.ReportingServices.Portal.WebHost.Services.IServiceController Microsoft.ReportingServices.Portal.WebHost.ServiceControllerService::_serviceController
0x636  callvirt instance void Microsoft.ReportingServices.Portal.WebHost.Services.IServiceController::Stop()
0x63b  leave.s  loc_657
0x63d  stloc.0
0x63e  ldarg.0
0x63f  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.ServiceControllerService::_logger
0x644  ldc.i4.1
0x645  ldstr    aUnhandledExcep_1// "Unhandled exception during shutdown: {0"...
0x64a  ldloc.0
0x64b  call     string [mscorlib]System.String::Format(string, object)
0x650  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x655  rethrow
0x657  ret
```
