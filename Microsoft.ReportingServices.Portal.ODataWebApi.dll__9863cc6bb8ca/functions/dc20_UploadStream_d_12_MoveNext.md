# <UploadStream>d__12::MoveNext

- ea: `0xdc20`
- end: `0xdf07`
- name: `<UploadStream>d__12::MoveNext`
- size: `743`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x34a0`
- `0x34b0`
- `0x34c0`
- `0x34e0`
- `0x3630`
- `0x3970`
- `0xcf30`
- `0xdc20`

## pseudocode

```c

```

## disassembly

```asm
0xdc20  ldarg.0
0xdc21  ldfld    int32 <UploadStream>d__12::<>1__state
0xdc26  stloc.0
0xdc27  ldarg.0
0xdc28  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PowerBIReportsController <UploadStream>d__12::<>4__this
0xdc2d  stloc.1
0xdc2e  ldloc.0
0xdc2f  ldc.i4.1
0xdc30  ble.un.s loc_DC53
0xdc32  ldarg.0
0xdc33  ldc.i4.2
0xdc34  newarr   [mscorlib]System.String
0xdc39  dup
0xdc3a  ldc.i4.0
0xdc3b  ldstr    aPost// "POST"
0xdc40  stelem.ref
0xdc41  dup
0xdc42  ldc.i4.1
0xdc43  ldstr    aPowerbireports_0// "PowerBIReports({Id})/Model.Upload"
0xdc48  stelem.ref
0xdc49  call     class [mscorlib]System.IDisposable [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use(string[])
0xdc4e  stfld    class [mscorlib]System.IDisposable <UploadStream>d__12::<>7__wrap1
0xdc53  nop
0xdc54  ldloc.0
0xdc55  brfalse.s loc_DCBF
0xdc57  ldloc.0
0xdc58  ldc.i4.1
0xdc59  beq      loc_DCFA
0xdc5e  ldloc.1
0xdc5f  call     instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IFileSizeRestrictions class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::get_FileSizeRestrictions()
0xdc64  ldloc.1
0xdc65  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0xdc6a  call     int64 [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.Http.BinaryUploader::ApproximateUploadSize(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0xdc6f  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IFileSizeRestrictions::ThrowIfSizeIsOutOfLimits(int64)
0xdc74  ldloc.1
0xdc75  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PowerBIReportsController::_systemService
0xdc7a  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService::IsBiServer()
0xdc7f  brtrue.s loc_DCE8
0xdc81  ldloc.1
0xdc82  ldarg.0
0xdc83  ldfld    string <UploadStream>d__12::Id
0xdc88  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::UploadStreamInternal(string)
0xdc8d  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::GetAwaiter()
0xdc92  stloc.3
0xdc93  ldloca.s 3
0xdc95  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::get_IsCompleted()
0xdc9a  brtrue.s loc_DCDB
0xdc9c  ldarg.0
0xdc9d  ldc.i4.0
0xdc9e  dup
0xdc9f  stloc.0
0xdca0  stfld    int32 <UploadStream>d__12::<>1__state
0xdca5  ldarg.0
0xdca6  ldloc.3
0xdca7  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__12::<>u__1
0xdcac  ldarg.0
0xdcad  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__12::<>t__builder
0xdcb2  ldloca.s 3
0xdcb4  ldarg.0
0xdcb5  call     T0x2B0000FD
0xdcba  leave    loc_DF06
0xdcbf  ldarg.0
0xdcc0  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__12::<>u__1
0xdcc5  stloc.3
0xdcc6  ldarg.0
0xdcc7  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__12::<>u__1
0xdccc  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>
0xdcd2  ldarg.0
0xdcd3  ldc.i4.m1
0xdcd4  dup
0xdcd5  stloc.0
0xdcd6  stfld    int32 <UploadStream>d__12::<>1__state
0xdcdb  ldloca.s 3
0xdcdd  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::GetResult()
0xdce2  stloc.2
0xdce3  leave    loc_DEF2
0xdce8  ldarg.0
0xdce9  ldloc.1
0xdcea  ldarg.0
0xdceb  ldfld    string <UploadStream>d__12::Id
0xdcf0  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PowerBIReportsController::GetOrCreatePowerBIReport(string Id)
0xdcf5  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport <UploadStream>d__12::<entity>5__3
0xdcfa  nop
0xdcfb  ldloc.0
0xdcfc  ldc.i4.1
0xdcfd  beq.s    loc_DD44
0xdcff  ldloc.1
0xdd00  ldfld    class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.Http.BinaryUploader Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PowerBIReportsController::_uploader
0xdd05  ldloc.1
0xdd06  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0xdd0b  call     class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PreShreddedPbixFiles> Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PreShreddedPbixFiles::UploadAndShred(class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.Http.BinaryUploader binaryUploader, class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0xdd10  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PreShreddedPbixFiles>::GetAwaiter()
0xdd15  stloc.s  5
0xdd17  ldloca.s 5
0xdd19  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PreShreddedPbixFiles>::get_IsCompleted()
0xdd1e  brtrue.s loc_DD61
0xdd20  ldarg.0
0xdd21  ldc.i4.1
0xdd22  dup
0xdd23  stloc.0
0xdd24  stfld    int32 <UploadStream>d__12::<>1__state
0xdd29  ldarg.0
0xdd2a  ldloc.s  5
0xdd2c  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PreShreddedPbixFiles> <UploadStream>d__12::<>u__2
0xdd31  ldarg.0
0xdd32  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__12::<>t__builder
0xdd37  ldloca.s 5
0xdd39  ldarg.0
0xdd3a  call     T0x2B0000FE
0xdd3f  leave    loc_DF06
0xdd44  ldarg.0
0xdd45  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PreShreddedPbixFiles> <UploadStream>d__12::<>u__2
0xdd4a  stloc.s  5
0xdd4c  ldarg.0
0xdd4d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PreShreddedPbixFiles> <UploadStream>d__12::<>u__2
0xdd52  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PreShreddedPbixFiles>
0xdd58  ldarg.0
0xdd59  ldc.i4.m1
0xdd5a  dup
0xdd5b  stloc.0
0xdd5c  stfld    int32 <UploadStream>d__12::<>1__state
0xdd61  ldloca.s 5
0xdd63  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PreShreddedPbixFiles>::GetResult()
0xdd68  stloc.s  4
0xdd6a  ldloc.1
0xdd6b  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PowerBIReportsController::_powerBIReportsControllerHelper
0xdd70  ldarg.0
0xdd71  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport <UploadStream>d__12::<entity>5__3
0xdd76  ldloc.s  4
0xdd78  callvirt instance void Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::PbiParse(class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport item, class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PreShreddedPbixFiles files)
0xdd7d  ldloc.s  4
0xdd7f  callvirt instance string Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PreShreddedPbixFiles::get_Original()
0xdd84  call     class [mscorlib]System.IO.FileStream Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PreShreddedPbixFiles::CreateReadStreamFromPathIfExists(string filePath)
0xdd89  stloc.s  6
0xdd8b  ldloc.s  4
0xdd8d  callvirt instance string Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PreShreddedPbixFiles::get_Pbix()
0xdd92  call     class [mscorlib]System.IO.FileStream Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PreShreddedPbixFiles::CreateReadStreamFromPathIfExists(string filePath)
0xdd97  stloc.s  7
0xdd99  ldloc.s  4
0xdd9b  callvirt instance string Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PreShreddedPbixFiles::get_Model()
0xdda0  call     class [mscorlib]System.IO.FileStream Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PreShreddedPbixFiles::CreateReadStreamFromPathIfExists(string filePath)
0xdda5  stloc.s  8
0xdda7  ldarg.0
0xdda8  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport <UploadStream>d__12::<entity>5__3
0xddad  ldloc.s  6
0xddaf  ldloc.s  7
0xddb1  ldloc.s  8
0xddb3  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport::SetPreShreddedReadStreams(class [mscorlib]System.IO.Stream, class [mscorlib]System.IO.Stream, class [mscorlib]System.IO.Stream)
0xddb8  ldarg.0
0xddb9  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport <UploadStream>d__12::<entity>5__3
0xddbe  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Properties()
0xddc3  brfalse.s loc_DE28
0xddc5  ldarg.0
0xddc6  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport <UploadStream>d__12::<entity>5__3
0xddcb  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Properties()
0xddd0  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>::GetEnumerator()
0xddd5  stloc.s  9
0xddd7  br.s     loc_DE0D
0xddd9  ldloc.s  9
0xdddb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>::get_Current()
0xdde0  stloc.s  0xA
0xdde2  ldloc.s  0xA
0xdde4  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Property::get_Name()
0xdde9  ldstr    aHasembeddedmod// "HasEmbeddedModels"
0xddee  ldc.i4.3
0xddef  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xddf4  brtrue.s loc_DE0D
0xddf6  ldloc.s  0xA
0xddf8  ldloc.s  8
0xddfa  ldnull
0xddfb  cgt.un
0xddfd  stloc.s  0xB
0xddff  ldloca.s 0xB
0xde01  call     instance string [mscorlib]System.Boolean::ToString()
0xde06  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Property::set_Value(string)
0xde0b  br.s     loc_DE16
0xde0d  ldloc.s  9
0xde0f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xde14  brtrue.s loc_DDD9
0xde16  leave.s  loc_DE28
0xde18  ldloc.0
0xde19  ldc.i4.0
0xde1a  bge.s    loc_DE27
0xde1c  ldloc.s  9
0xde1e  brfalse.s loc_DE27
0xde20  ldloc.s  9
0xde22  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xde27  endfinally
0xde28  ldloc.1
0xde29  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::get_CatalogRepository()
0xde2e  ldloc.1
0xde2f  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0xde34  ldarg.0
0xde35  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport <UploadStream>d__12::<entity>5__3
0xde3a  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::UploadPowerBIReport(class [mscorlib]System.Security.Principal.IPrincipal, class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport)
0xde3f  ldarg.0
0xde40  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport <UploadStream>d__12::<entity>5__3
0xde45  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport::ClearContent()
0xde4a  ldloc.1
0xde4b  ldarg.0
0xde4c  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport <UploadStream>d__12::<entity>5__3
0xde51  callvirt T0x2B0000FF
0xde56  stloc.2
0xde57  leave    loc_DEF2
0xde5c  ldloc.0
0xde5d  ldc.i4.0
0xde5e  bge.s    loc_DE6B
0xde60  ldloc.s  8
0xde62  brfalse.s loc_DE6B
0xde64  ldloc.s  8
0xde66  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xde6b  endfinally
0xde6c  ldloc.0
0xde6d  ldc.i4.0
0xde6e  bge.s    loc_DE7B
0xde70  ldloc.s  7
0xde72  brfalse.s loc_DE7B
0xde74  ldloc.s  7
0xde76  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xde7b  endfinally
0xde7c  ldloc.0
0xde7d  ldc.i4.0
0xde7e  bge.s    loc_DE8B
0xde80  ldloc.s  6
0xde82  brfalse.s loc_DE8B
0xde84  ldloc.s  6
0xde86  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xde8b  endfinally
0xde8c  ldloc.0
0xde8d  ldc.i4.0
0xde8e  bge.s    loc_DE9B
0xde90  ldloc.s  4
0xde92  brfalse.s loc_DE9B
0xde94  ldloc.s  4
0xde96  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xde9b  endfinally
0xde9c  stloc.s  0xC
0xde9e  ldloc.s  0xC
0xdea0  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::GetBaseException()
0xdea5  stloc.s  0xD
0xdea7  ldloc.s  0xD
0xdea9  isinst   [System]System.Net.HttpListenerException
0xdeae  brfalse.s loc_DEBF
0xdeb0  ldloc.s  0xD
0xdeb2  callvirt instance string [mscorlib]System.Exception::get_Message()
0xdeb7  ldloc.s  0xC
0xdeb9  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.UploadFileCanceledException::.ctor(string, class [mscorlib]System.Exception)
0xdebe  throw
0xdebf  rethrow
0xdec1  ldloc.0
0xdec2  ldc.i4.0
0xdec3  bge.s    loc_DED8
0xdec5  ldarg.0
0xdec6  ldfld    class [mscorlib]System.IDisposable <UploadStream>d__12::<>7__wrap1
0xdecb  brfalse.s loc_DED8
0xdecd  ldarg.0
0xdece  ldfld    class [mscorlib]System.IDisposable <UploadStream>d__12::<>7__wrap1
0xded3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xded8  endfinally
0xded9  stloc.s  0xE
0xdedb  ldarg.0
0xdedc  ldc.i4.s 0xFE
0xdede  stfld    int32 <UploadStream>d__12::<>1__state
0xdee3  ldarg.0
0xdee4  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__12::<>t__builder
0xdee9  ldloc.s  0xE
0xdeeb  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetException(class [mscorlib]System.Exception)
0xdef0  leave.s  loc_DF06
0xdef2  ldarg.0
0xdef3  ldc.i4.s 0xFE
0xdef5  stfld    int32 <UploadStream>d__12::<>1__state
0xdefa  ldarg.0
0xdefb  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <UploadStream>d__12::<>t__builder
0xdf00  ldloc.2
0xdf01  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetResult(var<u1>)
0xdf06  ret
```
