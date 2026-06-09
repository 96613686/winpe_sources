# Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseAction_15_0_11_0::Upgrade

- ea: `0x68850`
- end: `0x68886`
- name: `Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseAction_15_0_11_0::Upgrade`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x68866`: `\nIF  EXISTS (SELECT * FROM sys.indexes WHERE object_id = OBJECT_ID(N'[dbo].[ECMChangeLog]') AND name = N'IX_ECMChangeLog_Time')\nDROP INDEX [IX_ECMChangeLog_Time] ON [dbo].[ECMChangeLog] \nGO\n\nIF  EXISTS (SELECT * FROM sys.indexes WHERE object_id = OBJECT_ID(N'[dbo].[ECMChangeLog]') AND name = N'IX_ECMChangeLog_Partition')\nDROP INDEX [IX_ECMChangeLog_Partition] ON [dbo].[ECMChangeLog] \nGO\n\nIF EXISTS (SELECT * FROM sysobjects WHERE id = object_id(N'[dbo].[' + N'trigger_ECM_OnUpdat`
- `0x6887b`: `Updated ECMTerm and ECMChangeLog and ECMTermProperty tables.`

## pseudocode

```c

```
