# <UploadStream>d__5::MoveNext_0

- ea: `0xe620`
- end: `0xe6c0`
- name: `<UploadStream>d__5::MoveNext_0`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0xe620`

## pseudocode

```c

```

## disassembly

```asm
0xe620  ldarg.0
0xe621  ldfld    int32 <UploadStream>d__5::<>1__state
0xe626  stloc.0
0xe627  ldarg.0
0xe628  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.DataSourcesController <UploadStream>d__5::<>4__this
0xe62d  stloc.1
0xe62e  ldloc.0
0xe62f  brfalse.s loc_E66C
0xe631  ldloc.1
0xe632  ldarg.0
0xe633  ldfld    string <UploadStream>d__5::Id
0xe638  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::UploadStreamInternal(string)
0xe63d  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::GetAwaiter()
0xe642  stloc.3
0xe643  ldloca.s 3
0xe645  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::get_IsCompleted()
0xe64a  brtrue.s loc_E688
0xe64c  ldarg.0
0xe64d  ldc.i4.0
0xe64e  dup
0xe64f  stloc.0
0xe650  stfld    int32 <UploadStream>d__5::<>1__state
0xe655  ldarg.0
0xe656  ldloc.3
0xe657  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__5::<>u__1
0xe65c  ldarg.0
0xe65d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__5::<>t__builder
0xe662  ldloca.s 3
0xe664  ldarg.0
0xe665  call     T0x2B000106
0xe66a  leave.s  loc_E6BF
0xe66c  ldarg.0
0xe66d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__5::<>u__1
0xe672  stloc.3
0xe673  ldarg.0
0xe674  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__5::<>u__1
0xe679  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>
0xe67f  ldarg.0
0xe680  ldc.i4.m1
0xe681  dup
0xe682  stloc.0
0xe683  stfld    int32 <UploadStream>d__5::<>1__state
0xe688  ldloca.s 3
0xe68a  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::GetResult()
0xe68f  stloc.2
0xe690  leave.s  loc_E6AB
0xe692  stloc.s  4
0xe694  ldarg.0
0xe695  ldc.i4.s 0xFE
0xe697  stfld    int32 <UploadStream>d__5::<>1__state
0xe69c  ldarg.0
0xe69d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__5::<>t__builder
0xe6a2  ldloc.s  4
0xe6a4  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetException(class [mscorlib]System.Exception)
0xe6a9  leave.s  loc_E6BF
0xe6ab  ldarg.0
0xe6ac  ldc.i4.s 0xFE
0xe6ae  stfld    int32 <UploadStream>d__5::<>1__state
0xe6b3  ldarg.0
0xe6b4  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__5::<>t__builder
0xe6b9  ldloc.2
0xe6ba  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetResult(var<u1>)
0xe6bf  ret
```
