# Microsoft.ReportingServices.Portal.ODataWebApi.UnboundFunctionRoutingConvention::SelectAction

- ea: `0x4f0`
- end: `0x614`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.UnboundFunctionRoutingConvention::SelectAction`
- size: `292`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x4f0`
- `0xd150`
- `0xd170`
- `0xd1f0`

## pseudocode

```c

```

## disassembly

```asm
0x4f0  newobj   instance void <>c__DisplayClass4_0::.ctor()
0x4f5  stloc.0
0x4f6  ldloc.0
0x4f7  ldarg.1
0x4f8  stfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath <>c__DisplayClass4_0::odataPath
0x4fd  ldloc.0
0x4fe  ldarg.2
0x4ff  stfld    class [System.Web.Http]System.Web.Http.Controllers.HttpControllerContext <>c__DisplayClass4_0::controllerContext
0x504  ldloc.0
0x505  ldfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath <>c__DisplayClass4_0::odataPath
0x50a  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment> [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath::get_Segments()
0x50f  call     T0x2B000002
0x514  isinst   [Microsoft.OData.Core]Microsoft.OData.UriParser.OperationImportSegment
0x519  stloc.1
0x51a  ldloc.1
0x51b  brfalse  loc_612
0x520  newobj   instance void <>c__DisplayClass4_1::.ctor()
0x525  stloc.2
0x526  ldloc.2
0x527  ldloc.0
0x528  stfld    class <>c__DisplayClass4_0 <>c__DisplayClass4_1::CS$<>8__locals1
0x52d  ldloc.2
0x52e  ldarg.3
0x52f  ldloc.1
0x530  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmOperationImport> [Microsoft.OData.Core]Microsoft.OData.UriParser.OperationImportSegment::get_OperationImports()
0x535  call     T0x2B000004
0x53a  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x53f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>> class [System.Core]System.Linq.ILookup`2<string, class [System.Web.Http]System.Web.Http.Controllers.HttpActionDescriptor>::get_Item(void)
0x544  call     T0x2B000003
0x549  stfld    class [System.Web.Http]System.Web.Http.Controllers.HttpActionDescriptor <>c__DisplayClass4_1::action
0x54e  ldloc.2
0x54f  ldfld    class [System.Web.Http]System.Web.Http.Controllers.HttpActionDescriptor <>c__DisplayClass4_1::action
0x554  brfalse  loc_612
0x559  ldloc.2
0x55a  ldfld    class [System.Web.Http]System.Web.Http.Controllers.HttpActionDescriptor <>c__DisplayClass4_1::action
0x55f  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Web.Http]System.Web.Http.Controllers.HttpParameterDescriptor> [System.Web.Http]System.Web.Http.Controllers.HttpActionDescriptor::GetParameters()
0x564  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Web.Http]System.Web.Http.Controllers.HttpParameterDescriptor>::GetEnumerator()
0x569  stloc.3
0x56a  br.s     loc_5DA
0x56c  newobj   instance void <>c__DisplayClass4_2::.ctor()
0x571  stloc.s  4
0x573  ldloc.s  4
0x575  ldloc.3
0x576  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Web.Http]System.Web.Http.Controllers.HttpParameterDescriptor>::get_Current()
0x57b  stfld    class [System.Web.Http]System.Web.Http.Controllers.HttpParameterDescriptor <>c__DisplayClass4_2::parameter
0x580  ldloc.1
0x581  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.OperationSegmentParameter> [Microsoft.OData.Core]Microsoft.OData.UriParser.OperationImportSegment::get_Parameters()
0x586  ldloc.s  4
0x588  ldftn    instance bool <>c__DisplayClass4_2::<SelectAction>b__1(class [Microsoft.OData.Core]Microsoft.OData.UriParser.OperationSegmentParameter p)
0x58e  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.OData.Core]Microsoft.OData.UriParser.OperationSegmentParameter, bool>::.ctor(object, native int)
0x593  call     T0x2B000005
0x598  callvirt instance object [Microsoft.OData.Core]Microsoft.OData.UriParser.OperationSegmentParameter::get_Value()
0x59d  isinst   [Microsoft.OData.Core]Microsoft.OData.UriParser.ConstantNode
0x5a2  stloc.s  5
0x5a4  ldloc.s  5
0x5a6  callvirt instance object [Microsoft.OData.Core]Microsoft.OData.UriParser.ConstantNode::get_Value()
0x5ab  brfalse.s loc_5DA
0x5ad  ldloc.2
0x5ae  ldfld    class <>c__DisplayClass4_0 <>c__DisplayClass4_1::CS$<>8__locals1
0x5b3  ldfld    class [System.Web.Http]System.Web.Http.Controllers.HttpControllerContext <>c__DisplayClass4_0::controllerContext
0x5b8  callvirt instance class [System.Web.Http]System.Web.Http.Routing.IHttpRouteData [System.Web.Http]System.Web.Http.Controllers.HttpControllerContext::get_RouteData()
0x5bd  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [System.Web.Http]System.Web.Http.Routing.IHttpRouteData::get_Values()
0x5c2  ldloc.s  4
0x5c4  ldfld    class [System.Web.Http]System.Web.Http.Controllers.HttpParameterDescriptor <>c__DisplayClass4_2::parameter
0x5c9  callvirt instance string [System.Web.Http]System.Web.Http.Controllers.HttpParameterDescriptor::get_ParameterName()
0x5ce  ldloc.s  5
0x5d0  callvirt instance object [Microsoft.OData.Core]Microsoft.OData.UriParser.ConstantNode::get_Value()
0x5d5  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x5da  ldloc.3
0x5db  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5e0  brtrue.s loc_56C
0x5e2  leave.s  loc_5EE
0x5e4  ldloc.3
0x5e5  brfalse.s loc_5ED
0x5e7  ldloc.3
0x5e8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5ed  endfinally
0x5ee  ldarg.0
0x5ef  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.ODataWebApi.UnboundFunctionRoutingConvention::_logger
0x5f4  ldc.i4.4
0x5f5  ldloc.2
0x5f6  ldftn    instance string <>c__DisplayClass4_1::<SelectAction>b__0()
0x5fc  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0x601  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0x606  ldloc.2
0x607  ldfld    class [System.Web.Http]System.Web.Http.Controllers.HttpActionDescriptor <>c__DisplayClass4_1::action
0x60c  callvirt instance string [System.Web.Http]System.Web.Http.Controllers.HttpActionDescriptor::get_ActionName()
0x611  ret
0x612  ldnull
0x613  ret
```
