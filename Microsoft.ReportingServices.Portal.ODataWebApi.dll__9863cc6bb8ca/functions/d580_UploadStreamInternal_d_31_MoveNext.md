# <UploadStreamInternal>d__31::MoveNext

- ea: `0xd580`
- end: `0xd739`
- name: `<UploadStreamInternal>d__31::MoveNext`
- size: `441`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0xd580`

## pseudocode

```c

```

## disassembly

```asm
0xd580  ldarg.0
0xd581  ldfld    int32 valuetype <UploadStreamInternal>d__31<var<u1>>::<>1__state
0xd586  stloc.0
0xd587  ldarg.0
0xd588  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<var<u1>> valuetype <UploadStreamInternal>d__31<var<u1>>::<>4__this
0xd58d  stloc.1
0xd58e  ldloc.0
0xd58f  brfalse.s loc_D5D9
0xd591  ldloc.1
0xd592  call     instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IFileSizeRestrictions class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<var<u1>>::get_FileSizeRestrictions()
0xd597  ldloc.1
0xd598  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0xd59d  call     int64 [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.Http.BinaryUploader::ApproximateUploadSize(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0xd5a2  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IFileSizeRestrictions::ThrowIfSizeIsOutOfLimits(int64)
0xd5a7  ldarg.0
0xd5a8  ldloc.1
0xd5a9  ldarg.0
0xd5aa  ldfld    string valuetype <UploadStreamInternal>d__31<var<u1>>::Id
0xd5af  call     instance var<u1> class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<var<u1>>::GetOrCreateItem(!!T0)
0xd5b4  stfld    var<u1> valuetype <UploadStreamInternal>d__31<var<u1>>::<entity>5__2
0xd5b9  ldarg.0
0xd5ba  ldarg.0
0xd5bb  ldfld    var<u1> valuetype <UploadStreamInternal>d__31<var<u1>>::<entity>5__2
0xd5c0  box      var<u1>
0xd5c5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Id()
0xd5ca  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xd5cf  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xd5d4  stfld    bool valuetype <UploadStreamInternal>d__31<var<u1>>::<creating>5__3
0xd5d9  nop
0xd5da  ldloc.0
0xd5db  brfalse.s loc_D622
0xd5dd  ldloc.1
0xd5de  ldfld    class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.Http.BinaryUploader class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<var<u1>>::_uploader
0xd5e3  ldloc.1
0xd5e4  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0xd5e9  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.IO.FileInfo> [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.Http.BinaryUploader::Upload(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0xd5ee  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.IO.FileInfo>::GetAwaiter()
0xd5f3  stloc.s  4
0xd5f5  ldloca.s 4
0xd5f7  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.FileInfo>::get_IsCompleted()
0xd5fc  brtrue.s loc_D63F
0xd5fe  ldarg.0
0xd5ff  ldc.i4.0
0xd600  dup
0xd601  stloc.0
0xd602  stfld    int32 valuetype <UploadStreamInternal>d__31<var<u1>>::<>1__state
0xd607  ldarg.0
0xd608  ldloc.s  4
0xd60a  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.FileInfo> valuetype <UploadStreamInternal>d__31<var<u1>>::<>u__1
0xd60f  ldarg.0
0xd610  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> valuetype <UploadStreamInternal>d__31<var<u1>>::<>t__builder
0xd615  ldloca.s 4
0xd617  ldarg.0
0xd618  call     T0x2B0000F8
0xd61d  leave    loc_D738
0xd622  ldarg.0
0xd623  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.FileInfo> valuetype <UploadStreamInternal>d__31<var<u1>>::<>u__1
0xd628  stloc.s  4
0xd62a  ldarg.0
0xd62b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.FileInfo> valuetype <UploadStreamInternal>d__31<var<u1>>::<>u__1
0xd630  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.FileInfo>
0xd636  ldarg.0
0xd637  ldc.i4.m1
0xd638  dup
0xd639  stloc.0
0xd63a  stfld    int32 valuetype <UploadStreamInternal>d__31<var<u1>>::<>1__state
0xd63f  ldloca.s 4
0xd641  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.FileInfo>::GetResult()
0xd646  newobj   instance void [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ScopedFileDelete::.ctor(class [mscorlib]System.IO.FileInfo)
0xd64b  stloc.3
0xd64c  ldloc.1
0xd64d  callvirt instance bool class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<var<u1>>::get_EntityUsesStreamingStorage()
0xd652  brfalse.s loc_D6A2
0xd654  ldloc.3
0xd655  ldfld    string [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ScopedFileDelete::FullPath
0xd65a  ldc.i4.3
0xd65b  newobj   instance void [mscorlib]System.IO.FileStream::.ctor(string, valuetype [mscorlib]System.IO.FileMode)
0xd660  stloc.s  5
0xd662  ldarg.0
0xd663  ldfld    var<u1> valuetype <UploadStreamInternal>d__31<var<u1>>::<entity>5__2
0xd668  box      var<u1>
0xd66d  ldloc.s  5
0xd66f  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::SetContent(class [mscorlib]System.IO.Stream)
0xd674  ldloc.1
0xd675  ldarg.0
0xd676  ldfld    string valuetype <UploadStreamInternal>d__31<var<u1>>::Id
0xd67b  ldarg.0
0xd67c  ldfld    bool valuetype <UploadStreamInternal>d__31<var<u1>>::<creating>5__3
0xd681  ldarg.0
0xd682  ldfld    var<u1> valuetype <UploadStreamInternal>d__31<var<u1>>::<entity>5__2
0xd687  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<var<u1>>::Persist(string, bool, var<u1>)
0xd68c  stloc.2
0xd68d  leave    loc_D724
0xd692  ldloc.0
0xd693  ldc.i4.0
0xd694  bge.s    loc_D6A1
0xd696  ldloc.s  5
0xd698  brfalse.s loc_D6A1
0xd69a  ldloc.s  5
0xd69c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd6a1  endfinally
0xd6a2  ldarg.0
0xd6a3  ldfld    var<u1> valuetype <UploadStreamInternal>d__31<var<u1>>::<entity>5__2
0xd6a8  box      var<u1>
0xd6ad  ldloc.3
0xd6ae  ldfld    string [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ScopedFileDelete::FullPath
0xd6b3  call     unsigned int8[] [mscorlib]System.IO.File::ReadAllBytes(string)
0xd6b8  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_Content(unsigned int8[])
0xd6bd  ldloc.1
0xd6be  ldarg.0
0xd6bf  ldfld    string valuetype <UploadStreamInternal>d__31<var<u1>>::Id
0xd6c4  ldarg.0
0xd6c5  ldfld    bool valuetype <UploadStreamInternal>d__31<var<u1>>::<creating>5__3
0xd6ca  ldarg.0
0xd6cb  ldfld    var<u1> valuetype <UploadStreamInternal>d__31<var<u1>>::<entity>5__2
0xd6d0  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<var<u1>>::Persist(string, bool, var<u1>)
0xd6d5  stloc.2
0xd6d6  leave.s  loc_D724
0xd6d8  ldloc.0
0xd6d9  ldc.i4.0
0xd6da  bge.s    loc_D6E5
0xd6dc  ldloc.3
0xd6dd  brfalse.s loc_D6E5
0xd6df  ldloc.3
0xd6e0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd6e5  endfinally
0xd6e6  stloc.s  6
0xd6e8  ldloc.s  6
0xd6ea  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::GetBaseException()
0xd6ef  stloc.s  7
0xd6f1  ldloc.s  7
0xd6f3  isinst   [System]System.Net.HttpListenerException
0xd6f8  brfalse.s loc_D709
0xd6fa  ldloc.s  7
0xd6fc  callvirt instance string [mscorlib]System.Exception::get_Message()
0xd701  ldloc.s  6
0xd703  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.UploadFileCanceledException::.ctor(string, class [mscorlib]System.Exception)
0xd708  throw
0xd709  rethrow
0xd70b  stloc.s  8
0xd70d  ldarg.0
0xd70e  ldc.i4.s 0xFE
0xd710  stfld    int32 valuetype <UploadStreamInternal>d__31<var<u1>>::<>1__state
0xd715  ldarg.0
0xd716  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> valuetype <UploadStreamInternal>d__31<var<u1>>::<>t__builder
0xd71b  ldloc.s  8
0xd71d  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetException(class [mscorlib]System.Exception)
0xd722  leave.s  loc_D738
0xd724  ldarg.0
0xd725  ldc.i4.s 0xFE
0xd727  stfld    int32 valuetype <UploadStreamInternal>d__31<var<u1>>::<>1__state
0xd72c  ldarg.0
0xd72d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> valuetype <UploadStreamInternal>d__31<var<u1>>::<>t__builder
0xd732  ldloc.2
0xd733  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetResult(var<u1>)
0xd738  ret
```
