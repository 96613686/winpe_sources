# Microsoft.VisualStudio.Setup.Installer.NuGetPackageInstaller::UninstallCoreInternal

- ea: `0x31040`
- end: `0x31276`
- name: `Microsoft.VisualStudio.Setup.Installer.NuGetPackageInstaller::UninstallCoreInternal`
- size: `566`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callees

- `0x10050`
- `0x19e70`
- `0x19e90`
- `0x19eb0`
- `0x1a090`
- `0x2b140`
- `0x2b3c0`
- `0x2b560`
- `0x2b940`
- `0x31040`
- `0x31280`
- `0x31300`
- `0x31350`

## string_xrefs

- `0x3106f`: `Error_FailedToUninstall_PackageNull`
- `0x310b4`: `InvalidInputPaths`
- `0x310ec`: `Could not uninstall package '{0}' because either the NuGetPackageId or the NuGetPackageVersion is null.`

## pseudocode

```c

```

## disassembly

```asm
0x31040  ldarg.2
0x31041  isinst   [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NuGetPackage
0x31046  stloc.0
0x31047  ldarg.0
0x31048  ldloc.0
0x31049  ldloca.s 1
0x3104b  call     instance bool Microsoft.VisualStudio.Setup.Installer.NuGetPackageInstaller::TryGetTargetPath(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NuGetPackage nuGetPackage, [out] string& targetPath)
0x31050  brtrue   loc_310D6
0x31055  ldloc.0
0x31056  brtrue.s loc_3108F
0x31058  ldarg.0
0x31059  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x3105e  call     string Microsoft.VisualStudio.Setup.Resources::get_Error_FailedToUninstall_PackageNull()
0x31063  call     T0x2B000003
0x31068  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x3106d  ldc.i4.4
0x3106e  ldc.i4.0
0x3106f  ldstr    aErrorFailedtou_0// "Error_FailedToUninstall_PackageNull"
0x31074  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x31079  dup
0x3107a  call     string Microsoft.VisualStudio.Setup.Resources::get_Error_FailedToUninstall_PackageNull()
0x3107f  call     T0x2B000003
0x31084  call     string [mscorlib]System.String::Format(string, object[])
0x31089  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::set_Details(string)
0x3108e  ret
0x3108f  ldarg.0
0x31090  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x31095  call     string Microsoft.VisualStudio.Setup.Resources::get_Error_FailedToUninstall_InvalidTargetPath_Args2()
0x3109a  ldc.i4.2
0x3109b  newarr   [mscorlib]System.Object
0x310a0  dup
0x310a1  ldc.i4.0
0x310a2  ldarg.2
0x310a3  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::GetUniqueId()
0x310a8  stelem.ref
0x310a9  dup
0x310aa  ldc.i4.1
0x310ab  ldloc.1
0x310ac  stelem.ref
0x310ad  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x310b2  ldc.i4.4
0x310b3  ldc.i4.0
0x310b4  ldstr    aInvalidinputpa// "InvalidInputPaths"
0x310b9  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x310be  dup
0x310bf  call     string Microsoft.VisualStudio.Setup.Resources::get_Error_FailedToUninstall_InvalidTargetPath_Args2()
0x310c4  ldarg.2
0x310c5  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::GetUniqueId()
0x310ca  ldloc.1
0x310cb  call     string [mscorlib]System.String::Format(string, object, object)
0x310d0  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::set_Details(string)
0x310d5  ret
0x310d6  ldloc.0
0x310d7  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NuGetPackage::get_NuGetPackageId()
0x310dc  brfalse.s loc_310E6
0x310de  ldloc.0
0x310df  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NuGetPackage::get_NuGetPackageVersion()
0x310e4  brtrue.s loc_3111D
0x310e6  ldarg.0
0x310e7  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x310ec  ldstr    aCouldNotUninst// "Could not uninstall package '{0}' becau"...
0x310f1  ldc.i4.1
0x310f2  newarr   [mscorlib]System.Object
0x310f7  dup
0x310f8  ldc.i4.0
0x310f9  ldarg.2
0x310fa  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::GetUniqueId()
0x310ff  stelem.ref
0x31100  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x31105  ldc.i4.4
0x31106  ldc.i4.0
0x31107  ldstr    aErrorNugetpack// "Error_NuGetPackageIdOrNuGetPackageVersi"...
0x3110c  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x31111  dup
0x31112  call     string Microsoft.VisualStudio.Setup.Resources::get_Error_NuGetPackageIdOrNuGetPackageVersionNull()
0x31117  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::set_Details(string)
0x3111c  ret
0x3111d  ldc.i4.0
0x3111e  stloc.2
0x3111f  ldloc.0
0x31120  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NuGetPackage::get_NuGetPackageId()
0x31125  ldloc.0
0x31126  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NuGetPackage::get_NuGetPackageVersion()
0x3112b  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x31130  stloc.3
0x31131  ldarg.0
0x31132  ldloc.0
0x31133  ldnull
0x31134  call     instance class Microsoft.VisualStudio.Setup.Services.FileLogger Microsoft.VisualStudio.Setup.Installer.NuGetPackageInstaller::GetLoggerForPackage(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NuGetPackage pkg, string installerFile)
0x31139  stloc.s  4
0x3113b  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x31140  newobj   instance void class [System]System.Collections.Generic.SortedSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IComparer`1<var<u1>>)
0x31145  stloc.s  5
0x31147  ldarg.0
0x31148  ldloc.1
0x31149  ldloc.1
0x3114a  call     string [mscorlib]System.IO.Path::GetPathRoot(string)
0x3114f  ldloc.s  5
0x31151  call     instance void Microsoft.VisualStudio.Setup.Installer.FileInstaller::GetFolderAncestors(string pathToStartFrom, string rootDir, class [System]System.Collections.Generic.ISet`1<string> ancestors)
0x31156  ldarg.s  4
0x31158  brfalse  loc_31214
0x3115d  ldloc.0
0x3115e  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<var<u1>> class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FilePackage`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileItem>::get_Files()
0x31163  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileItem>::GetEnumerator()
0x31168  stloc.s  6
0x3116a  br.s     loc_311B9
0x3116c  ldloc.s  6
0x3116e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileItem>::get_Current()
0x31173  stloc.s  7
0x31175  ldloc.1
0x31176  ldloc.3
0x31177  ldloc.s  7
0x31179  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileItem::get_FileName()
0x3117e  call     string [mscorlib]System.IO.Path::Combine(string, string, string)
0x31183  stloc.s  8
0x31185  ldarg.0
0x31186  ldloc.s  8
0x31188  ldloc.1
0x31189  ldloc.s  4
0x3118b  ldloca.s 9
0x3118d  ldloc.s  5
0x3118f  call     instance bool Microsoft.VisualStudio.Setup.Installer.FileInstaller::DeleteFile(string file, string installDir, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger, [out] bool& rebootRequired, [opt] class [System]System.Collections.Generic.ISet`1<string> dirsDeleteCandidates)
0x31194  ldloc.2
0x31195  ldloc.s  9
0x31197  or
0x31198  stloc.2
0x31199  brtrue.s loc_311B9
0x3119b  ldloc.s  9
0x3119d  brtrue.s loc_311B9
0x3119f  ldc.i4.4
0x311a0  ldc.i4.0
0x311a1  call     string Microsoft.VisualStudio.Setup.Resources::get_FileDeletionFailed_Args1()
0x311a6  ldloc.s  8
0x311a8  call     string [mscorlib]System.String::Format(string, object)
0x311ad  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x311b2  stloc.s  0xA
0x311b4  leave    loc_31273
0x311b9  ldloc.s  6
0x311bb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x311c0  brtrue.s loc_3116C
0x311c2  leave.s  loc_311D0
0x311c4  ldloc.s  6
0x311c6  brfalse.s loc_311CF
0x311c8  ldloc.s  6
0x311ca  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x311cf  endfinally
0x311d0  ldloc.0
0x311d1  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NuGetPackage::get_Directories()
0x311d6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x311db  stloc.s  0xB
0x311dd  br.s     loc_311FD
0x311df  ldloc.s  0xB
0x311e1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x311e6  stloc.s  0xC
0x311e8  ldloc.1
0x311e9  ldloc.3
0x311ea  ldloc.s  0xC
0x311ec  call     string [mscorlib]System.IO.Path::Combine(string, string, string)
0x311f1  stloc.s  0xD
0x311f3  ldloc.s  5
0x311f5  ldloc.s  0xD
0x311f7  callvirt instance bool class [System]System.Collections.Generic.SortedSet`1<string>::Add(var<u1>)
0x311fc  pop
0x311fd  ldloc.s  0xB
0x311ff  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x31204  brtrue.s loc_311DF
0x31206  leave.s  loc_31243
0x31208  ldloc.s  0xB
0x3120a  brfalse.s loc_31213
0x3120c  ldloc.s  0xB
0x3120e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31213  endfinally
0x31214  ldloc.1
0x31215  ldloc.3
0x31216  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x3121b  stloc.s  0xE
0x3121d  ldarg.0
0x3121e  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.NuGetPackageInstaller::fileSystem
0x31223  ldloc.s  0xE
0x31225  ldc.i4.1
0x31226  ldc.i4.2
0x31227  ldc.i4   0x1F4
0x3122c  call     bool Microsoft.VisualStudio.Setup.Extensions::TryDeleteDirectoryWithRetry(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string path, [opt] bool recursive, [opt] int32 retryCount, [opt] int32 retryDelay)
0x31231  pop
0x31232  ldarg.0
0x31233  ldloc.s  0xE
0x31235  ldloc.s  0xE
0x31237  call     string [mscorlib]System.IO.Path::GetPathRoot(string)
0x3123c  ldloc.s  5
0x3123e  call     instance void Microsoft.VisualStudio.Setup.Installer.FileInstaller::GetFolderAncestors(string pathToStartFrom, string rootDir, class [System]System.Collections.Generic.ISet`1<string> ancestors)
0x31243  ldarg.0
0x31244  ldloc.s  5
0x31246  ldloc.2
0x31247  ldloc.s  4
0x31249  call     instance void Microsoft.VisualStudio.Setup.Installer.FileInstaller::DeleteEmptyDirectories(class [System]System.Collections.Generic.ISet`1<string> dirsDeleteCandidates, bool rebootPending, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0x3124e  ldarg.0
0x3124f  ldloc.s  4
0x31251  call     instance void Microsoft.VisualStudio.Setup.Installer.NuGetPackageInstaller::DeleteNugetConfigIfNecessary(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0x31256  leave.s  loc_31264
0x31258  ldloc.s  4
0x3125a  brfalse.s loc_31263
0x3125c  ldloc.s  4
0x3125e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31263  endfinally
0x31264  ldloc.2
0x31265  brtrue.s loc_3126A
0x31267  ldc.i4.1
0x31268  br.s     loc_3126B
0x3126a  ldc.i4.3
0x3126b  ldc.i4.0
0x3126c  ldnull
0x3126d  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x31272  ret
0x31273  ldloc.s  0xA
0x31275  ret
```
