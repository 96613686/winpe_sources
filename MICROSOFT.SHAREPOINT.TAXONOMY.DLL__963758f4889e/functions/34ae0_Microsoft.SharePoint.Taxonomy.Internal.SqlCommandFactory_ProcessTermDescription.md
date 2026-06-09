# Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::ProcessTermDescription

- ea: `0x34ae0`
- end: `0x34c1d`
- name: `Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::ProcessTermDescription`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x33d30`

## callees

- `0x242a0`
- `0x26fd0`
- `0x27010`
- `0x2acd0`
- `0x34ae0`
- `0x34e00`
- `0x34f10`
- `0x34f30`
- `0x34f60`
- `0x34f80`
- `0x363f0`
- `0x36bb0`
- `0x37150`
- `0x579b0`

## string_xrefs

- `0x34ae1`: `dataReader`
- `0x34b12`: `ErrorInvalidBackendDataXML`
- `0x34c0d`: `ErrorInvalidBackendDataXML`

## pseudocode

```c

```

## disassembly

```asm
0x34ae0  ldarg.1
0x34ae1  ldstr    aDatareader// "dataReader"
0x34ae6  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x34aeb  ldarg.1
0x34aec  call     valuetype Microsoft.SharePoint.Taxonomy.Internal.CommandAction Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::GetCurrentAction(class Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader dataReader)
0x34af1  stloc.0
0x34af2  ldarg.0
0x34af3  call     instance int32 Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::get_CurrentTermId()
0x34af8  stloc.1
0x34af9  ldloc.1
0x34afa  brtrue.s loc_34B22
0x34afc  ldc.i4   0x3134386E
0x34b01  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x34b06  ldc.i4.s 0xA
0x34b08  ldstr    aTermWasNotFoun_1// "Term was not found for the Term descrip"...
0x34b0d  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x34b12  ldstr    aErrorinvalidba// "ErrorInvalidBackendDataXML"
0x34b17  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x34b1c  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x34b21  throw
0x34b22  ldarg.0
0x34b23  call     instance void Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::AppendCommandPrefix()
0x34b28  ldloc.0
0x34b29  stloc.2
0x34b2a  ldloc.2
0x34b2b  switch   loc_34B41, loc_34B88, loc_34BBD
0x34b3c  br       loc_34BE1
0x34b41  ldarg.0
0x34b42  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::databaseAdapter
0x34b47  ldarg.0
0x34b48  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::commandBuilder
0x34b4d  ldarg.0
0x34b4e  call     instance class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::get_Parameters()
0x34b53  ldarg.0
0x34b54  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x34b59  ldloc.1
0x34b5a  ldarg.1
0x34b5b  ldstr    aA33// "a33"
0x34b60  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetInt(string name)
0x34b65  ldarg.1
0x34b66  ldstr    aA11// "a11"
0x34b6b  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetString(string name)
0x34b70  call     void AddTermDescription::CreateCommand(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase databaseAdapter, class [mscorlib]System.Text.StringBuilder builder, class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> parameters, valuetype [mscorlib]System.Guid partitionId, int32 termId, int32 lcid, string description)
0x34b75  ldarg.0
0x34b76  ldstr    aTaxonomyomcust// "TaxonomyOMCustomizeTermDescription"
0x34b7b  ldarg.0
0x34b7c  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x34b81  ldnull
0x34b82  call     instance void Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::AddToEngagementLogQueue(string engagementName, valuetype [mscorlib]System.Guid subscriptionId, string user)
0x34b87  ret
0x34b88  ldarg.0
0x34b89  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::databaseAdapter
0x34b8e  ldarg.0
0x34b8f  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::commandBuilder
0x34b94  ldarg.0
0x34b95  call     instance class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::get_Parameters()
0x34b9a  ldarg.0
0x34b9b  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x34ba0  ldloc.1
0x34ba1  ldarg.1
0x34ba2  ldstr    aA33// "a33"
0x34ba7  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetInt(string name)
0x34bac  ldarg.1
0x34bad  ldstr    aA11// "a11"
0x34bb2  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetString(string name)
0x34bb7  call     void UpdateTermDescription::CreateCommand(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase databaseAdapter, class [mscorlib]System.Text.StringBuilder builder, class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> parameters, valuetype [mscorlib]System.Guid partitionId, int32 termId, int32 lcid, string description)
0x34bbc  ret
0x34bbd  ldarg.0
0x34bbe  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::databaseAdapter
0x34bc3  ldarg.0
0x34bc4  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::commandBuilder
0x34bc9  ldarg.0
0x34bca  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x34bcf  ldloc.1
0x34bd0  ldarg.1
0x34bd1  ldstr    aA33// "a33"
0x34bd6  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetInt(string name)
0x34bdb  call     void DeleteTermDescription::CreateCommand(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase databaseAdapter, class [mscorlib]System.Text.StringBuilder builder, valuetype [mscorlib]System.Guid partitionId, int32 termId, int32 lcid)
0x34be0  ret
0x34be1  ldc.i4   0x6F667877
0x34be6  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x34beb  ldc.i4.s 0xA
0x34bed  ldstr    aInvalidTermDes// "Invalid term description action: {0}"
0x34bf2  ldc.i4.1
0x34bf3  newarr   [mscorlib]System.Object
0x34bf8  stloc.3
0x34bf9  ldloc.3
0x34bfa  ldc.i4.0
0x34bfb  ldloc.0
0x34bfc  box      Microsoft.SharePoint.Taxonomy.Internal.CommandAction
0x34c01  callvirt instance string [mscorlib]System.Object::ToString()
0x34c06  stelem.ref
0x34c07  ldloc.3
0x34c08  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x34c0d  ldstr    aErrorinvalidba// "ErrorInvalidBackendDataXML"
0x34c12  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x34c17  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x34c1c  throw
```
