# Microsoft.SharePoint.Utilities.Sql.SPSearchDatabaseSchema::BuildSchema15

- ea: `0xadfb20`
- end: `0xae09c1`
- name: `Microsoft.SharePoint.Utilities.Sql.SPSearchDatabaseSchema::BuildSchema15`
- size: `3745`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0xae09d0`

## callees

- `0x2beec0`
- `0x2bf170`
- `0x2bf250`
- `0x2bf260`
- `0x2bf280`
- `0x95fd80`
- `0x95fda0`
- `0x95fdb0`
- `0x95ffe0`
- `0x9600d0`
- `0x960270`
- `0xadf8e0`

## string_xrefs

- `0xae03ee`: `IsDeleted`
- `0xadfc3e`: `MSSCrawlLinks`
- `0xadfc86`: `DF_MSSCrawlLinks_InsertTime`
- `0xadfc9b`: `IX_MSSCrawlLinks_ParentTransactionID_ObjectID`
- `0xadfcc7`: `IX_MSSCrawlLinks_InsertTime`
- `0xadfceb`: `TVF_MSSCrawlLinks_ParentTransactionID_ObjectID`
- `0xadfd1f`: `TVF_MSSCrawlLinks_InsertTime`
- `0xadfdb9`: `DeleteReason`
- `0xae0408`: `DeleteReason`
- `0xadfdc6`: `DF_MSSCrawlQueue_DeleteReason`
- `0xadfdd4`: `CachedBlob`
- `0xadfdf2`: `DF_MSSCrawlLinks_Recovered`
- `0xae0076`: `Protocol`
- `0xae00bd`: `AccessData`
- `0xae00e9`: `DeletePending`
- `0xae02be`: `DeletePending`
- `0xae02f6`: `DeletePending`
- `0xae034d`: `DeletePending`
- `0xae0381`: `DeletePending`
- `0xae00f6`: `DF_MSSCrawlURL_DeletePending`
- `0xae01be`: `ErrorCode_SecurityOnly`
- `0xae043d`: `ErrorCode_SecurityOnly`
- `0xae01ca`: `DF_MSSCrawlURL_ErrorCode_SecurityOnly`
- `0xae01d9`: `ErrorCount_SecurityOnly`
- `0xae05b0`: `ErrorCount_SecurityOnly`
- `0xae01e6`: `DF_MSSCrawlURL_ErrorCount_SecurityOnly`
- `0xae01f5`: `SecurityID`
- `0xae03fa`: `DF_MSSCrawlURLReport_IsDeleted`
- `0xae0415`: `DF_MSSCrawlURLReport_DeleteReason`
- `0xae0449`: `DF_MSSCrawlURLReport_ErrorCode_SecurityOnly`
- `0xae04a1`: `TimeStamp_SecurityOnly`
- `0xae085c`: `MSSConfiguration`
- `0xae0892`: `LastUpdateTime`
- `0xae08ae`: `DF_MSSConfiguration_ManualServerAssignment`
- `0xae08c8`: `DF_MSSConfiguration_ContinuousCrawlEnabled`
- `0xae08dd`: `IX_MSSConfiguration_Server`
- `0xae0900`: `TVF_MSSConfiguration_Server`
- `0xae0926`: `MSSConfiguration2`
- `0xae0977`: `IX_MSSConfiguration2`
- `0xae099a`: `TVF_MSSConfiguration2_Name`

## pseudocode

```c

```

## disassembly

```asm
0xadfb20  newobj   instance void Microsoft.SharePoint.Utilities.Sql.SPSearchDatabaseSchema::.ctor()
0xadfb25  stloc.0
0xadfb26  ldloc.0
0xadfb27  ldstr    aMsssites// "MSSSites"
0xadfb2c  ldc.i4.0
0xadfb2d  ldc.i4.0
0xadfb2e  ldstr    aSiteid_0// "SiteId"
0xadfb33  ldc.i4.2
0xadfb34  newarr   Microsoft.SharePoint.Utilities.Sql.Column
0xadfb39  stloc.s  0x22
0xadfb3b  ldloc.s  0x22
0xadfb3d  ldc.i4.0
0xadfb3e  ldstr    aTenantid_2// "TenantID"
0xadfb43  ldc.i4.s 0xE
0xadfb45  ldc.i4.0
0xadfb46  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xadfb4b  stelem.ref
0xadfb4c  ldloc.s  0x22
0xadfb4e  ldc.i4.1
0xadfb4f  ldstr    aSiteid_3// "SiteID"
0xadfb54  ldc.i4.s 0xE
0xadfb56  ldc.i4.0
0xadfb57  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xadfb5c  stelem.ref
0xadfb5d  ldloc.s  0x22
0xadfb5f  callvirt instance class Microsoft.SharePoint.Utilities.Sql.Table Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddTable(string name, valuetype Microsoft.SharePoint.Utilities.Sql.PartitionOptions partOptions, valuetype Microsoft.SharePoint.Utilities.Sql.LargeValueTypesOffRowOption blobValues, string partitionKeyCol, class Microsoft.SharePoint.Utilities.Sql.Column[] columns)
0xadfb64  stloc.1
0xadfb65  ldloc.0
0xadfb66  ldstr    aIxMsssitesSite// "IX_MSSSites_SiteID"
0xadfb6b  ldloc.1
0xadfb6c  ldc.i4.3
0xadfb6d  ldc.i4.2
0xadfb6e  ldc.i4.1
0xadfb6f  newarr   [mscorlib]System.String
0xadfb74  stloc.s  0x23
0xadfb76  ldloc.s  0x23
0xadfb78  ldc.i4.0
0xadfb79  ldstr    aSiteid_3// "SiteID"
0xadfb7e  stelem.ref
0xadfb7f  ldloc.s  0x23
0xadfb81  callvirt instance class Microsoft.SharePoint.Utilities.Sql.Index Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddIndex(string idxName, class Microsoft.SharePoint.Utilities.Sql.Table tbl, valuetype Microsoft.SharePoint.Utilities.Sql.IndexType type, valuetype Microsoft.SharePoint.Utilities.Sql.FillFactor fillfactor, string[] cols)
0xadfb86  stloc.2
0xadfb87  ldloc.0
0xadfb88  ldstr    aTvfMsssitesSit// "TVF_MSSSites_SiteID"
0xadfb8d  ldloc.2
0xadfb8e  ldc.i4.0
0xadfb8f  ldc.i4.1
0xadfb90  newarr   Microsoft.SharePoint.Utilities.Sql.Restriction
0xadfb95  stloc.s  0x24
0xadfb97  ldloc.s  0x24
0xadfb99  ldc.i4.0
0xadfb9a  ldstr    aSiteid_3// "SiteID"
0xadfb9f  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterRestriction::.ctor(string column)
0xadfba4  stelem.ref
0xadfba5  ldloc.s  0x24
0xadfba7  callvirt instance void Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddTVF(string tvfName, class Microsoft.SharePoint.Utilities.Sql.Index idx, valuetype LockHint lockHints, class Microsoft.SharePoint.Utilities.Sql.Restriction[] args)
0xadfbac  ldloc.0
0xadfbad  ldstr    aMssbatchhistor// "MSSBatchHistory"
0xadfbb2  ldc.i4.0
0xadfbb3  ldc.i4.0
0xadfbb4  ldnull
0xadfbb5  ldc.i4.2
0xadfbb6  newarr   Microsoft.SharePoint.Utilities.Sql.Column
0xadfbbb  stloc.s  0x25
0xadfbbd  ldloc.s  0x25
0xadfbbf  ldc.i4.0
0xadfbc0  ldstr    aBatchid_1// "BatchID"
0xadfbc5  ldc.i4.0
0xadfbc6  ldstr    a11_4// "1,1"
0xadfbcb  ldc.i4.0
0xadfbcc  newobj   instance void Microsoft.SharePoint.Utilities.Sql.IdentityColumn::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type, string initVals, bool nullable)
0xadfbd1  stelem.ref
0xadfbd2  ldloc.s  0x25
0xadfbd4  ldc.i4.1
0xadfbd5  ldstr    aStamp// "Stamp"
0xadfbda  ldc.i4.4
0xadfbdb  ldc.i4.0
0xadfbdc  ldstr    aGetutcdate_0// "GETUTCDate()"
0xadfbe1  ldstr    aDfMssbatchhist// "DF_MSSBatchHistory_Stamp"
0xadfbe6  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable, string defaultExpression, string defaultConstraintName)
0xadfbeb  stelem.ref
0xadfbec  ldloc.s  0x25
0xadfbee  callvirt instance class Microsoft.SharePoint.Utilities.Sql.Table Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddTable(string name, valuetype Microsoft.SharePoint.Utilities.Sql.PartitionOptions partOptions, valuetype Microsoft.SharePoint.Utilities.Sql.LargeValueTypesOffRowOption blobValues, string partitionKeyCol, class Microsoft.SharePoint.Utilities.Sql.Column[] columns)
0xadfbf3  stloc.3
0xadfbf4  ldloc.0
0xadfbf5  ldstr    aIxMssbatchhist// "IX_MSSBatchHistory"
0xadfbfa  ldloc.3
0xadfbfb  ldc.i4.2
0xadfbfc  ldc.i4.2
0xadfbfd  ldc.i4.1
0xadfbfe  newarr   [mscorlib]System.String
0xadfc03  stloc.s  0x26
0xadfc05  ldloc.s  0x26
0xadfc07  ldc.i4.0
0xadfc08  ldstr    aStamp// "Stamp"
0xadfc0d  stelem.ref
0xadfc0e  ldloc.s  0x26
0xadfc10  callvirt instance class Microsoft.SharePoint.Utilities.Sql.Index Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddIndex(string idxName, class Microsoft.SharePoint.Utilities.Sql.Table tbl, valuetype Microsoft.SharePoint.Utilities.Sql.IndexType type, valuetype Microsoft.SharePoint.Utilities.Sql.FillFactor fillfactor, string[] cols)
0xadfc15  stloc.s  4
0xadfc17  ldloc.0
0xadfc18  ldstr    aTvfMssbatchhis// "TVF_MSSBatchHistory_Stamp"
0xadfc1d  ldloc.s  4
0xadfc1f  ldc.i4.0
0xadfc20  ldc.i4.1
0xadfc21  newarr   Microsoft.SharePoint.Utilities.Sql.Restriction
0xadfc26  stloc.s  0x27
0xadfc28  ldloc.s  0x27
0xadfc2a  ldc.i4.0
0xadfc2b  ldstr    aStamp// "Stamp"
0xadfc30  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterRestriction::.ctor(string column)
0xadfc35  stelem.ref
0xadfc36  ldloc.s  0x27
0xadfc38  callvirt instance void Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddTVF(string tvfName, class Microsoft.SharePoint.Utilities.Sql.Index idx, valuetype LockHint lockHints, class Microsoft.SharePoint.Utilities.Sql.Restriction[] args)
0xadfc3d  ldloc.0
0xadfc3e  ldstr    aMsscrawllinks// "MSSCrawlLinks"
0xadfc43  ldc.i4.0
0xadfc44  ldc.i4.0
0xadfc45  ldnull
0xadfc46  ldc.i4.3
0xadfc47  newarr   Microsoft.SharePoint.Utilities.Sql.Column
0xadfc4c  stloc.s  0x28
0xadfc4e  ldloc.s  0x28
0xadfc50  ldc.i4.0
0xadfc51  ldstr    aParenttransact// "ParentTransactionID"
0xadfc56  ldc.i4.s 0xC
0xadfc58  ldc.i4   0x100
0xadfc5d  ldc.i4.0
0xadfc5e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, int32 size, bool nullable)
0xadfc63  stelem.ref
0xadfc64  ldloc.s  0x28
0xadfc66  ldc.i4.1
0xadfc67  ldstr    aObjectid_3// "ObjectID"
0xadfc6c  ldc.i4.s 0xC
0xadfc6e  ldc.i4.s 0x64
0xadfc70  ldc.i4.0
0xadfc71  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, int32 size, bool nullable)
0xadfc76  stelem.ref
0xadfc77  ldloc.s  0x28
0xadfc79  ldc.i4.2
0xadfc7a  ldstr    aInserttime// "InsertTime"
0xadfc7f  ldc.i4.4
0xadfc80  ldc.i4.0
0xadfc81  ldstr    aGetutcdate_0// "GETUTCDate()"
0xadfc86  ldstr    aDfMsscrawllink// "DF_MSSCrawlLinks_InsertTime"
0xadfc8b  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable, string defaultExpression, string defaultConstraintName)
0xadfc90  stelem.ref
0xadfc91  ldloc.s  0x28
0xadfc93  callvirt instance class Microsoft.SharePoint.Utilities.Sql.Table Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddTable(string name, valuetype Microsoft.SharePoint.Utilities.Sql.PartitionOptions partOptions, valuetype Microsoft.SharePoint.Utilities.Sql.LargeValueTypesOffRowOption blobValues, string partitionKeyCol, class Microsoft.SharePoint.Utilities.Sql.Column[] columns)
0xadfc98  stloc.s  5
0xadfc9a  ldloc.0
0xadfc9b  ldstr    aIxMsscrawllink// "IX_MSSCrawlLinks_ParentTransactionID_Ob"...
0xadfca0  ldloc.s  5
0xadfca2  ldc.i4.3
0xadfca3  ldc.i4.2
0xadfca4  newarr   [mscorlib]System.String
0xadfca9  stloc.s  0x29
0xadfcab  ldloc.s  0x29
0xadfcad  ldc.i4.0
0xadfcae  ldstr    aParenttransact// "ParentTransactionID"
0xadfcb3  stelem.ref
0xadfcb4  ldloc.s  0x29
0xadfcb6  ldc.i4.1
0xadfcb7  ldstr    aObjectid_3// "ObjectID"
0xadfcbc  stelem.ref
0xadfcbd  ldloc.s  0x29
0xadfcbf  callvirt instance class Microsoft.SharePoint.Utilities.Sql.Index Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddIndex(string idxName, class Microsoft.SharePoint.Utilities.Sql.Table tbl, valuetype Microsoft.SharePoint.Utilities.Sql.IndexType type, string[] cols)
0xadfcc4  stloc.s  6
0xadfcc6  ldloc.0
0xadfcc7  ldstr    aIxMsscrawllink_0// "IX_MSSCrawlLinks_InsertTime"
0xadfccc  ldloc.s  5
0xadfcce  ldc.i4.4
0xadfccf  ldc.i4.2
0xadfcd0  ldc.i4.1
0xadfcd1  newarr   [mscorlib]System.String
0xadfcd6  stloc.s  0x2A
0xadfcd8  ldloc.s  0x2A
0xadfcda  ldc.i4.0
0xadfcdb  ldstr    aInserttime// "InsertTime"
0xadfce0  stelem.ref
0xadfce1  ldloc.s  0x2A
0xadfce3  callvirt instance class Microsoft.SharePoint.Utilities.Sql.Index Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddIndex(string idxName, class Microsoft.SharePoint.Utilities.Sql.Table tbl, valuetype Microsoft.SharePoint.Utilities.Sql.IndexType type, valuetype Microsoft.SharePoint.Utilities.Sql.FillFactor fillfactor, string[] cols)
0xadfce8  stloc.s  7
0xadfcea  ldloc.0
0xadfceb  ldstr    aTvfMsscrawllin// "TVF_MSSCrawlLinks_ParentTransactionID_O"...
0xadfcf0  ldloc.s  6
0xadfcf2  ldc.i4.0
0xadfcf3  ldc.i4.2
0xadfcf4  newarr   Microsoft.SharePoint.Utilities.Sql.Restriction
0xadfcf9  stloc.s  0x2B
0xadfcfb  ldloc.s  0x2B
0xadfcfd  ldc.i4.0
0xadfcfe  ldstr    aParenttransact// "ParentTransactionID"
0xadfd03  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterRestriction::.ctor(string column)
0xadfd08  stelem.ref
0xadfd09  ldloc.s  0x2B
0xadfd0b  ldc.i4.1
0xadfd0c  ldstr    aObjectid_3// "ObjectID"
0xadfd11  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterRestriction::.ctor(string column)
0xadfd16  stelem.ref
0xadfd17  ldloc.s  0x2B
0xadfd19  callvirt instance void Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddTVF(string tvfName, class Microsoft.SharePoint.Utilities.Sql.Index idx, valuetype LockHint lockHints, class Microsoft.SharePoint.Utilities.Sql.Restriction[] args)
0xadfd1e  ldloc.0
0xadfd1f  ldstr    aTvfMsscrawllin_0// "TVF_MSSCrawlLinks_InsertTime"
0xadfd24  ldloc.s  7
0xadfd26  ldc.i4.0
0xadfd27  ldc.i4.1
0xadfd28  newarr   Microsoft.SharePoint.Utilities.Sql.Restriction
0xadfd2d  stloc.s  0x2C
0xadfd2f  ldloc.s  0x2C
0xadfd31  ldc.i4.0
0xadfd32  ldstr    aInserttime// "InsertTime"
0xadfd37  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterRestriction::.ctor(string column)
0xadfd3c  stelem.ref
0xadfd3d  ldloc.s  0x2C
0xadfd3f  callvirt instance void Microsoft.SharePoint.Utilities.Sql.SqlSchema::AddTVF(string tvfName, class Microsoft.SharePoint.Utilities.Sql.Index idx, valuetype LockHint lockHints, class Microsoft.SharePoint.Utilities.Sql.Restriction[] args)
0xadfd44  ldloc.0
0xadfd45  ldstr    aMsscrawlqueue// "MSSCrawlQueue"
0xadfd4a  ldc.i4.0
0xadfd4b  ldc.i4.2
0xadfd4c  ldnull
0xadfd4d  ldc.i4.s 0xC
0xadfd4f  newarr   Microsoft.SharePoint.Utilities.Sql.Column
0xadfd54  stloc.s  0x2D
0xadfd56  ldloc.s  0x2D
0xadfd58  ldc.i4.0
0xadfd59  ldstr    aSeqid// "SeqID"
0xadfd5e  ldc.i4.0
0xadfd5f  ldstr    a11_4// "1,1"
0xadfd64  ldc.i4.0
0xadfd65  newobj   instance void Microsoft.SharePoint.Utilities.Sql.IdentityColumn::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type, string initVals, bool nullable)
0xadfd6a  stelem.ref
0xadfd6b  ldloc.s  0x2D
0xadfd6d  ldc.i4.1
0xadfd6e  ldstr    aDocid_4// "DocID"
0xadfd73  ldc.i4.0
0xadfd74  ldc.i4.0
0xadfd75  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xadfd7a  stelem.ref
0xadfd7b  ldloc.s  0x2D
0xadfd7d  ldc.i4.2
0xadfd7e  ldstr    aSiteid_3// "SiteID"
0xadfd83  ldc.i4.s 0xE
0xadfd85  ldc.i4.0
0xadfd86  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xadfd8b  stelem.ref
0xadfd8c  ldloc.s  0x2D
0xadfd8e  ldc.i4.3
0xadfd8f  ldstr    aTransactionfla// "TransactionFlags"
0xadfd94  ldc.i4.8
0xadfd95  ldc.i4.0
0xadfd96  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xadfd9b  stelem.ref
0xadfd9c  ldloc.s  0x2D
0xadfd9e  ldc.i4.4
0xadfd9f  ldstr    aBatchid_1// "BatchID"
0xadfda4  ldc.i4.0
0xadfda5  ldc.i4.0
0xadfda6  ldstr    a0// "0"
0xadfdab  ldstr    aDfMsscrawlqueu// "DF_MSSCrawlQueue_BatchID"
0xadfdb0  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable, string defaultExpression, string defaultConstraintName)
0xadfdb5  stelem.ref
0xadfdb6  ldloc.s  0x2D
0xadfdb8  ldc.i4.5
0xadfdb9  ldstr    aDeletereason// "DeleteReason"
0xadfdbe  ldc.i4.s 0x14
0xadfdc0  ldc.i4.0
0xadfdc1  ldstr    a0// "0"
0xadfdc6  ldstr    aDfMsscrawlqueu_0// "DF_MSSCrawlQueue_DeleteReason"
0xadfdcb  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable, string defaultExpression, string defaultConstraintName)
0xadfdd0  stelem.ref
0xadfdd1  ldloc.s  0x2D
0xadfdd3  ldc.i4.6
0xadfdd4  ldstr    aCachedblob// "CachedBlob"
0xadfdd9  ldc.i4.s 0x15
0xadfddb  ldc.i4.m1
0xadfddc  ldc.i4.1
0xadfddd  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, int32 size, bool nullable)
0xadfde2  stelem.ref
0xadfde3  ldloc.s  0x2D
0xadfde5  ldc.i4.7
0xadfde6  ldstr    aRecovered// "Recovered"
0xadfdeb  ldc.i4.2
0xadfdec  ldc.i4.0
0xadfded  ldstr    a0// "0"
0xadfdf2  ldstr    aDfMsscrawllink_0// "DF_MSSCrawlLinks_Recovered"
0xadfdf7  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable, string defaultExpression, string defaultConstraintName)
0xadfdfc  stelem.ref
0xadfdfd  ldloc.s  0x2D
0xadfdff  ldc.i4.8
0xadfe00  ldstr    aChangetime_0// "ChangeTime"
0xadfe05  ldc.i4.4
0xadfe06  ldc.i4.1
0xadfe07  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xadfe0c  stelem.ref
0xadfe0d  ldloc.s  0x2D
0xadfe0f  ldc.i4.s 9
0xadfe11  ldstr    aChangeretrieve// "ChangeRetrievedTime"
0xadfe16  ldc.i4.4
0xadfe17  ldc.i4.1
0xadfe18  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
  ... truncated ...
```
