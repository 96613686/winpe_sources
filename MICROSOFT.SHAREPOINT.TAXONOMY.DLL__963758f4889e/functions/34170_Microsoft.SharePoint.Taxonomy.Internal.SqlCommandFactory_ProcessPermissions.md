# Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::ProcessPermissions

- ea: `0x34170`
- end: `0x342db`
- name: `Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::ProcessPermissions`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x33d30`

## callees

- `0x242a0`
- `0x26fd0`
- `0x27010`
- `0x2acd0`
- `0x34170`
- `0x34f10`
- `0x34f30`
- `0x34f60`
- `0x35d10`
- `0x36670`
- `0x36e00`
- `0x579b0`

## string_xrefs

- `0x34171`: `dataReader`
- `0x342bb`: `ErrorInvalidBackendDataXML`

## pseudocode

```c

```

## disassembly

```asm
0x34170  ldarg.1
0x34171  ldstr    aDatareader// "dataReader"
0x34176  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x3417b  ldarg.1
0x3417c  call     valuetype Microsoft.SharePoint.Taxonomy.Internal.CommandAction Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::GetCurrentAction(class Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader dataReader)
0x34181  stloc.0
0x34182  ldarg.0
0x34183  call     instance void Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::AppendCommandPrefix()
0x34188  ldloc.0
0x34189  stloc.1
0x3418a  ldloc.1
0x3418b  switch   loc_341A1, loc_341FC, loc_34254
0x3419c  br       loc_3428F
0x341a1  ldarg.0
0x341a2  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::databaseAdapter
0x341a7  ldarg.0
0x341a8  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::commandBuilder
0x341ad  ldarg.0
0x341ae  call     instance class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::get_Parameters()
0x341b3  ldarg.0
0x341b4  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x341b9  ldarg.1
0x341ba  ldstr    aA1// "a1"
0x341bf  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetInt(string name)
0x341c4  ldarg.1
0x341c5  ldstr    aA2// "a2"
0x341ca  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetString(string name)
0x341cf  ldarg.1
0x341d0  ldstr    aA3// "a3"
0x341d5  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetString(string name)
0x341da  ldarg.1
0x341db  ldstr    aA4// "a4"
0x341e0  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetString(string name)
0x341e5  ldc.i4.s 0xA
0x341e7  call     unsigned int64 [mscorlib]System.Convert::ToUInt64(string, int32)
0x341ec  ldarg.0
0x341ed  ldfld    bool Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::addSessionPermissionChangesToLog
0x341f2  call     void CreatePermission::CreateCommand(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase databaseAdapter, class [mscorlib]System.Text.StringBuilder builder, class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> parameters, valuetype [mscorlib]System.Guid partitionId, int32 groupId, string principalName, string displayName, unsigned int64 rights, bool addToLog)
0x341f7  br       loc_342CB
0x341fc  ldarg.0
0x341fd  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::databaseAdapter
0x34202  ldarg.0
0x34203  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::commandBuilder
0x34208  ldarg.0
0x34209  call     instance class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::get_Parameters()
0x3420e  ldarg.0
0x3420f  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x34214  ldarg.1
0x34215  ldstr    aA1// "a1"
0x3421a  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetInt(string name)
0x3421f  ldarg.1
0x34220  ldstr    aA2// "a2"
0x34225  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetString(string name)
0x3422a  ldarg.1
0x3422b  ldstr    aA3// "a3"
0x34230  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetString(string name)
0x34235  ldarg.1
0x34236  ldstr    aA4// "a4"
0x3423b  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetString(string name)
0x34240  ldc.i4.s 0xA
0x34242  call     unsigned int64 [mscorlib]System.Convert::ToUInt64(string, int32)
0x34247  ldarg.0
0x34248  ldfld    bool Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::addSessionPermissionChangesToLog
0x3424d  call     void UpdatePermission::CreateCommand(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase databaseAdapter, class [mscorlib]System.Text.StringBuilder builder, class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> parameters, valuetype [mscorlib]System.Guid partitionId, int32 groupId, string principalName, string displayName, unsigned int64 rights, bool addToLog)
0x34252  br.s     loc_342CB
0x34254  ldarg.0
0x34255  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::databaseAdapter
0x3425a  ldarg.0
0x3425b  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::commandBuilder
0x34260  ldarg.0
0x34261  call     instance class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::get_Parameters()
0x34266  ldarg.0
0x34267  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x3426c  ldarg.1
0x3426d  ldstr    aA1// "a1"
0x34272  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetInt(string name)
0x34277  ldarg.1
0x34278  ldstr    aA2// "a2"
0x3427d  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetString(string name)
0x34282  ldarg.0
0x34283  ldfld    bool Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::addSessionPermissionChangesToLog
0x34288  call     void DeletePermission::CreateCommand(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase databaseAdapter, class [mscorlib]System.Text.StringBuilder builder, class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> parameters, valuetype [mscorlib]System.Guid partitionId, int32 groupId, string principalName, bool addToLog)
0x3428d  br.s     loc_342CB
0x3428f  ldc.i4   0x76706664
0x34294  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x34299  ldc.i4.s 0xA
0x3429b  ldstr    aInvalidPermiss// "Invalid permission action: {0}"
0x342a0  ldc.i4.1
0x342a1  newarr   [mscorlib]System.Object
0x342a6  stloc.2
0x342a7  ldloc.2
0x342a8  ldc.i4.0
0x342a9  ldloc.0
0x342aa  box      Microsoft.SharePoint.Taxonomy.Internal.CommandAction
0x342af  callvirt instance string [mscorlib]System.Object::ToString()
0x342b4  stelem.ref
0x342b5  ldloc.2
0x342b6  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x342bb  ldstr    aErrorinvalidba// "ErrorInvalidBackendDataXML"
0x342c0  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x342c5  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x342ca  throw
0x342cb  ldarg.0
0x342cc  ldfld    bool Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::addSessionPermissionChangesToLog
0x342d1  brfalse.s loc_342DA
0x342d3  ldarg.0
0x342d4  ldc.i4.0
0x342d5  stfld    bool Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::addSessionPermissionChangesToLog
0x342da  ret
```
