# Microsoft.SharePoint.Utilities.Sql.SPAppManagementSqlSchemaUpgradeActions::CreateAppPrincipalUserPermsTable

- ea: `0xabe2e0`
- end: `0xabe5dc`
- name: `Microsoft.SharePoint.Utilities.Sql.SPAppManagementSqlSchemaUpgradeActions::CreateAppPrincipalUserPermsTable`
- size: `764`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0xabe2a0`

## callees

- `0x95e370`
- `0x95e520`
- `0x95f500`
- `0x95f510`
- `0x95f9f0`
- `0x95fda0`
- `0x95fdb0`
- `0x960270`
- `0x9602b0`
- `0x960350`
- `0x960ed0`
- `0x960f30`

## string_xrefs

- `0xabe350`: `Created`
- `0xabe2f1`: `CompositePartitionKey`
- `0xabe364`: `CompositePartitionKey`
- `0xabe37b`: `CompositePartitionKey`
- `0xabe3cd`: `CompositePartitionKey`
- `0xabe407`: `CompositePartitionKey`
- `0xabe419`: `CompositePartitionKey`
- `0xabe453`: `CompositePartitionKey`
- `0xabe49b`: `CompositePartitionKey`
- `0xabe52f`: `CompositePartitionKey`
- `0xabe572`: `CompositePartitionKey`
- `0xabe580`: `CompositePartitionKey`
- `0xabe5b5`: `CompositePartitionKey`
- `0xabe5c3`: `CompositePartitionKey`
- `0xabe396`: `AM_AppPrincipalUserPerms_CompositePartitionKey_UserIdentity_ProviderTypeId`
- `0xabe3d7`: `AM_AppPrincipalUserPerms_UserIdentity_CompositePartitionKey`
- `0xabe401`: `TVF_AM_AppPrincipalUserPerms_CompositePartitionKey`
- `0xabe436`: `TVF_AM_AppPrincipalUserPerms_CompositePartitionKey_UserIdentity`
- `0xabe43c`: `CompositePartitionKey_UserIdentity`
- `0xabe47e`: `TVF_AM_AppPrincipalUserPerms_CompositePartitionKey_UserIdentity_ProviderTypeId`
- `0xabe484`: `CompositePartitionKey_UserIdentity_ProviderTypeId`
- `0xabe509`: `TVF_AM_AppPrincipalUserPerms_UserIdentity_CompositePartitionKey`
- `0xabe50f`: `UserIdentity_CompositePartitionKey`
- `0xabe54c`: `TVF_AM_AppPrincipalUserPerms_UserIdentity_Range_CompositePartitionKey`
- `0xabe552`: `UserIdentity_Range_CompositePartitionKey`
- `0xabe59d`: `TVF_AM_AppPrincipalUserPerms_Range_CompositePartitionKey`
- `0xabe5a3`: `Range_CompositePartitionKey`

## pseudocode

```c

```

## disassembly

```asm
0xabe2e0  ldstr    aAmAppprincipal_5// "AM_AppPrincipalUserPerms"
0xabe2e5  stloc.0
0xabe2e6  ldc.i4.6
0xabe2e7  newarr   Microsoft.SharePoint.Utilities.Sql.Column
0xabe2ec  stloc.s  7
0xabe2ee  ldloc.s  7
0xabe2f0  ldc.i4.0
0xabe2f1  ldstr    aCompositeparti_2// "CompositePartitionKey"
0xabe2f6  ldc.i4.s 0x15
0xabe2f8  ldc.i4   0x211
0xabe2fd  ldc.i4.0
0xabe2fe  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, int32 size, bool nullable)
0xabe303  stelem.ref
0xabe304  ldloc.s  7
0xabe306  ldc.i4.1
0xabe307  ldstr    aUseridentity_1// "UserIdentity"
0xabe30c  ldc.i4.s 0xC
0xabe30e  ldc.i4   0xFF
0xabe313  ldc.i4.0
0xabe314  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, int32 size, bool nullable)
0xabe319  stelem.ref
0xabe31a  ldloc.s  7
0xabe31c  ldc.i4.2
0xabe31d  ldstr    aProvidertypeid_0// "ProviderTypeId"
0xabe322  ldc.i4.s 0xE
0xabe324  ldc.i4.0
0xabe325  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xabe32a  stelem.ref
0xabe32b  ldloc.s  7
0xabe32d  ldc.i4.3
0xabe32e  ldstr    aPerm_1// "Perm"
0xabe333  ldc.i4.s 0x15
0xabe335  ldc.i4.m1
0xabe336  ldc.i4.0
0xabe337  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, int32 size, bool nullable)
0xabe33c  stelem.ref
0xabe33d  ldloc.s  7
0xabe33f  ldc.i4.4
0xabe340  ldstr    aVersion_1// "Version"
0xabe345  ldc.i4.8
0xabe346  ldc.i4.0
0xabe347  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xabe34c  stelem.ref
0xabe34d  ldloc.s  7
0xabe34f  ldc.i4.5
0xabe350  ldstr    aCreated_0// "Created"
0xabe355  ldc.i4.4
0xabe356  ldc.i4.1
0xabe357  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Column::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType t, bool nullable)
0xabe35c  stelem.ref
0xabe35d  ldloc.s  7
0xabe35f  stloc.1
0xabe360  ldloc.0
0xabe361  ldc.i4.s 9
0xabe363  ldc.i4.2
0xabe364  ldstr    aCompositeparti_2// "CompositePartitionKey"
0xabe369  ldloc.1
0xabe36a  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Table::.ctor(string name, valuetype Microsoft.SharePoint.Utilities.Sql.PartitionOptions partOpts, valuetype Microsoft.SharePoint.Utilities.Sql.LargeValueTypesOffRowOption blobsOffRow, string partitionKeyCol, class Microsoft.SharePoint.Utilities.Sql.Column[] columns)
0xabe36f  stloc.2
0xabe370  ldc.i4.3
0xabe371  newarr   [mscorlib]System.String
0xabe376  stloc.s  8
0xabe378  ldloc.s  8
0xabe37a  ldc.i4.0
0xabe37b  ldstr    aCompositeparti_2// "CompositePartitionKey"
0xabe380  stelem.ref
0xabe381  ldloc.s  8
0xabe383  ldc.i4.1
0xabe384  ldstr    aUseridentity_1// "UserIdentity"
0xabe389  stelem.ref
0xabe38a  ldloc.s  8
0xabe38c  ldc.i4.2
0xabe38d  ldstr    aProvidertypeid_0// "ProviderTypeId"
0xabe392  stelem.ref
0xabe393  ldloc.s  8
0xabe395  stloc.3
0xabe396  ldstr    aAmAppprincipal_6// "AM_AppPrincipalUserPerms_CompositeParti"...
0xabe39b  ldloc.2
0xabe39c  ldc.i4.0
0xabe39d  ldloc.3
0xabe39e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Index::.ctor(string name, class Microsoft.SharePoint.Utilities.Sql.Table table, valuetype Microsoft.SharePoint.Utilities.Sql.IndexType type, string[] columns)
0xabe3a3  stloc.s  4
0xabe3a5  ldloc.2
0xabe3a6  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.Index> Microsoft.SharePoint.Utilities.Sql.Table::get_Indicies()
0xabe3ab  ldloc.s  4
0xabe3ad  callvirt instance string Microsoft.SharePoint.Utilities.Sql.Index::get_Name()
0xabe3b2  ldloc.s  4
0xabe3b4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.Index>::Add(var<u1>, !!T0)
0xabe3b9  ldc.i4.2
0xabe3ba  newarr   [mscorlib]System.String
0xabe3bf  stloc.s  9
0xabe3c1  ldloc.s  9
0xabe3c3  ldc.i4.0
0xabe3c4  ldstr    aUseridentity_1// "UserIdentity"
0xabe3c9  stelem.ref
0xabe3ca  ldloc.s  9
0xabe3cc  ldc.i4.1
0xabe3cd  ldstr    aCompositeparti_2// "CompositePartitionKey"
0xabe3d2  stelem.ref
0xabe3d3  ldloc.s  9
0xabe3d5  stloc.s  5
0xabe3d7  ldstr    aAmAppprincipal_7// "AM_AppPrincipalUserPerms_UserIdentity_C"...
0xabe3dc  ldloc.2
0xabe3dd  ldc.i4.4
0xabe3de  ldloc.s  5
0xabe3e0  newobj   instance void Microsoft.SharePoint.Utilities.Sql.Index::.ctor(string name, class Microsoft.SharePoint.Utilities.Sql.Table table, valuetype Microsoft.SharePoint.Utilities.Sql.IndexType type, string[] columns)
0xabe3e5  stloc.s  6
0xabe3e7  ldloc.2
0xabe3e8  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.Index> Microsoft.SharePoint.Utilities.Sql.Table::get_Indicies()
0xabe3ed  ldloc.s  6
0xabe3ef  callvirt instance string Microsoft.SharePoint.Utilities.Sql.Index::get_Name()
0xabe3f4  ldloc.s  6
0xabe3f6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.Index>::Add(var<u1>, !!T0)
0xabe3fb  ldloc.2
0xabe3fc  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF> Microsoft.SharePoint.Utilities.Sql.Table::get_TVFs()
0xabe401  ldstr    aTvfAmAppprinci_5// "TVF_AM_AppPrincipalUserPerms_CompositeP"...
0xabe406  ldloc.0
0xabe407  ldstr    aCompositeparti_2// "CompositePartitionKey"
0xabe40c  ldloc.s  4
0xabe40e  ldc.i4.1
0xabe40f  newarr   Microsoft.SharePoint.Utilities.Sql.Restriction
0xabe414  stloc.s  0xA
0xabe416  ldloc.s  0xA
0xabe418  ldc.i4.0
0xabe419  ldstr    aCompositeparti_2// "CompositePartitionKey"
0xabe41e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterRestriction::.ctor(string column)
0xabe423  stelem.ref
0xabe424  ldloc.s  0xA
0xabe426  newobj   instance void Microsoft.SharePoint.Utilities.Sql.TVF::.ctor(string functionBase, string functionSuffix, class Microsoft.SharePoint.Utilities.Sql.Index index, class Microsoft.SharePoint.Utilities.Sql.Restriction[] restrictions)
0xabe42b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF>::Add(var<u1>, !!T0)
0xabe430  ldloc.2
0xabe431  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF> Microsoft.SharePoint.Utilities.Sql.Table::get_TVFs()
0xabe436  ldstr    aTvfAmAppprinci_6// "TVF_AM_AppPrincipalUserPerms_CompositeP"...
0xabe43b  ldloc.0
0xabe43c  ldstr    aCompositeparti_3// "CompositePartitionKey_UserIdentity"
0xabe441  ldloc.s  4
0xabe443  ldc.i4   0x80
0xabe448  ldc.i4.2
0xabe449  newarr   Microsoft.SharePoint.Utilities.Sql.Restriction
0xabe44e  stloc.s  0xB
0xabe450  ldloc.s  0xB
0xabe452  ldc.i4.0
0xabe453  ldstr    aCompositeparti_2// "CompositePartitionKey"
0xabe458  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterRestriction::.ctor(string column)
0xabe45d  stelem.ref
0xabe45e  ldloc.s  0xB
0xabe460  ldc.i4.1
0xabe461  ldstr    aUseridentity_1// "UserIdentity"
0xabe466  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterRestriction::.ctor(string column)
0xabe46b  stelem.ref
0xabe46c  ldloc.s  0xB
0xabe46e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.TVF::.ctor(string functionBase, string functionSuffix, class Microsoft.SharePoint.Utilities.Sql.Index index, valuetype LockHint lockHints, class Microsoft.SharePoint.Utilities.Sql.Restriction[] restrictions)
0xabe473  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF>::Add(var<u1>, !!T0)
0xabe478  ldloc.2
0xabe479  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF> Microsoft.SharePoint.Utilities.Sql.Table::get_TVFs()
0xabe47e  ldstr    aTvfAmAppprinci_7// "TVF_AM_AppPrincipalUserPerms_CompositeP"...
0xabe483  ldloc.0
0xabe484  ldstr    aCompositeparti_4// "CompositePartitionKey_UserIdentity_Prov"...
0xabe489  ldloc.s  4
0xabe48b  ldc.i4   0x80
0xabe490  ldc.i4.3
0xabe491  newarr   Microsoft.SharePoint.Utilities.Sql.Restriction
0xabe496  stloc.s  0xC
0xabe498  ldloc.s  0xC
0xabe49a  ldc.i4.0
0xabe49b  ldstr    aCompositeparti_2// "CompositePartitionKey"
0xabe4a0  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterRestriction::.ctor(string column)
0xabe4a5  stelem.ref
0xabe4a6  ldloc.s  0xC
0xabe4a8  ldc.i4.1
0xabe4a9  ldstr    aUseridentity_1// "UserIdentity"
0xabe4ae  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterRestriction::.ctor(string column)
0xabe4b3  stelem.ref
0xabe4b4  ldloc.s  0xC
0xabe4b6  ldc.i4.2
0xabe4b7  ldstr    aProvidertypeid_0// "ProviderTypeId"
0xabe4bc  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterRestriction::.ctor(string column)
0xabe4c1  stelem.ref
0xabe4c2  ldloc.s  0xC
0xabe4c4  newobj   instance void Microsoft.SharePoint.Utilities.Sql.TVF::.ctor(string functionBase, string functionSuffix, class Microsoft.SharePoint.Utilities.Sql.Index index, valuetype LockHint lockHints, class Microsoft.SharePoint.Utilities.Sql.Restriction[] restrictions)
0xabe4c9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF>::Add(var<u1>, !!T0)
0xabe4ce  ldloc.2
0xabe4cf  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF> Microsoft.SharePoint.Utilities.Sql.Table::get_TVFs()
0xabe4d4  ldstr    aTvfAmAppprinci_8// "TVF_AM_AppPrincipalUserPerms_UserIdenti"...
0xabe4d9  ldloc.0
0xabe4da  ldstr    aUseridentity_1// "UserIdentity"
0xabe4df  ldloc.s  6
0xabe4e1  ldc.i4.1
0xabe4e2  newarr   Microsoft.SharePoint.Utilities.Sql.Restriction
0xabe4e7  stloc.s  0xD
0xabe4e9  ldloc.s  0xD
0xabe4eb  ldc.i4.0
0xabe4ec  ldstr    aUseridentity_1// "UserIdentity"
0xabe4f1  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterRestriction::.ctor(string column)
0xabe4f6  stelem.ref
0xabe4f7  ldloc.s  0xD
0xabe4f9  newobj   instance void Microsoft.SharePoint.Utilities.Sql.TVF::.ctor(string functionBase, string functionSuffix, class Microsoft.SharePoint.Utilities.Sql.Index index, class Microsoft.SharePoint.Utilities.Sql.Restriction[] restrictions)
0xabe4fe  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF>::Add(var<u1>, !!T0)
0xabe503  ldloc.2
0xabe504  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF> Microsoft.SharePoint.Utilities.Sql.Table::get_TVFs()
0xabe509  ldstr    aTvfAmAppprinci_9// "TVF_AM_AppPrincipalUserPerms_UserIdenti"...
0xabe50e  ldloc.0
0xabe50f  ldstr    aUseridentityCo// "UserIdentity_CompositePartitionKey"
0xabe514  ldloc.s  6
0xabe516  ldc.i4.2
0xabe517  newarr   Microsoft.SharePoint.Utilities.Sql.Restriction
0xabe51c  stloc.s  0xE
0xabe51e  ldloc.s  0xE
0xabe520  ldc.i4.0
0xabe521  ldstr    aUseridentity_1// "UserIdentity"
0xabe526  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterRestriction::.ctor(string column)
0xabe52b  stelem.ref
0xabe52c  ldloc.s  0xE
0xabe52e  ldc.i4.1
0xabe52f  ldstr    aCompositeparti_2// "CompositePartitionKey"
0xabe534  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterRestriction::.ctor(string column)
0xabe539  stelem.ref
0xabe53a  ldloc.s  0xE
0xabe53c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.TVF::.ctor(string functionBase, string functionSuffix, class Microsoft.SharePoint.Utilities.Sql.Index index, class Microsoft.SharePoint.Utilities.Sql.Restriction[] restrictions)
0xabe541  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF>::Add(var<u1>, !!T0)
0xabe546  ldloc.2
0xabe547  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF> Microsoft.SharePoint.Utilities.Sql.Table::get_TVFs()
0xabe54c  ldstr    aTvfAmAppprinci_10// "TVF_AM_AppPrincipalUserPerms_UserIdenti"...
0xabe551  ldloc.0
0xabe552  ldstr    aUseridentityRa// "UserIdentity_Range_CompositePartitionKe"...
0xabe557  ldloc.s  6
0xabe559  ldc.i4.3
0xabe55a  newarr   Microsoft.SharePoint.Utilities.Sql.Restriction
0xabe55f  stloc.s  0xF
0xabe561  ldloc.s  0xF
0xabe563  ldc.i4.0
0xabe564  ldstr    aUseridentity_1// "UserIdentity"
0xabe569  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterRestriction::.ctor(string column)
0xabe56e  stelem.ref
0xabe56f  ldloc.s  0xF
0xabe571  ldc.i4.1
0xabe572  ldstr    aCompositeparti_2// "CompositePartitionKey"
0xabe577  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterGEQRestriction::.ctor(string column)
0xabe57c  stelem.ref
0xabe57d  ldloc.s  0xF
0xabe57f  ldc.i4.2
0xabe580  ldstr    aCompositeparti_2// "CompositePartitionKey"
0xabe585  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterScaleOutPartitionKeyLTRestriction::.ctor(string column)
0xabe58a  stelem.ref
0xabe58b  ldloc.s  0xF
0xabe58d  newobj   instance void Microsoft.SharePoint.Utilities.Sql.TVF::.ctor(string functionBase, string functionSuffix, class Microsoft.SharePoint.Utilities.Sql.Index index, class Microsoft.SharePoint.Utilities.Sql.Restriction[] restrictions)
0xabe592  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF>::Add(var<u1>, !!T0)
0xabe597  ldloc.2
0xabe598  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF> Microsoft.SharePoint.Utilities.Sql.Table::get_TVFs()
0xabe59d  ldstr    aTvfAmAppprinci_11// "TVF_AM_AppPrincipalUserPerms_Range_Comp"...
0xabe5a2  ldloc.0
0xabe5a3  ldstr    aRangeComposite// "Range_CompositePartitionKey"
0xabe5a8  ldloc.s  4
0xabe5aa  ldc.i4.2
0xabe5ab  newarr   Microsoft.SharePoint.Utilities.Sql.Restriction
0xabe5b0  stloc.s  0x10
0xabe5b2  ldloc.s  0x10
0xabe5b4  ldc.i4.0
0xabe5b5  ldstr    aCompositeparti_2// "CompositePartitionKey"
0xabe5ba  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterGEQRestriction::.ctor(string column)
0xabe5bf  stelem.ref
0xabe5c0  ldloc.s  0x10
0xabe5c2  ldc.i4.1
0xabe5c3  ldstr    aCompositeparti_2// "CompositePartitionKey"
0xabe5c8  newobj   instance void Microsoft.SharePoint.Utilities.Sql.ParameterScaleOutPartitionKeyLTRestriction::.ctor(string column)
0xabe5cd  stelem.ref
0xabe5ce  ldloc.s  0x10
0xabe5d0  newobj   instance void Microsoft.SharePoint.Utilities.Sql.TVF::.ctor(string functionBase, string functionSuffix, class Microsoft.SharePoint.Utilities.Sql.Index index, class Microsoft.SharePoint.Utilities.Sql.Restriction[] restrictions)
0xabe5d5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TVF>::Add(var<u1>, !!T0)
0xabe5da  ldloc.2
0xabe5db  ret
```
