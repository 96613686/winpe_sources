# Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1::Get

- ea: `0xbe70`
- end: `0xbfc0`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1::Get`
- size: `336`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xb300`
- `0xbe70`

## pseudocode

```c

```

## disassembly

```asm
0xbe70  newobj   instance void class <>c__DisplayClass9_0<var<u1>>::.ctor()
0xbe75  stloc.0
0xbe76  ldloc.0
0xbe77  ldarg.0
0xbe78  stfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>> class <>c__DisplayClass9_0<var<u1>>::<>4__this
0xbe7d  ldloc.0
0xbe7e  ldarg.1
0xbe7f  stfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath class <>c__DisplayClass9_0<var<u1>>::oDataPath
0xbe84  ldarg.0
0xbe85  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::get_Logger()
0xbe8a  ldc.i4.4
0xbe8b  ldloc.0
0xbe8c  ldftn    instance string class <>c__DisplayClass9_0<var<u1>>::<Get>b__0()
0xbe92  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xbe97  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0xbe9c  ldarg.0
0xbe9d  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0xbea2  callvirt instance bool [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary::get_IsValid()
0xbea7  brtrue.s loc_BEB6
0xbea9  ldarg.0
0xbeaa  ldarg.0
0xbeab  call     instance string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::GetModelStateValidationErrors()
0xbeb0  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::BadRequest(string)
0xbeb5  ret
0xbeb6  ldc.i4.0
0xbeb7  stloc.1
0xbeb8  ldarg.0
0xbeb9  ldloc.0
0xbeba  ldfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath class <>c__DisplayClass9_0<var<u1>>::oDataPath
0xbebf  ldloca.s 1
0xbec1  callvirt instance object class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::GetRoot(class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath, int32&)
0xbec6  stloc.2
0xbec7  ldloc.2
0xbec8  brtrue.s loc_BEFC
0xbeca  ldarg.0
0xbecb  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::get_Logger()
0xbed0  ldc.i4.4
0xbed1  ldsfld   class [mscorlib]System.Func`1<string> class <>c<var<u1>>::<>9__9_1
0xbed6  dup
0xbed7  brtrue.s loc_BEF0
0xbed9  pop
0xbeda  ldsfld   class <>c<var<u1>> class <>c<var<u1>>::<>9
0xbedf  ldftn    instance string class <>c<var<u1>>::<Get>b__9_1()
0xbee5  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xbeea  dup
0xbeeb  stsfld   class [mscorlib]System.Func`1<string> class <>c<var<u1>>::<>9__9_1
0xbef0  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0xbef5  ldarg.0
0xbef6  call     instance class [System.Web.Http]System.Web.Http.Results.NotFoundResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::NotFound()
0xbefb  ret
0xbefc  ldloc.0
0xbefd  ldfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath class <>c__DisplayClass9_0<var<u1>>::oDataPath
0xbf02  callvirt instance string [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath::get_PathTemplate()
0xbf07  ldc.i4.2
0xbf08  newarr   [mscorlib]System.String
0xbf0d  dup
0xbf0e  ldc.i4.0
0xbf0f  ldstr    asc_13216// "~/"
0xbf14  stelem.ref
0xbf15  dup
0xbf16  ldc.i4.1
0xbf17  ldstr    asc_10432// "/"
0xbf1c  stelem.ref
0xbf1d  ldc.i4.1
0xbf1e  callvirt instance string[] [mscorlib]System.String::Split(string[], valuetype [mscorlib]System.StringSplitOptions)
0xbf23  stloc.3
0xbf24  br.s     loc_BFA2
0xbf26  newobj   instance void class <>c__DisplayClass9_1<var<u1>>::.ctor()
0xbf2b  stloc.s  4
0xbf2d  ldloc.s  4
0xbf2f  ldloc.0
0xbf30  ldfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath class <>c__DisplayClass9_0<var<u1>>::oDataPath
0xbf35  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment> [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath::get_Segments()
0xbf3a  ldloc.1
0xbf3b  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment>::get_Item(!!T0)
0xbf40  stfld    class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment class <>c__DisplayClass9_1<var<u1>>::segment
0xbf45  ldloc.3
0xbf46  ldloc.1
0xbf47  ldelem.ref
0xbf48  stloc.s  5
0xbf4a  ldarg.0
0xbf4b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.SegmentHandlers.ISegmentHandler> class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::_handlers
0xbf50  ldloc.s  5
0xbf52  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.SegmentHandlers.ISegmentHandler>::ContainsKey(var<u1>)
0xbf57  brtrue.s loc_BF79
0xbf59  ldarg.0
0xbf5a  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::get_Logger()
0xbf5f  ldc.i4.4
0xbf60  ldloc.s  4
0xbf62  ldftn    instance string class <>c__DisplayClass9_1<var<u1>>::<Get>b__2()
0xbf68  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xbf6d  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0xbf72  ldarg.0
0xbf73  call     instance class [System.Web.Http]System.Web.Http.Results.NotFoundResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::NotFound()
0xbf78  ret
0xbf79  ldarg.0
0xbf7a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.SegmentHandlers.ISegmentHandler> class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::_handlers
0xbf7f  ldloc.s  5
0xbf81  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.SegmentHandlers.ISegmentHandler>::get_Item(void)
0xbf86  ldloc.2
0xbf87  ldloc.s  4
0xbf89  ldfld    class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment class <>c__DisplayClass9_1<var<u1>>::segment
0xbf8e  callvirt instance object Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.SegmentHandlers.ISegmentHandler::Handle(object source, class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment segment)
0xbf93  stloc.2
0xbf94  ldloc.2
0xbf95  brtrue.s loc_BF9E
0xbf97  ldarg.0
0xbf98  call     instance class [System.Web.Http]System.Web.Http.Results.NotFoundResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::NotFound()
0xbf9d  ret
0xbf9e  ldloc.1
0xbf9f  ldc.i4.1
0xbfa0  add
0xbfa1  stloc.1
0xbfa2  ldloc.1
0xbfa3  ldloc.0
0xbfa4  ldfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath class <>c__DisplayClass9_0<var<u1>>::oDataPath
0xbfa9  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment> [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath::get_Segments()
0xbfae  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment>::get_Count()
0xbfb3  blt      loc_BF26
0xbfb8  ldarg.0
0xbfb9  ldloc.2
0xbfba  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::CreateOk(object)
0xbfbf  ret
```
