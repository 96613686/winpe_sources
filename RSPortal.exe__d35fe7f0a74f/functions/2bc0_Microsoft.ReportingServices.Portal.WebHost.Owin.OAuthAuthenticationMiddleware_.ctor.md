# Microsoft.ReportingServices.Portal.WebHost.Owin.OAuthAuthenticationMiddleware::.ctor

- ea: `0x2bc0`
- end: `0x2bde`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.OAuthAuthenticationMiddleware::.ctor`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x2bc0  ldarg.0
0x2bc1  ldarg.1
0x2bc2  call     instance void [Microsoft.Owin]Microsoft.Owin.OwinMiddleware::.ctor(class [Microsoft.Owin]Microsoft.Owin.OwinMiddleware)
0x2bc7  ldarg.0
0x2bc8  ldarg.2
0x2bc9  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IOAuthClientConfigurationService Microsoft.ReportingServices.Portal.WebHost.Owin.OAuthAuthenticationMiddleware::_oAuthClientConfigurationService
0x2bce  ldarg.0
0x2bcf  ldarg.s  4
0x2bd1  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Owin.OAuthAuthenticationMiddleware::_logger
0x2bd6  ldarg.0
0x2bd7  ldarg.3
0x2bd8  stfld    class [Microsoft.BIServer.Owin.Common]Microsoft.BIServer.Owin.Common.Services.IAuthenticationService Microsoft.ReportingServices.Portal.WebHost.Owin.OAuthAuthenticationMiddleware::_authService
0x2bdd  ret
```
