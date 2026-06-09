# <PostDataModelParameters>d__33::MoveNext

- ea: `0xdf90`
- end: `0xe1d7`
- name: `<PostDataModelParameters>d__33::MoveNext`
- size: `583`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x3850`
- `0x3be0`
- `0x3c90`
- `0xcec0`
- `0xdf90`

## string_xrefs

- `0xe06a`: `Only report created with version October/2020 or later and with enhanced metadata enabled can have parameters updated.`
- `0xe0d9`: `Unable to aggregate the updates for parameters: {0} due to {1}`

## pseudocode

```c

```

## disassembly

```asm
0xdf90  ldarg.0
0xdf91  ldfld    int32 <PostDataModelParameters>d__33::<>1__state
0xdf96  stloc.0
0xdf97  ldarg.0
0xdf98  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PowerBIReportsController <PostDataModelParameters>d__33::<>4__this
0xdf9d  stloc.1
0xdf9e  ldloc.0
0xdf9f  brfalse  loc_E030
0xdfa4  ldarg.0
0xdfa5  ldloc.1
0xdfa6  ldarg.0
0xdfa7  ldfld    string <PostDataModelParameters>d__33::Id
0xdfac  ldnull
0xdfad  callvirt instance var<u1> class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::GetEntity(!!T0, string)
0xdfb2  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport <PostDataModelParameters>d__33::<item>5__2
0xdfb7  ldarg.0
0xdfb8  ldarg.0
0xdfb9  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport <PostDataModelParameters>d__33::<item>5__2
0xdfbe  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelParameter> [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport::get_DataModelParameters()
0xdfc3  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelParameter, string> <>c::<>9__33_0
0xdfc8  dup
0xdfc9  brtrue.s loc_DFE2
0xdfcb  pop
0xdfcc  ldsfld   class <>c <>c::<>9
0xdfd1  ldftn    instance string <>c::<PostDataModelParameters>b__33_0(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelParameter p)
0xdfd7  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelParameter, string>::.ctor(object, native int)
0xdfdc  dup
0xdfdd  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelParameter, string> <>c::<>9__33_0
0xdfe2  call     T0x2B000100
0xdfe7  stfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelParameter> <PostDataModelParameters>d__33::<currentParams>5__3
0xdfec  ldloc.1
0xdfed  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0xdff2  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Content()
0xdff7  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<string> [System.Net.Http]System.Net.Http.HttpContent::ReadAsStringAsync()
0xdffc  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::GetAwaiter()
0xe001  stloc.s  6
0xe003  ldloca.s 6
0xe005  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::get_IsCompleted()
0xe00a  brtrue.s loc_E04D
0xe00c  ldarg.0
0xe00d  ldc.i4.0
0xe00e  dup
0xe00f  stloc.0
0xe010  stfld    int32 <PostDataModelParameters>d__33::<>1__state
0xe015  ldarg.0
0xe016  ldloc.s  6
0xe018  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <PostDataModelParameters>d__33::<>u__1
0xe01d  ldarg.0
0xe01e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <PostDataModelParameters>d__33::<>t__builder
0xe023  ldloca.s 6
0xe025  ldarg.0
0xe026  call     T0x2B000101
0xe02b  leave    loc_E1D6
0xe030  ldarg.0
0xe031  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <PostDataModelParameters>d__33::<>u__1
0xe036  stloc.s  6
0xe038  ldarg.0
0xe039  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <PostDataModelParameters>d__33::<>u__1
0xe03e  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0xe044  ldarg.0
0xe045  ldc.i4.m1
0xe046  dup
0xe047  stloc.0
0xe048  stfld    int32 <PostDataModelParameters>d__33::<>1__state
0xe04d  ldloca.s 6
0xe04f  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::GetResult()
0xe054  stloc.3
0xe055  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelParameter>::.ctor()
0xe05a  stloc.s  4
0xe05c  ldloc.1
0xe05d  ldarg.0
0xe05e  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport <PostDataModelParameters>d__33::<item>5__2
0xe063  call     instance bool Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PowerBIReportsController::IsModelV1(class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport report)
0xe068  brfalse.s loc_E08D
0xe06a  ldstr    aOnlyReportCrea// "Only report created with version Octobe"...
0xe06f  stloc.s  7
0xe071  ldloc.1
0xe072  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::get_Logger()
0xe077  ldc.i4.1
0xe078  ldloc.s  7
0xe07a  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xe07f  ldloc.1
0xe080  ldloc.s  7
0xe082  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::BadRequest(string)
0xe087  stloc.2
0xe088  leave    loc_E1C2
0xe08d  nop
0xe08e  ldloc.3
0xe08f  ldloc.s  4
0xe091  call     void [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::PopulateObject(string, object)
0xe096  leave.s  loc_E0C6
0xe098  stloc.s  8
0xe09a  ldstr    aUnableToParseE// "Unable to parse exceptions : {0} due to"...
0xe09f  ldloc.s  4
0xe0a1  ldloc.s  8
0xe0a3  call     string [mscorlib]System.String::Format(string, object, object)
0xe0a8  stloc.s  9
0xe0aa  ldloc.1
0xe0ab  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::get_Logger()
0xe0b0  ldc.i4.1
0xe0b1  ldloc.s  9
0xe0b3  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xe0b8  ldloc.1
0xe0b9  ldloc.s  9
0xe0bb  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::BadRequest(string)
0xe0c0  stloc.2
0xe0c1  leave    loc_E1C2
0xe0c6  nop
0xe0c7  ldloc.1
0xe0c8  ldarg.0
0xe0c9  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelParameter> <PostDataModelParameters>d__33::<currentParams>5__3
0xe0ce  ldloc.s  4
0xe0d0  call     instance void Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PowerBIReportsController::UpdateParametersMapWithOnlyExistingParameters(class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelParameter> currentParams, class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelParameter> updatedParams)
0xe0d5  leave.s  loc_E105
0xe0d7  stloc.s  0xA
0xe0d9  ldstr    aUnableToAggreg// "Unable to aggregate the updates for par"...
0xe0de  ldloc.s  4
0xe0e0  ldloc.s  0xA
0xe0e2  call     string [mscorlib]System.String::Format(string, object, object)
0xe0e7  stloc.s  0xB
0xe0e9  ldloc.1
0xe0ea  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::get_Logger()
0xe0ef  ldc.i4.1
0xe0f0  ldloc.s  0xB
0xe0f2  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xe0f7  ldloc.1
0xe0f8  ldloc.s  0xB
0xe0fa  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::BadRequest(string)
0xe0ff  stloc.2
0xe100  leave    loc_E1C2
0xe105  ldarg.0
0xe106  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelParameter> <PostDataModelParameters>d__33::<currentParams>5__3
0xe10b  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelParameter>::get_Values()
0xe110  call     T0x2B0000EB
0xe115  call     string [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::SerializeObject(object)
0xe11a  stloc.s  5
0xe11c  ldloc.1
0xe11d  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::get_CatalogRepository()
0xe122  ldloc.1
0xe123  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0xe128  ldarg.0
0xe129  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport <PostDataModelParameters>d__33::<item>5__2
0xe12e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Id()
0xe133  ldloc.s  5
0xe135  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::SetDataModelParameters(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid, string)
0xe13a  ldloc.1
0xe13b  call     instance class Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PowerBIReportsController::get_PowerBIReportsControllerHelper()
0xe140  ldarg.0
0xe141  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport <PostDataModelParameters>d__33::<item>5__2
0xe146  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Id()
0xe14b  ldloc.s  4
0xe14d  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::UpdateDataModelParametersInAS(valuetype [mscorlib]System.Guid id, class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelParameter> parameters)
0xe152  stloc.s  0xC
0xe154  ldloc.1
0xe155  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::get_CatalogRepository()
0xe15a  ldloc.1
0xe15b  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0xe160  ldarg.0
0xe161  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport <PostDataModelParameters>d__33::<item>5__2
0xe166  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Id()
0xe16b  ldloc.s  0xC
0xe16d  ldc.i4.1
0xe16e  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::SetDataModelDataSourcesTrusted(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>, bool)
0xe173  leave.s  loc_E1A0
0xe175  stloc.s  0xD
0xe177  ldstr    aUnableToApplyN// "Unable to apply new parameters: {0} to "...
0xe17c  ldloc.s  4
0xe17e  ldloc.s  0xD
0xe180  call     string [mscorlib]System.String::Format(string, object, object)
0xe185  stloc.s  0xE
0xe187  ldloc.1
0xe188  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::get_Logger()
0xe18d  ldc.i4.1
0xe18e  ldloc.s  0xE
0xe190  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xe195  ldloc.1
0xe196  ldloc.s  0xE
0xe198  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::BadRequest(string)
0xe19d  stloc.2
0xe19e  leave.s  loc_E1C2
0xe1a0  ldloc.1
0xe1a1  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::Ok()
0xe1a6  stloc.2
0xe1a7  leave.s  loc_E1C2
0xe1a9  stloc.s  0xF
0xe1ab  ldarg.0
0xe1ac  ldc.i4.s 0xFE
0xe1ae  stfld    int32 <PostDataModelParameters>d__33::<>1__state
0xe1b3  ldarg.0
0xe1b4  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <PostDataModelParameters>d__33::<>t__builder
0xe1b9  ldloc.s  0xF
0xe1bb  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetException(class [mscorlib]System.Exception)
0xe1c0  leave.s  loc_E1D6
0xe1c2  ldarg.0
0xe1c3  ldc.i4.s 0xFE
0xe1c5  stfld    int32 <PostDataModelParameters>d__33::<>1__state
0xe1ca  ldarg.0
0xe1cb  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <PostDataModelParameters>d__33::<>t__builder
0xe1d0  ldloc.2
0xe1d1  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetResult(var<u1>)
0xe1d6  ret
```
