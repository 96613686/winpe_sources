# Microsoft.SharePoint.Utilities.SPUnifiedAppsDistributedCacheUtils::TryPrefetchAndCacheSSRForUnifiedApps

- ea: `0x7cbfd0`
- end: `0x7cc435`
- name: `Microsoft.SharePoint.Utilities.SPUnifiedAppsDistributedCacheUtils::TryPrefetchAndCacheSSRForUnifiedApps`
- size: `1125`
- prototype: ``
- caller_count: `0`
- callee_count: `26`
- tags: `broker_com_uri`

## callees

- `0x269a80`
- `0x26e660`
- `0x31af30`
- `0x50d270`
- `0x50d2b0`
- `0x50db50`
- `0x50e320`
- `0x5131a0`
- `0x5c9dc0`
- `0x7be190`
- `0x7cbfd0`
- `0x7cc550`
- `0x7cc590`
- `0x7cc810`
- `0x7ccdd0`
- `0x7ccdf0`
- `0x7cce10`
- `0x7cce30`
- `0x7cce50`
- `0x7cce70`
- `0x7cceb0`
- `0x7ccfb0`
- `0x7ccfd0`
- `0x8ecdb0`
- `0x93dae0`
- `0x957b10`

## string_xrefs

- `0x7cbfde`: `PrefetchAndCacheSSRForUnifiedApps: Starting... (prefetchAndCacheSSRCorrelationId = {0})`
- `0x7cc060`: `PrefetchAndCacheSSRForUnifiedApps: Unable to fetch SPFile object.(prefetchAndCacheSSRCorrelationId = {0})`
- `0x7cc08e`: `PrefetchAndCacheSSRForUnifiedApps: Starting SSR fetch...(prefetchAndCacheSSRCorrelationId = {0})`
- `0x7cc187`: `PrefetchAndCacheSSRForUnifiedApps: SSR stream is empty or null. (prefetchAndCacheSSRCorrelationId = {0}), (DocCreatedTime = {1}), (DocLastModified = {2}), (DocLevel = {3}), (DocId = {4}), (DocExtn = {5})`
- `0x7cc1f4`: `TryPrefetchAndCacheSSRForUnifiedApps`
- `0x7cc279`: `TryPrefetchAndCacheSSRForUnifiedApps`
- `0x7cc2e5`: `TryPrefetchAndCacheSSRForUnifiedApps`
- `0x7cc41a`: `TryPrefetchAndCacheSSRForUnifiedApps`
- `0x7cc1f9`: `d:\dbs\el\zlt\dev\sts\stsom\Utilities\SPUnifiedAppsDistributedCacheUtils.cs`
- `0x7cc27e`: `d:\dbs\el\zlt\dev\sts\stsom\Utilities\SPUnifiedAppsDistributedCacheUtils.cs`
- `0x7cc2ea`: `d:\dbs\el\zlt\dev\sts\stsom\Utilities\SPUnifiedAppsDistributedCacheUtils.cs`
- `0x7cc41f`: `d:\dbs\el\zlt\dev\sts\stsom\Utilities\SPUnifiedAppsDistributedCacheUtils.cs`
- `0x7cc235`: `PrefetchAndCacheSSRForUnifiedApps: SSR stream is too big! size {0} bytes. Skipping caching! (prefetchAndCacheSSRCorrelationId = {1})`
- `0x7cc2a1`: `PrefetchAndCacheSSRForUnifiedApps: Successfully fetched SSR of size {0} bytes.  (prefetchAndCacheSSRCorrelationId = {1})`
- `0x7cc305`: `PrefetchAndCacheSSRForUnifiedApps: Caching SSR...(prefetchAndCacheSSRCorrelationId = {0})`
- `0x7cc33d`: `PrefetchAndCacheSSRForUnifiedApps: (prefetchAndCacheSSRCorrelationId = {0}) , (CacheKey = {1})`
- `0x7cc37e`: `PrefetchAndCacheSSRForUnifiedApps: Successfully cached SSR. (prefetchAndCacheSSRCorrelationId = {0})`
- `0x7cc3ac`: `PrefetchAndCacheSSRForUnifiedApps: failed to cache SSR. (prefetchAndCacheSSRCorrelationId = {0})`
- `0x7cc3ed`: `PrefetchAndCacheSSRForUnifiedApps: failed for (prefetchAndCacheSSRCorrelationId = {0}) with error:{1}`

## pseudocode

```c

```

## disassembly

```asm
0x7cbfd0  ldnull
0x7cbfd1  stloc.0
0x7cbfd2  ldc.i4   0x1723546
0x7cbfd7  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_WOPI()
0x7cbfdc  ldc.i4.s 0x32
0x7cbfde  ldstr    aPrefetchandcac// "PrefetchAndCacheSSRForUnifiedApps: Star"...
0x7cbfe3  ldc.i4.1
0x7cbfe4  newarr   [mscorlib]System.Object
0x7cbfe9  stloc.s  0xB
0x7cbfeb  ldloc.s  0xB
0x7cbfed  ldc.i4.0
0x7cbfee  ldarg.s  4
0x7cbff0  stelem.ref
0x7cbff1  ldloc.s  0xB
0x7cbff3  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x7cbff8  ldarg.0
0x7cbff9  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x7cbffe  brfalse.s loc_7CC00B
0x7cc000  ldstr    aWeburl// "webUrl"
0x7cc005  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x7cc00a  throw
0x7cc00b  ldarg.1
0x7cc00c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7cc011  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x7cc016  brfalse.s loc_7CC023
0x7cc018  ldstr    aFileuniqueid// "fileUniqueId"
0x7cc01d  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x7cc022  throw
0x7cc023  ldarg.2
0x7cc024  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7cc029  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x7cc02e  brfalse.s loc_7CC03B
0x7cc030  ldstr    aStreamidguid// "streamIdGuid"
0x7cc035  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x7cc03a  throw
0x7cc03b  ldarg.0
0x7cc03c  newobj   instance void Microsoft.SharePoint.SPSite::.ctor(string requestUrl)
0x7cc041  stloc.1
0x7cc042  ldloc.1
0x7cc043  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPSite::OpenWeb()
0x7cc048  stloc.2
0x7cc049  ldloc.2
0x7cc04a  ldarg.1
0x7cc04b  callvirt instance class Microsoft.SharePoint.SPFile Microsoft.SharePoint.SPWeb::GetFile(valuetype [mscorlib]System.Guid uniqueId)
0x7cc050  stloc.3
0x7cc051  ldloc.3
0x7cc052  brtrue.s loc_7CC082
0x7cc054  ldc.i4   0x1723547
0x7cc059  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_WOPI()
0x7cc05e  ldc.i4.s 0x14
0x7cc060  ldstr    aPrefetchandcac_0// "PrefetchAndCacheSSRForUnifiedApps: Unab"...
0x7cc065  ldc.i4.1
0x7cc066  newarr   [mscorlib]System.Object
0x7cc06b  stloc.s  0xC
0x7cc06d  ldloc.s  0xC
0x7cc06f  ldc.i4.0
0x7cc070  ldarg.s  4
0x7cc072  stelem.ref
0x7cc073  ldloc.s  0xC
0x7cc075  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x7cc07a  ldc.i4.0
0x7cc07b  stloc.s  0xA
0x7cc07d  leave    loc_7CC432
0x7cc082  ldc.i4   0x1723548
0x7cc087  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_WOPI()
0x7cc08c  ldc.i4.s 0x32
0x7cc08e  ldstr    aPrefetchandcac_1// "PrefetchAndCacheSSRForUnifiedApps: Star"...
0x7cc093  ldc.i4.1
0x7cc094  newarr   [mscorlib]System.Object
0x7cc099  stloc.s  0xD
0x7cc09b  ldloc.s  0xD
0x7cc09d  ldc.i4.0
0x7cc09e  ldarg.s  4
0x7cc0a0  stelem.ref
0x7cc0a1  ldloc.s  0xD
0x7cc0a3  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x7cc0a8  ldloc.3
0x7cc0a9  ldloc.3
0x7cc0aa  callvirt instance valuetype Microsoft.SharePoint.SPFileLevel Microsoft.SharePoint.SPFile::get_Level()
0x7cc0af  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.SPFileLevel>::.ctor(var<u1>)
0x7cc0b4  ldstr    aPreview_2// "/preview/"
0x7cc0b9  ldarg.2
0x7cc0ba  ldarg.3
0x7cc0bb  callvirt instance class [mscorlib]System.IO.Stream Microsoft.SharePoint.SPFile::GetStream(valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.SPFileLevel> levelOverride, string scope, valuetype [mscorlib]System.Guid streamIdGuid, unsigned int32 streamIdInt)
0x7cc0c0  stloc.s  4
0x7cc0c2  ldc.i4   0x8C
0x7cc0c7  newobj   instance void Microsoft.SharePoint.Utilities.SPUnifiedAppsSSRFetchQosEvent::.ctor(valuetype Microsoft.SharePoint.GlobalEnums.SPFeatureId featureId)
0x7cc0cc  stloc.0
0x7cc0cd  ldloc.0
0x7cc0ce  ldarg.s  4
0x7cc0d0  callvirt instance void Microsoft.SharePoint.Utilities.SPUnifiedAppsOfficeBundleQosEventBase::set_UlsPrefetchCorrelationId(string value)
0x7cc0d5  ldloc.0
0x7cc0d6  ldarga.s 1
0x7cc0d8  constrained. [mscorlib]System.Guid
0x7cc0de  callvirt instance string [mscorlib]System.Object::ToString()
0x7cc0e3  callvirt instance void Microsoft.SharePoint.Utilities.SPUnifiedAppsOfficeBundleQosEventBase::set_DocId(string value)
0x7cc0e8  ldloc.0
0x7cc0e9  ldloc.3
0x7cc0ea  callvirt instance string Microsoft.SharePoint.SPFile::get_Name()
0x7cc0ef  call     string [mscorlib]System.IO.Path::GetExtension(string)
0x7cc0f4  callvirt instance void Microsoft.SharePoint.Utilities.SPUnifiedAppsOfficeBundleQosEventBase::set_DocExt(string value)
0x7cc0f9  ldloc.0
0x7cc0fa  ldloc.3
0x7cc0fb  callvirt instance valuetype Microsoft.SharePoint.SPFileLevel Microsoft.SharePoint.SPFile::get_Level()
0x7cc100  box      Microsoft.SharePoint.SPFileLevel
0x7cc105  callvirt instance string [mscorlib]System.Object::ToString()
0x7cc10a  callvirt instance void Microsoft.SharePoint.Utilities.SPUnifiedAppsOfficeBundleQosEventBase::set_DocLevel(string value)
0x7cc10f  ldloc.3
0x7cc110  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.SPFile::get_TimeCreated()
0x7cc115  pop
0x7cc116  ldloc.0
0x7cc117  ldloc.3
0x7cc118  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.SPFile::get_TimeCreated()
0x7cc11d  stloc.s  0xE
0x7cc11f  ldloca.s 0xE
0x7cc121  ldstr    aO// "o"
0x7cc126  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7cc12b  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0x7cc130  callvirt instance void Microsoft.SharePoint.Utilities.SPUnifiedAppsOfficeBundleQosEventBase::set_DocCreatedTimeUTC(string value)
0x7cc135  ldloc.3
0x7cc136  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.SPFile::get_TimeLastModified()
0x7cc13b  pop
0x7cc13c  ldloc.0
0x7cc13d  ldloc.3
0x7cc13e  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.SPFile::get_TimeLastModified()
0x7cc143  stloc.s  0xF
0x7cc145  ldloca.s 0xF
0x7cc147  ldstr    aO// "o"
0x7cc14c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7cc151  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0x7cc156  callvirt instance void Microsoft.SharePoint.Utilities.SPUnifiedAppsOfficeBundleQosEventBase::set_DocLastModifiedTimeUTC(string value)
0x7cc15b  ldloc.s  4
0x7cc15d  ldsfld   class [mscorlib]System.IO.Stream [mscorlib]System.IO.Stream::Null
0x7cc162  beq.s    loc_7CC172
0x7cc164  ldloc.s  4
0x7cc166  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x7cc16b  ldc.i4.0
0x7cc16c  conv.i8
0x7cc16d  bgt      loc_7CC21A
0x7cc172  ldc.i4   0x1723549
0x7cc177  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x7cc17c  stloc.s  5
0x7cc17e  ldloc.s  5
0x7cc180  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_WOPI()
0x7cc185  ldc.i4.s 0x14
0x7cc187  ldstr    aPrefetchandcac_2// "PrefetchAndCacheSSRForUnifiedApps: SSR "...
0x7cc18c  ldc.i4.6
0x7cc18d  newarr   [mscorlib]System.Object
0x7cc192  stloc.s  0x10
0x7cc194  ldloc.s  0x10
0x7cc196  ldc.i4.0
0x7cc197  ldarg.s  4
0x7cc199  stelem.ref
0x7cc19a  ldloc.s  0x10
0x7cc19c  ldc.i4.1
0x7cc19d  ldloc.3
0x7cc19e  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.SPFile::get_TimeCreated()
0x7cc1a3  box      [mscorlib]System.DateTime
0x7cc1a8  stelem.ref
0x7cc1a9  ldloc.s  0x10
0x7cc1ab  ldc.i4.2
0x7cc1ac  ldloc.3
0x7cc1ad  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.SPFile::get_TimeLastModified()
0x7cc1b2  box      [mscorlib]System.DateTime
0x7cc1b7  stelem.ref
0x7cc1b8  ldloc.s  0x10
0x7cc1ba  ldc.i4.3
0x7cc1bb  ldloc.3
0x7cc1bc  callvirt instance valuetype Microsoft.SharePoint.SPFileLevel Microsoft.SharePoint.SPFile::get_Level()
0x7cc1c1  box      Microsoft.SharePoint.SPFileLevel
0x7cc1c6  stelem.ref
0x7cc1c7  ldloc.s  0x10
0x7cc1c9  ldc.i4.4
0x7cc1ca  ldarg.1
0x7cc1cb  box      [mscorlib]System.Guid
0x7cc1d0  stelem.ref
0x7cc1d1  ldloc.s  0x10
0x7cc1d3  ldc.i4.5
0x7cc1d4  ldloc.3
0x7cc1d5  callvirt instance string Microsoft.SharePoint.SPFile::get_Name()
0x7cc1da  call     string [mscorlib]System.IO.Path::GetExtension(string)
0x7cc1df  stelem.ref
0x7cc1e0  ldloc.s  0x10
0x7cc1e2  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x7cc1e7  ldloc.0
0x7cc1e8  ldstr    aPrefetchssrnot// "PrefetchSSRNotFoundInStore"
0x7cc1ed  callvirt instance void Microsoft.SharePoint.Utilities.SPUnifiedAppsOfficeBundleQosEventBase::set_Status(string value)
0x7cc1f2  ldloc.0
0x7cc1f3  ldc.i4.4
0x7cc1f4  ldstr    aTryprefetchand// "TryPrefetchAndCacheSSRForUnifiedApps"
0x7cc1f9  ldstr    aDDbsElZltDevSt_37// "d:\\dbs\\el\\zlt\\dev\\sts\\stsom\\Util"...
0x7cc1fe  ldc.i4   0x1C8
0x7cc203  call     void Microsoft.SharePoint.Utilities.SPLogger::LogEvent(object e, [opt] valuetype Microsoft.SharePoint.Utilities.SPLogLevel level, [opt] string memberName, [opt] string filePath, [opt] int32 lineNumber)
0x7cc208  ldarg.0
0x7cc209  ldarg.s  9
0x7cc20b  ldarg.s  4
0x7cc20d  call     void Microsoft.SharePoint.Utilities.SPUnifiedAppsDistributedCacheUtils::GenerateSSROnDemand(string webUrl, string mediaTAGenerateSSRUrl, string prefetchAndCacheSSRCorrelationId)
0x7cc212  ldc.i4.0
0x7cc213  stloc.s  0xA
0x7cc215  leave    loc_7CC432
0x7cc21a  ldloc.s  4
0x7cc21c  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x7cc221  ldc.i4   0x200000
0x7cc226  conv.i8
0x7cc227  blt.s    loc_7CC295
0x7cc229  ldc.i4   0x172354A
0x7cc22e  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_WOPI()
0x7cc233  ldc.i4.s 0x14
0x7cc235  ldstr    aPrefetchandcac_3// "PrefetchAndCacheSSRForUnifiedApps: SSR "...
0x7cc23a  ldc.i4.2
0x7cc23b  newarr   [mscorlib]System.Object
0x7cc240  stloc.s  0x11
0x7cc242  ldloc.s  0x11
0x7cc244  ldc.i4.0
0x7cc245  ldloc.s  4
0x7cc247  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x7cc24c  box      [mscorlib]System.Int64
0x7cc251  stelem.ref
0x7cc252  ldloc.s  0x11
0x7cc254  ldc.i4.1
0x7cc255  ldarg.s  4
0x7cc257  stelem.ref
0x7cc258  ldloc.s  0x11
0x7cc25a  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x7cc25f  ldloc.0
0x7cc260  ldloc.s  4
0x7cc262  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x7cc267  callvirt instance void Microsoft.SharePoint.Utilities.SPUnifiedAppsSSRFetchQosEvent::set_StreamSizeInBytes(int64 value)
0x7cc26c  ldloc.0
0x7cc26d  ldstr    aPrefetchssrfou// "PrefetchSSRFoundInStore"
0x7cc272  callvirt instance void Microsoft.SharePoint.Utilities.SPUnifiedAppsOfficeBundleQosEventBase::set_Status(string value)
0x7cc277  ldloc.0
0x7cc278  ldc.i4.4
0x7cc279  ldstr    aTryprefetchand// "TryPrefetchAndCacheSSRForUnifiedApps"
0x7cc27e  ldstr    aDDbsElZltDevSt_37// "d:\\dbs\\el\\zlt\\dev\\sts\\stsom\\Util"...
0x7cc283  ldc.i4   0x1DB
0x7cc288  call     void Microsoft.SharePoint.Utilities.SPLogger::LogEvent(object e, [opt] valuetype Microsoft.SharePoint.Utilities.SPLogLevel level, [opt] string memberName, [opt] string filePath, [opt] int32 lineNumber)
0x7cc28d  ldc.i4.0
0x7cc28e  stloc.s  0xA
0x7cc290  leave    loc_7CC432
0x7cc295  ldc.i4   0x172354B
0x7cc29a  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_WOPI()
0x7cc29f  ldc.i4.s 0x32
0x7cc2a1  ldstr    aPrefetchandcac_4// "PrefetchAndCacheSSRForUnifiedApps: Succ"...
0x7cc2a6  ldc.i4.2
0x7cc2a7  newarr   [mscorlib]System.Object
0x7cc2ac  stloc.s  0x12
0x7cc2ae  ldloc.s  0x12
0x7cc2b0  ldc.i4.0
0x7cc2b1  ldloc.s  4
0x7cc2b3  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x7cc2b8  box      [mscorlib]System.Int64
0x7cc2bd  stelem.ref
0x7cc2be  ldloc.s  0x12
0x7cc2c0  ldc.i4.1
0x7cc2c1  ldarg.s  4
0x7cc2c3  stelem.ref
0x7cc2c4  ldloc.s  0x12
0x7cc2c6  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x7cc2cb  ldloc.0
0x7cc2cc  ldloc.s  4
0x7cc2ce  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x7cc2d3  callvirt instance void Microsoft.SharePoint.Utilities.SPUnifiedAppsSSRFetchQosEvent::set_StreamSizeInBytes(int64 value)
0x7cc2d8  ldloc.0
0x7cc2d9  ldstr    aPrefetchssrfou// "PrefetchSSRFoundInStore"
0x7cc2de  callvirt instance void Microsoft.SharePoint.Utilities.SPUnifiedAppsOfficeBundleQosEventBase::set_Status(string value)
0x7cc2e3  ldloc.0
0x7cc2e4  ldc.i4.4
0x7cc2e5  ldstr    aTryprefetchand// "TryPrefetchAndCacheSSRForUnifiedApps"
0x7cc2ea  ldstr    aDDbsElZltDevSt_37// "d:\\dbs\\el\\zlt\\dev\\sts\\stsom\\Util"...
0x7cc2ef  ldc.i4   0x1E8
0x7cc2f4  call     void Microsoft.SharePoint.Utilities.SPLogger::LogEvent(object e, [opt] valuetype Microsoft.SharePoint.Utilities.SPLogLevel level, [opt] string memberName, [opt] string filePath, [opt] int32 lineNumber)
0x7cc2f9  ldc.i4   0x172354C
0x7cc2fe  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_WOPI()
0x7cc303  ldc.i4.s 0x32
0x7cc305  ldstr    aPrefetchandcac_5// "PrefetchAndCacheSSRForUnifiedApps: Cach"...
0x7cc30a  ldc.i4.1
0x7cc30b  newarr   [mscorlib]System.Object
0x7cc310  stloc.s  0x13
0x7cc312  ldloc.s  0x13
0x7cc314  ldc.i4.0
0x7cc315  ldarg.s  4
0x7cc317  stelem.ref
0x7cc318  ldloc.s  0x13
0x7cc31a  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x7cc31f  ldloc.s  4
0x7cc321  call     unsigned int8[] Microsoft.SharePoint.Utilities.SPUnifiedAppsDistributedCacheUtils::ConvertSSRStreamToByteArray(class [mscorlib]System.IO.Stream s)
0x7cc326  stloc.s  6
0x7cc328  ldloc.3
0x7cc329  ldarg.2
0x7cc32a  call     string Microsoft.SharePoint.Utilities.SPUnifiedAppsDistributedCacheUtils::GenerateCacheKey(class Microsoft.SharePoint.SPFile file, valuetype [mscorlib]System.Guid streamIdGuid)
0x7cc32f  stloc.s  7
0x7cc331  ldc.i4   0x17800D3
0x7cc336  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_WOPI()
0x7cc33b  ldc.i4.s 0x32
0x7cc33d  ldstr    aPrefetchandcac_6// "PrefetchAndCacheSSRForUnifiedApps: (pre"...
0x7cc342  ldc.i4.2
0x7cc343  newarr   [mscorlib]System.Object
0x7cc348  stloc.s  0x14
0x7cc34a  ldloc.s  0x14
  ... truncated ...
```
