# System.IO.Packaging.PackWebRequest::set_CachePolicy

- ea: `0x14440`
- end: `0x14482`
- name: `System.IO.Packaging.PackWebRequest::set_CachePolicy`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14440`
- `0x146e40`

## string_xrefs

- `0x1446a`: `PackWebRequestCachePolicyIllegal`

## pseudocode

```c

```

## disassembly

```asm
0x14440  ldarg.1
0x14441  brtrue.s loc_1444F
0x14443  ldarg.0
0x14444  ldsfld   class [System]System.Net.Cache.RequestCachePolicy System.IO.Packaging.PackWebRequest::_defaultCachePolicy
0x14449  stfld    class [System]System.Net.Cache.RequestCachePolicy System.IO.Packaging.PackWebRequest::_cachePolicy
0x1444e  ret
0x1444f  ldarg.1
0x14450  callvirt instance valuetype [System]System.Net.Cache.RequestCacheLevel [System]System.Net.Cache.RequestCachePolicy::get_Level()
0x14455  stloc.0
0x14456  ldloc.0
0x14457  ldc.i4.1
0x14458  sub
0x14459  switch   loc_1447A, loc_1447A, loc_1447A
0x1446a  ldstr    aPackwebrequest// "PackWebRequestCachePolicyIllegal"
0x1446f  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x14474  newobj   instance void [System]System.Net.WebException::.ctor(string)
0x14479  throw
0x1447a  ldarg.0
0x1447b  ldarg.1
0x1447c  stfld    class [System]System.Net.Cache.RequestCachePolicy System.IO.Packaging.PackWebRequest::_cachePolicy
0x14481  ret
```
