# Microsoft.ReportingServices.Library.Security::GetSystemSecurityDescriptor

- ea: `0x4aeb0`
- end: `0x4af4b`
- name: `Microsoft.ReportingServices.Library.Security::GetSystemSecurityDescriptor`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x4afb0`

## callees

- `0x4aeb0`

## string_xrefs

- `0x4aeb1`: `GetSystemPolicy`
- `0x4af01`: `Could not find security descriptor.`

## pseudocode

```c

```

## disassembly

```asm
0x4aeb0  ldarg.0
0x4aeb1  ldstr    aGetsystempolic_0// "GetSystemPolicy"
0x4aeb6  ldnull
0x4aeb7  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x4aebc  stloc.0
0x4aebd  ldloc.0
0x4aebe  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x4aec3  ldstr    aAuthtype// "@AuthType"
0x4aec8  ldarg.0
0x4aec9  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.Security::m_userContext
0x4aece  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x4aed3  box      [mscorlib]System.Int32
0x4aed8  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4aedd  pop
0x4aede  ldloc.0
0x4aedf  callvirt instance class [System.Data]System.Data.IDataReader [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader()
0x4aee4  stloc.1
0x4aee5  ldloc.1
0x4aee6  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x4aeeb  brfalse.s loc_4AF01
0x4aeed  ldloc.1
0x4aeee  ldc.i4.0
0x4aeef  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x4aef4  brtrue.s loc_4AF0C
0x4aef6  ldarg.1
0x4aef7  ldloc.1
0x4aef8  ldc.i4.0
0x4aef9  call     unsigned int8[] [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.DataReaderHelper::ReadAllBytes(class [System.Data]System.Data.IDataRecord, int32)
0x4aefe  stind.ref
0x4aeff  br.s     loc_4AF0C
0x4af01  ldstr    aCouldNotFindSe// "Could not find security descriptor."
0x4af06  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x4af0b  throw
0x4af0c  leave.s  loc_4AF18
0x4af0e  ldloc.1
0x4af0f  brfalse.s loc_4AF17
0x4af11  ldloc.1
0x4af12  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4af17  endfinally
0x4af18  ldarg.0
0x4af19  call     instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::Commit()
0x4af1e  leave.s  loc_4AF2A
0x4af20  ldloc.0
0x4af21  brfalse.s loc_4AF29
0x4af23  ldloc.0
0x4af24  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4af29  endfinally
0x4af2a  leave.s  loc_4AF4A
0x4af2c  ldarg.0
0x4af2d  call     instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::AbortTransaction()
0x4af32  dup
0x4af33  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException
0x4af38  brfalse.s loc_4AF3C
0x4af3a  rethrow
0x4af3c  ldnull
0x4af3d  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(class [mscorlib]System.Exception, string)
0x4af42  throw
0x4af43  ldarg.0
0x4af44  call     instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::Disconnect()
0x4af49  endfinally
0x4af4a  ret
```
