# Microsoft.ReportingServices.Portal.ODataWebApi.MethodBasedRoutingConvention::SelectAction

- ea: `0x390`
- end: `0x46d`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.MethodBasedRoutingConvention::SelectAction`
- size: `221`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x390`
- `0xd060`
- `0xd080`

## pseudocode

```c

```

## disassembly

```asm
0x390  newobj   instance void <>c__DisplayClass2_0::.ctor()
0x395  stloc.0
0x396  ldloc.0
0x397  ldarg.1
0x398  stfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath <>c__DisplayClass2_0::odataPath
0x39d  ldloc.0
0x39e  ldarg.2
0x39f  stfld    class [System.Web.Http]System.Web.Http.Controllers.HttpControllerContext <>c__DisplayClass2_0::controllerContext
0x3a4  ldloc.0
0x3a5  ldnull
0x3a6  stfld    string <>c__DisplayClass2_0::name
0x3ab  ldloc.0
0x3ac  ldfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath <>c__DisplayClass2_0::odataPath
0x3b1  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment> [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath::get_Segments()
0x3b6  call     T0x2B000002
0x3bb  isinst   [Microsoft.OData.Core]Microsoft.OData.UriParser.EntitySetSegment
0x3c0  stloc.1
0x3c1  ldloc.1
0x3c2  brfalse.s loc_3D5
0x3c4  ldloc.0
0x3c5  ldloc.1
0x3c6  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntitySet [Microsoft.OData.Core]Microsoft.OData.UriParser.EntitySetSegment::get_EntitySet()
0x3cb  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x3d0  stfld    string <>c__DisplayClass2_0::name
0x3d5  ldloc.0
0x3d6  ldfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath <>c__DisplayClass2_0::odataPath
0x3db  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment> [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath::get_Segments()
0x3e0  call     T0x2B000002
0x3e5  isinst   [Microsoft.OData.Core]Microsoft.OData.UriParser.SingletonSegment
0x3ea  stloc.2
0x3eb  ldloc.2
0x3ec  brfalse.s loc_3FF
0x3ee  ldloc.0
0x3ef  ldloc.2
0x3f0  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmSingleton [Microsoft.OData.Core]Microsoft.OData.UriParser.SingletonSegment::get_Singleton()
0x3f5  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x3fa  stfld    string <>c__DisplayClass2_0::name
0x3ff  ldloc.0
0x400  ldfld    string <>c__DisplayClass2_0::name
0x405  brfalse.s loc_46B
0x407  newobj   instance void <>c__DisplayClass2_1::.ctor()
0x40c  stloc.3
0x40d  ldloc.3
0x40e  ldloc.0
0x40f  stfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x414  ldloc.3
0x415  ldarg.3
0x416  ldloc.3
0x417  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x41c  ldfld    class [System.Web.Http]System.Web.Http.Controllers.HttpControllerContext <>c__DisplayClass2_0::controllerContext
0x421  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.Controllers.HttpControllerContext::get_Request()
0x426  callvirt instance class [System.Net.Http]System.Net.Http.HttpMethod [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Method()
0x42b  callvirt instance string [System.Net.Http]System.Net.Http.HttpMethod::get_Method()
0x430  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>> class [System.Core]System.Linq.ILookup`2<string, class [System.Web.Http]System.Web.Http.Controllers.HttpActionDescriptor>::get_Item(void)
0x435  call     T0x2B000003
0x43a  stfld    class [System.Web.Http]System.Web.Http.Controllers.HttpActionDescriptor <>c__DisplayClass2_1::action
0x43f  ldloc.3
0x440  ldfld    class [System.Web.Http]System.Web.Http.Controllers.HttpActionDescriptor <>c__DisplayClass2_1::action
0x445  brfalse.s loc_46B
0x447  ldarg.0
0x448  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.ODataWebApi.MethodBasedRoutingConvention::_logger
0x44d  ldc.i4.4
0x44e  ldloc.3
0x44f  ldftn    instance string <>c__DisplayClass2_1::<SelectAction>b__0()
0x455  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0x45a  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0x45f  ldloc.3
0x460  ldfld    class [System.Web.Http]System.Web.Http.Controllers.HttpActionDescriptor <>c__DisplayClass2_1::action
0x465  callvirt instance string [System.Web.Http]System.Web.Http.Controllers.HttpActionDescriptor::get_ActionName()
0x46a  ret
0x46b  ldnull
0x46c  ret
```
