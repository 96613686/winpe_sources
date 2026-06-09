# Microsoft.ReportingServices.Portal.WebHost.Owin.CustomIndexMiddleware::.ctor

- ea: `0x1ca0`
- end: `0x1cb1`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.CustomIndexMiddleware::.ctor`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1cc0`
- `0x1db0`

## pseudocode

```c

```

## disassembly

```asm
0x1ca0  ldarg.0
0x1ca1  ldarg.1
0x1ca2  ldarg.2
0x1ca3  ldarg.3
0x1ca4  call     class [mscorlib]System.IO.StreamReader Microsoft.ReportingServices.Portal.WebHost.Owin.CustomIndexMiddleware::GetIndexFile(class [Microsoft.BIServer.Owin.Common]Microsoft.BIServer.Owin.Common.Services.IExposureControl exposureControl)
0x1ca9  ldarg.s  4
0x1cab  call     instance void Microsoft.ReportingServices.Portal.WebHost.Owin.CustomIndexMiddleware::.ctor(class [Microsoft.Owin]Microsoft.Owin.OwinMiddleware next, class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration serverConfiguration, class [mscorlib]System.IO.StreamReader contentStream, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger)
0x1cb0  ret
```
