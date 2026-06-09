# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::EnsureCatalogItemDataSourcesValid

- ea: `0x5c00`
- end: `0x5caa`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::EnsureCatalogItemDataSourcesValid`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x3000`
- `0x32c0`

## callees

- `0x4e60`
- `0x5bb0`
- `0x5c00`

## pseudocode

```c

```

## disassembly

```asm
0x5c00  ldstr    asc_25656// ""
0x5c05  stloc.0
0x5c06  ldarg.2
0x5c07  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Type()
0x5c0c  stloc.1
0x5c0d  ldloc.1
0x5c0e  ldc.i4.4
0x5c0f  bgt.s    loc_5C1B
0x5c11  ldloc.1
0x5c12  ldc.i4.2
0x5c13  beq.s    loc_5C27
0x5c15  ldloc.1
0x5c16  ldc.i4.4
0x5c17  beq.s    loc_5C27
0x5c19  br.s     loc_5C3E
0x5c1b  ldloc.1
0x5c1c  ldc.i4.s 9
0x5c1e  beq.s    loc_5C30
0x5c20  ldloc.1
0x5c21  ldc.i4.s 0xA
0x5c23  sub
0x5c24  ldc.i4.1
0x5c25  bgt.un.s loc_5C3E
0x5c27  ldarg.2
0x5c28  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0x5c2d  stloc.0
0x5c2e  br.s     loc_5C4A
0x5c30  ldarg.2
0x5c31  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Model.LinkedReport
0x5c36  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.LinkedReport::get_Link()
0x5c3b  stloc.0
0x5c3c  br.s     loc_5C4A
0x5c3e  ldarg.2
0x5c3f  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0x5c44  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.WrongItemTypeException::.ctor(string)
0x5c49  throw
0x5c4a  ldloc.0
0x5c4b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5c50  brtrue.s loc_5CA9
0x5c52  ldarg.0
0x5c53  ldarg.1
0x5c54  ldloc.0
0x5c55  call     instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetDataSourcesForCatalogItem(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string itemPath)
0x5c5a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::GetEnumerator()
0x5c5f  stloc.2
0x5c60  br.s     loc_5C95
0x5c62  ldloc.2
0x5c63  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::get_Current()
0x5c68  stloc.3
0x5c69  ldloc.3
0x5c6a  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialRetrievalType [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_CredentialRetrieval()
0x5c6f  ldc.i4.1
0x5c70  beq.s    loc_5C7A
0x5c72  ldloc.3
0x5c73  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CredentialRetrievalType [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_CredentialRetrieval()
0x5c78  brtrue.s loc_5C95
0x5c7a  ldarg.0
0x5c7b  ldarg.1
0x5c7c  ldloc.0
0x5c7d  ldloc.3
0x5c7e  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x5c83  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSourceCheckResult Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::TestDataSource(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string path, string dataSourceName)
0x5c88  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSourceCheckResult::get_IsSuccessful()
0x5c8d  brtrue.s loc_5C95
0x5c8f  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidDataSourceCredentialException::.ctor()
0x5c94  throw
0x5c95  ldloc.2
0x5c96  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5c9b  brtrue.s loc_5C62
0x5c9d  leave.s  loc_5CA9
0x5c9f  ldloc.2
0x5ca0  brfalse.s loc_5CA8
0x5ca2  ldloc.2
0x5ca3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5ca8  endfinally
0x5ca9  ret
```
