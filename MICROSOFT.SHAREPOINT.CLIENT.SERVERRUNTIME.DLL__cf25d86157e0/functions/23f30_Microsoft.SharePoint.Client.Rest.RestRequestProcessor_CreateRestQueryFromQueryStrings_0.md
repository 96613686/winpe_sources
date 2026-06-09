# Microsoft.SharePoint.Client.Rest.RestRequestProcessor::CreateRestQueryFromQueryStrings_0

- ea: `0x23f30`
- end: `0x24293`
- name: `Microsoft.SharePoint.Client.Rest.RestRequestProcessor::CreateRestQueryFromQueryStrings_0`
- size: `867`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x23f10`
- `0x27830`

## callees

- `0xe010`
- `0x12e20`
- `0x16f10`
- `0x1bd80`
- `0x1bdd0`
- `0x1bdf0`
- `0x1bf40`
- `0x215d0`
- `0x217d0`
- `0x217f0`
- `0x21810`
- `0x21830`
- `0x21850`
- `0x21a90`
- `0x23f30`

## string_xrefs

- `0x24165`: `$skiptoken`
- `0x2419c`: `$skiptoken`
- `0x241b0`: `$deltatoken`

## pseudocode

```c

```

## disassembly

```asm
0x23f30  newobj   instance void Microsoft.SharePoint.Client.RESTfulQuery::.ctor()
0x23f35  stloc.0
0x23f36  ldarg.0
0x23f37  ldstr    aSelect// "$select"
0x23f3c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x23f41  stloc.1
0x23f42  ldloc.1
0x23f43  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x23f48  brtrue.s loc_23F68
0x23f4a  ldloc.1
0x23f4b  ldloc.1
0x23f4c  newobj   instance void Microsoft.SharePoint.Client.Rest.EdmExpressionParser::.ctor(string input, string inputForErrorMessage)
0x23f51  stloc.2
0x23f52  ldloc.2
0x23f53  ldc.i4.1
0x23f54  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.SharePoint.Client.Rest.EdmExpressionParser::ParsePropertyList(bool allowWildcard)
0x23f59  stloc.3
0x23f5a  ldloc.0
0x23f5b  ldloc.3
0x23f5c  ldc.i4.1
0x23f5d  ldloc.1
0x23f5e  call     class Microsoft.SharePoint.Client.RestSelectExpandQuery Microsoft.SharePoint.Client.RestSelectExpandQuery::CreateFrom(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> expList, bool allowWildcard, string selectQuery)
0x23f63  callvirt instance void Microsoft.SharePoint.Client.RESTfulQuery::set_Select(class Microsoft.SharePoint.Client.RestSelectExpandQuery value)
0x23f68  ldarg.0
0x23f69  ldstr    aExpand// "$expand"
0x23f6e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x23f73  stloc.s  4
0x23f75  ldloc.s  4
0x23f77  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x23f7c  brtrue.s loc_23FA2
0x23f7e  ldloc.s  4
0x23f80  ldloc.s  4
0x23f82  newobj   instance void Microsoft.SharePoint.Client.Rest.EdmExpressionParser::.ctor(string input, string inputForErrorMessage)
0x23f87  stloc.s  5
0x23f89  ldloc.s  5
0x23f8b  ldc.i4.0
0x23f8c  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.SharePoint.Client.Rest.EdmExpressionParser::ParsePropertyList(bool allowWildcard)
0x23f91  stloc.s  6
0x23f93  ldloc.0
0x23f94  ldloc.s  6
0x23f96  ldc.i4.0
0x23f97  ldnull
0x23f98  call     class Microsoft.SharePoint.Client.RestSelectExpandQuery Microsoft.SharePoint.Client.RestSelectExpandQuery::CreateFrom(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> expList, bool allowWildcard, string selectQuery)
0x23f9d  callvirt instance void Microsoft.SharePoint.Client.RESTfulQuery::set_Expand(class Microsoft.SharePoint.Client.RestSelectExpandQuery value)
0x23fa2  ldarg.0
0x23fa3  ldstr    aFilter// "$filter"
0x23fa8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x23fad  stloc.s  7
0x23faf  ldnull
0x23fb0  stloc.s  8
0x23fb2  ldloc.s  7
0x23fb4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x23fb9  brtrue.s loc_2401D
0x23fbb  ldloc.s  7
0x23fbd  ldloc.s  7
0x23fbf  newobj   instance void Microsoft.SharePoint.Client.Rest.EdmExpressionParser::.ctor(string input, string inputForErrorMessage)
0x23fc4  stloc.s  9
0x23fc6  ldloc.s  9
0x23fc8  callvirt instance class Microsoft.SharePoint.Client.Rest.EdmParserNode Microsoft.SharePoint.Client.Rest.EdmExpressionParser::ParseFilter()
0x23fcd  stloc.s  8
0x23fcf  ldloc.s  8
0x23fd1  brtrue.s loc_2401D
0x23fd3  ldarg.1
0x23fd4  ldc.i4   0x1C50D9
0x23fd9  ldc.i4.1
0x23fda  ldstr    aTheFilter0IsNo// "The $filter {0} is not valid."
0x23fdf  ldc.i4.1
0x23fe0  newarr   [mscorlib]System.Object
0x23fe5  stloc.s  0x16
0x23fe7  ldloc.s  0x16
0x23fe9  ldc.i4.0
0x23fea  ldloc.s  7
0x23fec  stelem.ref
0x23fed  ldloc.s  0x16
0x23fef  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x23ff4  ldstr    aInvalidqueryex_0// "InvalidQueryExpressionWithName"
0x23ff9  ldc.i4.2
0x23ffa  newarr   [mscorlib]System.Object
0x23fff  stloc.s  0x17
0x24001  ldloc.s  0x17
0x24003  ldc.i4.0
0x24004  ldstr    aFilter// "$filter"
0x24009  stelem.ref
0x2400a  ldloc.s  0x17
0x2400c  ldc.i4.1
0x2400d  ldloc.s  7
0x2400f  stelem.ref
0x24010  ldloc.s  0x17
0x24012  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x24017  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor(string strMessage)
0x2401c  throw
0x2401d  ldarg.0
0x2401e  ldstr    aOrderby_0// "$orderby"
0x24023  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x24028  stloc.s  0xA
0x2402a  ldnull
0x2402b  stloc.s  0xB
0x2402d  ldloc.s  0xA
0x2402f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x24034  brtrue.s loc_24098
0x24036  ldloc.s  0xA
0x24038  ldloc.s  0xA
0x2403a  newobj   instance void Microsoft.SharePoint.Client.Rest.EdmExpressionParser::.ctor(string input, string inputForErrorMessage)
0x2403f  stloc.s  0xC
0x24041  ldloc.s  0xC
0x24043  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.SharePoint.Client.Rest.EdmParserNode> Microsoft.SharePoint.Client.Rest.EdmExpressionParser::ParseOrderBy()
0x24048  stloc.s  0xB
0x2404a  ldloc.s  0xB
0x2404c  brtrue.s loc_24098
0x2404e  ldarg.1
0x2404f  ldc.i4   0x1C50DA
0x24054  ldc.i4.1
0x24055  ldstr    aTheOrderby0IsN// "The $orderby {0} is not valid."
0x2405a  ldc.i4.1
0x2405b  newarr   [mscorlib]System.Object
0x24060  stloc.s  0x18
0x24062  ldloc.s  0x18
0x24064  ldc.i4.0
0x24065  ldloc.s  0xA
0x24067  stelem.ref
0x24068  ldloc.s  0x18
0x2406a  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x2406f  ldstr    aInvalidqueryex_0// "InvalidQueryExpressionWithName"
0x24074  ldc.i4.2
0x24075  newarr   [mscorlib]System.Object
0x2407a  stloc.s  0x19
0x2407c  ldloc.s  0x19
0x2407e  ldc.i4.0
0x2407f  ldstr    aOrderby_0// "$orderby"
0x24084  stelem.ref
0x24085  ldloc.s  0x19
0x24087  ldc.i4.1
0x24088  ldloc.s  0xA
0x2408a  stelem.ref
0x2408b  ldloc.s  0x19
0x2408d  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x24092  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor(string strMessage)
0x24097  throw
0x24098  ldloca.s 0xD
0x2409a  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x240a0  ldarg.0
0x240a1  ldstr    aTop// "$top"
0x240a6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x240ab  stloc.s  0xE
0x240ad  ldloc.s  0xE
0x240af  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x240b4  brtrue.s loc_240FE
0x240b6  ldc.i4.0
0x240b7  stloc.s  0xF
0x240b9  ldloc.s  0xE
0x240bb  ldc.i4.7
0x240bc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x240c1  ldloca.s 0xF
0x240c3  call     bool [mscorlib]System.Int32::TryParse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider, int32&)
0x240c8  brfalse.s loc_240D5
0x240ca  ldloca.s 0xD
0x240cc  ldloc.s  0xF
0x240ce  call     instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x240d3  br.s     loc_240FE
0x240d5  ldstr    aInvalidqueryex_0// "InvalidQueryExpressionWithName"
0x240da  ldc.i4.2
0x240db  newarr   [mscorlib]System.Object
0x240e0  stloc.s  0x1A
0x240e2  ldloc.s  0x1A
0x240e4  ldc.i4.0
0x240e5  ldstr    aTop// "$top"
0x240ea  stelem.ref
0x240eb  ldloc.s  0x1A
0x240ed  ldc.i4.1
0x240ee  ldloc.s  0xE
0x240f0  stelem.ref
0x240f1  ldloc.s  0x1A
0x240f3  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x240f8  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor(string strMessage)
0x240fd  throw
0x240fe  ldloca.s 0x10
0x24100  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x24106  ldarg.0
0x24107  ldstr    aSkip_0// "$skip"
0x2410c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x24111  stloc.s  0x11
0x24113  ldloc.s  0x11
0x24115  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2411a  brtrue.s loc_24164
0x2411c  ldc.i4.0
0x2411d  stloc.s  0x12
0x2411f  ldloc.s  0x11
0x24121  ldc.i4.7
0x24122  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24127  ldloca.s 0x12
0x24129  call     bool [mscorlib]System.Int32::TryParse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider, int32&)
0x2412e  brfalse.s loc_2413B
0x24130  ldloca.s 0x10
0x24132  ldloc.s  0x12
0x24134  call     instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x24139  br.s     loc_24164
0x2413b  ldstr    aInvalidqueryex_0// "InvalidQueryExpressionWithName"
0x24140  ldc.i4.2
0x24141  newarr   [mscorlib]System.Object
0x24146  stloc.s  0x1B
0x24148  ldloc.s  0x1B
0x2414a  ldc.i4.0
0x2414b  ldstr    aSkip_0// "$skip"
0x24150  stelem.ref
0x24151  ldloc.s  0x1B
0x24153  ldc.i4.1
0x24154  ldloc.s  0x11
0x24156  stelem.ref
0x24157  ldloc.s  0x1B
0x24159  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2415e  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor(string strMessage)
0x24163  throw
0x24164  ldarg.0
0x24165  ldstr    aSkiptoken// "$skiptoken"
0x2416a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2416f  stloc.s  0x13
0x24171  ldloc.s  0x13
0x24173  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x24178  brtrue.s loc_241AF
0x2417a  ldloca.s 0x10
0x2417c  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x24181  brfalse.s loc_241AF
0x24183  ldstr    aExclusiveparam// "ExclusiveParameters"
0x24188  ldc.i4.2
0x24189  newarr   [mscorlib]System.Object
0x2418e  stloc.s  0x1C
0x24190  ldloc.s  0x1C
0x24192  ldc.i4.0
0x24193  ldstr    aSkip_0// "$skip"
0x24198  stelem.ref
0x24199  ldloc.s  0x1C
0x2419b  ldc.i4.1
0x2419c  ldstr    aSkiptoken// "$skiptoken"
0x241a1  stelem.ref
0x241a2  ldloc.s  0x1C
0x241a4  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x241a9  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor(string strMessage)
0x241ae  throw
0x241af  ldarg.0
0x241b0  ldstr    aDeltatoken// "$deltatoken"
0x241b5  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x241ba  stloc.s  0x14
0x241bc  ldloc.0
0x241bd  ldloc.s  8
0x241bf  ldloc.s  0xB
0x241c1  ldloc.s  0xD
0x241c3  ldloc.s  0x13
0x241c5  ldloc.s  0x10
0x241c7  ldloc.s  0x14
0x241c9  newobj   instance void Microsoft.SharePoint.Client.Rest.RestClientQueryableExpression::.ctor(class Microsoft.SharePoint.Client.Rest.EdmParserNode filter, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.SharePoint.Client.Rest.EdmParserNode> orderBys, valuetype [mscorlib]System.Nullable`1<int32> take, string skiptoken, valuetype [mscorlib]System.Nullable`1<int32> skip, string deltatoken)
0x241ce  callvirt instance void Microsoft.SharePoint.Client.RESTfulQuery::set_QueryableExpression(class Microsoft.SharePoint.Client.Rest.RestClientQueryableExpression value)
0x241d3  ldarg.0
0x241d4  ldstr    aInlinecount// "$inlinecount"
0x241d9  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x241de  stloc.s  0x15
0x241e0  ldloc.s  0x15
0x241e2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x241e7  brtrue   loc_24291
0x241ec  ldarg.1
0x241ed  ldc.i4   0x5555D6
0x241f2  ldc.i4.4
0x241f3  ldstr    aInlinecountQue// "$inlinecount query string '{0}'"
0x241f8  ldc.i4.1
0x241f9  newarr   [mscorlib]System.Object
0x241fe  stloc.s  0x1D
0x24200  ldloc.s  0x1D
0x24202  ldc.i4.0
0x24203  ldloc.s  0x15
0x24205  stelem.ref
0x24206  ldloc.s  0x1D
0x24208  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x2420d  ldloc.s  0x15
0x2420f  ldstr    aAllpages// "allpages"
0x24214  ldc.i4.5
0x24215  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x2421a  brfalse.s loc_2422A
0x2421c  ldloc.0
0x2421d  ldc.i4.1
0x2421e  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x24223  callvirt instance void Microsoft.SharePoint.Client.RESTfulQuery::set_InlineCount(valuetype [mscorlib]System.Nullable`1<bool> value)
0x24228  br.s     loc_24291
0x2422a  ldloc.s  0x15
0x2422c  ldstr    aNone// "none"
0x24231  ldc.i4.5
0x24232  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x24237  brfalse.s loc_24247
0x24239  ldloc.0
0x2423a  ldc.i4.0
0x2423b  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x24240  callvirt instance void Microsoft.SharePoint.Client.RESTfulQuery::set_InlineCount(valuetype [mscorlib]System.Nullable`1<bool> value)
0x24245  br.s     loc_24291
0x24247  ldarg.1
0x24248  ldc.i4   0x5555D7
0x2424d  ldc.i4.1
0x2424e  ldstr    aInvalidInlinec// "Invalid $inlinecount query string '{0}'"
0x24253  ldc.i4.1
0x24254  newarr   [mscorlib]System.Object
0x24259  stloc.s  0x1E
0x2425b  ldloc.s  0x1E
0x2425d  ldc.i4.0
  ... truncated ...
```
