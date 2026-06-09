# Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::ProcessTermLabel

- ea: `0x349a0`
- end: `0x34ad7`
- name: `Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::ProcessTermLabel`
- size: `311`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x33d30`

## callees

- `0x242a0`
- `0x26fd0`
- `0x27010`
- `0x27030`
- `0x2acd0`
- `0x349a0`
- `0x34f10`
- `0x34f30`
- `0x34f60`
- `0x34f80`
- `0x362a0`
- `0x370a0`
- `0x579b0`

## string_xrefs

- `0x349a1`: `dataReader`
- `0x349d2`: `ErrorInvalidBackendDataXML`
- `0x34ac7`: `ErrorInvalidBackendDataXML`

## pseudocode

```c

```

## disassembly

```asm
0x349a0  ldarg.1
0x349a1  ldstr    aDatareader// "dataReader"
0x349a6  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x349ab  ldarg.1
0x349ac  call     valuetype Microsoft.SharePoint.Taxonomy.Internal.CommandAction Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::GetCurrentAction(class Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader dataReader)
0x349b1  stloc.0
0x349b2  ldarg.0
0x349b3  call     instance int32 Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::get_CurrentTermId()
0x349b8  stloc.1
0x349b9  ldloc.1
0x349ba  brtrue.s loc_349E2
0x349bc  ldc.i4   0x3134386D
0x349c1  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x349c6  ldc.i4.s 0xA
0x349c8  ldstr    aTermWasNotFoun_0// "Term was not found for the Term label o"...
0x349cd  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x349d2  ldstr    aErrorinvalidba// "ErrorInvalidBackendDataXML"
0x349d7  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x349dc  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x349e1  throw
0x349e2  ldarg.0
0x349e3  call     instance void Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::AppendCommandPrefix()
0x349e8  ldloc.0
0x349e9  stloc.2
0x349ea  ldloc.2
0x349eb  switch   loc_34A01, loc_34A9B, loc_34A66
0x349fc  br       loc_34A9B
0x34a01  ldarg.0
0x34a02  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::databaseAdapter
0x34a07  ldarg.0
0x34a08  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::commandBuilder
0x34a0d  ldarg.0
0x34a0e  call     instance class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::get_Parameters()
0x34a13  ldarg.0
0x34a14  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x34a19  ldloc.1
0x34a1a  ldarg.1
0x34a1b  ldstr    aA33// "a33"
0x34a20  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetInt(string name)
0x34a25  ldarg.1
0x34a26  ldstr    aA32// "a32"
0x34a2b  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetString(string name)
0x34a30  ldarg.1
0x34a31  ldstr    aA31// "a31"
0x34a36  ldc.i4.0
0x34a37  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetBoolean(string name, bool defaultValue)
0x34a3c  ldarg.1
0x34a3d  ldstr    aA35// "a35"
0x34a42  ldc.i4.0
0x34a43  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetBoolean(string name, bool defaultValue)
0x34a48  ldarg.1
0x34a49  ldstr    aA70// "a70"
0x34a4e  ldarg.2
0x34a4f  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetBoolean(string name, bool defaultValue)
0x34a54  ldarg.1
0x34a55  ldstr    aA75// "a75"
0x34a5a  ldc.i4.0
0x34a5b  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetBoolean(string name, bool defaultValue)
0x34a60  call     void AddTermLabel::CreateCommand(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase databaseAdapter, class [mscorlib]System.Text.StringBuilder builder, class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> parameters, valuetype [mscorlib]System.Guid partitionId, int32 termId, int32 lcid, string label, bool isDefault, bool isKeyword, bool isFirstOnly, bool skipDuplicateCheck)
0x34a65  ret
0x34a66  ldarg.0
0x34a67  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::databaseAdapter
0x34a6c  ldarg.0
0x34a6d  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::commandBuilder
0x34a72  ldarg.0
0x34a73  call     instance class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::get_Parameters()
0x34a78  ldarg.0
0x34a79  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x34a7e  ldloc.1
0x34a7f  ldarg.1
0x34a80  ldstr    aA33// "a33"
0x34a85  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetInt(string name)
0x34a8a  ldarg.1
0x34a8b  ldstr    aA32// "a32"
0x34a90  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetString(string name)
0x34a95  call     void DeleteTermLabel::CreateCommand(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase databaseAdapter, class [mscorlib]System.Text.StringBuilder builder, class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> parameters, valuetype [mscorlib]System.Guid partitionId, int32 termId, int32 lcid, string label)
0x34a9a  ret
0x34a9b  ldc.i4   0x6F667876
0x34aa0  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x34aa5  ldc.i4.s 0xA
0x34aa7  ldstr    aInvalidTermLab// "Invalid term label action: {0}"
0x34aac  ldc.i4.1
0x34aad  newarr   [mscorlib]System.Object
0x34ab2  stloc.3
0x34ab3  ldloc.3
0x34ab4  ldc.i4.0
0x34ab5  ldloc.0
0x34ab6  box      Microsoft.SharePoint.Taxonomy.Internal.CommandAction
0x34abb  callvirt instance string [mscorlib]System.Object::ToString()
0x34ac0  stelem.ref
0x34ac1  ldloc.3
0x34ac2  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x34ac7  ldstr    aErrorinvalidba// "ErrorInvalidBackendDataXML"
0x34acc  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x34ad1  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x34ad6  throw
```
