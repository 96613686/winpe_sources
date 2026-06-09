# Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1::Delete

- ea: `0xbb30`
- end: `0xbc79`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1::Delete`
- size: `329`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0xbb30`

## pseudocode

```c

```

## disassembly

```asm
0xbb30  newobj   instance void class <>c__DisplayClass16_0<var<u1>>::.ctor()
0xbb35  stloc.0
0xbb36  ldloc.0
0xbb37  ldarg.0
0xbb38  stfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class <>c__DisplayClass16_0<var<u1>>::<>4__this
0xbb3d  ldloc.0
0xbb3e  ldarg.1
0xbb3f  stfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath class <>c__DisplayClass16_0<var<u1>>::oDataPath
0xbb44  ldarg.0
0xbb45  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::get_Logger()
0xbb4a  ldc.i4.4
0xbb4b  ldloc.0
0xbb4c  ldftn    instance string class <>c__DisplayClass16_0<var<u1>>::<Delete>b__0()
0xbb52  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xbb57  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0xbb5c  ldarg.0
0xbb5d  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0xbb62  callvirt instance bool [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary::get_IsValid()
0xbb67  brtrue.s loc_BB76
0xbb69  ldarg.0
0xbb6a  ldarg.0
0xbb6b  call     instance string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::GetModelStateValidationErrors()
0xbb70  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::BadRequest(string)
0xbb75  ret
0xbb76  ldloc.0
0xbb77  ldfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath class <>c__DisplayClass16_0<var<u1>>::oDataPath
0xbb7c  callvirt instance string [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath::get_PathTemplate()
0xbb81  ldstr    aEntitysetKey// "~/entityset/key"
0xbb86  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbb8b  brfalse  loc_BC47
0xbb90  newobj   instance void class <>c__DisplayClass16_1<var<u1>>::.ctor()
0xbb95  stloc.1
0xbb96  ldloc.1
0xbb97  ldloc.0
0xbb98  ldfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath class <>c__DisplayClass16_0<var<u1>>::oDataPath
0xbb9d  call     string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>>::ParseEntitySetName(class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath)
0xbba2  stfld    string class <>c__DisplayClass16_1<var<u1>>::entitySetName
0xbba7  ldloc.1
0xbba8  ldloc.0
0xbba9  ldfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath class <>c__DisplayClass16_0<var<u1>>::oDataPath
0xbbae  call     string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>>::ParseKeyIfExists(class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath)
0xbbb3  stfld    string class <>c__DisplayClass16_1<var<u1>>::key
0xbbb8  ldarg.0
0xbbb9  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::get_Logger()
0xbbbe  ldc.i4.4
0xbbbf  ldloc.1
0xbbc0  ldftn    instance string class <>c__DisplayClass16_1<var<u1>>::<Delete>b__2()
0xbbc6  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xbbcb  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0xbbd0  ldarg.0
0xbbd1  ldloc.1
0xbbd2  ldfld    string class <>c__DisplayClass16_1<var<u1>>::key
0xbbd7  callvirt instance bool class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>>::DeleteEntity(string)
0xbbdc  brfalse.s loc_BC15
0xbbde  ldarg.0
0xbbdf  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::get_Logger()
0xbbe4  ldc.i4.4
0xbbe5  ldsfld   class [mscorlib]System.Func`1<string> class <>c<var<u1>>::<>9__16_3
0xbbea  dup
0xbbeb  brtrue.s loc_BC04
0xbbed  pop
0xbbee  ldsfld   class <>c<var<u1>> class <>c<var<u1>>::<>9
0xbbf3  ldftn    instance string class <>c<var<u1>>::<Delete>b__16_3()
0xbbf9  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xbbfe  dup
0xbbff  stsfld   class [mscorlib]System.Func`1<string> class <>c<var<u1>>::<>9__16_3
0xbc04  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0xbc09  ldarg.0
0xbc0a  ldc.i4   0xCC
0xbc0f  call     instance class [System.Web.Http]System.Web.Http.Results.StatusCodeResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::StatusCode(valuetype [System]System.Net.HttpStatusCode)
0xbc14  ret
0xbc15  ldarg.0
0xbc16  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::get_Logger()
0xbc1b  ldc.i4.4
0xbc1c  ldsfld   class [mscorlib]System.Func`1<string> class <>c<var<u1>>::<>9__16_4
0xbc21  dup
0xbc22  brtrue.s loc_BC3B
0xbc24  pop
0xbc25  ldsfld   class <>c<var<u1>> class <>c<var<u1>>::<>9
0xbc2a  ldftn    instance string class <>c<var<u1>>::<Delete>b__16_4()
0xbc30  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xbc35  dup
0xbc36  stsfld   class [mscorlib]System.Func`1<string> class <>c<var<u1>>::<>9__16_4
0xbc3b  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0xbc40  ldarg.0
0xbc41  call     instance class [System.Web.Http]System.Web.Http.Results.NotFoundResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::NotFound()
0xbc46  ret
0xbc47  ldarg.0
0xbc48  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::get_Logger()
0xbc4d  ldc.i4.4
0xbc4e  ldsfld   class [mscorlib]System.Func`1<string> class <>c<var<u1>>::<>9__16_1
0xbc53  dup
0xbc54  brtrue.s loc_BC6D
0xbc56  pop
0xbc57  ldsfld   class <>c<var<u1>> class <>c<var<u1>>::<>9
0xbc5c  ldftn    instance string class <>c<var<u1>>::<Delete>b__16_1()
0xbc62  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xbc67  dup
0xbc68  stsfld   class [mscorlib]System.Func`1<string> class <>c<var<u1>>::<>9__16_1
0xbc6d  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0xbc72  ldarg.0
0xbc73  callvirt instance class [System.Web.Http]System.Web.Http.Results.InternalServerErrorResult [System.Web.Http]System.Web.Http.ApiController::InternalServerError()
0xbc78  ret
```
