# <GetDataModelRoles>d__43::MoveNext

- ea: `0xe200`
- end: `0xe2df`
- name: `<GetDataModelRoles>d__43::MoveNext`
- size: `223`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0xe200`

## pseudocode

```c

```

## disassembly

```asm
0xe200  ldarg.0
0xe201  ldfld    int32 <GetDataModelRoles>d__43::<>1__state
0xe206  stloc.0
0xe207  ldarg.0
0xe208  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PowerBIReportsController <GetDataModelRoles>d__43::<>4__this
0xe20d  stloc.1
0xe20e  ldloc.0
0xe20f  brfalse.s loc_E280
0xe211  ldloc.1
0xe212  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PowerBIReportsController::_systemService
0xe217  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService::IsBiServer()
0xe21c  brtrue.s loc_E22A
0xe21e  ldloc.1
0xe21f  call     instance class [System.Web.Http]System.Web.Http.Results.StatusCodeResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::NotAllowed()
0xe224  stloc.2
0xe225  leave    loc_E2CA
0xe22a  ldloc.1
0xe22b  ldarg.0
0xe22c  ldfld    string <GetDataModelRoles>d__43::Id
0xe231  ldnull
0xe232  callvirt instance var<u1> class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::GetEntity(!!T0, string)
0xe237  stloc.3
0xe238  ldloc.1
0xe239  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::get_CatalogRepository()
0xe23e  ldloc.1
0xe23f  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0xe244  ldloc.3
0xe245  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Id()
0xe24a  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole>> [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetDataModelRolesAsync(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid)
0xe24f  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole>>::GetAwaiter()
0xe254  stloc.s  5
0xe256  ldloca.s 5
0xe258  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole>>::get_IsCompleted()
0xe25d  brtrue.s loc_E29D
0xe25f  ldarg.0
0xe260  ldc.i4.0
0xe261  dup
0xe262  stloc.0
0xe263  stfld    int32 <GetDataModelRoles>d__43::<>1__state
0xe268  ldarg.0
0xe269  ldloc.s  5
0xe26b  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole>> <GetDataModelRoles>d__43::<>u__1
0xe270  ldarg.0
0xe271  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <GetDataModelRoles>d__43::<>t__builder
0xe276  ldloca.s 5
0xe278  ldarg.0
0xe279  call     T0x2B000102
0xe27e  leave.s  loc_E2DE
0xe280  ldarg.0
0xe281  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole>> <GetDataModelRoles>d__43::<>u__1
0xe286  stloc.s  5
0xe288  ldarg.0
0xe289  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole>> <GetDataModelRoles>d__43::<>u__1
0xe28e  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole>>
0xe294  ldarg.0
0xe295  ldc.i4.m1
0xe296  dup
0xe297  stloc.0
0xe298  stfld    int32 <GetDataModelRoles>d__43::<>1__state
0xe29d  ldloca.s 5
0xe29f  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole>>::GetResult()
0xe2a4  stloc.s  4
0xe2a6  ldloc.1
0xe2a7  ldloc.s  4
0xe2a9  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::CreateOk(object)
0xe2ae  stloc.2
0xe2af  leave.s  loc_E2CA
0xe2b1  stloc.s  6
0xe2b3  ldarg.0
0xe2b4  ldc.i4.s 0xFE
0xe2b6  stfld    int32 <GetDataModelRoles>d__43::<>1__state
0xe2bb  ldarg.0
0xe2bc  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <GetDataModelRoles>d__43::<>t__builder
0xe2c1  ldloc.s  6
0xe2c3  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetException(class [mscorlib]System.Exception)
0xe2c8  leave.s  loc_E2DE
0xe2ca  ldarg.0
0xe2cb  ldc.i4.s 0xFE
0xe2cd  stfld    int32 <GetDataModelRoles>d__43::<>1__state
0xe2d2  ldarg.0
0xe2d3  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <GetDataModelRoles>d__43::<>t__builder
0xe2d8  ldloc.2
0xe2d9  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetResult(var<u1>)
0xe2de  ret
```
