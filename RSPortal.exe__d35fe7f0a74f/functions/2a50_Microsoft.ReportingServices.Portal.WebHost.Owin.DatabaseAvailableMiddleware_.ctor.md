# Microsoft.ReportingServices.Portal.WebHost.Owin.DatabaseAvailableMiddleware::.ctor

- ea: `0x2a50`
- end: `0x2a66`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.DatabaseAvailableMiddleware::.ctor`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x2a50  ldarg.0
0x2a51  ldarg.1
0x2a52  call     instance void [Microsoft.Owin]Microsoft.Owin.OwinMiddleware::.ctor(class [Microsoft.Owin]Microsoft.Owin.OwinMiddleware)
0x2a57  ldarg.0
0x2a58  ldarg.3
0x2a59  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Owin.DatabaseAvailableMiddleware::_logger
0x2a5e  ldarg.0
0x2a5f  ldarg.2
0x2a60  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IDatabaseService Microsoft.ReportingServices.Portal.WebHost.Owin.DatabaseAvailableMiddleware::databaseService
0x2a65  ret
```
