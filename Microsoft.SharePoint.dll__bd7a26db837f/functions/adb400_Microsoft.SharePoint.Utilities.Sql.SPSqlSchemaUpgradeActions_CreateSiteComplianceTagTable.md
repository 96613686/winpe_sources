# Microsoft.SharePoint.Utilities.Sql.SPSqlSchemaUpgradeActions::CreateSiteComplianceTagTable

- ea: `0xadb400`
- end: `0xadb5bb`
- name: `Microsoft.SharePoint.Utilities.Sql.SPSqlSchemaUpgradeActions::CreateSiteComplianceTagTable`
- size: `443`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0xadb3f0`

## callees

- `0x95e370`
- `0x95e520`
- `0x95f500`
- `0x95f510`
- `0x95f9f0`
- `0x95fda0`
- `0x95fdb0`
- `0x960270`
- `0x960760`
- `0x960f00`

## string_xrefs

- `0xadb52f`: `Deleted`
- `0xadb426`: `ComplianceTag`
- `0xadb479`: `ComplianceTag`
- `0xadb50d`: `ComplianceTag`
- `0xadb400`: `SiteComplianceTag`
- `0xadb43b`: `IsComplianceTagDeleted`
- `0xadb4ab`: `IsComplianceTagDeleted`
- `0xadb542`: `IsComplianceTagDeleted`
- `0xadb57c`: `IsComplianceTagDeleted`
- `0xadb44a`: `IsComplianceTagBlockDeletion`
- `0xadb4bd`: `IsComplianceTagBlockDeletion`
- `0xadb59d`: `IsComplianceTagBlockDeletion`
- `0xadb45e`: `SiteComplianceTag_CI`
- `0xadb499`: `SiteComplianceTag_NCI`
- `0xadb4e3`: `TVF_SiteComplianceTag_CI`
- `0xadb52a`: `TVF_SiteComplianceTag_Deleted`
- `0xadb564`: `TVF_SiteComplianceTag_SiteId_BlockDeletion`

## pseudocode

```c

```

## disassembly

```asm
0xadb400  ldstr    aSitecompliance// "SiteComplianceTag"
0xadb405  ldc.i4.s 9
0xadb407  ldc.i4.0
0xadb408  ldstr    aSiteid_0// "SiteId"
0xadb40d  ldc.i4.4
0xadb40e  newarr   Microsoft.SharePoint.Utilities.Sql.Column
0xadb413  stloc.3
0xadb414  ldloc.3
0xadb415  ldc.i4.0
0xadb416  ldstr    aSiteid_0// "SiteId"
0xadb41b  ldc.i4.s 0xE
0xadb41d  ldc.i4.0
0xadb41e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xadb423  stelem.ref
0xadb424  ldloc.3
0xadb425  ldc.i4.1
0xadb426  ldstr    aCompliancetag_1// "ComplianceTag"
0xadb42b  ldc.i4.s 0xC
0xadb42d  ldc.i4   0x1F4
0xadb432  ldc.i4.0
0xadb433  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, int32 size, bool nullable)
0xadb438  stelem.ref
0xadb439  ldloc.3
0xadb43a  ldc.i4.2
0xadb43b  ldstr    aIscomplianceta// "IsComplianceTagDeleted"
0xadb440  ldc.i4.2
0xadb441  ldc.i4.0
0xadb442  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xadb447  stelem.ref
0xadb448  ldloc.3
0xadb449  ldc.i4.3
0xadb44a  ldstr    aIscomplianceta_0// "IsComplianceTagBlockDeletion"
0xadb44f  ldc.i4.2
0xadb450  ldc.i4.0
0xadb451  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xadb456  stelem.ref
0xadb457  ldloc.3
0xadb458  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Table::.ctor(string name, valuetype Microsoft.SharePoint.Utilities.Sql.PartitionOptions partOpts, valuetype Microsoft.SharePoint.Utilities.Sql.LargeValueTypesOffRowOption blobsOffRow, string partitionKeyCol, class Microsoft.SharePoint.Utilities.Sql.Column[] columns)
0xadb45d  stloc.0
0xadb45e  ldstr    aSitecompliance_0// "SiteComplianceTag_CI"
0xadb463  ldloc.0
0xadb464  ldc.i4.3
0xadb465  ldc.i4.2
0xadb466  newarr   [mscorlib]System.String
0xadb46b  stloc.s  4
0xadb46d  ldloc.s  4
0xadb46f  ldc.i4.0
0xadb470  ldstr    aSiteid_0// "SiteId"
0xadb475  stelem.ref
0xadb476  ldloc.s  4
0xadb478  ldc.i4.1
0xadb479  ldstr    aCompliancetag_1// "ComplianceTag"
0xadb47e  stelem.ref
0xadb47f  ldloc.s  4
0xadb481  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Index::.ctor(string name, class Microsoft.SharePoint.Utilities.Sql.Table table, valuetype Microsoft.SharePoint.Utilities.Sql.IndexType type, string[] columns)
0xadb486  stloc.1
0xadb487  ldloc.0
0xadb488  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.Index> Microsoft.SharePoint.Utilities.Sql.Table::get_Indicies()
0xadb48d  ldloc.1
0xadb48e  callvirt instance string Microsoft.SharePoint.Utilities.Sql.Index::get_Name()
0xadb493  ldloc.1
0xadb494  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.Index>::Add(var<u1>, !!T0)
0xadb499  ldstr    aSitecompliance_1// "SiteComplianceTag_NCI"
0xadb49e  ldloc.0
0xadb49f  ldc.i4.4
0xadb4a0  ldc.i4.3
0xadb4a1  newarr   [mscorlib]System.String
0xadb4a6  stloc.s  5
0xadb4a8  ldloc.s  5
0xadb4aa  ldc.i4.0
0xadb4ab  ldstr    aIscomplianceta// "IsComplianceTagDeleted"
0xadb4b0  stelem.ref
0xadb4b1  ldloc.s  5
0xadb4b3  ldc.i4.1
0xadb4b4  ldstr    aSiteid_0// "SiteId"
0xadb4b9  stelem.ref
0xadb4ba  ldloc.s  5
0xadb4bc  ldc.i4.2
0xadb4bd  ldstr    aIscomplianceta_0// "IsComplianceTagBlockDeletion"
0xadb4c2  stelem.ref
0xadb4c3  ldloc.s  5
0xadb4c5  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Index::.ctor(string name, class Microsoft.SharePoint.Utilities.Sql.Table table, valuetype Microsoft.SharePoint.Utilities.Sql.IndexType type, string[] columns)
0xadb4ca  stloc.2
0xadb4cb  ldloc.0
0xadb4cc  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.Index> Microsoft.SharePoint.Utilities.Sql.Table::get_Indicies()
0xadb4d1  ldloc.2
0xadb4d2  callvirt instance string Microsoft.SharePoint.Utilities.Sql.Index::get_Name()
0xadb4d7  ldloc.2
0xadb4d8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.Index>::Add(var<u1>, !!T0)
0xadb4dd  ldloc.0
0xadb4de  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF> Microsoft.SharePoint.Utilities.Sql.Table::get_TVFs()
0xadb4e3  ldstr    aTvfSitecomplia// "TVF_SiteComplianceTag_CI"
0xadb4e8  ldstr    aCi_1// "CI"
0xadb4ed  ldloc.1
0xadb4ee  ldc.i4   0x81
0xadb4f3  ldc.i4.2
0xadb4f4  ldc.i4.2
0xadb4f5  newarr   Microsoft.SharePoint.Utilities.Sql.Restriction
0xadb4fa  stloc.s  6
0xadb4fc  ldloc.s  6
0xadb4fe  ldc.i4.0
0xadb4ff  ldstr    aSiteid_0// "SiteId"
0xadb504  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterRestriction::.ctor(string column)
0xadb509  stelem.ref
0xadb50a  ldloc.s  6
0xadb50c  ldc.i4.1
0xadb50d  ldstr    aCompliancetag_1// "ComplianceTag"
0xadb512  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterRestriction::.ctor(string column)
0xadb517  stelem.ref
0xadb518  ldloc.s  6
0xadb51a  newobj   instance void Microsoft.SharePoint.Utilities.Sql.TVF::.ctor(string functionSuffix, class Microsoft.SharePoint.Utilities.Sql.Index index, valuetype LockHint lockHints, valuetype Microsoft.SharePoint.Utilities.Sql.ForceSeekOptions fsOption, class Microsoft.SharePoint.Utilities.Sql.Restriction[] restrictions)
0xadb51f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF>::Add(var<u1>, !!T0)
0xadb524  ldloc.0
0xadb525  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF> Microsoft.SharePoint.Utilities.Sql.Table::get_TVFs()
0xadb52a  ldstr    aTvfSitecomplia_0// "TVF_SiteComplianceTag_Deleted"
0xadb52f  ldstr    aDeleted_0// "Deleted"
0xadb534  ldloc.2
0xadb535  ldc.i4.1
0xadb536  ldc.i4.2
0xadb537  ldc.i4.1
0xadb538  newarr   Microsoft.SharePoint.Utilities.Sql.Restriction
0xadb53d  stloc.s  7
0xadb53f  ldloc.s  7
0xadb541  ldc.i4.0
0xadb542  ldstr    aIscomplianceta// "IsComplianceTagDeleted"
0xadb547  ldstr    aConvertBit1_0// "CONVERT(bit, 1)"
0xadb54c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ConstantRestriction::.ctor(string column, string constant)
0xadb551  stelem.ref
0xadb552  ldloc.s  7
0xadb554  newobj   instance void Microsoft.SharePoint.Utilities.Sql.TVF::.ctor(string functionSuffix, class Microsoft.SharePoint.Utilities.Sql.Index index, valuetype LockHint lockHints, valuetype Microsoft.SharePoint.Utilities.Sql.ForceSeekOptions fsOption, class Microsoft.SharePoint.Utilities.Sql.Restriction[] restrictions)
0xadb559  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF>::Add(var<u1>, !!T0)
0xadb55e  ldloc.0
0xadb55f  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF> Microsoft.SharePoint.Utilities.Sql.Table::get_TVFs()
0xadb564  ldstr    aTvfSitecomplia_1// "TVF_SiteComplianceTag_SiteId_BlockDelet"...
0xadb569  ldstr    aSiteidBlockdel// "SiteId_BlockDeletion"
0xadb56e  ldloc.2
0xadb56f  ldc.i4.0
0xadb570  ldc.i4.2
0xadb571  ldc.i4.3
0xadb572  newarr   Microsoft.SharePoint.Utilities.Sql.Restriction
0xadb577  stloc.s  8
0xadb579  ldloc.s  8
0xadb57b  ldc.i4.0
0xadb57c  ldstr    aIscomplianceta// "IsComplianceTagDeleted"
0xadb581  ldstr    aConvertBit0// "CONVERT(bit, 0)"
0xadb586  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ConstantRestriction::.ctor(string column, string constant)
0xadb58b  stelem.ref
0xadb58c  ldloc.s  8
0xadb58e  ldc.i4.1
0xadb58f  ldstr    aSiteid_0// "SiteId"
0xadb594  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterRestriction::.ctor(string column)
0xadb599  stelem.ref
0xadb59a  ldloc.s  8
0xadb59c  ldc.i4.2
0xadb59d  ldstr    aIscomplianceta_0// "IsComplianceTagBlockDeletion"
0xadb5a2  ldstr    aConvertBit1_0// "CONVERT(bit, 1)"
0xadb5a7  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ConstantRestriction::.ctor(string column, string constant)
0xadb5ac  stelem.ref
0xadb5ad  ldloc.s  8
0xadb5af  newobj   instance void Microsoft.SharePoint.Utilities.Sql.TVF::.ctor(string functionSuffix, class Microsoft.SharePoint.Utilities.Sql.Index index, valuetype LockHint lockHints, valuetype Microsoft.SharePoint.Utilities.Sql.ForceSeekOptions fsOption, class Microsoft.SharePoint.Utilities.Sql.Restriction[] restrictions)
0xadb5b4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF>::Add(var<u1>, !!T0)
0xadb5b9  ldloc.0
0xadb5ba  ret
```
