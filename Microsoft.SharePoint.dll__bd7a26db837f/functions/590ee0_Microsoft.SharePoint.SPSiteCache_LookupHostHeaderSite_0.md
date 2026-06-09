# Microsoft.SharePoint.SPSiteCache::LookupHostHeaderSite_0

- ea: `0x590ee0`
- end: `0x59184a`
- name: `Microsoft.SharePoint.SPSiteCache::LookupHostHeaderSite_0`
- size: `2410`
- prototype: ``
- caller_count: `2`
- callee_count: `47`
- tags: `service_task, broker_com_uri`

## callers

- `0x325ad0`
- `0x590cf0`

## callees

- `0x19e820`
- `0x1c87b0`
- `0x1c89b0`
- `0x1f79c0`
- `0x1f7d10`
- `0x1f8610`
- `0x1f8740`
- `0x249dc0`
- `0x249e90`
- `0x24bd10`
- `0x24bd20`
- `0x24bd30`
- `0x26b530`
- `0x32cb80`
- `0x32dbf0`
- `0x472c20`
- `0x52dcc0`
- `0x590360`
- `0x5903c0`
- `0x5903d0`
- `0x590b30`
- `0x590cb0`
- `0x590e40`
- `0x590ee0`
- `0x591850`
- `0x591c20`
- `0x592110`
- `0x592130`
- `0x592150`
- `0x592290`
- `0x5922b0`
- `0x5922d0`
- `0x5922f0`
- `0x592310`
- `0x592330`
- `0x6696d0`
- `0x669860`
- `0x7a0fb0`
- `0x7b4dc0`
- `0x7c78d0`
- `0x8ecdb0`
- `0x93dab0`
- `0x93dae0`
- `0x941d20`
- `0x957470`
- `0x9577d0`
- `0x957eb0`

## string_xrefs

- `0x59104d`: `in-memory cache`
- `0x590f2e`: `Skipping lookups for request Uri {0}.`
- `0x590ffa`: `Return early! Found negative sitemap key in the HttpContext for this Request Uri {0}.`
- `0x591029`: `Could not find negative sitemap key in HttpContext for this Request Uri {0}.`
- `0x5910d2`: `LookupHostHeaderSite: found appLookupInfo with lookup string {0} for request Uri {1} in {2}. SiteSubscriptionId {3}.`
- `0x5912b8`: `LookupHostHeaderSite: found appLookupInfo with lookup string {0} for request Uri {1} in {2}. SiteSubscriptionId {3}.`
- `0x591124`: `LookupHostHeaderSite: could not find appLookupInfo with lookup string {0} for request Uri {1} in {2}.`
- `0x591310`: `LookupHostHeaderSite: could not find appLookupInfo with lookup string {0} for request Uri {1} in {2}.`
- `0x59115c`: `LookupHostHeaderSite: found SPSiteLookupInfo with lookup string {0} for request Uri {1} in {2}. SiteSubscriptionId {3}.`
- `0x59134e`: `LookupHostHeaderSite: found SPSiteLookupInfo with lookup string {0} for request Uri {1} in {2}. SiteSubscriptionId {3}.`
- `0x59180c`: `LookupHostHeaderSite: found SPSiteLookupInfo with lookup string {0} for request Uri {1} in {2}. SiteSubscriptionId {3}.`
- `0x5911b7`: `File-system cache`
- `0x5911cf`: `Looking up HostHeaderSite in file system cachee`
- `0x591395`: `LookupHostHeaderSite: could not find SPSiteLookupInfo with lookup string {0} for request Uri {1} in {2}.`
- `0x5915a8`: `LookupHostHeaderSite: could not find SPSiteLookupInfo for host-header site-based multi-url lookup string {0} for request Uri {1} in {2}. UserAgent: {3}`
- `0x591608`: `Site not found in sitmap db! Setting negative sitemap key '{0}' for this Request Uri {1}.`
- `0x59163a`: `HttpContext is null! Could not set the negative sitemap key for Request Uri {0}.`
- `0x591697`: `LookupHostHeaderSite: Using site lookup provider {0} for multi-url lookup string {1} for request Uri {2}.`
- `0x5917c0`: `LookupHostHeaderSite: found appLookupInfo for lookup string {0} for request Uri {1} in {2}. SiteSubscriptionId {3}`

## pseudocode

```c

```

## disassembly

```asm
0x590ee0  ldarg.0
0x590ee1  ldnull
0x590ee2  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x590ee7  brtrue.s loc_590EFC
0x590ee9  ldarg.0
0x590eea  callvirt instance string [System]System.Uri::get_Host()
0x590eef  ldsfld   string Microsoft.SharePoint.Administration.SPConstants::EdgeProbesURISuffix
0x590ef4  ldc.i4.5
0x590ef5  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x590efa  brfalse.s loc_590F17
0x590efc  ldc.i4   0x131E204
0x590f01  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SiteCache()
0x590f06  ldc.i4   0xC8
0x590f0b  ldstr    aSkippingLookup// "Skipping lookups for Edge Probes."
0x590f10  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x590f15  ldnull
0x590f16  ret
0x590f17  ldarg.0
0x590f18  call     bool Microsoft.SharePoint.SPSiteCache::SkipLookupForUri(class [System]System.Uri requestUri)
0x590f1d  brfalse.s loc_590F4E
0x590f1f  ldc.i4   0x149C1CB
0x590f24  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SiteCache()
0x590f29  ldc.i4   0xC8
0x590f2e  ldstr    aSkippingLookup_0// "Skipping lookups for request Uri {0}."
0x590f33  ldc.i4.1
0x590f34  newarr   [mscorlib]System.Object
0x590f39  stloc.s  0x13
0x590f3b  ldloc.s  0x13
0x590f3d  ldc.i4.0
0x590f3e  ldarg.0
0x590f3f  callvirt instance string [mscorlib]System.Object::ToString()
0x590f44  stelem.ref
0x590f45  ldloc.s  0x13
0x590f47  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x590f4c  ldnull
0x590f4d  ret
0x590f4e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x590f53  stloc.0
0x590f54  ldnull
0x590f55  stloc.1
0x590f56  ldnull
0x590f57  stloc.2
0x590f58  ldarg.0
0x590f59  call     valuetype Microsoft.SharePoint.SPHostHeaderSiteUriScheme Microsoft.SharePoint.SPHostHeaderSiteUri::SchemeFromUri(class [System]System.Uri siteUri)
0x590f5e  stloc.3
0x590f5f  ldnull
0x590f60  stloc.s  4
0x590f62  ldc.i4.0
0x590f63  stloc.s  5
0x590f65  ldnull
0x590f66  stloc.s  6
0x590f68  ldnull
0x590f69  stloc.s  7
0x590f6b  ldnull
0x590f6c  stloc.s  8
0x590f6e  ldnull
0x590f6f  stloc.s  9
0x590f71  ldnull
0x590f72  stloc.s  0xA
0x590f74  ldnull
0x590f75  stloc.s  0xB
0x590f77  ldnull
0x590f78  stloc.s  0xC
0x590f7a  ldarg.0
0x590f7b  ldarg.1
0x590f7c  call     string Microsoft.SharePoint.SPSite::GetHostHeaderLookupKey(class [System]System.Uri uri, class Microsoft.SharePoint.Administration.SPFarm farm)
0x590f81  stloc.s  0xA
0x590f83  ldarg.0
0x590f84  ldc.i4.3
0x590f85  ldloca.s 6
0x590f87  ldloca.s 7
0x590f89  ldloca.s 8
0x590f8b  ldloca.s 9
0x590f8d  ldc.i4.1
0x590f8e  call     bool Microsoft.SharePoint.Utilities.SPUtility::IsAppWebUrl(class [System]System.Uri appWebUrl, valuetype AppWebUrlParsing parseFlags, string& appSiteDomainPrefix, string& subscriptionName, string& appSiteDomainId, string& appWebDomainId, bool verifyAppDomain)
0x590f93  stloc.s  5
0x590f95  ldloc.s  5
0x590f97  brfalse.s loc_590FA5
0x590f99  ldloc.s  6
0x590f9b  ldloc.3
0x590f9c  call     string Microsoft.SharePoint.SPSiteCache::GetLookupString(string hostHeaderLookupKey, valuetype Microsoft.SharePoint.SPHostHeaderSiteUriScheme scheme)
0x590fa1  stloc.s  0xB
0x590fa3  br.s     loc_590FBF
0x590fa5  ldloc.s  0xA
0x590fa7  callvirt instance int32 [mscorlib]System.String::get_Length()
0x590fac  ldc.i4   0x80
0x590fb1  ble.s    loc_590FB5
0x590fb3  ldnull
0x590fb4  ret
0x590fb5  ldloc.s  0xA
0x590fb7  ldloc.3
0x590fb8  call     string Microsoft.SharePoint.SPSiteCache::GetLookupString(string hostHeaderLookupKey, valuetype Microsoft.SharePoint.SPHostHeaderSiteUriScheme scheme)
0x590fbd  stloc.s  0xB
0x590fbf  ldstr    aNegativesitema// "NegativeSiteMap."
0x590fc4  ldloc.s  0xB
0x590fc6  call     string [mscorlib]System.String::Concat(string, string)
0x590fcb  stloc.s  0xC
0x590fcd  call     bool Microsoft.SharePoint.SPGlobal::get_IsSPO()
0x590fd2  brfalse.s loc_591047
0x590fd4  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x590fd9  brfalse.s loc_59101A
0x590fdb  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x590fe0  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x590fe5  ldloc.s  0xC
0x590fe7  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x590fec  brfalse.s loc_59101A
0x590fee  ldc.i4   0x1323400
0x590ff3  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SiteCache()
0x590ff8  ldc.i4.s 0x32
0x590ffa  ldstr    aReturnEarlyFou// "Return early! Found negative sitemap ke"...
0x590fff  ldc.i4.1
0x591000  newarr   [mscorlib]System.Object
0x591005  stloc.s  0x14
0x591007  ldloc.s  0x14
0x591009  ldc.i4.0
0x59100a  ldarg.0
0x59100b  callvirt instance string [mscorlib]System.Object::ToString()
0x591010  stelem.ref
0x591011  ldloc.s  0x14
0x591013  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x591018  ldnull
0x591019  ret
0x59101a  ldc.i4   0x1323401
0x59101f  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SiteCache()
0x591024  ldc.i4   0xC8
0x591029  ldstr    aCouldNotFindNe_0// "Could not find negative sitemap key in "...
0x59102e  ldc.i4.1
0x59102f  newarr   [mscorlib]System.Object
0x591034  stloc.s  0x15
0x591036  ldloc.s  0x15
0x591038  ldc.i4.0
0x591039  ldarg.0
0x59103a  callvirt instance string [mscorlib]System.Object::ToString()
0x59103f  stelem.ref
0x591040  ldloc.s  0x15
0x591042  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x591047  ldc.i4.0
0x591048  stloc.s  0xD
0x59104a  ldc.i4.0
0x59104b  stloc.s  0xE
0x59104d  ldstr    aInMemoryCache// "in-memory cache"
0x591052  stloc.s  0xF
0x591054  ldsfld   class Microsoft.SharePoint.Administration.SPVolatileCache`2<string, class Microsoft.SharePoint.Administration.SPSiteMultiUrlLookupInfo> Microsoft.SharePoint.SPSiteCache::s_HostHeaderLookupCache
0x591059  ldloc.s  0xB
0x59105b  callvirt instance var<u1> class Microsoft.SharePoint.Administration.SPCache`2<string, class Microsoft.SharePoint.Administration.SPSiteMultiUrlLookupInfo>::get_Item(void)
0x591060  stloc.2
0x591061  ldloc.2
0x591062  brfalse  loc_591197
0x591067  ldsfld   class Microsoft.SharePoint.SPSiteCachePerformanceCounter Microsoft.SharePoint.SPSiteCache::s_SPSiteCachePerformanceCounter
0x59106c  callvirt instance void Microsoft.SharePoint.SPSiteCachePerformanceCounter::IncrementTotalHNSCLookupInMemoryCacheHit()
0x591071  ldloc.2
0x591072  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPSiteMultiUrlLookupInfo::get_SiteId()
0x591077  stloc.0
0x591078  ldloc.0
0x591079  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x59107e  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x591083  brfalse  loc_59119A
0x591088  ldsfld   class Microsoft.SharePoint.Administration.SPVolatileCache`2<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Administration.SPSiteLookupInfo> Microsoft.SharePoint.SPSiteCache::s_LookupIdCache
0x59108d  ldloc.0
0x59108e  callvirt instance var<u1> class Microsoft.SharePoint.Administration.SPCache`2<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Administration.SPSiteLookupInfo>::get_Item(void)
0x591093  stloc.1
0x591094  ldloc.1
0x591095  brfalse  loc_59119A
0x59109a  ldsfld   class Microsoft.SharePoint.SPSiteCachePerformanceCounter Microsoft.SharePoint.SPSiteCache::s_SPSiteCachePerformanceCounter
0x59109f  callvirt instance void Microsoft.SharePoint.SPSiteCachePerformanceCounter::IncrementTotalSiteIdLookupInMemoryCacheHit()
0x5910a4  ldloc.s  5
0x5910a6  brfalse  loc_591150
0x5910ab  ldarg.1
0x5910ac  ldloc.1
0x5910ad  ldloc.2
0x5910ae  ldloc.s  7
0x5910b0  ldarg.0
0x5910b1  call     class Microsoft.SharePoint.Administration.SPAppSiteLookupInfoRequestContainer Microsoft.SharePoint.Administration.SPAppSiteLookupInfoRequestContainer::Create(class Microsoft.SharePoint.Administration.SPFarm farm, class Microsoft.SharePoint.Administration.SPSiteLookupInfo siteLookupInfo, class Microsoft.SharePoint.Administration.SPSiteMultiUrlLookupInfo multiUrlLookupInfo, string subscriptionName, class [System]System.Uri requestUri)
0x5910b6  stloc.s  4
0x5910b8  ldloc.s  4
0x5910ba  brfalse.s loc_59110F
0x5910bc  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x5910c1  call     void Microsoft.SharePoint.SPSiteCache::SetAppRequestState(class [System.Web]System.Web.HttpContext httpContext)
0x5910c6  ldc.i4   0x131E205
0x5910cb  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SiteCache()
0x5910d0  ldc.i4.s 0x64
0x5910d2  ldstr    aLookuphosthead// "LookupHostHeaderSite: found appLookupIn"...
0x5910d7  ldc.i4.4
0x5910d8  newarr   [mscorlib]System.Object
0x5910dd  stloc.s  0x16
0x5910df  ldloc.s  0x16
0x5910e1  ldc.i4.0
0x5910e2  ldloc.s  0xB
0x5910e4  stelem.ref
0x5910e5  ldloc.s  0x16
0x5910e7  ldc.i4.1
0x5910e8  ldarg.0
0x5910e9  callvirt instance string [mscorlib]System.Object::ToString()
0x5910ee  stelem.ref
0x5910ef  ldloc.s  0x16
0x5910f1  ldc.i4.2
0x5910f2  ldloc.s  0xF
0x5910f4  stelem.ref
0x5910f5  ldloc.s  0x16
0x5910f7  ldc.i4.3
0x5910f8  ldloc.s  4
0x5910fa  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPAppSiteLookupInfoRequestContainer::get_SiteSubscriptionId()
0x5910ff  box      [mscorlib]System.Guid
0x591104  stelem.ref
0x591105  ldloc.s  0x16
0x591107  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x59110c  ldloc.s  4
0x59110e  ret
0x59110f  ldloc.0
0x591110  call     bool Microsoft.SharePoint.SPSiteCache::ClearLookupIdCacheEntry(valuetype [mscorlib]System.Guid siteId)
0x591115  pop
0x591116  ldnull
0x591117  stloc.1
0x591118  ldc.i4   0x131E206
0x59111d  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SiteCache()
0x591122  ldc.i4.s 0x32
0x591124  ldstr    aLookuphosthead_0// "LookupHostHeaderSite: could not find ap"...
0x591129  ldc.i4.3
0x59112a  newarr   [mscorlib]System.Object
0x59112f  stloc.s  0x17
0x591131  ldloc.s  0x17
0x591133  ldc.i4.0
0x591134  ldloc.s  0xB
0x591136  stelem.ref
0x591137  ldloc.s  0x17
0x591139  ldc.i4.1
0x59113a  ldarg.0
0x59113b  callvirt instance string [mscorlib]System.Object::ToString()
0x591140  stelem.ref
0x591141  ldloc.s  0x17
0x591143  ldc.i4.2
0x591144  ldloc.s  0xF
0x591146  stelem.ref
0x591147  ldloc.s  0x17
0x591149  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x59114e  br.s     loc_59119A
0x591150  ldc.i4   0x131E207
0x591155  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SiteCache()
0x59115a  ldc.i4.s 0x64
0x59115c  ldstr    aLookuphosthead_1// "LookupHostHeaderSite: found SPSiteLooku"...
0x591161  ldc.i4.4
0x591162  newarr   [mscorlib]System.Object
0x591167  stloc.s  0x18
0x591169  ldloc.s  0x18
0x59116b  ldc.i4.0
0x59116c  ldloc.s  0xB
0x59116e  stelem.ref
0x59116f  ldloc.s  0x18
0x591171  ldc.i4.1
0x591172  ldarg.0
0x591173  callvirt instance string [mscorlib]System.Object::ToString()
0x591178  stelem.ref
0x591179  ldloc.s  0x18
0x59117b  ldc.i4.2
0x59117c  ldloc.s  0xF
0x59117e  stelem.ref
0x59117f  ldloc.s  0x18
0x591181  ldc.i4.3
0x591182  ldloc.1
0x591183  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPSiteLookupInfo::get_SiteSubscriptionId()
0x591188  box      [mscorlib]System.Guid
0x59118d  stelem.ref
0x59118e  ldloc.s  0x18
0x591190  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x591195  ldloc.1
0x591196  ret
0x591197  ldc.i4.1
0x591198  stloc.s  0xD
0x59119a  ldloc.0
0x59119b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5911a0  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5911a5  brtrue.s loc_5911AD
0x5911a7  ldloc.1
0x5911a8  brtrue   loc_5913D8
0x5911ad  call     bool Microsoft.SharePoint.SPSiteCache::get_IsFileSystemCacheEnabled()
0x5911b2  brfalse  loc_5913D8
0x5911b7  ldstr    aFileSystemCach_3// "File-system cache"
0x5911bc  stloc.s  0xF
0x5911be  ldc.i4   0x68D74B
0x5911c3  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x5911c8  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Monitoring()
0x5911cd  ldc.i4.s 0x64
0x5911cf  ldstr    aLookingUpHosth// "Looking up HostHeaderSite in file syste"...
0x5911d4  ldc.i4.2
0x5911d5  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x5911da  stloc.s  0x19
0x5911dc  ldloc.s  0x19
0x5911de  ldc.i4.0
0x5911df  ldc.i4.5
0x5911e0  newobj   instance void Microsoft.SharePoint.Utilities.SPExecutionTimeCounter::.ctor(unsigned int32 maxValue)
0x5911e5  stelem.ref
0x5911e6  ldloc.s  0x19
0x5911e8  ldc.i4.1
0x5911e9  newobj   instance void Microsoft.SharePoint.Utilities.SPCPUCycleCounter::.ctor()
0x5911ee  stelem.ref
0x5911ef  ldloc.s  0x19
0x5911f1  call     class [mscorlib]System.IDisposable Microsoft.SharePoint.Utilities.SPMonitoredScopeFactory::Create(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCatBase category, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string name, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x5911f6  stloc.s  0x1A
0x5911f8  call     class Microsoft.SharePoint.Administration.SPSiteMultiUrlLookupFileSystemCache Microsoft.SharePoint.SPSiteCache::get_SiteMultiUrlLookupFSCache()
0x5911fd  ldloc.s  0xB
  ... truncated ...
```
