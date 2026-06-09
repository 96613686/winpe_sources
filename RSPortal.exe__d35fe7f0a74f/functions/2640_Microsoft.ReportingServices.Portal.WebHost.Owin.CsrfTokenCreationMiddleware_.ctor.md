# Microsoft.ReportingServices.Portal.WebHost.Owin.CsrfTokenCreationMiddleware::.ctor

- ea: `0x2640`
- end: `0x2664`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.CsrfTokenCreationMiddleware::.ctor`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x2640`

## string_xrefs

- `0x264a`: `csrfTokenValidation`

## pseudocode

```c

```

## disassembly

```asm
0x2640  ldarg.0
0x2641  ldarg.1
0x2642  call     instance void [Microsoft.Owin]Microsoft.Owin.OwinMiddleware::.ctor(class [Microsoft.Owin]Microsoft.Owin.OwinMiddleware)
0x2647  ldarg.2
0x2648  brtrue.s loc_2655
0x264a  ldstr    aCsrftokenvalid// "csrfTokenValidation"
0x264f  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2654  throw
0x2655  ldarg.0
0x2656  ldarg.2
0x2657  stfld    class Microsoft.ReportingServices.Portal.WebHost.Services.ICsrfTokenValidation Microsoft.ReportingServices.Portal.WebHost.Owin.CsrfTokenCreationMiddleware::_csrfTokenValidation
0x265c  ldarg.0
0x265d  ldarg.3
0x265e  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Owin.CsrfTokenCreationMiddleware::_logger
0x2663  ret
```
