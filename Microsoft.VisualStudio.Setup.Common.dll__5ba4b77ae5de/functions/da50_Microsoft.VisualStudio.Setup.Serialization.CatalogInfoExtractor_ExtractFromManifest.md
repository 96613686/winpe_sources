# Microsoft.VisualStudio.Setup.Serialization.CatalogInfoExtractor::ExtractFromManifest

- ea: `0xda50`
- end: `0xdabb`
- name: `Microsoft.VisualStudio.Setup.Serialization.CatalogInfoExtractor::ExtractFromManifest`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x2ae0`

## callees

- `0xda50`
- `0xdac0`
- `0x10210`
- `0x11900`
- `0x11970`

## pseudocode

```c

```

## disassembly

```asm
0xda50  ldarg.0
0xda51  ldfld    class Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Serialization.CatalogInfoExtractor::fileSystem
0xda56  ldarg.1
0xda57  callvirt instance bool Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string path)
0xda5c  brtrue.s loc_DA75
0xda5e  ldstr    aFile// "File "
0xda63  ldarg.1
0xda64  ldstr    aDoesNotExist// " does not exist."
0xda69  call     string [mscorlib]System.String::Concat(string, string, string)
0xda6e  ldarg.1
0xda6f  newobj   instance void [mscorlib]System.IO.FileNotFoundException::.ctor(string, string)
0xda74  throw
0xda75  ldarg.0
0xda76  ldfld    class Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Serialization.CatalogInfoExtractor::fileSystem
0xda7b  ldarg.1
0xda7c  callvirt instance class [mscorlib]System.IO.TextReader Microsoft.VisualStudio.Setup.Services.IFileSystem::OpenText(string path)
0xda81  stloc.0
0xda82  ldloc.0
0xda83  newobj   instance void Microsoft.VisualStudio.Setup.Serialization.OptimizedJsonTextReader::.ctor(class [mscorlib]System.IO.TextReader reader)
0xda88  stloc.1
0xda89  ldarg.0
0xda8a  ldloc.1
0xda8b  call     instance bool Microsoft.VisualStudio.Setup.Serialization.CatalogInfoExtractor::FindCatalogInfo(class [Newtonsoft.Json]Newtonsoft.Json.JsonTextReader reader)
0xda90  brfalse.s loc_DAA1
0xda92  ldnull
0xda93  newobj   instance void class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<class Microsoft.VisualStudio.Setup.CatalogInfo>::.ctor(class [mscorlib]System.IServiceProvider)
0xda98  ldloc.1
0xda99  callvirt instance var<u1> class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<class Microsoft.VisualStudio.Setup.CatalogInfo>::Deserialize(!!T0)
0xda9e  stloc.2
0xda9f  leave.s  loc_DAB9
0xdaa1  leave.s  loc_DAB7
0xdaa3  ldloc.1
0xdaa4  brfalse.s loc_DAAC
0xdaa6  ldloc.1
0xdaa7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdaac  endfinally
0xdaad  ldloc.0
0xdaae  brfalse.s loc_DAB6
0xdab0  ldloc.0
0xdab1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdab6  endfinally
0xdab7  ldnull
0xdab8  ret
0xdab9  ldloc.2
0xdaba  ret
```
