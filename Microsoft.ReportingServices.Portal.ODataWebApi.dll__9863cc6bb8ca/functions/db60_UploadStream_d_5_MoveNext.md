# <UploadStream>d__5::MoveNext

- ea: `0xdb60`
- end: `0xdc00`
- name: `<UploadStream>d__5::MoveNext`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0xdb60`

## pseudocode

```c

```

## disassembly

```asm
0xdb60  ldarg.0
0xdb61  ldfld    int32 <UploadStream>d__5::<>1__state
0xdb66  stloc.0
0xdb67  ldarg.0
0xdb68  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.ResourcesController <UploadStream>d__5::<>4__this
0xdb6d  stloc.1
0xdb6e  ldloc.0
0xdb6f  brfalse.s loc_DBAC
0xdb71  ldloc.1
0xdb72  ldarg.0
0xdb73  ldfld    string <UploadStream>d__5::Id
0xdb78  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Resource>::UploadStreamInternal(string)
0xdb7d  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::GetAwaiter()
0xdb82  stloc.3
0xdb83  ldloca.s 3
0xdb85  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::get_IsCompleted()
0xdb8a  brtrue.s loc_DBC8
0xdb8c  ldarg.0
0xdb8d  ldc.i4.0
0xdb8e  dup
0xdb8f  stloc.0
0xdb90  stfld    int32 <UploadStream>d__5::<>1__state
0xdb95  ldarg.0
0xdb96  ldloc.3
0xdb97  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__5::<>u__1
0xdb9c  ldarg.0
0xdb9d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__5::<>t__builder
0xdba2  ldloca.s 3
0xdba4  ldarg.0
0xdba5  call     T0x2B0000FC
0xdbaa  leave.s  loc_DBFF
0xdbac  ldarg.0
0xdbad  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__5::<>u__1
0xdbb2  stloc.3
0xdbb3  ldarg.0
0xdbb4  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__5::<>u__1
0xdbb9  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>
0xdbbf  ldarg.0
0xdbc0  ldc.i4.m1
0xdbc1  dup
0xdbc2  stloc.0
0xdbc3  stfld    int32 <UploadStream>d__5::<>1__state
0xdbc8  ldloca.s 3
0xdbca  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::GetResult()
0xdbcf  stloc.2
0xdbd0  leave.s  loc_DBEB
0xdbd2  stloc.s  4
0xdbd4  ldarg.0
0xdbd5  ldc.i4.s 0xFE
0xdbd7  stfld    int32 <UploadStream>d__5::<>1__state
0xdbdc  ldarg.0
0xdbdd  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__5::<>t__builder
0xdbe2  ldloc.s  4
0xdbe4  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetException(class [mscorlib]System.Exception)
0xdbe9  leave.s  loc_DBFF
0xdbeb  ldarg.0
0xdbec  ldc.i4.s 0xFE
0xdbee  stfld    int32 <UploadStream>d__5::<>1__state
0xdbf3  ldarg.0
0xdbf4  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__5::<>t__builder
0xdbf9  ldloc.2
0xdbfa  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetResult(var<u1>)
0xdbff  ret
```
