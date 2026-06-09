# Microsoft.SharePoint.SPTenantStore::LoadFromDBOrCache

- ea: `0x5a7710`
- end: `0x5a7e8c`
- name: `Microsoft.SharePoint.SPTenantStore::LoadFromDBOrCache`
- size: `1916`
- prototype: ``
- caller_count: `3`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x5a7f00`
- `0x5a80a0`
- `0x5a8230`

## callees

- `0x5a7400`
- `0x5a74f0`
- `0x5a7700`
- `0x5a7710`
- `0x5a83a0`
- `0x5a86c0`
- `0x5a8a50`
- `0x5a9820`
- `0x5a9830`
- `0x5a98b0`
- `0x5a9930`
- `0x5a9cb0`
- `0x5aaf30`
- `0x5aaf50`
- `0x5aaf70`
- `0x5ab350`
- `0x5ab770`
- `0x5abb00`
- `0x5ac5a0`
- `0x6c9890`
- `0x93dae0`
- `0x957470`

## string_xrefs

- `0x5a771c`: `LoadFromDBOrCache: Enter: cacheKey [{0}], useTenantStoreCache [{1}], siteID [{2}], siteUrl [{3}], freshnessDelay[{4}].`
- `0x5a77fa`: `LoadFromDBOrCache`
- `0x5a78d2`: `LoadFromDBOrCache - noMemCache`
- `0x5a78f9`: `LoadFromDBOrCache: Could not perform optimization for non-cache access for cacheKey [{0)], reverting to DB Access. Exception: {1}`
- `0x5a7a11`: `LoadFromDBOrCache: Tenant Store Cache hit for cacheKey: {0}`
- `0x5a7a64`: `LoadFromDBOrCache: Tenant Store Cache up to date for cacheKey: {0}`
- `0x5a7a9c`: `LoadFromDBOrCache: Tenant Store Cache expired for cacheKey: {0}`
- `0x5a7ae6`: `LoadFromDBOrCache - existsInMemCache`
- `0x5a7c09`: `LoadFromDBOrCache: Tenant Store Cache reloaded with fresh data for cacheKey: {0}`
- `0x5a7c6d`: `LoadFromDBOrCache: Tenant Store Cache miss for cacheKey: {0}`
- `0x5a7cb7`: `LoadFromDBOrCache - notInMemCache`
- `0x5a7dda`: `LoadFromDBOrCache: Tenant Store Cache loaded with data for cacheKey: {0}`
- `0x5a7e3d`: `LoadFromDBOrCache: Reverting to not using the cache for cacheKey: {0}. Exception: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x5a7710  ldc.i4   0x1142094
0x5a7715  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x5a771a  ldc.i4.s 0x64
0x5a771c  ldstr    aLoadfromdborca// "LoadFromDBOrCache: Enter: cacheKey [{0}"...
0x5a7721  ldc.i4.5
0x5a7722  newarr   [mscorlib]System.Object
0x5a7727  stloc.s  0x19
0x5a7729  ldloc.s  0x19
0x5a772b  ldc.i4.0
0x5a772c  ldarg.0
0x5a772d  box      [mscorlib]System.Guid
0x5a7732  stelem.ref
0x5a7733  ldloc.s  0x19
0x5a7735  ldc.i4.1
0x5a7736  ldarg.1
0x5a7737  box      [mscorlib]System.Boolean
0x5a773c  stelem.ref
0x5a773d  ldloc.s  0x19
0x5a773f  ldc.i4.2
0x5a7740  ldarg.s  4
0x5a7742  box      [mscorlib]System.Guid
0x5a7747  stelem.ref
0x5a7748  ldloc.s  0x19
0x5a774a  ldc.i4.3
0x5a774b  ldarg.s  5
0x5a774d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5a7752  brtrue.s loc_5A7758
0x5a7754  ldarg.s  5
0x5a7756  br.s     loc_5A775D
0x5a7758  ldstr    aEmpty_3// "<empty>"
0x5a775d  stelem.ref
0x5a775e  ldloc.s  0x19
0x5a7760  ldc.i4.4
0x5a7761  ldarg.s  6
0x5a7763  box      [mscorlib]System.Int32
0x5a7768  stelem.ref
0x5a7769  ldloc.s  0x19
0x5a776b  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x5a7770  ldarg.s  6
0x5a7772  ldsfld   int32 Microsoft.SharePoint.SPTenantStore::propertyCacheMinTTLInMin
0x5a7777  blt.s    loc_5A7782
0x5a7779  ldarg.s  6
0x5a777b  ldsfld   int32 Microsoft.SharePoint.SPTenantStore::propertyCacheMaxTTLInMin
0x5a7780  ble.s    loc_5A77E2
0x5a7782  ldc.i4.7
0x5a7783  newarr   [mscorlib]System.Object
0x5a7788  stloc.s  0x1A
0x5a778a  ldloc.s  0x1A
0x5a778c  ldc.i4.0
0x5a778d  ldstr    aFreshnessdelay// "freshnessDelayToleranceInMinutes ["
0x5a7792  stelem.ref
0x5a7793  ldloc.s  0x1A
0x5a7795  ldc.i4.1
0x5a7796  ldarg.s  6
0x5a7798  box      [mscorlib]System.Int32
0x5a779d  stelem.ref
0x5a779e  ldloc.s  0x1A
0x5a77a0  ldc.i4.2
0x5a77a1  ldstr    aMustBeBetween// "] must be between ["
0x5a77a6  stelem.ref
0x5a77a7  ldloc.s  0x1A
0x5a77a9  ldc.i4.3
0x5a77aa  ldsfld   int32 Microsoft.SharePoint.SPTenantStore::propertyCacheMinTTLInMin
0x5a77af  box      [mscorlib]System.Int32
0x5a77b4  stelem.ref
0x5a77b5  ldloc.s  0x1A
0x5a77b7  ldc.i4.4
0x5a77b8  ldstr    aAnd_4// "] and ["
0x5a77bd  stelem.ref
0x5a77be  ldloc.s  0x1A
0x5a77c0  ldc.i4.5
0x5a77c1  ldsfld   int32 Microsoft.SharePoint.SPTenantStore::propertyCacheMaxTTLInMin
0x5a77c6  box      [mscorlib]System.Int32
0x5a77cb  stelem.ref
0x5a77cc  ldloc.s  0x1A
0x5a77ce  ldc.i4.6
0x5a77cf  ldstr    asc_C681A6// "]"
0x5a77d4  stelem.ref
0x5a77d5  ldloc.s  0x1A
0x5a77d7  call     string [mscorlib]System.String::Concat(object[])
0x5a77dc  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x5a77e1  throw
0x5a77e2  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPTenantStore::UseTenantStoreDiskCacheKillSwitch
0x5a77e7  ldsfld   string Microsoft.SharePoint.SPTenantStore::UseTenantStoreDiskCacheKillSwitchLastModifiedDate
0x5a77ec  ldsfld   string Microsoft.SharePoint.SPTenantStore::UseTenantStoreDiskCacheKillSwitchLabel
0x5a77f1  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x5a77f6  stloc.0
0x5a77f7  ldloc.0
0x5a77f8  brtrue.s loc_5A7806
0x5a77fa  ldstr    aLoadfromdborca_0// "LoadFromDBOrCache"
0x5a77ff  call     bool Microsoft.SharePoint.SPTenantStore::ShouldUseTenantStoreCache(string methodName)
0x5a7804  br.s     loc_5A7807
0x5a7806  ldc.i4.0
0x5a7807  stloc.1
0x5a7808  ldloc.1
0x5a7809  brfalse.s loc_5A7819
0x5a780b  ldarg.s  6
0x5a780d  ldsfld   int32 Microsoft.SharePoint.SPTenantStore::propertyCacheTTLInMin
0x5a7812  clt
0x5a7814  ldc.i4.0
0x5a7815  ceq
0x5a7817  br.s     loc_5A781A
0x5a7819  ldc.i4.0
0x5a781a  stloc.2
0x5a781b  ldc.i4.0
0x5a781c  stloc.3
0x5a781d  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x5a7822  stloc.s  4
0x5a7824  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPTenantStore::GranularLockTenantStoreCacheKillSwitch
0x5a7829  ldsfld   string Microsoft.SharePoint.SPTenantStore::GranularLockTenantStoreCacheKillSwitchLastModified
0x5a782e  ldsfld   string Microsoft.SharePoint.SPTenantStore::GranularLockTenantStoreCacheKillSwitchLabel
0x5a7833  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x5a7838  ldc.i4.0
0x5a7839  ceq
0x5a783b  stloc.s  5
0x5a783d  ldc.i4.0
0x5a783e  stloc.s  6
0x5a7840  ldarg.1
0x5a7841  brtrue   loc_5A7924
0x5a7846  ldloc.2
0x5a7847  brfalse  loc_5A7924
0x5a784c  ldloc.3
0x5a784d  brfalse  loc_5A78E9
0x5a7852  ldarg.3
0x5a7853  ldarg.s  4
0x5a7855  ldarg.s  5
0x5a7857  call     valuetype [mscorlib]System.DateTime TenantStoreDiskCache::GetTenantStorePropertiesChanged(valuetype [mscorlib]System.Guid siteSubscriptionId, valuetype [mscorlib]System.Guid siteId, string siteUrl)
0x5a785c  stloc.s  7
0x5a785e  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x5a7863  stloc.s  8
0x5a7865  ldloca.s 9
0x5a7867  ldc.i4.0
0x5a7868  ldarg.s  6
0x5a786a  ldc.i4.0
0x5a786b  call     instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x5a7870  ldloc.s  7
0x5a7872  ldloca.s 8
0x5a7874  ldloc.s  9
0x5a7876  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Subtract(valuetype [mscorlib]System.TimeSpan)
0x5a787b  call     bool [mscorlib]System.DateTime::op_LessThanOrEqual(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x5a7880  brfalse.s loc_5A78E9
0x5a7882  ldsfld   class TenantStoreDiskCache Microsoft.SharePoint.SPTenantStore::cacheTenantStoreOnDisk
0x5a7887  brtrue.s loc_5A78BA
0x5a7889  ldc.i4.0
0x5a788a  stloc.s  0xA
0x5a788c  ldsfld   object Microsoft.SharePoint.SPTenantStore::lockTenantStoreCache
0x5a7891  dup
0x5a7892  stloc.s  0x1B
0x5a7894  ldloca.s 0xA
0x5a7896  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x5a789b  ldsfld   class TenantStoreDiskCache Microsoft.SharePoint.SPTenantStore::cacheTenantStoreOnDisk
0x5a78a0  brtrue.s loc_5A78AC
0x5a78a2  newobj   instance void TenantStoreDiskCache::.ctor()
0x5a78a7  stsfld   class TenantStoreDiskCache Microsoft.SharePoint.SPTenantStore::cacheTenantStoreOnDisk
0x5a78ac  leave.s  loc_5A78BA
0x5a78ae  ldloc.s  0xA
0x5a78b0  brfalse.s loc_5A78B9
0x5a78b2  ldloc.s  0x1B
0x5a78b4  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x5a78b9  endfinally
0x5a78ba  ldsfld   class TenantStoreDiskCache Microsoft.SharePoint.SPTenantStore::cacheTenantStoreOnDisk
0x5a78bf  ldarg.0
0x5a78c0  ldarg.1
0x5a78c1  ldarg.2
0x5a78c2  ldarg.3
0x5a78c3  ldarg.s  4
0x5a78c5  ldarg.s  5
0x5a78c7  ldarg.s  6
0x5a78c9  callvirt instance class Microsoft.SharePoint.SPTenantStore TenantStoreDiskCache::LoadFromFileSystemCache(valuetype [mscorlib]System.Guid cacheKey, bool useTenantStoreCache, valuetype [mscorlib]System.Guid companyId, valuetype [mscorlib]System.Guid siteSubscriptionId, valuetype [mscorlib]System.Guid siteID, string siteUrl, int32 freshnessDelayToleranceInMinutes)
0x5a78ce  stloc.s  0xB
0x5a78d0  ldloc.s  4
0x5a78d2  ldstr    aLoadfromdborca_1// "LoadFromDBOrCache - noMemCache"
0x5a78d7  call     void Microsoft.SharePoint.SPTenantStore::BackoffTenantStoreCacheIfNecessary(valuetype [mscorlib]System.DateTime startTime, string methodName)
0x5a78dc  ldloc.s  0xB
0x5a78de  brfalse.s loc_5A78E9
0x5a78e0  ldloc.s  0xB
0x5a78e2  stloc.s  0x18
0x5a78e4  leave    loc_5A7E89
0x5a78e9  leave.s  loc_5A7924
0x5a78eb  stloc.s  0xC
0x5a78ed  ldc.i4   0x135C6C0
0x5a78f2  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x5a78f7  ldc.i4.s 0xA
0x5a78f9  ldstr    aLoadfromdborca_2// "LoadFromDBOrCache: Could not perform op"...
0x5a78fe  ldc.i4.2
0x5a78ff  newarr   [mscorlib]System.Object
0x5a7904  stloc.s  0x1C
0x5a7906  ldloc.s  0x1C
0x5a7908  ldc.i4.0
0x5a7909  ldarg.0
0x5a790a  box      [mscorlib]System.Guid
0x5a790f  stelem.ref
0x5a7910  ldloc.s  0x1C
0x5a7912  ldc.i4.1
0x5a7913  ldloc.s  0xC
0x5a7915  callvirt instance string [mscorlib]System.Object::ToString()
0x5a791a  stelem.ref
0x5a791b  ldloc.s  0x1C
0x5a791d  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x5a7922  leave.s  loc_5A7924
0x5a7924  ldarg.1
0x5a7925  brtrue   loc_5A79BB
0x5a792a  ldloc.s  6
0x5a792c  brfalse.s loc_5A7966
0x5a792e  ldsfld   class TenantStoreDiskCache Microsoft.SharePoint.SPTenantStore::cacheTenantStoreOnDisk
0x5a7933  brtrue.s loc_5A7966
0x5a7935  ldc.i4.0
0x5a7936  stloc.s  0xD
0x5a7938  ldsfld   object Microsoft.SharePoint.SPTenantStore::lockTenantStoreCache
0x5a793d  dup
0x5a793e  stloc.s  0x1D
0x5a7940  ldloca.s 0xD
0x5a7942  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x5a7947  ldsfld   class TenantStoreDiskCache Microsoft.SharePoint.SPTenantStore::cacheTenantStoreOnDisk
0x5a794c  brtrue.s loc_5A7958
0x5a794e  newobj   instance void TenantStoreDiskCache::.ctor()
0x5a7953  stsfld   class TenantStoreDiskCache Microsoft.SharePoint.SPTenantStore::cacheTenantStoreOnDisk
0x5a7958  leave.s  loc_5A7966
0x5a795a  ldloc.s  0xD
0x5a795c  brfalse.s loc_5A7965
0x5a795e  ldloc.s  0x1D
0x5a7960  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x5a7965  endfinally
0x5a7966  ldarg.s  4
0x5a7968  ldarg.s  5
0x5a796a  call     class Microsoft.SharePoint.SPSite Microsoft.SharePoint.SPTenantStore::LoadSPSite(valuetype [mscorlib]System.Guid siteId, string url)
0x5a796f  ldarg.1
0x5a7970  newobj   instance void Microsoft.SharePoint.SPTenantStore::.ctor(class Microsoft.SharePoint.SPSite fundamentalSite, bool isCachedObject)
0x5a7975  stloc.s  0xE
0x5a7977  ldloc.s  0xE
0x5a7979  ldc.i4.1
0x5a797a  ldloc.1
0x5a797b  callvirt instance void Microsoft.SharePoint.SPTenantStore::RefreshFundamentalSite(bool force, bool refreshPropertyBag)
0x5a7980  ldloc.s  6
0x5a7982  brfalse.s loc_5A79B2
0x5a7984  ldsfld   class TenantStoreDiskCache Microsoft.SharePoint.SPTenantStore::cacheTenantStoreOnDisk
0x5a7989  ldarg.0
0x5a798a  ldloc.s  0xE
0x5a798c  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.SPTenantStore::m_fundamentalSitePropertyBag
0x5a7991  ldloc.s  0xE
0x5a7993  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPTenantStore::get_CompanyId()
0x5a7998  ldloc.s  0xE
0x5a799a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPTenantStore::get_SiteSubscriptionId()
0x5a799f  ldloc.s  0xE
0x5a79a1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPTenantStore::get_SiteId()
0x5a79a6  ldloc.s  0xE
0x5a79a8  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPTenantStore::get_DatabaseId()
0x5a79ad  callvirt instance void TenantStoreDiskCache::WriteToFileSystemCache(valuetype [mscorlib]System.Guid cacheKey, class [mscorlib]System.Collections.Hashtable fundamentalPropertyBag, valuetype [mscorlib]System.Guid companyId, valuetype [mscorlib]System.Guid siteSubscriptionId, valuetype [mscorlib]System.Guid siteId, valuetype [mscorlib]System.Guid databaseId)
0x5a79b2  ldloc.s  0xE
0x5a79b4  stloc.s  0x18
0x5a79b6  leave    loc_5A7E89
0x5a79bb  ldsfld   object Microsoft.SharePoint.SPTenantStore::lockTenantStoreCache
0x5a79c0  call     void [mscorlib]System.Threading.Monitor::Enter(object)
0x5a79c5  ldloc.1
0x5a79c6  brfalse.s loc_5A79D9
0x5a79c8  ldsfld   class TenantStoreDiskCache Microsoft.SharePoint.SPTenantStore::cacheTenantStoreOnDisk
0x5a79cd  brtrue.s loc_5A79D9
0x5a79cf  newobj   instance void TenantStoreDiskCache::.ctor()
0x5a79d4  stsfld   class TenantStoreDiskCache Microsoft.SharePoint.SPTenantStore::cacheTenantStoreOnDisk
0x5a79d9  ldnull
0x5a79da  stloc.s  0xF
0x5a79dc  ldsfld   class Microsoft.SharePoint.Administration.SPVolatileCache`2<valuetype [mscorlib]System.Guid, class TenantStoreCacheEntry> Microsoft.SharePoint.SPTenantStore::cacheTenantStore
0x5a79e1  ldarg.0
0x5a79e2  ldloca.s 0xF
0x5a79e4  callvirt instance bool class Microsoft.SharePoint.Administration.SPVolatileCache`2<valuetype [mscorlib]System.Guid, class TenantStoreCacheEntry>::TryGetValue(var<u1>, !!T0)
0x5a79e9  stloc.s  0x10
0x5a79eb  ldloc.s  0x10
0x5a79ed  brfalse  loc_5A7C61
0x5a79f2  ldloc.s  0xF
0x5a79f4  brfalse  loc_5A7C61
0x5a79f9  ldloc.s  0xF
0x5a79fb  callvirt instance class Microsoft.SharePoint.SPTenantStore TenantStoreCacheEntry::get_TenantStore()
0x5a7a00  brfalse  loc_5A7C61
0x5a7a05  ldc.i4   0x1142095
0x5a7a0a  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x5a7a0f  ldc.i4.s 0x64
0x5a7a11  ldstr    aLoadfromdborca_3// "LoadFromDBOrCache: Tenant Store Cache h"...
0x5a7a16  ldc.i4.1
0x5a7a17  newarr   [mscorlib]System.Object
0x5a7a1c  stloc.s  0x1E
0x5a7a1e  ldloc.s  0x1E
0x5a7a20  ldc.i4.0
0x5a7a21  ldarg.0
0x5a7a22  box      [mscorlib]System.Guid
0x5a7a27  stelem.ref
0x5a7a28  ldloc.s  0x1E
0x5a7a2a  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x5a7a2f  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x5a7a34  stloc.s  0x11
0x5a7a36  ldloca.s 0x12
0x5a7a38  ldc.i4.0
0x5a7a39  ldarg.s  6
0x5a7a3b  ldc.i4.0
0x5a7a3c  call     instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x5a7a41  ldloca.s 0x11
0x5a7a43  ldloc.s  0x12
0x5a7a45  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Subtract(valuetype [mscorlib]System.TimeSpan)
0x5a7a4a  ldloc.s  0xF
0x5a7a4c  callvirt instance valuetype [mscorlib]System.DateTime TenantStoreCacheEntry::get_TimeStamp()
0x5a7a51  call     bool [mscorlib]System.DateTime::op_LessThanOrEqual(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
  ... truncated ...
```
