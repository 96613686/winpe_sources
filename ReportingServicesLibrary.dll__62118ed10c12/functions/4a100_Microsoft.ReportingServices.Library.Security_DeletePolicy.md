# Microsoft.ReportingServices.Library.Security::DeletePolicy

- ea: `0x4a100`
- end: `0x4a167`
- name: `Microsoft.ReportingServices.Library.Security::DeletePolicy`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3dd90`

## callees

- `0x4a100`

## string_xrefs

- `0x4a101`: `DeletePolicy`
- `0x4a129`: `No policies found in internal DeletePolicy`

## pseudocode

```c

```

## disassembly

```asm
0x4a100  ldarg.0
0x4a101  ldstr    aDeletepolicy// "DeletePolicy"
0x4a106  ldnull
0x4a107  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x4a10c  stloc.0
0x4a10d  ldloc.0
0x4a10e  ldstr    aItemname_0// "@ItemName"
0x4a113  ldc.i4.s 0xC
0x4a115  ldarg.1
0x4a116  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath::get_NativeCatalogPath()
0x4a11b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x4a120  pop
0x4a121  ldloc.0
0x4a122  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x4a127  brtrue.s loc_4A134
0x4a129  ldstr    aNoPoliciesFoun// "No policies found in internal DeletePol"...
0x4a12e  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x4a133  throw
0x4a134  leave.s  loc_4A140
0x4a136  ldloc.0
0x4a137  brfalse.s loc_4A13F
0x4a139  ldloc.0
0x4a13a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4a13f  endfinally
0x4a140  leave.s  loc_4A166
0x4a142  stloc.1
0x4a143  ldloc.1
0x4a144  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerStorageException::get_IsSqlException()
0x4a149  brfalse.s loc_4A164
0x4a14b  ldloc.1
0x4a14c  callvirt instance int32 [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerStorageException::get_SqlErrorNumber()
0x4a151  ldsfld   int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Native::SqlConstraintViolationCode
0x4a156  bne.un.s loc_4A164
0x4a158  ldarg.1
0x4a159  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x4a15e  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InheritedPolicyException::.ctor(string)
0x4a163  throw
0x4a164  leave.s  loc_4A166
0x4a166  ret
```
