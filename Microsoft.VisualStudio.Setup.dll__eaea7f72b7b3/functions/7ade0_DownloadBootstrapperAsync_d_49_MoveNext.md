# <DownloadBootstrapperAsync>d__49::MoveNext

- ea: `0x7ade0`
- end: `0x7b273`
- name: `<DownloadBootstrapperAsync>d__49::MoveNext`
- size: `1171`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0xffb0`
- `0x1deb0`
- `0x58920`
- `0x58a90`
- `0x58ae0`
- `0x58b60`
- `0x58c60`
- `0x58c80`
- `0x7ade0`

## string_xrefs

- `0x7ae29`: `Creating temporary download cache: {0}`
- `0x7af41`: `Downloaded temporary bootstrapper from: {0}`
- `0x7af86`: `Failed to get the Installer URI.`
- `0x7b051`: `Downloaded Installer from: {0}`
- `0x7b10b`: `Failed to move files from temp bootstrapperPath`
- `0x7b213`: `Failed to delete temporary download cache: {0}, reboot required: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x7ade0  ldarg.0
0x7ade1  ldfld    int32 <DownloadBootstrapperAsync>d__49::<>1__state
0x7ade6  stloc.0
0x7ade7  ldarg.0
0x7ade8  ldfld    class Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader <DownloadBootstrapperAsync>d__49::<>4__this
0x7aded  stloc.1
0x7adee  ldloc.0
0x7adef  ldc.i4.2
0x7adf0  ble.un   loc_7AE79
0x7adf5  ldarg.0
0x7adf6  ldloc.1
0x7adf7  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::get_FileSystem()
0x7adfc  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::get_TemporaryDirectory()
0x7ae01  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x7ae06  stloc.3
0x7ae07  ldloca.s 3
0x7ae09  ldstr    aN_1// "n"
0x7ae0e  call     instance string [mscorlib]System.Guid::ToString(string)
0x7ae13  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x7ae18  stfld    string <DownloadBootstrapperAsync>d__49::<tempDirectory>5__2
0x7ae1d  ldarg.0
0x7ae1e  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <DownloadBootstrapperAsync>d__49::logger
0x7ae23  dup
0x7ae24  brtrue.s loc_7AE29
0x7ae26  pop
0x7ae27  br.s     loc_7AE42
0x7ae29  ldstr    aCreatingTempor// "Creating temporary download cache: {0}"
0x7ae2e  ldc.i4.1
0x7ae2f  newarr   [mscorlib]System.Object
0x7ae34  dup
0x7ae35  ldc.i4.0
0x7ae36  ldarg.0
0x7ae37  ldfld    string <DownloadBootstrapperAsync>d__49::<tempDirectory>5__2
0x7ae3c  stelem.ref
0x7ae3d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x7ae42  ldloc.1
0x7ae43  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::get_FileSystem()
0x7ae48  ldarg.0
0x7ae49  ldfld    string <DownloadBootstrapperAsync>d__49::<tempDirectory>5__2
0x7ae4e  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::CreateDirectory(string)
0x7ae53  ldarg.0
0x7ae54  ldloc.1
0x7ae55  ldflda   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) int32 Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::operationId
0x7ae5a  call     int32 [mscorlib]System.Threading.Interlocked::Increment(int32&)
0x7ae5f  stfld    int32 <DownloadBootstrapperAsync>d__49::<operationId>5__3
0x7ae64  ldloc.1
0x7ae65  ldarg.0
0x7ae66  ldfld    int32 <DownloadBootstrapperAsync>d__49::<operationId>5__3
0x7ae6b  ldc.r8   0.0
0x7ae74  call     instance void Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::OnProgress(int32 operationId, float64 progress)
0x7ae79  nop
0x7ae7a  ldloc.0
0x7ae7b  switch   loc_7AF0C, loc_7B01C, loc_7B0B0
0x7ae8c  ldarg.0
0x7ae8d  ldarg.0
0x7ae8e  ldfld    string <DownloadBootstrapperAsync>d__49::<tempDirectory>5__2
0x7ae93  ldsfld   string Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::OfflineBootstrapperName
0x7ae98  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x7ae9d  stfld    string <DownloadBootstrapperAsync>d__49::<tempBootstrapperPath>5__4
0x7aea2  ldloc.1
0x7aea3  ldarg.0
0x7aea4  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <DownloadBootstrapperAsync>d__49::logger
0x7aea9  ldarg.0
0x7aeaa  ldfld    class [System]System.Uri <DownloadBootstrapperAsync>d__49::bootstrapperUri
0x7aeaf  ldarg.0
0x7aeb0  ldfld    string <DownloadBootstrapperAsync>d__49::<tempBootstrapperPath>5__4
0x7aeb5  ldarg.0
0x7aeb6  ldfld    int32 <DownloadBootstrapperAsync>d__49::<operationId>5__3
0x7aebb  ldc.r8   0.02
0x7aec4  ldc.r8   0.0
0x7aecd  ldarg.0
0x7aece  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <DownloadBootstrapperAsync>d__49::cancellationToken
0x7aed3  call     instance class [mscorlib]System.Threading.Tasks.Task`1<bool> Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::DownloadAsync(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger, class [System]System.Uri uri, string path, int32 operationId, float64 weight, float64 offset, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x7aed8  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::GetAwaiter()
0x7aedd  stloc.s  4
0x7aedf  ldloca.s 4
0x7aee1  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::get_IsCompleted()
0x7aee6  brtrue.s loc_7AF29
0x7aee8  ldarg.0
0x7aee9  ldc.i4.0
0x7aeea  dup
0x7aeeb  stloc.0
0x7aeec  stfld    int32 <DownloadBootstrapperAsync>d__49::<>1__state
0x7aef1  ldarg.0
0x7aef2  ldloc.s  4
0x7aef4  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <DownloadBootstrapperAsync>d__49::<>u__1
0x7aef9  ldarg.0
0x7aefa  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System]System.Uri> <DownloadBootstrapperAsync>d__49::<>t__builder
0x7aeff  ldloca.s 4
0x7af01  ldarg.0
0x7af02  call     T0x2B00038B
0x7af07  leave    loc_7B272
0x7af0c  ldarg.0
0x7af0d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <DownloadBootstrapperAsync>d__49::<>u__1
0x7af12  stloc.s  4
0x7af14  ldarg.0
0x7af15  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <DownloadBootstrapperAsync>d__49::<>u__1
0x7af1a  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>
0x7af20  ldarg.0
0x7af21  ldc.i4.m1
0x7af22  dup
0x7af23  stloc.0
0x7af24  stfld    int32 <DownloadBootstrapperAsync>d__49::<>1__state
0x7af29  ldloca.s 4
0x7af2b  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::GetResult()
0x7af30  brfalse  loc_7B19E
0x7af35  ldarg.0
0x7af36  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <DownloadBootstrapperAsync>d__49::logger
0x7af3b  dup
0x7af3c  brtrue.s loc_7AF41
0x7af3e  pop
0x7af3f  br.s     loc_7AF5A
0x7af41  ldstr    aDownloadedTemp// "Downloaded temporary bootstrapper from:"...
0x7af46  ldc.i4.1
0x7af47  newarr   [mscorlib]System.Object
0x7af4c  dup
0x7af4d  ldc.i4.0
0x7af4e  ldarg.0
0x7af4f  ldfld    class [System]System.Uri <DownloadBootstrapperAsync>d__49::bootstrapperUri
0x7af54  stelem.ref
0x7af55  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x7af5a  ldarg.0
0x7af5b  ldloc.1
0x7af5c  ldarg.0
0x7af5d  ldfld    class [System]System.Uri <DownloadBootstrapperAsync>d__49::bootstrapperUri
0x7af62  ldarg.0
0x7af63  ldfld    string <DownloadBootstrapperAsync>d__49::<tempBootstrapperPath>5__4
0x7af68  call     instance class [System]System.Uri Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::GetInstallerUri(class [System]System.Uri, string bootstrapperUri)
0x7af6d  stfld    class [System]System.Uri <DownloadBootstrapperAsync>d__49::<installerUri>5__5
0x7af72  ldarg.0
0x7af73  ldfld    class [System]System.Uri <DownloadBootstrapperAsync>d__49::<installerUri>5__5
0x7af78  brtrue.s loc_7AF9C
0x7af7a  ldarg.0
0x7af7b  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <DownloadBootstrapperAsync>d__49::logger
0x7af80  dup
0x7af81  brtrue.s loc_7AF86
0x7af83  pop
0x7af84  br.s     loc_7AF95
0x7af86  ldstr    aFailedToGetThe_8// "Failed to get the Installer URI."
0x7af8b  call     T0x2B000003
0x7af90  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x7af95  ldnull
0x7af96  stloc.2
0x7af97  leave    loc_7B257
0x7af9c  ldarg.0
0x7af9d  ldarg.0
0x7af9e  ldfld    string <DownloadBootstrapperAsync>d__49::<tempDirectory>5__2
0x7afa3  ldsfld   string Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::OfflineInstallerName
0x7afa8  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x7afad  stfld    string <DownloadBootstrapperAsync>d__49::<tempInstallerPath>5__6
0x7afb2  ldloc.1
0x7afb3  ldarg.0
0x7afb4  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <DownloadBootstrapperAsync>d__49::logger
0x7afb9  ldarg.0
0x7afba  ldfld    class [System]System.Uri <DownloadBootstrapperAsync>d__49::<installerUri>5__5
0x7afbf  ldarg.0
0x7afc0  ldfld    string <DownloadBootstrapperAsync>d__49::<tempInstallerPath>5__6
0x7afc5  ldarg.0
0x7afc6  ldfld    int32 <DownloadBootstrapperAsync>d__49::<operationId>5__3
0x7afcb  ldc.r8   0.98
0x7afd4  ldc.r8   0.02
0x7afdd  ldarg.0
0x7afde  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <DownloadBootstrapperAsync>d__49::cancellationToken
0x7afe3  call     instance class [mscorlib]System.Threading.Tasks.Task`1<bool> Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::DownloadAsync(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger, class [System]System.Uri uri, string path, int32 operationId, float64 weight, float64 offset, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x7afe8  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::GetAwaiter()
0x7afed  stloc.s  4
0x7afef  ldloca.s 4
0x7aff1  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::get_IsCompleted()
0x7aff6  brtrue.s loc_7B039
0x7aff8  ldarg.0
0x7aff9  ldc.i4.1
0x7affa  dup
0x7affb  stloc.0
0x7affc  stfld    int32 <DownloadBootstrapperAsync>d__49::<>1__state
0x7b001  ldarg.0
0x7b002  ldloc.s  4
0x7b004  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <DownloadBootstrapperAsync>d__49::<>u__1
0x7b009  ldarg.0
0x7b00a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System]System.Uri> <DownloadBootstrapperAsync>d__49::<>t__builder
0x7b00f  ldloca.s 4
0x7b011  ldarg.0
0x7b012  call     T0x2B00038B
0x7b017  leave    loc_7B272
0x7b01c  ldarg.0
0x7b01d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <DownloadBootstrapperAsync>d__49::<>u__1
0x7b022  stloc.s  4
0x7b024  ldarg.0
0x7b025  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <DownloadBootstrapperAsync>d__49::<>u__1
0x7b02a  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>
0x7b030  ldarg.0
0x7b031  ldc.i4.m1
0x7b032  dup
0x7b033  stloc.0
0x7b034  stfld    int32 <DownloadBootstrapperAsync>d__49::<>1__state
0x7b039  ldloca.s 4
0x7b03b  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::GetResult()
0x7b040  brfalse  loc_7B169
0x7b045  ldarg.0
0x7b046  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <DownloadBootstrapperAsync>d__49::logger
0x7b04b  dup
0x7b04c  brtrue.s loc_7B051
0x7b04e  pop
0x7b04f  br.s     loc_7B06A
0x7b051  ldstr    aDownloadedInst// "Downloaded Installer from: {0}"
0x7b056  ldc.i4.1
0x7b057  newarr   [mscorlib]System.Object
0x7b05c  dup
0x7b05d  ldc.i4.0
0x7b05e  ldarg.0
0x7b05f  ldfld    class [System]System.Uri <DownloadBootstrapperAsync>d__49::<installerUri>5__5
0x7b064  stelem.ref
0x7b065  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x7b06a  ldloc.1
0x7b06b  ldarg.0
0x7b06c  ldfld    string <DownloadBootstrapperAsync>d__49::<tempInstallerPath>5__6
0x7b071  ldarg.0
0x7b072  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <DownloadBootstrapperAsync>d__49::cancellationToken
0x7b077  call     instance class [mscorlib]System.Threading.Tasks.Task`1<bool> Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::IsInstallerVersionExpectedAsync(string tempInstallerPath, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x7b07c  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::GetAwaiter()
0x7b081  stloc.s  4
0x7b083  ldloca.s 4
0x7b085  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::get_IsCompleted()
0x7b08a  brtrue.s loc_7B0CD
0x7b08c  ldarg.0
0x7b08d  ldc.i4.2
0x7b08e  dup
0x7b08f  stloc.0
0x7b090  stfld    int32 <DownloadBootstrapperAsync>d__49::<>1__state
0x7b095  ldarg.0
0x7b096  ldloc.s  4
0x7b098  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <DownloadBootstrapperAsync>d__49::<>u__1
0x7b09d  ldarg.0
0x7b09e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System]System.Uri> <DownloadBootstrapperAsync>d__49::<>t__builder
0x7b0a3  ldloca.s 4
0x7b0a5  ldarg.0
0x7b0a6  call     T0x2B00038B
0x7b0ab  leave    loc_7B272
0x7b0b0  ldarg.0
0x7b0b1  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <DownloadBootstrapperAsync>d__49::<>u__1
0x7b0b6  stloc.s  4
0x7b0b8  ldarg.0
0x7b0b9  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <DownloadBootstrapperAsync>d__49::<>u__1
0x7b0be  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>
0x7b0c4  ldarg.0
0x7b0c5  ldc.i4.m1
0x7b0c6  dup
0x7b0c7  stloc.0
0x7b0c8  stfld    int32 <DownloadBootstrapperAsync>d__49::<>1__state
0x7b0cd  ldloca.s 4
0x7b0cf  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::GetResult()
0x7b0d4  brfalse.s loc_7B11C
0x7b0d6  ldloc.1
0x7b0d7  ldarg.0
0x7b0d8  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <DownloadBootstrapperAsync>d__49::logger
0x7b0dd  ldarg.0
0x7b0de  ldfld    string <DownloadBootstrapperAsync>d__49::<tempBootstrapperPath>5__4
0x7b0e3  ldarg.0
0x7b0e4  ldfld    string <DownloadBootstrapperAsync>d__49::<tempInstallerPath>5__6
0x7b0e9  call     instance bool Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::MoveFiles(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger, string tempBootstrapperPath, string tempInstallerPath)
0x7b0ee  brfalse.s loc_7B0FC
0x7b0f0  ldarg.0
0x7b0f1  ldfld    class [System]System.Uri <DownloadBootstrapperAsync>d__49::<installerUri>5__5
0x7b0f6  stloc.2
0x7b0f7  leave    loc_7B257
0x7b0fc  ldarg.0
0x7b0fd  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <DownloadBootstrapperAsync>d__49::logger
0x7b102  dup
0x7b103  brtrue.s loc_7B10B
0x7b105  pop
0x7b106  br       loc_7B18E
0x7b10b  ldstr    aFailedToMoveFi_0// "Failed to move files from temp bootstra"...
0x7b110  call     T0x2B000003
0x7b115  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x7b11a  br.s     loc_7B18E
0x7b11c  ldloc.1
0x7b11d  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::services
0x7b122  ldarg.0
0x7b123  ldfld    string <DownloadBootstrapperAsync>d__49::<tempInstallerPath>5__6
0x7b128  ldarg.0
0x7b129  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <DownloadBootstrapperAsync>d__49::cancellationToken
0x7b12e  call     class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Client::GetClientPackageVersionFromOpc(class [mscorlib]System.IServiceProvider, string services, valuetype [mscorlib]System.Threading.CancellationToken opcPath)
0x7b133  stloc.s  5
0x7b135  ldstr    aTheDownloadedI// "The downloaded instaler was not the exp"...
0x7b13a  ldloc.s  5
0x7b13c  ldloc.1
0x7b13d  ldfld    class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Bootstrapper.BootstrapperDownloader::clientVersion
0x7b142  call     string [mscorlib]System.String::Format(string, object, object)
0x7b147  stloc.s  6
0x7b149  ldarg.0
0x7b14a  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <DownloadBootstrapperAsync>d__49::logger
0x7b14f  dup
0x7b150  brtrue.s loc_7B155
0x7b152  pop
0x7b153  br.s     loc_7B161
0x7b155  ldloc.s  6
0x7b157  call     T0x2B000003
0x7b15c  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x7b161  ldloc.s  6
0x7b163  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7b168  throw
  ... truncated ...
```
