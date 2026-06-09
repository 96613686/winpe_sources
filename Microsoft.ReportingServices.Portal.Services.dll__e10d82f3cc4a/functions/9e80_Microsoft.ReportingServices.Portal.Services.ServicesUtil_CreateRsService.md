# Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService

- ea: `0x9e80`
- end: `0x9ec3`
- name: `Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService`
- size: `67`
- prototype: ``
- caller_count: `131`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x990`
- `0x1a70`
- `0x1a90`
- `0x1b30`
- `0x1b50`
- `0x1be0`
- `0x1c00`
- `0x1e40`
- `0x1e60`
- `0x1f30`
- `0x1ff0`
- `0x20c0`
- `0x2120`
- `0x21c0`
- `0x2200`
- `0x2270`
- `0x2290`
- `0x2370`
- `0x23f0`
- `0x2410`
- `0x24a0`
- `0x2530`
- `0x2a20`
- `0x2c20`
- `0x2c50`
- `0x2c70`
- `0x2ee0`
- `0x3000`
- `0x3180`
- `0x31e0`
- `0x3240`
- `0x3280`
- `0x32f0`
- `0x3350`
- `0x3400`
- `0x34b0`
- `0x35b0`
- `0x3830`
- `0x3b00`
- `0x4940`
- `0x4990`
- `0x49e0`
- `0x4b50`
- `0x4e30`
- `0x4e60`
- `0x4eb0`
- `0x4f70`
- `0x4fe0`
- `0x5110`
- `0x5450`

## callees

- `0x9e80`
- `0x12cb0`
- `0x12d30`

## pseudocode

```c

```

## disassembly

```asm
0x9e80  ldnull
0x9e81  stloc.0
0x9e82  ldarg.0
0x9e83  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x9e88  isinst   [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.IUserContextContainer
0x9e8d  stloc.1
0x9e8e  ldloc.1
0x9e8f  brfalse.s loc_9E9A
0x9e91  ldloc.1
0x9e92  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Portal.Services.Extensions.IdentityExtensions::ToUserContext(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.IUserContextContainer identity)
0x9e97  stloc.0
0x9e98  br.s     loc_9EA6
0x9e9a  ldarg.0
0x9e9b  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x9ea0  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Portal.Services.Extensions.IdentityExtensions::ToUserContext(class [mscorlib]System.Security.Principal.IIdentity identity)
0x9ea5  stloc.0
0x9ea6  ldloc.0
0x9ea7  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_UserName()
0x9eac  ldloc.0
0x9ead  callvirt instance object [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_UserToken()
0x9eb2  ldloc.0
0x9eb3  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x9eb8  ldsfld   class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.IRSRequestInspector Microsoft.ReportingServices.Portal.Services.RSRequestInspector::Instance
0x9ebd  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::.ctor(string, object, valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.IRSRequestInspector)
0x9ec2  ret
```
