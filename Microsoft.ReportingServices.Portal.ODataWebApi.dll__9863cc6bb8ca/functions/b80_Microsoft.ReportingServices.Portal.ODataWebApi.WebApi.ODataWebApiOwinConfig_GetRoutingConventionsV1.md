# Microsoft.ReportingServices.Portal.ODataWebApi.WebApi.ODataWebApiOwinConfig::GetRoutingConventionsV1

- ea: `0xb80`
- end: `0xb9e`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.WebApi.ODataWebApiOwinConfig::GetRoutingConventionsV1`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xd2f0`

## callees

- `0x370`
- `0x480`

## pseudocode

```c

```

## disassembly

```asm
0xb80  call     class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.Conventions.IODataRoutingConvention> [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.Conventions.ODataRoutingConventions::CreateDefault()
0xb85  dup
0xb86  ldarg.0
0xb87  newobj   instance void Microsoft.ReportingServices.Portal.ODataWebApi.MethodBasedRoutingConvention::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger)
0xb8c  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.Conventions.IODataRoutingConvention>::Add(var<u1>)
0xb91  dup
0xb92  ldarg.0
0xb93  newobj   instance void Microsoft.ReportingServices.Portal.ODataWebApi.UnboundFunctionRoutingConvention::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger)
0xb98  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.Conventions.IODataRoutingConvention>::Add(var<u1>)
0xb9d  ret
```
