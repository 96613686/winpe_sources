# Microsoft.ReportingServices.Library.DBInterface::TryGetContentCache

- ea: `0x76b0`
- end: `0x779a`
- name: `Microsoft.ReportingServices.Library.DBInterface::TryGetContentCache`
- size: `234`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x76b0`

## string_xrefs

- `0x76b9`: `GetContentCache`
- `0x7782`: `Error in GetContentCache: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x76b0  ldarg.s  4
0x76b2  ldnull
0x76b3  stind.ref
0x76b4  ldarg.s  5
0x76b6  ldc.i4.0
0x76b7  stind.i4
0x76b8  ldarg.0
0x76b9  ldstr    aGetcontentcach// "GetContentCache"
0x76be  ldnull
0x76bf  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x76c4  stloc.0
0x76c5  ldloc.0
0x76c6  ldstr    aCatalogitemid// "@CatalogItemID"
0x76cb  ldc.i4.s 0xE
0x76cd  ldarg.1
0x76ce  box      [mscorlib]System.Guid
0x76d3  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x76d8  pop
0x76d9  ldloc.0
0x76da  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x76df  ldstr    aParamshash// "@ParamsHash"
0x76e4  ldarg.2
0x76e5  box      [mscorlib]System.Int32
0x76ea  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x76ef  pop
0x76f0  ldloc.0
0x76f1  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x76f6  ldstr    aContenttype// "@ContentType"
0x76fb  ldarga.s 3
0x76fd  constrained. ContentCacheTypes
0x7703  callvirt instance string [mscorlib]System.Object::ToString()
0x7708  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x770d  pop
0x770e  ldloc.0
0x770f  callvirt instance class [System.Data]System.Data.IDataReader [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader()
0x7714  stloc.1
0x7715  ldloc.1
0x7716  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x771b  brfalse.s loc_7763
0x771d  ldloc.1
0x771e  ldstr    aContent_1// "Content"
0x7723  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x7728  brfalse.s loc_773E
0x772a  ldarg.s  4
0x772c  ldloc.1
0x772d  ldloc.1
0x772e  ldstr    aContent_1// "Content"
0x7733  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetOrdinal(string)
0x7738  call     unsigned int8[] [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.DataReaderHelper::ReadAllBytes(class [System.Data]System.Data.IDataRecord, int32)
0x773d  stind.ref
0x773e  ldloc.1
0x773f  ldstr    aVersion_0// "Version"
0x7744  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x7749  brfalse.s loc_775F
0x774b  ldarg.s  5
0x774d  ldloc.1
0x774e  ldloc.1
0x774f  ldstr    aVersion_0// "Version"
0x7754  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetOrdinal(string)
0x7759  callvirt instance int16 [System.Data]System.Data.IDataRecord::GetInt16(int32)
0x775e  stind.i4
0x775f  ldc.i4.1
0x7760  stloc.2
0x7761  leave.s  loc_7798
0x7763  ldc.i4.0
0x7764  stloc.2
0x7765  leave.s  loc_7798
0x7767  ldloc.1
0x7768  brfalse.s loc_7770
0x776a  ldloc.1
0x776b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7770  endfinally
0x7771  ldloc.0
0x7772  brfalse.s loc_777A
0x7774  ldloc.0
0x7775  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x777a  endfinally
0x777b  stloc.3
0x777c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x7781  ldc.i4.1
0x7782  ldstr    aErrorInGetcont// "Error in GetContentCache: {0}"
0x7787  ldc.i4.1
0x7788  newarr   [mscorlib]System.Object
0x778d  dup
0x778e  ldc.i4.0
0x778f  ldloc.3
0x7790  stelem.ref
0x7791  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x7796  rethrow
0x7798  ldloc.2
0x7799  ret
```
