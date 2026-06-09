# Microsoft.ReportingServices.Library.Security::BuildSqlCommandFromScope

- ea: `0x49e90`
- end: `0x49f89`
- name: `Microsoft.ReportingServices.Library.Security::BuildSqlCommandFromScope`
- size: `249`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x49bb0`

## callees

- `0x49e90`
- `0x8b270`
- `0x8b280`

## string_xrefs

- `0x49eaa`: `SetSystemPolicy`
- `0x49f02`: `SetModelItemPolicy`
- `0x49f3d`: `Unknown security scope.`
- `0x49f7a`: `Exception while disposing command object.`

## pseudocode

```c

```

## disassembly

```asm
0x49e90  ldnull
0x49e91  stloc.0
0x49e92  ldarg.2
0x49e93  switch   loc_49EBB, loc_49EA9, loc_49F01
0x49ea4  br       loc_49F3D
0x49ea9  ldarg.0
0x49eaa  ldstr    aSetsystempolic_0// "SetSystemPolicy"
0x49eaf  ldnull
0x49eb0  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x49eb5  stloc.0
0x49eb6  br       loc_49F48
0x49ebb  ldarg.0
0x49ebc  ldstr    aSetpolicy// "SetPolicy"
0x49ec1  ldnull
0x49ec2  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x49ec7  stloc.0
0x49ec8  ldloc.0
0x49ec9  ldstr    aItemname_0// "@ItemName"
0x49ece  ldc.i4.s 0xC
0x49ed0  ldarg.3
0x49ed1  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x49ed6  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x49edb  pop
0x49edc  ldloc.0
0x49edd  ldstr    aItemnamelike// "@ItemNameLike"
0x49ee2  ldc.i4.s 0xC
0x49ee4  ldarg.3
0x49ee5  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x49eea  call     string [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::EncodeForLike(string)
0x49eef  ldstr    asc_92514// "/%"
0x49ef4  call     string [mscorlib]System.String::Concat(string, string)
0x49ef9  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x49efe  pop
0x49eff  br.s     loc_49F48
0x49f01  ldarg.0
0x49f02  ldstr    aSetmodelitempo_0// "SetModelItemPolicy"
0x49f07  ldnull
0x49f08  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x49f0d  stloc.0
0x49f0e  ldloc.0
0x49f0f  ldstr    aCatalogitemid// "@CatalogItemID"
0x49f14  ldc.i4.s 0xE
0x49f16  ldarg.1
0x49f17  callvirt instance valuetype [mscorlib]System.Guid SecurityPolicy::get_CatalogItemID()
0x49f1c  box      [mscorlib]System.Guid
0x49f21  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x49f26  pop
0x49f27  ldloc.0
0x49f28  ldstr    aModelitemid// "@ModelItemID"
0x49f2d  ldc.i4.s 0xC
0x49f2f  ldarg.1
0x49f30  callvirt instance string SecurityPolicy::get_ModelItemID()
0x49f35  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x49f3a  pop
0x49f3b  br.s     loc_49F48
0x49f3d  ldstr    aUnknownSecurit// "Unknown security scope."
0x49f42  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x49f47  throw
0x49f48  ldloc.0
0x49f49  stloc.1
0x49f4a  leave.s  loc_49F87
0x49f4c  stloc.2
0x49f4d  ldloc.0
0x49f4e  brfalse.s loc_49F59
0x49f50  ldloc.0
0x49f51  brfalse.s loc_49F59
0x49f53  ldloc.0
0x49f54  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x49f59  leave.s  loc_49F85
0x49f5b  stloc.3
0x49f5c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x49f61  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x49f66  brfalse.s loc_49F79
0x49f68  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x49f6d  ldc.i4.1
0x49f6e  ldloc.3
0x49f6f  callvirt instance string [mscorlib]System.Object::ToString()
0x49f74  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::TraceException(valuetype [System]System.Diagnostics.TraceLevel, string)
0x49f79  ldloc.2
0x49f7a  ldstr    aExceptionWhile// "Exception while disposing command objec"...
0x49f7f  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(class [mscorlib]System.Exception, string)
0x49f84  throw
0x49f85  rethrow
0x49f87  ldloc.1
0x49f88  ret
```
