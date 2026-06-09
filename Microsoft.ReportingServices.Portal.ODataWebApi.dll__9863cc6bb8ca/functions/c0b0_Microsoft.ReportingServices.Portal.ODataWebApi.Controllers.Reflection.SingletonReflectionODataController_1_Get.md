# Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.SingletonReflectionODataController`1::GetRoot

- ea: `0xc0b0`
- end: `0xc126`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.SingletonReflectionODataController`1::GetRoot`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0xc0b0`

## string_xrefs

- `0xc110`: `No singleton handler for path '{0}'`

## pseudocode

```c

```

## disassembly

```asm
0xc0b0  ldarg.1
0xc0b1  callvirt instance string [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath::get_PathTemplate()
0xc0b6  ldstr    aSingleton// "~/singleton"
0xc0bb  callvirt instance bool [mscorlib]System.String::StartsWith(string)
0xc0c0  brfalse.s loc_C110
0xc0c2  newobj   instance void class <>c__DisplayClass3_0<var<u1>>::.ctor()
0xc0c7  stloc.0
0xc0c8  ldloc.0
0xc0c9  ldarg.1
0xc0ca  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment> [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath::get_Segments()
0xc0cf  ldc.i4.0
0xc0d0  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment>::get_Item(!!T0)
0xc0d5  castclass [Microsoft.OData.Core]Microsoft.OData.UriParser.SingletonSegment
0xc0da  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmSingleton [Microsoft.OData.Core]Microsoft.OData.UriParser.SingletonSegment::get_Singleton()
0xc0df  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0xc0e4  stfld    string class <>c__DisplayClass3_0<var<u1>>::singletonName
0xc0e9  ldarg.0
0xc0ea  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::get_Logger()
0xc0ef  ldc.i4.4
0xc0f0  ldloc.0
0xc0f1  ldftn    instance string class <>c__DisplayClass3_0<var<u1>>::<GetRoot>b__0()
0xc0f7  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xc0fc  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0xc101  ldarg.2
0xc102  ldc.i4.1
0xc103  stind.i4
0xc104  ldarg.0
0xc105  callvirt instance var<u1> class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.SingletonReflectionODataController`1<var<u1>>::GetSingleton()
0xc10a  box      var<u1>
0xc10f  ret
0xc110  ldstr    aNoSingletonHan// "No singleton handler for path '{0}'"
0xc115  ldarg.1
0xc116  callvirt instance string [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath::get_PathTemplate()
0xc11b  call     string [mscorlib]System.String::Format(string, object)
0xc120  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xc125  throw
```
