# System.IO.Packaging.PackWebRequest::GetResponse

- ea: `0x14350`
- end: `0x14429`
- name: `System.IO.Packaging.PackWebRequest::GetResponse`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x14350`
- `0x14630`
- `0x146b0`
- `0x14740`
- `0x14800`
- `0x146e40`

## string_xrefs

- `0x1439c`: `ResourceNotFoundUnderCacheOnlyPolicy`
- `0x143ac`: `PackWebRequestCachePolicyIllegal`

## pseudocode

```c

```

## disassembly

```asm
0x14350  ldarg.0
0x14351  call     instance bool System.IO.Packaging.PackWebRequest::get_IsCachedPackage()
0x14356  stloc.0
0x14357  ldloc.0
0x14358  brfalse.s loc_14365
0x1435a  ldloc.0
0x1435b  brfalse.s loc_143BC
0x1435d  ldarg.0
0x1435e  ldfld    bool System.IO.Packaging.PackWebRequest::_respectCachePolicy
0x14363  brfalse.s loc_143BC
0x14365  ldarg.0
0x14366  ldfld    class [System]System.Net.Cache.RequestCachePolicy System.IO.Packaging.PackWebRequest::_cachePolicy
0x1436b  callvirt instance valuetype [System]System.Net.Cache.RequestCacheLevel [System]System.Net.Cache.RequestCachePolicy::get_Level()
0x14370  stloc.1
0x14371  ldloc.1
0x14372  brtrue.s loc_1437F
0x14374  ldsfld   class [System]System.Net.Cache.RequestCachePolicy System.IO.Packaging.PackWebRequest::_defaultCachePolicy
0x14379  callvirt instance valuetype [System]System.Net.Cache.RequestCacheLevel [System]System.Net.Cache.RequestCachePolicy::get_Level()
0x1437e  stloc.1
0x1437f  ldloc.1
0x14380  ldc.i4.1
0x14381  sub
0x14382  switch   loc_14395, loc_14399, loc_143BC
0x14393  br.s     loc_143AC
0x14395  ldc.i4.0
0x14396  stloc.0
0x14397  br.s     loc_143BC
0x14399  ldloc.0
0x1439a  brtrue.s loc_143BC
0x1439c  ldstr    aResourcenotfou// "ResourceNotFoundUnderCacheOnlyPolicy"
0x143a1  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x143a6  newobj   instance void [System]System.Net.WebException::.ctor(string)
0x143ab  throw
0x143ac  ldstr    aPackwebrequest// "PackWebRequestCachePolicyIllegal"
0x143b1  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x143b6  newobj   instance void [System]System.Net.WebException::.ctor(string)
0x143bb  throw
0x143bc  ldloc.0
0x143bd  brfalse.s loc_143E3
0x143bf  ldarg.0
0x143c0  ldfld    class [System]System.Uri System.IO.Packaging.PackWebRequest::_uri
0x143c5  ldarg.0
0x143c6  ldfld    class [System]System.Uri System.IO.Packaging.PackWebRequest::_innerUri
0x143cb  ldarg.0
0x143cc  ldfld    class [System]System.Uri System.IO.Packaging.PackWebRequest::_partName
0x143d1  ldarg.0
0x143d2  ldfld    class [WindowsBase]System.IO.Packaging.Package System.IO.Packaging.PackWebRequest::_cacheEntry
0x143d7  ldarg.0
0x143d8  ldfld    bool System.IO.Packaging.PackWebRequest::_cachedPackageIsThreadSafe
0x143dd  newobj   instance void System.IO.Packaging.PackWebResponse::.ctor(class [System]System.Uri uri, class [System]System.Uri innerUri, class [System]System.Uri partName, class [WindowsBase]System.IO.Packaging.Package cacheEntry, bool cachedPackageIsThreadSafe)
0x143e2  ret
0x143e3  ldarg.0
0x143e4  ldc.i4.0
0x143e5  call     instance class [System]System.Net.WebRequest System.IO.Packaging.PackWebRequest::GetRequest(bool allowPseudoRequest)
0x143ea  stloc.2
0x143eb  ldarg.0
0x143ec  ldfld    class [System]System.Net.WebRequest System.IO.Packaging.PackWebRequest::_webRequest
0x143f1  brfalse.s loc_14400
0x143f3  ldarg.0
0x143f4  ldfld    class [System]System.Net.WebRequest System.IO.Packaging.PackWebRequest::_webRequest
0x143f9  isinst   MS.Internal.IO.Packaging.PseudoWebRequest
0x143fe  brfalse.s loc_14410
0x14400  ldstr    aSchemainvalidf// "SchemaInvalidForTransport"
0x14405  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x1440a  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1440f  throw
0x14410  ldarg.0
0x14411  ldfld    class [System]System.Uri System.IO.Packaging.PackWebRequest::_uri
0x14416  ldarg.0
0x14417  ldfld    class [System]System.Uri System.IO.Packaging.PackWebRequest::_innerUri
0x1441c  ldarg.0
0x1441d  ldfld    class [System]System.Uri System.IO.Packaging.PackWebRequest::_partName
0x14422  ldloc.2
0x14423  newobj   instance void System.IO.Packaging.PackWebResponse::.ctor(class [System]System.Uri uri, class [System]System.Uri innerUri, class [System]System.Uri partName, class [System]System.Net.WebRequest innerRequest)
0x14428  ret
```
