# <PatchOnDataModelDataSourcesCollectionAsync>d__53::MoveNext

- ea: `0xd7a0`
- end: `0xd932`
- name: `<PatchOnDataModelDataSourcesCollectionAsync>d__53::MoveNext`
- size: `402`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0xd7a0`

## pseudocode

```c

```

## disassembly

```asm
0xd7a0  ldarg.0
0xd7a1  ldfld    int32 valuetype <PatchOnDataModelDataSourcesCollectionAsync>d__53<var<u1>>::<>1__state
0xd7a6  stloc.0
0xd7a7  ldarg.0
0xd7a8  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<var<u1>> valuetype <PatchOnDataModelDataSourcesCollectionAsync>d__53<var<u1>>::<>4__this
0xd7ad  stloc.1
0xd7ae  ldloc.0
0xd7af  brfalse  loc_D865
0xd7b4  ldloc.1
0xd7b5  ldarg.0
0xd7b6  ldfld    string valuetype <PatchOnDataModelDataSourcesCollectionAsync>d__53<var<u1>>::itemId
0xd7bb  ldnull
0xd7bc  callvirt instance var<u1> class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>>::GetEntity(!!T0, string)
0xd7c1  stloc.3
0xd7c2  ldarg.0
0xd7c3  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage valuetype <PatchOnDataModelDataSourcesCollectionAsync>d__53<var<u1>>::request
0xd7c8  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Content()
0xd7cd  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<string> [System.Net.Http]System.Net.Http.HttpContent::ReadAsStringAsync()
0xd7d2  callvirt instance var<u1> class [mscorlib]System.Threading.Tasks.Task`1<string>::get_Result()
0xd7d7  stloc.s  4
0xd7d9  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::.ctor()
0xd7de  stloc.s  5
0xd7e0  ldloc.s  4
0xd7e2  ldloc.s  5
0xd7e4  call     void [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::PopulateObject(string, object)
0xd7e9  leave.s  loc_D81B
0xd7eb  stloc.s  6
0xd7ed  ldloc.1
0xd7ee  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::get_Logger()
0xd7f3  ldc.i4.4
0xd7f4  ldstr    aInvalidPayload// "Invalid payload: {0}"
0xd7f9  ldloc.s  6
0xd7fb  callvirt instance string [mscorlib]System.Exception::get_Message()
0xd800  call     string [mscorlib]System.String::Format(string, object)
0xd805  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xd80a  ldloc.1
0xd80b  ldc.i4   0x190
0xd810  call     instance class [System.Web.Http]System.Web.Http.Results.StatusCodeResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::StatusCode(valuetype [System]System.Net.HttpStatusCode)
0xd815  stloc.2
0xd816  leave    loc_D91D
0xd81b  ldloc.s  5
0xd81d  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource, bool> class <>c<var<u1>>::<>9__53_0
0xd822  dup
0xd823  brtrue.s loc_D83C
0xd825  pop
0xd826  ldsfld   class <>c<var<u1>> class <>c<var<u1>>::<>9
0xd82b  ldftn    instance bool class <>c<var<u1>>::<PatchOnDataModelDataSourcesCollectionAsync>b__53_0(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource)
0xd831  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource, bool>::.ctor(object, native int)
0xd836  dup
0xd837  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource, bool> class <>c<var<u1>>::<>9__53_0
0xd83c  call     T0x2B0000F9
0xd841  brfalse.s loc_D865
0xd843  ldloc.1
0xd844  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::get_Logger()
0xd849  ldc.i4.4
0xd84a  ldstr    aThereIsNoDatam// "There is no DataModel in one of the dat"...
0xd84f  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xd854  ldloc.1
0xd855  ldc.i4   0x190
0xd85a  call     instance class [System.Web.Http]System.Web.Http.Results.StatusCodeResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::StatusCode(valuetype [System]System.Net.HttpStatusCode)
0xd85f  stloc.2
0xd860  leave    loc_D91D
0xd865  nop
0xd866  ldloc.0
0xd867  brfalse.s loc_D8B8
0xd869  ldloc.1
0xd86a  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<var<u1>>::get_CatalogRepository()
0xd86f  ldloc.1
0xd870  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0xd875  ldloc.3
0xd876  box      var<u1>
0xd87b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Id()
0xd880  ldloc.s  5
0xd882  callvirt instance class [mscorlib]System.Threading.Tasks.Task [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::UpdateDataModelDataSourcesAsync(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>)
0xd887  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0xd88c  stloc.s  7
0xd88e  ldloca.s 7
0xd890  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0xd895  brtrue.s loc_D8D5
0xd897  ldarg.0
0xd898  ldc.i4.0
0xd899  dup
0xd89a  stloc.0
0xd89b  stfld    int32 valuetype <PatchOnDataModelDataSourcesCollectionAsync>d__53<var<u1>>::<>1__state
0xd8a0  ldarg.0
0xd8a1  ldloc.s  7
0xd8a3  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter valuetype <PatchOnDataModelDataSourcesCollectionAsync>d__53<var<u1>>::<>u__1
0xd8a8  ldarg.0
0xd8a9  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> valuetype <PatchOnDataModelDataSourcesCollectionAsync>d__53<var<u1>>::<>t__builder
0xd8ae  ldloca.s 7
0xd8b0  ldarg.0
0xd8b1  call     T0x2B0000FA
0xd8b6  leave.s  loc_D931
0xd8b8  ldarg.0
0xd8b9  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter valuetype <PatchOnDataModelDataSourcesCollectionAsync>d__53<var<u1>>::<>u__1
0xd8be  stloc.s  7
0xd8c0  ldarg.0
0xd8c1  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter valuetype <PatchOnDataModelDataSourcesCollectionAsync>d__53<var<u1>>::<>u__1
0xd8c6  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0xd8cc  ldarg.0
0xd8cd  ldc.i4.m1
0xd8ce  dup
0xd8cf  stloc.0
0xd8d0  stfld    int32 valuetype <PatchOnDataModelDataSourcesCollectionAsync>d__53<var<u1>>::<>1__state
0xd8d5  ldloca.s 7
0xd8d7  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0xd8dc  leave.s  loc_D8F6
0xd8de  pop
0xd8df  ldc.i4   0x193
0xd8e4  newobj   instance void [System.Web.Http]System.Web.Http.HttpResponseException::.ctor(valuetype [System]System.Net.HttpStatusCode)
0xd8e9  throw
0xd8ea  pop
0xd8eb  ldc.i4   0x190
0xd8f0  newobj   instance void [System.Web.Http]System.Web.Http.HttpResponseException::.ctor(valuetype [System]System.Net.HttpStatusCode)
0xd8f5  throw
0xd8f6  ldloc.1
0xd8f7  ldc.i4   0xC8
0xd8fc  call     instance class [System.Web.Http]System.Web.Http.Results.StatusCodeResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::StatusCode(valuetype [System]System.Net.HttpStatusCode)
0xd901  stloc.2
0xd902  leave.s  loc_D91D
0xd904  stloc.s  8
0xd906  ldarg.0
0xd907  ldc.i4.s 0xFE
0xd909  stfld    int32 valuetype <PatchOnDataModelDataSourcesCollectionAsync>d__53<var<u1>>::<>1__state
0xd90e  ldarg.0
0xd90f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> valuetype <PatchOnDataModelDataSourcesCollectionAsync>d__53<var<u1>>::<>t__builder
0xd914  ldloc.s  8
0xd916  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetException(class [mscorlib]System.Exception)
0xd91b  leave.s  loc_D931
0xd91d  ldarg.0
0xd91e  ldc.i4.s 0xFE
0xd920  stfld    int32 valuetype <PatchOnDataModelDataSourcesCollectionAsync>d__53<var<u1>>::<>1__state
0xd925  ldarg.0
0xd926  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> valuetype <PatchOnDataModelDataSourcesCollectionAsync>d__53<var<u1>>::<>t__builder
0xd92b  ldloc.2
0xd92c  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetResult(var<u1>)
0xd931  ret
```
