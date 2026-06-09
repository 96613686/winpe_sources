# Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1::Post

- ea: `0xb770`
- end: `0xb82e`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1::Post`
- size: `190`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xb770`

## pseudocode

```c

```

## disassembly

```asm
0xb770  newobj   instance void class <>c__DisplayClass13_0<var<u1>>::.ctor()
0xb775  stloc.0
0xb776  ldloc.0
0xb777  ldarg.0
0xb778  stfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class <>c__DisplayClass13_0<var<u1>>::<>4__this
0xb77d  ldloc.0
0xb77e  ldarg.1
0xb77f  stfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath class <>c__DisplayClass13_0<var<u1>>::oDataPath
0xb784  ldarg.0
0xb785  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::get_Logger()
0xb78a  ldc.i4.4
0xb78b  ldloc.0
0xb78c  ldftn    instance string class <>c__DisplayClass13_0<var<u1>>::<Post>b__0()
0xb792  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xb797  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0xb79c  ldarg.0
0xb79d  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0xb7a2  callvirt instance bool [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary::get_IsValid()
0xb7a7  brfalse.s loc_B7B1
0xb7a9  ldarg.2
0xb7aa  box      var<u1>
0xb7af  brtrue.s loc_B7BE
0xb7b1  ldarg.0
0xb7b2  ldarg.0
0xb7b3  call     instance string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::GetModelStateValidationErrors()
0xb7b8  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::BadRequest(string)
0xb7bd  ret
0xb7be  ldarg.0
0xb7bf  ldarg.2
0xb7c0  ldloca.s 1
0xb7c2  callvirt instance bool class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>>::AddEntity(var<u1>, !!T0)
0xb7c7  brfalse.s loc_B7FC
0xb7c9  ldarg.0
0xb7ca  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::get_Logger()
0xb7cf  ldc.i4.4
0xb7d0  ldsfld   class [mscorlib]System.Func`1<string> class <>c<var<u1>>::<>9__13_1
0xb7d5  dup
0xb7d6  brtrue.s loc_B7EF
0xb7d8  pop
0xb7d9  ldsfld   class <>c<var<u1>> class <>c<var<u1>>::<>9
0xb7de  ldftn    instance string class <>c<var<u1>>::<Post>b__13_1()
0xb7e4  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xb7e9  dup
0xb7ea  stsfld   class [mscorlib]System.Func`1<string> class <>c<var<u1>>::<>9__13_1
0xb7ef  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0xb7f4  ldarg.0
0xb7f5  ldloc.1
0xb7f6  callvirt T0x2B000041
0xb7fb  ret
0xb7fc  ldarg.0
0xb7fd  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::get_Logger()
0xb802  ldc.i4.4
0xb803  ldsfld   class [mscorlib]System.Func`1<string> class <>c<var<u1>>::<>9__13_2
0xb808  dup
0xb809  brtrue.s loc_B822
0xb80b  pop
0xb80c  ldsfld   class <>c<var<u1>> class <>c<var<u1>>::<>9
0xb811  ldftn    instance string class <>c<var<u1>>::<Post>b__13_2()
0xb817  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xb81c  dup
0xb81d  stsfld   class [mscorlib]System.Func`1<string> class <>c<var<u1>>::<>9__13_2
0xb822  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0xb827  ldarg.0
0xb828  callvirt instance class [System.Web.Http]System.Web.Http.Results.InternalServerErrorResult [System.Web.Http]System.Web.Http.ApiController::InternalServerError()
0xb82d  ret
```
