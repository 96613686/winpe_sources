# Microsoft.VisualStudio.Setup.Installer.NuGetPackageInstaller::InstallCoreInternal

- ea: `0x30c00`
- end: `0x30cf9`
- name: `Microsoft.VisualStudio.Setup.Installer.NuGetPackageInstaller::InstallCoreInternal`
- size: `249`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xf0e0`
- `0x16ac0`
- `0x16ae0`
- `0x2b920`
- `0x2b940`
- `0x2bb70`
- `0x2c050`
- `0x30c00`
- `0x30d00`
- `0x31280`
- `0x31350`
- `0x40b90`

## string_xrefs

- `0x30c31`: `InvalidInputPaths`
- `0x30c64`: `InvalidInputPaths`
- `0x30c1b`: `Invalid source path {0}.`
- `0x30c4e`: `Invalid nupkg target installation path {0}.`
- `0x30c94`: `Config`

## pseudocode

```c

```

## disassembly

```asm
0x30c00  ldarg.0
0x30c01  ldarg.3
0x30c02  call     T0x2B00017D
0x30c07  stloc.0
0x30c08  ldarg.0
0x30c09  ldarg.1
0x30c0a  ldarg.3
0x30c0b  ldloca.s 1
0x30c0d  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.InstallerBase::TryGetValidatedInstallerFilePath(string localPath, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage pkg, [out] string& primaryPayloadPath)
0x30c12  brtrue.s loc_30C3C
0x30c14  ldarg.0
0x30c15  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x30c1a  ldnull
0x30c1b  ldstr    aInvalidSourceP// "Invalid source path {0}."
0x30c20  ldc.i4.1
0x30c21  newarr   [mscorlib]System.Object
0x30c26  dup
0x30c27  ldc.i4.0
0x30c28  ldarg.1
0x30c29  stelem.ref
0x30c2a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x30c2f  ldc.i4.4
0x30c30  ldc.i4.0
0x30c31  ldstr    aInvalidinputpa// "InvalidInputPaths"
0x30c36  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x30c3b  ret
0x30c3c  ldarg.0
0x30c3d  ldloc.0
0x30c3e  ldloca.s 2
0x30c40  call     instance bool Microsoft.VisualStudio.Setup.Installer.NuGetPackageInstaller::TryGetTargetPath(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NuGetPackage nuGetPackage, [out] string& targetPath)
0x30c45  brtrue.s loc_30C6F
0x30c47  ldarg.0
0x30c48  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x30c4d  ldnull
0x30c4e  ldstr    aInvalidNupkgTa// "Invalid nupkg target installation path "...
0x30c53  ldc.i4.1
0x30c54  newarr   [mscorlib]System.Object
0x30c59  dup
0x30c5a  ldc.i4.0
0x30c5b  ldloc.2
0x30c5c  stelem.ref
0x30c5d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x30c62  ldc.i4.4
0x30c63  ldc.i4.0
0x30c64  ldstr    aInvalidinputpa// "InvalidInputPaths"
0x30c69  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x30c6e  ret
0x30c6f  ldarg.0
0x30c70  ldloc.0
0x30c71  ldloc.1
0x30c72  call     instance class Microsoft.VisualStudio.Setup.Services.FileLogger Microsoft.VisualStudio.Setup.Installer.NuGetPackageInstaller::GetLoggerForPackage(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NuGetPackage pkg, string installerFile)
0x30c77  stloc.3
0x30c78  ldarg.0
0x30c79  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_Services()
0x30c7e  ldloc.3
0x30c7f  newobj   instance void Microsoft.VisualStudio.Setup.NugetConfigGenerator::.ctor(class [mscorlib]System.IServiceProvider container, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0x30c84  ldarg.0
0x30c85  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.NuGetPackageInstaller::fileSystem
0x30c8a  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::get_SharedProgramsDirectory()
0x30c8f  ldstr    aNuget// "Nuget"
0x30c94  ldstr    aConfig// "Config"
0x30c99  call     string [mscorlib]System.IO.Path::Combine(string, string, string)
0x30c9e  stloc.s  4
0x30ca0  ldarg.0
0x30ca1  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.VisualStudio.Setup.Installer.InstallerBase::GetProperties()
0x30ca6  stloc.s  5
0x30ca8  ldarg.0
0x30ca9  ldfld    string Microsoft.VisualStudio.Setup.Installer.NuGetPackageInstaller::nugetFallbackFolder
0x30cae  ldloc.s  5
0x30cb0  ldnull
0x30cb1  ldc.i4.0
0x30cb2  call     string Microsoft.VisualStudio.Setup.Extensions::ReplaceVariables(string value, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> properties, [opt] class [System]System.Collections.Generic.ISet`1<string> variablesToIgnore, [opt] bool recursive)
0x30cb7  stloc.s  6
0x30cb9  ldloc.s  4
0x30cbb  ldloc.s  6
0x30cbd  callvirt instance void Microsoft.VisualStudio.Setup.NugetConfigGenerator::AddNugetConfig(string nugetConfigDirectoryPath, string fallbackfolderPath)
0x30cc2  ldloc.0
0x30cc3  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<var<u1>> class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FilePackage`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileItem>::get_Files()
0x30cc8  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileItem>::Clear()
0x30ccd  ldloc.0
0x30cce  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NuGetPackage::get_Directories()
0x30cd3  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Clear()
0x30cd8  ldarg.0
0x30cd9  ldloc.3
0x30cda  ldloc.3
0x30cdb  newobj   instance void Microsoft.VisualStudio.Setup.Services.NupkgLoggerAdapter::.ctor(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0x30ce0  ldloc.1
0x30ce1  ldloc.2
0x30ce2  ldloc.0
0x30ce3  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Installer.NuGetPackageInstaller::ExtractNupkg(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger, class Microsoft.VisualStudio.Setup.Services.NupkgLoggerAdapter loggerAdapter, string installerFile, string targetPath, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NuGetPackage nuGetPackage)
0x30ce8  stloc.s  7
0x30cea  leave.s  loc_30CF6
0x30cec  ldloc.3
0x30ced  brfalse.s loc_30CF5
0x30cef  ldloc.3
0x30cf0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x30cf5  endfinally
0x30cf6  ldloc.s  7
0x30cf8  ret
```
