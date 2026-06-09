# Microsoft.ReportingServices.Portal.WebHost.Owin.CompositionRootVX::Create

- ea: `0x15b0`
- end: `0x15e8`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.CompositionRootVX::Create`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x15b0`

## pseudocode

```c

```

## disassembly

```asm
0x15b0  ldarg.3
0x15b1  ldtoken  [Microsoft.ReportingServices.Portal.WebApi]Microsoft.ReportingServices.Portal.WebApi.VX.Controllers.EndpointsController
0x15b6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15bb  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x15c0  brfalse.s loc_15C8
0x15c2  newobj   instance void [Microsoft.ReportingServices.Portal.WebApi]Microsoft.ReportingServices.Portal.WebApi.VX.Controllers.EndpointsController::.ctor()
0x15c7  ret
0x15c8  ldarg.3
0x15c9  ldtoken  [Microsoft.ReportingServices.Portal.WebApi]Microsoft.ReportingServices.Portal.WebApi.V2.Controllers.SessionController
0x15ce  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15d3  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x15d8  brfalse.s loc_15E6
0x15da  ldarg.0
0x15db  ldfld    class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration Microsoft.ReportingServices.Portal.WebHost.Owin.CompositionRootVX::_serverConfiguration
0x15e0  newobj   instance void [Microsoft.ReportingServices.Portal.WebApi]Microsoft.ReportingServices.Portal.WebApi.V2.Controllers.SessionController::.ctor(class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration)
0x15e5  ret
0x15e6  ldnull
0x15e7  ret
```
