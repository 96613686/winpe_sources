# Microsoft.VisualStudio.Setup.Installer.ZipInstaller::UninstallCoreInternal

- ea: `0x34ec0`
- end: `0x35058`
- name: `Microsoft.VisualStudio.Setup.Installer.ZipInstaller::UninstallCoreInternal`
- size: `408`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1a090`
- `0x2b140`
- `0x2b3c0`
- `0x2b560`
- `0x2b940`
- `0x2bb70`
- `0x34ec0`
- `0x35060`
- `0x35080`

## string_xrefs

- `0x34eca`: `InstallDir`
- `0x34f3d`: `InvalidInputPaths`
- `0x34eea`: `The cached manifest for the zip package could not be found.`
- `0x34f1d`: `The cached manifest for the zip package could not be found.`
- `0x34efb`: `Could not uninstall package '{0}' because it is not cached.`

## pseudocode

```c

```

## disassembly

```asm
0x34ec0  ldarg.s  4
0x34ec2  brtrue.s loc_34F28
0x34ec4  ldarg.0
0x34ec5  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.VisualStudio.Setup.Installer.InstallerBase::GetProperties()
0x34eca  ldstr    aInstalldir// "InstallDir"
0x34ecf  ldloca.s 3
0x34ed1  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::TryGetValue(var<u1>, !!T0)
0x34ed6  brfalse.s loc_34EF5
0x34ed8  ldloc.3
0x34ed9  ldarg.1
0x34eda  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::ContainsPath(string, string)
0x34edf  brtrue.s loc_34EF5
0x34ee1  ldc.i4.4
0x34ee2  ldc.i4.0
0x34ee3  ldnull
0x34ee4  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x34ee9  dup
0x34eea  ldstr    aTheCachedManif// "The cached manifest for the zip package"...
0x34eef  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::set_Details(string)
0x34ef4  ret
0x34ef5  ldarg.0
0x34ef6  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x34efb  ldstr    aCouldNotUninst_0// "Could not uninstall package '{0}' becau"...
0x34f00  ldc.i4.1
0x34f01  newarr   [mscorlib]System.Object
0x34f06  dup
0x34f07  ldc.i4.0
0x34f08  ldarg.2
0x34f09  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::GetUniqueId()
0x34f0e  stelem.ref
0x34f0f  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x34f14  ldc.i4.1
0x34f15  ldc.i4.0
0x34f16  ldnull
0x34f17  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x34f1c  dup
0x34f1d  ldstr    aTheCachedManif// "The cached manifest for the zip package"...
0x34f22  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::set_Details(string)
0x34f27  ret
0x34f28  ldarg.2
0x34f29  isinst   [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ZipPackage
0x34f2e  stloc.0
0x34f2f  ldarg.0
0x34f30  ldarg.1
0x34f31  ldloc.0
0x34f32  ldloca.s 1
0x34f34  call     instance bool Microsoft.VisualStudio.Setup.Installer.ZipInstaller::TryGetTargetPath(string installDir, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ZipPackage zipPackage, [out] string& targetPath)
0x34f39  brtrue.s loc_34F48
0x34f3b  ldc.i4.4
0x34f3c  ldc.i4.0
0x34f3d  ldstr    aInvalidinputpa// "InvalidInputPaths"
0x34f42  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x34f47  ret
0x34f48  ldc.i4.0
0x34f49  stloc.2
0x34f4a  ldarg.0
0x34f4b  ldloc.0
0x34f4c  ldnull
0x34f4d  call     instance class Microsoft.VisualStudio.Setup.Services.FileLogger Microsoft.VisualStudio.Setup.Installer.ZipInstaller::GetLoggerForPackage(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ZipPackage pkg, string installerFile)
0x34f52  stloc.s  4
0x34f54  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x34f59  newobj   instance void class [System]System.Collections.Generic.SortedSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IComparer`1<var<u1>>)
0x34f5e  stloc.s  5
0x34f60  ldarg.1
0x34f61  ldloc.1
0x34f62  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x34f67  brfalse.s loc_34F78
0x34f69  ldarg.0
0x34f6a  ldloc.1
0x34f6b  ldloc.1
0x34f6c  call     string [mscorlib]System.IO.Path::GetPathRoot(string)
0x34f71  ldloc.s  5
0x34f73  call     instance void Microsoft.VisualStudio.Setup.Installer.FileInstaller::GetFolderAncestors(string pathToStartFrom, string rootDir, class [System]System.Collections.Generic.ISet`1<string> ancestors)
0x34f78  ldloc.0
0x34f79  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<var<u1>> class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FilePackage`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileItem>::get_Files()
0x34f7e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileItem>::GetEnumerator()
0x34f83  stloc.s  6
0x34f85  br.s     loc_34FD3
0x34f87  ldloc.s  6
0x34f89  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileItem>::get_Current()
0x34f8e  stloc.s  7
0x34f90  ldloc.1
0x34f91  ldloc.s  7
0x34f93  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileItem::get_FileName()
0x34f98  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x34f9d  stloc.s  8
0x34f9f  ldarg.0
0x34fa0  ldloc.s  8
0x34fa2  ldloc.1
0x34fa3  ldloc.s  4
0x34fa5  ldloca.s 9
0x34fa7  ldloc.s  5
0x34fa9  call     instance bool Microsoft.VisualStudio.Setup.Installer.FileInstaller::DeleteFile(string file, string installDir, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger, [out] bool& rebootRequired, [opt] class [System]System.Collections.Generic.ISet`1<string> dirsDeleteCandidates)
0x34fae  ldloc.2
0x34faf  ldloc.s  9
0x34fb1  or
0x34fb2  stloc.2
0x34fb3  brtrue.s loc_34FD3
0x34fb5  ldloc.s  9
0x34fb7  brtrue.s loc_34FD3
0x34fb9  ldc.i4.4
0x34fba  ldc.i4.0
0x34fbb  call     string Microsoft.VisualStudio.Setup.Resources::get_FileDeletionFailed_Args1()
0x34fc0  ldloc.s  8
0x34fc2  call     string [mscorlib]System.String::Format(string, object)
0x34fc7  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x34fcc  stloc.s  0xA
0x34fce  leave    loc_35055
0x34fd3  ldloc.s  6
0x34fd5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x34fda  brtrue.s loc_34F87
0x34fdc  leave.s  loc_34FEA
0x34fde  ldloc.s  6
0x34fe0  brfalse.s loc_34FE9
0x34fe2  ldloc.s  6
0x34fe4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x34fe9  endfinally
0x34fea  ldloc.0
0x34feb  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ZipPackage::get_Directories()
0x34ff0  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x34ff5  stloc.s  0xB
0x34ff7  br.s     loc_35016
0x34ff9  ldloc.s  0xB
0x34ffb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x35000  stloc.s  0xC
0x35002  ldloc.1
0x35003  ldloc.s  0xC
0x35005  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x3500a  stloc.s  0xD
0x3500c  ldloc.s  5
0x3500e  ldloc.s  0xD
0x35010  callvirt instance bool class [System]System.Collections.Generic.SortedSet`1<string>::Add(var<u1>)
0x35015  pop
0x35016  ldloc.s  0xB
0x35018  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3501d  brtrue.s loc_34FF9
0x3501f  leave.s  loc_3502D
0x35021  ldloc.s  0xB
0x35023  brfalse.s loc_3502C
0x35025  ldloc.s  0xB
0x35027  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3502c  endfinally
0x3502d  ldarg.0
0x3502e  ldloc.s  5
0x35030  ldloc.2
0x35031  ldloc.s  4
0x35033  call     instance void Microsoft.VisualStudio.Setup.Installer.FileInstaller::DeleteEmptyDirectories(class [System]System.Collections.Generic.ISet`1<string> dirsDeleteCandidates, bool rebootPending, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0x35038  leave.s  loc_35046
0x3503a  ldloc.s  4
0x3503c  brfalse.s loc_35045
0x3503e  ldloc.s  4
0x35040  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x35045  endfinally
0x35046  ldloc.2
0x35047  brtrue.s loc_3504C
0x35049  ldc.i4.1
0x3504a  br.s     loc_3504D
0x3504c  ldc.i4.3
0x3504d  ldc.i4.0
0x3504e  ldnull
0x3504f  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x35054  ret
0x35055  ldloc.s  0xA
0x35057  ret
```
