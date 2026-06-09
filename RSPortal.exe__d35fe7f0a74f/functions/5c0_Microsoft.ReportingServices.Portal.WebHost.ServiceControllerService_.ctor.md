# Microsoft.ReportingServices.Portal.WebHost.ServiceControllerService::.ctor

- ea: `0x5c0`
- end: `0x5f1`
- name: `Microsoft.ReportingServices.Portal.WebHost.ServiceControllerService::.ctor`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x5c0`

## string_xrefs

- `0x5c9`: `serviceController`

## pseudocode

```c

```

## disassembly

```asm
0x5c0  ldarg.0
0x5c1  call     instance void [System.ServiceProcess]System.ServiceProcess.ServiceBase::.ctor()
0x5c6  ldarg.1
0x5c7  brtrue.s loc_5D4
0x5c9  ldstr    aServicecontrol// "serviceController"
0x5ce  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5d3  throw
0x5d4  ldarg.2
0x5d5  brtrue.s loc_5E2
0x5d7  ldstr    aLogger// "logger"
0x5dc  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5e1  throw
0x5e2  ldarg.0
0x5e3  ldarg.1
0x5e4  stfld    class Microsoft.ReportingServices.Portal.WebHost.Services.IServiceController Microsoft.ReportingServices.Portal.WebHost.ServiceControllerService::_serviceController
0x5e9  ldarg.0
0x5ea  ldarg.2
0x5eb  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.ServiceControllerService::_logger
0x5f0  ret
```
