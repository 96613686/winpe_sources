# TenantStoreDiskCache::GetDatabasesHoldingTenantStoresOnDisk

- ea: `0x5abf60`
- end: `0x5ac592`
- name: `TenantStoreDiskCache::GetDatabasesHoldingTenantStoresOnDisk`
- size: `1586`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x5acd80`

## callees

- `0x1c8480`
- `0x1c8540`
- `0x2ed980`
- `0x5aafa0`
- `0x5aafc0`
- `0x5aafe0`
- `0x5ab000`
- `0x5ab020`
- `0x5ab220`
- `0x5ab350`
- `0x5abf60`
- `0x5ad690`
- `0x93dab0`
- `0x93dae0`
- `0x945c80`
- `0x957470`

## string_xrefs

- `0x5ac00d`: `GetDatabasesHoldingTenantStoresOnDisk: First-time or forced access to databaseList on disk - ready to compute from cached tenant stores`
- `0x5ac05b`: `GetDatabasesHoldingTenantStoresOnDisk: attempting to scan sub directory {0}`
- `0x5ac0e5`: `GetDatabasesHoldingTenantStoresOnDisk: Read [{0}] bytes from file [{1}].`
- `0x5ac132`: `GetDatabasesHoldingTenantStoresOnDisk: Could not read TenantStoreDiskCacheEntry from file [{0}], ignoring Exception: [{1}]`
- `0x5ac21a`: `GetDatabasesHoldingTenantStoresOnDisk: Purged old cache entry with key: CompanyId [{0}], SiteSubscriptionId [{1}], SiteId [{2}], DatabaseId [{3}].`
- `0x5ac281`: `GetDatabasesHoldingTenantStoresOnDisk: Could NOT purge old cache entry with key: CompanyId [{0}], SiteSubscriptionId [{1}], SiteId [{2}], DatabaseId [{3}]: Exception [{4}].`
- `0x5ac31e`: `GetDatabasesHoldingTenantStoresOnDisk: Found new DatabaesId to refresh from: [{0}].`
- `0x5ac359`: `GetDatabasesHoldingTenantStoresOnDisk: Could not read all TenantStoreDiskCacheEntries from directory [{0}], ignoring Exception: [{1}]`
- `0x5ac3a1`: `GetDatabasesHoldingTenantStoresOnDisk: cache does not exist at directory {0}, skipping...`
- `0x5ac3e5`: `GetDatabasesHoldingTenantStoresOnDisk: First-time or forced load: Could not process existing databaseList on disk from cacheDirectory [{0}], ignoring Exception: [{1}]`
- `0x5ac47a`: `Could NOT update`
- `0x5ac481`: `Successfully updated`
- `0x5ac547`: `GetDatabasesHoldingTenantStoresOnDisk : Skipping Database [{0}] since no cached tenant store from it on disk.`

## pseudocode

```c

```

## disassembly

```asm
0x5abf60  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPContentDatabase>::.ctor()
0x5abf65  stloc.0
0x5abf66  ldarg.1
0x5abf67  brfalse.s loc_5ABF72
0x5abf69  ldarg.1
0x5abf6a  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPContentDatabase>::get_Count()
0x5abf6f  ldc.i4.0
0x5abf70  bgt.s    loc_5ABF74
0x5abf72  ldloc.0
0x5abf73  ret
0x5abf74  ldarg.0
0x5abf75  call     instance string class Microsoft.SharePoint.Administration.SPFileSystemSubCache`2<valuetype [mscorlib]System.Guid, class TenantStoreDiskCacheEntry>::get_CacheDirectory()
0x5abf7a  ldstr    aDatabaselistIn// "DatabaseList.ini"
0x5abf7f  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x5abf84  stloc.1
0x5abf85  ldnull
0x5abf86  stloc.2
0x5abf87  ldc.i4.0
0x5abf88  stloc.3
0x5abf89  call     class Microsoft.SharePoint.Utilities.SecurityContext Microsoft.SharePoint.Utilities.SecurityContext::RevertToSelf()
0x5abf8e  stloc.s  4
0x5abf90  ldc.i4.0
0x5abf91  ldc.i4.s 0xA
0x5abf93  call     int32 SRandom::Random(int32 min, int32 max)
0x5abf98  ldc.i4.s 9
0x5abf9a  clt
0x5abf9c  ldc.i4.0
0x5abf9d  ceq
0x5abf9f  stloc.s  5
0x5abfa1  ldloc.s  5
0x5abfa3  brfalse.s loc_5ABFA9
0x5abfa5  ldnull
0x5abfa6  stloc.2
0x5abfa7  br.s     loc_5ABFDE
0x5abfa9  ldloc.1
0x5abfaa  call     string[] [mscorlib]System.IO.File::ReadAllLines(string)
0x5abfaf  stloc.2
0x5abfb0  leave.s  loc_5ABFDE
0x5abfb2  stloc.s  6
0x5abfb4  ldc.i4   0x13C7782
0x5abfb9  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x5abfbe  ldc.i4.s 0x14
0x5abfc0  ldstr    aGetdatabasesho// "GetDatabasesHoldingTenantStoresOnDisk: "...
0x5abfc5  ldc.i4.1
0x5abfc6  newarr   [mscorlib]System.Object
0x5abfcb  stloc.s  0x18
0x5abfcd  ldloc.s  0x18
0x5abfcf  ldc.i4.0
0x5abfd0  ldloc.s  6
0x5abfd2  stelem.ref
0x5abfd3  ldloc.s  0x18
0x5abfd5  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x5abfda  ldnull
0x5abfdb  stloc.2
0x5abfdc  leave.s  loc_5ABFDE
0x5abfde  ldloc.2
0x5abfdf  brfalse.s loc_5ABFEA
0x5abfe1  ldloc.2
0x5abfe2  ldlen
0x5abfe3  conv.i4
0x5abfe4  ldc.i4.0
0x5abfe5  bgt      loc_5AC48E
0x5abfea  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x5abfef  stloc.s  0x19
0x5abff1  ldloca.s 0x19
0x5abff3  ldsfld   int32 Microsoft.SharePoint.SPTenantStore::propertyCacheFlushTTLInMin
0x5abff8  neg
0x5abff9  conv.r8
0x5abffa  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x5abfff  stloc.s  7
0x5ac001  ldc.i4   0x13C7783
0x5ac006  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x5ac00b  ldc.i4.s 0x14
0x5ac00d  ldstr    aGetdatabasesho_0// "GetDatabasesHoldingTenantStoresOnDisk: "...
0x5ac012  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x5ac017  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x5ac01c  stloc.s  8
0x5ac01e  ldarg.0
0x5ac01f  call     instance string class Microsoft.SharePoint.Administration.SPFileSystemSubCache`2<valuetype [mscorlib]System.Guid, class TenantStoreDiskCacheEntry>::get_CacheDirectory()
0x5ac024  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x5ac029  stloc.s  9
0x5ac02b  ldloc.s  9
0x5ac02d  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0x5ac032  brfalse  loc_5AC395
0x5ac037  ldloc.s  9
0x5ac039  callvirt instance class [mscorlib]System.IO.DirectoryInfo[] [mscorlib]System.IO.DirectoryInfo::GetDirectories()
0x5ac03e  stloc.s  0x1A
0x5ac040  ldc.i4.0
0x5ac041  stloc.s  0x1B
0x5ac043  br       loc_5AC388
0x5ac048  ldloc.s  0x1A
0x5ac04a  ldloc.s  0x1B
0x5ac04c  ldelem.ref
0x5ac04d  stloc.s  0xA
0x5ac04f  ldc.i4   0x13C7784
0x5ac054  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x5ac059  ldc.i4.s 0x32
0x5ac05b  ldstr    aGetdatabasesho_1// "GetDatabasesHoldingTenantStoresOnDisk: "...
0x5ac060  ldc.i4.1
0x5ac061  newarr   [mscorlib]System.Object
0x5ac066  stloc.s  0x1C
0x5ac068  ldloc.s  0x1C
0x5ac06a  ldc.i4.0
0x5ac06b  ldloc.s  0xA
0x5ac06d  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x5ac072  stelem.ref
0x5ac073  ldloc.s  0x1C
0x5ac075  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x5ac07a  ldloc.s  0xA
0x5ac07c  callvirt instance class [mscorlib]System.IO.FileInfo[] [mscorlib]System.IO.DirectoryInfo::GetFiles()
0x5ac081  stloc.s  0x1D
0x5ac083  ldc.i4.0
0x5ac084  stloc.s  0x1E
0x5ac086  br       loc_5AC33E
0x5ac08b  ldloc.s  0x1D
0x5ac08d  ldloc.s  0x1E
0x5ac08f  ldelem.ref
0x5ac090  stloc.s  0xB
0x5ac092  ldnull
0x5ac093  stloc.s  0xC
0x5ac095  ldloc.s  0xB
0x5ac097  ldc.i4.0
0x5ac098  call     class [mscorlib]System.IO.FileStream Microsoft.SharePoint.Administration.SPServer::OpenFile(class [mscorlib]System.IO.FileInfo fi, bool forWriting)
0x5ac09d  stloc.s  0xD
0x5ac09f  ldloc.s  0xD
0x5ac0a1  brtrue.s loc_5AC0A8
0x5ac0a3  leave    loc_5AC338
0x5ac0a8  ldloc.s  0xD
0x5ac0aa  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.Stream)
0x5ac0af  stloc.s  0xE
0x5ac0b1  ldsfld   class [System.Runtime.Serialization]System.Runtime.Serialization.DataContractSerializer TenantStoreDiskCache::TenantStoreDiskCacheEntrySerializer
0x5ac0b6  ldloc.s  0xE
0x5ac0b8  callvirt instance object [System.Runtime.Serialization]System.Runtime.Serialization.XmlObjectSerializer::ReadObject(class [System.Xml]System.Xml.XmlReader)
0x5ac0bd  isinst   TenantStoreDiskCacheEntry
0x5ac0c2  stloc.s  0xC
0x5ac0c4  leave.s  loc_5AC0D2
0x5ac0c6  ldloc.s  0xE
0x5ac0c8  brfalse.s loc_5AC0D1
0x5ac0ca  ldloc.s  0xE
0x5ac0cc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5ac0d1  endfinally
0x5ac0d2  ldloc.s  0xC
0x5ac0d4  callvirt instance void TenantStoreDiskCacheEntry::PostDeserialize()
0x5ac0d9  ldc.i4   0x13C7785
0x5ac0de  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x5ac0e3  ldc.i4.s 0x32
0x5ac0e5  ldstr    aGetdatabasesho_2// "GetDatabasesHoldingTenantStoresOnDisk: "...
0x5ac0ea  ldc.i4.2
0x5ac0eb  newarr   [mscorlib]System.Object
0x5ac0f0  stloc.s  0x1F
0x5ac0f2  ldloc.s  0x1F
0x5ac0f4  ldc.i4.0
0x5ac0f5  ldloc.s  0xD
0x5ac0f7  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x5ac0fc  box      [mscorlib]System.Int64
0x5ac101  stelem.ref
0x5ac102  ldloc.s  0x1F
0x5ac104  ldc.i4.1
0x5ac105  ldloc.s  0xB
0x5ac107  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x5ac10c  stelem.ref
0x5ac10d  ldloc.s  0x1F
0x5ac10f  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x5ac114  leave.s  loc_5AC122
0x5ac116  ldloc.s  0xD
0x5ac118  brfalse.s loc_5AC121
0x5ac11a  ldloc.s  0xD
0x5ac11c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5ac121  endfinally
0x5ac122  leave.s  loc_5AC15C
0x5ac124  stloc.s  0xF
0x5ac126  ldc.i4   0x13C7786
0x5ac12b  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x5ac130  ldc.i4.s 0xA
0x5ac132  ldstr    aGetdatabasesho_3// "GetDatabasesHoldingTenantStoresOnDisk: "...
0x5ac137  ldc.i4.2
0x5ac138  newarr   [mscorlib]System.Object
0x5ac13d  stloc.s  0x20
0x5ac13f  ldloc.s  0x20
0x5ac141  ldc.i4.0
0x5ac142  ldloc.s  0xB
0x5ac144  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x5ac149  stelem.ref
0x5ac14a  ldloc.s  0x20
0x5ac14c  ldc.i4.1
0x5ac14d  ldloc.s  0xF
0x5ac14f  stelem.ref
0x5ac150  ldloc.s  0x20
0x5ac152  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x5ac157  ldnull
0x5ac158  stloc.s  0xC
0x5ac15a  leave.s  loc_5AC15C
0x5ac15c  ldloc.s  0xC
0x5ac15e  brfalse  loc_5AC338
0x5ac163  ldloc.s  0xC
0x5ac165  callvirt instance valuetype [mscorlib]System.DateTime TenantStoreDiskCacheEntry::get_TimeStamp()
0x5ac16a  ldloc.s  7
0x5ac16c  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x5ac171  brfalse  loc_5AC2E2
0x5ac176  ldsfld   class TenantStoreDiskCache Microsoft.SharePoint.SPTenantStore::cacheTenantStoreOnDisk
0x5ac17b  brtrue.s loc_5AC1AE
0x5ac17d  ldc.i4.0
0x5ac17e  stloc.s  0x10
0x5ac180  ldsfld   object Microsoft.SharePoint.SPTenantStore::lockTenantStoreCache
0x5ac185  dup
0x5ac186  stloc.s  0x21
0x5ac188  ldloca.s 0x10
0x5ac18a  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x5ac18f  ldsfld   class TenantStoreDiskCache Microsoft.SharePoint.SPTenantStore::cacheTenantStoreOnDisk
0x5ac194  brtrue.s loc_5AC1A0
0x5ac196  newobj   instance void TenantStoreDiskCache::.ctor()
0x5ac19b  stsfld   class TenantStoreDiskCache Microsoft.SharePoint.SPTenantStore::cacheTenantStoreOnDisk
0x5ac1a0  leave.s  loc_5AC1AE
0x5ac1a2  ldloc.s  0x10
0x5ac1a4  brfalse.s loc_5AC1AD
0x5ac1a6  ldloc.s  0x21
0x5ac1a8  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x5ac1ad  endfinally
0x5ac1ae  ldsfld   class TenantStoreDiskCache Microsoft.SharePoint.SPTenantStore::cacheTenantStoreOnDisk
0x5ac1b3  ldloc.s  0xC
0x5ac1b5  callvirt instance valuetype [mscorlib]System.Guid TenantStoreDiskCacheEntry::get_CompanyId()
0x5ac1ba  callvirt instance bool class Microsoft.SharePoint.Administration.SPFileSystemSubCache`2<valuetype [mscorlib]System.Guid, class TenantStoreDiskCacheEntry>::RemoveFromFileSystemSubCache(var<u1>)
0x5ac1bf  stloc.s  0x11
0x5ac1c1  ldloc.s  0xC
0x5ac1c3  callvirt instance valuetype [mscorlib]System.Guid TenantStoreDiskCacheEntry::get_CompanyId()
0x5ac1c8  ldloc.s  0xC
0x5ac1ca  callvirt instance valuetype [mscorlib]System.Guid TenantStoreDiskCacheEntry::get_SiteSubscriptionId()
0x5ac1cf  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5ac1d4  brfalse.s loc_5AC1F0
0x5ac1d6  ldloc.s  0x11
0x5ac1d8  brfalse.s loc_5AC1ED
0x5ac1da  ldsfld   class TenantStoreDiskCache Microsoft.SharePoint.SPTenantStore::cacheTenantStoreOnDisk
0x5ac1df  ldloc.s  0xC
0x5ac1e1  callvirt instance valuetype [mscorlib]System.Guid TenantStoreDiskCacheEntry::get_SiteSubscriptionId()
0x5ac1e6  callvirt instance bool class Microsoft.SharePoint.Administration.SPFileSystemSubCache`2<valuetype [mscorlib]System.Guid, class TenantStoreDiskCacheEntry>::RemoveFromFileSystemSubCache(var<u1>)
0x5ac1eb  br.s     loc_5AC1EE
0x5ac1ed  ldc.i4.0
0x5ac1ee  stloc.s  0x11
0x5ac1f0  ldloc.s  0x11
0x5ac1f2  brfalse.s loc_5AC207
0x5ac1f4  ldsfld   class TenantStoreDiskCache Microsoft.SharePoint.SPTenantStore::cacheTenantStoreOnDisk
0x5ac1f9  ldloc.s  0xC
0x5ac1fb  callvirt instance valuetype [mscorlib]System.Guid TenantStoreDiskCacheEntry::get_SiteId()
0x5ac200  callvirt instance bool class Microsoft.SharePoint.Administration.SPFileSystemSubCache`2<valuetype [mscorlib]System.Guid, class TenantStoreDiskCacheEntry>::RemoveFromFileSystemSubCache(var<u1>)
0x5ac205  br.s     loc_5AC208
0x5ac207  ldc.i4.0
0x5ac208  stloc.s  0x11
0x5ac20a  ldloc.s  0x11
0x5ac20c  brfalse.s loc_5AC271
0x5ac20e  ldc.i4   0x150A391
0x5ac213  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x5ac218  ldc.i4.s 0x32
0x5ac21a  ldstr    aGetdatabasesho_4// "GetDatabasesHoldingTenantStoresOnDisk: "...
0x5ac21f  ldc.i4.4
0x5ac220  newarr   [mscorlib]System.Object
0x5ac225  stloc.s  0x22
0x5ac227  ldloc.s  0x22
0x5ac229  ldc.i4.0
0x5ac22a  ldloc.s  0xC
0x5ac22c  callvirt instance valuetype [mscorlib]System.Guid TenantStoreDiskCacheEntry::get_CompanyId()
0x5ac231  box      [mscorlib]System.Guid
0x5ac236  stelem.ref
0x5ac237  ldloc.s  0x22
0x5ac239  ldc.i4.1
0x5ac23a  ldloc.s  0xC
0x5ac23c  callvirt instance valuetype [mscorlib]System.Guid TenantStoreDiskCacheEntry::get_SiteSubscriptionId()
0x5ac241  box      [mscorlib]System.Guid
0x5ac246  stelem.ref
0x5ac247  ldloc.s  0x22
0x5ac249  ldc.i4.2
0x5ac24a  ldloc.s  0xC
0x5ac24c  callvirt instance valuetype [mscorlib]System.Guid TenantStoreDiskCacheEntry::get_SiteId()
0x5ac251  box      [mscorlib]System.Guid
0x5ac256  stelem.ref
0x5ac257  ldloc.s  0x22
0x5ac259  ldc.i4.3
0x5ac25a  ldloc.s  0xC
0x5ac25c  callvirt instance valuetype [mscorlib]System.Guid TenantStoreDiskCacheEntry::get_DatabaseId()
0x5ac261  box      [mscorlib]System.Guid
0x5ac266  stelem.ref
0x5ac267  ldloc.s  0x22
0x5ac269  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x5ac26e  ldnull
0x5ac26f  stloc.s  0xC
0x5ac271  leave.s  loc_5AC2E2
0x5ac273  stloc.s  0x12
0x5ac275  ldc.i4   0x150A392
0x5ac27a  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x5ac27f  ldc.i4.s 0x14
0x5ac281  ldstr    aGetdatabasesho_5// "GetDatabasesHoldingTenantStoresOnDisk: "...
0x5ac286  ldc.i4.5
0x5ac287  newarr   [mscorlib]System.Object
0x5ac28c  stloc.s  0x23
0x5ac28e  ldloc.s  0x23
0x5ac290  ldc.i4.0
0x5ac291  ldloc.s  0xC
0x5ac293  callvirt instance valuetype [mscorlib]System.Guid TenantStoreDiskCacheEntry::get_CompanyId()
0x5ac298  box      [mscorlib]System.Guid
0x5ac29d  stelem.ref
0x5ac29e  ldloc.s  0x23
  ... truncated ...
```
