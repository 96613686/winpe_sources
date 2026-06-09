# <GetDataModelRoleAssignments>d__44::MoveNext

- ea: `0xe300`
- end: `0xe3df`
- name: `<GetDataModelRoleAssignments>d__44::MoveNext`
- size: `223`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0xe300`

## pseudocode

```c

```

## disassembly

```asm
0xe300  ldarg.0
0xe301  ldfld    int32 <GetDataModelRoleAssignments>d__44::<>1__state
0xe306  stloc.0
0xe307  ldarg.0
0xe308  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PowerBIReportsController <GetDataModelRoleAssignments>d__44::<>4__this
0xe30d  stloc.1
0xe30e  ldloc.0
0xe30f  brfalse.s loc_E380
0xe311  ldloc.1
0xe312  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PowerBIReportsController::_systemService
0xe317  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService::IsBiServer()
0xe31c  brtrue.s loc_E32A
0xe31e  ldloc.1
0xe31f  call     instance class [System.Web.Http]System.Web.Http.Results.StatusCodeResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::NotAllowed()
0xe324  stloc.2
0xe325  leave    loc_E3CA
0xe32a  ldloc.1
0xe32b  ldarg.0
0xe32c  ldfld    string <GetDataModelRoleAssignments>d__44::Id
0xe331  ldnull
0xe332  callvirt instance var<u1> class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::GetEntity(!!T0, string)
0xe337  stloc.3
0xe338  ldloc.1
0xe339  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::get_CatalogRepository()
0xe33e  ldloc.1
0xe33f  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0xe344  ldloc.3
0xe345  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Id()
0xe34a  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment>> [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetDataModelRoleAssignmentsAsync(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid)
0xe34f  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment>>::GetAwaiter()
0xe354  stloc.s  5
0xe356  ldloca.s 5
0xe358  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment>>::get_IsCompleted()
0xe35d  brtrue.s loc_E39D
0xe35f  ldarg.0
0xe360  ldc.i4.0
0xe361  dup
0xe362  stloc.0
0xe363  stfld    int32 <GetDataModelRoleAssignments>d__44::<>1__state
0xe368  ldarg.0
0xe369  ldloc.s  5
0xe36b  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment>> <GetDataModelRoleAssignments>d__44::<>u__1
0xe370  ldarg.0
0xe371  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <GetDataModelRoleAssignments>d__44::<>t__builder
0xe376  ldloca.s 5
0xe378  ldarg.0
0xe379  call     T0x2B000103
0xe37e  leave.s  loc_E3DE
0xe380  ldarg.0
0xe381  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment>> <GetDataModelRoleAssignments>d__44::<>u__1
0xe386  stloc.s  5
0xe388  ldarg.0
0xe389  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment>> <GetDataModelRoleAssignments>d__44::<>u__1
0xe38e  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment>>
0xe394  ldarg.0
0xe395  ldc.i4.m1
0xe396  dup
0xe397  stloc.0
0xe398  stfld    int32 <GetDataModelRoleAssignments>d__44::<>1__state
0xe39d  ldloca.s 5
0xe39f  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment>>::GetResult()
0xe3a4  stloc.s  4
0xe3a6  ldloc.1
0xe3a7  ldloc.s  4
0xe3a9  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::CreateOk(object)
0xe3ae  stloc.2
0xe3af  leave.s  loc_E3CA
0xe3b1  stloc.s  6
0xe3b3  ldarg.0
0xe3b4  ldc.i4.s 0xFE
0xe3b6  stfld    int32 <GetDataModelRoleAssignments>d__44::<>1__state
0xe3bb  ldarg.0
0xe3bc  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <GetDataModelRoleAssignments>d__44::<>t__builder
0xe3c1  ldloc.s  6
0xe3c3  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetException(class [mscorlib]System.Exception)
0xe3c8  leave.s  loc_E3DE
0xe3ca  ldarg.0
0xe3cb  ldc.i4.s 0xFE
0xe3cd  stfld    int32 <GetDataModelRoleAssignments>d__44::<>1__state
0xe3d2  ldarg.0
0xe3d3  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <GetDataModelRoleAssignments>d__44::<>t__builder
0xe3d8  ldloc.2
0xe3d9  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetResult(var<u1>)
0xe3de  ret
```
