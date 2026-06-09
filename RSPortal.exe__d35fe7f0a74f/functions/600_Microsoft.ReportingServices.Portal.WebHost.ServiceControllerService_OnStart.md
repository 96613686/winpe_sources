# Microsoft.ReportingServices.Portal.WebHost.ServiceControllerService::OnStart

- ea: `0x600`
- end: `0x628`
- name: `Microsoft.ReportingServices.Portal.WebHost.ServiceControllerService::OnStart`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x600`
- `0x8a0`

## string_xrefs

- `0x615`: `Unhandled exception during startup: {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x600  ldarg.0
0x601  ldfld    class Microsoft.ReportingServices.Portal.WebHost.Services.IServiceController Microsoft.ReportingServices.Portal.WebHost.ServiceControllerService::_serviceController
0x606  callvirt instance void Microsoft.ReportingServices.Portal.WebHost.Services.IServiceController::Start()
0x60b  leave.s  loc_627
0x60d  stloc.0
0x60e  ldarg.0
0x60f  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.ServiceControllerService::_logger
0x614  ldc.i4.1
0x615  ldstr    aUnhandledExcep_0// "Unhandled exception during startup: {0}"...
0x61a  ldloc.0
0x61b  call     string [mscorlib]System.String::Format(string, object)
0x620  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x625  rethrow
0x627  ret
```
