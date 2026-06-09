# Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::AddPackage

- ea: `0x53f20`
- end: `0x54089`
- name: `Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::AddPackage`
- size: `361`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x50b20`
- `0x51680`
- `0x56d40`

## callees

- `0x53f20`
- `0x54170`
- `0x54300`
- `0x54350`
- `0x547f0`
- `0x54830`

## string_xrefs

- `0x53fe3`: `Updating the package manifest for `
- `0x5403b`: `Skipping caching the package manifest for `
- `0x54046`: ` as it was already found in the cache`

## pseudocode

```c

```

## disassembly

```asm
0x53f20  ldarg.0
0x53f21  call     void Microsoft.VisualStudio.Setup.Cache.Extensions::ValidateCanWrite(class Microsoft.VisualStudio.Setup.Cache.IReadOnlyRepository repository)
0x53f26  ldarg.1
0x53f27  ldstr    aPackage// "package"
0x53f2c  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x53f31  ldarg.0
0x53f32  ldc.i4.1
0x53f33  ldc.i4.1
0x53f34  call     bool Microsoft.VisualStudio.Setup.Cache.Extensions::Supports(class Microsoft.VisualStudio.Setup.Cache.IPackageRepository repository, valuetype Microsoft.VisualStudio.Setup.RepositoryCapabilities capability, [opt] bool throw)
0x53f39  pop
0x53f3a  ldarg.0
0x53f3b  ldarg.1
0x53f3c  callvirt instance string Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::GetPackageDirectory(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity identity)
0x53f41  stloc.0
0x53f42  ldarg.0
0x53f43  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::get_FileSystem()
0x53f48  ldloc.0
0x53f49  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::CreateDirectory(string)
0x53f4e  ldloc.0
0x53f4f  ldsfld   string Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::ManifestFileName
0x53f54  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x53f59  stloc.1
0x53f5a  ldarg.0
0x53f5b  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::services
0x53f60  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.PackageSerializer::.ctor(class [mscorlib]System.IServiceProvider)
0x53f65  dup
0x53f66  ldloc.1
0x53f67  callvirt instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::set_Location(string)
0x53f6c  stloc.2
0x53f6d  ldnull
0x53f6e  stloc.3
0x53f6f  ldarg.0
0x53f70  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::get_FileSystem()
0x53f75  ldloc.1
0x53f76  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x53f7b  brfalse.s loc_53FA2
0x53f7d  ldarg.0
0x53f7e  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::get_FileSystem()
0x53f83  ldloc.1
0x53f84  callvirt instance class [mscorlib]System.IO.TextReader [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::OpenText(string)
0x53f89  stloc.s  4
0x53f8b  ldloc.2
0x53f8c  ldloc.s  4
0x53f8e  callvirt instance var<u1> class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::Deserialize(!!T0)
0x53f93  stloc.3
0x53f94  leave.s  loc_53FA2
0x53f96  ldloc.s  4
0x53f98  brfalse.s loc_53FA1
0x53f9a  ldloc.s  4
0x53f9c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x53fa1  endfinally
0x53fa2  ldsfld   class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageIdentityComparer [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageIdentityComparer::Default
0x53fa7  ldloc.3
0x53fa8  ldarg.1
0x53fa9  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageIdentityComparer::Equals(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity)
0x53fae  brfalse  loc_5405B
0x53fb3  ldloc.3
0x53fb4  isinst   [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage
0x53fb9  stloc.s  5
0x53fbb  ldloc.s  5
0x53fbd  brfalse.s loc_54030
0x53fbf  ldarg.1
0x53fc0  isinst   [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage
0x53fc5  stloc.s  6
0x53fc7  ldloc.s  6
0x53fc9  brfalse.s loc_54030
0x53fcb  ldarg.0
0x53fcc  ldloc.s  5
0x53fce  ldloc.s  6
0x53fd0  call     instance bool Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::MergeAndValidateShortcutLocalPath(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage source, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage target)
0x53fd5  brfalse.s loc_54030
0x53fd7  ldarg.0
0x53fd8  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::logger
0x53fdd  dup
0x53fde  brtrue.s loc_53FE3
0x53fe0  pop
0x53fe1  br.s     loc_54002
0x53fe3  ldstr    aUpdatingThePac// "Updating the package manifest for "
0x53fe8  ldarg.1
0x53fe9  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0x53fee  ldstr    aAsNewInformati// " as new information is added."
0x53ff3  call     string [mscorlib]System.String::Concat(string, string, string)
0x53ff8  call     T0x2B000003
0x53ffd  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x54002  ldarg.0
0x54003  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::get_FileSystem()
0x54008  ldloc.1
0x54009  ldc.i4.1
0x5400a  callvirt instance class [mscorlib]System.IO.TextWriter [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::CreateText(string, bool)
0x5400f  stloc.s  7
0x54011  ldloc.2
0x54012  ldloc.s  7
0x54014  ldloc.s  5
0x54016  callvirt instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::Serialize(class [mscorlib]System.IO.TextWriter, var<u1>)
0x5401b  ldloc.s  7
0x5401d  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.Extensions::Complete(class [mscorlib]System.IO.TextWriter)
0x54022  leave.s  loc_54088
0x54024  ldloc.s  7
0x54026  brfalse.s loc_5402F
0x54028  ldloc.s  7
0x5402a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5402f  endfinally
0x54030  ldarg.0
0x54031  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::logger
0x54036  dup
0x54037  brtrue.s loc_5403B
0x54039  pop
0x5403a  ret
0x5403b  ldstr    aSkippingCachin// "Skipping caching the package manifest f"...
0x54040  ldarg.1
0x54041  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0x54046  ldstr    aAsItWasAlready// " as it was already found in the cache"
0x5404b  call     string [mscorlib]System.String::Concat(string, string, string)
0x54050  call     T0x2B000003
0x54055  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5405a  ret
0x5405b  ldarg.0
0x5405c  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::get_FileSystem()
0x54061  ldloc.1
0x54062  ldc.i4.1
0x54063  callvirt instance class [mscorlib]System.IO.TextWriter [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::CreateText(string, bool)
0x54068  stloc.s  8
0x5406a  ldloc.2
0x5406b  ldloc.s  8
0x5406d  ldarg.1
0x5406e  callvirt instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::Serialize(class [mscorlib]System.IO.TextWriter, var<u1>)
0x54073  ldloc.s  8
0x54075  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.Extensions::Complete(class [mscorlib]System.IO.TextWriter)
0x5407a  leave.s  loc_54088
0x5407c  ldloc.s  8
0x5407e  brfalse.s loc_54087
0x54080  ldloc.s  8
0x54082  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x54087  endfinally
0x54088  ret
```
