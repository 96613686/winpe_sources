# Microsoft.ReportingServices.Portal.WebHost.Owin.CustomIndexMiddleware::.ctor_0

- ea: `0x1cc0`
- end: `0x1d0f`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.CustomIndexMiddleware::.ctor_0`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1ca0`

## callees

- `0x1cc0`
- `0x1e20`

## string_xrefs

- `0x1cd9`: `serverConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x1cc0  ldarg.0
0x1cc1  ldarg.1
0x1cc2  call     instance void [Microsoft.Owin]Microsoft.Owin.OwinMiddleware::.ctor(class [Microsoft.Owin]Microsoft.Owin.OwinMiddleware)
0x1cc7  ldarg.s  4
0x1cc9  brtrue.s loc_1CD6
0x1ccb  ldstr    aLogger// "logger"
0x1cd0  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1cd5  throw
0x1cd6  ldarg.2
0x1cd7  brtrue.s loc_1CE4
0x1cd9  ldstr    aServerconfigur// "serverConfiguration"
0x1cde  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1ce3  throw
0x1ce4  ldarg.3
0x1ce5  brtrue.s loc_1CF2
0x1ce7  ldstr    aContentstream// "contentStream"
0x1cec  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1cf1  throw
0x1cf2  ldarg.0
0x1cf3  ldarg.s  4
0x1cf5  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Owin.CustomIndexMiddleware::_logger
0x1cfa  ldarg.0
0x1cfb  ldarg.2
0x1cfc  stfld    class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration Microsoft.ReportingServices.Portal.WebHost.Owin.CustomIndexMiddleware::_serverConfiguration
0x1d01  ldarg.0
0x1d02  ldarg.0
0x1d03  ldarg.3
0x1d04  call     instance string Microsoft.ReportingServices.Portal.WebHost.Owin.CustomIndexMiddleware::ModifyContent(class [mscorlib]System.IO.StreamReader stream)
0x1d09  stfld    string Microsoft.ReportingServices.Portal.WebHost.Owin.CustomIndexMiddleware::_indexContents
0x1d0e  ret
```
