# <UploadStream>d__5::MoveNext_1

- ea: `0xe6e0`
- end: `0xe780`
- name: `<UploadStream>d__5::MoveNext_1`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0xe6e0`

## pseudocode

```c

```

## disassembly

```asm
0xe6e0  ldarg.0
0xe6e1  ldfld    int32 <UploadStream>d__5::<>1__state
0xe6e6  stloc.0
0xe6e7  ldarg.0
0xe6e8  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.DataSetsController <UploadStream>d__5::<>4__this
0xe6ed  stloc.1
0xe6ee  ldloc.0
0xe6ef  brfalse.s loc_E72C
0xe6f1  ldloc.1
0xe6f2  ldarg.0
0xe6f3  ldfld    string <UploadStream>d__5::Id
0xe6f8  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet>::UploadStreamInternal(string)
0xe6fd  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::GetAwaiter()
0xe702  stloc.3
0xe703  ldloca.s 3
0xe705  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::get_IsCompleted()
0xe70a  brtrue.s loc_E748
0xe70c  ldarg.0
0xe70d  ldc.i4.0
0xe70e  dup
0xe70f  stloc.0
0xe710  stfld    int32 <UploadStream>d__5::<>1__state
0xe715  ldarg.0
0xe716  ldloc.3
0xe717  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__5::<>u__1
0xe71c  ldarg.0
0xe71d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__5::<>t__builder
0xe722  ldloca.s 3
0xe724  ldarg.0
0xe725  call     T0x2B000107
0xe72a  leave.s  loc_E77F
0xe72c  ldarg.0
0xe72d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__5::<>u__1
0xe732  stloc.3
0xe733  ldarg.0
0xe734  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__5::<>u__1
0xe739  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>
0xe73f  ldarg.0
0xe740  ldc.i4.m1
0xe741  dup
0xe742  stloc.0
0xe743  stfld    int32 <UploadStream>d__5::<>1__state
0xe748  ldloca.s 3
0xe74a  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::GetResult()
0xe74f  stloc.2
0xe750  leave.s  loc_E76B
0xe752  stloc.s  4
0xe754  ldarg.0
0xe755  ldc.i4.s 0xFE
0xe757  stfld    int32 <UploadStream>d__5::<>1__state
0xe75c  ldarg.0
0xe75d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__5::<>t__builder
0xe762  ldloc.s  4
0xe764  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetException(class [mscorlib]System.Exception)
0xe769  leave.s  loc_E77F
0xe76b  ldarg.0
0xe76c  ldc.i4.s 0xFE
0xe76e  stfld    int32 <UploadStream>d__5::<>1__state
0xe773  ldarg.0
0xe774  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__5::<>t__builder
0xe779  ldloc.2
0xe77a  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetResult(var<u1>)
0xe77f  ret
```
