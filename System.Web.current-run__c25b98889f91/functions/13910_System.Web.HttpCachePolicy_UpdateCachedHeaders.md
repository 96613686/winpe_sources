# System.Web.HttpCachePolicy::UpdateCachedHeaders

- ea: `0x13910`
- end: `0x13d16`
- name: `System.Web.HttpCachePolicy::UpdateCachedHeaders`
- size: `1030`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, installer_update`

## callers

- `0x13d20`
- `0x13f00`

## callees

- `0x129c0`
- `0x12b70`
- `0x137c0`
- `0x13820`
- `0x13910`
- `0x149b0`
- `0x16a10`
- `0x188d0`
- `0x18910`
- `0x1dd50`
- `0x21b60`
- `0x26580`
- `0x14f100`
- `0x1565e0`
- `0x156b00`

## string_xrefs

- `0x13a6b`: `no-cache="`
- `0x13bb7`: `no-cache`

## pseudocode

```c

```

## disassembly

```asm
0x13910  ldarg.0
0x13911  ldfld    bool System.Web.HttpCachePolicy::_useCachedHeaders
0x13916  brfalse.s loc_13919
0x13918  ret
0x13919  ldarg.0
0x1391a  ldfld    valuetype [mscorlib]System.DateTime System.Web.HttpCachePolicy::_utcTimestampCreated
0x1391f  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x13924  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x13929  brfalse.s loc_1393C
0x1392b  ldarg.0
0x1392c  ldarg.1
0x1392d  callvirt instance class System.Web.HttpContext System.Web.HttpResponse::get_Context()
0x13932  callvirt instance valuetype [mscorlib]System.DateTime System.Web.HttpContext::get_UtcTimestamp()
0x13937  stfld    valuetype [mscorlib]System.DateTime System.Web.HttpCachePolicy::_utcTimestampCreated
0x1393c  ldarg.0
0x1393d  ldarg.1
0x1393e  callvirt instance class System.Web.HttpContext System.Web.HttpResponse::get_Context()
0x13943  callvirt instance valuetype [mscorlib]System.DateTime System.Web.HttpContext::get_UtcTimestamp()
0x13948  stfld    valuetype [mscorlib]System.DateTime System.Web.HttpCachePolicy::_utcTimestampRequest
0x1394d  ldarg.0
0x1394e  ldfld    int32 System.Web.HttpCachePolicy::_slidingExpiration
0x13953  ldc.i4.1
0x13954  beq.s    loc_13963
0x13956  ldarg.0
0x13957  ldsfld   valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Zero
0x1395c  stfld    valuetype [mscorlib]System.TimeSpan System.Web.HttpCachePolicy::_slidingDelta
0x13961  br.s     loc_139A5
0x13963  ldarg.0
0x13964  ldfld    bool System.Web.HttpCachePolicy::_isMaxAgeSet
0x13969  brfalse.s loc_13979
0x1396b  ldarg.0
0x1396c  ldarg.0
0x1396d  ldfld    valuetype [mscorlib]System.TimeSpan System.Web.HttpCachePolicy::_maxAge
0x13972  stfld    valuetype [mscorlib]System.TimeSpan System.Web.HttpCachePolicy::_slidingDelta
0x13977  br.s     loc_139A5
0x13979  ldarg.0
0x1397a  ldfld    bool System.Web.HttpCachePolicy::_isExpiresSet
0x1397f  brfalse.s loc_1399A
0x13981  ldarg.0
0x13982  ldarg.0
0x13983  ldfld    valuetype [mscorlib]System.DateTime System.Web.HttpCachePolicy::_utcExpires
0x13988  ldarg.0
0x13989  ldfld    valuetype [mscorlib]System.DateTime System.Web.HttpCachePolicy::_utcTimestampCreated
0x1398e  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x13993  stfld    valuetype [mscorlib]System.TimeSpan System.Web.HttpCachePolicy::_slidingDelta
0x13998  br.s     loc_139A5
0x1399a  ldarg.0
0x1399b  ldsfld   valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Zero
0x139a0  stfld    valuetype [mscorlib]System.TimeSpan System.Web.HttpCachePolicy::_slidingDelta
0x139a5  ldarg.0
0x139a6  ldnull
0x139a7  stfld    class System.Web.HttpResponseHeader System.Web.HttpCachePolicy::_headerCacheControl
0x139ac  ldarg.0
0x139ad  ldnull
0x139ae  stfld    class System.Web.HttpResponseHeader System.Web.HttpCachePolicy::_headerPragma
0x139b3  ldarg.0
0x139b4  ldnull
0x139b5  stfld    class System.Web.HttpResponseHeader System.Web.HttpCachePolicy::_headerExpires
0x139ba  ldarg.0
0x139bb  ldnull
0x139bc  stfld    class System.Web.HttpResponseHeader System.Web.HttpCachePolicy::_headerLastModified
0x139c1  ldarg.0
0x139c2  ldnull
0x139c3  stfld    class System.Web.HttpResponseHeader System.Web.HttpCachePolicy::_headerEtag
0x139c8  ldarg.0
0x139c9  ldnull
0x139ca  stfld    class System.Web.HttpResponseHeader System.Web.HttpCachePolicy::_headerVaryBy
0x139cf  ldarg.0
0x139d0  ldarg.1
0x139d1  call     instance void System.Web.HttpCachePolicy::UpdateFromDependencies(class System.Web.HttpResponse response)
0x139d6  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x139db  stloc.0
0x139dc  ldarg.0
0x139dd  ldfld    valuetype System.Web.HttpCacheability System.Web.HttpCachePolicy::_cacheability
0x139e2  ldc.i4.6
0x139e3  bne.un.s loc_139E9
0x139e5  ldc.i4.2
0x139e6  stloc.1
0x139e7  br.s     loc_139F0
0x139e9  ldarg.0
0x139ea  ldfld    valuetype System.Web.HttpCacheability System.Web.HttpCachePolicy::_cacheability
0x139ef  stloc.1
0x139f0  ldloc.0
0x139f1  ldsfld   string[] System.Web.HttpCachePolicy::s_cacheabilityTokens
0x139f6  ldloc.1
0x139f7  ldelem.ref
0x139f8  call     void System.Web.HttpCachePolicy::AppendValueToHeader(class [mscorlib]System.Text.StringBuilder s, string value)
0x139fd  ldloc.1
0x139fe  ldc.i4.4
0x139ff  bne.un.s loc_13A5A
0x13a01  ldarg.0
0x13a02  ldfld    class System.Web.HttpDictionary System.Web.HttpCachePolicy::_privateFields
0x13a07  brfalse.s loc_13A5A
0x13a09  ldloc.0
0x13a0a  ldstr    aPrivate// "private=\""
0x13a0f  call     void System.Web.HttpCachePolicy::AppendValueToHeader(class [mscorlib]System.Text.StringBuilder s, string value)
0x13a14  ldloc.0
0x13a15  ldarg.0
0x13a16  ldfld    class System.Web.HttpDictionary System.Web.HttpCachePolicy::_privateFields
0x13a1b  ldc.i4.0
0x13a1c  callvirt instance string System.Web.HttpDictionary::GetKey(int32 index)
0x13a21  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x13a26  pop
0x13a27  ldc.i4.1
0x13a28  stloc.2
0x13a29  ldarg.0
0x13a2a  ldfld    class System.Web.HttpDictionary System.Web.HttpCachePolicy::_privateFields
0x13a2f  callvirt instance int32 System.Web.HttpDictionary::get_Size()
0x13a34  stloc.3
0x13a35  br.s     loc_13A4D
0x13a37  ldloc.0
0x13a38  ldarg.0
0x13a39  ldfld    class System.Web.HttpDictionary System.Web.HttpCachePolicy::_privateFields
0x13a3e  ldloc.2
0x13a3f  callvirt instance string System.Web.HttpDictionary::GetKey(int32 index)
0x13a44  call     void System.Web.HttpCachePolicy::AppendValueToHeader(class [mscorlib]System.Text.StringBuilder s, string value)
0x13a49  ldloc.2
0x13a4a  ldc.i4.1
0x13a4b  add
0x13a4c  stloc.2
0x13a4d  ldloc.2
0x13a4e  ldloc.3
0x13a4f  blt.s    loc_13A37
0x13a51  ldloc.0
0x13a52  ldc.i4.s 0x22
0x13a54  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x13a59  pop
0x13a5a  ldloc.1
0x13a5b  ldc.i4.1
0x13a5c  beq.s    loc_13ABB
0x13a5e  ldloc.1
0x13a5f  ldc.i4.3
0x13a60  beq.s    loc_13ABB
0x13a62  ldarg.0
0x13a63  ldfld    class System.Web.HttpDictionary System.Web.HttpCachePolicy::_noCacheFields
0x13a68  brfalse.s loc_13ABB
0x13a6a  ldloc.0
0x13a6b  ldstr    aNoCache// "no-cache=\""
0x13a70  call     void System.Web.HttpCachePolicy::AppendValueToHeader(class [mscorlib]System.Text.StringBuilder s, string value)
0x13a75  ldloc.0
0x13a76  ldarg.0
0x13a77  ldfld    class System.Web.HttpDictionary System.Web.HttpCachePolicy::_noCacheFields
0x13a7c  ldc.i4.0
0x13a7d  callvirt instance string System.Web.HttpDictionary::GetKey(int32 index)
0x13a82  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x13a87  pop
0x13a88  ldc.i4.1
0x13a89  stloc.2
0x13a8a  ldarg.0
0x13a8b  ldfld    class System.Web.HttpDictionary System.Web.HttpCachePolicy::_noCacheFields
0x13a90  callvirt instance int32 System.Web.HttpDictionary::get_Size()
0x13a95  stloc.3
0x13a96  br.s     loc_13AAE
0x13a98  ldloc.0
0x13a99  ldarg.0
0x13a9a  ldfld    class System.Web.HttpDictionary System.Web.HttpCachePolicy::_noCacheFields
0x13a9f  ldloc.2
0x13aa0  callvirt instance string System.Web.HttpDictionary::GetKey(int32 index)
0x13aa5  call     void System.Web.HttpCachePolicy::AppendValueToHeader(class [mscorlib]System.Text.StringBuilder s, string value)
0x13aaa  ldloc.2
0x13aab  ldc.i4.1
0x13aac  add
0x13aad  stloc.2
0x13aae  ldloc.2
0x13aaf  ldloc.3
0x13ab0  blt.s    loc_13A98
0x13ab2  ldloc.0
0x13ab3  ldc.i4.s 0x22
0x13ab5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x13aba  pop
0x13abb  ldarg.0
0x13abc  ldfld    bool System.Web.HttpCachePolicy::_noStore
0x13ac1  brfalse.s loc_13ACE
0x13ac3  ldloc.0
0x13ac4  ldstr    aNoStore// "no-store"
0x13ac9  call     void System.Web.HttpCachePolicy::AppendValueToHeader(class [mscorlib]System.Text.StringBuilder s, string value)
0x13ace  ldloc.0
0x13acf  ldsfld   string[] System.Web.HttpCachePolicy::s_revalidationTokens
0x13ad4  ldarg.0
0x13ad5  ldfld    valuetype System.Web.HttpCacheRevalidation System.Web.HttpCachePolicy::_revalidation
0x13ada  ldelem.ref
0x13adb  call     void System.Web.HttpCachePolicy::AppendValueToHeader(class [mscorlib]System.Text.StringBuilder s, string value)
0x13ae0  ldarg.0
0x13ae1  ldfld    bool System.Web.HttpCachePolicy::_noTransforms
0x13ae6  brfalse.s loc_13AF3
0x13ae8  ldloc.0
0x13ae9  ldstr    aNoTransform// "no-transform"
0x13aee  call     void System.Web.HttpCachePolicy::AppendValueToHeader(class [mscorlib]System.Text.StringBuilder s, string value)
0x13af3  ldarg.0
0x13af4  ldfld    string System.Web.HttpCachePolicy::_cacheExtension
0x13af9  brfalse.s loc_13B07
0x13afb  ldloc.0
0x13afc  ldarg.0
0x13afd  ldfld    string System.Web.HttpCachePolicy::_cacheExtension
0x13b02  call     void System.Web.HttpCachePolicy::AppendValueToHeader(class [mscorlib]System.Text.StringBuilder s, string value)
0x13b07  ldarg.0
0x13b08  ldfld    int32 System.Web.HttpCachePolicy::_slidingExpiration
0x13b0d  ldc.i4.1
0x13b0e  bne.un.s loc_13B8C
0x13b10  ldloc.1
0x13b11  ldc.i4.1
0x13b12  beq.s    loc_13B8C
0x13b14  ldloc.1
0x13b15  ldc.i4.3
0x13b16  beq.s    loc_13B8C
0x13b18  ldarg.0
0x13b19  ldfld    bool System.Web.HttpCachePolicy::_isMaxAgeSet
0x13b1e  brfalse.s loc_13B52
0x13b20  ldarg.0
0x13b21  ldfld    bool System.Web.HttpCachePolicy::_noMaxAgeInCacheControl
0x13b26  brtrue.s loc_13B52
0x13b28  ldloc.0
0x13b29  ldstr    aMaxAge// "max-age="
0x13b2e  ldarg.0
0x13b2f  ldflda   valuetype [mscorlib]System.TimeSpan System.Web.HttpCachePolicy::_maxAge
0x13b34  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x13b39  conv.i8
0x13b3a  stloc.s  8
0x13b3c  ldloca.s 8
0x13b3e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13b43  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x13b48  call     string [mscorlib]System.String::Concat(string, string)
0x13b4d  call     void System.Web.HttpCachePolicy::AppendValueToHeader(class [mscorlib]System.Text.StringBuilder s, string value)
0x13b52  ldarg.0
0x13b53  ldfld    bool System.Web.HttpCachePolicy::_isProxyMaxAgeSet
0x13b58  brfalse.s loc_13B8C
0x13b5a  ldarg.0
0x13b5b  ldfld    bool System.Web.HttpCachePolicy::_noMaxAgeInCacheControl
0x13b60  brtrue.s loc_13B8C
0x13b62  ldloc.0
0x13b63  ldstr    aSMaxage// "s-maxage="
0x13b68  ldarg.0
0x13b69  ldflda   valuetype [mscorlib]System.TimeSpan System.Web.HttpCachePolicy::_proxyMaxAge
0x13b6e  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x13b73  conv.i8
0x13b74  stloc.s  8
0x13b76  ldloca.s 8
0x13b78  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13b7d  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x13b82  call     string [mscorlib]System.String::Concat(string, string)
0x13b87  call     void System.Web.HttpCachePolicy::AppendValueToHeader(class [mscorlib]System.Text.StringBuilder s, string value)
0x13b8c  ldloc.0
0x13b8d  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x13b92  ldc.i4.0
0x13b93  ble.s    loc_13BA7
0x13b95  ldarg.0
0x13b96  ldc.i4.0
0x13b97  ldloc.0
0x13b98  callvirt instance string [mscorlib]System.Object::ToString()
0x13b9d  newobj   instance void System.Web.HttpResponseHeader::.ctor(int32 knownHeaderIndex, string value)
0x13ba2  stfld    class System.Web.HttpResponseHeader System.Web.HttpCachePolicy::_headerCacheControl
0x13ba7  ldloc.1
0x13ba8  ldc.i4.1
0x13ba9  beq.s    loc_13BAF
0x13bab  ldloc.1
0x13bac  ldc.i4.3
0x13bad  bne.un.s loc_13C05
0x13baf  ldsfld   class System.Web.HttpResponseHeader System.Web.HttpCachePolicy::s_headerPragmaNoCache
0x13bb4  brtrue.s loc_13BC6
0x13bb6  ldc.i4.4
0x13bb7  ldstr    aNoCache_0// "no-cache"
0x13bbc  newobj   instance void System.Web.HttpResponseHeader::.ctor(int32 knownHeaderIndex, string value)
0x13bc1  stsfld   class System.Web.HttpResponseHeader System.Web.HttpCachePolicy::s_headerPragmaNoCache
0x13bc6  ldarg.0
0x13bc7  ldsfld   class System.Web.HttpResponseHeader System.Web.HttpCachePolicy::s_headerPragmaNoCache
0x13bcc  stfld    class System.Web.HttpResponseHeader System.Web.HttpCachePolicy::_headerPragma
0x13bd1  ldarg.0
0x13bd2  ldfld    int32 System.Web.HttpCachePolicy::_allowInHistory
0x13bd7  ldc.i4.1
0x13bd8  beq      loc_13D0E
0x13bdd  ldsfld   class System.Web.HttpResponseHeader System.Web.HttpCachePolicy::s_headerExpiresMinus1
0x13be2  brtrue.s loc_13BF5
0x13be4  ldc.i4.s 0x12
0x13be6  ldstr    a1// "-1"
0x13beb  newobj   instance void System.Web.HttpResponseHeader::.ctor(int32 knownHeaderIndex, string value)
0x13bf0  stsfld   class System.Web.HttpResponseHeader System.Web.HttpCachePolicy::s_headerExpiresMinus1
0x13bf5  ldarg.0
0x13bf6  ldsfld   class System.Web.HttpResponseHeader System.Web.HttpCachePolicy::s_headerExpiresMinus1
0x13bfb  stfld    class System.Web.HttpResponseHeader System.Web.HttpCachePolicy::_headerExpires
0x13c00  br       loc_13D0E
0x13c05  ldarg.0
0x13c06  ldfld    bool System.Web.HttpCachePolicy::_isExpiresSet
0x13c0b  brfalse.s loc_13C32
0x13c0d  ldarg.0
0x13c0e  ldfld    int32 System.Web.HttpCachePolicy::_slidingExpiration
0x13c13  ldc.i4.1
0x13c14  beq.s    loc_13C32
0x13c16  ldarg.0
0x13c17  ldfld    valuetype [mscorlib]System.DateTime System.Web.HttpCachePolicy::_utcExpires
0x13c1c  call     string System.Web.HttpUtility::FormatHttpDateTimeUtc(valuetype [mscorlib]System.DateTime dt)
0x13c21  stloc.s  4
0x13c23  ldarg.0
0x13c24  ldc.i4.s 0x12
0x13c26  ldloc.s  4
0x13c28  newobj   instance void System.Web.HttpResponseHeader::.ctor(int32 knownHeaderIndex, string value)
0x13c2d  stfld    class System.Web.HttpResponseHeader System.Web.HttpCachePolicy::_headerExpires
0x13c32  ldarg.0
0x13c33  ldfld    bool System.Web.HttpCachePolicy::_isLastModifiedSet
0x13c38  brfalse.s loc_13C56
0x13c3a  ldarg.0
  ... truncated ...
```
