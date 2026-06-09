# Microsoft.SharePoint.Utilities.Sql.SPSiteMapDBSqlSchema::BuildSchema

- ea: `0xabbcd0`
- end: `0xabc51b`
- name: `Microsoft.SharePoint.Utilities.Sql.SPSiteMapDBSqlSchema::BuildSchema`
- size: `2123`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0xabc670`

## callees

- `0x2bec60`
- `0x2beeb0`
- `0x2beec0`
- `0x2bf120`
- `0x2bf170`
- `0x2bf250`
- `0x2bf380`
- `0x95fd70`
- `0x95fda0`
- `0x95fdb0`
- `0x95fde0`
- `0x960030`
- `0x960270`
- `0x960760`
- `0x960800`
- `0xabc520`

## string_xrefs

- `0xabbd8e`: `DeleteTransactionId`
- `0xabbeab`: `DeleteTransactionId`
- `0xabbede`: `DeleteTransactionId`
- `0xabbfde`: `DeleteTransactionId`
- `0xabc023`: `DeleteTransactionId`
- `0xabc24d`: `DeleteTransactionId`
- `0xabc2dc`: `DeleteTransactionId`
- `0xabc319`: `DeleteTransactionId`
- `0xabc36f`: `DeleteTransactionId`
- `0xabc390`: `DeleteTransactionId`
- `0xabc3bf`: `DeleteTransactionId`
- `0xabc3fb`: `DeleteTransactionId`
- `0xabc487`: `DeleteTransactionId`
- `0xabc4b1`: `DeleteTransactionId`
- `0xabc4d2`: `DeleteTransactionId`
- `0xabbf41`: `IX_SiteMap_Path_HostHeaderIsSiteName`
- `0xabc1f0`: `NumSites`
- `0xabc276`: `HostAndPath`
- `0xabc2e5`: `HostAndPath`
- `0xabbeba`: `IX_SiteMap_DatabaseId_Path`
- `0xabc03b`: `TVF_SiteMap_Path`

## pseudocode

```c

```

## disassembly

```asm
0xabbcd0  ldloca.s 0xB
0xabbcd2  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [System.Data]System.Data.SqlDbType>
0xabbcd8  ldloc.s  0xB
0xabbcda  newobj   instance void Microsoft.SharePoint.Utilities.Sql.SPSiteMapDBSqlSchema::.ctor(valuetype [mscorlib]System.Nullable`1<valuetype [System.Data]System.Data.SqlDbType> partitionType)
0xabbcdf  stloc.0
0xabbce0  ldloc.0
0xabbce1  ldstr    aTvparrayofguid// "tvpArrayOfGuids"
0xabbce6  ldc.i4.1
0xabbce7  newarr   Microsoft.SharePoint.Utilities.Sql.Column
0xabbcec  stloc.s  0xC
0xabbcee  ldloc.s  0xC
0xabbcf0  ldc.i4.0
0xabbcf1  ldstr    aGuidvalue// "GuidValue"
0xabbcf6  ldc.i4.s 0xE
0xabbcf8  ldc.i4.0
0xabbcf9  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xabbcfe  stelem.ref
0xabbcff  ldloc.s  0xC
0xabbd01  callvirt instance class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddTableValuedType(string typeName, class Microsoft.SharePoint.Utilities.Sql.Column[] columns)
0xabbd06  pop
0xabbd07  ldloc.0
0xabbd08  ldstr    aTvpsiteurls2// "tvpSiteUrls2"
0xabbd0d  ldc.i4.4
0xabbd0e  newarr   Microsoft.SharePoint.Utilities.Sql.Column
0xabbd13  stloc.s  0xD
0xabbd15  ldloc.s  0xD
0xabbd17  ldc.i4.0
0xabbd18  ldstr    aHostheader_0// "HostHeader"
0xabbd1d  ldc.i4.s 0xC
0xabbd1f  ldc.i4   0x80
0xabbd24  ldc.i4.0
0xabbd25  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, int32 size, bool nullable)
0xabbd2a  stelem.ref
0xabbd2b  ldloc.s  0xD
0xabbd2d  ldc.i4.1
0xabbd2e  ldstr    aScheme_1// "Scheme"
0xabbd33  ldc.i4.s 0xC
0xabbd35  ldc.i4.5
0xabbd36  ldc.i4.0
0xabbd37  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, int32 size, bool nullable)
0xabbd3c  stelem.ref
0xabbd3d  ldloc.s  0xD
0xabbd3f  ldc.i4.2
0xabbd40  ldstr    aUrlzone_0// "UrlZone"
0xabbd45  ldc.i4.s 0x14
0xabbd47  ldc.i4.0
0xabbd48  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xabbd4d  stelem.ref
0xabbd4e  ldloc.s  0xD
0xabbd50  ldc.i4.3
0xabbd51  ldstr    aAppsitedomaini_3// "AppSiteDomainId"
0xabbd56  ldc.i4.s 0x16
0xabbd58  ldc.i4.6
0xabbd59  ldc.i4.1
0xabbd5a  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, int32 size, bool nullable)
0xabbd5f  stelem.ref
0xabbd60  ldloc.s  0xD
0xabbd62  callvirt instance class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddTableValuedType(string typeName, class Microsoft.SharePoint.Utilities.Sql.Column[] columns)
0xabbd67  pop
0xabbd68  ldloc.0
0xabbd69  ldstr    aSitemap// "SiteMap"
0xabbd6e  ldc.i4.0
0xabbd6f  ldc.i4.0
0xabbd70  ldnull
0xabbd71  ldc.i4.s 0xE
0xabbd73  newarr   Microsoft.SharePoint.Utilities.Sql.Column
0xabbd78  stloc.s  0xE
0xabbd7a  ldloc.s  0xE
0xabbd7c  ldc.i4.0
0xabbd7d  ldstr    aId_2// "Id"
0xabbd82  ldc.i4.s 0xE
0xabbd84  ldc.i4.0
0xabbd85  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xabbd8a  stelem.ref
0xabbd8b  ldloc.s  0xE
0xabbd8d  ldc.i4.1
0xabbd8e  ldstr    aDeletetransact_3// "DeleteTransactionId"
0xabbd93  ldc.i4.s 0x15
0xabbd95  ldc.i4.s 0x10
0xabbd97  ldc.i4.0
0xabbd98  ldstr    a0x// "0x"
0xabbd9d  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type, int32 size, bool nullable, string defaultExpression)
0xabbda2  stelem.ref
0xabbda3  ldloc.s  0xE
0xabbda5  ldc.i4.2
0xabbda6  ldstr    aDeletiontime_0// "DeletionTime"
0xabbdab  ldc.i4.4
0xabbdac  ldc.i4.1
0xabbdad  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xabbdb2  stelem.ref
0xabbdb3  ldloc.s  0xE
0xabbdb5  ldc.i4.3
0xabbdb6  ldstr    aDatabaseid_0// "DatabaseId"
0xabbdbb  ldc.i4.s 0xE
0xabbdbd  ldc.i4.0
0xabbdbe  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xabbdc3  stelem.ref
0xabbdc4  ldloc.s  0xE
0xabbdc6  ldc.i4.4
0xabbdc7  ldstr    aPath_1// "Path"
0xabbdcc  ldc.i4.s 0xC
0xabbdce  ldc.i4   0x80
0xabbdd3  ldc.i4.0
0xabbdd4  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, int32 size, bool nullable)
0xabbdd9  stelem.ref
0xabbdda  ldloc.s  0xE
0xabbddc  ldc.i4.5
0xabbddd  ldstr    aPairing_0// "Pairing"
0xabbde2  ldc.i4.s 0x14
0xabbde4  ldc.i4.0
0xabbde5  ldstr    a0// "0"
0xabbdea  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable, string defaultExpression)
0xabbdef  stelem.ref
0xabbdf0  ldloc.s  0xE
0xabbdf2  ldc.i4.6
0xabbdf3  ldstr    aStatus_1// "Status"
0xabbdf8  ldc.i4.8
0xabbdf9  ldc.i4.0
0xabbdfa  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xabbdff  stelem.ref
0xabbe00  ldloc.s  0xE
0xabbe02  ldc.i4.7
0xabbe03  ldstr    aVersion_1// "Version"
0xabbe08  ldc.i4.s 0x13
0xabbe0a  ldc.i4.0
0xabbe0b  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xabbe10  stelem.ref
0xabbe11  ldloc.s  0xE
0xabbe13  ldc.i4.8
0xabbe14  ldstr    aRedirecturl_0// "RedirectUrl"
0xabbe19  ldc.i4.s 0xC
0xabbe1b  ldc.i4   0x200
0xabbe20  ldc.i4.1
0xabbe21  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, int32 size, bool nullable)
0xabbe26  stelem.ref
0xabbe27  ldloc.s  0xE
0xabbe29  ldc.i4.s 9
0xabbe2b  ldstr    aHostheaderissi_1// "HostHeaderIsSiteName"
0xabbe30  ldc.i4.2
0xabbe31  ldc.i4.0
0xabbe32  ldstr    a0// "0"
0xabbe37  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable, string defaultExpression)
0xabbe3c  stelem.ref
0xabbe3d  ldloc.s  0xE
0xabbe3f  ldc.i4.s 0xA
0xabbe41  ldstr    aSubscriptionid// "SubscriptionId"
0xabbe46  ldc.i4.s 0xE
0xabbe48  ldc.i4.1
0xabbe49  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xabbe4e  stelem.ref
0xabbe4f  ldloc.s  0xE
0xabbe51  ldc.i4.s 0xB
0xabbe53  ldstr    aSourcesiteid_0// "SourceSiteId"
0xabbe58  ldc.i4.s 0xE
0xabbe5a  newobj   instance void Microsoft.SharePoint.Utilities.Sql.SparseColumn::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0xabbe5f  stelem.ref
0xabbe60  ldloc.s  0xE
0xabbe62  ldc.i4.s 0xC
0xabbe64  ldstr    aSubscriptionna_2// "SubscriptionName"
0xabbe69  ldc.i4.s 0xC
0xabbe6b  ldc.i4.s 0x30
0xabbe6d  ldc.i4.1
0xabbe6e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, int32 size, bool nullable)
0xabbe73  stelem.ref
0xabbe74  ldloc.s  0xE
0xabbe76  ldc.i4.s 0xD
0xabbe78  ldstr    aAppsitedomaini_3// "AppSiteDomainId"
0xabbe7d  ldc.i4.s 0x16
0xabbe7f  ldc.i4.6
0xabbe80  ldc.i4.1
0xabbe81  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, int32 size, bool nullable)
0xabbe86  stelem.ref
0xabbe87  ldloc.s  0xE
0xabbe89  callvirt instance class Microsoft.SharePoint.Utilities.Sql.Table Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddTable(string name, valuetype Microsoft.SharePoint.Utilities.Sql.PartitionOptions partOptions, valuetype Microsoft.SharePoint.Utilities.Sql.LargeValueTypesOffRowOption blobValues, string partitionKeyCol, class Microsoft.SharePoint.Utilities.Sql.Column[] columns)
0xabbe8e  stloc.1
0xabbe8f  ldloc.0
0xabbe90  ldstr    aPkSitemap// "PK_SiteMap"
0xabbe95  ldloc.1
0xabbe96  ldc.i4.1
0xabbe97  ldc.i4.2
0xabbe98  newarr   [mscorlib]System.String
0xabbe9d  stloc.s  0xF
0xabbe9f  ldloc.s  0xF
0xabbea1  ldc.i4.0
0xabbea2  ldstr    aId_2// "Id"
0xabbea7  stelem.ref
0xabbea8  ldloc.s  0xF
0xabbeaa  ldc.i4.1
0xabbeab  ldstr    aDeletetransact_3// "DeleteTransactionId"
0xabbeb0  stelem.ref
0xabbeb1  ldloc.s  0xF
0xabbeb3  callvirt instance class Microsoft.SharePoint.Utilities.Sql.Index Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddIndex(string idxName, class Microsoft.SharePoint.Utilities.Sql.Table tbl, valuetype Microsoft.SharePoint.Utilities.Sql.IndexType type, string[] cols)
0xabbeb8  stloc.2
0xabbeb9  ldloc.0
0xabbeba  ldstr    aIxSitemapDatab_0// "IX_SiteMap_DatabaseId_Path"
0xabbebf  ldloc.1
0xabbec0  ldc.i4.3
0xabbec1  ldc.i4.3
0xabbec2  newarr   [mscorlib]System.String
0xabbec7  stloc.s  0x10
0xabbec9  ldloc.s  0x10
0xabbecb  ldc.i4.0
0xabbecc  ldstr    aPath_1// "Path"
0xabbed1  stelem.ref
0xabbed2  ldloc.s  0x10
0xabbed4  ldc.i4.1
0xabbed5  ldstr    aDatabaseid_0// "DatabaseId"
0xabbeda  stelem.ref
0xabbedb  ldloc.s  0x10
0xabbedd  ldc.i4.2
0xabbede  ldstr    aDeletetransact_3// "DeleteTransactionId"
0xabbee3  stelem.ref
0xabbee4  ldloc.s  0x10
0xabbee6  callvirt instance class Microsoft.SharePoint.Utilities.Sql.Index Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddIndex(string idxName, class Microsoft.SharePoint.Utilities.Sql.Table tbl, valuetype Microsoft.SharePoint.Utilities.Sql.IndexType type, string[] cols)
0xabbeeb  stloc.3
0xabbeec  ldloc.0
0xabbeed  ldstr    aIxSitemapDatab// "IX_SiteMap_DatabaseId_SubscriptionId"
0xabbef2  ldloc.1
0xabbef3  ldc.i4.4
0xabbef4  ldc.i4.2
0xabbef5  newarr   [mscorlib]System.String
0xabbefa  stloc.s  0x11
0xabbefc  ldloc.s  0x11
0xabbefe  ldc.i4.0
0xabbeff  ldstr    aDatabaseid_0// "DatabaseId"
0xabbf04  stelem.ref
0xabbf05  ldloc.s  0x11
0xabbf07  ldc.i4.1
0xabbf08  ldstr    aSubscriptionid// "SubscriptionId"
0xabbf0d  stelem.ref
0xabbf0e  ldloc.s  0x11
0xabbf10  callvirt instance class Microsoft.SharePoint.Utilities.Sql.Index Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddIndex(string idxName, class Microsoft.SharePoint.Utilities.Sql.Table tbl, valuetype Microsoft.SharePoint.Utilities.Sql.IndexType type, string[] cols)
0xabbf15  pop
0xabbf16  ldloc.0
0xabbf17  ldstr    aIxSitemapSubsc_0// "IX_SiteMap_SubscriptionId_DatabaseId"
0xabbf1c  ldloc.1
0xabbf1d  ldc.i4.4
0xabbf1e  ldc.i4.2
0xabbf1f  newarr   [mscorlib]System.String
0xabbf24  stloc.s  0x12
0xabbf26  ldloc.s  0x12
0xabbf28  ldc.i4.0
0xabbf29  ldstr    aSubscriptionid// "SubscriptionId"
0xabbf2e  stelem.ref
0xabbf2f  ldloc.s  0x12
0xabbf31  ldc.i4.1
0xabbf32  ldstr    aDatabaseid_0// "DatabaseId"
0xabbf37  stelem.ref
0xabbf38  ldloc.s  0x12
0xabbf3a  callvirt instance class Microsoft.SharePoint.Utilities.Sql.Index Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddIndex(string idxName, class Microsoft.SharePoint.Utilities.Sql.Table tbl, valuetype Microsoft.SharePoint.Utilities.Sql.IndexType type, string[] cols)
0xabbf3f  pop
0xabbf40  ldloc.0
0xabbf41  ldstr    aIxSitemapPathH// "IX_SiteMap_Path_HostHeaderIsSiteName"
0xabbf46  ldloc.1
0xabbf47  ldc.i4.4
0xabbf48  ldc.i4.2
0xabbf49  newarr   [mscorlib]System.String
0xabbf4e  stloc.s  0x13
0xabbf50  ldloc.s  0x13
0xabbf52  ldc.i4.0
0xabbf53  ldstr    aPath_1// "Path"
0xabbf58  stelem.ref
0xabbf59  ldloc.s  0x13
0xabbf5b  ldc.i4.1
0xabbf5c  ldstr    aHostheaderissi_1// "HostHeaderIsSiteName"
0xabbf61  stelem.ref
0xabbf62  ldloc.s  0x13
0xabbf64  callvirt instance class Microsoft.SharePoint.Utilities.Sql.Index Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddIndex(string idxName, class Microsoft.SharePoint.Utilities.Sql.Table tbl, valuetype Microsoft.SharePoint.Utilities.Sql.IndexType type, string[] cols)
0xabbf69  pop
0xabbf6a  ldloc.0
0xabbf6b  ldstr    aIxSitemapAppsi// "IX_SiteMap_AppSiteDomainPrefix"
0xabbf70  ldloc.1
0xabbf71  ldc.i4.4
0xabbf72  ldc.i4.2
0xabbf73  newarr   [mscorlib]System.String
0xabbf78  stloc.s  0x14
0xabbf7a  ldloc.s  0x14
0xabbf7c  ldc.i4.0
0xabbf7d  ldstr    aSubscriptionna_2// "SubscriptionName"
0xabbf82  stelem.ref
0xabbf83  ldloc.s  0x14
0xabbf85  ldc.i4.1
0xabbf86  ldstr    aAppsitedomaini_3// "AppSiteDomainId"
0xabbf8b  stelem.ref
0xabbf8c  ldloc.s  0x14
0xabbf8e  callvirt instance class Microsoft.SharePoint.Utilities.Sql.Index Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddIndex(string idxName, class Microsoft.SharePoint.Utilities.Sql.Table tbl, valuetype Microsoft.SharePoint.Utilities.Sql.IndexType type, string[] cols)
0xabbf93  pop
0xabbf94  ldloc.0
0xabbf95  ldstr    aIxSitemapDatab_1// "IX_SiteMap_DatabaseId_DeletionTime"
0xabbf9a  ldloc.1
0xabbf9b  ldc.i4.4
0xabbf9c  ldc.i4.2
0xabbf9d  newarr   [mscorlib]System.String
0xabbfa2  stloc.s  0x15
0xabbfa4  ldloc.s  0x15
0xabbfa6  ldc.i4.0
0xabbfa7  ldstr    aDatabaseid_0// "DatabaseId"
0xabbfac  stelem.ref
0xabbfad  ldloc.s  0x15
0xabbfaf  ldc.i4.1
  ... truncated ...
```
