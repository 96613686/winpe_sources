# Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::Process

- ea: `0x33d30`
- end: `0x33f1d`
- name: `Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::Process`
- size: `493`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x72760`
- `0x72a70`

## callees

- `0x1e2e0`
- `0x242a0`
- `0x27070`
- `0x270f0`
- `0x2acd0`
- `0x33d30`
- `0x33f20`
- `0x34000`
- `0x34170`
- `0x342e0`
- `0x34520`
- `0x347a0`
- `0x349a0`
- `0x34ae0`
- `0x34c20`
- `0x35040`
- `0x579b0`

## string_xrefs

- `0x33d31`: `dataReader`
- `0x33ece`: `ErrorInvalidBackendDataXML`
- `0x33eea`: `Non-command node in the XML is skipped: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x33d30  ldarg.1
0x33d31  ldstr    aDatareader// "dataReader"
0x33d36  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x33d3b  ldc.i4.1
0x33d3c  stloc.0
0x33d3d  ldarg.1
0x33d3e  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::get_LocalName()
0x33d43  ldstr    aT// "T"
0x33d48  ldc.i4.5
0x33d49  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x33d4e  brfalse.s loc_33D68
0x33d50  ldarg.0
0x33d51  ldfld    class ObjectContext Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::objectContext
0x33d56  callvirt instance void ObjectContext::ResetContext()
0x33d5b  ldarg.0
0x33d5c  ldarg.1
0x33d5d  ldarg.2
0x33d5e  call     instance void Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::ProcessTerm(class Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader dataReader, bool isRestrictedWrite)
0x33d63  br       loc_33F07
0x33d68  ldarg.1
0x33d69  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::get_LocalName()
0x33d6e  ldstr    aTm// "TM"
0x33d73  ldc.i4.5
0x33d74  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x33d79  brfalse.s loc_33D88
0x33d7b  ldarg.0
0x33d7c  ldarg.1
0x33d7d  ldarg.2
0x33d7e  call     instance void Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::ProcessTermSetMembership(class Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader dataReader, bool isRestrictedWrite)
0x33d83  br       loc_33F07
0x33d88  ldarg.1
0x33d89  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::get_LocalName()
0x33d8e  ldstr    aTl// "TL"
0x33d93  ldc.i4.5
0x33d94  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x33d99  brfalse.s loc_33DA8
0x33d9b  ldarg.0
0x33d9c  ldarg.1
0x33d9d  ldarg.2
0x33d9e  call     instance void Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::ProcessTermLabel(class Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader dataReader, bool isRestrictedWrite)
0x33da3  br       loc_33F07
0x33da8  ldarg.1
0x33da9  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::get_LocalName()
0x33dae  ldstr    aTd// "TD"
0x33db3  ldc.i4.5
0x33db4  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x33db9  brfalse.s loc_33DC7
0x33dbb  ldarg.0
0x33dbc  ldarg.1
0x33dbd  call     instance void Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::ProcessTermDescription(class Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader dataReader)
0x33dc2  br       loc_33F07
0x33dc7  ldarg.1
0x33dc8  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::get_LocalName()
0x33dcd  ldstr    aTp// "TP"
0x33dd2  ldc.i4.5
0x33dd3  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x33dd8  brfalse.s loc_33DE6
0x33dda  ldarg.0
0x33ddb  ldarg.1
0x33ddc  call     instance void Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::ProcessTermProperty(class Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader dataReader)
0x33de1  br       loc_33F07
0x33de6  ldarg.1
0x33de7  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::get_LocalName()
0x33dec  ldstr    aL// "L"
0x33df1  ldc.i4.5
0x33df2  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x33df7  brfalse.s loc_33E10
0x33df9  ldarg.0
0x33dfa  ldfld    class ObjectContext Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::objectContext
0x33dff  callvirt instance void ObjectContext::ResetContext()
0x33e04  ldarg.0
0x33e05  ldarg.1
0x33e06  call     instance void Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::ProcessLanguage(class Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader dataReader)
0x33e0b  br       loc_33F07
0x33e10  ldarg.1
0x33e11  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::get_LocalName()
0x33e16  ldstr    aG// "G"
0x33e1b  ldc.i4.5
0x33e1c  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x33e21  brfalse.s loc_33E3A
0x33e23  ldarg.0
0x33e24  ldfld    class ObjectContext Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::objectContext
0x33e29  callvirt instance void ObjectContext::ResetContext()
0x33e2e  ldarg.0
0x33e2f  ldarg.1
0x33e30  call     instance void Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::ProcessGroup(class Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader dataReader)
0x33e35  br       loc_33F07
0x33e3a  ldarg.1
0x33e3b  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::get_LocalName()
0x33e40  ldstr    aTs// "TS"
0x33e45  ldc.i4.5
0x33e46  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x33e4b  brfalse.s loc_33E64
0x33e4d  ldarg.0
0x33e4e  ldfld    class ObjectContext Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::objectContext
0x33e53  callvirt instance void ObjectContext::ResetContext()
0x33e58  ldarg.0
0x33e59  ldarg.1
0x33e5a  call     instance void Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::ProcessTermSet(class Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader dataReader)
0x33e5f  br       loc_33F07
0x33e64  ldarg.1
0x33e65  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::get_LocalName()
0x33e6a  ldstr    aP_0// "P"
0x33e6f  callvirt instance bool [mscorlib]System.String::Equals(string)
0x33e74  brfalse.s loc_33E8A
0x33e76  ldarg.0
0x33e77  ldfld    class ObjectContext Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::objectContext
0x33e7c  callvirt instance void ObjectContext::ResetContext()
0x33e81  ldarg.0
0x33e82  ldarg.1
0x33e83  call     instance void Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::ProcessPermissions(class Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader dataReader)
0x33e88  br.s     loc_33F07
0x33e8a  ldarg.1
0x33e8b  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::get_LocalName()
0x33e90  ldstr    aPartition// "Partition"
0x33e95  callvirt instance bool [mscorlib]System.String::Equals(string)
0x33e9a  brfalse.s loc_33EDE
0x33e9c  ldarg.0
0x33e9d  ldfld    class ObjectContext Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::objectContext
0x33ea2  callvirt instance void ObjectContext::ResetContext()
0x33ea7  ldarg.1
0x33ea8  ldstr    aId// "Id"
0x33ead  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x33eb2  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::TryGetGuid(string name, valuetype [mscorlib]System.Guid defaultValue)
0x33eb7  stloc.1
0x33eb8  ldarg.3
0x33eb9  ldloc.1
0x33eba  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext::ResolvePartitionId(valuetype [mscorlib]System.Guid rawPartitionId)
0x33ebf  stloc.2
0x33ec0  ldarg.0
0x33ec1  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::partitionId
0x33ec6  ldloc.2
0x33ec7  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x33ecc  brfalse.s loc_33F07
0x33ece  ldstr    aErrorinvalidba// "ErrorInvalidBackendDataXML"
0x33ed3  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x33ed8  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message)
0x33edd  throw
0x33ede  ldc.i4   0x6F667778
0x33ee3  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x33ee8  ldc.i4.s 0x64
0x33eea  ldstr    aNonCommandNode// "Non-command node in the XML is skipped:"...
0x33eef  ldc.i4.1
0x33ef0  newarr   [mscorlib]System.Object
0x33ef5  stloc.3
0x33ef6  ldloc.3
0x33ef7  ldc.i4.0
0x33ef8  ldarg.1
0x33ef9  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::get_LocalName()
0x33efe  stelem.ref
0x33eff  ldloc.3
0x33f00  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x33f05  ldc.i4.0
0x33f06  stloc.0
0x33f07  ldloc.0
0x33f08  brfalse.s loc_33F1B
0x33f0a  ldarg.0
0x33f0b  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::commandBuilder
0x33f10  ldstr    aIfError0OrRetv// "IF (@@ERROR<>0 OR @retVal<>0)  RETURN"
0x33f15  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x33f1a  pop
0x33f1b  ldloc.0
0x33f1c  ret
```
