# Microsoft.SharePoint.Utilities.Sql.SPSqlSchemaUpgradeActions::AddDeletedABSBlobTable

- ea: `0xad93a0`
- end: `0xad954a`
- name: `Microsoft.SharePoint.Utilities.Sql.SPSqlSchemaUpgradeActions::AddDeletedABSBlobTable`
- size: `426`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0xa66380`
- `0xabeb10`

## callees

- `0x95e370`
- `0x95e540`
- `0x95f500`
- `0x95f510`
- `0x95f9f0`
- `0x95fda0`
- `0x95fdb0`
- `0x960270`
- `0x9603f0`
- `0x960f00`
- `0x962250`

## string_xrefs

- `0xad93d5`: `ABSId`
- `0xad943a`: `ABSId`
- `0xad94f7`: `ABSId`
- `0xad93a0`: `DeletedABSBlob`
- `0xad93fa`: `DeletedDate`
- `0xad946d`: `DeletedDate`
- `0xad952c`: `DeletedDate`
- `0xad941e`: `DeletedABSBlob_NCI`
- `0xad945a`: `DeletedABSBlob_DeletedDateCI`
- `0xad949c`: `TVF_DeletedABSBlob_Site`
- `0xad94d1`: `TVF_DeletedABSBlob_SiteIdABSId`
- `0xad94d6`: `SiteIdABSId`
- `0xad9514`: `TVF_DeletedABSBlob_DeletedDateLT`
- `0xad9519`: `DeletedDateLT`

## pseudocode

```c

```

## disassembly

```asm
0xad93a0  ldstr    aDeletedabsblob// "DeletedABSBlob"
0xad93a5  ldc.i4.0
0xad93a6  ldc.i4.0
0xad93a7  ldstr    aSiteid_0// "SiteId"
0xad93ac  ldc.i4.6
0xad93ad  newarr   Microsoft.SharePoint.Utilities.Sql.Column
0xad93b2  stloc.3
0xad93b3  ldloc.3
0xad93b4  ldc.i4.0
0xad93b5  ldstr    aSiteid_0// "SiteId"
0xad93ba  ldc.i4.s 0xE
0xad93bc  ldc.i4.0
0xad93bd  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xad93c2  stelem.ref
0xad93c3  ldloc.3
0xad93c4  ldc.i4.1
0xad93c5  ldstr    aDocid_0// "DocId"
0xad93ca  ldc.i4.s 0xE
0xad93cc  ldc.i4.1
0xad93cd  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xad93d2  stelem.ref
0xad93d3  ldloc.3
0xad93d4  ldc.i4.2
0xad93d5  ldstr    aAbsid_2// "ABSId"
0xad93da  ldc.i4.s 0xE
0xad93dc  ldc.i4.1
0xad93dd  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xad93e2  stelem.ref
0xad93e3  ldloc.3
0xad93e4  ldc.i4.3
0xad93e5  ldstr    aAbsinfo_1// "ABSInfo"
0xad93ea  ldc.i4.s 0x15
0xad93ec  ldc.i4   0x3E8
0xad93f1  ldc.i4.1
0xad93f2  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, int32 size, bool nullable)
0xad93f7  stelem.ref
0xad93f8  ldloc.3
0xad93f9  ldc.i4.4
0xad93fa  ldstr    aDeleteddate// "DeletedDate"
0xad93ff  ldc.i4.4
0xad9400  ldc.i4.0
0xad9401  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xad9406  stelem.ref
0xad9407  ldloc.3
0xad9408  ldc.i4.5
0xad9409  ldstr    aCorrelationid_0// "CorrelationId"
0xad940e  ldc.i4.s 0xE
0xad9410  ldc.i4.1
0xad9411  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xad9416  stelem.ref
0xad9417  ldloc.3
0xad9418  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Table::.ctor(string name, valuetype Microsoft.SharePoint.Utilities.Sql.PartitionOptions partOpts, valuetype Microsoft.SharePoint.Utilities.Sql.LargeValueTypesOffRowOption blobsOffRow, string partitionKeyCol, class Microsoft.SharePoint.Utilities.Sql.Column[] columns)
0xad941d  stloc.0
0xad941e  ldstr    aDeletedabsblob_0// "DeletedABSBlob_NCI"
0xad9423  ldloc.0
0xad9424  ldc.i4.4
0xad9425  ldc.i4.2
0xad9426  ldc.i4.2
0xad9427  newarr   [mscorlib]System.String
0xad942c  stloc.s  4
0xad942e  ldloc.s  4
0xad9430  ldc.i4.0
0xad9431  ldstr    aSiteid_0// "SiteId"
0xad9436  stelem.ref
0xad9437  ldloc.s  4
0xad9439  ldc.i4.1
0xad943a  ldstr    aAbsid_2// "ABSId"
0xad943f  stelem.ref
0xad9440  ldloc.s  4
0xad9442  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Index::.ctor(string name, class Microsoft.SharePoint.Utilities.Sql.Table table, valuetype Microsoft.SharePoint.Utilities.Sql.IndexType type, valuetype Microsoft.SharePoint.Utilities.Sql.FillFactor ffactor, string[] columns)
0xad9447  stloc.1
0xad9448  ldloc.0
0xad9449  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.Index> Microsoft.SharePoint.Utilities.Sql.Table::get_Indicies()
0xad944e  ldloc.1
0xad944f  callvirt instance string Microsoft.SharePoint.Utilities.Sql.Index::get_Name()
0xad9454  ldloc.1
0xad9455  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.Index>::Add(var<u1>, !!T0)
0xad945a  ldstr    aDeletedabsblob_1// "DeletedABSBlob_DeletedDateCI"
0xad945f  ldloc.0
0xad9460  ldc.i4.2
0xad9461  ldc.i4.2
0xad9462  ldc.i4.2
0xad9463  newarr   [mscorlib]System.String
0xad9468  stloc.s  5
0xad946a  ldloc.s  5
0xad946c  ldc.i4.0
0xad946d  ldstr    aDeleteddate// "DeletedDate"
0xad9472  stelem.ref
0xad9473  ldloc.s  5
0xad9475  ldc.i4.1
0xad9476  ldstr    aSiteid_0// "SiteId"
0xad947b  stelem.ref
0xad947c  ldloc.s  5
0xad947e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Index::.ctor(string name, class Microsoft.SharePoint.Utilities.Sql.Table table, valuetype Microsoft.SharePoint.Utilities.Sql.IndexType type, valuetype Microsoft.SharePoint.Utilities.Sql.FillFactor ffactor, string[] columns)
0xad9483  stloc.2
0xad9484  ldloc.0
0xad9485  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.Index> Microsoft.SharePoint.Utilities.Sql.Table::get_Indicies()
0xad948a  ldloc.2
0xad948b  callvirt instance string Microsoft.SharePoint.Utilities.Sql.Index::get_Name()
0xad9490  ldloc.2
0xad9491  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.Index>::Add(var<u1>, !!T0)
0xad9496  ldloc.0
0xad9497  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF> Microsoft.SharePoint.Utilities.Sql.Table::get_TVFs()
0xad949c  ldstr    aTvfDeletedabsb// "TVF_DeletedABSBlob_Site"
0xad94a1  ldstr    aSite_0// "Site"
0xad94a6  ldloc.1
0xad94a7  ldc.i4.0
0xad94a8  ldc.i4.2
0xad94a9  ldc.i4.1
0xad94aa  newarr   Microsoft.SharePoint.Utilities.Sql.Restriction
0xad94af  stloc.s  6
0xad94b1  ldloc.s  6
0xad94b3  ldc.i4.0
0xad94b4  ldstr    aSiteid_0// "SiteId"
0xad94b9  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterRestriction::.ctor(string column)
0xad94be  stelem.ref
0xad94bf  ldloc.s  6
0xad94c1  newobj   instance void Microsoft.SharePoint.Utilities.Sql.TVF::.ctor(string functionSuffix, class Microsoft.SharePoint.Utilities.Sql.Index index, valuetype LockHint lockHints, valuetype Microsoft.SharePoint.Utilities.Sql.ForceSeekOptions fsOption, class Microsoft.SharePoint.Utilities.Sql.Restriction[] restrictions)
0xad94c6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF>::Add(var<u1>, !!T0)
0xad94cb  ldloc.0
0xad94cc  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF> Microsoft.SharePoint.Utilities.Sql.Table::get_TVFs()
0xad94d1  ldstr    aTvfDeletedabsb_0// "TVF_DeletedABSBlob_SiteIdABSId"
0xad94d6  ldstr    aSiteidabsid// "SiteIdABSId"
0xad94db  ldloc.1
0xad94dc  ldc.i4.1
0xad94dd  ldc.i4.2
0xad94de  ldc.i4.2
0xad94df  newarr   Microsoft.SharePoint.Utilities.Sql.Restriction
0xad94e4  stloc.s  7
0xad94e6  ldloc.s  7
0xad94e8  ldc.i4.0
0xad94e9  ldstr    aSiteid_0// "SiteId"
0xad94ee  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterRestriction::.ctor(string column)
0xad94f3  stelem.ref
0xad94f4  ldloc.s  7
0xad94f6  ldc.i4.1
0xad94f7  ldstr    aAbsid_2// "ABSId"
0xad94fc  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterRestriction::.ctor(string column)
0xad9501  stelem.ref
0xad9502  ldloc.s  7
0xad9504  newobj   instance void Microsoft.SharePoint.Utilities.Sql.TVF::.ctor(string functionSuffix, class Microsoft.SharePoint.Utilities.Sql.Index index, valuetype LockHint lockHints, valuetype Microsoft.SharePoint.Utilities.Sql.ForceSeekOptions fsOption, class Microsoft.SharePoint.Utilities.Sql.Restriction[] restrictions)
0xad9509  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF>::Add(var<u1>, !!T0)
0xad950e  ldloc.0
0xad950f  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF> Microsoft.SharePoint.Utilities.Sql.Table::get_TVFs()
0xad9514  ldstr    aTvfDeletedabsb_1// "TVF_DeletedABSBlob_DeletedDateLT"
0xad9519  ldstr    aDeleteddatelt// "DeletedDateLT"
0xad951e  ldloc.2
0xad951f  ldc.i4.0
0xad9520  ldc.i4.2
0xad9521  ldc.i4.1
0xad9522  newarr   Microsoft.SharePoint.Utilities.Sql.Restriction
0xad9527  stloc.s  8
0xad9529  ldloc.s  8
0xad952b  ldc.i4.0
0xad952c  ldstr    aDeleteddate// "DeletedDate"
0xad9531  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterLTRestriction::.ctor(string column)
0xad9536  stelem.ref
0xad9537  ldloc.s  8
0xad9539  newobj   instance void Microsoft.SharePoint.Utilities.Sql.TVF::.ctor(string functionSuffix, class Microsoft.SharePoint.Utilities.Sql.Index index, valuetype LockHint lockHints, valuetype Microsoft.SharePoint.Utilities.Sql.ForceSeekOptions fsOption, class Microsoft.SharePoint.Utilities.Sql.Restriction[] restrictions)
0xad953e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF>::Add(var<u1>, !!T0)
0xad9543  ldloc.0
0xad9544  newobj   instance void Microsoft.SharePoint.Utilities.Sql.AddTableUpgradeAction::.ctor(class Microsoft.SharePoint.Utilities.Sql.Table table)
0xad9549  ret
```
