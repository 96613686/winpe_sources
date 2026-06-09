# <DownloadCoreAsync>d__25::MoveNext

- ea: `0x7b2a0`
- end: `0x7b6cc`
- name: `<DownloadCoreAsync>d__25::MoveNext`
- size: `1068`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `installer_update`

## callees

- `0xee70`
- `0xffb0`
- `0x588d0`
- `0x58920`
- `0x589e0`
- `0x58a00`
- `0x58a40`
- `0x58d10`
- `0x58d60`
- `0x58f70`
- `0x58f90`
- `0x58fb0`
- `0x58fd0`
- `0x58ff0`
- `0x59370`
- `0x593c0`
- `0x7b2a0`

## string_xrefs

- `0x7b413`: `Downloading bootstrapper to cache: {0}`
- `0x7b4d1`: `Failed to download installer: {0}`
- `0x7b5b8`: `Failed to cache bootstrapper information: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x7b2a0  ldarg.0
0x7b2a1  ldfld    int32 <DownloadCoreAsync>d__25::<>1__state
0x7b2a6  stloc.0
0x7b2a7  ldarg.0
0x7b2a8  ldfld    class Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader <DownloadCoreAsync>d__25::<>4__this
0x7b2ad  stloc.1
0x7b2ae  ldloc.0
0x7b2af  switch   loc_7B39A, loc_7B402, loc_7B503
0x7b2c0  ldarg.0
0x7b2c1  ldloc.1
0x7b2c2  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::services
0x7b2c7  ldc.i4.0
0x7b2c8  call     T0x2B000001
0x7b2cd  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <DownloadCoreAsync>d__25::<logger>5__2
0x7b2d2  ldarg.0
0x7b2d3  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest <DownloadCoreAsync>d__25::manifest
0x7b2d8  dup
0x7b2d9  brtrue.s loc_7B2DF
0x7b2db  pop
0x7b2dc  ldnull
0x7b2dd  br.s     loc_7B2E4
0x7b2df  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::get_UpdateUri()
0x7b2e4  stloc.3
0x7b2e5  ldarg.0
0x7b2e6  ldfld    bool <DownloadCoreAsync>d__25::skipLayoutCheck
0x7b2eb  brtrue.s loc_7B31F
0x7b2ed  ldloc.3
0x7b2ee  brfalse.s loc_7B31F
0x7b2f0  ldloc.3
0x7b2f1  call     bool Microsoft.VisualStudio.Setup.Extensions::IsLayoutPath(class [System]System.Uri uri)
0x7b2f6  brfalse.s loc_7B31F
0x7b2f8  ldarg.0
0x7b2f9  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <DownloadCoreAsync>d__25::<logger>5__2
0x7b2fe  dup
0x7b2ff  brtrue.s loc_7B304
0x7b301  pop
0x7b302  br.s     loc_7B318
0x7b304  ldstr    aSkippingDownlo_2// "Skipping download of bootstrapper from "...
0x7b309  ldc.i4.1
0x7b30a  newarr   [mscorlib]System.Object
0x7b30f  dup
0x7b310  ldc.i4.0
0x7b311  ldloc.3
0x7b312  stelem.ref
0x7b313  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x7b318  ldnull
0x7b319  stloc.2
0x7b31a  leave    loc_7B6A9
0x7b31f  ldarg.0
0x7b320  ldarg.0
0x7b321  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest <DownloadCoreAsync>d__25::manifest
0x7b326  dup
0x7b327  brtrue.s loc_7B32D
0x7b329  pop
0x7b32a  ldnull
0x7b32b  br.s     loc_7B332
0x7b32d  call     class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IBootstrapperItem Microsoft.VisualStudio.Setup.Bootstrapper.Extensions::GetBootstrapper(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest)
0x7b332  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IBootstrapperItem <DownloadCoreAsync>d__25::<bootstrapperItem>5__3
0x7b337  ldarg.0
0x7b338  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IBootstrapperItem <DownloadCoreAsync>d__25::<bootstrapperItem>5__3
0x7b33d  brfalse  loc_7B67E
0x7b342  ldarg.0
0x7b343  ldloc.1
0x7b344  call     instance string Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::get_BootstrapperPath()
0x7b349  stfld    string <DownloadCoreAsync>d__25::<bootstrapperPath>5__4
0x7b34e  ldloc.1
0x7b34f  ldarg.0
0x7b350  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <DownloadCoreAsync>d__25::<logger>5__2
0x7b355  ldarg.0
0x7b356  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IBootstrapperItem <DownloadCoreAsync>d__25::<bootstrapperItem>5__3
0x7b35b  ldarg.0
0x7b35c  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <DownloadCoreAsync>d__25::cancellationToken
0x7b361  call     instance class [mscorlib]System.Threading.Tasks.Task`1<bool> Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::ShouldDownloadBootstrapperAsync(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IBootstrapperItem bootstrapperItem, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x7b366  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::GetAwaiter()
0x7b36b  stloc.s  4
0x7b36d  ldloca.s 4
0x7b36f  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::get_IsCompleted()
0x7b374  brtrue.s loc_7B3B7
0x7b376  ldarg.0
0x7b377  ldc.i4.0
0x7b378  dup
0x7b379  stloc.0
0x7b37a  stfld    int32 <DownloadCoreAsync>d__25::<>1__state
0x7b37f  ldarg.0
0x7b380  ldloc.s  4
0x7b382  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <DownloadCoreAsync>d__25::<>u__1
0x7b387  ldarg.0
0x7b388  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperInformation> <DownloadCoreAsync>d__25::<>t__builder
0x7b38d  ldloca.s 4
0x7b38f  ldarg.0
0x7b390  call     T0x2B00038C
0x7b395  leave    loc_7B6CB
0x7b39a  ldarg.0
0x7b39b  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <DownloadCoreAsync>d__25::<>u__1
0x7b3a0  stloc.s  4
0x7b3a2  ldarg.0
0x7b3a3  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <DownloadCoreAsync>d__25::<>u__1
0x7b3a8  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>
0x7b3ae  ldarg.0
0x7b3af  ldc.i4.m1
0x7b3b0  dup
0x7b3b1  stloc.0
0x7b3b2  stfld    int32 <DownloadCoreAsync>d__25::<>1__state
0x7b3b7  ldloca.s 4
0x7b3b9  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::GetResult()
0x7b3be  brfalse  loc_7B677
0x7b3c3  ldloc.1
0x7b3c4  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::get_FileSystem()
0x7b3c9  ldloc.1
0x7b3ca  call     instance string Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::get_RootDirectory()
0x7b3cf  ldloca.s 5
0x7b3d1  ldc.i4.0
0x7b3d2  ldc.i4.1
0x7b3d3  ldc.i4.2
0x7b3d4  ldc.i4   0x1F4
0x7b3d9  ldnull
0x7b3da  call     bool Microsoft.VisualStudio.Setup.Extensions::DeleteDirectoryWithRetry(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string path, [out] bool& rebootRequired, [opt] bool rebootOK, [opt] bool recursive, [opt] int32 retryCount, [opt] int32 retryDelay, [opt] class [mscorlib]System.Func`3<class [mscorlib]System.Exception, int32, bool> errorAction)
0x7b3df  pop
0x7b3e0  ldarg.0
0x7b3e1  ldarg.0
0x7b3e2  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IBootstrapperItem <DownloadCoreAsync>d__25::<bootstrapperItem>5__3
0x7b3e7  call     class [System]System.Uri Microsoft.VisualStudio.Setup.Bootstrapper.Extensions::GetBootstrapperUri(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IBootstrapperItem)
0x7b3ec  stfld    class [System]System.Uri <DownloadCoreAsync>d__25::<bootstrapperUri>5__5
0x7b3f1  ldarg.0
0x7b3f2  ldfld    class [System]System.Uri <DownloadCoreAsync>d__25::<bootstrapperUri>5__5
0x7b3f7  ldnull
0x7b3f8  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x7b3fd  brfalse  loc_7B670
0x7b402  nop
0x7b403  ldloc.0
0x7b404  ldc.i4.1
0x7b405  beq.s    loc_7B478
0x7b407  ldarg.0
0x7b408  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <DownloadCoreAsync>d__25::<logger>5__2
0x7b40d  dup
0x7b40e  brtrue.s loc_7B413
0x7b410  pop
0x7b411  br.s     loc_7B42C
0x7b413  ldstr    aDownloadingBoo// "Downloading bootstrapper to cache: {0}"
0x7b418  ldc.i4.1
0x7b419  newarr   [mscorlib]System.Object
0x7b41e  dup
0x7b41f  ldc.i4.0
0x7b420  ldarg.0
0x7b421  ldfld    string <DownloadCoreAsync>d__25::<bootstrapperPath>5__4
0x7b426  stelem.ref
0x7b427  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x7b42c  ldloc.1
0x7b42d  ldarg.0
0x7b42e  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <DownloadCoreAsync>d__25::<logger>5__2
0x7b433  ldarg.0
0x7b434  ldfld    class [System]System.Uri <DownloadCoreAsync>d__25::<bootstrapperUri>5__5
0x7b439  ldarg.0
0x7b43a  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <DownloadCoreAsync>d__25::cancellationToken
0x7b43f  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [System]System.Uri> Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::DownloadBootstrapperAsync(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger, class [System]System.Uri logger, valuetype [mscorlib]System.Threading.CancellationToken bootstrapperUri)
0x7b444  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [System]System.Uri>::GetAwaiter()
0x7b449  stloc.s  8
0x7b44b  ldloca.s 8
0x7b44d  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System]System.Uri>::get_IsCompleted()
0x7b452  brtrue.s loc_7B495
0x7b454  ldarg.0
0x7b455  ldc.i4.1
0x7b456  dup
0x7b457  stloc.0
0x7b458  stfld    int32 <DownloadCoreAsync>d__25::<>1__state
0x7b45d  ldarg.0
0x7b45e  ldloc.s  8
0x7b460  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System]System.Uri> <DownloadCoreAsync>d__25::<>u__2
0x7b465  ldarg.0
0x7b466  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperInformation> <DownloadCoreAsync>d__25::<>t__builder
0x7b46b  ldloca.s 8
0x7b46d  ldarg.0
0x7b46e  call     T0x2B00038D
0x7b473  leave    loc_7B6CB
0x7b478  ldarg.0
0x7b479  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System]System.Uri> <DownloadCoreAsync>d__25::<>u__2
0x7b47e  stloc.s  8
0x7b480  ldarg.0
0x7b481  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System]System.Uri> <DownloadCoreAsync>d__25::<>u__2
0x7b486  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System]System.Uri>
0x7b48c  ldarg.0
0x7b48d  ldc.i4.m1
0x7b48e  dup
0x7b48f  stloc.0
0x7b490  stfld    int32 <DownloadCoreAsync>d__25::<>1__state
0x7b495  ldloca.s 8
0x7b497  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System]System.Uri>::GetResult()
0x7b49c  stloc.s  7
0x7b49e  ldarg.0
0x7b49f  ldloc.s  7
0x7b4a1  stfld    class [System]System.Uri <DownloadCoreAsync>d__25::<installerUri>5__6
0x7b4a6  leave.s  loc_7B4F2
0x7b4a8  isinst   [mscorlib]System.Exception
0x7b4ad  dup
0x7b4ae  brtrue.s loc_7B4B4
0x7b4b0  pop
0x7b4b1  ldc.i4.0
0x7b4b2  br.s     loc_7B4C2
0x7b4b4  stloc.s  9
0x7b4b6  ldloc.1
0x7b4b7  ldfld    bool Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::canThrowExceptions
0x7b4bc  ldc.i4.0
0x7b4bd  ceq
0x7b4bf  ldc.i4.0
0x7b4c0  cgt.un
0x7b4c2  endfilter
0x7b4c4  pop
0x7b4c5  ldarg.0
0x7b4c6  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <DownloadCoreAsync>d__25::<logger>5__2
0x7b4cb  dup
0x7b4cc  brtrue.s loc_7B4D1
0x7b4ce  pop
0x7b4cf  br.s     loc_7B4EB
0x7b4d1  ldstr    aFailedToDownlo_11// "Failed to download installer: {0}"
0x7b4d6  ldc.i4.1
0x7b4d7  newarr   [mscorlib]System.Object
0x7b4dc  dup
0x7b4dd  ldc.i4.0
0x7b4de  ldloc.s  9
0x7b4e0  callvirt instance string [mscorlib]System.Exception::get_Message()
0x7b4e5  stelem.ref
0x7b4e6  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x7b4eb  ldnull
0x7b4ec  stloc.2
0x7b4ed  leave    loc_7B6A9
0x7b4f2  ldarg.0
0x7b4f3  ldfld    class [System]System.Uri <DownloadCoreAsync>d__25::<installerUri>5__6
0x7b4f8  ldnull
0x7b4f9  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x7b4fe  brfalse  loc_7B5D9
0x7b503  nop
0x7b504  ldloc.0
0x7b505  ldc.i4.2
0x7b506  beq.s    loc_7B569
0x7b508  ldarg.0
0x7b509  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <DownloadCoreAsync>d__25::<logger>5__2
0x7b50e  dup
0x7b50f  brtrue.s loc_7B514
0x7b511  pop
0x7b512  br.s     loc_7B523
0x7b514  ldstr    aCachingBootstr// "Caching bootstrapper information."
0x7b519  call     T0x2B000003
0x7b51e  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x7b523  ldloc.1
0x7b524  ldarg.0
0x7b525  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest <DownloadCoreAsync>d__25::manifest
0x7b52a  ldarg.0
0x7b52b  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <DownloadCoreAsync>d__25::cancellationToken
0x7b530  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::SaveChannelBootstrapperInfoAsync(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest manifest, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x7b535  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x7b53a  stloc.s  0xA
0x7b53c  ldloca.s 0xA
0x7b53e  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x7b543  brtrue.s loc_7B586
0x7b545  ldarg.0
0x7b546  ldc.i4.2
0x7b547  dup
0x7b548  stloc.0
0x7b549  stfld    int32 <DownloadCoreAsync>d__25::<>1__state
0x7b54e  ldarg.0
0x7b54f  ldloc.s  0xA
0x7b551  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <DownloadCoreAsync>d__25::<>u__3
0x7b556  ldarg.0
0x7b557  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperInformation> <DownloadCoreAsync>d__25::<>t__builder
0x7b55c  ldloca.s 0xA
0x7b55e  ldarg.0
0x7b55f  call     T0x2B00038E
0x7b564  leave    loc_7B6CB
0x7b569  ldarg.0
0x7b56a  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <DownloadCoreAsync>d__25::<>u__3
0x7b56f  stloc.s  0xA
0x7b571  ldarg.0
0x7b572  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <DownloadCoreAsync>d__25::<>u__3
0x7b577  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x7b57d  ldarg.0
0x7b57e  ldc.i4.m1
0x7b57f  dup
0x7b580  stloc.0
0x7b581  stfld    int32 <DownloadCoreAsync>d__25::<>1__state
0x7b586  ldloca.s 0xA
0x7b588  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x7b58d  leave.s  loc_7B5D9
0x7b58f  isinst   [mscorlib]System.Exception
0x7b594  dup
0x7b595  brtrue.s loc_7B59B
0x7b597  pop
0x7b598  ldc.i4.0
0x7b599  br.s     loc_7B5A9
0x7b59b  stloc.s  0xB
0x7b59d  ldloc.1
0x7b59e  ldfld    bool Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::canThrowExceptions
0x7b5a3  ldc.i4.0
0x7b5a4  ceq
0x7b5a6  ldc.i4.0
0x7b5a7  cgt.un
0x7b5a9  endfilter
0x7b5ab  pop
0x7b5ac  ldarg.0
0x7b5ad  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <DownloadCoreAsync>d__25::<logger>5__2
0x7b5b2  dup
  ... truncated ...
```
