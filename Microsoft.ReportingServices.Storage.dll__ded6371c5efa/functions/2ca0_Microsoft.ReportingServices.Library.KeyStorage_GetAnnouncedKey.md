# Microsoft.ReportingServices.Library.KeyStorage::GetAnnouncedKey

- ea: `0x2ca0`
- end: `0x2d3d`
- name: `Microsoft.ReportingServices.Library.KeyStorage::GetAnnouncedKey`
- size: `157`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x2ca0`
- `0x6c00`
- `0x7120`
- `0x7320`
- `0x79c0`
- `0x9250`

## string_xrefs

- `0x2cb3`: `InstallationID`

## pseudocode

```c

```

## disassembly

```asm
0x2ca0  ldarg.0
0x2ca1  ldstr    aGetannouncedke// "GetAnnouncedKey"
0x2ca6  ldnull
0x2ca7  callvirt instance class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string storedProcedureName, [opt] class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection connection)
0x2cac  stloc.0
0x2cad  ldloc.0
0x2cae  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x2cb3  ldstr    aInstallationid_0// "InstallationID"
0x2cb8  ldarg.1
0x2cb9  box      [mscorlib]System.Guid
0x2cbe  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2cc3  pop
0x2cc4  ldnull
0x2cc5  stloc.1
0x2cc6  ldloc.0
0x2cc7  callvirt instance class [System.Data]System.Data.IDataReader Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader()
0x2ccc  stloc.2
0x2ccd  ldloc.2
0x2cce  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x2cd3  brfalse.s loc_2D16
0x2cd5  ldloc.2
0x2cd6  ldc.i4.0
0x2cd7  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x2cdc  brtrue.s loc_2D16
0x2cde  ldloc.2
0x2cdf  ldc.i4.0
0x2ce0  call     unsigned int8[] Microsoft.ReportingServices.Library.DataReaderHelper::ReadAllBytes(class [System.Data]System.Data.IDataRecord row, int32 i)
0x2ce5  ldnull
0x2ce6  stloc.3
0x2ce7  ldnull
0x2ce8  stloc.s  4
0x2cea  ldloc.2
0x2ceb  ldc.i4.1
0x2cec  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x2cf1  brtrue.s loc_2CFB
0x2cf3  ldloc.2
0x2cf4  ldc.i4.1
0x2cf5  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0x2cfa  stloc.3
0x2cfb  ldloc.2
0x2cfc  ldc.i4.2
0x2cfd  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x2d02  brtrue.s loc_2D0D
0x2d04  ldloc.2
0x2d05  ldc.i4.2
0x2d06  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0x2d0b  stloc.s  4
0x2d0d  ldloc.3
0x2d0e  ldloc.s  4
0x2d10  newobj   instance void AnnoucedKeyResults::.ctor(unsigned int8[] key, string machineName, string instanceName)
0x2d15  stloc.1
0x2d16  leave.s  loc_2D22
0x2d18  ldloc.2
0x2d19  brfalse.s loc_2D21
0x2d1b  ldloc.2
0x2d1c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2d21  endfinally
0x2d22  ldloc.1
0x2d23  brtrue.s loc_2D2B
0x2d25  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RemotePublicKeyUnavailableException::.ctor()
0x2d2a  throw
0x2d2b  ldloc.1
0x2d2c  stloc.s  5
0x2d2e  leave.s  loc_2D3A
0x2d30  ldloc.0
0x2d31  brfalse.s loc_2D39
0x2d33  ldloc.0
0x2d34  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2d39  endfinally
0x2d3a  ldloc.s  5
0x2d3c  ret
```
