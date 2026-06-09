# Microsoft.SharePoint.Administration.SPConfigurationDatabase::RefreshCache_1

- ea: `0x24ad40`
- end: `0x24bb89`
- name: `Microsoft.SharePoint.Administration.SPConfigurationDatabase::RefreshCache_1`
- size: `3657`
- prototype: ``
- caller_count: `5`
- callee_count: `55`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x24ac40`
- `0x24ace0`
- `0x24ad10`
- `0x259cc0`
- `0x2d7f30`

## callees

- `0x19b8b0`
- `0x1c8540`
- `0x1c86a0`
- `0x1c8740`
- `0x1c89e0`
- `0x232090`
- `0x23cc40`
- `0x23cc50`
- `0x242050`
- `0x249cc0`
- `0x249cd0`
- `0x249ce0`
- `0x249d00`
- `0x249d30`
- `0x249f70`
- `0x24a090`
- `0x24a840`
- `0x24ad40`
- `0x24bb90`
- `0x24c980`
- `0x24c9c0`
- `0x24ccc0`
- `0x24cde0`
- `0x2500e0`
- `0x250820`
- `0x251ae0`
- `0x251b10`
- `0x251bd0`
- `0x251d80`
- `0x251e70`
- `0x253480`
- `0x2b4c40`
- `0x2b4d30`
- `0x2b4de0`
- `0x2b5080`
- `0x2d5830`
- `0x2d5840`
- `0x2d5850`
- `0x2d5970`
- `0x2d5990`
- `0x2d5f20`
- `0x2d6120`
- `0x2d68d0`
- `0x2d6d90`
- `0x2ed970`
- `0x2eda90`
- `0x37ecc0`
- `0x7a0fb0`
- `0x7c6850`
- `0x7c6860`

## string_xrefs

- `0x24b543`: `@NewestCachedVersion`
- `0x24ad73`: `Config caches disabled.  Skipping cache refresh.`
- `0x24adab`: `Skipping recursive call to SPConfigurationDatabase.RefreshCache.`
- `0x24ae4b`: `RefreshCache: Refreshing the cache, refreshCacheFlags=[{0}] currentVersionOverride=[{1}],`
- `0x24af17`: `Lock acquired (if needed), refreshing config file system cache. Stack trace: {0}`
- `0x24af65`: `Corrupt cache.ini detected.  Dumping the config cache.`
- `0x24af82`: `Corrupt cache.ini detected.  Dumping the config cache.`
- `0x24afde`: `No valid derived collection cache is present. Performing full collection cache rebuild. {0}`
- `0x24b094`: `The configuration cache on the local machine is newer than the object store in the database.  This may occur when the configuration database has been restored to the previous version.  To resolve this, the configuration filesystem cache will be flushed and rebuilt.`
- `0x24b0d5`: `RefreshCache - Successful refresh: Early exit since there were no changes since cache version [{0}].`
- `0x24b1c3`: `Object Changed During Refresh`
- `0x24b651`: `Object Changed During Refresh`
- `0x24b530`: `\n                                                        SELECT\n                                                            Objects.Id AS DependantId, Dependencies.ObjectId\n                                                        FROM\n                                                            Objects\n                                                        LEFT OUTER JOIN \n                                                            Dependencies\n                                      `
- `0x24b7ce`: `SPConfigurationDatabase:RefreshCache: Failed update of the persisted class dictionary. {0}`
- `0x24b847`: `SPConfigurationDatabase:RefreshCache: Failed updating the persisted derived collection cache. {0}`
- `0x24b8b4`: `RefreshCache - Successful refresh: Old cache version [{0}], new cache version [{1}], changes fetched since [{2}]`
- `0x24b949`: `RefreshCache - Successful refresh: No changes since cache version [{0}], but changes since [{1}] were fetched by request.`
- `0x24b9c4`: `RefreshCache - Number of objects updated {0}, dependent objects refreshed {1}`
- `0x24ba18`: `RefreshCache - dependent object [{0}]`
- `0x24ba6e`: `RefreshCache - Successful refresh: No changes since cache version [{0}], though we did not exit early.`
- `0x24bad1`: `IOException in RefreshCache. Try # {0}. Retrying. Exception message :{1}`
- `0x24bb17`: `Exception in RefreshCache. Exception message :{0}`

## pseudocode

```c

```

## disassembly

```asm
0x24ad40  ldarg.0
0x24ad41  call     instance class Microsoft.SharePoint.Administration.SPLoggedVolatileCache`2<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Administration.SPPersistedObject> Microsoft.SharePoint.Administration.SPConfigurationDatabase::get_ObjectCache()
0x24ad46  ldfld    bool class Microsoft.SharePoint.Administration.SPCache`2<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Administration.SPPersistedObject>::Enabled
0x24ad4b  brtrue.s loc_24AD93
0x24ad4d  ldarg.0
0x24ad4e  call     instance class Microsoft.SharePoint.Administration.SPVolatileCache`2<valuetype QualifiedObjectName, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Administration.SPConfigurationDatabase::get_NameCache()
0x24ad53  ldfld    bool class Microsoft.SharePoint.Administration.SPCache`2<valuetype QualifiedObjectName, valuetype [mscorlib]System.Guid>::Enabled
0x24ad58  brtrue.s loc_24AD93
0x24ad5a  ldarg.0
0x24ad5b  call     instance class Microsoft.SharePoint.Administration.SPFileSystemCache Microsoft.SharePoint.Administration.SPConfigurationDatabase::get_FileCache()
0x24ad60  ldfld    bool class Microsoft.SharePoint.Administration.SPCache`2<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Administration.SPPersistedObject>::Enabled
0x24ad65  brtrue.s loc_24AD93
0x24ad67  ldc.i4   0x4166A1
0x24ad6c  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ConfigCache()
0x24ad71  ldc.i4.s 0x32
0x24ad73  ldstr    aConfigCachesDi// "Config caches disabled.  Skipping cache"...
0x24ad78  ldc.i4.1
0x24ad79  newarr   [mscorlib]System.Object
0x24ad7e  stloc.s  0x3D
0x24ad80  ldloc.s  0x3D
0x24ad82  ldc.i4.0
0x24ad83  ldarg.0
0x24ad84  call     instance string Microsoft.SharePoint.Administration.SPConfigurationDatabase::get_CachePath()
0x24ad89  stelem.ref
0x24ad8a  ldloc.s  0x3D
0x24ad8c  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x24ad91  ldc.i4.0
0x24ad92  ret
0x24ad93  ldsfld   string Microsoft.SharePoint.Administration.SPConfigurationDatabase::s_RecursionTestString
0x24ad98  call     object Microsoft.SharePoint.Utilities.SPThreadContext::Get(string key)
0x24ad9d  brfalse.s loc_24ADCB
0x24ad9f  ldc.i4   0x4166A2
0x24ada4  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ConfigCache()
0x24ada9  ldc.i4.s 0x32
0x24adab  ldstr    aSkippingRecurs// "Skipping recursive call to SPConfigurat"...
0x24adb0  ldc.i4.1
0x24adb1  newarr   [mscorlib]System.Object
0x24adb6  stloc.s  0x3D
0x24adb8  ldloc.s  0x3D
0x24adba  ldc.i4.0
0x24adbb  ldarg.0
0x24adbc  call     instance string Microsoft.SharePoint.Administration.SPConfigurationDatabase::get_CachePath()
0x24adc1  stelem.ref
0x24adc2  ldloc.s  0x3D
0x24adc4  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x24adc9  ldc.i4.0
0x24adca  ret
0x24adcb  ldarg.2
0x24adcc  box      RefreshCacheFlags
0x24add1  ldc.i4.2
0x24add2  box      RefreshCacheFlags
0x24add7  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x24addc  ldc.i4.0
0x24addd  ceq
0x24addf  stloc.0
0x24ade0  ldarg.2
0x24ade1  box      RefreshCacheFlags
0x24ade6  ldc.i4.4
0x24ade7  box      RefreshCacheFlags
0x24adec  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x24adf1  stloc.1
0x24adf2  ldarg.2
0x24adf3  box      RefreshCacheFlags
0x24adf8  ldc.i4.8
0x24adf9  box      RefreshCacheFlags
0x24adfe  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x24ae03  stloc.2
0x24ae04  ldarg.2
0x24ae05  box      RefreshCacheFlags
0x24ae0a  ldc.i4.1
0x24ae0b  box      RefreshCacheFlags
0x24ae10  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x24ae15  stloc.3
0x24ae16  ldloc.2
0x24ae17  brfalse.s loc_24AE29
0x24ae19  ldloc.3
0x24ae1a  brfalse.s loc_24AE29
0x24ae1c  call     bool Microsoft.SharePoint.Administration.SPConfigurationDatabaseDebuggingSettings::get_DeleteUnknownObjectFilesInCollectionCacheRefresh()
0x24ae21  brfalse.s loc_24AE29
0x24ae23  ldarg.2
0x24ae24  ldc.i4.s 0x10
0x24ae26  or
0x24ae27  starg.s  2
0x24ae29  ldc.i4.0
0x24ae2a  stloc.s  5
0x24ae2c  ldc.i4.0
0x24ae2d  stloc.s  6
0x24ae2f  ldc.i4.0
0x24ae30  stloc.s  7
0x24ae32  ldc.i4.0
0x24ae33  stloc.s  8
0x24ae35  ldc.i4   0x11498A0
0x24ae3a  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x24ae3f  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ConfigCache()
0x24ae44  ldc.i4.s 0x32
0x24ae46  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24ae4b  ldstr    aRefreshcacheRe// "RefreshCache: Refreshing the cache, ref"...
0x24ae50  ldc.i4.2
0x24ae51  newarr   [mscorlib]System.Object
0x24ae56  stloc.s  0x3D
0x24ae58  ldloc.s  0x3D
0x24ae5a  ldc.i4.0
0x24ae5b  ldarg.2
0x24ae5c  box      RefreshCacheFlags
0x24ae61  stelem.ref
0x24ae62  ldloc.s  0x3D
0x24ae64  ldc.i4.1
0x24ae65  ldarg.1
0x24ae66  box      [mscorlib]System.Int64
0x24ae6b  stelem.ref
0x24ae6c  ldloc.s  0x3D
0x24ae6e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x24ae73  ldc.i4.1
0x24ae74  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x24ae79  stloc.s  0x3E
0x24ae7b  ldloc.s  0x3E
0x24ae7d  ldc.i4.0
0x24ae7e  newobj   instance void Microsoft.SharePoint.Utilities.SPCPUCycleCounter::.ctor()
0x24ae83  stelem.ref
0x24ae84  ldloc.s  0x3E
0x24ae86  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCatBase category, valuetype Microsoft.SharePoint.Administration.TraceSeverity severity, string name, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x24ae8b  dup
0x24ae8c  stloc.s  4
0x24ae8e  stloc.s  0x3F
0x24ae90  ldsfld   string Microsoft.SharePoint.Administration.SPConfigurationDatabase::s_RecursionTestString
0x24ae95  newobj   instance void [mscorlib]System.Object::.ctor()
0x24ae9a  call     void Microsoft.SharePoint.Utilities.SPThreadContext::Set(string objectName, object objectValue)
0x24ae9f  ldarg.s  5
0x24aea1  ldsfld   int32 Microsoft.SharePoint.Administration.SPConstants::InvalidRowVersion
0x24aea6  conv.i8
0x24aea7  stind.i8
0x24aea8  ldarg.1
0x24aea9  ldc.i4.0
0x24aeaa  conv.i8
0x24aeab  bne.un.s loc_24AEB3
0x24aead  ldloc.2
0x24aeae  ldc.i4.0
0x24aeaf  ceq
0x24aeb1  br.s     loc_24AEB4
0x24aeb3  ldc.i4.0
0x24aeb4  stloc.s  9
0x24aeb6  br       loc_24BB49
0x24aebb  call     class Microsoft.SharePoint.Utilities.SecurityContext Microsoft.SharePoint.Utilities.SecurityContext::RevertToSelf()
0x24aec0  stloc.s  0xA
0x24aec2  ldarg.0
0x24aec3  call     instance string Microsoft.SharePoint.Administration.SPConfigurationDatabase::get_CachePath()
0x24aec8  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x24aecd  stloc.s  0xB
0x24aecf  ldloc.s  0xB
0x24aed1  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0x24aed6  brtrue.s loc_24AEE5
0x24aed8  ldarg.0
0x24aed9  call     instance string Microsoft.SharePoint.Administration.SPConfigurationDatabase::get_CachePath()
0x24aede  ldc.i4.1
0x24aedf  call     class [mscorlib]System.IO.DirectoryInfo Microsoft.SharePoint.Administration.SPServer::CreateDirectory(string path, valuetype Microsoft.SharePoint.Administration.SPAclGroupAccessLevel userGroupAccessLevel)
0x24aee4  pop
0x24aee5  ldarg.0
0x24aee6  call     instance string Microsoft.SharePoint.Administration.SPConfigurationDatabase::get_CacheIniPath()
0x24aeeb  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0x24aef0  stloc.s  0xC
0x24aef2  ldloc.s  0xC
0x24aef4  ldc.i4.4
0x24aef5  ldc.i4.3
0x24aef6  ldc.i4.0
0x24aef7  callvirt instance class [mscorlib]System.IO.FileStream [mscorlib]System.IO.FileInfo::Open(valuetype [mscorlib]System.IO.FileMode, valuetype [mscorlib]System.IO.FileAccess, valuetype [mscorlib]System.IO.FileShare)
0x24aefc  stloc.s  0xD
0x24aefe  ldc.i4.0
0x24aeff  conv.i8
0x24af00  stloc.s  0xE
0x24af02  ldloc.s  0xD
0x24af04  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0x24af09  stloc.s  0x10
0x24af0b  ldc.i4   0x111D550
0x24af10  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ConfigCache()
0x24af15  ldc.i4.s 0x32
0x24af17  ldstr    aLockAcquiredIf// "Lock acquired (if needed), refreshing c"...
0x24af1c  ldc.i4.1
0x24af1d  newarr   [mscorlib]System.Object
0x24af22  stloc.s  0x3D
0x24af24  ldloc.s  0x3D
0x24af26  ldc.i4.0
0x24af27  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ConfigCache()
0x24af2c  ldc.i4.s 0x32
0x24af2e  call     string Microsoft.SharePoint.Utilities.SPUtility::StackTraceString(class Microsoft.SharePoint.Diagnostics.ULSCat traceCategory, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level)
0x24af33  stelem.ref
0x24af34  ldloc.s  0x3D
0x24af36  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x24af3b  ldloc.s  0x10
0x24af3d  callvirt instance string [mscorlib]System.IO.TextReader::ReadLine()
0x24af42  stloc.s  0xF
0x24af44  ldloc.s  0xF
0x24af46  brfalse.s loc_24AF92
0x24af48  ldloc.s  0xF
0x24af4a  call     class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.NumberFormatInfo::get_InvariantInfo()
0x24af4f  call     int64 [mscorlib]System.Int64::Parse(string, class [mscorlib]System.IFormatProvider)
0x24af54  stloc.s  0xE
0x24af56  leave.s  loc_24AF92
0x24af58  pop
0x24af59  ldc.i4   0x4166A3
0x24af5e  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ConfigCache()
0x24af63  ldc.i4.s 0x14
0x24af65  ldstr    aCorruptCacheIn// "Corrupt cache.ini detected.  Dumping th"...
0x24af6a  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x24af6f  ldc.i4.0
0x24af70  conv.i8
0x24af71  stloc.s  0xE
0x24af73  leave.s  loc_24AF92
0x24af75  pop
0x24af76  ldc.i4   0x4166C0
0x24af7b  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ConfigCache()
0x24af80  ldc.i4.s 0x14
0x24af82  ldstr    aCorruptCacheIn// "Corrupt cache.ini detected.  Dumping th"...
0x24af87  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x24af8c  ldc.i4.0
0x24af8d  conv.i8
0x24af8e  stloc.s  0xE
0x24af90  leave.s  loc_24AF92
0x24af92  ldarg.0
0x24af93  ldloc.s  0xE
0x24af95  stfld    int64 Microsoft.SharePoint.Administration.SPConfigurationDatabase::m_LastCacheRefresh
0x24af9a  ldarg.1
0x24af9b  ldsfld   int32 Microsoft.SharePoint.Administration.SPConstants::InvalidRowVersion
0x24afa0  conv.i8
0x24afa1  beq.s    loc_24AFAD
0x24afa3  ldloc.s  0xE
0x24afa5  ldarg.1
0x24afa6  call     int64 [mscorlib]System.Math::Min(int64, int64)
0x24afab  stloc.s  0xE
0x24afad  ldnull
0x24afae  stloc.s  0x11
0x24afb0  call     bool Microsoft.SharePoint.Administration.SPConfigurationDatabaseDebuggingSettings::get_UseDerivedCollectionCacheRefresh()
0x24afb5  brfalse.s loc_24B014
0x24afb7  ldloc.3
0x24afb8  brtrue.s loc_24AFCB
0x24afba  ldloc.s  9
0x24afbc  brtrue.s loc_24AFCB
0x24afbe  ldloca.s 0x11
0x24afc0  call     bool Microsoft.SharePoint.Administration.SPPersistedObjectDerivedCollectionCache::ReadFromFile([out] class Microsoft.SharePoint.Administration.SPPersistedObjectDerivedCollectionCacheState& cacheState)
0x24afc5  brfalse.s loc_24AFCB
0x24afc7  ldloc.s  0x11
0x24afc9  brtrue.s loc_24B004
0x24afcb  ldloc.0
0x24afcc  brfalse.s loc_24B014
0x24afce  ldc.i4.0
0x24afcf  conv.i8
0x24afd0  stloc.s  0xE
0x24afd2  ldc.i4   0x11498A1
0x24afd7  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ConfigCache()
0x24afdc  ldc.i4.s 0xF
0x24afde  ldstr    aNoValidDerived// "No valid derived collection cache is pr"...
0x24afe3  ldc.i4.1
0x24afe4  newarr   [mscorlib]System.Object
0x24afe9  stloc.s  0x3D
0x24afeb  ldloc.s  0x3D
0x24afed  ldc.i4.0
0x24afee  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ConfigCache()
0x24aff3  ldc.i4.s 0xF
0x24aff5  call     string Microsoft.SharePoint.Utilities.SPUtility::StackTraceString(class Microsoft.SharePoint.Diagnostics.ULSCat traceCategory, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level)
0x24affa  stelem.ref
0x24affb  ldloc.s  0x3D
0x24affd  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x24b002  br.s     loc_24B014
0x24b004  ldloc.s  0xE
0x24b006  ldloc.s  0x11
0x24b008  callvirt instance int64 Microsoft.SharePoint.Administration.SPPersistedObjectDerivedCollectionCacheState::get_ConfigVersion()
0x24b00d  call     int64 [mscorlib]System.Math::Min(int64, int64)
0x24b012  stloc.s  0xE
0x24b014  ldarg.3
0x24b015  ldind.ref
0x24b016  brtrue.s loc_24B01F
0x24b018  ldarg.3
0x24b019  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPPersistedObject>::.ctor()
0x24b01e  stind.ref
0x24b01f  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x24b024  stloc.s  0x12
0x24b026  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x24b02b  stloc.s  0x13
0x24b02d  ldarg.s  4
0x24b02f  ldind.ref
0x24b030  brtrue.s loc_24B03A
0x24b032  ldarg.s  4
0x24b034  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x24b039  stind.ref
0x24b03a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x24b03f  stloc.s  0x14
0x24b041  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::.ctor()
0x24b046  stloc.s  0x15
0x24b048  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::.ctor()
0x24b04d  stloc.s  0x16
0x24b04f  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int64>>::.ctor()
0x24b054  stloc.s  0x17
0x24b056  ldnull
0x24b057  stloc.s  0x18
0x24b059  ldarg.0
0x24b05a  ldloc.s  0xE
0x24b05c  ldarg.2
0x24b05d  ldloca.s 0x19
0x24b05f  call     instance class [System.Data]System.Data.SqlClient.SqlDataReader Microsoft.SharePoint.Administration.SPConfigurationDatabase::FetchNewObjectsFromDatabase(int64 lastRefreshed, valuetype RefreshCacheFlags refreshCacheFlags, [out] class [System.Data]System.Data.SqlClient.SqlParameter& returnValue)
0x24b064  stloc.s  0x1A
0x24b066  ldloc.s  0x1A
  ... truncated ...
```
