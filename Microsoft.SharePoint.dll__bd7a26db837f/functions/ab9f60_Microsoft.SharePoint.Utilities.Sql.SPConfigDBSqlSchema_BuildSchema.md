# Microsoft.SharePoint.Utilities.Sql.SPConfigDBSqlSchema::BuildSchema

- ea: `0xab9f60`
- end: `0xabb7cc`
- name: `Microsoft.SharePoint.Utilities.Sql.SPConfigDBSqlSchema::BuildSchema`
- size: `6252`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0xab9ed0`

## callees

- `0x2bc030`
- `0x2bec60`
- `0x2beeb0`
- `0x2beec0`
- `0x2bf120`
- `0x2bf170`
- `0x2bf250`
- `0x2bf260`
- `0x2bf380`
- `0x95f3c0`
- `0x95fd70`
- `0x95fda0`
- `0x95fdb0`
- `0x95fde0`
- `0x95ffe0`
- `0x960030`
- `0x960270`
- `0x960760`
- `0x960800`
- `0xabb830`

## string_xrefs

- `0xabaeff`: `ProcessId`
- `0xababcc`: `LastUpdate`
- `0xabb7b8`: `SPDataAccess`
- `0xaba4da`: `DeleteTransactionId`
- `0xaba60b`: `DeleteTransactionId`
- `0xaba640`: `DeleteTransactionId`
- `0xaba7b9`: `DeleteTransactionId`
- `0xaba885`: `DeleteTransactionId`
- `0xaba914`: `DeleteTransactionId`
- `0xaba951`: `DeleteTransactionId`
- `0xaba9a7`: `DeleteTransactionId`
- `0xaba9c8`: `DeleteTransactionId`
- `0xaba9f7`: `DeleteTransactionId`
- `0xabaa33`: `DeleteTransactionId`
- `0xabaabf`: `DeleteTransactionId`
- `0xabaae9`: `DeleteTransactionId`
- `0xabab0a`: `DeleteTransactionId`
- `0xabac85`: `Deleted`
- `0xabaf1f`: `Created`
- `0xabb2dc`: `ServiceId`
- `0xabb3ab`: `ServiceId`
- `0xabb429`: `ServiceId`
- `0xabb5a2`: `ServiceId`
- `0xabb64f`: `ServiceId`
- `0xaba0b2`: `BaseClassId`
- `0xaba112`: `BaseClassId`
- `0xaba15a`: `BaseClassId`
- `0xaba17e`: `BaseClassId`
- `0xaba100`: `IX_Classes_BaseClassId`
- `0xaba147`: `TVF_Classes_BaseClassId`
- `0xaba2c0`: `ClassId`
- `0xaba393`: `ClassId`
- `0xaba3ee`: `ClassId`
- `0xaba414`: `ClassId`
- `0xaba455`: `ClassId`
- `0xaba380`: `IX_Objects_ClassId_ParentId_Name`
- `0xaba61b`: `IX_SiteMap_ApplicationId_Path`
- `0xaba6a6`: `IX_SiteMap_Path_HostHeaderIsSiteName`
- `0xaba828`: `NumSites`
- `0xaba8ae`: `HostAndPath`
- `0xaba91d`: `HostAndPath`
- `0xabac07`: `PK_LastUpdate`
- `0xabaf0f`: `ThreadId`
- `0xabaf2f`: `Updated`
- `0xabaf50`: `CommandLine`
- `0xabafab`: `CacheClusterConfig`
- `0xabb010`: `PK_CacheClusterConfig`
- `0xabb03c`: `IX_CacheClusterConfig_Type`
- `0xabb05f`: `TVF_CacheClusterConfig_EntryKey`
- `0xabb084`: `TVF_CacheClusterConfig_EntryType`
- `0xabb0a9`: `TVF_CacheClusterConfig_EntryKey_EntryType`
- `0xabb0dc`: `TVF_CacheClusterConfig_EntryKey_EntryType_Version`
- `0xabb11d`: `CacheClusterConfigSchemaVersion`
- `0xabb177`: `PK_CacheClusterConfigSchemaVersion`
- `0xabb19a`: `TVF_CacheClusterConfigSchemaVersion_Major`
- `0xabb398`: `IX_TimerRunningJobs_ServiceId_VirtualServerId_JobId_ServerId`
- `0xabb58f`: `IX_TimerJobHistory_ServiceId_Id`
- `0xabb63c`: `TimerScheduledJobs`
- `0xabb6aa`: `IX_TimerScheduledJobs_JobId_ServerId`
- `0xabb6d5`: `ExtensionMap`
- `0xabb754`: `PK_ExtensionMap`
- `0xabb78d`: `\n-- Grant DELETE on TimerLocks table\nIF EXISTS (SELECT TOP 1 1 FROM sys.tables WHERE object_id = object_id(N'[dbo].[TimerLocks]') AND TYPE_DESC=N'USER_TABLE')\nBEGIN\n    GRANT DELETE ON [dbo].[TimerLocks] TO [SPDataAccess]\nEND`
- `0xabb79a`: `\n-- Grant DELETE on TimerRunningJobs table\nIF EXISTS (SELECT TOP 1 1 FROM sys.tables WHERE object_id = object_id(N'[dbo].[TimerRunningJobs]') AND TYPE_DESC=N'USER_TABLE')\nBEGIN\n    GRANT DELETE ON [dbo].[TimerRunningJobs] TO [SPDataAccess]\nEND`
- `0xabb7a7`: `\n-- Grant DELETE on Locks table\nIF EXISTS (SELECT TOP 1 1 FROM sys.tables WHERE object_id = object_id(N'[dbo].[Locks]') AND TYPE_DESC=N'USER_TABLE')\nBEGIN\n    GRANT DELETE ON [dbo].[Locks] TO [SPDataAccess]\nEND`

## pseudocode

```c

```

## disassembly

```asm
0xab9f60  ldloca.s 0x24
0xab9f62  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [System.Data]System.Data.SqlDbType>
0xab9f68  ldloc.s  0x24
0xab9f6a  newobj   instance void Microsoft.SharePoint.Utilities.Sql.SPConfigDBSqlSchema::.ctor(valuetype [mscorlib]System.Nullable`1<valuetype [System.Data]System.Data.SqlDbType> partitionType)
0xab9f6f  stloc.0
0xab9f70  ldloc.0
0xab9f71  ldstr    aTvparrayofguid// "tvpArrayOfGuids"
0xab9f76  ldc.i4.1
0xab9f77  newarr   Microsoft.SharePoint.Utilities.Sql.Column
0xab9f7c  stloc.s  0x25
0xab9f7e  ldloc.s  0x25
0xab9f80  ldc.i4.0
0xab9f81  ldstr    aGuidvalue// "GuidValue"
0xab9f86  ldc.i4.s 0xE
0xab9f88  ldc.i4.0
0xab9f89  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xab9f8e  stelem.ref
0xab9f8f  ldloc.s  0x25
0xab9f91  callvirt instance class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddTableValuedType(string typeName, class Microsoft.SharePoint.Utilities.Sql.Column[] columns)
0xab9f96  pop
0xab9f97  ldloc.0
0xab9f98  ldstr    aTvpsiteurls2// "tvpSiteUrls2"
0xab9f9d  ldc.i4.4
0xab9f9e  newarr   Microsoft.SharePoint.Utilities.Sql.Column
0xab9fa3  stloc.s  0x26
0xab9fa5  ldloc.s  0x26
0xab9fa7  ldc.i4.0
0xab9fa8  ldstr    aHostheader_0// "HostHeader"
0xab9fad  ldc.i4.s 0xC
0xab9faf  ldc.i4   0x80
0xab9fb4  ldc.i4.0
0xab9fb5  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, int32 size, bool nullable)
0xab9fba  stelem.ref
0xab9fbb  ldloc.s  0x26
0xab9fbd  ldc.i4.1
0xab9fbe  ldstr    aScheme_1// "Scheme"
0xab9fc3  ldc.i4.s 0xC
0xab9fc5  ldc.i4.5
0xab9fc6  ldc.i4.0
0xab9fc7  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, int32 size, bool nullable)
0xab9fcc  stelem.ref
0xab9fcd  ldloc.s  0x26
0xab9fcf  ldc.i4.2
0xab9fd0  ldstr    aUrlzone_0// "UrlZone"
0xab9fd5  ldc.i4.s 0x14
0xab9fd7  ldc.i4.0
0xab9fd8  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xab9fdd  stelem.ref
0xab9fde  ldloc.s  0x26
0xab9fe0  ldc.i4.3
0xab9fe1  ldstr    aAppsitedomaini_3// "AppSiteDomainId"
0xab9fe6  ldc.i4.s 0x16
0xab9fe8  ldc.i4.6
0xab9fe9  ldc.i4.1
0xab9fea  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, int32 size, bool nullable)
0xab9fef  stelem.ref
0xab9ff0  ldloc.s  0x26
0xab9ff2  callvirt instance class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddTableValuedType(string typeName, class Microsoft.SharePoint.Utilities.Sql.Column[] columns)
0xab9ff7  pop
0xab9ff8  ldloc.0
0xab9ff9  ldstr    aBinaries// "Binaries"
0xab9ffe  ldc.i4.0
0xab9fff  ldc.i4.2
0xaba000  ldnull
0xaba001  ldc.i4.2
0xaba002  newarr   Microsoft.SharePoint.Utilities.Sql.Column
0xaba007  stloc.s  0x27
0xaba009  ldloc.s  0x27
0xaba00b  ldc.i4.0
0xaba00c  ldstr    aObjectid_1// "ObjectId"
0xaba011  ldc.i4.s 0xE
0xaba013  ldc.i4.0
0xaba014  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xaba019  stelem.ref
0xaba01a  ldloc.s  0x27
0xaba01c  ldc.i4.1
0xaba01d  ldstr    aFileimage// "FileImage"
0xaba022  ldc.i4.s 0x15
0xaba024  ldc.i4.m1
0xaba025  ldc.i4.0
0xaba026  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, int32 size, bool nullable)
0xaba02b  stelem.ref
0xaba02c  ldloc.s  0x27
0xaba02e  callvirt instance class Microsoft.SharePoint.Utilities.Sql.Table Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddTable(string name, valuetype Microsoft.SharePoint.Utilities.Sql.PartitionOptions partOptions, valuetype Microsoft.SharePoint.Utilities.Sql.LargeValueTypesOffRowOption blobValues, string partitionKeyCol, class Microsoft.SharePoint.Utilities.Sql.Column[] columns)
0xaba033  stloc.1
0xaba034  ldloc.0
0xaba035  ldstr    aPkObjectid// "PK_ObjectId"
0xaba03a  ldloc.1
0xaba03b  ldc.i4.0
0xaba03c  ldc.i4.1
0xaba03d  newarr   [mscorlib]System.String
0xaba042  stloc.s  0x28
0xaba044  ldloc.s  0x28
0xaba046  ldc.i4.0
0xaba047  ldstr    aObjectid_1// "ObjectId"
0xaba04c  stelem.ref
0xaba04d  ldloc.s  0x28
0xaba04f  callvirt instance class Microsoft.SharePoint.Utilities.Sql.Index Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddIndex(string idxName, class Microsoft.SharePoint.Utilities.Sql.Table tbl, valuetype Microsoft.SharePoint.Utilities.Sql.IndexType type, string[] cols)
0xaba054  pop
0xaba055  ldloc.0
0xaba056  ldstr    aFkBinaries1Obj// "FK_Binaries1_Objects"
0xaba05b  ldloc.1
0xaba05c  ldc.i4.1
0xaba05d  newarr   [mscorlib]System.String
0xaba062  stloc.s  0x29
0xaba064  ldloc.s  0x29
0xaba066  ldc.i4.0
0xaba067  ldstr    aObjectid_1// "ObjectId"
0xaba06c  stelem.ref
0xaba06d  ldloc.s  0x29
0xaba06f  ldstr    aObjects// "Objects"
0xaba074  ldc.i4.1
0xaba075  newarr   [mscorlib]System.String
0xaba07a  stloc.s  0x2A
0xaba07c  ldloc.s  0x2A
0xaba07e  ldc.i4.0
0xaba07f  ldstr    aId_2// "Id"
0xaba084  stelem.ref
0xaba085  ldloc.s  0x2A
0xaba087  ldc.i4.2
0xaba088  callvirt instance void Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddFKConstraint(string fkConsName, class Microsoft.SharePoint.Utilities.Sql.Table tblA, string[] tblACols, string tblBName, string[] tblBCols, valuetype FKOptions opts)
0xaba08d  ldloc.0
0xaba08e  ldstr    aClasses// "Classes"
0xaba093  ldc.i4.0
0xaba094  ldc.i4.0
0xaba095  ldnull
0xaba096  ldc.i4.3
0xaba097  newarr   Microsoft.SharePoint.Utilities.Sql.Column
0xaba09c  stloc.s  0x2B
0xaba09e  ldloc.s  0x2B
0xaba0a0  ldc.i4.0
0xaba0a1  ldstr    aId_2// "Id"
0xaba0a6  ldc.i4.s 0xE
0xaba0a8  ldc.i4.0
0xaba0a9  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xaba0ae  stelem.ref
0xaba0af  ldloc.s  0x2B
0xaba0b1  ldc.i4.1
0xaba0b2  ldstr    aBaseclassid_0// "BaseClassId"
0xaba0b7  ldc.i4.s 0xE
0xaba0b9  ldc.i4.0
0xaba0ba  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xaba0bf  stelem.ref
0xaba0c0  ldloc.s  0x2B
0xaba0c2  ldc.i4.2
0xaba0c3  ldstr    aFullname_1// "FullName"
0xaba0c8  ldc.i4.s 0xC
0xaba0ca  ldc.i4   0x100
0xaba0cf  ldc.i4.0
0xaba0d0  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, int32 size, bool nullable)
0xaba0d5  stelem.ref
0xaba0d6  ldloc.s  0x2B
0xaba0d8  callvirt instance class Microsoft.SharePoint.Utilities.Sql.Table Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddTable(string name, valuetype Microsoft.SharePoint.Utilities.Sql.PartitionOptions partOptions, valuetype Microsoft.SharePoint.Utilities.Sql.LargeValueTypesOffRowOption blobValues, string partitionKeyCol, class Microsoft.SharePoint.Utilities.Sql.Column[] columns)
0xaba0dd  stloc.2
0xaba0de  ldloc.0
0xaba0df  ldstr    aPkClasses// "PK_Classes"
0xaba0e4  ldloc.2
0xaba0e5  ldc.i4.1
0xaba0e6  ldc.i4.1
0xaba0e7  newarr   [mscorlib]System.String
0xaba0ec  stloc.s  0x2C
0xaba0ee  ldloc.s  0x2C
0xaba0f0  ldc.i4.0
0xaba0f1  ldstr    aId_2// "Id"
0xaba0f6  stelem.ref
0xaba0f7  ldloc.s  0x2C
0xaba0f9  callvirt instance class Microsoft.SharePoint.Utilities.Sql.Index Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddIndex(string idxName, class Microsoft.SharePoint.Utilities.Sql.Table tbl, valuetype Microsoft.SharePoint.Utilities.Sql.IndexType type, string[] cols)
0xaba0fe  stloc.3
0xaba0ff  ldloc.0
0xaba100  ldstr    aIxClassesBasec// "IX_Classes_BaseClassId"
0xaba105  ldloc.2
0xaba106  ldc.i4.2
0xaba107  ldc.i4.1
0xaba108  newarr   [mscorlib]System.String
0xaba10d  stloc.s  0x2D
0xaba10f  ldloc.s  0x2D
0xaba111  ldc.i4.0
0xaba112  ldstr    aBaseclassid_0// "BaseClassId"
0xaba117  stelem.ref
0xaba118  ldloc.s  0x2D
0xaba11a  callvirt instance class Microsoft.SharePoint.Utilities.Sql.Index Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddIndex(string idxName, class Microsoft.SharePoint.Utilities.Sql.Table tbl, valuetype Microsoft.SharePoint.Utilities.Sql.IndexType type, string[] cols)
0xaba11f  stloc.s  4
0xaba121  ldloc.0
0xaba122  ldstr    aTvfClassesId// "TVF_Classes_Id"
0xaba127  ldloc.3
0xaba128  ldc.i4.1
0xaba129  ldc.i4.1
0xaba12a  newarr   Microsoft.SharePoint.Utilities.Sql.Restriction
0xaba12f  stloc.s  0x2E
0xaba131  ldloc.s  0x2E
0xaba133  ldc.i4.0
0xaba134  ldstr    aId_2// "Id"
0xaba139  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterRestriction::.ctor(string column)
0xaba13e  stelem.ref
0xaba13f  ldloc.s  0x2E
0xaba141  callvirt instance void Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddTVF(string tvfName, class Microsoft.SharePoint.Utilities.Sql.Index idx, valuetype LockHint lockHints, class Microsoft.SharePoint.Utilities.Sql.Restriction[] args)
0xaba146  ldloc.0
0xaba147  ldstr    aTvfClassesBase// "TVF_Classes_BaseClassId"
0xaba14c  ldloc.s  4
0xaba14e  ldc.i4.1
0xaba14f  ldc.i4.1
0xaba150  newarr   Microsoft.SharePoint.Utilities.Sql.Restriction
0xaba155  stloc.s  0x2F
0xaba157  ldloc.s  0x2F
0xaba159  ldc.i4.0
0xaba15a  ldstr    aBaseclassid_0// "BaseClassId"
0xaba15f  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterRestriction::.ctor(string column)
0xaba164  stelem.ref
0xaba165  ldloc.s  0x2F
0xaba167  callvirt instance void Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddTVF(string tvfName, class Microsoft.SharePoint.Utilities.Sql.Index idx, valuetype LockHint lockHints, class Microsoft.SharePoint.Utilities.Sql.Restriction[] args)
0xaba16c  ldloc.0
0xaba16d  ldstr    aFkClassesClass// "FK_Classes_Classes"
0xaba172  ldloc.2
0xaba173  ldc.i4.1
0xaba174  newarr   [mscorlib]System.String
0xaba179  stloc.s  0x30
0xaba17b  ldloc.s  0x30
0xaba17d  ldc.i4.0
0xaba17e  ldstr    aBaseclassid_0// "BaseClassId"
0xaba183  stelem.ref
0xaba184  ldloc.s  0x30
0xaba186  ldstr    aClasses// "Classes"
0xaba18b  ldc.i4.1
0xaba18c  newarr   [mscorlib]System.String
0xaba191  stloc.s  0x31
0xaba193  ldloc.s  0x31
0xaba195  ldc.i4.0
0xaba196  ldstr    aId_2// "Id"
0xaba19b  stelem.ref
0xaba19c  ldloc.s  0x31
0xaba19e  ldc.i4.0
0xaba19f  callvirt instance void Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddFKConstraint(string fkConsName, class Microsoft.SharePoint.Utilities.Sql.Table tblA, string[] tblACols, string tblBName, string[] tblBCols, valuetype FKOptions opts)
0xaba1a4  ldloc.0
0xaba1a5  ldstr    aDependencies// "Dependencies"
0xaba1aa  ldc.i4.0
0xaba1ab  ldc.i4.0
0xaba1ac  ldnull
0xaba1ad  ldc.i4.2
0xaba1ae  newarr   Microsoft.SharePoint.Utilities.Sql.Column
0xaba1b3  stloc.s  0x32
0xaba1b5  ldloc.s  0x32
0xaba1b7  ldc.i4.0
0xaba1b8  ldstr    aObjectid_1// "ObjectId"
0xaba1bd  ldc.i4.s 0xE
0xaba1bf  ldc.i4.0
0xaba1c0  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xaba1c5  stelem.ref
0xaba1c6  ldloc.s  0x32
0xaba1c8  ldc.i4.1
0xaba1c9  ldstr    aDependantid_0// "DependantId"
0xaba1ce  ldc.i4.s 0xE
0xaba1d0  ldc.i4.0
0xaba1d1  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xaba1d6  stelem.ref
0xaba1d7  ldloc.s  0x32
0xaba1d9  callvirt instance class Microsoft.SharePoint.Utilities.Sql.Table Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddTable(string name, valuetype Microsoft.SharePoint.Utilities.Sql.PartitionOptions partOptions, valuetype Microsoft.SharePoint.Utilities.Sql.LargeValueTypesOffRowOption blobValues, string partitionKeyCol, class Microsoft.SharePoint.Utilities.Sql.Column[] columns)
0xaba1de  stloc.s  5
0xaba1e0  ldloc.0
0xaba1e1  ldstr    aIxDependencies// "IX_Dependencies_ObjectId"
0xaba1e6  ldloc.s  5
0xaba1e8  ldc.i4.2
0xaba1e9  ldc.i4.1
0xaba1ea  newarr   [mscorlib]System.String
0xaba1ef  stloc.s  0x33
0xaba1f1  ldloc.s  0x33
0xaba1f3  ldc.i4.0
0xaba1f4  ldstr    aObjectid_1// "ObjectId"
0xaba1f9  stelem.ref
0xaba1fa  ldloc.s  0x33
0xaba1fc  callvirt instance class Microsoft.SharePoint.Utilities.Sql.Index Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddIndex(string idxName, class Microsoft.SharePoint.Utilities.Sql.Table tbl, valuetype Microsoft.SharePoint.Utilities.Sql.IndexType type, string[] cols)
0xaba201  stloc.s  6
0xaba203  ldloc.0
0xaba204  ldstr    aTvfDependencie// "TVF_Dependencies_ObjectId"
0xaba209  ldloc.s  6
0xaba20b  ldc.i4.1
0xaba20c  ldc.i4.1
0xaba20d  newarr   Microsoft.SharePoint.Utilities.Sql.Restriction
0xaba212  stloc.s  0x34
0xaba214  ldloc.s  0x34
0xaba216  ldc.i4.0
0xaba217  ldstr    aObjectid_1// "ObjectId"
0xaba21c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterRestriction::.ctor(string column)
0xaba221  stelem.ref
0xaba222  ldloc.s  0x34
0xaba224  callvirt instance void Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddTVF(string tvfName, class Microsoft.SharePoint.Utilities.Sql.Index idx, valuetype LockHint lockHints, class Microsoft.SharePoint.Utilities.Sql.Restriction[] args)
0xaba229  ldloc.0
0xaba22a  ldstr    aFkDependencies// "FK_Dependencies1_Objects"
0xaba22f  ldloc.s  5
0xaba231  ldc.i4.1
0xaba232  newarr   [mscorlib]System.String
0xaba237  stloc.s  0x35
0xaba239  ldloc.s  0x35
0xaba23b  ldc.i4.0
0xaba23c  ldstr    aObjectid_1// "ObjectId"
0xaba241  stelem.ref
0xaba242  ldloc.s  0x35
0xaba244  ldstr    aObjects// "Objects"
0xaba249  ldc.i4.1
0xaba24a  newarr   [mscorlib]System.String
0xaba24f  stloc.s  0x36
  ... truncated ...
```
