# Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::ProcessTermProperty

- ea: `0x34c20`
- end: `0x34db1`
- name: `Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::ProcessTermProperty`
- size: `401`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x33d30`

## callees

- `0x242a0`
- `0x27010`
- `0x27090`
- `0x2acd0`
- `0x34c20`
- `0x34f10`
- `0x34f30`
- `0x34f60`
- `0x34f80`
- `0x35000`
- `0x35020`
- `0x364a0`
- `0x36c60`
- `0x371f0`
- `0x579b0`

## string_xrefs

- `0x34c21`: `dataReader`
- `0x34caa`: `ErrorInvalidBackendDataXML`
- `0x34da1`: `ErrorInvalidBackendDataXML`
- `0x34c84`: `Object type in the TermProperty XML is None`

## pseudocode

```c

```

## disassembly

```asm
0x34c20  ldarg.1
0x34c21  ldstr    aDatareader// "dataReader"
0x34c26  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x34c2b  ldarg.1
0x34c2c  call     valuetype Microsoft.SharePoint.Taxonomy.Internal.CommandAction Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::GetCurrentAction(class Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader dataReader)
0x34c31  stloc.0
0x34c32  ldc.i4.0
0x34c33  stloc.1
0x34c34  ldc.i4.0
0x34c35  stloc.2
0x34c36  ldarg.0
0x34c37  ldfld    class ObjectContext Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::objectContext
0x34c3c  callvirt instance valuetype ObjectType ObjectContext::get_CurrentObjectType()
0x34c41  stloc.3
0x34c42  ldloc.3
0x34c43  ldc.i4.1
0x34c44  sub
0x34c45  switch   loc_34C54, loc_34C6A
0x34c52  br.s     loc_34C78
0x34c54  ldarg.0
0x34c55  call     instance int32 Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::get_CurrentTermId()
0x34c5a  stloc.1
0x34c5b  ldarg.1
0x34c5c  ldstr    aA24// "a24"
0x34c61  ldc.i4.0
0x34c62  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetInt(string name, int32 defaultValue)
0x34c67  stloc.2
0x34c68  br.s     loc_34C8E
0x34c6a  ldarg.0
0x34c6b  ldfld    class ObjectContext Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::objectContext
0x34c70  callvirt instance int32 ObjectContext::get_ObjectId()
0x34c75  stloc.2
0x34c76  br.s     loc_34C8E
0x34c78  ldc.i4   0x143CB
0x34c7d  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x34c82  ldc.i4.s 0xA
0x34c84  ldstr    aObjectTypeInTh// "Object type in the TermProperty XML is "...
0x34c89  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x34c8e  ldloc.1
0x34c8f  brtrue.s loc_34CBA
0x34c91  ldloc.2
0x34c92  brtrue.s loc_34CBA
0x34c94  ldc.i4   0x33637378
0x34c99  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x34c9e  ldc.i4.s 0xA
0x34ca0  ldstr    aNeitherTermOrT// "Neither Term or TermSet was not found f"...
0x34ca5  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x34caa  ldstr    aErrorinvalidba// "ErrorInvalidBackendDataXML"
0x34caf  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x34cb4  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x34cb9  throw
0x34cba  ldarg.0
0x34cbb  call     instance void Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::AppendCommandPrefix()
0x34cc0  ldloc.0
0x34cc1  stloc.s  4
0x34cc3  ldloc.s  4
0x34cc5  switch   loc_34CDB, loc_34D11, loc_34D47
0x34cd6  br       loc_34D72
0x34cdb  ldarg.0
0x34cdc  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::databaseAdapter
0x34ce1  ldarg.0
0x34ce2  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::commandBuilder
0x34ce7  ldarg.0
0x34ce8  call     instance class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::get_Parameters()
0x34ced  ldarg.0
0x34cee  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x34cf3  ldloc.1
0x34cf4  ldloc.2
0x34cf5  ldarg.1
0x34cf6  ldstr    aA37// "a37"
0x34cfb  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetString(string name)
0x34d00  ldarg.1
0x34d01  ldstr    aA38// "a38"
0x34d06  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetString(string name)
0x34d0b  call     void AddTermProperty::CreateCommand(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase databaseAdapter, class [mscorlib]System.Text.StringBuilder builder, class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> parameters, valuetype [mscorlib]System.Guid partitionId, int32 termId, int32 termSetId, string propertyName, string propertyValue)
0x34d10  ret
0x34d11  ldarg.0
0x34d12  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::databaseAdapter
0x34d17  ldarg.0
0x34d18  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::commandBuilder
0x34d1d  ldarg.0
0x34d1e  call     instance class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::get_Parameters()
0x34d23  ldarg.0
0x34d24  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x34d29  ldloc.1
0x34d2a  ldloc.2
0x34d2b  ldarg.1
0x34d2c  ldstr    aA37// "a37"
0x34d31  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetString(string name)
0x34d36  ldarg.1
0x34d37  ldstr    aA38// "a38"
0x34d3c  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetString(string name)
0x34d41  call     void UpdateTermProperty::CreateCommand(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase databaseAdapter, class [mscorlib]System.Text.StringBuilder builder, class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> parameters, valuetype [mscorlib]System.Guid partitionId, int32 termId, int32 termSetId, string propertyName, string propertyValue)
0x34d46  ret
0x34d47  ldarg.0
0x34d48  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::databaseAdapter
0x34d4d  ldarg.0
0x34d4e  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::commandBuilder
0x34d53  ldarg.0
0x34d54  call     instance class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::get_Parameters()
0x34d59  ldarg.0
0x34d5a  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x34d5f  ldloc.1
0x34d60  ldloc.2
0x34d61  ldarg.1
0x34d62  ldstr    aA37// "a37"
0x34d67  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetString(string name)
0x34d6c  call     void DeleteTermProperty::CreateCommand(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase databaseAdapter, class [mscorlib]System.Text.StringBuilder builder, class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> parameters, valuetype [mscorlib]System.Guid partitionId, int32 termId, int32 termSetId, string propertyName)
0x34d71  ret
0x34d72  ldc.i4   0x33637379
0x34d77  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x34d7c  ldc.i4.s 0xA
0x34d7e  ldstr    aInvalidTermPro// "Invalid term property action: {0}"
0x34d83  ldc.i4.1
0x34d84  newarr   [mscorlib]System.Object
0x34d89  stloc.s  5
0x34d8b  ldloc.s  5
0x34d8d  ldc.i4.0
0x34d8e  ldloc.0
0x34d8f  box      Microsoft.SharePoint.Taxonomy.Internal.CommandAction
0x34d94  callvirt instance string [mscorlib]System.Object::ToString()
0x34d99  stelem.ref
0x34d9a  ldloc.s  5
0x34d9c  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x34da1  ldstr    aErrorinvalidba// "ErrorInvalidBackendDataXML"
0x34da6  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x34dab  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x34db0  throw
```
