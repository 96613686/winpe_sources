# Microsoft.ReportingServices.Library.KeyStorage::AnnouncePublicKeyOrGetSymmetricKey

- ea: `0x2d40`
- end: `0x2ef9`
- name: `Microsoft.ReportingServices.Library.KeyStorage::AnnouncePublicKeyOrGetSymmetricKey`
- size: `441`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x3420`

## callees

- `0x2d40`
- `0x2f70`
- `0x6c00`
- `0x70e0`
- `0x7120`
- `0x7320`
- `0x79c0`

## string_xrefs

- `0x2d86`: `@InstallationID`
- `0x2ebf`: `@InstallationID`
- `0x2daf`: `@NumAnnouncedServices`
- `0x2ddb`: `Cannot read matching key record`

## pseudocode

```c

```

## disassembly

```asm
0x2d40  call     string [mscorlib]System.Environment::get_MachineName()
0x2d45  stloc.0
0x2d46  ldarg.0
0x2d47  ldstr    aAnnounceorgetk// "AnnounceOrGetKey"
0x2d4c  ldnull
0x2d4d  callvirt instance class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string storedProcedureName, [opt] class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection connection)
0x2d52  stloc.1
0x2d53  ldloc.1
0x2d54  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x2d59  ldstr    aMachinename// "@MachineName"
0x2d5e  ldloc.0
0x2d5f  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2d64  pop
0x2d65  ldloc.1
0x2d66  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x2d6b  ldstr    aInstancename// "@InstanceName"
0x2d70  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x2d75  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_InstanceName()
0x2d7a  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2d7f  pop
0x2d80  ldloc.1
0x2d81  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x2d86  ldstr    aInstallationid// "@InstallationID"
0x2d8b  ldarg.1
0x2d8c  box      [mscorlib]System.Guid
0x2d91  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2d96  pop
0x2d97  ldloc.1
0x2d98  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x2d9d  ldstr    aPublickey// "@PublicKey"
0x2da2  ldarg.2
0x2da3  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2da8  pop
0x2da9  ldloc.1
0x2daa  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x2daf  ldstr    aNumannouncedse// "@NumAnnouncedServices"
0x2db4  ldc.i4.8
0x2db5  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x2dba  stloc.2
0x2dbb  ldloc.2
0x2dbc  ldc.i4.2
0x2dbd  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x2dc2  ldnull
0x2dc3  stloc.3
0x2dc4  ldarg.3
0x2dc5  ldnull
0x2dc6  stind.ref
0x2dc7  ldnull
0x2dc8  stloc.s  4
0x2dca  ldloc.1
0x2dcb  callvirt instance class [System.Data]System.Data.IDataReader Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader()
0x2dd0  stloc.s  6
0x2dd2  ldloc.s  6
0x2dd4  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x2dd9  brtrue.s loc_2DE6
0x2ddb  ldstr    aCannotReadMatc// "Cannot read matching key record"
0x2de0  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(string)
0x2de5  throw
0x2de6  ldloc.s  6
0x2de8  ldc.i4.0
0x2de9  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x2dee  brtrue.s loc_2DF9
0x2df0  ldloc.s  6
0x2df2  ldc.i4.0
0x2df3  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0x2df8  stloc.3
0x2df9  ldloc.s  6
0x2dfb  ldc.i4.1
0x2dfc  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x2e01  brtrue.s loc_2E0D
0x2e03  ldarg.3
0x2e04  ldloc.s  6
0x2e06  ldc.i4.1
0x2e07  call     unsigned int8[] Microsoft.ReportingServices.Library.DataReaderHelper::ReadAllBytes(class [System.Data]System.Data.IDataRecord row, int32 i)
0x2e0c  stind.ref
0x2e0d  ldloc.s  6
0x2e0f  ldc.i4.2
0x2e10  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x2e15  brtrue.s loc_2E21
0x2e17  ldloc.s  6
0x2e19  ldc.i4.2
0x2e1a  call     unsigned int8[] Microsoft.ReportingServices.Library.DataReaderHelper::ReadAllBytes(class [System.Data]System.Data.IDataRecord row, int32 i)
0x2e1f  stloc.s  4
0x2e21  ldloc.s  6
0x2e23  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x2e28  brfalse.s loc_2E35
0x2e2a  ldstr    aMoreThanOneMat// "More than one matching key record prese"...
0x2e2f  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(string)
0x2e34  throw
0x2e35  leave.s  loc_2E43
0x2e37  ldloc.s  6
0x2e39  brfalse.s loc_2E42
0x2e3b  ldloc.s  6
0x2e3d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2e42  endfinally
0x2e43  ldloc.2
0x2e44  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x2e49  unbox.any [mscorlib]System.Int32
0x2e4e  stloc.s  5
0x2e50  ldloc.s  5
0x2e52  ldc.i4.1
0x2e53  ble.s    loc_2E82
0x2e55  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0x2e5a  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x2e5f  brfalse.s loc_2E71
0x2e61  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0x2e66  ldc.i4.3
0x2e67  ldstr    aPerformingSkuV// "Performing sku validation : Scale-Out"
0x2e6c  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x2e71  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x2e76  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_InstanceID()
0x2e7b  ldc.i4.s 0xB
0x2e7d  call     void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Sku::ThrowIfFeatureNotEnabled(string, valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.RestrictedFeatures)
0x2e82  ldloc.0
0x2e83  ldloc.3
0x2e84  ldc.i4.5
0x2e85  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x2e8a  brfalse.s loc_2EE6
0x2e8c  ldarg.0
0x2e8d  ldarg.2
0x2e8e  ldloc.s  4
0x2e90  call     instance bool Microsoft.ReportingServices.Library.KeyStorage::ByteArraysAreEqual(unsigned int8[] x, unsigned int8[] y)
0x2e95  brfalse.s loc_2EE6
0x2e97  ldarg.0
0x2e98  ldstr    aSetmachinename// "SetMachineName"
0x2e9d  ldnull
0x2e9e  callvirt instance class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string storedProcedureName, [opt] class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection connection)
0x2ea3  stloc.s  7
0x2ea5  ldloc.s  7
0x2ea7  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x2eac  ldstr    aMachinename// "@MachineName"
0x2eb1  ldloc.0
0x2eb2  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2eb7  pop
0x2eb8  ldloc.s  7
0x2eba  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x2ebf  ldstr    aInstallationid// "@InstallationID"
0x2ec4  ldarg.1
0x2ec5  box      [mscorlib]System.Guid
0x2eca  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2ecf  pop
0x2ed0  ldloc.s  7
0x2ed2  callvirt instance int32 Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x2ed7  pop
0x2ed8  leave.s  loc_2EE6
0x2eda  ldloc.s  7
0x2edc  brfalse.s loc_2EE5
0x2ede  ldloc.s  7
0x2ee0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2ee5  endfinally
0x2ee6  ldloc.s  5
0x2ee8  stloc.s  8
0x2eea  leave.s  loc_2EF6
0x2eec  ldloc.1
0x2eed  brfalse.s loc_2EF5
0x2eef  ldloc.1
0x2ef0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2ef5  endfinally
0x2ef6  ldloc.s  8
0x2ef8  ret
```
