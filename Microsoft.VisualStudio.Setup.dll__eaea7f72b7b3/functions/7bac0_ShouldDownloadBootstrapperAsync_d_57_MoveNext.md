# <ShouldDownloadBootstrapperAsync>d__57::MoveNext

- ea: `0x7bac0`
- end: `0x7bd07`
- name: `<ShouldDownloadBootstrapperAsync>d__57::MoveNext`
- size: `583`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x58920`
- `0x589e0`
- `0x58a00`
- `0x58a20`
- `0x58c20`
- `0x58db0`
- `0x7bac0`

## string_xrefs

- `0x7bb3d`: `No bootstrapper cached previously: {0}`
- `0x7bcbc`: `No bootstrapper cached previously: {0}`
- `0x7bbb7`: `Installer is not signed by Microsoft at {0}`
- `0x7bc7c`: `{0} bootstrapper cached: {1}, version: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x7bac0  ldarg.0
0x7bac1  ldfld    int32 <ShouldDownloadBootstrapperAsync>d__57::<>1__state
0x7bac6  stloc.0
0x7bac7  ldarg.0
0x7bac8  ldfld    class Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader <ShouldDownloadBootstrapperAsync>d__57::<>4__this
0x7bacd  stloc.1
0x7bace  ldloc.0
0x7bacf  brfalse  loc_7BC15
0x7bad4  ldloc.1
0x7bad5  call     instance bool Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::get_IsMeteredConnection()
0x7bada  brfalse.s loc_7BB06
0x7badc  ldloc.1
0x7badd  ldfld    bool Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::downloadOverMeteredConnections
0x7bae2  brtrue.s loc_7BB06
0x7bae4  ldarg.0
0x7bae5  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <ShouldDownloadBootstrapperAsync>d__57::logger
0x7baea  dup
0x7baeb  brtrue.s loc_7BAF0
0x7baed  pop
0x7baee  br.s     loc_7BAFF
0x7baf0  ldstr    aSkippingDownlo_3// "Skipping download of bootstrapper on me"...
0x7baf5  call     T0x2B000003
0x7bafa  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x7baff  ldc.i4.0
0x7bb00  stloc.2
0x7bb01  leave    loc_7BCF2
0x7bb06  ldloc.1
0x7bb07  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::get_FileSystem()
0x7bb0c  ldloc.1
0x7bb0d  call     instance string Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::get_InstallerPath()
0x7bb12  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x7bb17  brfalse.s loc_7BB2C
0x7bb19  ldloc.1
0x7bb1a  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::get_FileSystem()
0x7bb1f  ldloc.1
0x7bb20  call     instance string Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::get_BootstrapperPath()
0x7bb25  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x7bb2a  brtrue.s loc_7BB5B
0x7bb2c  ldc.i4.1
0x7bb2d  stloc.3
0x7bb2e  ldarg.0
0x7bb2f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <ShouldDownloadBootstrapperAsync>d__57::logger
0x7bb34  dup
0x7bb35  brtrue.s loc_7BB3D
0x7bb37  pop
0x7bb38  br       loc_7BCD5
0x7bb3d  ldstr    aNoBootstrapper// "No bootstrapper cached previously: {0}"
0x7bb42  ldc.i4.1
0x7bb43  newarr   [mscorlib]System.Object
0x7bb48  dup
0x7bb49  ldc.i4.0
0x7bb4a  ldloc.1
0x7bb4b  call     instance string Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::get_BootstrapperPath()
0x7bb50  stelem.ref
0x7bb51  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x7bb56  br       loc_7BCD5
0x7bb5b  ldloc.1
0x7bb5c  ldloc.1
0x7bb5d  call     instance string Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::get_BootstrapperPath()
0x7bb62  call     instance bool Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::IsMicrosoftSigned(string path)
0x7bb67  brtrue.s loc_7BB98
0x7bb69  ldc.i4.1
0x7bb6a  stloc.3
0x7bb6b  ldarg.0
0x7bb6c  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <ShouldDownloadBootstrapperAsync>d__57::logger
0x7bb71  dup
0x7bb72  brtrue.s loc_7BB7A
0x7bb74  pop
0x7bb75  br       loc_7BCD5
0x7bb7a  ldstr    aBootstrapperIs// "Bootstrapper is not signed by Microsoft"...
0x7bb7f  ldc.i4.1
0x7bb80  newarr   [mscorlib]System.Object
0x7bb85  dup
0x7bb86  ldc.i4.0
0x7bb87  ldloc.1
0x7bb88  call     instance string Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::get_BootstrapperPath()
0x7bb8d  stelem.ref
0x7bb8e  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x7bb93  br       loc_7BCD5
0x7bb98  ldloc.1
0x7bb99  ldloc.1
0x7bb9a  call     instance string Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::get_InstallerPath()
0x7bb9f  call     instance bool Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::IsMicrosoftSigned(string path)
0x7bba4  brtrue.s loc_7BBD5
0x7bba6  ldc.i4.1
0x7bba7  stloc.3
0x7bba8  ldarg.0
0x7bba9  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <ShouldDownloadBootstrapperAsync>d__57::logger
0x7bbae  dup
0x7bbaf  brtrue.s loc_7BBB7
0x7bbb1  pop
0x7bbb2  br       loc_7BCD5
0x7bbb7  ldstr    aInstallerIsNot// "Installer is not signed by Microsoft at"...
0x7bbbc  ldc.i4.1
0x7bbbd  newarr   [mscorlib]System.Object
0x7bbc2  dup
0x7bbc3  ldc.i4.0
0x7bbc4  ldloc.1
0x7bbc5  call     instance string Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::get_InstallerPath()
0x7bbca  stelem.ref
0x7bbcb  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x7bbd0  br       loc_7BCD5
0x7bbd5  ldloc.1
0x7bbd6  ldarg.0
0x7bbd7  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <ShouldDownloadBootstrapperAsync>d__57::cancellationToken
0x7bbdc  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Version> Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::GetPreviousBootstrapperVersionAsync(valuetype [mscorlib]System.Threading.CancellationToken)
0x7bbe1  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Version>::GetAwaiter()
0x7bbe6  stloc.s  5
0x7bbe8  ldloca.s 5
0x7bbea  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Version>::get_IsCompleted()
0x7bbef  brtrue.s loc_7BC32
0x7bbf1  ldarg.0
0x7bbf2  ldc.i4.0
0x7bbf3  dup
0x7bbf4  stloc.0
0x7bbf5  stfld    int32 <ShouldDownloadBootstrapperAsync>d__57::<>1__state
0x7bbfa  ldarg.0
0x7bbfb  ldloc.s  5
0x7bbfd  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Version> <ShouldDownloadBootstrapperAsync>d__57::<>u__1
0x7bc02  ldarg.0
0x7bc03  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <ShouldDownloadBootstrapperAsync>d__57::<>t__builder
0x7bc08  ldloca.s 5
0x7bc0a  ldarg.0
0x7bc0b  call     T0x2B000393
0x7bc10  leave    loc_7BD06
0x7bc15  ldarg.0
0x7bc16  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Version> <ShouldDownloadBootstrapperAsync>d__57::<>u__1
0x7bc1b  stloc.s  5
0x7bc1d  ldarg.0
0x7bc1e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Version> <ShouldDownloadBootstrapperAsync>d__57::<>u__1
0x7bc23  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Version>
0x7bc29  ldarg.0
0x7bc2a  ldc.i4.m1
0x7bc2b  dup
0x7bc2c  stloc.0
0x7bc2d  stfld    int32 <ShouldDownloadBootstrapperAsync>d__57::<>1__state
0x7bc32  ldloca.s 5
0x7bc34  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Version>::GetResult()
0x7bc39  stloc.s  4
0x7bc3b  ldloc.s  4
0x7bc3d  ldnull
0x7bc3e  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x7bc43  brfalse.s loc_7BCAE
0x7bc45  ldarg.0
0x7bc46  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IBootstrapperItem <ShouldDownloadBootstrapperAsync>d__57::bootstrapperItem
0x7bc4b  callvirt instance class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::get_Version()
0x7bc50  stloc.s  6
0x7bc52  ldloc.s  4
0x7bc54  brfalse.s loc_7BC6E
0x7bc56  ldloc.s  6
0x7bc58  ldnull
0x7bc59  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x7bc5e  brfalse.s loc_7BC6B
0x7bc60  ldloc.s  6
0x7bc62  ldloc.s  4
0x7bc64  call     bool [mscorlib]System.Version::op_GreaterThan(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x7bc69  br.s     loc_7BC6F
0x7bc6b  ldc.i4.0
0x7bc6c  br.s     loc_7BC6F
0x7bc6e  ldc.i4.1
0x7bc6f  stloc.3
0x7bc70  ldarg.0
0x7bc71  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <ShouldDownloadBootstrapperAsync>d__57::logger
0x7bc76  dup
0x7bc77  brtrue.s loc_7BC7C
0x7bc79  pop
0x7bc7a  br.s     loc_7BCD5
0x7bc7c  ldstr    a0BootstrapperC// "{0} bootstrapper cached: {1}, version: "...
0x7bc81  ldc.i4.3
0x7bc82  newarr   [mscorlib]System.Object
0x7bc87  dup
0x7bc88  ldc.i4.0
0x7bc89  ldloc.3
0x7bc8a  brtrue.s loc_7BC93
0x7bc8c  ldstr    aNewer// "Newer"
0x7bc91  br.s     loc_7BC98
0x7bc93  ldstr    aOlder// "Older"
0x7bc98  stelem.ref
0x7bc99  dup
0x7bc9a  ldc.i4.1
0x7bc9b  ldloc.1
0x7bc9c  call     instance string Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::get_BootstrapperPath()
0x7bca1  stelem.ref
0x7bca2  dup
0x7bca3  ldc.i4.2
0x7bca4  ldloc.s  4
0x7bca6  stelem.ref
0x7bca7  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x7bcac  br.s     loc_7BCD5
0x7bcae  ldc.i4.1
0x7bcaf  stloc.3
0x7bcb0  ldarg.0
0x7bcb1  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <ShouldDownloadBootstrapperAsync>d__57::logger
0x7bcb6  dup
0x7bcb7  brtrue.s loc_7BCBC
0x7bcb9  pop
0x7bcba  br.s     loc_7BCD5
0x7bcbc  ldstr    aNoBootstrapper// "No bootstrapper cached previously: {0}"
0x7bcc1  ldc.i4.1
0x7bcc2  newarr   [mscorlib]System.Object
0x7bcc7  dup
0x7bcc8  ldc.i4.0
0x7bcc9  ldloc.1
0x7bcca  call     instance string Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::get_BootstrapperPath()
0x7bccf  stelem.ref
0x7bcd0  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x7bcd5  ldloc.3
0x7bcd6  stloc.2
0x7bcd7  leave.s  loc_7BCF2
0x7bcd9  stloc.s  7
0x7bcdb  ldarg.0
0x7bcdc  ldc.i4.s 0xFE
0x7bcde  stfld    int32 <ShouldDownloadBootstrapperAsync>d__57::<>1__state
0x7bce3  ldarg.0
0x7bce4  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <ShouldDownloadBootstrapperAsync>d__57::<>t__builder
0x7bce9  ldloc.s  7
0x7bceb  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool>::SetException(class [mscorlib]System.Exception)
0x7bcf0  leave.s  loc_7BD06
0x7bcf2  ldarg.0
0x7bcf3  ldc.i4.s 0xFE
0x7bcf5  stfld    int32 <ShouldDownloadBootstrapperAsync>d__57::<>1__state
0x7bcfa  ldarg.0
0x7bcfb  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <ShouldDownloadBootstrapperAsync>d__57::<>t__builder
0x7bd00  ldloc.2
0x7bd01  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool>::SetResult(var<u1>)
0x7bd06  ret
```
