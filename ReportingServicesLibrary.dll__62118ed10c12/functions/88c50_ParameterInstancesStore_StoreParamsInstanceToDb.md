# ParameterInstancesStore::StoreParamsInstanceToDb

- ea: `0x88c50`
- end: `0x88dd3`
- name: `ParameterInstancesStore::StoreParamsInstanceToDb`
- size: `387`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callers

- `0x88b40`

## callees

- `0x88b70`
- `0x88bf0`
- `0x88c50`

## string_xrefs

- `0x88c9a`: `@Path`
- `0x88d3f`: `@Path`
- `0x88c8b`: `@ServerParametersID`
- `0x88d30`: `@ServerParametersID`
- `0x88da5`: `@ParentParametersID`

## pseudocode

```c

```

## disassembly

```asm
0x88c50  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x88c55  stloc.0
0x88c56  ldarg.0
0x88c57  ldstr    aStoreserverpar// "StoreServerParameters"
0x88c5c  ldnull
0x88c5d  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x88c62  stloc.1
0x88c63  ldarg.s  5
0x88c65  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x88c6a  brfalse.s loc_88C7B
0x88c6c  ldarg.0
0x88c6d  ldarg.s  4
0x88c6f  ldarga.s 1
0x88c71  call     instance bool ParameterInstancesStore::NeedToStoreCommonParams(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection commonParams, string& paramId)
0x88c76  brfalse  loc_88D05
0x88c7b  ldarg.0
0x88c7c  ldarg.s  4
0x88c7e  ldc.i4.0
0x88c7f  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection::ToXml(bool)
0x88c84  call     instance unsigned int8[] ParameterInstancesStore::Compress(string source)
0x88c89  stloc.2
0x88c8a  ldloc.1
0x88c8b  ldstr    aServerparamete// "@ServerParametersID"
0x88c90  ldc.i4.s 0xC
0x88c92  ldarg.1
0x88c93  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x88c98  pop
0x88c99  ldloc.1
0x88c9a  ldstr    aPath// "@Path"
0x88c9f  ldc.i4.s 0xC
0x88ca1  ldarg.3
0x88ca2  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x88ca7  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x88cac  pop
0x88cad  ldloc.1
0x88cae  ldstr    aCurrentdate// "@CurrentDate"
0x88cb3  ldc.i4.4
0x88cb4  ldloc.0
0x88cb5  box      [mscorlib]System.DateTime
0x88cba  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x88cbf  pop
0x88cc0  ldloc.1
0x88cc1  ldstr    aTimeout// "@Timeout"
0x88cc6  ldc.i4.8
0x88cc7  ldarg.s  6
0x88cc9  box      [mscorlib]System.Int32
0x88cce  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x88cd3  pop
0x88cd4  ldloc.1
0x88cd5  ldstr    aExpiration// "@Expiration"
0x88cda  ldc.i4.4
0x88cdb  ldloca.s 0
0x88cdd  ldarg.s  6
0x88cdf  conv.r8
0x88ce0  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x88ce5  box      [mscorlib]System.DateTime
0x88cea  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x88cef  pop
0x88cf0  ldloc.1
0x88cf1  ldstr    aParametersvalu// "@ParametersValues"
0x88cf6  ldc.i4.7
0x88cf7  ldloc.2
0x88cf8  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x88cfd  pop
0x88cfe  ldloc.1
0x88cff  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x88d04  pop
0x88d05  ldarg.s  5
0x88d07  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x88d0c  ldc.i4.0
0x88d0d  ble      loc_88DC6
0x88d12  ldarg.0
0x88d13  ldstr    aStoreserverpar// "StoreServerParameters"
0x88d18  ldnull
0x88d19  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x88d1e  stloc.3
0x88d1f  ldarg.0
0x88d20  ldarg.s  5
0x88d22  ldc.i4.0
0x88d23  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection::ToXml(bool)
0x88d28  call     instance unsigned int8[] ParameterInstancesStore::Compress(string source)
0x88d2d  stloc.s  4
0x88d2f  ldloc.3
0x88d30  ldstr    aServerparamete// "@ServerParametersID"
0x88d35  ldc.i4.s 0xC
0x88d37  ldarg.2
0x88d38  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x88d3d  pop
0x88d3e  ldloc.3
0x88d3f  ldstr    aPath// "@Path"
0x88d44  ldc.i4.s 0xC
0x88d46  ldarg.3
0x88d47  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x88d4c  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x88d51  pop
0x88d52  ldloc.3
0x88d53  ldstr    aCurrentdate// "@CurrentDate"
0x88d58  ldc.i4.4
0x88d59  ldloc.0
0x88d5a  box      [mscorlib]System.DateTime
0x88d5f  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x88d64  pop
0x88d65  ldloc.3
0x88d66  ldstr    aTimeout// "@Timeout"
0x88d6b  ldc.i4.8
0x88d6c  ldarg.s  6
0x88d6e  box      [mscorlib]System.Int32
0x88d73  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x88d78  pop
0x88d79  ldloc.3
0x88d7a  ldstr    aExpiration// "@Expiration"
0x88d7f  ldc.i4.4
0x88d80  ldloca.s 0
0x88d82  ldarg.s  6
0x88d84  conv.r8
0x88d85  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x88d8a  box      [mscorlib]System.DateTime
0x88d8f  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x88d94  pop
0x88d95  ldloc.3
0x88d96  ldstr    aParametersvalu// "@ParametersValues"
0x88d9b  ldc.i4.7
0x88d9c  ldloc.s  4
0x88d9e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x88da3  pop
0x88da4  ldloc.3
0x88da5  ldstr    aParentparamete// "@ParentParametersID"
0x88daa  ldc.i4.s 0xC
0x88dac  ldarg.1
0x88dad  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x88db2  pop
0x88db3  ldloc.3
0x88db4  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x88db9  pop
0x88dba  leave.s  loc_88DD2
0x88dbc  ldloc.3
0x88dbd  brfalse.s loc_88DC5
0x88dbf  ldloc.3
0x88dc0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x88dc5  endfinally
0x88dc6  leave.s  loc_88DD2
0x88dc8  ldloc.1
0x88dc9  brfalse.s loc_88DD1
0x88dcb  ldloc.1
0x88dcc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x88dd1  endfinally
0x88dd2  ret
```
