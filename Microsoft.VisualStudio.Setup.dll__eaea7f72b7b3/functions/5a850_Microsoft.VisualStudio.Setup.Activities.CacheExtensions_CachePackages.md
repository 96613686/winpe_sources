# Microsoft.VisualStudio.Setup.Activities.CacheExtensions::CachePackages

- ea: `0x5a850`
- end: `0x5a94a`
- name: `Microsoft.VisualStudio.Setup.Activities.CacheExtensions::CachePackages`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x5a730`

## callees

- `0x5a850`

## string_xrefs

- `0x5a8a6`: `Cached extension packages for `
- `0x5a8e0`: `Exception occurred while trying to cache packages for `
- `0x5a902`: `. Skipping to the next extension.`
- `0x5a927`: `Did not cache any extension packages for `
- `0x5a932`: ` since there are no packages to cache.`

## pseudocode

```c

```

## disassembly

```asm
0x5a850  ldarg.2
0x5a851  call     T0x2B0000AB
0x5a856  brtrue.s loc_5A8C9
0x5a858  ldarg.2
0x5a859  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::GetEnumerator()
0x5a85e  stloc.0
0x5a85f  br.s     loc_5A886
0x5a861  ldloc.0
0x5a862  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::get_Current()
0x5a867  isinst   [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage
0x5a86c  stloc.1
0x5a86d  ldloc.1
0x5a86e  brfalse.s loc_5A886
0x5a870  ldloc.1
0x5a871  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RequestedState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage::get_RequestedState()
0x5a876  ldc.i4.3
0x5a877  bne.un.s loc_5A886
0x5a879  ldarg.0
0x5a87a  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.ICacheManager Microsoft.VisualStudio.Setup.Activities.CacheExtensions::cacheManager
0x5a87f  ldloc.1
0x5a880  ldc.i4.0
0x5a881  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.ICacheManager::CachePackage(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage, bool)
0x5a886  ldloc.0
0x5a887  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5a88c  brtrue.s loc_5A861
0x5a88e  leave.s  loc_5A89A
0x5a890  ldloc.0
0x5a891  brfalse.s loc_5A899
0x5a893  ldloc.0
0x5a894  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5a899  endfinally
0x5a89a  ldarg.0
0x5a89b  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.CacheExtensions::logger
0x5a8a0  dup
0x5a8a1  brtrue.s loc_5A8A6
0x5a8a3  pop
0x5a8a4  br.s     loc_5A8C5
0x5a8a6  ldstr    aCachedExtensio// "Cached extension packages for "
0x5a8ab  ldarg.1
0x5a8ac  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::GetManifestId(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IManifest)
0x5a8b1  ldstr    asc_80DBA// "."
0x5a8b6  call     string [mscorlib]System.String::Concat(string, string, string)
0x5a8bb  call     T0x2B000003
0x5a8c0  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5a8c5  ldc.i4.1
0x5a8c6  stloc.2
0x5a8c7  leave.s  loc_5A948
0x5a8c9  leave.s  loc_5A91B
0x5a8cb  stloc.3
0x5a8cc  ldarg.0
0x5a8cd  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.CacheExtensions::logger
0x5a8d2  dup
0x5a8d3  brtrue.s loc_5A8D8
0x5a8d5  pop
0x5a8d6  br.s     loc_5A917
0x5a8d8  ldc.i4.5
0x5a8d9  newarr   [mscorlib]System.String
0x5a8de  dup
0x5a8df  ldc.i4.0
0x5a8e0  ldstr    aExceptionOccur_4// "Exception occurred while trying to cach"...
0x5a8e5  stelem.ref
0x5a8e6  dup
0x5a8e7  ldc.i4.1
0x5a8e8  ldarg.1
0x5a8e9  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::GetManifestId(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IManifest)
0x5a8ee  stelem.ref
0x5a8ef  dup
0x5a8f0  ldc.i4.2
0x5a8f1  ldstr    asc_82BA2// ": "
0x5a8f6  stelem.ref
0x5a8f7  dup
0x5a8f8  ldc.i4.3
0x5a8f9  ldloc.3
0x5a8fa  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5a8ff  stelem.ref
0x5a900  dup
0x5a901  ldc.i4.4
0x5a902  ldstr    aSkippingToTheN// ". Skipping to the next extension."
0x5a907  stelem.ref
0x5a908  call     string [mscorlib]System.String::Concat(string[])
0x5a90d  call     T0x2B000003
0x5a912  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5a917  ldc.i4.0
0x5a918  stloc.2
0x5a919  leave.s  loc_5A948
0x5a91b  ldarg.0
0x5a91c  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.CacheExtensions::logger
0x5a921  dup
0x5a922  brtrue.s loc_5A927
0x5a924  pop
0x5a925  br.s     loc_5A946
0x5a927  ldstr    aDidNotCacheAny// "Did not cache any extension packages fo"...
0x5a92c  ldarg.1
0x5a92d  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::GetManifestId(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IManifest)
0x5a932  ldstr    aSinceThereAreN// " since there are no packages to cache."
0x5a937  call     string [mscorlib]System.String::Concat(string, string, string)
0x5a93c  call     T0x2B000003
0x5a941  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5a946  ldc.i4.0
0x5a947  ret
0x5a948  ldloc.2
0x5a949  ret
```
