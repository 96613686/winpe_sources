# Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1::Put

- ea: `0xb830`
- end: `0xb9ad`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1::Put`
- size: `381`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xb830`

## pseudocode

```c

```

## disassembly

```asm
0xb830  newobj   instance void class <>c__DisplayClass14_0<var<u1>>::.ctor()
0xb835  stloc.0
0xb836  ldloc.0
0xb837  ldarg.0
0xb838  stfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class <>c__DisplayClass14_0<var<u1>>::<>4__this
0xb83d  ldloc.0
0xb83e  ldarg.1
0xb83f  stfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath class <>c__DisplayClass14_0<var<u1>>::oDataPath
0xb844  ldarg.0
0xb845  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::get_Logger()
0xb84a  ldc.i4.4
0xb84b  ldloc.0
0xb84c  ldftn    instance string class <>c__DisplayClass14_0<var<u1>>::<Put>b__0()
0xb852  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xb857  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0xb85c  ldarg.0
0xb85d  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0xb862  callvirt instance bool [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary::get_IsValid()
0xb867  brtrue.s loc_B876
0xb869  ldarg.0
0xb86a  ldarg.0
0xb86b  call     instance string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::GetModelStateValidationErrors()
0xb870  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::BadRequest(string)
0xb875  ret
0xb876  ldloc.0
0xb877  ldfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath class <>c__DisplayClass14_0<var<u1>>::oDataPath
0xb87c  callvirt instance string [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath::get_PathTemplate()
0xb881  ldstr    aEntitysetKey// "~/entityset/key"
0xb886  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb88b  brfalse  loc_B97B
0xb890  newobj   instance void class <>c__DisplayClass14_1<var<u1>>::.ctor()
0xb895  stloc.1
0xb896  ldloc.1
0xb897  ldloc.0
0xb898  ldfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath class <>c__DisplayClass14_0<var<u1>>::oDataPath
0xb89d  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment> [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath::get_Segments()
0xb8a2  ldc.i4.0
0xb8a3  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment>::get_Item(!!T0)
0xb8a8  castclass [Microsoft.OData.Core]Microsoft.OData.UriParser.EntitySetSegment
0xb8ad  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntitySet [Microsoft.OData.Core]Microsoft.OData.UriParser.EntitySetSegment::get_EntitySet()
0xb8b2  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0xb8b7  stfld    string class <>c__DisplayClass14_1<var<u1>>::entitySetName
0xb8bc  ldloc.1
0xb8bd  ldloc.0
0xb8be  ldfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath class <>c__DisplayClass14_0<var<u1>>::oDataPath
0xb8c3  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment> [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath::get_Segments()
0xb8c8  ldc.i4.1
0xb8c9  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment>::get_Item(!!T0)
0xb8ce  castclass [Microsoft.OData.Core]Microsoft.OData.UriParser.KeySegment
0xb8d3  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>> [Microsoft.OData.Core]Microsoft.OData.UriParser.KeySegment::get_Keys()
0xb8d8  call     T0x2B0000F0
0xb8dd  stloc.2
0xb8de  ldloca.s 2
0xb8e0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0xb8e5  callvirt instance string [mscorlib]System.Object::ToString()
0xb8ea  stfld    string class <>c__DisplayClass14_1<var<u1>>::key
0xb8ef  ldarg.0
0xb8f0  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::get_Logger()
0xb8f5  ldc.i4.4
0xb8f6  ldloc.1
0xb8f7  ldftn    instance string class <>c__DisplayClass14_1<var<u1>>::<Put>b__2()
0xb8fd  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xb902  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0xb907  ldarg.0
0xb908  ldloc.1
0xb909  ldfld    string class <>c__DisplayClass14_1<var<u1>>::key
0xb90e  ldarg.2
0xb90f  callvirt instance bool class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>>::PutEntity(string, var<u1>)
0xb914  brfalse.s loc_B949
0xb916  ldarg.0
0xb917  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::get_Logger()
0xb91c  ldc.i4.4
0xb91d  ldsfld   class [mscorlib]System.Func`1<string> class <>c<var<u1>>::<>9__14_3
0xb922  dup
0xb923  brtrue.s loc_B93C
0xb925  pop
0xb926  ldsfld   class <>c<var<u1>> class <>c<var<u1>>::<>9
0xb92b  ldftn    instance string class <>c<var<u1>>::<Put>b__14_3()
0xb931  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xb936  dup
0xb937  stsfld   class [mscorlib]System.Func`1<string> class <>c<var<u1>>::<>9__14_3
0xb93c  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0xb941  ldarg.0
0xb942  ldarg.2
0xb943  callvirt T0x2B000042
0xb948  ret
0xb949  ldarg.0
0xb94a  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::get_Logger()
0xb94f  ldc.i4.4
0xb950  ldsfld   class [mscorlib]System.Func`1<string> class <>c<var<u1>>::<>9__14_4
0xb955  dup
0xb956  brtrue.s loc_B96F
0xb958  pop
0xb959  ldsfld   class <>c<var<u1>> class <>c<var<u1>>::<>9
0xb95e  ldftn    instance string class <>c<var<u1>>::<Put>b__14_4()
0xb964  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xb969  dup
0xb96a  stsfld   class [mscorlib]System.Func`1<string> class <>c<var<u1>>::<>9__14_4
0xb96f  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0xb974  ldarg.0
0xb975  call     instance class [System.Web.Http]System.Web.Http.Results.NotFoundResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::NotFound()
0xb97a  ret
0xb97b  ldarg.0
0xb97c  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::get_Logger()
0xb981  ldc.i4.4
0xb982  ldsfld   class [mscorlib]System.Func`1<string> class <>c<var<u1>>::<>9__14_1
0xb987  dup
0xb988  brtrue.s loc_B9A1
0xb98a  pop
0xb98b  ldsfld   class <>c<var<u1>> class <>c<var<u1>>::<>9
0xb990  ldftn    instance string class <>c<var<u1>>::<Put>b__14_1()
0xb996  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xb99b  dup
0xb99c  stsfld   class [mscorlib]System.Func`1<string> class <>c<var<u1>>::<>9__14_1
0xb9a1  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0xb9a6  ldarg.0
0xb9a7  callvirt instance class [System.Web.Http]System.Web.Http.Results.InternalServerErrorResult [System.Web.Http]System.Web.Http.ApiController::InternalServerError()
0xb9ac  ret
```
