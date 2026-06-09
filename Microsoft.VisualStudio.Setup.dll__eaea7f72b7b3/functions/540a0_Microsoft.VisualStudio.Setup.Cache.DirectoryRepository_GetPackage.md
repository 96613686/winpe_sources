# Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::GetPackage

- ea: `0x540a0`
- end: `0x54169`
- name: `Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::GetPackage`
- size: `201`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x50270`
- `0x50b60`
- `0x517f0`
- `0x51f40`
- `0x52240`

## callees

- `0x540a0`
- `0x54170`
- `0x54300`

## string_xrefs

- `0x540cd`: `Package directory for `
- `0x54114`: `Package manifest for `

## pseudocode

```c

```

## disassembly

```asm
0x540a0  ldarg.1
0x540a1  ldstr    aIdentity// "identity"
0x540a6  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x540ab  ldarg.0
0x540ac  ldarg.1
0x540ad  callvirt instance string Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::GetPackageDirectory(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity identity)
0x540b2  stloc.0
0x540b3  ldarg.0
0x540b4  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::get_FileSystem()
0x540b9  ldloc.0
0x540ba  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::DirectoryExists(string)
0x540bf  brtrue.s loc_540EE
0x540c1  ldarg.0
0x540c2  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::logger
0x540c7  dup
0x540c8  brtrue.s loc_540CD
0x540ca  pop
0x540cb  br.s     loc_540EC
0x540cd  ldstr    aPackageDirecto// "Package directory for "
0x540d2  ldarg.1
0x540d3  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::GetUniqueId()
0x540d8  ldstr    aWasNotFound_0// " was not found."
0x540dd  call     string [mscorlib]System.String::Concat(string, string, string)
0x540e2  call     T0x2B000003
0x540e7  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x540ec  ldnull
0x540ed  ret
0x540ee  ldloc.0
0x540ef  ldsfld   string Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::ManifestFileName
0x540f4  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x540f9  stloc.1
0x540fa  ldarg.0
0x540fb  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::get_FileSystem()
0x54100  ldloc.1
0x54101  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x54106  brtrue.s loc_54135
0x54108  ldarg.0
0x54109  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::logger
0x5410e  dup
0x5410f  brtrue.s loc_54114
0x54111  pop
0x54112  br.s     loc_54133
0x54114  ldstr    aPackageManifes// "Package manifest for "
0x54119  ldarg.1
0x5411a  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::GetUniqueId()
0x5411f  ldstr    aWasNotFound_0// " was not found."
0x54124  call     string [mscorlib]System.String::Concat(string, string, string)
0x54129  call     T0x2B000003
0x5412e  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x54133  ldnull
0x54134  ret
0x54135  ldarg.0
0x54136  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::get_FileSystem()
0x5413b  ldloc.1
0x5413c  callvirt instance class [mscorlib]System.IO.TextReader [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::OpenText(string)
0x54141  stloc.2
0x54142  ldarg.0
0x54143  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::services
0x54148  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.PackageSerializer::.ctor(class [mscorlib]System.IServiceProvider)
0x5414d  dup
0x5414e  ldloc.1
0x5414f  callvirt instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::set_Location(string)
0x54154  ldloc.2
0x54155  callvirt instance var<u1> class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::Deserialize(!!T0)
0x5415a  stloc.3
0x5415b  leave.s  loc_54167
0x5415d  ldloc.2
0x5415e  brfalse.s loc_54166
0x54160  ldloc.2
0x54161  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x54166  endfinally
0x54167  ldloc.3
0x54168  ret
```
