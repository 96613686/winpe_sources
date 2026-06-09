# Microsoft.VisualStudio.Setup.Activities.CacheCatalog::CacheComponents

- ea: `0x5a610`
- end: `0x5a6d0`
- name: `Microsoft.VisualStudio.Setup.Activities.CacheCatalog::CacheComponents`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x5a4a0`

## callees

- `0x596d0`
- `0x596f0`
- `0x5a610`

## string_xrefs

- `0x5a61c`: `Caching component catalog.`
- `0x5a658`: `Failed to deserialize the catalog.`
- `0x5a6b2`: `Failed to cache components: `

## pseudocode

```c

```

## disassembly

```asm
0x5a610  ldarg.0
0x5a611  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5a616  dup
0x5a617  brtrue.s loc_5A61C
0x5a619  pop
0x5a61a  br.s     loc_5A62B
0x5a61c  ldstr    aCachingCompone// "Caching component catalog."
0x5a621  call     T0x2B000003
0x5a626  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5a62b  nop
0x5a62c  ldnull
0x5a62d  stloc.0
0x5a62e  ldarg.0
0x5a62f  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Activities.Activity::get_Services()
0x5a634  ldarg.0
0x5a635  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity> Microsoft.VisualStudio.Setup.Activities.CacheCatalog::packages
0x5a63a  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.ComponentCacheSerializer::.ctor(class [mscorlib]System.IServiceProvider, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity>)
0x5a63f  stloc.1
0x5a640  ldarg.0
0x5a641  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Activities.CacheCatalog::fileSystem
0x5a646  ldarg.2
0x5a647  callvirt instance class [mscorlib]System.IO.TextReader [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::OpenText(string)
0x5a64c  stloc.3
0x5a64d  ldloc.1
0x5a64e  ldloc.3
0x5a64f  callvirt instance var<u1> class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog>::Deserialize(!!T0)
0x5a654  dup
0x5a655  brtrue.s loc_5A663
0x5a657  pop
0x5a658  ldstr    aFailedToDeseri_1// "Failed to deserialize the catalog."
0x5a65d  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x5a662  throw
0x5a663  stloc.0
0x5a664  leave.s  loc_5A670
0x5a666  ldloc.3
0x5a667  brfalse.s loc_5A66F
0x5a669  ldloc.3
0x5a66a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5a66f  endfinally
0x5a670  ldarg.1
0x5a671  ldsfld   string Microsoft.VisualStudio.Setup.Cache.InstanceRepository::ComponentCacheFileName
0x5a676  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x5a67b  stloc.2
0x5a67c  ldarg.0
0x5a67d  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Activities.CacheCatalog::fileSystem
0x5a682  ldloc.2
0x5a683  ldc.i4.0
0x5a684  callvirt instance class [mscorlib]System.IO.TextWriter [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::CreateText(string, bool)
0x5a689  stloc.s  4
0x5a68b  ldloc.1
0x5a68c  ldloc.s  4
0x5a68e  ldloc.0
0x5a68f  callvirt instance void class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog>::Serialize(class [mscorlib]System.IO.TextWriter, var<u1>)
0x5a694  leave.s  loc_5A6A2
0x5a696  ldloc.s  4
0x5a698  brfalse.s loc_5A6A1
0x5a69a  ldloc.s  4
0x5a69c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5a6a1  endfinally
0x5a6a2  leave.s  loc_5A6CF
0x5a6a4  stloc.s  5
0x5a6a6  ldarg.0
0x5a6a7  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5a6ac  dup
0x5a6ad  brtrue.s loc_5A6B2
0x5a6af  pop
0x5a6b0  br.s     loc_5A6CD
0x5a6b2  ldstr    aFailedToCacheC// "Failed to cache components: "
0x5a6b7  ldloc.s  5
0x5a6b9  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5a6be  call     string [mscorlib]System.String::Concat(string, string)
0x5a6c3  call     T0x2B000003
0x5a6c8  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x5a6cd  leave.s  loc_5A6CF
0x5a6cf  ret
```
