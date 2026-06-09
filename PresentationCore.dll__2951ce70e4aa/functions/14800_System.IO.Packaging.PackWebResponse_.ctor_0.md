# System.IO.Packaging.PackWebResponse::.ctor_0

- ea: `0x14800`
- end: `0x14889`
- name: `System.IO.Packaging.PackWebResponse::.ctor_0`
- size: `137`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14350`

## callees

- `0x14800`
- `0x147370`

## string_xrefs

- `0x1482e`: `innerUri`
- `0x14851`: `cacheEntry`

## pseudocode

```c

```

## disassembly

```asm
0x14800  ldarg.0
0x14801  call     instance void [System]System.Net.WebResponse::.ctor()
0x14806  ldarg.0
0x14807  newobj   instance void [mscorlib]System.Object::.ctor()
0x1480c  stfld    object System.IO.Packaging.PackWebResponse::_lockObject
0x14811  ldarg.1
0x14812  ldnull
0x14813  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x14818  brfalse.s loc_14825
0x1481a  ldstr    aUri// "uri"
0x1481f  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x14824  throw
0x14825  ldarg.2
0x14826  ldnull
0x14827  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x1482c  brfalse.s loc_14839
0x1482e  ldstr    aInneruri// "innerUri"
0x14833  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x14838  throw
0x14839  ldarg.3
0x1483a  ldnull
0x1483b  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x14840  brfalse.s loc_1484D
0x14842  ldstr    aPartname// "partName"
0x14847  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1484c  throw
0x1484d  ldarg.s  4
0x1484f  brtrue.s loc_1485C
0x14851  ldstr    aCacheentry// "cacheEntry"
0x14856  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1485b  throw
0x1485c  ldarg.0
0x1485d  ldarg.1
0x1485e  stfld    class [System]System.Uri System.IO.Packaging.PackWebResponse::_uri
0x14863  ldarg.0
0x14864  ldarg.2
0x14865  stfld    class [System]System.Uri System.IO.Packaging.PackWebResponse::_innerUri
0x1486a  ldarg.0
0x1486b  ldarg.3
0x1486c  stfld    class [System]System.Uri System.IO.Packaging.PackWebResponse::_partName
0x14871  ldarg.0
0x14872  ldnull
0x14873  stfld    class [WindowsBase]MS.Internal.ContentType System.IO.Packaging.PackWebResponse::_mimeType
0x14878  ldarg.0
0x14879  ldarg.0
0x1487a  ldarg.s  4
0x1487c  ldarg.s  5
0x1487e  newobj   instance void CachedResponse::.ctor(class System.IO.Packaging.PackWebResponse parent, class [WindowsBase]System.IO.Packaging.Package cacheEntry, bool cachedPackageIsThreadSafe)
0x14883  stfld    class CachedResponse System.IO.Packaging.PackWebResponse::_cachedResponse
0x14888  ret
```
