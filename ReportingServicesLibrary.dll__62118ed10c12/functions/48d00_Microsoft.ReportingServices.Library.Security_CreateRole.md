# Microsoft.ReportingServices.Library.Security::CreateRole

- ea: `0x48d00`
- end: `0x48da8`
- name: `Microsoft.ReportingServices.Library.Security::CreateRole`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3d080`

## callees

- `0x48d00`

## string_xrefs

- `0x48d01`: `CreateRole`
- `0x48d4a`: `@TaskMask`

## pseudocode

```c

```

## disassembly

```asm
0x48d00  ldarg.0
0x48d01  ldstr    aCreaterole// "CreateRole"
0x48d06  ldnull
0x48d07  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x48d0c  stloc.0
0x48d0d  ldloc.0
0x48d0e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x48d13  ldstr    aRoleid// "@RoleID"
0x48d18  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x48d1d  box      [mscorlib]System.Guid
0x48d22  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x48d27  pop
0x48d28  ldloc.0
0x48d29  ldstr    aRolename// "@RoleName"
0x48d2e  ldc.i4.s 0xC
0x48d30  ldarg.1
0x48d31  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x48d36  pop
0x48d37  ldarg.2
0x48d38  brfalse.s loc_48D49
0x48d3a  ldloc.0
0x48d3b  ldstr    aDescription// "@Description"
0x48d40  ldc.i4.s 0xC
0x48d42  ldarg.2
0x48d43  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x48d48  pop
0x48d49  ldloc.0
0x48d4a  ldstr    aTaskmask// "@TaskMask"
0x48d4f  ldc.i4.s 0xC
0x48d51  ldarg.3
0x48d52  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x48d57  pop
0x48d58  ldarg.s  4
0x48d5a  conv.u1
0x48d5b  stloc.1
0x48d5c  ldloc.0
0x48d5d  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x48d62  ldstr    aRoleflags// "@RoleFlags"
0x48d67  ldloc.1
0x48d68  box      [mscorlib]System.Byte
0x48d6d  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x48d72  pop
0x48d73  ldloc.0
0x48d74  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x48d79  pop
0x48d7a  leave.s  loc_48D86
0x48d7c  ldloc.0
0x48d7d  brfalse.s loc_48D85
0x48d7f  ldloc.0
0x48d80  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x48d85  endfinally
0x48d86  leave.s  loc_48DA7
0x48d88  stloc.2
0x48d89  ldloc.2
0x48d8a  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerStorageException::get_IsSqlException()
0x48d8f  brfalse.s loc_48DA5
0x48d91  ldloc.2
0x48d92  callvirt instance int32 [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerStorageException::get_SqlErrorNumber()
0x48d97  ldsfld   int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Native::SqlUniqueIndexViolationCode
0x48d9c  bne.un.s loc_48DA5
0x48d9e  ldarg.1
0x48d9f  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RoleAlreadyExistsException::.ctor(string)
0x48da4  throw
0x48da5  rethrow
0x48da7  ret
```
