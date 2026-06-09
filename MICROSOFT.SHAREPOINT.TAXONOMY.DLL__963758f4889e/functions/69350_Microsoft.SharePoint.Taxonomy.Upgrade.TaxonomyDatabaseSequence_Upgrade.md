# Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseSequence::Upgrade

- ea: `0x69350`
- end: `0x693b0`
- name: `Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseSequence::Upgrade`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x68280`
- `0x692c0`
- `0x69350`

## string_xrefs

- `0x69375`: `Executing script to update the stored procs`
- `0x6938a`: `taxupdateprocs.sql`
- `0x693a5`: `Finish upgrading MetadataWebServiceDatabase.`

## pseudocode

```c

```

## disassembly

```asm
0x69350  ldarg.0
0x69351  call     instance class [mscorlib]System.Version [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPDatabaseSequence::get_SchemaVersion()
0x69356  stloc.0
0x69357  ldarg.0
0x69358  call     instance void [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPDatabaseSequence::Upgrade()
0x6935d  ldloc.0
0x6935e  ldsfld   class [mscorlib]System.Version Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseSequence::LastVersionWithLegacyBehavior
0x69363  call     bool [mscorlib]System.Version::op_LessThan(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x69368  brfalse.s loc_693AF
0x6936a  ldarg.0
0x6936b  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPLog [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPDelegate::get_Log()
0x69370  ldc.i4   0x6867DC
0x69375  ldstr    aExecutingScrip// "Executing script to update the stored p"...
0x6937a  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32, string)
0x6937f  ldarg.0
0x69380  call     instance class [Microsoft.Office.Server]Microsoft.Office.Server.Data.SqlSession Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseSequence::get_SqlSession()
0x69385  call     string Microsoft.SharePoint.Taxonomy.Upgrade.MetadataDatabaseUpgradeSqlScripts::get_SqlScriptPath()
0x6938a  ldstr    aTaxupdateprocs// "taxupdateprocs.sql"
0x6938f  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x69394  callvirt instance void [Microsoft.Office.Server]Microsoft.Office.Server.Data.SqlSession::ExecuteScript(string)
0x69399  ldc.i4   0x6867DD
0x6939e  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x693a3  ldc.i4.s 0x14
0x693a5  ldstr    aFinishUpgradin_0// "Finish upgrading MetadataWebServiceData"...
0x693aa  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x693af  ret
```
