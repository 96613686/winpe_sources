# System.Web.Caching.OutputCacheModule::OnEnter

- ea: `0x18bbd0`
- end: `0x18c1ca`
- name: `System.Web.Caching.OutputCacheModule::OnEnter`
- size: `1530`
- prototype: ``
- caller_count: `0`
- callee_count: `49`
- tags: ``

## callees

- `0xe390`
- `0xe790`
- `0x11cf0`
- `0x12c40`
- `0x12f80`
- `0x13030`
- `0x130a0`
- `0x13120`
- `0x13130`
- `0x13190`
- `0x131b0`
- `0x13220`
- `0x13230`
- `0x13240`
- `0x132d0`
- `0x134e0`
- `0x16330`
- `0x16350`
- `0x16a10`
- `0x16a20`
- `0x16ab0`
- `0x1a290`
- `0x1a2b0`
- `0x1b730`
- `0x1c3b0`
- `0x1c3d0`
- `0x1c660`
- `0x1c780`
- `0x1e9b0`
- `0x1efc0`
- `0x1f6e0`
- `0x1fbf0`
- `0x20150`
- `0x21c20`
- `0x21c40`
- `0x2ae20`
- `0x32200`
- `0x57180`
- `0x58eb0`
- `0x58f20`
- `0x1890c0`
- `0x189270`
- `0x189340`
- `0x18b370`
- `0x18b830`
- `0x18b850`
- `0x18bb00`
- `0x18bb60`
- `0x18bbd0`

## string_xrefs

- `0x18bddb`: `no-cache`
- `0x18bf23`: `no-cache`
- `0x18bda9`: `Cache-Control`

## pseudocode

```c

```

## disassembly

```asm
0x18bbd0  ldarg.0
0x18bbd1  ldnull
0x18bbd2  stfld    string System.Web.Caching.OutputCacheModule::_key
0x18bbd7  ldarg.0
0x18bbd8  ldc.i4.0
0x18bbd9  stfld    bool System.Web.Caching.OutputCacheModule::_recordedCacheMiss
0x18bbde  call     bool System.Web.Caching.OutputCache::get_InUse()
0x18bbe3  brtrue.s loc_18BBE6
0x18bbe5  ret
0x18bbe6  ldnull
0x18bbe7  stloc.s  0x14
0x18bbe9  ldnull
0x18bbea  stloc.s  0x16
0x18bbec  ldarg.1
0x18bbed  castclass System.Web.HttpApplication
0x18bbf2  stloc.0
0x18bbf3  ldloc.0
0x18bbf4  callvirt instance class System.Web.HttpContext System.Web.HttpApplication::get_Context()
0x18bbf9  stloc.1
0x18bbfa  ldloc.1
0x18bbfb  callvirt instance class System.Web.CachedPathData System.Web.HttpContext::GetFilePathData()
0x18bc00  stloc.s  0x1F
0x18bc02  ldloc.1
0x18bc03  callvirt instance class System.Web.HttpRequest System.Web.HttpContext::get_Request()
0x18bc08  stloc.3
0x18bc09  ldloc.1
0x18bc0a  callvirt instance class System.Web.HttpResponse System.Web.HttpContext::get_Response()
0x18bc0f  stloc.s  4
0x18bc11  ldloc.3
0x18bc12  callvirt instance valuetype System.Web.HttpVerb System.Web.HttpRequest::get_HttpVerb()
0x18bc17  stloc.s  0x21
0x18bc19  ldloc.s  0x21
0x18bc1b  ldc.i4.2
0x18bc1c  beq.s    loc_18BC26
0x18bc1e  ldloc.s  0x21
0x18bc20  ldc.i4.4
0x18bc21  sub
0x18bc22  ldc.i4.1
0x18bc23  ble.un.s loc_18BC26
0x18bc25  ret
0x18bc26  ldarg.0
0x18bc27  ldarg.0
0x18bc28  ldloc.1
0x18bc29  ldnull
0x18bc2a  call     instance string System.Web.Caching.OutputCacheModule::CreateOutputCachedItemKey(class System.Web.HttpContext context, class System.Web.Caching.CachedVary cachedVary)
0x18bc2f  dup
0x18bc30  stloc.2
0x18bc31  stfld    string System.Web.Caching.OutputCacheModule::_key
0x18bc36  ldloc.2
0x18bc37  call     object System.Web.Caching.OutputCache::Get(string key)
0x18bc3c  stloc.s  5
0x18bc3e  ldloc.s  5
0x18bc40  brtrue.s loc_18BC43
0x18bc42  ret
0x18bc43  ldloc.s  5
0x18bc45  isinst   System.Web.Caching.CachedVary
0x18bc4a  stloc.s  0x1D
0x18bc4c  ldloc.s  0x1D
0x18bc4e  brfalse  loc_18BD2B
0x18bc53  ldarg.0
0x18bc54  ldloc.1
0x18bc55  ldloc.s  0x1D
0x18bc57  call     instance string System.Web.Caching.OutputCacheModule::CreateOutputCachedItemKey(class System.Web.HttpContext context, class System.Web.Caching.CachedVary cachedVary)
0x18bc5c  stloc.2
0x18bc5d  ldloc.2
0x18bc5e  brtrue.s loc_18BC61
0x18bc60  ret
0x18bc61  ldloc.s  0x1D
0x18bc63  ldfld    string[] System.Web.Caching.CachedVary::_contentEncodings
0x18bc68  brtrue.s loc_18BC77
0x18bc6a  ldloc.2
0x18bc6b  call     object System.Web.Caching.OutputCache::Get(string key)
0x18bc70  stloc.s  5
0x18bc72  br       loc_18BD01
0x18bc77  ldnull
0x18bc78  stloc.s  5
0x18bc7a  ldc.i4.1
0x18bc7b  stloc.s  0x22
0x18bc7d  ldloc.1
0x18bc7e  callvirt instance class System.Web.HttpWorkerRequest System.Web.HttpContext::get_WorkerRequest()
0x18bc83  ldc.i4.s 0x16
0x18bc85  callvirt instance string System.Web.HttpWorkerRequest::GetKnownRequestHeader(int32 index)
0x18bc8a  stloc.s  0x23
0x18bc8c  ldloc.s  0x23
0x18bc8e  brfalse.s loc_18BCEF
0x18bc90  ldloc.s  0x1D
0x18bc92  ldfld    string[] System.Web.Caching.CachedVary::_contentEncodings
0x18bc97  stloc.s  0x24
0x18bc99  ldc.i4.0
0x18bc9a  stloc.s  0x25
0x18bc9c  ldc.i4.0
0x18bc9d  stloc.s  0x26
0x18bc9f  br.s     loc_18BCEB
0x18bca1  ldc.i4.1
0x18bca2  stloc.s  0x26
0x18bca4  ldloc.s  0x24
0x18bca6  ldloc.s  0x25
0x18bca8  ldloc.s  0x23
0x18bcaa  call     int32 System.Web.Caching.OutputCacheModule::GetAcceptableEncoding(string[] contentEncodings, int32 startIndex, string acceptEncoding)
0x18bcaf  stloc.s  0x27
0x18bcb1  ldloc.s  0x27
0x18bcb3  ldc.i4.m1
0x18bcb4  ble.s    loc_18BCE2
0x18bcb6  ldc.i4.0
0x18bcb7  stloc.s  0x22
0x18bcb9  ldloc.2
0x18bcba  ldloc.s  0x24
0x18bcbc  ldloc.s  0x27
0x18bcbe  ldelem.ref
0x18bcbf  call     string [mscorlib]System.String::Concat(string, string)
0x18bcc4  call     object System.Web.Caching.OutputCache::Get(string key)
0x18bcc9  stloc.s  5
0x18bccb  ldloc.s  5
0x18bccd  brtrue.s loc_18BCEB
0x18bccf  ldloc.s  0x27
0x18bcd1  ldc.i4.1
0x18bcd2  add
0x18bcd3  stloc.s  0x25
0x18bcd5  ldloc.s  0x25
0x18bcd7  ldloc.s  0x24
0x18bcd9  ldlen
0x18bcda  conv.i4
0x18bcdb  bge.s    loc_18BCEB
0x18bcdd  ldc.i4.0
0x18bcde  stloc.s  0x26
0x18bce0  br.s     loc_18BCEB
0x18bce2  ldloc.s  0x27
0x18bce4  ldc.i4.s 0xFE
0x18bce6  bne.un.s loc_18BCEB
0x18bce8  ldc.i4.0
0x18bce9  stloc.s  0x22
0x18bceb  ldloc.s  0x26
0x18bced  brfalse.s loc_18BCA1
0x18bcef  ldloc.s  5
0x18bcf1  ldnull
0x18bcf2  ceq
0x18bcf4  ldloc.s  0x22
0x18bcf6  and
0x18bcf7  brfalse.s loc_18BD01
0x18bcf9  ldloc.2
0x18bcfa  call     object System.Web.Caching.OutputCache::Get(string key)
0x18bcff  stloc.s  5
0x18bd01  ldloc.s  5
0x18bd03  brfalse.s loc_18BD1F
0x18bd05  ldloc.s  5
0x18bd07  castclass System.Web.Caching.CachedRawResponse
0x18bd0c  ldfld    valuetype [mscorlib]System.Guid System.Web.Caching.CachedRawResponse::_cachedVaryId
0x18bd11  ldloc.s  0x1D
0x18bd13  callvirt instance valuetype [mscorlib]System.Guid System.Web.Caching.CachedVary::get_CachedVaryId()
0x18bd18  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x18bd1d  brfalse.s loc_18BD2B
0x18bd1f  ldloc.s  5
0x18bd21  brfalse.s loc_18BD2A
0x18bd23  ldloc.2
0x18bd24  ldloc.1
0x18bd25  call     void System.Web.Caching.OutputCache::Remove(string key, class System.Web.HttpContext context)
0x18bd2a  ret
0x18bd2b  ldloc.s  5
0x18bd2d  castclass System.Web.Caching.CachedRawResponse
0x18bd32  stloc.s  6
0x18bd34  ldloc.s  6
0x18bd36  ldfld    class System.Web.HttpCachePolicySettings System.Web.Caching.CachedRawResponse::_settings
0x18bd3b  stloc.s  7
0x18bd3d  ldloc.s  0x1D
0x18bd3f  brtrue.s loc_18BD69
0x18bd41  ldloc.s  7
0x18bd43  callvirt instance bool System.Web.HttpCachePolicySettings::get_IgnoreParams()
0x18bd48  brtrue.s loc_18BD69
0x18bd4a  ldloc.3
0x18bd4b  callvirt instance valuetype System.Web.HttpVerb System.Web.HttpRequest::get_HttpVerb()
0x18bd50  ldc.i4.5
0x18bd51  bne.un.s loc_18BD5A
0x18bd53  ldarg.0
0x18bd54  call     instance void System.Web.Caching.OutputCacheModule::RecordCacheMiss()
0x18bd59  ret
0x18bd5a  ldloc.3
0x18bd5b  callvirt instance bool System.Web.HttpRequest::get_HasQueryString()
0x18bd60  brfalse.s loc_18BD69
0x18bd62  ldarg.0
0x18bd63  call     instance void System.Web.Caching.OutputCacheModule::RecordCacheMiss()
0x18bd68  ret
0x18bd69  ldloc.s  7
0x18bd6b  callvirt instance bool System.Web.HttpCachePolicySettings::get_IgnoreRangeRequests()
0x18bd70  brfalse.s loc_18BD93
0x18bd72  ldloc.3
0x18bd73  callvirt instance class [System]System.Collections.Specialized.NameValueCollection System.Web.HttpRequest::get_Headers()
0x18bd78  ldstr    aRange// "Range"
0x18bd7d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x18bd82  stloc.s  0x28
0x18bd84  ldloc.s  0x28
0x18bd86  ldstr    aBytes// "bytes"
0x18bd8b  call     bool System.Web.Util.StringUtil::StringStartsWithIgnoreCase(string s1, string s2)
0x18bd90  brfalse.s loc_18BD93
0x18bd92  ret
0x18bd93  ldloc.s  7
0x18bd95  callvirt instance bool System.Web.HttpCachePolicySettings::HasValidationPolicy()
0x18bd9a  stloc.s  0x1C
0x18bd9c  ldloc.s  0x1C
0x18bd9e  brtrue   loc_18BF49
0x18bda3  ldloc.3
0x18bda4  callvirt instance class [System]System.Collections.Specialized.NameValueCollection System.Web.HttpRequest::get_Headers()
0x18bda9  ldstr    aCacheControl// "Cache-Control"
0x18bdae  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x18bdb3  stloc.s  0x13
0x18bdb5  ldloc.s  0x13
0x18bdb7  brfalse  loc_18BEF2
0x18bdbc  ldloc.s  0x13
0x18bdbe  ldsfld   char[] System.Web.Caching.OutputCacheModule::s_fieldSeparators
0x18bdc3  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x18bdc8  stloc.s  0x14
0x18bdca  ldc.i4.0
0x18bdcb  stloc.s  8
0x18bdcd  br       loc_18BEE7
0x18bdd2  ldloc.s  0x14
0x18bdd4  ldloc.s  8
0x18bdd6  ldelem.ref
0x18bdd7  stloc.s  0x17
0x18bdd9  ldloc.s  0x17
0x18bddb  ldstr    aNoCache_0// "no-cache"
0x18bde0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18bde5  brtrue.s loc_18BDF5
0x18bde7  ldloc.s  0x17
0x18bde9  ldstr    aNoStore// "no-store"
0x18bdee  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18bdf3  brfalse.s loc_18BDFC
0x18bdf5  ldarg.0
0x18bdf6  call     instance void System.Web.Caching.OutputCacheModule::RecordCacheMiss()
0x18bdfb  ret
0x18bdfc  ldloc.s  0x17
0x18bdfe  ldstr    aMaxAge// "max-age="
0x18be03  call     bool System.Web.Util.StringUtil::StringStartsWith(string s1, string s2)
0x18be08  brfalse.s loc_18BE68
0x18be0a  ldloc.s  0x17
0x18be0c  ldc.i4.8
0x18be0d  callvirt instance string [mscorlib]System.String::Substring(int32)
0x18be12  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18be17  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x18be1c  stloc.s  0x18
0x18be1e  leave.s  loc_18BE26
0x18be20  pop
0x18be21  ldc.i4.m1
0x18be22  stloc.s  0x18
0x18be24  leave.s  loc_18BE26
0x18be26  ldloc.s  0x18
0x18be28  ldc.i4.0
0x18be29  blt      loc_18BEE1
0x18be2e  ldloc.1
0x18be2f  callvirt instance valuetype [mscorlib]System.DateTime System.Web.HttpContext::get_UtcTimestamp()
0x18be34  stloc.s  0x29
0x18be36  ldloca.s 0x29
0x18be38  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x18be3d  ldloc.s  7
0x18be3f  callvirt instance valuetype [mscorlib]System.DateTime System.Web.HttpCachePolicySettings::get_UtcTimestampCreated()
0x18be44  stloc.s  0x29
0x18be46  ldloca.s 0x29
0x18be48  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x18be4d  sub
0x18be4e  ldc.i4   0x989680
0x18be53  conv.i8
0x18be54  div
0x18be55  conv.i4
0x18be56  stloc.s  0x1A
0x18be58  ldloc.s  0x1A
0x18be5a  ldloc.s  0x18
0x18be5c  blt      loc_18BEE1
0x18be61  ldarg.0
0x18be62  call     instance void System.Web.Caching.OutputCacheModule::RecordCacheMiss()
0x18be67  ret
0x18be68  ldloc.s  0x17
0x18be6a  ldstr    aMinFresh// "min-fresh="
0x18be6f  call     bool System.Web.Util.StringUtil::StringStartsWith(string s1, string s2)
0x18be74  brfalse.s loc_18BEE1
0x18be76  ldloc.s  0x17
0x18be78  ldc.i4.s 0xA
0x18be7a  callvirt instance string [mscorlib]System.String::Substring(int32)
0x18be7f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18be84  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x18be89  stloc.s  0x19
0x18be8b  leave.s  loc_18BE93
0x18be8d  pop
0x18be8e  ldc.i4.m1
0x18be8f  stloc.s  0x19
0x18be91  leave.s  loc_18BE93
0x18be93  ldloc.s  0x19
0x18be95  ldc.i4.0
0x18be96  blt.s    loc_18BEE1
0x18be98  ldloc.s  7
0x18be9a  callvirt instance bool System.Web.HttpCachePolicySettings::get_IsExpiresSet()
0x18be9f  brfalse.s loc_18BEE1
0x18bea1  ldloc.s  7
0x18bea3  callvirt instance bool System.Web.HttpCachePolicySettings::get_SlidingExpiration()
0x18bea8  brtrue.s loc_18BEE1
0x18beaa  ldloc.s  7
0x18beac  callvirt instance valuetype [mscorlib]System.DateTime System.Web.HttpCachePolicySettings::get_UtcExpires()
0x18beb1  stloc.s  0x29
0x18beb3  ldloca.s 0x29
0x18beb5  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x18beba  ldloc.1
0x18bebb  callvirt instance valuetype [mscorlib]System.DateTime System.Web.HttpContext::get_UtcTimestamp()
0x18bec0  stloc.s  0x29
  ... truncated ...
```
