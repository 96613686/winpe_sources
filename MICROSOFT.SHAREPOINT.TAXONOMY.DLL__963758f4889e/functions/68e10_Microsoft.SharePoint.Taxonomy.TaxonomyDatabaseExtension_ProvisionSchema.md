# Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseExtension::ProvisionSchema

- ea: `0x68e10`
- end: `0x68e65`
- name: `Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseExtension::ProvisionSchema`
- size: `85`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x68cf0`
- `0x68d20`

## callees

- `0x17970`
- `0x1b5f0`
- `0x38c50`
- `0x68e10`
- `0x68e70`

## string_xrefs

- `0x68e1c`: `TaxonomyDatabaseExtension.ProvisionSchema() called`
- `0x68e5a`: `TaxonomyDatabaseExtension.ProvisionSchema() completed successfully`

## pseudocode

```c

```

## disassembly

```asm
0x68e10  ldc.i4   0x6CE1DE
0x68e15  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x68e1a  ldc.i4.s 0x14
0x68e1c  ldstr    aTaxonomydataba_3// "TaxonomyDatabaseExtension.ProvisionSche"...
0x68e21  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x68e26  ldarg.0
0x68e27  call     class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapter Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::GetAdapterForContentDatabase(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase contentDatabase)
0x68e2c  stloc.0
0x68e2d  ldloc.0
0x68e2e  ldc.i4.0
0x68e2f  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyTransactionalSqlSession Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase::CreateTransactionalSqlSession(valuetype Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseConnectionType connectionType)
0x68e34  stloc.1
0x68e35  ldloc.0
0x68e36  ldloc.1
0x68e37  call     void Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseExtension::ProvisionSchema(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapter databaseAdapter, class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.ISqlSession sqlSession)
0x68e3c  ldloc.1
0x68e3d  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.TaxonomyTransactionalSqlSession::CommitTransaction()
0x68e42  leave.s  loc_68E4E
0x68e44  ldloc.1
0x68e45  brfalse.s loc_68E4D
0x68e47  ldloc.1
0x68e48  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x68e4d  endfinally
0x68e4e  ldc.i4   0x6CE1DF
0x68e53  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x68e58  ldc.i4.s 0x14
0x68e5a  ldstr    aTaxonomydataba_4// "TaxonomyDatabaseExtension.ProvisionSche"...
0x68e5f  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x68e64  ret
```
