# Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseAction_14_0_6_0::Upgrade

- ea: `0x68370`
- end: `0x683a6`
- name: `Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseAction_14_0_6_0::Upgrade`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x68386`: `\n        IF EXISTS (	SELECT \n                        TOP 1 index_id \n                    FROM \n                        sys.Indexes\n                    WHERE \n                        object_id = OBJECT_ID(N'dbo.ECMTermSet')\n                    AND\n                        name = 'IX_ECMTermSet_Name')\n        BEGIN\n            DROP INDEX dbo.ECMTermSet.IX_ECMTermSet_Name\n        END\n        GO\n\n        DECLARE @maxLength int\n        SELECT \n            @maxLength = m`
- `0x6839b`: `Updated the ECMTermSet name column.`

## pseudocode

```c

```
