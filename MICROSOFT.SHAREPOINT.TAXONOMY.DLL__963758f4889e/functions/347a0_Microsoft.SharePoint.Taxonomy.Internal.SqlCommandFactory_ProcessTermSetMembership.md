# Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::ProcessTermSetMembership

- ea: `0x347a0`
- end: `0x34994`
- name: `Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::ProcessTermSetMembership`
- size: `500`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x33d30`

## callees

- `0x242a0`
- `0x26ee0`
- `0x26fd0`
- `0x27010`
- `0x27090`
- `0x2acd0`
- `0x347a0`
- `0x34f10`
- `0x34f30`
- `0x34f80`
- `0x360d0`
- `0x36a70`
- `0x37000`
- `0x37290`
- `0x579b0`

## string_xrefs

- `0x347a1`: `dataReader`
- `0x347d2`: `ErrorInvalidBackendDataXML`
- `0x34984`: `ErrorInvalidBackendDataXML`

## pseudocode

```c

```

## disassembly

```asm
0x347a0  ldarg.1
0x347a1  ldstr    aDatareader// "dataReader"
0x347a6  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x347ab  ldarg.1
0x347ac  call     valuetype Microsoft.SharePoint.Taxonomy.Internal.CommandAction Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::GetCurrentAction(class Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader dataReader)
0x347b1  stloc.0
0x347b2  ldarg.0
0x347b3  call     instance int32 Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::get_CurrentTermId()
0x347b8  stloc.1
0x347b9  ldloc.1
0x347ba  brtrue.s loc_347E2
0x347bc  ldc.i4   0x3134386C
0x347c1  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x347c6  ldc.i4.s 0xA
0x347c8  ldstr    aTermWasNotFoun// "Term was not found for the TermSet memb"...
0x347cd  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x347d2  ldstr    aErrorinvalidba// "ErrorInvalidBackendDataXML"
0x347d7  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x347dc  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x347e1  throw
0x347e2  ldarg.0
0x347e3  call     instance void Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::AppendCommandPrefix()
0x347e8  ldloc.0
0x347e9  stloc.2
0x347ea  ldloc.2
0x347eb  switch   loc_34805, loc_34863, loc_34934, loc_348C6
0x34800  br       loc_34958
0x34805  ldarg.0
0x34806  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::databaseAdapter
0x3480b  ldarg.0
0x3480c  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::commandBuilder
0x34811  ldarg.0
0x34812  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x34817  ldarg.1
0x34818  ldstr    aA24// "a24"
0x3481d  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetInt(string name)
0x34822  ldloc.1
0x34823  ldarg.1
0x34824  ldstr    aA25// "a25"
0x34829  ldc.i4.0
0x3482a  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetInt(string name, int32 defaultValue)
0x3482f  ldarg.1
0x34830  ldstr    aA17// "a17"
0x34835  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetBoolean(string name)
0x3483a  ldarg.1
0x3483b  ldstr    aA67// "a67"
0x34840  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetString(string name)
0x34845  ldarg.1
0x34846  ldstr    aA26// "a26"
0x3484b  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetBoolean(string name)
0x34850  ldarg.2
0x34851  ldarg.1
0x34852  ldstr    aA74// "a74"
0x34857  ldc.i4.0
0x34858  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetInt(string name, int32 defaultValue)
0x3485d  call     void AddTermSetMembership::CreateCommand(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase databaseAdapter, class [mscorlib]System.Text.StringBuilder builder, valuetype [mscorlib]System.Guid partitionId, int32 termSetId, int32 termId, int32 parentTermId, bool availableForTagging, string customSortOrder, bool isSource, bool isRestrictedToOpenTermSets, int32 pinSourceTermSetId)
0x34862  ret
0x34863  ldarg.0
0x34864  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::databaseAdapter
0x34869  ldarg.0
0x3486a  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::commandBuilder
0x3486f  ldarg.0
0x34870  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::parameters
0x34875  ldarg.0
0x34876  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x3487b  ldarg.1
0x3487c  ldstr    aA24// "a24"
0x34881  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetInt(string name)
0x34886  ldloc.1
0x34887  ldarg.1
0x34888  ldstr    aA25// "a25"
0x3488d  ldc.i4.0
0x3488e  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetInt(string name, int32 defaultValue)
0x34893  ldarg.1
0x34894  ldstr    aA17// "a17"
0x34899  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetBoolean(string name)
0x3489e  ldarg.1
0x3489f  ldstr    aA67// "a67"
0x348a4  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetString(string name)
0x348a9  ldarg.1
0x348aa  ldstr    aA26// "a26"
0x348af  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetBoolean(string name)
0x348b4  ldarg.1
0x348b5  ldstr    aA74// "a74"
0x348ba  ldc.i4.0
0x348bb  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetInt(string name, int32 defaultValue)
0x348c0  call     void UpdateTermSetMembership::CreateCommand(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase databaseAdapter, class [mscorlib]System.Text.StringBuilder builder, class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> parameters, valuetype [mscorlib]System.Guid partitionId, int32 termSetId, int32 termId, int32 parentTermId, bool availableForTagging, string customSortOrder, bool isSource, int32 pinSourceTermSetId)
0x348c5  ret
0x348c6  ldarg.0
0x348c7  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::databaseAdapter
0x348cc  ldarg.0
0x348cd  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::commandBuilder
0x348d2  ldarg.0
0x348d3  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::parameters
0x348d8  ldarg.0
0x348d9  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x348de  ldarg.1
0x348df  ldstr    aA24// "a24"
0x348e4  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetInt(string name)
0x348e9  ldloc.1
0x348ea  ldarg.1
0x348eb  ldstr    aA25// "a25"
0x348f0  ldc.i4.0
0x348f1  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetInt(string name, int32 defaultValue)
0x348f6  ldarg.1
0x348f7  ldstr    aA17// "a17"
0x348fc  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetBoolean(string name)
0x34901  ldarg.1
0x34902  ldstr    aA67// "a67"
0x34907  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetString(string name)
0x3490c  ldarg.1
0x3490d  ldstr    aA26// "a26"
0x34912  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetBoolean(string name)
0x34917  ldarg.1
0x34918  ldstr    aA46// "a46"
0x3491d  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetInt(string name)
0x34922  ldarg.1
0x34923  ldstr    aA47// "a47"
0x34928  ldc.i4.0
0x34929  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetInt(string name, int32 defaultValue)
0x3492e  call     void MoveTermSetMembership::CreateCommand(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase databaseAdapter, class [mscorlib]System.Text.StringBuilder builder, class [mscorlib]System.Collections.Generic.List`1<class [System.Data]System.Data.SqlClient.SqlParameter> parameters, valuetype [mscorlib]System.Guid partitionId, int32 termSetId, int32 termId, int32 parentTermId, bool availableForTagging, string customSortOrder, bool isSource, int32 sourceTermSetId, int32 sourceParentTermId)
0x34933  ret
0x34934  ldarg.0
0x34935  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::databaseAdapter
0x3493a  ldarg.0
0x3493b  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::commandBuilder
0x34940  ldarg.0
0x34941  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x34946  ldloc.1
0x34947  ldarg.1
0x34948  ldstr    aA24// "a24"
0x3494d  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetInt(string name)
0x34952  call     void DeleteTerm::CreateCommand(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase databaseAdapter, class [mscorlib]System.Text.StringBuilder builder, valuetype [mscorlib]System.Guid partitionId, int32 termId, int32 termSetId)
0x34957  ret
0x34958  ldc.i4   0x6F667875
0x3495d  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x34962  ldc.i4.s 0xA
0x34964  ldstr    aInvalidTermMem// "Invalid term membership action: {0}"
0x34969  ldc.i4.1
0x3496a  newarr   [mscorlib]System.Object
0x3496f  stloc.3
0x34970  ldloc.3
0x34971  ldc.i4.0
0x34972  ldloc.0
0x34973  box      Microsoft.SharePoint.Taxonomy.Internal.CommandAction
0x34978  callvirt instance string [mscorlib]System.Object::ToString()
0x3497d  stelem.ref
0x3497e  ldloc.3
0x3497f  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x34984  ldstr    aErrorinvalidba// "ErrorInvalidBackendDataXML"
0x34989  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x3498e  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x34993  throw
```
