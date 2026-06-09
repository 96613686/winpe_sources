# <UploadStream>d__7::MoveNext

- ea: `0xe560`
- end: `0xe600`
- name: `<UploadStream>d__7::MoveNext`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0xe560`

## pseudocode

```c

```

## disassembly

```asm
0xe560  ldarg.0
0xe561  ldfld    int32 <UploadStream>d__7::<>1__state
0xe566  stloc.0
0xe567  ldarg.0
0xe568  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.ExcelWorkbooksController <UploadStream>d__7::<>4__this
0xe56d  stloc.1
0xe56e  ldloc.0
0xe56f  brfalse.s loc_E5AC
0xe571  ldloc.1
0xe572  ldarg.0
0xe573  ldfld    string <UploadStream>d__7::Id
0xe578  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExcelWorkbook>::UploadStreamInternal(string)
0xe57d  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::GetAwaiter()
0xe582  stloc.3
0xe583  ldloca.s 3
0xe585  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::get_IsCompleted()
0xe58a  brtrue.s loc_E5C8
0xe58c  ldarg.0
0xe58d  ldc.i4.0
0xe58e  dup
0xe58f  stloc.0
0xe590  stfld    int32 <UploadStream>d__7::<>1__state
0xe595  ldarg.0
0xe596  ldloc.3
0xe597  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__7::<>u__1
0xe59c  ldarg.0
0xe59d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__7::<>t__builder
0xe5a2  ldloca.s 3
0xe5a4  ldarg.0
0xe5a5  call     T0x2B000105
0xe5aa  leave.s  loc_E5FF
0xe5ac  ldarg.0
0xe5ad  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__7::<>u__1
0xe5b2  stloc.3
0xe5b3  ldarg.0
0xe5b4  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__7::<>u__1
0xe5b9  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>
0xe5bf  ldarg.0
0xe5c0  ldc.i4.m1
0xe5c1  dup
0xe5c2  stloc.0
0xe5c3  stfld    int32 <UploadStream>d__7::<>1__state
0xe5c8  ldloca.s 3
0xe5ca  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::GetResult()
0xe5cf  stloc.2
0xe5d0  leave.s  loc_E5EB
0xe5d2  stloc.s  4
0xe5d4  ldarg.0
0xe5d5  ldc.i4.s 0xFE
0xe5d7  stfld    int32 <UploadStream>d__7::<>1__state
0xe5dc  ldarg.0
0xe5dd  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__7::<>t__builder
0xe5e2  ldloc.s  4
0xe5e4  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetException(class [mscorlib]System.Exception)
0xe5e9  leave.s  loc_E5FF
0xe5eb  ldarg.0
0xe5ec  ldc.i4.s 0xFE
0xe5ee  stfld    int32 <UploadStream>d__7::<>1__state
0xe5f3  ldarg.0
0xe5f4  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__7::<>t__builder
0xe5f9  ldloc.2
0xe5fa  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetResult(var<u1>)
0xe5ff  ret
```
