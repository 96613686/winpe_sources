# Microsoft.ReportingServices.Library.DBInterface::CreateOrUpdateContentCache

- ea: `0x75c0`
- end: `0x76ac`
- name: `Microsoft.ReportingServices.Library.DBInterface::CreateOrUpdateContentCache`
- size: `236`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x75c0`

## string_xrefs

- `0x75c1`: `CreateOrUpdateContentCache`
- `0x7695`: `Error in CreateOrUpdateContentCache: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x75c0  ldarg.0
0x75c1  ldstr    aCreateorupdate// "CreateOrUpdateContentCache"
0x75c6  ldnull
0x75c7  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x75cc  stloc.0
0x75cd  ldloc.0
0x75ce  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x75d3  ldstr    aCatalogitemid// "@CatalogItemID"
0x75d8  ldc.i4.s 0xE
0x75da  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x75df  ldarg.1
0x75e0  box      [mscorlib]System.Guid
0x75e5  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x75ea  ldloc.0
0x75eb  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x75f0  ldstr    aParamshash// "@ParamsHash"
0x75f5  ldc.i4.8
0x75f6  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x75fb  ldarg.2
0x75fc  box      [mscorlib]System.Int32
0x7601  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x7606  ldloc.0
0x7607  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x760c  ldstr    aEffectiveparam// "@EffectiveParams"
0x7611  ldc.i4.s 0xC
0x7613  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x7618  ldarg.3
0x7619  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x761e  ldloc.0
0x761f  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x7624  ldstr    aContenttype// "@ContentType"
0x7629  ldc.i4.s 0xC
0x762b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x7630  ldarga.s 4
0x7632  constrained. ContentCacheTypes
0x7638  callvirt instance string [mscorlib]System.Object::ToString()
0x763d  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x7642  ldloc.0
0x7643  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x7648  ldstr    aVersion// "@Version"
0x764d  ldc.i4.s 0x10
0x764f  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x7654  ldarg.s  5
0x7656  box      [mscorlib]System.Int32
0x765b  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x7660  ldloc.0
0x7661  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x7666  ldstr    aContent_0// "@Content"
0x766b  ldc.i4.s 0x15
0x766d  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x7672  ldarg.s  6
0x7674  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x7679  ldloc.0
0x767a  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x767f  pop
0x7680  leave.s  loc_768C
0x7682  ldloc.0
0x7683  brfalse.s loc_768B
0x7685  ldloc.0
0x7686  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x768b  endfinally
0x768c  leave.s  loc_76AB
0x768e  stloc.1
0x768f  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x7694  ldc.i4.1
0x7695  ldstr    aErrorInCreateo// "Error in CreateOrUpdateContentCache: {0"...
0x769a  ldc.i4.1
0x769b  newarr   [mscorlib]System.Object
0x76a0  dup
0x76a1  ldc.i4.0
0x76a2  ldloc.1
0x76a3  stelem.ref
0x76a4  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x76a9  rethrow
0x76ab  ret
```
