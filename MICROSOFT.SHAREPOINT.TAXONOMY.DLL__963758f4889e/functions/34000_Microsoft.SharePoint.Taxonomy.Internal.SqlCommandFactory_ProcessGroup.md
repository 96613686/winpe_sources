# Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::ProcessGroup

- ea: `0x34000`
- end: `0x3416b`
- name: `Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::ProcessGroup`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x33d30`

## callees

- `0x242a0`
- `0x26f60`
- `0x26fd0`
- `0x27010`
- `0x27050`
- `0x27090`
- `0x270b0`
- `0x2acd0`
- `0x34000`
- `0x34e00`
- `0x34f10`
- `0x34f30`
- `0x34f60`
- `0x35c30`
- `0x36580`
- `0x36d20`
- `0x579b0`

## string_xrefs

- `0x34001`: `dataReader`
- `0x3415b`: `ErrorInvalidBackendDataXML`
- `0x34088`: `TaxonomyOMCreateGroup`
- `0x3411d`: `TaxonomyOMDeleteGroup`

## pseudocode

```c

```

## disassembly

```asm
0x34000  ldarg.1
0x34001  ldstr    aDatareader// "dataReader"
0x34006  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x3400b  ldarg.1
0x3400c  call     valuetype Microsoft.SharePoint.Taxonomy.Internal.CommandAction Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::GetCurrentAction(class Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader dataReader)
0x34011  stloc.0
0x34012  ldarg.0
0x34013  call     instance void Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::AppendCommandPrefix()
0x34018  ldloc.0
0x34019  stloc.1
0x3401a  ldloc.1
0x3401b  switch   loc_34031, loc_3409A, loc_340EA
0x3402c  br       loc_3412F
0x34031  ldarg.0
0x34032  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::databaseAdapter
0x34037  ldarg.0
0x34038  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::commandBuilder
0x3403d  ldarg.0
0x3403e  call     instance class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::get_Parameters()
0x34043  ldarg.0
0x34044  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x34049  ldarg.1
0x3404a  ldstr    aA9// "a9"
0x3404f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetGuid(string name)
0x34054  ldarg.1
0x34055  ldstr    aA12// "a12"
0x3405a  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetString(string name)
0x3405f  ldarg.1
0x34060  ldstr    aA11// "a11"
0x34065  ldnull
0x34066  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetString(string name, string defaultValue)
0x3406b  ldarg.1
0x3406c  ldstr    aA15// "a15"
0x34071  ldc.i4.0
0x34072  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetInt(string name, int32 defaultValue)
0x34077  ldarg.1
0x34078  ldstr    aA6// "a6"
0x3407d  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetInt(string name)
0x34082  call     void CreateGroup::CreateCommand(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase databaseAdapter, class [mscorlib]System.Text.StringBuilder builder, class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> parameters, valuetype [mscorlib]System.Guid partitionId, valuetype [mscorlib]System.Guid uniqueId, string name, string description, valuetype Microsoft.SharePoint.Taxonomy.Internal.GroupType type, int32 oldId)
0x34087  ldarg.0
0x34088  ldstr    aTaxonomyomcrea// "TaxonomyOMCreateGroup"
0x3408d  ldarg.0
0x3408e  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x34093  ldnull
0x34094  call     instance void Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::AddToEngagementLogQueue(string engagementName, valuetype [mscorlib]System.Guid subscriptionId, string user)
0x34099  ret
0x3409a  ldarg.0
0x3409b  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::databaseAdapter
0x340a0  ldarg.0
0x340a1  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::commandBuilder
0x340a6  ldarg.0
0x340a7  call     instance class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::get_Parameters()
0x340ac  ldarg.0
0x340ad  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x340b2  ldarg.1
0x340b3  ldstr    aA6// "a6"
0x340b8  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetInt(string name)
0x340bd  ldarg.1
0x340be  ldstr    aA12// "a12"
0x340c3  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetString(string name)
0x340c8  ldarg.1
0x340c9  ldstr    aA11// "a11"
0x340ce  ldnull
0x340cf  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetString(string name, string defaultValue)
0x340d4  ldarg.1
0x340d5  ldstr    aA8// "a8"
0x340da  ldsfld   valuetype [mscorlib]System.DateTime DefaultValue::LastModifiedTime
0x340df  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetDateTime(string name, valuetype [mscorlib]System.DateTime defaultValue)
0x340e4  call     void UpdateGroup::CreateCommand(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase databaseAdapter, class [mscorlib]System.Text.StringBuilder builder, class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> parameters, valuetype [mscorlib]System.Guid partitionId, int32 id, string name, string description, valuetype [mscorlib]System.DateTime lastModifiedTime)
0x340e9  ret
0x340ea  ldarg.0
0x340eb  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::databaseAdapter
0x340f0  ldarg.0
0x340f1  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::commandBuilder
0x340f6  ldarg.0
0x340f7  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x340fc  ldarg.1
0x340fd  ldstr    aA6// "a6"
0x34102  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetInt(string name)
0x34107  ldarg.1
0x34108  ldstr    aA8// "a8"
0x3410d  ldsfld   valuetype [mscorlib]System.DateTime DefaultValue::LastModifiedTime
0x34112  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetDateTime(string name, valuetype [mscorlib]System.DateTime defaultValue)
0x34117  call     void DeleteGroup::CreateCommand(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase databaseAdapter, class [mscorlib]System.Text.StringBuilder builder, valuetype [mscorlib]System.Guid partitionId, int32 id, valuetype [mscorlib]System.DateTime lastModifiedTime)
0x3411c  ldarg.0
0x3411d  ldstr    aTaxonomyomdele// "TaxonomyOMDeleteGroup"
0x34122  ldarg.0
0x34123  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x34128  ldnull
0x34129  call     instance void Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::AddToEngagementLogQueue(string engagementName, valuetype [mscorlib]System.Guid subscriptionId, string user)
0x3412e  ret
0x3412f  ldc.i4   0x6F667864
0x34134  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x34139  ldc.i4.s 0xA
0x3413b  ldstr    aInvalidGroupAc// "Invalid group action: {0}"
0x34140  ldc.i4.1
0x34141  newarr   [mscorlib]System.Object
0x34146  stloc.2
0x34147  ldloc.2
0x34148  ldc.i4.0
0x34149  ldloc.0
0x3414a  box      Microsoft.SharePoint.Taxonomy.Internal.CommandAction
0x3414f  callvirt instance string [mscorlib]System.Object::ToString()
0x34154  stelem.ref
0x34155  ldloc.2
0x34156  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x3415b  ldstr    aErrorinvalidba// "ErrorInvalidBackendDataXML"
0x34160  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x34165  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x3416a  throw
```
