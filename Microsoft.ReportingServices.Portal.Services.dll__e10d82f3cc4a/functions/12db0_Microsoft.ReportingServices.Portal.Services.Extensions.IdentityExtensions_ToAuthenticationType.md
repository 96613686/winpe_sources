# Microsoft.ReportingServices.Portal.Services.Extensions.IdentityExtensions::ToAuthenticationType

- ea: `0x12db0`
- end: `0x12dd2`
- name: `Microsoft.ReportingServices.Portal.Services.Extensions.IdentityExtensions::ToAuthenticationType`
- size: `34`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x6940`
- `0x71c0`
- `0x73b0`
- `0x1e6d0`

## callees

- `0x12cb0`
- `0x12d30`
- `0x12db0`

## pseudocode

```c

```

## disassembly

```asm
0x12db0  ldarg.0
0x12db1  isinst   [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.IUserContextContainer
0x12db6  stloc.0
0x12db7  ldloc.0
0x12db8  brtrue.s loc_12DC6
0x12dba  ldarg.0
0x12dbb  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Portal.Services.Extensions.IdentityExtensions::ToUserContext(class [mscorlib]System.Security.Principal.IIdentity identity)
0x12dc0  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x12dc5  ret
0x12dc6  ldloc.0
0x12dc7  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Portal.Services.Extensions.IdentityExtensions::ToUserContext(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.IUserContextContainer identity)
0x12dcc  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x12dd1  ret
```
