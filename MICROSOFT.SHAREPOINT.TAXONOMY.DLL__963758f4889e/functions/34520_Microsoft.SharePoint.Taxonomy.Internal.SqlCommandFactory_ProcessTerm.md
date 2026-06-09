# Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::ProcessTerm

- ea: `0x34520`
- end: `0x34795`
- name: `Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::ProcessTerm`
- size: `629`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x33d30`

## callees

- `0x242a0`
- `0x26ee0`
- `0x26f60`
- `0x26fd0`
- `0x27010`
- `0x27030`
- `0x27050`
- `0x27090`
- `0x270b0`
- `0x2acd0`
- `0x34520`
- `0x34e00`
- `0x34f10`
- `0x34f30`
- `0x34f60`
- `0x35010`
- `0x35030`
- `0x35fb0`
- `0x368e0`
- `0x37000`
- `0x373e0`
- `0x579b0`

## string_xrefs

- `0x34521`: `dataReader`
- `0x34785`: `ErrorInvalidBackendDataXML`
- `0x3462e`: `TaxonomyOMCreateTerm`
- `0x346e4`: `TaxonomyOMDeleteTermAndChildren`

## pseudocode

```c

```

## disassembly

```asm
0x34520  ldarg.1
0x34521  ldstr    aDatareader// "dataReader"
0x34526  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x3452b  ldarg.1
0x3452c  call     valuetype Microsoft.SharePoint.Taxonomy.Internal.CommandAction Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::GetCurrentAction(class Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader dataReader)
0x34531  stloc.0
0x34532  ldarg.1
0x34533  ldstr    aA6// "a6"
0x34538  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetInt(string name)
0x3453d  stloc.1
0x3453e  ldarg.0
0x3453f  ldfld    class ObjectContext Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::objectContext
0x34544  ldloc.1
0x34545  callvirt instance void ObjectContext::set_ObjectId(int32 value)
0x3454a  ldarg.0
0x3454b  ldfld    class ObjectContext Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::objectContext
0x34550  ldc.i4.1
0x34551  callvirt instance void ObjectContext::set_CurrentObjectType(valuetype ObjectType value)
0x34556  ldarg.0
0x34557  call     instance void Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::AppendCommandPrefix()
0x3455c  ldloc.0
0x3455d  stloc.3
0x3455e  ldloc.3
0x3455f  switch   loc_34581, loc_34640, loc_346B6, loc_34756, loc_34581, loc_346F6
0x3457c  br       loc_34756
0x34581  ldarg.1
0x34582  ldstr    aA14// "a14"
0x34587  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetString(string name)
0x3458c  stloc.2
0x3458d  ldarg.0
0x3458e  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::databaseAdapter
0x34593  ldarg.0
0x34594  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::commandBuilder
0x34599  ldarg.0
0x3459a  call     instance class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::get_Parameters()
0x3459f  ldarg.0
0x345a0  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x345a5  ldarg.1
0x345a6  ldstr    aA9// "a9"
0x345ab  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetGuid(string name)
0x345b0  ldloc.2
0x345b1  ldarg.1
0x345b2  ldstr    aA20// "a20"
0x345b7  ldc.i4.0
0x345b8  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetInt(string name, int32 defaultValue)
0x345bd  ldarg.1
0x345be  ldstr    aA21// "a21"
0x345c3  ldc.i4.0
0x345c4  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetBoolean(string name, bool defaultValue)
0x345c9  ldloc.1
0x345ca  ldarg.1
0x345cb  ldstr    aA24// "a24"
0x345d0  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetInt(string name)
0x345d5  ldarg.1
0x345d6  ldstr    aA25// "a25"
0x345db  ldc.i4.0
0x345dc  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetInt(string name, int32 defaultValue)
0x345e1  ldarg.1
0x345e2  ldstr    aA17// "a17"
0x345e7  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetBoolean(string name)
0x345ec  ldarg.1
0x345ed  ldstr    aA67// "a67"
0x345f2  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetString(string name)
0x345f7  ldarg.1
0x345f8  ldstr    aA10// "a10"
0x345fd  ldc.i4.0
0x345fe  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetInt(string name, int32 defaultValue)
0x34603  ldarg.2
0x34604  ldarg.1
0x34605  ldstr    aA74// "a74"
0x3460a  ldc.i4.0
0x3460b  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetInt(string name, int32 defaultValue)
0x34610  ldarg.1
0x34611  ldstr    aA33// "a33"
0x34616  ldc.i4.0
0x34617  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetInt(string name, int32 defaultValue)
0x3461c  ldarg.1
0x3461d  ldstr    aA32// "a32"
0x34622  ldnull
0x34623  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetString(string name, string defaultValue)
0x34628  call     void CreateTerm::CreateCommand(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase databaseAdapter, class [mscorlib]System.Text.StringBuilder builder, class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> parameters, valuetype [mscorlib]System.Guid partitionId, valuetype [mscorlib]System.Guid uniqueId, string owner, int32 useCount, bool isDeprecated, int32 oldId, int32 termSetId, int32 parentTermId, bool availableForTagging, string customSortOrder, int32 sourceTermId, bool isRestrictedToOpenTermSets, int32 pinSourceTermSetId, int32 lcid, string label)
0x3462d  ldarg.0
0x3462e  ldstr    aTaxonomyomcrea_1// "TaxonomyOMCreateTerm"
0x34633  ldarg.0
0x34634  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x34639  ldloc.2
0x3463a  call     instance void Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::AddToEngagementLogQueue(string engagementName, valuetype [mscorlib]System.Guid subscriptionId, string user)
0x3463f  ret
0x34640  ldarg.0
0x34641  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::databaseAdapter
0x34646  ldarg.0
0x34647  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::commandBuilder
0x3464c  ldarg.0
0x3464d  call     instance class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::get_Parameters()
0x34652  ldarg.0
0x34653  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x34658  ldloc.1
0x34659  ldarg.1
0x3465a  ldstr    aA14// "a14"
0x3465f  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetString(string name)
0x34664  ldarg.1
0x34665  ldstr    aA20// "a20"
0x3466a  ldc.i4.0
0x3466b  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetInt(string name, int32 defaultValue)
0x34670  ldarg.1
0x34671  ldstr    aA21// "a21"
0x34676  ldc.i4.0
0x34677  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetBoolean(string name, bool defaultValue)
0x3467c  ldarg.1
0x3467d  ldstr    aA8// "a8"
0x34682  ldsfld   valuetype [mscorlib]System.DateTime DefaultValue::LastModifiedTime
0x34687  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetDateTime(string name, valuetype [mscorlib]System.DateTime defaultValue)
0x3468c  ldarg.1
0x3468d  ldstr    aA27// "a27"
0x34692  ldc.i4.0
0x34693  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetBoolean(string name, bool defaultValue)
0x34698  ldarg.1
0x34699  ldstr    aA30// "a30"
0x3469e  ldc.i4.1
0x3469f  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetBoolean(string name, bool defaultValue)
0x346a4  ldarg.1
0x346a5  ldstr    aA55// "a55"
0x346aa  ldnull
0x346ab  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetString(string name, string defaultValue)
0x346b0  call     void UpdateTerm::CreateCommand(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase databaseAdapter, class [mscorlib]System.Text.StringBuilder builder, class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> parameters, valuetype [mscorlib]System.Guid partitionId, int32 id, string owner, int32 useCount, bool isDeprecated, valuetype [mscorlib]System.DateTime lastModifiedTime, bool anyDefaultLabelChanged, bool addToLog, string changeData)
0x346b5  ret
0x346b6  ldarg.0
0x346b7  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::databaseAdapter
0x346bc  ldarg.0
0x346bd  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::commandBuilder
0x346c2  ldarg.0
0x346c3  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x346c8  ldarg.1
0x346c9  ldstr    aA6// "a6"
0x346ce  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetInt(string name)
0x346d3  ldarg.1
0x346d4  ldstr    aA24// "a24"
0x346d9  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetInt(string name)
0x346de  call     void DeleteTerm::CreateCommand(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase databaseAdapter, class [mscorlib]System.Text.StringBuilder builder, valuetype [mscorlib]System.Guid partitionId, int32 termId, int32 termSetId)
0x346e3  ldarg.0
0x346e4  ldstr    aTaxonomyomdele_1// "TaxonomyOMDeleteTermAndChildren"
0x346e9  ldarg.0
0x346ea  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x346ef  ldnull
0x346f0  call     instance void Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::AddToEngagementLogQueue(string engagementName, valuetype [mscorlib]System.Guid subscriptionId, string user)
0x346f5  ret
0x346f6  ldarg.0
0x346f7  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::databaseAdapter
0x346fc  ldarg.0
0x346fd  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::commandBuilder
0x34702  ldarg.0
0x34703  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x34708  ldarg.1
0x34709  ldstr    aA6// "a6"
0x3470e  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetInt(string name)
0x34713  ldarg.1
0x34714  ldstr    aA28// "a28"
0x34719  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetInt(string name)
0x3471e  ldarg.1
0x3471f  ldstr    aA8// "a8"
0x34724  ldsfld   valuetype [mscorlib]System.DateTime DefaultValue::NoDefaultTime
0x34729  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetDateTime(string name, valuetype [mscorlib]System.DateTime defaultValue)
0x3472e  ldarg.1
0x3472f  ldstr    aA29// "a29"
0x34734  ldsfld   valuetype [mscorlib]System.DateTime DefaultValue::NoDefaultTime
0x34739  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetDateTime(string name, valuetype [mscorlib]System.DateTime defaultValue)
0x3473e  call     void MergeTerm::CreateCommand(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase databaseAdapter, class [mscorlib]System.Text.StringBuilder builder, valuetype [mscorlib]System.Guid partitionId, int32 termId, int32 targetTermId, valuetype [mscorlib]System.DateTime lastModifiedTime, valuetype [mscorlib]System.DateTime targetLastModifiedTime)
0x34743  ldarg.0
0x34744  ldstr    aTaxonomyommerg// "TaxonomyOMMergeTerm"
0x34749  ldarg.0
0x3474a  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x3474f  ldnull
0x34750  call     instance void Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::AddToEngagementLogQueue(string engagementName, valuetype [mscorlib]System.Guid subscriptionId, string user)
0x34755  ret
0x34756  ldc.i4   0x6F667867
0x3475b  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x34760  ldc.i4.s 0xA
0x34762  ldstr    aInvalidTermAct// "Invalid term action: {0}"
0x34767  ldc.i4.1
0x34768  newarr   [mscorlib]System.Object
0x3476d  stloc.s  4
0x3476f  ldloc.s  4
0x34771  ldc.i4.0
0x34772  ldloc.0
0x34773  box      Microsoft.SharePoint.Taxonomy.Internal.CommandAction
0x34778  callvirt instance string [mscorlib]System.Object::ToString()
0x3477d  stelem.ref
0x3477e  ldloc.s  4
0x34780  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x34785  ldstr    aErrorinvalidba// "ErrorInvalidBackendDataXML"
0x3478a  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x3478f  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x34794  throw
```
