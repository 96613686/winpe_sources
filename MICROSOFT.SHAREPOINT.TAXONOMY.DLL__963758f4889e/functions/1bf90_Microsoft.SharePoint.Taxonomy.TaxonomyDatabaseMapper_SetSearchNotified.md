# Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::SetSearchNotified

- ea: `0x1bf90`
- end: `0x1c03e`
- name: `Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::SetSearchNotified`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x64b00`

## callees

- `0x1b420`
- `0x1bc00`
- `0x1beb0`
- `0x1bf90`
- `0x1e280`
- `0x1e2c0`
- `0x2a8f0`

## string_xrefs

- `0x1bfbe`: `MetadataWebServiceApplication.SetSearchNotified called for '{0}', rawPartitionId={1}.`
- `0x1c00b`: `MetadataWebServiceApplication.SetSearchNotified called for '{0}', rawPartitionId={1} but existing value of isSearchNotified is same as new value = {2}`

## pseudocode

```c

```

## disassembly

```asm
0x1bf90  ldarg.0
0x1bf91  call     instance class Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::get_DatabaseMapperContext()
0x1bf96  ldc.i4   0x4000
0x1bf9b  conv.i8
0x1bf9c  callvirt instance void Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext::CheckPermission(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.AccessControl.SPIisWebServiceApplicationRights requiredPermissions)
0x1bfa1  ldarg.0
0x1bfa2  ldarg.1
0x1bfa3  call     instance class Microsoft.SharePoint.Taxonomy.PartitionSettings Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::GetPartitionSettingsLocal(valuetype [mscorlib]System.Guid resolvedPartitionId)
0x1bfa8  stloc.0
0x1bfa9  ldloc.0
0x1bfaa  ldfld    bool Microsoft.SharePoint.Taxonomy.PartitionSettings::isSearchNotified
0x1bfaf  ldarg.2
0x1bfb0  beq.s    loc_1BFFF
0x1bfb2  ldc.i4   0x1018595
0x1bfb7  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1bfbc  ldc.i4.s 0x32
0x1bfbe  ldstr    aMetadatawebser_5// "MetadataWebServiceApplication.SetSearch"...
0x1bfc3  ldc.i4.2
0x1bfc4  newarr   [mscorlib]System.Object
0x1bfc9  stloc.2
0x1bfca  ldloc.2
0x1bfcb  ldc.i4.0
0x1bfcc  ldarg.0
0x1bfcd  call     instance class Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::get_DatabaseMapperContext()
0x1bfd2  callvirt instance string Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext::get_Name()
0x1bfd7  stelem.ref
0x1bfd8  ldloc.2
0x1bfd9  ldc.i4.1
0x1bfda  ldarg.1
0x1bfdb  box      [mscorlib]System.Guid
0x1bfe0  stelem.ref
0x1bfe1  ldloc.2
0x1bfe2  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x1bfe7  ldloc.0
0x1bfe8  ldarg.2
0x1bfe9  stfld    bool Microsoft.SharePoint.Taxonomy.PartitionSettings::isSearchNotified
0x1bfee  ldloc.0
0x1bfef  callvirt instance string Microsoft.SharePoint.Taxonomy.PartitionSettings::GenerateServiceSettingsXml()
0x1bff4  stloc.1
0x1bff5  ldarg.0
0x1bff6  ldarg.1
0x1bff7  ldloc.1
0x1bff8  ldc.i4.0
0x1bff9  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapper::SetServiceSettingsLocal(valuetype [mscorlib]System.Guid rawPartitionId, string settingsXml, bool unpublishAllPackages)
0x1bffe  ret
0x1bfff  ldc.i4   0x1018596
0x1c004  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1c009  ldc.i4.s 0x32
0x1c00b  ldstr    aMetadatawebser_6// "MetadataWebServiceApplication.SetSearch"...
0x1c010  ldc.i4.3
0x1c011  newarr   [mscorlib]System.Object
0x1c016  stloc.3
0x1c017  ldloc.3
0x1c018  ldc.i4.0
0x1c019  ldarg.0
0x1c01a  call     instance class Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext Microsoft.SharePoint.Taxonomy.TaxonomyDatabaseMapperBase::get_DatabaseMapperContext()
0x1c01f  callvirt instance string Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext::get_Name()
0x1c024  stelem.ref
0x1c025  ldloc.3
0x1c026  ldc.i4.1
0x1c027  ldarg.1
0x1c028  box      [mscorlib]System.Guid
0x1c02d  stelem.ref
0x1c02e  ldloc.3
0x1c02f  ldc.i4.2
0x1c030  ldarg.2
0x1c031  box      [mscorlib]System.Boolean
0x1c036  stelem.ref
0x1c037  ldloc.3
0x1c038  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x1c03d  ret
```
