# Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::ProcessTermSet

- ea: `0x342e0`
- end: `0x3451d`
- name: `Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::ProcessTermSet`
- size: `573`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x33d30`

## callees

- `0x242a0`
- `0x26f60`
- `0x26fd0`
- `0x27010`
- `0x27030`
- `0x27050`
- `0x27090`
- `0x270b0`
- `0x2acd0`
- `0x342e0`
- `0x34e00`
- `0x34f10`
- `0x34f30`
- `0x34f60`
- `0x35010`
- `0x35030`
- `0x35df0`
- `0x36750`
- `0x36f20`
- `0x579b0`

## string_xrefs

- `0x342e1`: `dataReader`
- `0x3450d`: `ErrorInvalidBackendDataXML`
- `0x343f9`: `TaxonomyOMCreateTermSet`
- `0x344cc`: `TaxonomyOMDeleteTermSetAndChildren`

## pseudocode

```c

```

## disassembly

```asm
0x342e0  ldarg.1
0x342e1  ldstr    aDatareader// "dataReader"
0x342e6  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x342eb  ldarg.1
0x342ec  call     valuetype Microsoft.SharePoint.Taxonomy.Internal.CommandAction Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::GetCurrentAction(class Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader dataReader)
0x342f1  stloc.0
0x342f2  ldarg.1
0x342f3  ldstr    aA6// "a6"
0x342f8  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetInt(string name)
0x342fd  stloc.1
0x342fe  ldarg.0
0x342ff  ldfld    class ObjectContext Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::objectContext
0x34304  ldloc.1
0x34305  callvirt instance void ObjectContext::set_ObjectId(int32 value)
0x3430a  ldarg.0
0x3430b  ldfld    class ObjectContext Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::objectContext
0x34310  ldc.i4.2
0x34311  callvirt instance void ObjectContext::set_CurrentObjectType(valuetype ObjectType value)
0x34316  ldarg.0
0x34317  call     instance void Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::AppendCommandPrefix()
0x3431c  ldloc.0
0x3431d  stloc.3
0x3431e  ldloc.3
0x3431f  switch   loc_3433D, loc_3440B, loc_344A3, loc_3440B, loc_3433D
0x34338  br       loc_344DE
0x3433d  ldarg.1
0x3433e  ldstr    aA14// "a14"
0x34343  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetString(string name)
0x34348  stloc.2
0x34349  ldarg.0
0x3434a  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::databaseAdapter
0x3434f  ldarg.0
0x34350  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::commandBuilder
0x34355  ldarg.0
0x34356  call     instance class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::get_Parameters()
0x3435b  ldarg.0
0x3435c  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x34361  ldarg.1
0x34362  ldstr    aA9// "a9"
0x34367  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetGuid(string name)
0x3436c  ldarg.1
0x3436d  ldstr    aA12// "a12"
0x34372  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetString(string name)
0x34377  ldarg.1
0x34378  ldstr    aA11// "a11"
0x3437d  ldnull
0x3437e  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetString(string name, string defaultValue)
0x34383  ldloc.2
0x34384  ldarg.1
0x34385  ldstr    aA67// "a67"
0x3438a  ldnull
0x3438b  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetString(string name, string defaultValue)
0x34390  ldarg.1
0x34391  ldstr    aA15// "a15"
0x34396  ldc.i4.0
0x34397  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetInt(string name, int32 defaultValue)
0x3439c  ldarg.1
0x3439d  ldstr    aA16// "a16"
0x343a2  ldc.i4.0
0x343a3  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetBoolean(string name, bool defaultValue)
0x343a8  ldarg.1
0x343a9  ldstr    aA17// "a17"
0x343ae  ldc.i4.0
0x343af  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetBoolean(string name, bool defaultValue)
0x343b4  ldarg.1
0x343b5  ldstr    aA18// "a18"
0x343ba  ldnull
0x343bb  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetString(string name, string defaultValue)
0x343c0  ldarg.1
0x343c1  ldstr    aA68// "a68"
0x343c6  ldnull
0x343c7  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetString(string name, string defaultValue)
0x343cc  ldarg.1
0x343cd  ldstr    aA1// "a1"
0x343d2  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetInt(string name)
0x343d7  ldarg.1
0x343d8  ldstr    aA6// "a6"
0x343dd  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetInt(string name)
0x343e2  ldarg.1
0x343e3  ldstr    aA10// "a10"
0x343e8  ldc.i4.0
0x343e9  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetInt(string name, int32 defaultValue)
0x343ee  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x343f3  call     void CreateTermSet::CreateCommand(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase databaseAdapter, class [mscorlib]System.Text.StringBuilder builder, class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> parameters, valuetype [mscorlib]System.Guid partitionId, valuetype [mscorlib]System.Guid uniqueId, string name, string description, string owner, string customSortOrder, valuetype Microsoft.SharePoint.Taxonomy.Internal.TermSetType type, bool isOpen, bool isAvailableForTagging, string stakeHolders, string contact, int32 groupId, int32 oldId, valuetype [mscorlib]System.Nullable`1<int32> sourceId)
0x343f8  ldarg.0
0x343f9  ldstr    aTaxonomyomcrea_0// "TaxonomyOMCreateTermSet"
0x343fe  ldarg.0
0x343ff  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x34404  ldloc.2
0x34405  call     instance void Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::AddToEngagementLogQueue(string engagementName, valuetype [mscorlib]System.Guid subscriptionId, string user)
0x3440a  ret
0x3440b  ldarg.0
0x3440c  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::databaseAdapter
0x34411  ldarg.0
0x34412  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::commandBuilder
0x34417  ldarg.0
0x34418  call     instance class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::get_Parameters()
0x3441d  ldarg.0
0x3441e  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x34423  ldloc.1
0x34424  ldarg.1
0x34425  ldstr    aA12// "a12"
0x3442a  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetString(string name)
0x3442f  ldarg.1
0x34430  ldstr    aA11// "a11"
0x34435  ldnull
0x34436  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetString(string name, string defaultValue)
0x3443b  ldarg.1
0x3443c  ldstr    aA14// "a14"
0x34441  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetString(string name)
0x34446  ldarg.1
0x34447  ldstr    aA67// "a67"
0x3444c  ldnull
0x3444d  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetString(string name, string defaultValue)
0x34452  ldarg.1
0x34453  ldstr    aA16// "a16"
0x34458  ldc.i4.0
0x34459  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetBoolean(string name, bool defaultValue)
0x3445e  ldarg.1
0x3445f  ldstr    aA17// "a17"
0x34464  ldc.i4.0
0x34465  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetBoolean(string name, bool defaultValue)
0x3446a  ldarg.1
0x3446b  ldstr    aA18// "a18"
0x34470  ldnull
0x34471  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetString(string name, string defaultValue)
0x34476  ldarg.1
0x34477  ldstr    aA68// "a68"
0x3447c  ldnull
0x3447d  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetString(string name, string defaultValue)
0x34482  ldarg.1
0x34483  ldstr    aA8// "a8"
0x34488  ldsfld   valuetype [mscorlib]System.DateTime DefaultValue::LastModifiedTime
0x3448d  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetDateTime(string name, valuetype [mscorlib]System.DateTime defaultValue)
0x34492  ldarg.1
0x34493  ldstr    aA1// "a1"
0x34498  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetInt(string name)
0x3449d  call     void UpdateTermSet::CreateCommand(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase databaseAdapter, class [mscorlib]System.Text.StringBuilder builder, class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> parameters, valuetype [mscorlib]System.Guid partitionId, int32 id, string name, string description, string owner, string customSortOrder, bool isOpen, bool isAvailableForTagging, string stakeHolders, string contact, valuetype [mscorlib]System.DateTime lastModifiedTime, int32 groupId)
0x344a2  ret
0x344a3  ldarg.0
0x344a4  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::databaseAdapter
0x344a9  ldarg.0
0x344aa  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::commandBuilder
0x344af  ldarg.0
0x344b0  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x344b5  ldloc.1
0x344b6  ldarg.1
0x344b7  ldstr    aA8// "a8"
0x344bc  ldsfld   valuetype [mscorlib]System.DateTime DefaultValue::LastModifiedTime
0x344c1  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetDateTime(string name, valuetype [mscorlib]System.DateTime defaultValue)
0x344c6  call     void DeleteTermSet::CreateCommand(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase databaseAdapter, class [mscorlib]System.Text.StringBuilder builder, valuetype [mscorlib]System.Guid partitionId, int32 id, valuetype [mscorlib]System.DateTime lastModifiedTime)
0x344cb  ldarg.0
0x344cc  ldstr    aTaxonomyomdele_0// "TaxonomyOMDeleteTermSetAndChildren"
0x344d1  ldarg.0
0x344d2  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x344d7  ldnull
0x344d8  call     instance void Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::AddToEngagementLogQueue(string engagementName, valuetype [mscorlib]System.Guid subscriptionId, string user)
0x344dd  ret
0x344de  ldc.i4   0x6F667865
0x344e3  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x344e8  ldc.i4.s 0xA
0x344ea  ldstr    aInvalidTermSet// "Invalid term set action: {0}"
0x344ef  ldc.i4.1
0x344f0  newarr   [mscorlib]System.Object
0x344f5  stloc.s  4
0x344f7  ldloc.s  4
0x344f9  ldc.i4.0
0x344fa  ldloc.0
0x344fb  box      Microsoft.SharePoint.Taxonomy.Internal.CommandAction
0x34500  callvirt instance string [mscorlib]System.Object::ToString()
0x34505  stelem.ref
0x34506  ldloc.s  4
0x34508  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x3450d  ldstr    aErrorinvalidba// "ErrorInvalidBackendDataXML"
0x34512  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x34517  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x3451c  throw
```
