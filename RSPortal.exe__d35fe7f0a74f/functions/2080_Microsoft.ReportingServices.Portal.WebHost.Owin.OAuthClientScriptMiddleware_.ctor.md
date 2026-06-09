# Microsoft.ReportingServices.Portal.WebHost.Owin.OAuthClientScriptMiddleware::.ctor

- ea: `0x2080`
- end: `0x20b2`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.OAuthClientScriptMiddleware::.ctor`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x2080`

## string_xrefs

- `0x2098`: `oAuthClientConfigurationService`

## pseudocode

```c

```

## disassembly

```asm
0x2080  ldarg.0
0x2081  ldarg.1
0x2082  call     instance void [Microsoft.Owin]Microsoft.Owin.OwinMiddleware::.ctor(class [Microsoft.Owin]Microsoft.Owin.OwinMiddleware)
0x2087  ldarg.3
0x2088  brtrue.s loc_2095
0x208a  ldstr    aLogger// "logger"
0x208f  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2094  throw
0x2095  ldarg.2
0x2096  brtrue.s loc_20A3
0x2098  ldstr    aOauthclientcon// "oAuthClientConfigurationService"
0x209d  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x20a2  throw
0x20a3  ldarg.0
0x20a4  ldarg.3
0x20a5  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.WebHost.Owin.OAuthClientScriptMiddleware::_logger
0x20aa  ldarg.0
0x20ab  ldarg.2
0x20ac  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IOAuthClientConfigurationService Microsoft.ReportingServices.Portal.WebHost.Owin.OAuthClientScriptMiddleware::_oAuthClientConfigurationService
0x20b1  ret
```
