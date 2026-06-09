# Microsoft.VisualStudio.Setup.BackgroundDownloader::LaunchChildAndWait

- ea: `0xdf0`
- end: `0x1070`
- name: `Microsoft.VisualStudio.Setup.BackgroundDownloader::LaunchChildAndWait`
- size: `640`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x3c10`

## callees

- `0xdf0`
- `0x1280`
- `0x1330`
- `0x18d0`
- `0x18e0`
- `0x1900`
- `0x1910`
- `0x1c10`
- `0x1cd0`
- `0x2950`

## string_xrefs

- `0xe5d`: `No Instances installed to update`
- `0xe7f`: `\Installer\`
- `0xeac`: `\Installer\`
- `0xe91`: `Unable to find '\Installer\' in '`
- `0xf35`: ` --child --activityId {0} --childClientVersion {1} --childClientInstallerVersion {2}`
- `0xfb8`: `Waiting for setup process to complete...`

## pseudocode

```c

```

## disassembly

```asm
0xdf0  ldarg.0
0xdf1  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Logger()
0xdf6  ldstr    aLaunchChildAnd// "Launch child and wait"
0xdfb  newobj   instance void Microsoft.VisualStudio.Setup.OperationLogger::.ctor(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger, string text)
0xe00  stloc.0
0xe01  ldarga.s 3
0xe03  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0xe08  ldarg.0
0xe09  ldarg.1
0xe0a  ldarg.2
0xe0b  ldarg.3
0xe0c  call     instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperInformation Microsoft.VisualStudio.Setup.BackgroundDownloader::DownloadUpdatedBootstrapper(string engineUrl, class [mscorlib]System.Version clientVersion, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0xe11  stloc.1
0xe12  ldarg.0
0xe13  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_FileSystem()
0xe18  ldc.i4.2
0xe19  ldc.i4   0x1F4
0xe1e  call     string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extensions::CreateTemporaryFolderInTempWithRetry(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem, int32, int32)
0xe23  stloc.2
0xe24  ldarg.0
0xe25  ldloc.1
0xe26  ldloc.2
0xe27  ldarg.3
0xe28  call     instance void Microsoft.VisualStudio.Setup.BackgroundDownloader::ExtractOPC(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperInformation bootstrapperInfo, string destinationFolder, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0xe2d  ldtoken  Microsoft.VisualStudio.Setup.BackgroundDownloader
0xe32  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe37  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0xe3c  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0xe41  call     string [mscorlib]System.IO.Path::GetFileName(string)
0xe46  stloc.3
0xe47  ldnull
0xe48  stloc.s  4
0xe4a  ldarg.0
0xe4b  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Cache.IQuery Microsoft.VisualStudio.Setup.BackgroundDownloader::query
0xe50  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance> [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Cache.IQuery::GetAllInstances()
0xe55  dup
0xe56  call     T0x2B000008
0xe5b  brfalse.s loc_E68
0xe5d  ldstr    aNoInstancesIns// "No Instances installed to update"
0xe62  newobj   instance void [mscorlib]System.OperationCanceledException::.ctor(string)
0xe67  throw
0xe68  call     T0x2B000009
0xe6d  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_EnginePath()
0xe72  stloc.s  5
0xe74  ldloc.s  5
0xe76  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xe7b  brtrue.s loc_EBE
0xe7d  ldloc.s  5
0xe7f  ldstr    aInstaller// "\\Installer\\"
0xe84  ldc.i4.5
0xe85  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0xe8a  stloc.s  7
0xe8c  ldloc.s  7
0xe8e  ldc.i4.0
0xe8f  bge.s    loc_EA8
0xe91  ldstr    aUnableToFindIn// "Unable to find '\\Installer\\' in '"
0xe96  ldloc.s  5
0xe98  ldstr    asc_7126// "'"
0xe9d  call     string [mscorlib]System.String::Concat(string, string, string)
0xea2  newobj   instance void [mscorlib]System.OperationCanceledException::.ctor(string)
0xea7  throw
0xea8  ldloc.s  5
0xeaa  ldloc.s  7
0xeac  ldstr    aInstaller// "\\Installer\\"
0xeb1  call     instance int32 [mscorlib]System.String::get_Length()
0xeb6  add
0xeb7  callvirt instance string [mscorlib]System.String::Substring(int32)
0xebc  stloc.s  4
0xebe  ldloc.2
0xebf  ldloc.s  4
0xec1  ldloc.3
0xec2  call     string [mscorlib]System.IO.Path::Combine(string, string, string)
0xec7  stloc.s  6
0xec9  ldarg.0
0xeca  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_FileSystem()
0xecf  ldloc.s  6
0xed1  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0xed6  brfalse  loc_1011
0xedb  ldarga.s 3
0xedd  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0xee2  ldarg.0
0xee3  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Services()
0xee8  ldloc.2
0xee9  call     class [mscorlib]System.Version [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Client::GetClientPackageVersion(class [mscorlib]System.IServiceProvider, string)
0xeee  stloc.s  8
0xef0  ldarg.0
0xef1  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Services()
0xef6  ldloc.2
0xef7  call     class [mscorlib]System.Version [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Client::GetInstallerVersion(class [mscorlib]System.IServiceProvider, string)
0xefc  stloc.s  9
0xefe  ldarg.0
0xeff  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService Microsoft.VisualStudio.Setup.BackgroundDownloader::processService
0xf04  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService::CreateProcess()
0xf09  stloc.s  0xA
0xf0b  ldloc.s  0xA
0xf0d  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess::get_StartInfo()
0xf12  ldloc.s  6
0xf14  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo::set_FileName(string)
0xf19  ldloc.s  0xA
0xf1b  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess::get_StartInfo()
0xf20  ldstr    asc_712A// " "
0xf25  ldarg.0
0xf26  call     instance class Microsoft.VisualStudio.Setup.CommandLine Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_CommandLine()
0xf2b  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyList`1<string> Microsoft.VisualStudio.Setup.CommandLine::get_Args()
0xf30  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0xf35  ldstr    aChildActivityi// " --child --activityId {0} --childClient"...
0xf3a  ldarg.0
0xf3b  call     instance class Microsoft.VisualStudio.Setup.CommandLine Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_CommandLine()
0xf40  callvirt instance string Microsoft.VisualStudio.Setup.CommandLine::get_ActivityId()
0xf45  ldloc.s  8
0xf47  ldloc.s  9
0xf49  call     string [mscorlib]System.String::Format(string, object, object, object)
0xf4e  call     string [mscorlib]System.String::Concat(string, string)
0xf53  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo::set_Arguments(string)
0xf58  ldloc.s  0xA
0xf5a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess::get_StartInfo()
0xf5f  ldc.i4.1
0xf60  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo::set_UseShellExecute(bool)
0xf65  ldloc.s  0xA
0xf67  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess::get_StartInfo()
0xf6c  ldloc.s  6
0xf6e  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0xf73  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo::set_WorkingDirectory(string)
0xf78  ldloc.s  0xA
0xf7a  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess::Start()
0xf7f  pop
0xf80  ldarg.0
0xf81  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Logger()
0xf86  dup
0xf87  brtrue.s loc_F8C
0xf89  pop
0xf8a  br.s     loc_FAC
0xf8c  ldstr    aChildProcessSt// "Child process started: "
0xf91  ldloc.s  0xA
0xf93  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess::get_StartInfo()
0xf98  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo::get_FileName()
0xf9d  call     string [mscorlib]System.String::Concat(string, string)
0xfa2  call     T0x2B00000A
0xfa7  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0xfac  ldarg.0
0xfad  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Logger()
0xfb2  dup
0xfb3  brtrue.s loc_FB8
0xfb5  pop
0xfb6  br.s     loc_FC7
0xfb8  ldstr    aWaitingForSetu// "Waiting for setup process to complete.."...
0xfbd  call     T0x2B00000A
0xfc2  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0xfc7  ldloc.s  0xA
0xfc9  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess::WaitForExit()
0xfce  ldarg.0
0xfcf  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Logger()
0xfd4  dup
0xfd5  brtrue.s loc_FDA
0xfd7  pop
0xfd8  br.s     loc_FFA
0xfda  ldstr    aChildProcessEx// "Child process exited with code {0}"
0xfdf  ldloc.s  0xA
0xfe1  callvirt instance int32 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess::get_ExitCode()
0xfe6  box      [mscorlib]System.Int32
0xfeb  call     string [mscorlib]System.String::Format(string, object)
0xff0  call     T0x2B00000A
0xff5  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0xffa  ldloc.s  0xA
0xffc  callvirt instance int32 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess::get_ExitCode()
0x1001  stloc.s  0xB
0x1003  leave.s  loc_106D
0x1005  ldloc.s  0xA
0x1007  brfalse.s loc_1010
0x1009  ldloc.s  0xA
0x100b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1010  endfinally
0x1011  ldloc.1
0x1012  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Bootstrapper.IBootstrapperInformation::get_OfflineInstallerPath()
0x1017  newobj   instance void [mscorlib]System.IO.FileNotFoundException::.ctor(string)
0x101c  stloc.s  0xC
0x101e  ldarg.0
0x101f  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Logger()
0x1024  dup
0x1025  brtrue.s loc_102A
0x1027  pop
0x1028  br.s     loc_1047
0x102a  ldloc.s  0xC
0x102c  ldstr    aFailedToFindTh// "Failed to find the background exe: "
0x1031  ldloc.s  6
0x1033  ldstr    asc_72E8// "."
0x1038  call     string [mscorlib]System.String::Concat(string, string, string)
0x103d  call     T0x2B00000A
0x1042  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x1047  ldloc.s  0xC
0x1049  throw
0x104a  ldarg.0
0x104b  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_FileSystem()
0x1050  ldloc.2
0x1051  ldloca.s 0xD
0x1053  ldc.i4.1
0x1054  ldc.i4.1
0x1055  ldc.i4.2
0x1056  ldc.i4   0x1F4
0x105b  ldnull
0x105c  call     bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extensions::DeleteDirectoryWithRetry(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem, string, bool&, bool, bool, int32, int32, class [mscorlib]System.Func`3<class [mscorlib]System.Exception, int32, bool>)
0x1061  pop
0x1062  endfinally
0x1063  ldloc.0
0x1064  brfalse.s loc_106C
0x1066  ldloc.0
0x1067  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x106c  endfinally
0x106d  ldloc.s  0xB
0x106f  ret
```
