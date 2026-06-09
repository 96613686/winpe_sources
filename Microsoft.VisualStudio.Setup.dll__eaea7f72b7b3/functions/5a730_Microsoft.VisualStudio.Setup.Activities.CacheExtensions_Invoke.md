# Microsoft.VisualStudio.Setup.Activities.CacheExtensions::Invoke

- ea: `0x5a730`
- end: `0x5a84a`
- name: `Microsoft.VisualStudio.Setup.Activities.CacheExtensions::Invoke`
- size: `282`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x5a730`
- `0x5a850`
- `0x5a950`
- `0x7bdb0`

## string_xrefs

- `0x5a748`: `Skipping the extension caching since there are no extensions.`
- `0x5a788`: `Starting caching extension packages and manifest for `
- `0x5a812`: `Exception happened while caching extensions: `
- `0x5a83a`: `Finished caching extension packages and manifests for resume.`

## pseudocode

```c

```

## disassembly

```asm
0x5a730  ldarg.0
0x5a731  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog> Microsoft.VisualStudio.Setup.Activities.CacheExtensions::extensionManifests
0x5a736  call     T0x2B00028E
0x5a73b  brfalse.s loc_5A758
0x5a73d  ldarg.0
0x5a73e  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.CacheExtensions::logger
0x5a743  dup
0x5a744  brtrue.s loc_5A748
0x5a746  pop
0x5a747  ret
0x5a748  ldstr    aSkippingTheExt// "Skipping the extension caching since th"...
0x5a74d  call     T0x2B000003
0x5a752  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5a757  ret
0x5a758  nop
0x5a759  ldarg.0
0x5a75a  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog> Microsoft.VisualStudio.Setup.Activities.CacheExtensions::extensionManifests
0x5a75f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog>::GetEnumerator()
0x5a764  stloc.0
0x5a765  br       loc_5A7EB
0x5a76a  newobj   instance void <>c__DisplayClass6_0::.ctor()
0x5a76f  stloc.1
0x5a770  ldloc.1
0x5a771  ldloc.0
0x5a772  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog>::get_Current()
0x5a777  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog <>c__DisplayClass6_0::manifest
0x5a77c  ldarg.0
0x5a77d  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.CacheExtensions::logger
0x5a782  dup
0x5a783  brtrue.s loc_5A788
0x5a785  pop
0x5a786  br.s     loc_5A7AC
0x5a788  ldstr    aStartingCachin// "Starting caching extension packages and"...
0x5a78d  ldloc.1
0x5a78e  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog <>c__DisplayClass6_0::manifest
0x5a793  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::GetManifestId(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IManifest)
0x5a798  ldstr    asc_80DBA// "."
0x5a79d  call     string [mscorlib]System.String::Concat(string, string, string)
0x5a7a2  call     T0x2B000003
0x5a7a7  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5a7ac  ldarg.0
0x5a7ad  ldfld    class [System]System.Collections.Generic.ISet`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage> Microsoft.VisualStudio.Setup.Activities.CacheExtensions::plannedPackages
0x5a7b2  ldloc.1
0x5a7b3  ldftn    instance bool <>c__DisplayClass6_0::<Invoke>b__0(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage x)
0x5a7b9  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage, bool>::.ctor(object, native int)
0x5a7be  call     T0x2B000012
0x5a7c3  dup
0x5a7c4  brtrue.s loc_5A7CA
0x5a7c6  pop
0x5a7c7  ldnull
0x5a7c8  br.s     loc_5A7CF
0x5a7ca  call     T0x2B00028F
0x5a7cf  stloc.2
0x5a7d0  ldarg.0
0x5a7d1  ldloc.1
0x5a7d2  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog <>c__DisplayClass6_0::manifest
0x5a7d7  ldloc.2
0x5a7d8  call     instance bool Microsoft.VisualStudio.Setup.Activities.CacheExtensions::CachePackages(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog manifest, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage> packagesToCache)
0x5a7dd  stloc.3
0x5a7de  ldarg.0
0x5a7df  ldloc.3
0x5a7e0  ldloc.1
0x5a7e1  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog <>c__DisplayClass6_0::manifest
0x5a7e6  call     instance void Microsoft.VisualStudio.Setup.Activities.CacheExtensions::CacheManifest(bool cached, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog manifest)
0x5a7eb  ldloc.0
0x5a7ec  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5a7f1  brtrue   loc_5A76A
0x5a7f6  leave.s  loc_5A802
0x5a7f8  ldloc.0
0x5a7f9  brfalse.s loc_5A801
0x5a7fb  ldloc.0
0x5a7fc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5a801  endfinally
0x5a802  leave.s  loc_5A82F
0x5a804  stloc.s  4
0x5a806  ldarg.0
0x5a807  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.CacheExtensions::logger
0x5a80c  dup
0x5a80d  brtrue.s loc_5A812
0x5a80f  pop
0x5a810  br.s     loc_5A82D
0x5a812  ldstr    aExceptionHappe// "Exception happened while caching extens"...
0x5a817  ldloc.s  4
0x5a819  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5a81e  call     string [mscorlib]System.String::Concat(string, string)
0x5a823  call     T0x2B000003
0x5a828  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5a82d  leave.s  loc_5A82F
0x5a82f  ldarg.0
0x5a830  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.CacheExtensions::logger
0x5a835  dup
0x5a836  brtrue.s loc_5A83A
0x5a838  pop
0x5a839  ret
0x5a83a  ldstr    aFinishedCachin// "Finished caching extension packages and"...
0x5a83f  call     T0x2B000003
0x5a844  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5a849  ret
```
