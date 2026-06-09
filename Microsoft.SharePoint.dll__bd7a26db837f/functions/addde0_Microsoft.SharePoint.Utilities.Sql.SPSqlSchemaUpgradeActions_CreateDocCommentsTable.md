# Microsoft.SharePoint.Utilities.Sql.SPSqlSchemaUpgradeActions::CreateDocCommentsTable

- ea: `0xaddde0`
- end: `0xade296`
- name: `Microsoft.SharePoint.Utilities.Sql.SPSqlSchemaUpgradeActions::CreateDocCommentsTable`
- size: `1206`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0xaddd30`

## callees

- `0x95e370`
- `0x95e540`
- `0x95f500`
- `0x95f510`
- `0x95f9f0`
- `0x95fda0`
- `0x95fdb0`
- `0x960270`
- `0x9602b0`
- `0x960530`
- `0x960f00`

## string_xrefs

- `0xadde50`: `Created`
- `0xaddfab`: `Created`
- `0xade12f`: `Created`
- `0xade17b`: `Created`
- `0xaddee8`: `DocComments`
- `0xaddefc`: `DocComments_CI`
- `0xaddf38`: `DocComments_ParentIdLatestReplyId`
- `0xaddf7d`: `DocComments_ParentIdCreatedId`
- `0xaddfc3`: `DocComments_Id`
- `0xade0b2`: `TVF_DocComments_ParentIdLEQLatestReply`
- `0xade0fd`: `TVF_DocComments_ParentIdGEQLatestReply`
- `0xade109`: `ParentIdLEQCreated`
- `0xade149`: `TVF_DocComments_ParentIdLEQCreated`
- `0xade155`: `ParentIdGEQCreated`
- `0xade195`: `TVF_DocComments_ParentIdGEQCreated`
- `0xade1d6`: `TVF_DocComments_ParentId`
- `0xade218`: `TVF_DocComments_Id`
- `0xade253`: `TVF_DocComments_SiteIdDocId`
- `0xade288`: `TVF_DocComments_SiteId`

## pseudocode

```c

```

## disassembly

```asm
0xaddde0  ldc.i4.s 0xF
0xaddde2  newarr   Microsoft.SharePoint.Utilities.Sql.Column
0xaddde7  stloc.s  0x12
0xaddde9  ldloc.s  0x12
0xadddeb  ldc.i4.0
0xadddec  ldstr    aSiteid_0// "SiteId"
0xadddf1  ldc.i4.s 0xE
0xadddf3  ldc.i4.0
0xadddf4  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xadddf9  stelem.ref
0xadddfa  ldloc.s  0x12
0xadddfc  ldc.i4.1
0xadddfd  ldstr    aDocid_0// "DocId"
0xadde02  ldc.i4.s 0xE
0xadde04  ldc.i4.0
0xadde05  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xadde0a  stelem.ref
0xadde0b  ldloc.s  0x12
0xadde0d  ldc.i4.2
0xadde0e  ldstr    aParentid_2// "ParentId"
0xadde13  ldc.i4.8
0xadde14  ldc.i4.0
0xadde15  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xadde1a  stelem.ref
0xadde1b  ldloc.s  0x12
0xadde1d  ldc.i4.3
0xadde1e  ldstr    aId_2// "Id"
0xadde23  ldc.i4.8
0xadde24  ldc.i4.0
0xadde25  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xadde2a  stelem.ref
0xadde2b  ldloc.s  0x12
0xadde2d  ldc.i4.4
0xadde2e  ldstr    aText_2// "Text"
0xadde33  ldc.i4.s 0x15
0xadde35  ldc.i4.m1
0xadde36  ldc.i4.0
0xadde37  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, int32 size, bool nullable)
0xadde3c  stelem.ref
0xadde3d  ldloc.s  0x12
0xadde3f  ldc.i4.5
0xadde40  ldstr    aUserid_0// "UserId"
0xadde45  ldc.i4.8
0xadde46  ldc.i4.0
0xadde47  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xadde4c  stelem.ref
0xadde4d  ldloc.s  0x12
0xadde4f  ldc.i4.6
0xadde50  ldstr    aCreated_0// "Created"
0xadde55  ldc.i4.4
0xadde56  ldc.i4.0
0xadde57  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xadde5c  stelem.ref
0xadde5d  ldloc.s  0x12
0xadde5f  ldc.i4.7
0xadde60  ldstr    aLatestreplydat// "LatestReplyDate"
0xadde65  ldc.i4.4
0xadde66  ldc.i4.0
0xadde67  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xadde6c  stelem.ref
0xadde6d  ldloc.s  0x12
0xadde6f  ldc.i4.8
0xadde70  ldstr    aUiversion_0// "UIVersion"
0xadde75  ldc.i4.8
0xadde76  ldc.i4.0
0xadde77  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xadde7c  stelem.ref
0xadde7d  ldloc.s  0x12
0xadde7f  ldc.i4.s 9
0xadde81  ldstr    aReplycount// "ReplyCount"
0xadde86  ldc.i4.8
0xadde87  ldc.i4.0
0xadde88  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xadde8d  stelem.ref
0xadde8e  ldloc.s  0x12
0xadde90  ldc.i4.s 0xA
0xadde92  ldstr    aLikecount// "LikeCount"
0xadde97  ldc.i4.8
0xadde98  ldc.i4.0
0xadde99  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xadde9e  stelem.ref
0xadde9f  ldloc.s  0x12
0xaddea1  ldc.i4.s 0xB
0xaddea3  ldstr    aModifiedby// "ModifiedBy"
0xaddea8  ldc.i4.8
0xaddea9  ldc.i4.1
0xaddeaa  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xaddeaf  stelem.ref
0xaddeb0  ldloc.s  0x12
0xaddeb2  ldc.i4.s 0xC
0xaddeb4  ldstr    aModifieddate// "ModifiedDate"
0xaddeb9  ldc.i4.4
0xaddeba  ldc.i4.1
0xaddebb  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xaddec0  stelem.ref
0xaddec1  ldloc.s  0x12
0xaddec3  ldc.i4.s 0xD
0xaddec5  ldstr    aLocation// "Location"
0xaddeca  ldc.i4.s 0xC
0xaddecc  ldc.i4.m1
0xaddecd  ldc.i4.1
0xaddece  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, int32 size, bool nullable)
0xadded3  stelem.ref
0xadded4  ldloc.s  0x12
0xadded6  ldc.i4.s 0xE
0xadded8  ldstr    aSize// "Size"
0xaddedd  ldc.i4.0
0xaddede  ldc.i4.0
0xaddedf  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xaddee4  stelem.ref
0xaddee5  ldloc.s  0x12
0xaddee7  stloc.0
0xaddee8  ldstr    aDoccomments_0// "DocComments"
0xaddeed  ldc.i4.s 9
0xaddeef  ldc.i4.2
0xaddef0  ldstr    aSiteid_0// "SiteId"
0xaddef5  ldloc.0
0xaddef6  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Table::.ctor(string name, valuetype Microsoft.SharePoint.Utilities.Sql.PartitionOptions partOpts, valuetype Microsoft.SharePoint.Utilities.Sql.LargeValueTypesOffRowOption blobsOffRow, string partitionKeyCol, class Microsoft.SharePoint.Utilities.Sql.Column[] columns)
0xaddefb  stloc.1
0xaddefc  ldstr    aDoccommentsCi// "DocComments_CI"
0xaddf01  ldloc.1
0xaddf02  ldc.i4.3
0xaddf03  ldc.i4.2
0xaddf04  ldc.i4.4
0xaddf05  newarr   [mscorlib]System.String
0xaddf0a  stloc.s  0x13
0xaddf0c  ldloc.s  0x13
0xaddf0e  ldc.i4.0
0xaddf0f  ldstr    aSiteid_0// "SiteId"
0xaddf14  stelem.ref
0xaddf15  ldloc.s  0x13
0xaddf17  ldc.i4.1
0xaddf18  ldstr    aDocid_0// "DocId"
0xaddf1d  stelem.ref
0xaddf1e  ldloc.s  0x13
0xaddf20  ldc.i4.2
0xaddf21  ldstr    aParentid_2// "ParentId"
0xaddf26  stelem.ref
0xaddf27  ldloc.s  0x13
0xaddf29  ldc.i4.3
0xaddf2a  ldstr    aId_2// "Id"
0xaddf2f  stelem.ref
0xaddf30  ldloc.s  0x13
0xaddf32  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Index::.ctor(string name, class Microsoft.SharePoint.Utilities.Sql.Table table, valuetype Microsoft.SharePoint.Utilities.Sql.IndexType type, valuetype Microsoft.SharePoint.Utilities.Sql.FillFactor ffactor, string[] columns)
0xaddf37  stloc.2
0xaddf38  ldstr    aDoccommentsPar// "DocComments_ParentIdLatestReplyId"
0xaddf3d  ldloc.1
0xaddf3e  ldc.i4.5
0xaddf3f  ldc.i4.2
0xaddf40  ldc.i4.5
0xaddf41  newarr   [mscorlib]System.String
0xaddf46  stloc.s  0x14
0xaddf48  ldloc.s  0x14
0xaddf4a  ldc.i4.0
0xaddf4b  ldstr    aSiteid_0// "SiteId"
0xaddf50  stelem.ref
0xaddf51  ldloc.s  0x14
0xaddf53  ldc.i4.1
0xaddf54  ldstr    aDocid_0// "DocId"
0xaddf59  stelem.ref
0xaddf5a  ldloc.s  0x14
0xaddf5c  ldc.i4.2
0xaddf5d  ldstr    aParentid_2// "ParentId"
0xaddf62  stelem.ref
0xaddf63  ldloc.s  0x14
0xaddf65  ldc.i4.3
0xaddf66  ldstr    aLatestreplydat// "LatestReplyDate"
0xaddf6b  stelem.ref
0xaddf6c  ldloc.s  0x14
0xaddf6e  ldc.i4.4
0xaddf6f  ldstr    aId_2// "Id"
0xaddf74  stelem.ref
0xaddf75  ldloc.s  0x14
0xaddf77  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Index::.ctor(string name, class Microsoft.SharePoint.Utilities.Sql.Table table, valuetype Microsoft.SharePoint.Utilities.Sql.IndexType type, valuetype Microsoft.SharePoint.Utilities.Sql.FillFactor ffactor, string[] columns)
0xaddf7c  stloc.3
0xaddf7d  ldstr    aDoccommentsPar_0// "DocComments_ParentIdCreatedId"
0xaddf82  ldloc.1
0xaddf83  ldc.i4.5
0xaddf84  ldc.i4.2
0xaddf85  ldc.i4.5
0xaddf86  newarr   [mscorlib]System.String
0xaddf8b  stloc.s  0x15
0xaddf8d  ldloc.s  0x15
0xaddf8f  ldc.i4.0
0xaddf90  ldstr    aSiteid_0// "SiteId"
0xaddf95  stelem.ref
0xaddf96  ldloc.s  0x15
0xaddf98  ldc.i4.1
0xaddf99  ldstr    aDocid_0// "DocId"
0xaddf9e  stelem.ref
0xaddf9f  ldloc.s  0x15
0xaddfa1  ldc.i4.2
0xaddfa2  ldstr    aParentid_2// "ParentId"
0xaddfa7  stelem.ref
0xaddfa8  ldloc.s  0x15
0xaddfaa  ldc.i4.3
0xaddfab  ldstr    aCreated_0// "Created"
0xaddfb0  stelem.ref
0xaddfb1  ldloc.s  0x15
0xaddfb3  ldc.i4.4
0xaddfb4  ldstr    aId_2// "Id"
0xaddfb9  stelem.ref
0xaddfba  ldloc.s  0x15
0xaddfbc  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Index::.ctor(string name, class Microsoft.SharePoint.Utilities.Sql.Table table, valuetype Microsoft.SharePoint.Utilities.Sql.IndexType type, valuetype Microsoft.SharePoint.Utilities.Sql.FillFactor ffactor, string[] columns)
0xaddfc1  stloc.s  4
0xaddfc3  ldstr    aDoccommentsId// "DocComments_Id"
0xaddfc8  ldloc.1
0xaddfc9  ldc.i4.1
0xaddfca  ldc.i4.2
0xaddfcb  ldc.i4.3
0xaddfcc  newarr   [mscorlib]System.String
0xaddfd1  stloc.s  0x16
0xaddfd3  ldloc.s  0x16
0xaddfd5  ldc.i4.0
0xaddfd6  ldstr    aSiteid_0// "SiteId"
0xaddfdb  stelem.ref
0xaddfdc  ldloc.s  0x16
0xaddfde  ldc.i4.1
0xaddfdf  ldstr    aDocid_0// "DocId"
0xaddfe4  stelem.ref
0xaddfe5  ldloc.s  0x16
0xaddfe7  ldc.i4.2
0xaddfe8  ldstr    aId_2// "Id"
0xaddfed  stelem.ref
0xaddfee  ldloc.s  0x16
0xaddff0  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Index::.ctor(string name, class Microsoft.SharePoint.Utilities.Sql.Table table, valuetype Microsoft.SharePoint.Utilities.Sql.IndexType type, valuetype Microsoft.SharePoint.Utilities.Sql.FillFactor ffactor, string[] columns)
0xaddff5  stloc.s  5
0xaddff7  ldloc.1
0xaddff8  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.Index> Microsoft.SharePoint.Utilities.Sql.Table::get_Indicies()
0xaddffd  ldloc.2
0xaddffe  callvirt instance string Microsoft.SharePoint.Utilities.Sql.Index::get_Name()
0xade003  ldloc.2
0xade004  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.Index>::Add(var<u1>, !!T0)
0xade009  ldloc.1
0xade00a  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.Index> Microsoft.SharePoint.Utilities.Sql.Table::get_Indicies()
0xade00f  ldloc.3
0xade010  callvirt instance string Microsoft.SharePoint.Utilities.Sql.Index::get_Name()
0xade015  ldloc.3
0xade016  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.Index>::Add(var<u1>, !!T0)
0xade01b  ldloc.1
0xade01c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.Index> Microsoft.SharePoint.Utilities.Sql.Table::get_Indicies()
0xade021  ldloc.s  4
0xade023  callvirt instance string Microsoft.SharePoint.Utilities.Sql.Index::get_Name()
0xade028  ldloc.s  4
0xade02a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.Index>::Add(var<u1>, !!T0)
0xade02f  ldloc.1
0xade030  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.Index> Microsoft.SharePoint.Utilities.Sql.Table::get_Indicies()
0xade035  ldloc.s  5
0xade037  callvirt instance string Microsoft.SharePoint.Utilities.Sql.Index::get_Name()
0xade03c  ldloc.s  5
0xade03e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.Index>::Add(var<u1>, !!T0)
0xade043  ldstr    aId_2// "Id"
0xade048  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterRestriction::.ctor(string column)
0xade04d  stloc.s  6
0xade04f  ldstr    aSiteid_0// "SiteId"
0xade054  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterRestriction::.ctor(string column)
0xade059  stloc.s  7
0xade05b  ldstr    aDocid_0// "DocId"
0xade060  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterRestriction::.ctor(string column)
0xade065  stloc.s  8
0xade067  ldstr    aParentid_2// "ParentId"
0xade06c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterRestriction::.ctor(string column)
0xade071  stloc.s  9
0xade073  ldstr    aParentidleqlat// "ParentIdLEQLatestReply"
0xade078  ldloc.3
0xade079  ldc.i4.1
0xade07a  ldc.i4.2
0xade07b  ldc.i4.4
0xade07c  newarr   Microsoft.SharePoint.Utilities.Sql.Restriction
0xade081  stloc.s  0x17
0xade083  ldloc.s  0x17
0xade085  ldc.i4.0
0xade086  ldloc.s  7
0xade088  stelem.ref
0xade089  ldloc.s  0x17
0xade08b  ldc.i4.1
0xade08c  ldloc.s  8
0xade08e  stelem.ref
0xade08f  ldloc.s  0x17
0xade091  ldc.i4.2
0xade092  ldloc.s  9
0xade094  stelem.ref
0xade095  ldloc.s  0x17
0xade097  ldc.i4.3
0xade098  ldstr    aLatestreplydat// "LatestReplyDate"
0xade09d  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterLEQRestriction::.ctor(string column)
0xade0a2  stelem.ref
0xade0a3  ldloc.s  0x17
0xade0a5  newobj   instance void Microsoft.SharePoint.Utilities.Sql.TVF::.ctor(string functionSuffix, class Microsoft.SharePoint.Utilities.Sql.Index index, valuetype LockHint lockHints, valuetype Microsoft.SharePoint.Utilities.Sql.ForceSeekOptions fsOption, class Microsoft.SharePoint.Utilities.Sql.Restriction[] restrictions)
0xade0aa  stloc.s  0xA
0xade0ac  ldloc.1
0xade0ad  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF> Microsoft.SharePoint.Utilities.Sql.Table::get_TVFs()
0xade0b2  ldstr    aTvfDoccomments// "TVF_DocComments_ParentIdLEQLatestReply"
0xade0b7  ldloc.s  0xA
0xade0b9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF>::Add(var<u1>, !!T0)
0xade0be  ldstr    aParentidgeqlat// "ParentIdGEQLatestReply"
0xade0c3  ldloc.3
0xade0c4  ldc.i4.1
0xade0c5  ldc.i4.2
0xade0c6  ldc.i4.4
  ... truncated ...
```
