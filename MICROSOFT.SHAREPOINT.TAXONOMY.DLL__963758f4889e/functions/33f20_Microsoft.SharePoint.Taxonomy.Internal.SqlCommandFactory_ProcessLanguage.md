# Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::ProcessLanguage

- ea: `0x33f20`
- end: `0x33fff`
- name: `Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::ProcessLanguage`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x33d30`

## callees

- `0x242a0`
- `0x26fd0`
- `0x27030`
- `0x2acd0`
- `0x33f20`
- `0x34f10`
- `0x34f30`
- `0x35910`
- `0x364e0`
- `0x36ca0`
- `0x579b0`

## string_xrefs

- `0x33f21`: `dataReader`
- `0x33fef`: `ErrorInvalidBackendDataXML`

## pseudocode

```c

```

## disassembly

```asm
0x33f20  ldarg.1
0x33f21  ldstr    aDatareader// "dataReader"
0x33f26  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x33f2b  ldarg.1
0x33f2c  call     valuetype Microsoft.SharePoint.Taxonomy.Internal.CommandAction Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::GetCurrentAction(class Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader dataReader)
0x33f31  stloc.0
0x33f32  ldarg.0
0x33f33  call     instance void Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::AppendCommandPrefix()
0x33f38  ldloc.0
0x33f39  stloc.1
0x33f3a  ldloc.1
0x33f3b  switch   loc_33F4E, loc_33F7D, loc_33FA0
0x33f4c  br.s     loc_33FC3
0x33f4e  ldarg.0
0x33f4f  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::databaseAdapter
0x33f54  ldarg.0
0x33f55  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::commandBuilder
0x33f5a  ldarg.0
0x33f5b  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x33f60  ldarg.1
0x33f61  ldstr    aA59// "a59"
0x33f66  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetInt(string name)
0x33f6b  ldarg.1
0x33f6c  ldstr    aA58// "a58"
0x33f71  ldc.i4.0
0x33f72  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetBoolean(string name, bool defaultValue)
0x33f77  call     void AddLanguage::CreateCommand(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase databaseAdapter, class [mscorlib]System.Text.StringBuilder builder, valuetype [mscorlib]System.Guid partitionId, int32 lcid, bool isDefault)
0x33f7c  ret
0x33f7d  ldarg.0
0x33f7e  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::databaseAdapter
0x33f83  ldarg.0
0x33f84  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::commandBuilder
0x33f89  ldarg.0
0x33f8a  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x33f8f  ldarg.1
0x33f90  ldstr    aA59// "a59"
0x33f95  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetInt(string name)
0x33f9a  call     void SetDefaultLanguage::CreateCommand(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase databaseAdapter, class [mscorlib]System.Text.StringBuilder builder, valuetype [mscorlib]System.Guid partitionId, int32 lcid)
0x33f9f  ret
0x33fa0  ldarg.0
0x33fa1  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::databaseAdapter
0x33fa6  ldarg.0
0x33fa7  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::commandBuilder
0x33fac  ldarg.0
0x33fad  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x33fb2  ldarg.1
0x33fb3  ldstr    aA59// "a59"
0x33fb8  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::GetInt(string name)
0x33fbd  call     void DeleteLanguage::CreateCommand(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase databaseAdapter, class [mscorlib]System.Text.StringBuilder builder, valuetype [mscorlib]System.Guid partitionId, int32 lcid)
0x33fc2  ret
0x33fc3  ldc.i4   0x6F667863
0x33fc8  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x33fcd  ldc.i4.s 0xA
0x33fcf  ldstr    aInvalidLanguag// "Invalid language action: {0}"
0x33fd4  ldc.i4.1
0x33fd5  newarr   [mscorlib]System.Object
0x33fda  stloc.2
0x33fdb  ldloc.2
0x33fdc  ldc.i4.0
0x33fdd  ldloc.0
0x33fde  box      Microsoft.SharePoint.Taxonomy.Internal.CommandAction
0x33fe3  callvirt instance string [mscorlib]System.Object::ToString()
0x33fe8  stelem.ref
0x33fe9  ldloc.2
0x33fea  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x33fef  ldstr    aErrorinvalidba// "ErrorInvalidBackendDataXML"
0x33ff4  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x33ff9  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x33ffe  throw
```
