# Microsoft.ReportingServices.Portal.ODataWebApi.WebApi.ODataWebApiOwinConfig::GetRoutingConventionsV2

- ea: `0xba0`
- end: `0xbc4`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.WebApi.ODataWebApiOwinConfig::GetRoutingConventionsV2`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xd530`

## callees

- `0x370`
- `0x480`

## pseudocode

```c

```

## disassembly

```asm
0xba0  ldstr    aOdatav2// "odataV2"
0xba5  ldarg.0
0xba6  call     class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.Conventions.IODataRoutingConvention> [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.Conventions.ODataRoutingConventions::CreateDefaultWithAttributeRouting(string, class [System.Web.Http]System.Web.Http.HttpConfiguration)
0xbab  dup
0xbac  ldarg.2
0xbad  newobj   instance void Microsoft.ReportingServices.Portal.ODataWebApi.MethodBasedRoutingConvention::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger)
0xbb2  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.Conventions.IODataRoutingConvention>::Add(var<u1>)
0xbb7  dup
0xbb8  ldarg.2
0xbb9  newobj   instance void Microsoft.ReportingServices.Portal.ODataWebApi.UnboundFunctionRoutingConvention::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger)
0xbbe  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.Conventions.IODataRoutingConvention>::Add(var<u1>)
0xbc3  ret
```
