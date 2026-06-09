# <UploadAndShred>d__9::MoveNext

- ea: `0xd960`
- end: `0xdb34`
- name: `<UploadAndShred>d__9::MoveNext`
- size: `468`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x3530`
- `0x35d0`
- `0xd960`

## string_xrefs

- `0xda1a`: `CopyOrignal`

## pseudocode

```c

```

## disassembly

```asm
0xd960  ldarg.0
0xd961  ldfld    int32 <UploadAndShred>d__9::<>1__state
0xd966  stloc.0
0xd967  ldloc.0
0xd968  brfalse.s loc_D98B
0xd96a  ldarg.0
0xd96b  ldc.i4.2
0xd96c  newarr   [mscorlib]System.String
0xd971  dup
0xd972  ldc.i4.0
0xd973  ldstr    aPreshredder// "PreShredder"
0xd978  stelem.ref
0xd979  dup
0xd97a  ldc.i4.1
0xd97b  ldstr    aTotal// "Total"
0xd980  stelem.ref
0xd981  call     class [mscorlib]System.IDisposable [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use(string[])
0xd986  stfld    class [mscorlib]System.IDisposable <UploadAndShred>d__9::<>7__wrap1
0xd98b  nop
0xd98c  ldloc.0
0xd98d  brfalse.s loc_D9D4
0xd98f  ldarg.0
0xd990  ldfld    class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.Http.BinaryUploader <UploadAndShred>d__9::binaryUploader
0xd995  ldarg.0
0xd996  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <UploadAndShred>d__9::request
0xd99b  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.IO.FileInfo> [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.Http.BinaryUploader::Upload(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0xd9a0  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.IO.FileInfo>::GetAwaiter()
0xd9a5  stloc.s  4
0xd9a7  ldloca.s 4
0xd9a9  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.FileInfo>::get_IsCompleted()
0xd9ae  brtrue.s loc_D9F1
0xd9b0  ldarg.0
0xd9b1  ldc.i4.0
0xd9b2  dup
0xd9b3  stloc.0
0xd9b4  stfld    int32 <UploadAndShred>d__9::<>1__state
0xd9b9  ldarg.0
0xd9ba  ldloc.s  4
0xd9bc  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.FileInfo> <UploadAndShred>d__9::<>u__1
0xd9c1  ldarg.0
0xd9c2  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PreShreddedPbixFiles> <UploadAndShred>d__9::<>t__builder
0xd9c7  ldloca.s 4
0xd9c9  ldarg.0
0xd9ca  call     T0x2B0000FB
0xd9cf  leave    loc_DB33
0xd9d4  ldarg.0
0xd9d5  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.FileInfo> <UploadAndShred>d__9::<>u__1
0xd9da  stloc.s  4
0xd9dc  ldarg.0
0xd9dd  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.FileInfo> <UploadAndShred>d__9::<>u__1
0xd9e2  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.FileInfo>
0xd9e8  ldarg.0
0xd9e9  ldc.i4.m1
0xd9ea  dup
0xd9eb  stloc.0
0xd9ec  stfld    int32 <UploadAndShred>d__9::<>1__state
0xd9f1  ldloca.s 4
0xd9f3  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.IO.FileInfo>::GetResult()
0xd9f8  stloc.2
0xd9f9  ldloc.2
0xd9fa  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0xd9ff  ldstr    aOriginal// "_Original"
0xda04  call     string [mscorlib]System.String::Concat(string, string)
0xda09  stloc.3
0xda0a  ldc.i4.2
0xda0b  newarr   [mscorlib]System.String
0xda10  dup
0xda11  ldc.i4.0
0xda12  ldstr    aPreshredder// "PreShredder"
0xda17  stelem.ref
0xda18  dup
0xda19  ldc.i4.1
0xda1a  ldstr    aCopyorignal// "CopyOrignal"
0xda1f  stelem.ref
0xda20  call     class [mscorlib]System.IDisposable [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use(string[])
0xda25  stloc.s  5
0xda27  ldloc.2
0xda28  ldloc.3
0xda29  callvirt instance class [mscorlib]System.IO.FileInfo [mscorlib]System.IO.FileInfo::CopyTo(string)
0xda2e  pop
0xda2f  leave.s  loc_DA41
0xda31  ldloc.0
0xda32  ldc.i4.0
0xda33  bge.s    loc_DA40
0xda35  ldloc.s  5
0xda37  brfalse.s loc_DA40
0xda39  ldloc.s  5
0xda3b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xda40  endfinally
0xda41  ldc.i4.2
0xda42  newarr   [mscorlib]System.String
0xda47  dup
0xda48  ldc.i4.0
0xda49  ldstr    aPreshredder// "PreShredder"
0xda4e  stelem.ref
0xda4f  dup
0xda50  ldc.i4.1
0xda51  ldstr    aZipsurgery// "ZipSurgery"
0xda56  stelem.ref
0xda57  call     class [mscorlib]System.IDisposable [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use(string[])
0xda5c  stloc.s  5
0xda5e  ldloc.2
0xda5f  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0xda64  ldc.i4.2
0xda65  call     class [System.IO.Compression]System.IO.Compression.ZipArchive [System.IO.Compression.FileSystem]System.IO.Compression.ZipFile::Open(string, valuetype [System.IO.Compression]System.IO.Compression.ZipArchiveMode)
0xda6a  stloc.s  6
0xda6c  ldloc.s  6
0xda6e  ldstr    aDatamodel// "DataModel"
0xda73  callvirt instance class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry [System.IO.Compression]System.IO.Compression.ZipArchive::GetEntry(string)
0xda78  stloc.s  7
0xda7a  ldloc.s  7
0xda7c  brtrue.s loc_DA8F
0xda7e  ldloc.2
0xda7f  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0xda84  newobj   instance void Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PreShreddedPbixFiles::.ctor(string pbix)
0xda89  stloc.1
0xda8a  leave    loc_DB1F
0xda8f  ldloc.2
0xda90  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0xda95  ldstr    aModel_0// "_Model"
0xda9a  call     string [mscorlib]System.String::Concat(string, string)
0xda9f  stloc.s  8
0xdaa1  ldloc.s  7
0xdaa3  ldloc.s  8
0xdaa5  call     void [System.IO.Compression.FileSystem]System.IO.Compression.ZipFileExtensions::ExtractToFile(class [System.IO.Compression]System.IO.Compression.ZipArchiveEntry, string)
0xdaaa  ldloc.s  8
0xdaac  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xdab1  call     void [mscorlib]System.IO.File::SetLastWriteTime(string, valuetype [mscorlib]System.DateTime)
0xdab6  ldloc.s  7
0xdab8  callvirt instance void [System.IO.Compression]System.IO.Compression.ZipArchiveEntry::Delete()
0xdabd  ldloc.3
0xdabe  ldloc.2
0xdabf  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0xdac4  ldloc.s  8
0xdac6  newobj   instance void Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PreShreddedPbixFiles::.ctor(string original, string pbix, string model)
0xdacb  stloc.1
0xdacc  leave.s  loc_DB1F
0xdace  ldloc.0
0xdacf  ldc.i4.0
0xdad0  bge.s    loc_DADD
0xdad2  ldloc.s  6
0xdad4  brfalse.s loc_DADD
0xdad6  ldloc.s  6
0xdad8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdadd  endfinally
0xdade  ldloc.0
0xdadf  ldc.i4.0
0xdae0  bge.s    loc_DAED
0xdae2  ldloc.s  5
0xdae4  brfalse.s loc_DAED
0xdae6  ldloc.s  5
0xdae8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdaed  endfinally
0xdaee  ldloc.0
0xdaef  ldc.i4.0
0xdaf0  bge.s    loc_DB05
0xdaf2  ldarg.0
0xdaf3  ldfld    class [mscorlib]System.IDisposable <UploadAndShred>d__9::<>7__wrap1
0xdaf8  brfalse.s loc_DB05
0xdafa  ldarg.0
0xdafb  ldfld    class [mscorlib]System.IDisposable <UploadAndShred>d__9::<>7__wrap1
0xdb00  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdb05  endfinally
0xdb06  stloc.s  9
0xdb08  ldarg.0
0xdb09  ldc.i4.s 0xFE
0xdb0b  stfld    int32 <UploadAndShred>d__9::<>1__state
0xdb10  ldarg.0
0xdb11  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PreShreddedPbixFiles> <UploadAndShred>d__9::<>t__builder
0xdb16  ldloc.s  9
0xdb18  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PreShreddedPbixFiles>::SetException(class [mscorlib]System.Exception)
0xdb1d  leave.s  loc_DB33
0xdb1f  ldarg.0
0xdb20  ldc.i4.s 0xFE
0xdb22  stfld    int32 <UploadAndShred>d__9::<>1__state
0xdb27  ldarg.0
0xdb28  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PreShreddedPbixFiles> <UploadAndShred>d__9::<>t__builder
0xdb2d  ldloc.1
0xdb2e  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PreShreddedPbixFiles>::SetResult(var<u1>)
0xdb33  ret
```
