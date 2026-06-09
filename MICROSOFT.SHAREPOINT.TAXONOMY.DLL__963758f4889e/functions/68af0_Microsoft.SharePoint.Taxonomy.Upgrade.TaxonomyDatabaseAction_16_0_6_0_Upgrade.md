# Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseAction_16_0_6_0::Upgrade

- ea: `0x68af0`
- end: `0x68b26`
- name: `Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseAction_16_0_6_0::Upgrade`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x68afb`: `Updating the ECMServiceSettings table with a new column.`
- `0x68b06`: `\nIF NOT EXISTS (SELECT 1 FROM sys.all_columns AS SAC\nWHERE \n    SAC.object_id = OBJECT_ID(N'[dbo].[ECMServiceSettings]') AND\n    SAC.name = 'IsReadOnly')\nBEGIN\n    ALTER TABLE [dbo].[ECMServiceSettings] ADD\n[IsReadOnly] bit NULL DEFAULT 0\n\nIF EXISTS (SELECT TOP 1 1 FROM sys.objects WHERE object_id = object_id(N'[dbo].[TVF_ECMServiceSettings_PartitionId]') AND type = 'IF')\n    EXEC sys.sp_refreshsqlmodule '[dbo].[TVF_ECMServiceSettings_PartitionId]'\n\n\nDECLARE @ViewName s`
- `0x68b1b`: `Updated the ECMServiceSettings table with a new column.`

## pseudocode

```c

```

## disassembly

```asm
0x68af0  ldarg.0
0x68af1  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPLog [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPAction::get_Log()
0x68af6  ldc.i4   0x69F4E2
0x68afb  ldstr    aUpdatingTheEcm_2// "Updating the ECMServiceSettings table w"...
0x68b00  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32, string)
0x68b05  ldarg.0
0x68b06  ldstr    aIfNotExistsSel_1// "\r\nIF NOT EXISTS (SELECT 1 FROM sys.al"...
0x68b0b  call     instance void [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPDatabaseAction::ExecuteSql(string)
0x68b10  ldarg.0
0x68b11  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPLog [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPAction::get_Log()
0x68b16  ldc.i4   0x69F4E3
0x68b1b  ldstr    aUpdatedTheEcms// "Updated the ECMServiceSettings table wi"...
0x68b20  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32, string)
0x68b25  ret
```
