# Microsoft.ReportingServices.Portal.ODataWebApi.UnboundFunctionRoutingConvention::SelectController

- ea: `0x4a0`
- end: `0x4eb`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.UnboundFunctionRoutingConvention::SelectController`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x4a0`
- `0xd100`

## pseudocode

```c

```

## disassembly

```asm
0x4a0  newobj   instance void <>c__DisplayClass3_0::.ctor()
0x4a5  stloc.0
0x4a6  ldloc.0
0x4a7  ldarg.1
0x4a8  stfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath <>c__DisplayClass3_0::odataPath
0x4ad  ldloc.0
0x4ae  ldarg.2
0x4af  stfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <>c__DisplayClass3_0::request
0x4b4  ldloc.0
0x4b5  ldfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath <>c__DisplayClass3_0::odataPath
0x4ba  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment> [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath::get_Segments()
0x4bf  call     T0x2B000002
0x4c4  isinst   [Microsoft.OData.Core]Microsoft.OData.UriParser.OperationImportSegment
0x4c9  brfalse.s loc_4E9
0x4cb  ldarg.0
0x4cc  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.ODataWebApi.UnboundFunctionRoutingConvention::_logger
0x4d1  ldc.i4.4
0x4d2  ldloc.0
0x4d3  ldftn    instance string <>c__DisplayClass3_0::<SelectController>b__0()
0x4d9  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0x4de  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0x4e3  ldstr    aUnboundfunctio// "UnboundFunction"
0x4e8  ret
0x4e9  ldnull
0x4ea  ret
```
