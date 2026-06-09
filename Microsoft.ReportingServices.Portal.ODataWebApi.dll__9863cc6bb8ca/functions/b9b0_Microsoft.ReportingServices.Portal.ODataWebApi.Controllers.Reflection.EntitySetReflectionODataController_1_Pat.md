# Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1::Patch

- ea: `0xb9b0`
- end: `0xbb22`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1::Patch`
- size: `370`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0xb9b0`

## pseudocode

```c

```

## disassembly

```asm
0xb9b0  newobj   instance void class <>c__DisplayClass15_0<var<u1>>::.ctor()
0xb9b5  stloc.0
0xb9b6  ldloc.0
0xb9b7  ldarg.0
0xb9b8  stfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class <>c__DisplayClass15_0<var<u1>>::<>4__this
0xb9bd  ldloc.0
0xb9be  ldarg.1
0xb9bf  stfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath class <>c__DisplayClass15_0<var<u1>>::oDataPath
0xb9c4  ldarg.0
0xb9c5  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::get_Logger()
0xb9ca  ldc.i4.4
0xb9cb  ldloc.0
0xb9cc  ldftn    instance string class <>c__DisplayClass15_0<var<u1>>::<Patch>b__0()
0xb9d2  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xb9d7  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0xb9dc  ldarg.0
0xb9dd  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0xb9e2  callvirt instance bool [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary::get_IsValid()
0xb9e7  brtrue.s loc_B9F6
0xb9e9  ldarg.0
0xb9ea  ldarg.0
0xb9eb  call     instance string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::GetModelStateValidationErrors()
0xb9f0  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::BadRequest(string)
0xb9f5  ret
0xb9f6  ldloc.0
0xb9f7  ldfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath class <>c__DisplayClass15_0<var<u1>>::oDataPath
0xb9fc  callvirt instance string [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath::get_PathTemplate()
0xba01  ldstr    aEntitysetKey// "~/entityset/key"
0xba06  call     bool [mscorlib]System.String::op_Equality(string, string)
0xba0b  brfalse  loc_BAF0
0xba10  newobj   instance void class <>c__DisplayClass15_1<var<u1>>::.ctor()
0xba15  stloc.1
0xba16  ldloc.1
0xba17  ldloc.0
0xba18  ldfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath class <>c__DisplayClass15_0<var<u1>>::oDataPath
0xba1d  call     string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>>::ParseEntitySetName(class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath)
0xba22  stfld    string class <>c__DisplayClass15_1<var<u1>>::entitySetName
0xba27  ldloc.1
0xba28  ldloc.0
0xba29  ldfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath class <>c__DisplayClass15_0<var<u1>>::oDataPath
0xba2e  call     string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>>::ParseKeyIfExists(class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath)
0xba33  stfld    string class <>c__DisplayClass15_1<var<u1>>::key
0xba38  ldloc.0
0xba39  ldfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath class <>c__DisplayClass15_0<var<u1>>::oDataPath
0xba3e  call     string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>>::ParseCastIfExists(class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath)
0xba43  stloc.2
0xba44  ldarg.0
0xba45  ldloc.1
0xba46  ldfld    string class <>c__DisplayClass15_1<var<u1>>::key
0xba4b  ldloc.2
0xba4c  callvirt instance var<u1> class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>>::GetEntity(!!T0, string)
0xba51  stloc.3
0xba52  ldarg.2
0xba53  ldloc.3
0xba54  callvirt instance void class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Delta`1<var<u1>>::Patch(var<u1>)
0xba59  ldarg.0
0xba5a  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::get_Logger()
0xba5f  ldc.i4.4
0xba60  ldloc.1
0xba61  ldftn    instance string class <>c__DisplayClass15_1<var<u1>>::<Patch>b__2()
0xba67  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xba6c  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0xba71  ldarg.0
0xba72  ldloc.1
0xba73  ldfld    string class <>c__DisplayClass15_1<var<u1>>::key
0xba78  ldloc.3
0xba79  ldarg.2
0xba7a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Delta::GetChangedPropertyNames()
0xba7f  call     T0x2B00009A
0xba84  callvirt instance bool class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>>::PatchEntity(string, var<u1>, !!T0)
0xba89  brfalse.s loc_BABE
0xba8b  ldarg.0
0xba8c  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::get_Logger()
0xba91  ldc.i4.4
0xba92  ldsfld   class [mscorlib]System.Func`1<string> class <>c<var<u1>>::<>9__15_3
0xba97  dup
0xba98  brtrue.s loc_BAB1
0xba9a  pop
0xba9b  ldsfld   class <>c<var<u1>> class <>c<var<u1>>::<>9
0xbaa0  ldftn    instance string class <>c<var<u1>>::<Patch>b__15_3()
0xbaa6  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xbaab  dup
0xbaac  stsfld   class [mscorlib]System.Func`1<string> class <>c<var<u1>>::<>9__15_3
0xbab1  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0xbab6  ldarg.0
0xbab7  ldloc.3
0xbab8  callvirt T0x2B000042
0xbabd  ret
0xbabe  ldarg.0
0xbabf  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::get_Logger()
0xbac4  ldc.i4.4
0xbac5  ldsfld   class [mscorlib]System.Func`1<string> class <>c<var<u1>>::<>9__15_4
0xbaca  dup
0xbacb  brtrue.s loc_BAE4
0xbacd  pop
0xbace  ldsfld   class <>c<var<u1>> class <>c<var<u1>>::<>9
0xbad3  ldftn    instance string class <>c<var<u1>>::<Patch>b__15_4()
0xbad9  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xbade  dup
0xbadf  stsfld   class [mscorlib]System.Func`1<string> class <>c<var<u1>>::<>9__15_4
0xbae4  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0xbae9  ldarg.0
0xbaea  call     instance class [System.Web.Http]System.Web.Http.Results.NotFoundResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::NotFound()
0xbaef  ret
0xbaf0  ldarg.0
0xbaf1  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::get_Logger()
0xbaf6  ldc.i4.4
0xbaf7  ldsfld   class [mscorlib]System.Func`1<string> class <>c<var<u1>>::<>9__15_1
0xbafc  dup
0xbafd  brtrue.s loc_BB16
0xbaff  pop
0xbb00  ldsfld   class <>c<var<u1>> class <>c<var<u1>>::<>9
0xbb05  ldftn    instance string class <>c<var<u1>>::<Patch>b__15_1()
0xbb0b  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xbb10  dup
0xbb11  stsfld   class [mscorlib]System.Func`1<string> class <>c<var<u1>>::<>9__15_1
0xbb16  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0xbb1b  ldarg.0
0xbb1c  callvirt instance class [System.Web.Http]System.Web.Http.Results.InternalServerErrorResult [System.Web.Http]System.Web.Http.ApiController::InternalServerError()
0xbb21  ret
```
