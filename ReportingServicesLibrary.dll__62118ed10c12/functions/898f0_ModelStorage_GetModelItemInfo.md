# ModelStorage::GetModelItemInfo

- ea: `0x898f0`
- end: `0x89a14`
- name: `ModelStorage::GetModelItemInfo`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x89330`

## callees

- `0x22e10`
- `0x24cd0`
- `0x2f500`
- `0x49ae0`
- `0x898f0`

## string_xrefs

- `0x898fe`: `@Path`
- `0x8991c`: `@UseUpdateLock`
- `0x89984`: `GetModelItemInfo: No model item security records returned.`

## pseudocode

```c

```

## disassembly

```asm
0x898f0  ldarg.0
0x898f1  ldstr    aGetmodelitemin// "GetModelItemInfo"
0x898f6  ldnull
0x898f7  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x898fc  stloc.0
0x898fd  ldloc.0
0x898fe  ldstr    aPath// "@Path"
0x89903  ldc.i4.s 0xC
0x89905  ldarg.1
0x89906  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext Microsoft.ReportingServices.Library.CatalogItem::get_ItemContext()
0x8990b  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::get_CatalogItemPath()
0x89910  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x89915  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x8991a  pop
0x8991b  ldloc.0
0x8991c  ldstr    aUseupdatelock// "@UseUpdateLock"
0x89921  ldc.i4.2
0x89922  ldarg.2
0x89923  box      [mscorlib]System.Boolean
0x89928  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x8992d  pop
0x8992e  ldloc.0
0x8992f  callvirt instance class [System.Data]System.Data.IDataReader [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader()
0x89934  stloc.1
0x89935  ldloc.1
0x89936  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x8993b  brtrue.s loc_89953
0x8993d  ldarg.1
0x8993e  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext Microsoft.ReportingServices.Library.CatalogItem::get_ItemContext()
0x89943  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_OriginalItemPath()
0x89948  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x8994d  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ItemNotFoundException::.ctor(string)
0x89952  throw
0x89953  ldloc.1
0x89954  ldc.i4.0
0x89955  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x8995a  brtrue.s loc_89969
0x8995c  ldarg.1
0x8995d  ldloc.1
0x8995e  ldc.i4.0
0x8995f  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.IDataRecord::GetGuid(int32)
0x89964  stfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.ModelCatalogItem::m_binarySnapshotID
0x89969  ldloc.1
0x8996a  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x8996f  brfalse.s loc_8997C
0x89971  ldstr    aGetmodelinfoMo// "GetModelInfo: More than one model found"...
0x89976  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x8997b  throw
0x8997c  ldloc.1
0x8997d  callvirt instance bool [System.Data]System.Data.IDataReader::NextResult()
0x89982  brtrue.s loc_899E2
0x89984  ldstr    aGetmodelitemin_0// "GetModelItemInfo: No model item securit"...
0x89989  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x8998e  throw
0x8998f  ldloc.1
0x89990  ldc.i4.0
0x89991  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0x89996  stloc.2
0x89997  ldnull
0x89998  stloc.3
0x89999  ldloc.1
0x8999a  ldc.i4.1
0x8999b  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x899a0  brtrue.s loc_899AA
0x899a2  ldloc.1
0x899a3  ldc.i4.1
0x899a4  call     unsigned int8[] [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.DataReaderHelper::ReadAllBytes(class [System.Data]System.Data.IDataRecord, int32)
0x899a9  stloc.3
0x899aa  ldnull
0x899ab  stloc.s  4
0x899ad  ldloc.1
0x899ae  ldc.i4.2
0x899af  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x899b4  brtrue.s loc_899C1
0x899b6  ldloc.1
0x899b7  ldc.i4.2
0x899b8  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0x899bd  stloc.s  4
0x899bf  br.s     loc_899C8
0x899c1  call     string Microsoft.ReportingServices.Library.Security::ProduceEmptyPolicy()
0x899c6  stloc.s  4
0x899c8  ldarg.1
0x899c9  callvirt instance class Microsoft.ReportingServices.Library.ModelItemPolicyCollection Microsoft.ReportingServices.Library.ModelCatalogItem::get_ModelItemPolicies()
0x899ce  ldloc.2
0x899cf  ldloc.3
0x899d0  ldloc.s  4
0x899d2  ldarg.1
0x899d3  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext Microsoft.ReportingServices.Library.CatalogItem::get_ItemContext()
0x899d8  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_ItemPath()
0x899dd  callvirt instance void Microsoft.ReportingServices.Library.ModelItemPolicyCollection::AddPolicyRoot(string modelItemID, unsigned int8[] securityDescriptor, string xmlPolicy, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath itemPath)
0x899e2  ldloc.1
0x899e3  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x899e8  brtrue.s loc_8998F
0x899ea  ldloc.1
0x899eb  callvirt instance bool [System.Data]System.Data.IDataReader::NextResult()
0x899f0  brfalse.s loc_899FD
0x899f2  ldstr    aGetmodelitemin_1// "GetModelItemInfo: Found third result se"...
0x899f7  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x899fc  throw
0x899fd  leave.s  loc_89A13
0x899ff  ldloc.1
0x89a00  brfalse.s loc_89A08
0x89a02  ldloc.1
0x89a03  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x89a08  endfinally
0x89a09  ldloc.0
0x89a0a  brfalse.s loc_89A12
0x89a0c  ldloc.0
0x89a0d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x89a12  endfinally
0x89a13  ret
```
