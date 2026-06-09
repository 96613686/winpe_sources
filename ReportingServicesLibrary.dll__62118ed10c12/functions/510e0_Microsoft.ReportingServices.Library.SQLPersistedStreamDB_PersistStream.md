# Microsoft.ReportingServices.Library.SQLPersistedStreamDB::PersistStream

- ea: `0x510e0`
- end: `0x512cf`
- name: `Microsoft.ReportingServices.Library.SQLPersistedStreamDB::PersistStream`
- size: `495`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x50df0`

## callees

- `0xf3c0`
- `0x510e0`
- `0x56470`
- `0x56490`
- `0x564b0`
- `0x564d0`

## string_xrefs

- `0x51187`: `@Extension`
- `0x5110d`: `WriteFirstPortionPersistedStream`
- `0x511ea`: `WriteNextPortionPersistedStream`
- `0x5121c`: `@DeleteLength`

## pseudocode

```c

```

## disassembly

```asm
0x510e0  ldarg.2
0x510e1  ldc.i4.0
0x510e2  conv.i8
0x510e3  callvirt instance void [mscorlib]System.IO.Stream::set_Position(int64)
0x510e8  ldarg.2
0x510e9  isinst   Microsoft.ReportingServices.Library.RSStream
0x510ee  stloc.0
0x510ef  call     int32 Microsoft.ReportingServices.Library.Global::get_ResponseBufferSizeBytes()
0x510f4  stloc.1
0x510f5  ldloc.1
0x510f6  newarr   [mscorlib]System.Byte
0x510fb  stloc.2
0x510fc  ldc.i4.0
0x510fd  stloc.3
0x510fe  ldc.i4.0
0x510ff  stloc.s  4
0x51101  ldarg.2
0x51102  ldloc.2
0x51103  ldc.i4.0
0x51104  ldloc.1
0x51105  callvirt instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0x5110a  stloc.s  4
0x5110c  ldarg.0
0x5110d  ldstr    aWritefirstport// "WriteFirstPortionPersistedStream"
0x51112  ldnull
0x51113  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x51118  stloc.s  6
0x5111a  ldloc.s  6
0x5111c  ldstr    aSessionid_0// "@SessionID"
0x51121  ldc.i4.s 0x16
0x51123  ldarg.0
0x51124  ldfld    string Microsoft.ReportingServices.Library.SQLPersistedStreamDB::m_sessionID
0x51129  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x5112e  pop
0x5112f  ldloc.s  6
0x51131  ldstr    aIndex// "@Index"
0x51136  ldc.i4.8
0x51137  ldarg.1
0x51138  box      [mscorlib]System.Int32
0x5113d  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x51142  pop
0x51143  ldloc.0
0x51144  callvirt instance string Microsoft.ReportingServices.Library.RSStream::get_Name()
0x51149  brfalse.s loc_51160
0x5114b  ldloc.s  6
0x5114d  ldstr    aName_0// "@Name"
0x51152  ldc.i4.s 0xC
0x51154  ldloc.0
0x51155  callvirt instance string Microsoft.ReportingServices.Library.RSStream::get_Name()
0x5115a  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x5115f  pop
0x51160  ldloc.0
0x51161  callvirt instance string Microsoft.ReportingServices.Library.RSStream::get_MimeType()
0x51166  brfalse.s loc_5117D
0x51168  ldloc.s  6
0x5116a  ldstr    aMimetype// "@MimeType"
0x5116f  ldc.i4.s 0xC
0x51171  ldloc.0
0x51172  callvirt instance string Microsoft.ReportingServices.Library.RSStream::get_MimeType()
0x51177  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x5117c  pop
0x5117d  ldloc.0
0x5117e  callvirt instance string Microsoft.ReportingServices.Library.RSStream::get_Extension()
0x51183  brfalse.s loc_5119A
0x51185  ldloc.s  6
0x51187  ldstr    aExtension// "@Extension"
0x5118c  ldc.i4.s 0xC
0x5118e  ldloc.0
0x5118f  callvirt instance string Microsoft.ReportingServices.Library.RSStream::get_Extension()
0x51194  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x51199  pop
0x5119a  ldloc.0
0x5119b  callvirt instance class [mscorlib]System.Text.Encoding Microsoft.ReportingServices.Library.RSStream::get_Encoding()
0x511a0  brfalse.s loc_511B6
0x511a2  ldloc.s  6
0x511a4  ldstr    aEncoding// "@Encoding"
0x511a9  ldc.i4.8
0x511aa  ldloc.0
0x511ab  callvirt instance class [mscorlib]System.Text.Encoding Microsoft.ReportingServices.Library.RSStream::get_Encoding()
0x511b0  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x511b5  pop
0x511b6  ldloc.s  6
0x511b8  ldstr    aContent_0// "@Content"
0x511bd  ldc.i4.7
0x511be  ldloc.2
0x511bf  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x511c4  dup
0x511c5  ldloc.s  4
0x511c7  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Size(int32)
0x511cc  ldc.i4.0
0x511cd  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_Offset(int32)
0x511d2  ldloc.s  6
0x511d4  callvirt instance object [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteScalar()
0x511d9  stloc.s  5
0x511db  leave.s  loc_511E9
0x511dd  ldloc.s  6
0x511df  brfalse.s loc_511E8
0x511e1  ldloc.s  6
0x511e3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x511e8  endfinally
0x511e9  ldarg.0
0x511ea  ldstr    aWritenextporti// "WriteNextPortionPersistedStream"
0x511ef  ldnull
0x511f0  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x511f5  stloc.s  7
0x511f7  ldloc.s  7
0x511f9  ldstr    aDatapointer// "@DataPointer"
0x511fe  ldc.i4.1
0x511ff  ldloc.s  5
0x51201  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x51206  pop
0x51207  ldloc.s  7
0x51209  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5120e  ldstr    aDataindex// "@DataIndex"
0x51213  ldc.i4.8
0x51214  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x51219  pop
0x5121a  ldloc.s  7
0x5121c  ldstr    aDeletelength// "@DeleteLength"
0x51221  ldc.i4.8
0x51222  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x51227  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x5122c  pop
0x5122d  ldloc.s  7
0x5122f  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x51234  ldstr    aContent_0// "@Content"
0x51239  ldc.i4.7
0x5123a  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5123f  pop
0x51240  br.s     loc_512B2
0x51242  ldloc.s  7
0x51244  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x51249  ldstr    aDataindex// "@DataIndex"
0x5124e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::get_Item(string)
0x51253  ldloc.s  4
0x51255  box      [mscorlib]System.Int32
0x5125a  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5125f  ldloc.s  7
0x51261  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x51266  ldstr    aContent_0// "@Content"
0x5126b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::get_Item(string)
0x51270  ldloc.2
0x51271  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x51276  ldloc.s  7
0x51278  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5127d  ldstr    aContent_0// "@Content"
0x51282  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::get_Item(string)
0x51287  ldloc.3
0x51288  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Size(int32)
0x5128d  ldloc.s  7
0x5128f  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x51294  ldstr    aContent_0// "@Content"
0x51299  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::get_Item(string)
0x5129e  ldc.i4.0
0x5129f  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_Offset(int32)
0x512a4  ldloc.s  4
0x512a6  ldloc.3
0x512a7  add
0x512a8  stloc.s  4
0x512aa  ldloc.s  7
0x512ac  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x512b1  pop
0x512b2  ldarg.2
0x512b3  ldloc.2
0x512b4  ldc.i4.0
0x512b5  ldloc.1
0x512b6  callvirt instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0x512bb  dup
0x512bc  stloc.3
0x512bd  ldc.i4.0
0x512be  bgt.s    loc_51242
0x512c0  leave.s  loc_512CE
0x512c2  ldloc.s  7
0x512c4  brfalse.s loc_512CD
0x512c6  ldloc.s  7
0x512c8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x512cd  endfinally
0x512ce  ret
```
