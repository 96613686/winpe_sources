# System.IO.Packaging.PackWebRequestFactory::System.Net.IWebRequestCreate.Create

- ea: `0x141e0`
- end: `0x1428d`
- name: `System.IO.Packaging.PackWebRequestFactory::System.Net.IWebRequestCreate.Create`
- size: `173`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x141e0`
- `0x142f0`
- `0x14300`
- `0x14e00`
- `0x133d20`
- `0x146e40`
- `0x146e70`

## string_xrefs

- `0x141fc`: `UriMustBeAbsolute`
- `0x14224`: `UriSchemeMismatch`

## pseudocode

```c

```

## disassembly

```asm
0x141e0  ldarg.1
0x141e1  ldnull
0x141e2  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x141e7  brfalse.s loc_141F4
0x141e9  ldstr    aUri// "uri"
0x141ee  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x141f3  throw
0x141f4  ldarg.1
0x141f5  callvirt instance bool [System]System.Uri::get_IsAbsoluteUri()
0x141fa  brtrue.s loc_14211
0x141fc  ldstr    aUrimustbeabsol// "UriMustBeAbsolute"
0x14201  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x14206  ldstr    aUri// "uri"
0x1420b  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x14210  throw
0x14211  ldarg.1
0x14212  callvirt instance string [System]System.Uri::get_Scheme()
0x14217  ldsfld   string [WindowsBase]System.IO.Packaging.PackUriHelper::UriSchemePack
0x1421c  ldc.i4.4
0x1421d  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x14222  brfalse.s loc_14247
0x14224  ldstr    aUrischememisma// "UriSchemeMismatch"
0x14229  ldc.i4.1
0x1422a  newarr   [mscorlib]System.Object
0x1422f  dup
0x14230  ldc.i4.0
0x14231  ldsfld   string [WindowsBase]System.IO.Packaging.PackUriHelper::UriSchemePack
0x14236  stelem.ref
0x14237  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x1423c  ldstr    aUri// "uri"
0x14241  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x14246  throw
0x14247  ldarg.1
0x14248  ldloca.s 1
0x1424a  ldloca.s 2
0x1424c  call     void [WindowsBase]System.IO.Packaging.PackUriHelper::ValidateAndGetPackUriComponents(class [System]System.Uri, class [System]System.Uri&, class [System]System.Uri&)
0x14251  ldloc.2
0x14252  ldnull
0x14253  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x14258  brfalse.s loc_14284
0x1425a  ldloc.1
0x1425b  ldloca.s 4
0x1425d  call     class [WindowsBase]System.IO.Packaging.Package MS.Internal.IO.Packaging.PreloadedPackages::GetPackage(class [System]System.Uri uri, [out] bool& threadSafe)
0x14262  stloc.0
0x14263  ldc.i4.0
0x14264  stloc.3
0x14265  ldloc.0
0x14266  brtrue.s loc_14274
0x14268  ldc.i4.0
0x14269  stloc.s  4
0x1426b  ldc.i4.1
0x1426c  stloc.3
0x1426d  ldloc.1
0x1426e  call     class [WindowsBase]System.IO.Packaging.Package System.IO.Packaging.PackageStore::GetPackage(class [System]System.Uri uri)
0x14273  stloc.0
0x14274  ldloc.0
0x14275  brfalse.s loc_14284
0x14277  ldarg.1
0x14278  ldloc.1
0x14279  ldloc.2
0x1427a  ldloc.0
0x1427b  ldloc.3
0x1427c  ldloc.s  4
0x1427e  newobj   instance void System.IO.Packaging.PackWebRequest::.ctor(class [System]System.Uri uri, class [System]System.Uri packageUri, class [System]System.Uri partUri, class [WindowsBase]System.IO.Packaging.Package cacheEntry, bool respectCachePolicy, bool cachedPackageIsThreadSafe)
0x14283  ret
0x14284  ldarg.1
0x14285  ldloc.1
0x14286  ldloc.2
0x14287  newobj   instance void System.IO.Packaging.PackWebRequest::.ctor(class [System]System.Uri uri, class [System]System.Uri packageUri, class [System]System.Uri partUri)
0x1428c  ret
```
