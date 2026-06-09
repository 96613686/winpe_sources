# Microsoft.SharePoint.Administration.SPPersistedObjectCollectionCache::Get_1

- ea: `0x2d2de0`
- end: `0x2d33b3`
- name: `Microsoft.SharePoint.Administration.SPPersistedObjectCollectionCache::Get_1`
- size: `1491`
- prototype: ``
- caller_count: `4`
- callee_count: `27`
- tags: `registry_config, broker_com_uri`

## callers

- `0x250c10`
- `0x2d2db0`
- `0x2d5320`
- `0x2d7330`

## callees

- `0x19b8b0`
- `0x1c8540`
- `0x1c87b0`
- `0x1c89b0`
- `0x23cbf0`
- `0x23cc00`
- `0x249550`
- `0x251ae0`
- `0x251b10`
- `0x251b40`
- `0x2d2b30`
- `0x2d2d70`
- `0x2d2de0`
- `0x2d33c0`
- `0x2d3650`
- `0x2d3760`
- `0x2d3950`
- `0x2d4020`
- `0x2d42b0`
- `0x2d44c0`
- `0x2d56d0`
- `0x2d56f0`
- `0x58a130`
- `0x93dab0`
- `0x93dae0`
- `0x957f10`
- `0x957f30`

## string_xrefs

- `0x2d2e1e`: `SPPersistedObjectCollectionCache.Get: object type={0}, parent=[{1}], memberType={2}`
- `0x2d2e68`: `SPPersistedObjectCollectionCache.Get: Parent object ConfigurationDatabase member is null. Stack Trace: {0}`
- `0x2d2e9f`: `SPPersistedObjectCollectionCache.Get: Attempting to fall back to SPConfigurationDatabase.Local.`
- `0x2d2ec6`: `SPPersistedObjectCollectionCache.Get: Exiting because configDb is still null.`
- `0x2d2f45`: `SPPersistedObjectCollectionCache.Get: memory cache hit. objectIDs count={0}`
- `0x2d2f79`: `Skipping collection cache because the value is dirty for {0}:{1}:{2}`
- `0x2d2ff9`: `SPPersistedObjectCollectionCache.Get: got collection cache result for {0} with parent {1} [{2}] and type {3} [{4}]. objectIDs count={5}, objectIDs is {6}.`
- `0x2d30d2`: `SPPersistedObjectCollectionCache.Get: look up file ({0}). objectIDs count={1}`
- `0x2d31aa`: `SPPersistedObjectCollectionCache.Get: Database query for {0} failed: Exception {1}`
- `0x2d3251`: `SPPersistedObjectCollectionCache.Get: got SQL result. objectIDs count={0}`
- `0x2d3293`: `SPPersistedObjectCollectionCache: Missed memory and file cache, falling back to SQL query. CollectionType={0}, ObjectType={1}, CollectionParentId={2}, Object Count={3}, Stack={4}`
- `0x2d3325`: `SPPersistedObjectCollectionCache.Get: cannot get result from SQL or file cache: Stack trace: {0}.`
- `0x2d3357`: `SPPersistedObjectCollectionCache.Get: cannot get result from cache: Stack trace: {0}.`
- `0x2d3395`: `SPPersistedObjectCollectionCache.Get: Hit exception while retrieving collection: {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x2d2de0  ldnull
0x2d2de1  stloc.0
0x2d2de2  ldnull
0x2d2de3  stloc.1
0x2d2de4  ldarg.1
0x2d2de5  stloc.s  0x10
0x2d2de7  ldloc.s  0x10
0x2d2de9  switch   loc_2D2DF8, loc_2D2E06
0x2d2df6  br.s     loc_2D2E12
0x2d2df8  ldsfld   class Microsoft.SharePoint.Administration.SPVolatileCache`2<class [mscorlib]System.Type, class Microsoft.SharePoint.Administration.SPVolatileCache`2<valuetype [mscorlib]System.Guid, class DirtiableListOfGuids>> Microsoft.SharePoint.Administration.SPPersistedObjectCollectionCache::s_ChildCollectionCache
0x2d2dfd  ldarg.2
0x2d2dfe  callvirt instance var<u1> class Microsoft.SharePoint.Administration.SPCache`2<class [mscorlib]System.Type, class Microsoft.SharePoint.Administration.SPVolatileCache`2<valuetype [mscorlib]System.Guid, class DirtiableListOfGuids>>::get_Item(void)
0x2d2e03  stloc.0
0x2d2e04  br.s     loc_2D2E12
0x2d2e06  ldsfld   class Microsoft.SharePoint.Administration.SPVolatileCache`2<class [mscorlib]System.Type, class Microsoft.SharePoint.Administration.SPVolatileCache`2<valuetype [mscorlib]System.Guid, class DirtiableListOfGuids>> Microsoft.SharePoint.Administration.SPPersistedObjectCollectionCache::s_DependencyCollectionCache
0x2d2e0b  ldarg.2
0x2d2e0c  callvirt instance var<u1> class Microsoft.SharePoint.Administration.SPCache`2<class [mscorlib]System.Type, class Microsoft.SharePoint.Administration.SPVolatileCache`2<valuetype [mscorlib]System.Guid, class DirtiableListOfGuids>>::get_Item(void)
0x2d2e11  stloc.0
0x2d2e12  ldc.i4   0x660807
0x2d2e17  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ConfigCache()
0x2d2e1c  ldc.i4.s 0x64
0x2d2e1e  ldstr    aSppersistedobj_5// "SPPersistedObjectCollectionCache.Get: o"...
0x2d2e23  ldc.i4.3
0x2d2e24  newarr   [mscorlib]System.Object
0x2d2e29  stloc.s  0x11
0x2d2e2b  ldloc.s  0x11
0x2d2e2d  ldc.i4.0
0x2d2e2e  ldarg.2
0x2d2e2f  stelem.ref
0x2d2e30  ldloc.s  0x11
0x2d2e32  ldc.i4.1
0x2d2e33  ldarg.0
0x2d2e34  stelem.ref
0x2d2e35  ldloc.s  0x11
0x2d2e37  ldc.i4.2
0x2d2e38  ldarg.2
0x2d2e39  callvirt instance string [mscorlib]System.Type::get_FullName()
0x2d2e3e  stelem.ref
0x2d2e3f  ldloc.s  0x11
0x2d2e41  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2d2e46  ldc.i4.0
0x2d2e47  stloc.2
0x2d2e48  ldc.i4.0
0x2d2e49  stloc.3
0x2d2e4a  ldarg.0
0x2d2e4b  callvirt instance class Microsoft.SharePoint.Administration.SPConfigurationDatabase Microsoft.SharePoint.Administration.SPPersistedObject::get_ConfigurationDatabase()
0x2d2e50  stloc.s  4
0x2d2e52  ldloc.s  4
0x2d2e54  ldnull
0x2d2e55  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x2d2e5a  brfalse.s loc_2D2ED5
0x2d2e5c  ldc.i4   0x111D582
0x2d2e61  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ConfigCache()
0x2d2e66  ldc.i4.s 0x14
0x2d2e68  ldstr    aSppersistedobj_6// "SPPersistedObjectCollectionCache.Get: P"...
0x2d2e6d  ldc.i4.1
0x2d2e6e  newarr   [mscorlib]System.Object
0x2d2e73  stloc.s  0x12
0x2d2e75  ldloc.s  0x12
0x2d2e77  ldc.i4.0
0x2d2e78  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ConfigCache()
0x2d2e7d  ldc.i4.s 0x32
0x2d2e7f  call     string Microsoft.SharePoint.Utilities.SPUtility::StackTraceString(class Microsoft.SharePoint.Diagnostics.ULSCat traceCategory, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level)
0x2d2e84  stelem.ref
0x2d2e85  ldloc.s  0x12
0x2d2e87  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2d2e8c  ldsfld   bool Microsoft.SharePoint.Administration.SPFarm::IsBeingCreated
0x2d2e91  brtrue.s loc_2D2EB0
0x2d2e93  ldc.i4   0x111D583
0x2d2e98  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ConfigCache()
0x2d2e9d  ldc.i4.s 0x14
0x2d2e9f  ldstr    aSppersistedobj_7// "SPPersistedObjectCollectionCache.Get: A"...
0x2d2ea4  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2d2ea9  call     class Microsoft.SharePoint.Administration.SPConfigurationDatabase Microsoft.SharePoint.Administration.SPConfigurationDatabase::get_Local()
0x2d2eae  stloc.s  4
0x2d2eb0  ldloc.s  4
0x2d2eb2  ldnull
0x2d2eb3  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x2d2eb8  brfalse.s loc_2D2ED5
0x2d2eba  ldc.i4   0x111D584
0x2d2ebf  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ConfigCache()
0x2d2ec4  ldc.i4.s 0xF
0x2d2ec6  ldstr    aSppersistedobj_8// "SPPersistedObjectCollectionCache.Get: E"...
0x2d2ecb  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2d2ed0  br       loc_2D3304
0x2d2ed5  ldsfld   class Microsoft.SharePoint.Administration.SPVolatileCache`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Type> Microsoft.SharePoint.Utilities.SPTypeSerializer::s_TypeGuidMap
0x2d2eda  ldarg.2
0x2d2edb  callvirt instance valuetype [mscorlib]System.Guid [mscorlib]System.Type::get_GUID()
0x2d2ee0  callvirt instance bool class Microsoft.SharePoint.Administration.SPVolatileCache`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Type>::ContainsKey(var<u1>)
0x2d2ee5  brtrue.s loc_2D2EF8
0x2d2ee7  ldsfld   class Microsoft.SharePoint.Administration.SPVolatileCache`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Type> Microsoft.SharePoint.Utilities.SPTypeSerializer::s_TypeGuidMap
0x2d2eec  ldarg.2
0x2d2eed  callvirt instance valuetype [mscorlib]System.Guid [mscorlib]System.Type::get_GUID()
0x2d2ef2  ldarg.2
0x2d2ef3  callvirt instance void class Microsoft.SharePoint.Administration.SPCache`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Type>::set_Item(var<u1>, !!T0)
0x2d2ef8  ldarg.3
0x2d2ef9  brfalse  loc_2D2FAB
0x2d2efe  ldloc.0
0x2d2eff  brfalse  loc_2D2FAB
0x2d2f04  ldsfld   class Microsoft.SharePoint.Administration.SPCachePerformanceProvider Microsoft.SharePoint.Administration.SPPersistedObjectCollectionCache::s_CollectionCacheProvider
0x2d2f09  callvirt instance void Microsoft.SharePoint.Administration.SPCachePerformanceProvider::IncrementMemoryCacheCounter()
0x2d2f0e  ldloc.0
0x2d2f0f  ldarg.0
0x2d2f10  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x2d2f15  callvirt instance var<u1> class Microsoft.SharePoint.Administration.SPCache`2<valuetype [mscorlib]System.Guid, class DirtiableListOfGuids>::get_Item(void)
0x2d2f1a  stloc.s  5
0x2d2f1c  ldloc.s  5
0x2d2f1e  brfalse  loc_2D2FAB
0x2d2f23  ldloc.s  5
0x2d2f25  callvirt instance bool DirtiableListOfGuids::get_IsDirty()
0x2d2f2a  stloc.2
0x2d2f2b  ldloc.s  5
0x2d2f2d  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> DirtiableListOfGuids::get_Ids()
0x2d2f32  stloc.1
0x2d2f33  ldloc.1
0x2d2f34  brfalse.s loc_2D2FAB
0x2d2f36  ldloc.2
0x2d2f37  brtrue.s loc_2D2F6D
0x2d2f39  ldc.i4   0x660808
0x2d2f3e  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ConfigCache()
0x2d2f43  ldc.i4.s 0x64
0x2d2f45  ldstr    aSppersistedobj_9// "SPPersistedObjectCollectionCache.Get: m"...
0x2d2f4a  ldc.i4.1
0x2d2f4b  newarr   [mscorlib]System.Object
0x2d2f50  stloc.s  0x13
0x2d2f52  ldloc.s  0x13
0x2d2f54  ldc.i4.0
0x2d2f55  ldloc.1
0x2d2f56  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x2d2f5b  box      [mscorlib]System.Int32
0x2d2f60  stelem.ref
0x2d2f61  ldloc.s  0x13
0x2d2f63  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2d2f68  ldc.i4.0
0x2d2f69  starg.s  6
0x2d2f6b  br.s     loc_2D2FAB
0x2d2f6d  ldc.i4   0x1023259
0x2d2f72  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ConfigCache()
0x2d2f77  ldc.i4.s 0x32
0x2d2f79  ldstr    aSkippingCollec// "Skipping collection cache because the v"...
0x2d2f7e  ldc.i4.3
0x2d2f7f  newarr   [mscorlib]System.Object
0x2d2f84  stloc.s  0x14
0x2d2f86  ldloc.s  0x14
0x2d2f88  ldc.i4.0
0x2d2f89  ldarg.1
0x2d2f8a  box      Microsoft.SharePoint.Administration.SPPersistedObjectCollectionType
0x2d2f8f  stelem.ref
0x2d2f90  ldloc.s  0x14
0x2d2f92  ldc.i4.1
0x2d2f93  ldarg.2
0x2d2f94  stelem.ref
0x2d2f95  ldloc.s  0x14
0x2d2f97  ldc.i4.2
0x2d2f98  ldarg.0
0x2d2f99  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x2d2f9e  box      [mscorlib]System.Guid
0x2d2fa3  stelem.ref
0x2d2fa4  ldloc.s  0x14
0x2d2fa6  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2d2fab  ldc.i4.0
0x2d2fac  stloc.s  6
0x2d2fae  ldc.i4.0
0x2d2faf  stloc.s  7
0x2d2fb1  ldarg.s  4
0x2d2fb3  brfalse  loc_2D3142
0x2d2fb8  ldloc.1
0x2d2fb9  brfalse.s loc_2D2FC1
0x2d2fbb  ldloc.2
0x2d2fbc  brfalse  loc_2D3142
0x2d2fc1  call     bool Microsoft.SharePoint.Administration.SPPersistedObjectCollectionCache::get_FileCacheEnabled()
0x2d2fc6  brfalse  loc_2D3140
0x2d2fcb  call     bool Microsoft.SharePoint.Administration.SPConfigurationDatabaseDebuggingSettings::get_UseDerivedCollectionCacheRefresh()
0x2d2fd0  brfalse  loc_2D3078
0x2d2fd5  ldc.i4.1
0x2d2fd6  stloc.s  6
0x2d2fd8  ldloc.s  4
0x2d2fda  ldarg.1
0x2d2fdb  ldarg.0
0x2d2fdc  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x2d2fe1  ldarg.2
0x2d2fe2  callvirt instance valuetype [mscorlib]System.Guid [mscorlib]System.Type::get_GUID()
0x2d2fe7  call     class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Administration.SPPersistedObjectCollectionCache::GetFromContainerCache(class Microsoft.SharePoint.Administration.SPConfigurationDatabase configDb, valuetype Microsoft.SharePoint.Administration.SPPersistedObjectCollectionType collectionType, valuetype [mscorlib]System.Guid parentId, valuetype [mscorlib]System.Guid classId)
0x2d2fec  stloc.1
0x2d2fed  ldc.i4   0x111D585
0x2d2ff2  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ConfigCache()
0x2d2ff7  ldc.i4.s 0x64
0x2d2ff9  ldstr    aSppersistedobj_10// "SPPersistedObjectCollectionCache.Get: g"...
0x2d2ffe  ldc.i4.7
0x2d2fff  newarr   [mscorlib]System.Object
0x2d3004  stloc.s  0x15
0x2d3006  ldloc.s  0x15
0x2d3008  ldc.i4.0
0x2d3009  ldarg.1
0x2d300a  box      Microsoft.SharePoint.Administration.SPPersistedObjectCollectionType
0x2d300f  stelem.ref
0x2d3010  ldloc.s  0x15
0x2d3012  ldc.i4.1
0x2d3013  ldarg.0
0x2d3014  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x2d3019  box      [mscorlib]System.Guid
0x2d301e  stelem.ref
0x2d301f  ldloc.s  0x15
0x2d3021  ldc.i4.2
0x2d3022  ldarg.0
0x2d3023  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2d3028  callvirt instance string [mscorlib]System.Type::get_FullName()
0x2d302d  stelem.ref
0x2d302e  ldloc.s  0x15
0x2d3030  ldc.i4.3
0x2d3031  ldarg.2
0x2d3032  callvirt instance valuetype [mscorlib]System.Guid [mscorlib]System.Type::get_GUID()
0x2d3037  box      [mscorlib]System.Guid
0x2d303c  stelem.ref
0x2d303d  ldloc.s  0x15
0x2d303f  ldc.i4.4
0x2d3040  ldarg.2
0x2d3041  callvirt instance string [mscorlib]System.Type::get_FullName()
0x2d3046  stelem.ref
0x2d3047  ldloc.s  0x15
0x2d3049  ldc.i4.5
0x2d304a  ldloc.1
0x2d304b  brfalse.s loc_2D3055
0x2d304d  ldloc.1
0x2d304e  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x2d3053  br.s     loc_2D3056
0x2d3055  ldc.i4.0
0x2d3056  box      [mscorlib]System.Int32
0x2d305b  stelem.ref
0x2d305c  ldloc.s  0x15
0x2d305e  ldc.i4.6
0x2d305f  ldloc.1
0x2d3060  brfalse.s loc_2D3069
0x2d3062  ldstr    aNotNull// "not null"
0x2d3067  br.s     loc_2D306E
0x2d3069  ldstr    aNull_2// "null"
0x2d306e  stelem.ref
0x2d306f  ldloc.s  0x15
0x2d3071  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2d3076  br.s     loc_2D307A
0x2d3078  ldnull
0x2d3079  stloc.1
0x2d307a  ldloc.2
0x2d307b  brtrue   loc_2D3142
0x2d3080  call     bool Microsoft.SharePoint.Administration.SPConfigurationDatabaseDebuggingSettings::get_TrustDerivedCollectionCacheRefresh()
0x2d3085  brtrue   loc_2D3142
0x2d308a  ldarg.1
0x2d308b  ldarg.0
0x2d308c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x2d3091  ldarg.2
0x2d3092  call     class [mscorlib]System.IO.FileInfo Microsoft.SharePoint.Administration.SPPersistedObjectCollectionCache::GetFileInfo(valuetype Microsoft.SharePoint.Administration.SPPersistedObjectCollectionType collectionType, valuetype [mscorlib]System.Guid collectionParentId, class [mscorlib]System.Type objectType)
0x2d3097  stloc.s  8
0x2d3099  ldloc.s  8
0x2d309b  brfalse  loc_2D3142
0x2d30a0  ldloc.s  8
0x2d30a2  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0x2d30a7  brfalse  loc_2D3142
0x2d30ac  ldsfld   class Microsoft.SharePoint.Administration.SPCachePerformanceProvider Microsoft.SharePoint.Administration.SPPersistedObjectCollectionCache::s_CollectionCacheProvider
0x2d30b1  callvirt instance void Microsoft.SharePoint.Administration.SPCachePerformanceProvider::IncrementFileCacheCounter()
0x2d30b6  ldloc.s  8
0x2d30b8  call     class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Administration.SPPersistedObjectCollectionCache::FetchObjectCollectionFromFile(class [mscorlib]System.IO.FileInfo collectionCacheFileInfo)
0x2d30bd  stloc.s  9
0x2d30bf  ldloc.s  9
0x2d30c1  brfalse.s loc_2D313C
0x2d30c3  ldc.i4.1
0x2d30c4  stloc.s  7
0x2d30c6  ldc.i4   0x660809
0x2d30cb  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ConfigCache()
0x2d30d0  ldc.i4.s 0x64
0x2d30d2  ldstr    aSppersistedobj_11// "SPPersistedObjectCollectionCache.Get: l"...
0x2d30d7  ldc.i4.2
0x2d30d8  newarr   [mscorlib]System.Object
0x2d30dd  stloc.s  0x16
0x2d30df  ldloc.s  0x16
0x2d30e1  ldc.i4.0
0x2d30e2  ldarg.1
0x2d30e3  ldarg.0
0x2d30e4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x2d30e9  ldarg.2
0x2d30ea  call     class [mscorlib]System.IO.FileInfo Microsoft.SharePoint.Administration.SPPersistedObjectCollectionCache::GetFileInfo(valuetype Microsoft.SharePoint.Administration.SPPersistedObjectCollectionType collectionType, valuetype [mscorlib]System.Guid collectionParentId, class [mscorlib]System.Type objectType)
0x2d30ef  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x2d30f4  stelem.ref
0x2d30f5  ldloc.s  0x16
0x2d30f7  ldc.i4.1
0x2d30f8  ldloc.s  9
0x2d30fa  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x2d30ff  box      [mscorlib]System.Int32
0x2d3104  stelem.ref
0x2d3105  ldloc.s  0x16
0x2d3107  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2d310c  ldloc.1
0x2d310d  brfalse.s loc_2D3137
0x2d310f  call     bool Microsoft.SharePoint.Administration.SPConfigurationDatabaseDebuggingSettings::get_UseDerivedCollectionCacheRefresh()
0x2d3114  brfalse.s loc_2D3137
0x2d3116  ldarg.0
0x2d3117  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x2d311c  ldarg.0
0x2d311d  callvirt instance string [mscorlib]System.Object::ToString()
0x2d3122  ldarg.1
0x2d3123  ldarg.2
  ... truncated ...
```
