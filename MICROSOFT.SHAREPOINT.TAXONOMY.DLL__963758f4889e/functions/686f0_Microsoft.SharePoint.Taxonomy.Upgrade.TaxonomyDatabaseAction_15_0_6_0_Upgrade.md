# Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseAction_15_0_6_0::Upgrade

- ea: `0x686f0`
- end: `0x68726`
- name: `Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseAction_15_0_6_0::Upgrade`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x6871b`: `Updated the ECMChangeLog index.`
- `0x68706`: `\n        IF EXISTS (	SELECT \n                        TOP 1 ic.index_id \n                    FROM\n                        sys.index_columns ic\n                    INNER JOIN\n                        sys.Columns c\n                    ON \n                        ic.object_id = c.object_id\n                    AND\n                        ic.object_id = OBJECT_ID(N'dbo.ECMChangeLog')\n                    AND\n                        ic.column_id = c.column_id\n                   `

## pseudocode

```c

```
