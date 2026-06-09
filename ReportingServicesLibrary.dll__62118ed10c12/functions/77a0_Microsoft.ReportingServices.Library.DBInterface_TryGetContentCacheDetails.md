# Microsoft.ReportingServices.Library.DBInterface::TryGetContentCacheDetails

- ea: `0x77a0`
- end: `0x7865`
- name: `Microsoft.ReportingServices.Library.DBInterface::TryGetContentCacheDetails`
- size: `197`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x77a0`

## string_xrefs

- `0x77a5`: `GetContentCacheDetails`
- `0x784d`: `Error in GetContentCacheDetails: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x77a0  ldarg.s  4
0x77a2  ldc.i4.0
0x77a3  stind.i4
0x77a4  ldarg.0
0x77a5  ldstr    aGetcontentcach_0// "GetContentCacheDetails"
0x77aa  ldnull
0x77ab  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x77b0  stloc.0
0x77b1  ldloc.0
0x77b2  ldstr    aCatalogitemid// "@CatalogItemID"
0x77b7  ldc.i4.s 0xE
0x77b9  ldarg.1
0x77ba  box      [mscorlib]System.Guid
0x77bf  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x77c4  pop
0x77c5  ldloc.0
0x77c6  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x77cb  ldstr    aParamshash// "@ParamsHash"
0x77d0  ldarg.2
0x77d1  box      [mscorlib]System.Int32
0x77d6  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x77db  pop
0x77dc  ldloc.0
0x77dd  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x77e2  ldstr    aContenttype// "@ContentType"
0x77e7  ldarga.s 3
0x77e9  constrained. ContentCacheTypes
0x77ef  callvirt instance string [mscorlib]System.Object::ToString()
0x77f4  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x77f9  pop
0x77fa  ldloc.0
0x77fb  callvirt instance class [System.Data]System.Data.IDataReader [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader()
0x7800  stloc.1
0x7801  ldloc.1
0x7802  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x7807  brfalse.s loc_782E
0x7809  ldloc.1
0x780a  ldstr    aVersion_0// "Version"
0x780f  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x7814  brfalse.s loc_782A
0x7816  ldarg.s  4
0x7818  ldloc.1
0x7819  ldloc.1
0x781a  ldstr    aVersion_0// "Version"
0x781f  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetOrdinal(string)
0x7824  callvirt instance int16 [System.Data]System.Data.IDataRecord::GetInt16(int32)
0x7829  stind.i4
0x782a  ldc.i4.1
0x782b  stloc.2
0x782c  leave.s  loc_7863
0x782e  ldc.i4.0
0x782f  stloc.2
0x7830  leave.s  loc_7863
0x7832  ldloc.1
0x7833  brfalse.s loc_783B
0x7835  ldloc.1
0x7836  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x783b  endfinally
0x783c  ldloc.0
0x783d  brfalse.s loc_7845
0x783f  ldloc.0
0x7840  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7845  endfinally
0x7846  stloc.3
0x7847  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x784c  ldc.i4.1
0x784d  ldstr    aErrorInGetcont_0// "Error in GetContentCacheDetails: {0}"
0x7852  ldc.i4.1
0x7853  newarr   [mscorlib]System.Object
0x7858  dup
0x7859  ldc.i4.0
0x785a  ldloc.3
0x785b  stelem.ref
0x785c  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x7861  rethrow
0x7863  ldloc.2
0x7864  ret
```
