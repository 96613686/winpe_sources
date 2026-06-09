# Microsoft.VisualStudio.Setup.Activities.CacheExtensions::CacheManifest

- ea: `0x5a950`
- end: `0x5aa08`
- name: `Microsoft.VisualStudio.Setup.Activities.CacheExtensions::CacheManifest`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x5a730`

## callees

- `0x5a950`

## string_xrefs

- `0x5a9f0`: `. Skipping to the next extension.`
- `0x5a96b`: `Cached the extension manifest for `
- `0x5a998`: `Did not cache the extension manifest for `
- `0x5a9a3`: ` since the packages for the extension were not cached.`
- `0x5a9ce`: `Exception occurred while trying to cache manifest for `

## pseudocode

```c

```

## disassembly

```asm
0x5a950  ldarg.1
0x5a951  brfalse.s loc_5A98C
0x5a953  ldarg.0
0x5a954  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.ICacheManager Microsoft.VisualStudio.Setup.Activities.CacheExtensions::cacheManager
0x5a959  ldarg.2
0x5a95a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.ICacheManager::AddExtensionCatalog(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog)
0x5a95f  ldarg.0
0x5a960  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.CacheExtensions::logger
0x5a965  dup
0x5a966  brtrue.s loc_5A96B
0x5a968  pop
0x5a969  br.s     loc_5A9B7
0x5a96b  ldstr    aCachedTheExten// "Cached the extension manifest for "
0x5a970  ldarg.2
0x5a971  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::GetManifestId(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IManifest)
0x5a976  ldstr    asc_80DBA// "."
0x5a97b  call     string [mscorlib]System.String::Concat(string, string, string)
0x5a980  call     T0x2B000003
0x5a985  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5a98a  br.s     loc_5A9B7
0x5a98c  ldarg.0
0x5a98d  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.CacheExtensions::logger
0x5a992  dup
0x5a993  brtrue.s loc_5A998
0x5a995  pop
0x5a996  br.s     loc_5A9B7
0x5a998  ldstr    aDidNotCacheThe// "Did not cache the extension manifest fo"...
0x5a99d  ldarg.2
0x5a99e  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::GetManifestId(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IManifest)
0x5a9a3  ldstr    aSinceThePackag// " since the packages for the extension w"...
0x5a9a8  call     string [mscorlib]System.String::Concat(string, string, string)
0x5a9ad  call     T0x2B000003
0x5a9b2  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5a9b7  leave.s  loc_5AA07
0x5a9b9  stloc.0
0x5a9ba  ldarg.0
0x5a9bb  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.CacheExtensions::logger
0x5a9c0  dup
0x5a9c1  brtrue.s loc_5A9C6
0x5a9c3  pop
0x5a9c4  br.s     loc_5AA05
0x5a9c6  ldc.i4.5
0x5a9c7  newarr   [mscorlib]System.String
0x5a9cc  dup
0x5a9cd  ldc.i4.0
0x5a9ce  ldstr    aExceptionOccur_5// "Exception occurred while trying to cach"...
0x5a9d3  stelem.ref
0x5a9d4  dup
0x5a9d5  ldc.i4.1
0x5a9d6  ldarg.2
0x5a9d7  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::GetManifestId(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IManifest)
0x5a9dc  stelem.ref
0x5a9dd  dup
0x5a9de  ldc.i4.2
0x5a9df  ldstr    asc_82BA2// ": "
0x5a9e4  stelem.ref
0x5a9e5  dup
0x5a9e6  ldc.i4.3
0x5a9e7  ldloc.0
0x5a9e8  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5a9ed  stelem.ref
0x5a9ee  dup
0x5a9ef  ldc.i4.4
0x5a9f0  ldstr    aSkippingToTheN// ". Skipping to the next extension."
0x5a9f5  stelem.ref
0x5a9f6  call     string [mscorlib]System.String::Concat(string[])
0x5a9fb  call     T0x2B000003
0x5aa00  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5aa05  leave.s  loc_5AA07
0x5aa07  ret
```
