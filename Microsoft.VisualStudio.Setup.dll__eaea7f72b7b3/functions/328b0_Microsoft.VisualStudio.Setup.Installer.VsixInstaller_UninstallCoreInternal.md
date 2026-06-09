# Microsoft.VisualStudio.Setup.Installer.VsixInstaller::UninstallCoreInternal

- ea: `0x328b0`
- end: `0x32ce9`
- name: `Microsoft.VisualStudio.Setup.Installer.VsixInstaller::UninstallCoreInternal`
- size: `1081`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x10ef0`
- `0x119a0`
- `0x1a090`
- `0x2b560`
- `0x2b900`
- `0x2b920`
- `0x2b9e0`
- `0x2bb70`
- `0x2c050`
- `0x32270`
- `0x328b0`
- `0x32cf0`
- `0x32d70`
- `0x32ff0`
- `0x33010`
- `0x33230`
- `0x33e80`
- `0x34070`
- `0x342d0`
- `0x3cea0`
- `0x3ceb0`

## string_xrefs

- `0x32b07`: `InvalidInputPaths`
- `0x32cd6`: `InvalidExtensionDir`
- `0x329da`: `VsixMissingInCache`
- `0x32aab`: ` package has no files per the cached manifest.`

## pseudocode

```c

```

## disassembly

```asm
0x328b0  ldarg.0
0x328b1  ldarg.2
0x328b2  call     T0x2B000183
0x328b7  stloc.0
0x328b8  ldarg.0
0x328b9  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.VisualStudio.Setup.Installer.InstallerBase::GetProperties()
0x328be  stloc.1
0x328bf  ldloc.1
0x328c0  ldloc.0
0x328c1  ldarg.1
0x328c2  call     void Microsoft.VisualStudio.Setup.Extensions::AppendExtendedProperties(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> properties, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage vsixPackage, string installDir)
0x328c7  ldarg.0
0x328c8  ldarg.3
0x328c9  ldarg.2
0x328ca  ldloca.s 3
0x328cc  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.InstallerBase::TryGetValidatedInstallerFilePath(string localPath, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage pkg, [out] string& primaryPayloadPath)
0x328d1  stloc.2
0x328d2  ldloc.2
0x328d3  brtrue.s loc_328D8
0x328d5  ldnull
0x328d6  br.s     loc_328D9
0x328d8  ldloc.3
0x328d9  stloc.3
0x328da  ldarg.1
0x328db  stloc.s  4
0x328dd  ldarg.0
0x328de  ldarg.0
0x328df  ldloc.1
0x328e0  ldloc.0
0x328e1  ldloc.3
0x328e2  ldarg.1
0x328e3  ldloca.s 4
0x328e5  call     instance valuetype Microsoft.VisualStudio.Setup.Installer.VsixType Microsoft.VisualStudio.Setup.Installer.VsixInstaller::ParseVsix(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> nonEnvironmentVars, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage vsixPkg, string installerFile, string installDir, string& layoutDir)
0x328ea  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.VsixType>::.ctor(var<u1>)
0x328ef  stfld    valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.VsixType> Microsoft.VisualStudio.Setup.Installer.VsixInstaller::vsixType
0x328f4  ldnull
0x328f5  stloc.s  5
0x328f7  ldarg.0
0x328f8  call     instance class Microsoft.VisualStudio.Setup.IEngineContext Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_EngineContext()
0x328fd  dup
0x328fe  brtrue.s loc_32904
0x32900  pop
0x32901  ldc.i4.0
0x32902  br.s     loc_32909
0x32904  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction Microsoft.VisualStudio.Setup.IEngineContext::get_BootstrapperAction()
0x32909  stloc.s  6
0x3290b  ldarg.0
0x3290c  ldloc.0
0x3290d  ldloc.3
0x3290e  call     instance class Microsoft.VisualStudio.Setup.Services.FileLogger Microsoft.VisualStudio.Setup.Installer.VsixInstaller::GetLoggerForPackage(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage pkg, string installerFile)
0x32913  stloc.s  7
0x32915  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x3291a  newobj   instance void class [System]System.Collections.Generic.SortedSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IComparer`1<var<u1>>)
0x3291f  stloc.s  8
0x32921  ldloc.0
0x32922  brfalse  loc_329EE
0x32927  ldarg.0
0x32928  ldloc.0
0x32929  ldnull
0x3292a  ldc.i4.3
0x3292b  ldloc.s  7
0x3292d  ldarg.s  4
0x3292f  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage Microsoft.VisualStudio.Setup.Installer.VsixInstaller::GetEmbeddedVsixPackage(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity vsix, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackage package, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction action, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger, bool isManifestCached)
0x32934  stloc.s  5
0x32936  ldloc.s  5
0x32938  brtrue   loc_329EE
0x3293d  ldarg.3
0x3293e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x32943  brtrue.s loc_32959
0x32945  ldloc.2
0x32946  brfalse.s loc_32959
0x32948  ldarg.0
0x32949  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_FileSystem()
0x3294e  ldloc.3
0x3294f  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x32954  brtrue   loc_329EE
0x32959  ldarg.0
0x3295a  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.VsixType> Microsoft.VisualStudio.Setup.Installer.VsixInstaller::vsixType
0x3295f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.VsixType>::GetValueOrDefault()
0x32964  ldc.i4.2
0x32965  bne.un.s loc_329C3
0x32967  ldarg.0
0x32968  ldloc.0
0x32969  ldarg.1
0x3296a  call     instance string Microsoft.VisualStudio.Setup.Installer.VsixInstaller::GetExtensionDir(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage pkg, string installDir)
0x3296f  ldsfld   string Microsoft.VisualStudio.Setup.Installer.VsixInstaller::ManifestName
0x32974  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x32979  stloc.s  0xD
0x3297b  ldarg.0
0x3297c  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_FileSystem()
0x32981  ldloc.s  0xD
0x32983  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x32988  brfalse.s loc_329EE
0x3298a  ldarg.0
0x3298b  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_FileSystem()
0x32990  ldloc.s  0xD
0x32992  callvirt instance class [mscorlib]System.IO.TextReader [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::OpenText(string)
0x32997  stloc.s  0xE
0x32999  ldnull
0x3299a  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.PackageSerializer::.ctor(class [mscorlib]System.IServiceProvider)
0x3299f  dup
0x329a0  ldloc.s  0xD
0x329a2  callvirt instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::set_Location(string)
0x329a7  ldloc.s  0xE
0x329a9  callvirt instance var<u1> class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::Deserialize(!!T0)
0x329ae  isinst   [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage
0x329b3  stloc.s  5
0x329b5  leave.s  loc_329EE
0x329b7  ldloc.s  0xE
0x329b9  brfalse.s loc_329C2
0x329bb  ldloc.s  0xE
0x329bd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x329c2  endfinally
0x329c3  ldloc.s  6
0x329c5  ldc.i4.3
0x329c6  beq.s    loc_329EE
0x329c8  ldarg.0
0x329c9  ldarg.2
0x329ca  ldc.i4.3
0x329cb  ldc.i4.0
0x329cc  ldloc.s  7
0x329ce  stloc.s  0xF
0x329d0  ldloca.s 0x10
0x329d2  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x329d8  ldloc.s  0x10
0x329da  ldstr    aVsixmissinginc// "VsixMissingInCache"
0x329df  ldnull
0x329e0  ldloc.s  0xF
0x329e2  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Installer.VsixInstaller::ReturnVSIXReturnCode(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage pkg, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction action, [opt] valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RebootType rebootPending, [opt] valuetype [mscorlib]System.Nullable`1<int32> code, [opt] string resourceId, [opt] string details, [opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger pkgLogger)
0x329e7  stloc.s  0x11
0x329e9  leave    loc_32CE6
0x329ee  ldc.i4.0
0x329ef  ldnull
0x329f0  newobj   instance void class [mscorlib]System.Tuple`2<bool, string>::.ctor(var<u1>, !!T0)
0x329f5  stloc.s  9
0x329f7  ldloc.s  5
0x329f9  brfalse  loc_32AC4
0x329fe  ldarg.0
0x329ff  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.VisualStudio.Setup.Installer.InstallerBase::GetProperties()
0x32a04  stloc.1
0x32a05  ldloc.1
0x32a06  ldloc.s  5
0x32a08  ldarg.1
0x32a09  call     void Microsoft.VisualStudio.Setup.Extensions::AppendExtendedProperties(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> properties, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage vsixPackage, string installDir)
0x32a0e  ldarg.0
0x32a0f  ldloc.s  5
0x32a11  ldloc.1
0x32a12  ldc.i4.0
0x32a13  call     instance void Microsoft.VisualStudio.Setup.Installer.VsixInstaller::DoShortcutAction(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage pkg, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> variableMapping, bool create)
0x32a18  ldarg.0
0x32a19  ldarg.0
0x32a1a  ldloc.1
0x32a1b  ldloc.s  5
0x32a1d  ldloc.3
0x32a1e  ldarg.1
0x32a1f  ldloca.s 4
0x32a21  call     instance valuetype Microsoft.VisualStudio.Setup.Installer.VsixType Microsoft.VisualStudio.Setup.Installer.VsixInstaller::ParseVsix(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> nonEnvironmentVars, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage vsixPkg, string installerFile, string installDir, string& layoutDir)
0x32a26  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.VsixType>::.ctor(var<u1>)
0x32a2b  stfld    valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.VsixType> Microsoft.VisualStudio.Setup.Installer.VsixInstaller::vsixType
0x32a30  ldloc.s  5
0x32a32  brfalse.s loc_32AA3
0x32a34  ldloc.s  5
0x32a36  call     instance class [mscorlib]System.Collections.Generic.IList`1<var<u1>> class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FilePackage`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixFile>::get_Files()
0x32a3b  dup
0x32a3c  brtrue.s loc_32A4B
0x32a3e  pop
0x32a3f  ldloca.s 0x13
0x32a41  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x32a47  ldloc.s  0x13
0x32a49  br.s     loc_32A55
0x32a4b  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixFile>::get_Count()
0x32a50  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x32a55  stloc.s  0x10
0x32a57  ldc.i4.0
0x32a58  stloc.s  0x12
0x32a5a  ldloca.s 0x10
0x32a5c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x32a61  ldloc.s  0x12
0x32a63  cgt
0x32a65  ldloca.s 0x10
0x32a67  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x32a6c  and
0x32a6d  brfalse.s loc_32AA3
0x32a6f  ldarg.0
0x32a70  ldloc.1
0x32a71  ldloc.s  5
0x32a73  brtrue.s loc_32A78
0x32a75  ldnull
0x32a76  br.s     loc_32A7F
0x32a78  ldloc.s  5
0x32a7a  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage::get_FolderMappings()
0x32a7f  ldloc.s  4
0x32a81  ldarg.0
0x32a82  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.VsixType> Microsoft.VisualStudio.Setup.Installer.VsixInstaller::vsixType
0x32a87  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.VsixType>::get_Value()
0x32a8c  ldloc.s  7
0x32a8e  ldloc.s  8
0x32a90  ldloc.s  5
0x32a92  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<var<u1>> class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FilePackage`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixFile>::get_Files()
0x32a97  call     instance class [mscorlib]System.Tuple`2<bool, string> Microsoft.VisualStudio.Setup.Installer.VsixInstaller::ProcessVsixForUninstall(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> nonEnvironmentVars, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> folderMappings, string layoutDir, valuetype Microsoft.VisualStudio.Setup.Installer.VsixType vsixType, class Microsoft.VisualStudio.Setup.Services.FileLogger logger, class [System]System.Collections.Generic.SortedSet`1<string> dirsDeleteCandidates, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixFile> files)
0x32a9c  stloc.s  9
0x32a9e  br       loc_32C20
0x32aa3  ldloc.s  7
0x32aa5  ldloc.0
0x32aa6  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Id()
0x32aab  ldstr    aPackageHasNoFi// " package has no files per the cached ma"...
0x32ab0  call     string [mscorlib]System.String::Concat(string, string)
0x32ab5  call     T0x2B000003
0x32aba  callvirt instance void Microsoft.VisualStudio.Setup.Services.FileLogger::WriteWarning(string format, object[] args)
0x32abf  br       loc_32C20
0x32ac4  ldarg.3
0x32ac5  brfalse  loc_32C10
0x32aca  ldloc.2
0x32acb  brfalse.s loc_32ADB
0x32acd  ldarg.0
0x32ace  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_FileSystem()
0x32ad3  ldloc.3
0x32ad4  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x32ad9  brtrue.s loc_32B1B
0x32adb  ldloc.s  6
0x32add  ldc.i4.3
0x32ade  bne.un.s loc_32AF5
0x32ae0  ldarg.0
0x32ae1  ldloc.0
0x32ae2  ldloc.1
0x32ae3  ldloc.s  4
0x32ae5  ldloc.s  8
0x32ae7  ldloc.s  7
0x32ae9  call     instance class [mscorlib]System.Tuple`2<bool, string> Microsoft.VisualStudio.Setup.Installer.VsixInstaller::UninstallWithoutCachedManifestAndPayload(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage vsixPkg, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> nonEnvironmentVars, string layoutDir, class [System]System.Collections.Generic.SortedSet`1<string> dirsDeleteCandidates, class Microsoft.VisualStudio.Setup.Services.FileLogger logger)
0x32aee  stloc.s  9
0x32af0  br       loc_32C20
0x32af5  ldarg.0
0x32af6  ldarg.2
0x32af7  ldc.i4.3
0x32af8  ldc.i4.0
0x32af9  ldloc.s  7
0x32afb  stloc.s  0xF
0x32afd  ldloca.s 0x10
0x32aff  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x32b05  ldloc.s  0x10
0x32b07  ldstr    aInvalidinputpa// "InvalidInputPaths"
0x32b0c  ldnull
0x32b0d  ldloc.s  0xF
0x32b0f  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Installer.VsixInstaller::ReturnVSIXReturnCode(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage pkg, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction action, [opt] valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RebootType rebootPending, [opt] valuetype [mscorlib]System.Nullable`1<int32> code, [opt] string resourceId, [opt] string details, [opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger pkgLogger)
0x32b14  stloc.s  0x11
0x32b16  leave    loc_32CE6
0x32b1b  ldloc.s  7
0x32b1d  ldsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerDiagnosticMessages::ExtractionOpenPackage
0x32b22  ldc.i4.1
0x32b23  newarr   [mscorlib]System.Object
0x32b28  dup
0x32b29  ldc.i4.0
0x32b2a  ldloc.3
0x32b2b  stelem.ref
0x32b2c  callvirt instance void Microsoft.VisualStudio.Setup.Services.FileLogger::WriteVerbose(string format, object[] args)
0x32b31  ldarg.0
0x32b32  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_FileSystem()
0x32b37  ldloc.3
0x32b38  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::OpenFile(string)
0x32b3d  stloc.s  0x14
0x32b3f  ldarg.0
0x32b40  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackageReader Microsoft.VisualStudio.Setup.Installer.VsixInstaller::compressedPackageReader
0x32b45  ldloc.s  0x14
0x32b47  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackage [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackageReader::Open(class [mscorlib]System.IO.Stream)
0x32b4c  stloc.s  0x15
0x32b4e  ldarg.0
0x32b4f  ldloc.0
0x32b50  ldloc.s  0x15
0x32b52  ldc.i4.3
0x32b53  ldloc.s  7
0x32b55  ldarg.s  4
0x32b57  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage Microsoft.VisualStudio.Setup.Installer.VsixInstaller::GetEmbeddedVsixPackage(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity vsix, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackage package, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction action, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger, bool isManifestCached)
0x32b5c  stloc.s  5
0x32b5e  ldloc.s  5
0x32b60  brfalse.s loc_32B8C
0x32b62  ldarg.0
0x32b63  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.VisualStudio.Setup.Installer.InstallerBase::GetProperties()
0x32b68  stloc.1
0x32b69  ldloc.1
0x32b6a  ldloc.s  5
0x32b6c  ldarg.1
0x32b6d  call     void Microsoft.VisualStudio.Setup.Extensions::AppendExtendedProperties(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> properties, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage vsixPackage, string installDir)
0x32b72  ldarg.0
0x32b73  ldarg.0
0x32b74  ldloc.1
0x32b75  ldloc.s  5
0x32b77  ldloc.3
0x32b78  ldarg.1
0x32b79  ldloca.s 4
0x32b7b  call     instance valuetype Microsoft.VisualStudio.Setup.Installer.VsixType Microsoft.VisualStudio.Setup.Installer.VsixInstaller::ParseVsix(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> nonEnvironmentVars, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VsixPackage vsixPkg, string installerFile, string installDir, string& layoutDir)
0x32b80  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.VsixType>::.ctor(var<u1>)
0x32b85  stfld    valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Installer.VsixType> Microsoft.VisualStudio.Setup.Installer.VsixInstaller::vsixType
0x32b8a  br.s     loc_32BAA
0x32b8c  ldarg.0
0x32b8d  ldarg.2
0x32b8e  ldc.i4.3
0x32b8f  ldc.i4.0
0x32b90  ldc.i4   0x643
0x32b95  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x32b9a  ldnull
  ... truncated ...
```
