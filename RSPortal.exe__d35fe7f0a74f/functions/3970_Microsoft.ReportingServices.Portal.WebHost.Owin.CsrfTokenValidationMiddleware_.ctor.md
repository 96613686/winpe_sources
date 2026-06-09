# Microsoft.ReportingServices.Portal.WebHost.Owin.CsrfTokenValidationMiddleware::.ctor

- ea: `0x3970`
- end: `0x39a2`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.CsrfTokenValidationMiddleware::.ctor`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x3970`

## string_xrefs

- `0x397a`: `csrfTokenValidation`

## pseudocode

```c

```

## disassembly

```asm
0x3970  ldarg.0
0x3971  ldarg.1
0x3972  call     instance void [Microsoft.Owin]Microsoft.Owin.OwinMiddleware::.ctor(class [Microsoft.Owin]Microsoft.Owin.OwinMiddleware)
0x3977  ldarg.2
0x3978  brtrue.s loc_3985
0x397a  ldstr    aCsrftokenvalid// "csrfTokenValidation"
0x397f  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3984  throw
0x3985  ldarg.3
0x3986  brtrue.s loc_3993
0x3988  ldstr    aLogger// "logger"
0x398d  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3992  throw
0x3993  ldarg.0
0x3994  ldarg.2
0x3995  stfld    class Microsoft.ReportingServices.Portal.WebHost.Services.ICsrfTokenValidation Microsoft.ReportingServices.Portal.WebHost.Owin.CsrfTokenValidationMiddleware::_csrfTokenValidation
0x399a  ldarg.0
0x399b  ldarg.3
0x399c  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Owin.CsrfTokenValidationMiddleware::_logger
0x39a1  ret
```
