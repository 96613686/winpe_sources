# Microsoft.SharePoint.Utilities.Sql.SPAppManagementSqlSchemaUpgradeActions::CreateApprovedAppsTable

- ea: `0xabe6d0`
- end: `0xabe8be`
- name: `Microsoft.SharePoint.Utilities.Sql.SPAppManagementSqlSchemaUpgradeActions::CreateApprovedAppsTable`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0xabe2c0`

## callees

- `0x95e370`
- `0x95e520`
- `0x95f500`
- `0x95f510`
- `0x95f9f0`
- `0x95fda0`
- `0x95fdb0`
- `0x960270`
- `0x960ed0`
- `0x960f30`

## string_xrefs

- `0xabe6e1`: `CompositePartitionKey`
- `0xabe76e`: `CompositePartitionKey`
- `0xabe785`: `CompositePartitionKey`
- `0xabe7c5`: `CompositePartitionKey`
- `0xabe81a`: `CompositePartitionKey`
- `0xabe862`: `CompositePartitionKey`
- `0xabe893`: `CompositePartitionKey`
- `0xabe8a5`: `CompositePartitionKey`
- `0xabe758`: `PermissionXml`
- `0xabe797`: `AM_ApprovedApps_CompositePartitionKey_Id`
- `0xabe7d8`: `AM_ApprovedApps_CompositePartitionKey_ProductId`
- `0xabe802`: `TVF_AM_ApprovedApps_CompositePartitionKey_Id`
- `0xabe808`: `CompositePartitionKey_Id`
- `0xabe845`: `TVF_AM_ApprovedApps_CompositePartitionKey_ProductId`
- `0xabe84b`: `CompositePartitionKey_ProductId`
- `0xabe88d`: `TVF_AM_ApprovedApps_CompositePartitionKey`

## pseudocode

```c

```

## disassembly

```asm
0xabe6d0  ldstr    aAmApprovedapps// "AM_ApprovedApps"
0xabe6d5  stloc.0
0xabe6d6  ldc.i4.7
0xabe6d7  newarr   Microsoft.SharePoint.Utilities.Sql.Column
0xabe6dc  stloc.s  7
0xabe6de  ldloc.s  7
0xabe6e0  ldc.i4.0
0xabe6e1  ldstr    aCompositeparti_2// "CompositePartitionKey"
0xabe6e6  ldc.i4.s 0x15
0xabe6e8  ldc.i4   0x211
0xabe6ed  ldc.i4.0
0xabe6ee  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, int32 size, bool nullable)
0xabe6f3  stelem.ref
0xabe6f4  ldloc.s  7
0xabe6f6  ldc.i4.1
0xabe6f7  ldstr    aId_2// "Id"
0xabe6fc  ldc.i4.s 0xE
0xabe6fe  ldc.i4.0
0xabe6ff  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xabe704  stelem.ref
0xabe705  ldloc.s  7
0xabe707  ldc.i4.2
0xabe708  ldstr    aProductid_0// "ProductId"
0xabe70d  ldc.i4.s 0xE
0xabe70f  ldc.i4.0
0xabe710  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xabe715  stelem.ref
0xabe716  ldloc.s  7
0xabe718  ldc.i4.3
0xabe719  ldstr    aAssetid_1// "AssetId"
0xabe71e  ldc.i4.s 0xC
0xabe720  ldc.i4.s 0xE
0xabe722  ldc.i4.1
0xabe723  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, int32 size, bool nullable)
0xabe728  stelem.ref
0xabe729  ldloc.s  7
0xabe72b  ldc.i4.4
0xabe72c  ldstr    aTitle_0// "Title"
0xabe731  ldc.i4.s 0xC
0xabe733  ldc.i4   0x200
0xabe738  ldc.i4.0
0xabe739  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, int32 size, bool nullable)
0xabe73e  stelem.ref
0xabe73f  ldloc.s  7
0xabe741  ldc.i4.5
0xabe742  ldstr    aJustification_1// "Justification"
0xabe747  ldc.i4.s 0xC
0xabe749  ldc.i4   0x200
0xabe74e  ldc.i4.0
0xabe74f  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, int32 size, bool nullable)
0xabe754  stelem.ref
0xabe755  ldloc.s  7
0xabe757  ldc.i4.6
0xabe758  ldstr    aPermissionxml_1// "PermissionXml"
0xabe75d  ldc.i4.s 0xC
0xabe75f  ldc.i4.m1
0xabe760  ldc.i4.0
0xabe761  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, int32 size, bool nullable)
0xabe766  stelem.ref
0xabe767  ldloc.s  7
0xabe769  stloc.1
0xabe76a  ldloc.0
0xabe76b  ldc.i4.s 9
0xabe76d  ldc.i4.2
0xabe76e  ldstr    aCompositeparti_2// "CompositePartitionKey"
0xabe773  ldloc.1
0xabe774  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Table::.ctor(string name, valuetype Microsoft.SharePoint.Utilities.Sql.PartitionOptions partOpts, valuetype Microsoft.SharePoint.Utilities.Sql.LargeValueTypesOffRowOption blobsOffRow, string partitionKeyCol, class Microsoft.SharePoint.Utilities.Sql.Column[] columns)
0xabe779  stloc.2
0xabe77a  ldc.i4.2
0xabe77b  newarr   [mscorlib]System.String
0xabe780  stloc.s  8
0xabe782  ldloc.s  8
0xabe784  ldc.i4.0
0xabe785  ldstr    aCompositeparti_2// "CompositePartitionKey"
0xabe78a  stelem.ref
0xabe78b  ldloc.s  8
0xabe78d  ldc.i4.1
0xabe78e  ldstr    aId_2// "Id"
0xabe793  stelem.ref
0xabe794  ldloc.s  8
0xabe796  stloc.3
0xabe797  ldstr    aAmApprovedapps_0// "AM_ApprovedApps_CompositePartitionKey_I"...
0xabe79c  ldloc.2
0xabe79d  ldc.i4.0
0xabe79e  ldloc.3
0xabe79f  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Index::.ctor(string name, class Microsoft.SharePoint.Utilities.Sql.Table table, valuetype Microsoft.SharePoint.Utilities.Sql.IndexType type, string[] columns)
0xabe7a4  stloc.s  4
0xabe7a6  ldloc.2
0xabe7a7  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.Index> Microsoft.SharePoint.Utilities.Sql.Table::get_Indicies()
0xabe7ac  ldloc.s  4
0xabe7ae  callvirt instance string Microsoft.SharePoint.Utilities.Sql.Index::get_Name()
0xabe7b3  ldloc.s  4
0xabe7b5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.Index>::Add(var<u1>, !!T0)
0xabe7ba  ldc.i4.2
0xabe7bb  newarr   [mscorlib]System.String
0xabe7c0  stloc.s  9
0xabe7c2  ldloc.s  9
0xabe7c4  ldc.i4.0
0xabe7c5  ldstr    aCompositeparti_2// "CompositePartitionKey"
0xabe7ca  stelem.ref
0xabe7cb  ldloc.s  9
0xabe7cd  ldc.i4.1
0xabe7ce  ldstr    aProductid_0// "ProductId"
0xabe7d3  stelem.ref
0xabe7d4  ldloc.s  9
0xabe7d6  stloc.s  5
0xabe7d8  ldstr    aAmApprovedapps_1// "AM_ApprovedApps_CompositePartitionKey_P"...
0xabe7dd  ldloc.2
0xabe7de  ldc.i4.5
0xabe7df  ldloc.s  5
0xabe7e1  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Index::.ctor(string name, class Microsoft.SharePoint.Utilities.Sql.Table table, valuetype Microsoft.SharePoint.Utilities.Sql.IndexType type, string[] columns)
0xabe7e6  stloc.s  6
0xabe7e8  ldloc.2
0xabe7e9  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.Index> Microsoft.SharePoint.Utilities.Sql.Table::get_Indicies()
0xabe7ee  ldloc.s  6
0xabe7f0  callvirt instance string Microsoft.SharePoint.Utilities.Sql.Index::get_Name()
0xabe7f5  ldloc.s  6
0xabe7f7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.Index>::Add(var<u1>, !!T0)
0xabe7fc  ldloc.2
0xabe7fd  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF> Microsoft.SharePoint.Utilities.Sql.Table::get_TVFs()
0xabe802  ldstr    aTvfAmApproveda// "TVF_AM_ApprovedApps_CompositePartitionK"...
0xabe807  ldloc.0
0xabe808  ldstr    aCompositeparti_5// "CompositePartitionKey_Id"
0xabe80d  ldloc.s  4
0xabe80f  ldc.i4.2
0xabe810  newarr   Microsoft.SharePoint.Utilities.Sql.Restriction
0xabe815  stloc.s  0xA
0xabe817  ldloc.s  0xA
0xabe819  ldc.i4.0
0xabe81a  ldstr    aCompositeparti_2// "CompositePartitionKey"
0xabe81f  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterRestriction::.ctor(string column)
0xabe824  stelem.ref
0xabe825  ldloc.s  0xA
0xabe827  ldc.i4.1
0xabe828  ldstr    aId_2// "Id"
0xabe82d  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterRestriction::.ctor(string column)
0xabe832  stelem.ref
0xabe833  ldloc.s  0xA
0xabe835  newobj   instance void Microsoft.SharePoint.Utilities.Sql.TVF::.ctor(string functionBase, string functionSuffix, class Microsoft.SharePoint.Utilities.Sql.Index index, class Microsoft.SharePoint.Utilities.Sql.Restriction[] restrictions)
0xabe83a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF>::Add(var<u1>, !!T0)
0xabe83f  ldloc.2
0xabe840  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF> Microsoft.SharePoint.Utilities.Sql.Table::get_TVFs()
0xabe845  ldstr    aTvfAmApproveda_0// "TVF_AM_ApprovedApps_CompositePartitionK"...
0xabe84a  ldloc.0
0xabe84b  ldstr    aCompositeparti_6// "CompositePartitionKey_ProductId"
0xabe850  ldloc.s  6
0xabe852  ldc.i4   0x80
0xabe857  ldc.i4.2
0xabe858  newarr   Microsoft.SharePoint.Utilities.Sql.Restriction
0xabe85d  stloc.s  0xB
0xabe85f  ldloc.s  0xB
0xabe861  ldc.i4.0
0xabe862  ldstr    aCompositeparti_2// "CompositePartitionKey"
0xabe867  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterRestriction::.ctor(string column)
0xabe86c  stelem.ref
0xabe86d  ldloc.s  0xB
0xabe86f  ldc.i4.1
0xabe870  ldstr    aProductid_0// "ProductId"
0xabe875  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterRestriction::.ctor(string column)
0xabe87a  stelem.ref
0xabe87b  ldloc.s  0xB
0xabe87d  newobj   instance void Microsoft.SharePoint.Utilities.Sql.TVF::.ctor(string functionBase, string functionSuffix, class Microsoft.SharePoint.Utilities.Sql.Index index, valuetype LockHint lockHints, class Microsoft.SharePoint.Utilities.Sql.Restriction[] restrictions)
0xabe882  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF>::Add(var<u1>, !!T0)
0xabe887  ldloc.2
0xabe888  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF> Microsoft.SharePoint.Utilities.Sql.Table::get_TVFs()
0xabe88d  ldstr    aTvfAmApproveda_1// "TVF_AM_ApprovedApps_CompositePartitionK"...
0xabe892  ldloc.0
0xabe893  ldstr    aCompositeparti_2// "CompositePartitionKey"
0xabe898  ldloc.s  4
0xabe89a  ldc.i4.1
0xabe89b  newarr   Microsoft.SharePoint.Utilities.Sql.Restriction
0xabe8a0  stloc.s  0xC
0xabe8a2  ldloc.s  0xC
0xabe8a4  ldc.i4.0
0xabe8a5  ldstr    aCompositeparti_2// "CompositePartitionKey"
0xabe8aa  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterRestriction::.ctor(string column)
0xabe8af  stelem.ref
0xabe8b0  ldloc.s  0xC
0xabe8b2  newobj   instance void Microsoft.SharePoint.Utilities.Sql.TVF::.ctor(string functionBase, string functionSuffix, class Microsoft.SharePoint.Utilities.Sql.Index index, class Microsoft.SharePoint.Utilities.Sql.Restriction[] restrictions)
0xabe8b7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF>::Add(var<u1>, !!T0)
0xabe8bc  ldloc.2
0xabe8bd  ret
```
