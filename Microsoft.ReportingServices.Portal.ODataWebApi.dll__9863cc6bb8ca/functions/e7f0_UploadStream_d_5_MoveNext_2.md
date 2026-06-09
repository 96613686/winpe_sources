# <UploadStream>d__5::MoveNext_2

- ea: `0xe7f0`
- end: `0xe890`
- name: `<UploadStream>d__5::MoveNext_2`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0xe7f0`

## pseudocode

```c

```

## disassembly

```asm
0xe7f0  ldarg.0
0xe7f1  ldfld    int32 <UploadStream>d__5::<>1__state
0xe7f6  stloc.0
0xe7f7  ldarg.0
0xe7f8  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.ReportsController <UploadStream>d__5::<>4__this
0xe7fd  stloc.1
0xe7fe  ldloc.0
0xe7ff  brfalse.s loc_E83C
0xe801  ldloc.1
0xe802  ldarg.0
0xe803  ldfld    string <UploadStream>d__5::Id
0xe808  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report>::UploadStreamInternal(string)
0xe80d  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::GetAwaiter()
0xe812  stloc.3
0xe813  ldloca.s 3
0xe815  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::get_IsCompleted()
0xe81a  brtrue.s loc_E858
0xe81c  ldarg.0
0xe81d  ldc.i4.0
0xe81e  dup
0xe81f  stloc.0
0xe820  stfld    int32 <UploadStream>d__5::<>1__state
0xe825  ldarg.0
0xe826  ldloc.3
0xe827  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__5::<>u__1
0xe82c  ldarg.0
0xe82d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__5::<>t__builder
0xe832  ldloca.s 3
0xe834  ldarg.0
0xe835  call     T0x2B000108
0xe83a  leave.s  loc_E88F
0xe83c  ldarg.0
0xe83d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__5::<>u__1
0xe842  stloc.3
0xe843  ldarg.0
0xe844  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__5::<>u__1
0xe849  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>
0xe84f  ldarg.0
0xe850  ldc.i4.m1
0xe851  dup
0xe852  stloc.0
0xe853  stfld    int32 <UploadStream>d__5::<>1__state
0xe858  ldloca.s 3
0xe85a  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::GetResult()
0xe85f  stloc.2
0xe860  leave.s  loc_E87B
0xe862  stloc.s  4
0xe864  ldarg.0
0xe865  ldc.i4.s 0xFE
0xe867  stfld    int32 <UploadStream>d__5::<>1__state
0xe86c  ldarg.0
0xe86d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__5::<>t__builder
0xe872  ldloc.s  4
0xe874  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetException(class [mscorlib]System.Exception)
0xe879  leave.s  loc_E88F
0xe87b  ldarg.0
0xe87c  ldc.i4.s 0xFE
0xe87e  stfld    int32 <UploadStream>d__5::<>1__state
0xe883  ldarg.0
0xe884  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__5::<>t__builder
0xe889  ldloc.2
0xe88a  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetResult(var<u1>)
0xe88f  ret
```
