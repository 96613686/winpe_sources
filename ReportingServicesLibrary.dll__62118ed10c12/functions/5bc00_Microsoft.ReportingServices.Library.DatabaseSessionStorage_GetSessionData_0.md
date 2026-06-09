# Microsoft.ReportingServices.Library.DatabaseSessionStorage::GetSessionData_0

- ea: `0x5bc00`
- end: `0x5c265`
- name: `Microsoft.ReportingServices.Library.DatabaseSessionStorage::GetSessionData_0`
- size: `1637`
- prototype: ``
- caller_count: `1`
- callee_count: `32`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x5bbc0`

## callees

- `0xf300`
- `0xf570`
- `0x5bc00`
- `0x5df60`
- `0x5dfc0`
- `0x5dfe0`
- `0x5e040`
- `0x5e080`
- `0x5e0a0`
- `0x5e0c0`
- `0x5e100`
- `0x5e1f0`
- `0x5e660`
- `0x5eaa0`
- `0x5eac0`
- `0x5eae0`
- `0x5eb40`
- `0x5eb60`
- `0x5eb80`
- `0x5eba0`
- `0x5ebc0`
- `0x5ebe0`
- `0x5ec00`
- `0x5ec20`
- `0x5ec40`
- `0x5ec60`
- `0x5ed20`
- `0x5ed40`
- `0x5ed60`
- `0x5ed80`
- `0x5edd0`
- `0x5fac0`

## string_xrefs

- `0x5bc7f`: `@OwnerSid`

## pseudocode

```c

```

## disassembly

```asm
0x5bc00  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_SessionTrace()
0x5bc05  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x5bc0a  brfalse.s loc_5BC26
0x5bc0c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_SessionTrace()
0x5bc11  ldc.i4.4
0x5bc12  ldstr    aGettingSnapsho// "Getting snapshot data: session:'{0}'"
0x5bc17  ldc.i4.1
0x5bc18  newarr   [mscorlib]System.Object
0x5bc1d  dup
0x5bc1e  ldc.i4.0
0x5bc1f  ldarg.1
0x5bc20  stelem.ref
0x5bc21  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x5bc26  ldnull
0x5bc27  stloc.0
0x5bc28  ldarg.3
0x5bc29  callvirt instance class [mscorlib]System.IDisposable [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::EnterThreadSafeContext()
0x5bc2e  stloc.1
0x5bc2f  ldarg.3
0x5bc30  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::get_Connection()
0x5bc35  stloc.2
0x5bc36  ldstr    aGetsessiondata// "GetSessionData"
0x5bc3b  ldloc.2
0x5bc3c  ldarg.3
0x5bc3d  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::get_Transaction()
0x5bc42  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::.ctor(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction)
0x5bc47  call     class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::GetInstrumentedSqlCommand(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand)
0x5bc4c  stloc.3
0x5bc4d  ldloc.3
0x5bc4e  ldc.i4.4
0x5bc4f  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x5bc54  ldloc.3
0x5bc55  call     int32 Microsoft.ReportingServices.Library.Global::get_SessionAccessTimeout()
0x5bc5a  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandTimeout(int32)
0x5bc5f  ldloc.3
0x5bc60  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5bc65  ldstr    aSessionid_0// "@SessionID"
0x5bc6a  ldc.i4.s 0x16
0x5bc6c  ldc.i4.s 0x20
0x5bc6e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x5bc73  ldarg.1
0x5bc74  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5bc79  ldloc.3
0x5bc7a  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5bc7f  ldstr    aOwnersid// "@OwnerSid"
0x5bc84  ldc.i4.s 0x15
0x5bc86  ldc.i4.s 0x55
0x5bc88  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x5bc8d  ldarg.2
0x5bc8e  call     unsigned int8[] Microsoft.ReportingServices.Library.Global::NameToSid(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext user)
0x5bc93  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5bc98  ldloc.3
0x5bc99  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5bc9e  ldstr    aOwnername// "@OwnerName"
0x5bca3  ldc.i4.s 0xC
0x5bca5  ldc.i4   0x104
0x5bcaa  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x5bcaf  ldarg.2
0x5bcb0  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_UserName()
0x5bcb5  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5bcba  ldloc.3
0x5bcbb  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5bcc0  ldstr    aAuthtype// "@AuthType"
0x5bcc5  ldc.i4.8
0x5bcc6  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5bccb  ldarg.2
0x5bccc  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x5bcd1  box      [mscorlib]System.Int32
0x5bcd6  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5bcdb  ldloc.3
0x5bcdc  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5bce1  ldstr    aSnapshottimeou// "@SnapshotTimeoutMinutes"
0x5bce6  ldc.i4.8
0x5bce7  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5bcec  ldc.i4   0x5A0
0x5bcf1  box      [mscorlib]System.Int32
0x5bcf6  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5bcfb  ldloc.3
0x5bcfc  callvirt instance class [System.Data]System.Data.IDataReader [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader()
0x5bd01  stloc.s  4
0x5bd03  ldloc.s  4
0x5bd05  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x5bd0a  brtrue.s loc_5BD14
0x5bd0c  ldnull
0x5bd0d  stloc.s  0x25
0x5bd0f  leave    loc_5C262
0x5bd14  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5bd19  stloc.s  5
0x5bd1b  ldloc.s  4
0x5bd1d  ldc.i4.0
0x5bd1e  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5bd23  brtrue.s loc_5BD2F
0x5bd25  ldloc.s  4
0x5bd27  ldc.i4.0
0x5bd28  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.IDataRecord::GetGuid(int32)
0x5bd2d  stloc.s  5
0x5bd2f  ldnull
0x5bd30  stloc.s  6
0x5bd32  ldloc.s  4
0x5bd34  ldc.i4.1
0x5bd35  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5bd3a  brtrue.s loc_5BD46
0x5bd3c  ldloc.s  4
0x5bd3e  ldc.i4.1
0x5bd3f  call     unsigned int8[] [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.DataReaderHelper::ReadAllBytes(class [System.Data]System.Data.IDataRecord, int32)
0x5bd44  stloc.s  6
0x5bd46  ldnull
0x5bd47  stloc.s  7
0x5bd49  ldloc.s  4
0x5bd4b  ldc.i4.2
0x5bd4c  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5bd51  brtrue.s loc_5BD5D
0x5bd53  ldloc.s  4
0x5bd55  ldc.i4.2
0x5bd56  call     unsigned int8[] [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.DataReaderHelper::ReadAllBytes(class [System.Data]System.Data.IDataRecord, int32)
0x5bd5b  stloc.s  7
0x5bd5d  ldnull
0x5bd5e  stloc.s  8
0x5bd60  ldloc.s  4
0x5bd62  ldc.i4.3
0x5bd63  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5bd68  brtrue.s loc_5BD74
0x5bd6a  ldloc.s  4
0x5bd6c  ldc.i4.3
0x5bd6d  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0x5bd72  stloc.s  8
0x5bd74  ldnull
0x5bd75  stloc.s  9
0x5bd77  ldloc.s  4
0x5bd79  ldc.i4.4
0x5bd7a  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5bd7f  brtrue.s loc_5BD8B
0x5bd81  ldloc.s  4
0x5bd83  ldc.i4.4
0x5bd84  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0x5bd89  stloc.s  9
0x5bd8b  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x5bd90  stloc.s  0xA
0x5bd92  ldloc.s  4
0x5bd94  ldc.i4.5
0x5bd95  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5bd9a  brtrue.s loc_5BDA6
0x5bd9c  ldloc.s  4
0x5bd9e  ldc.i4.5
0x5bd9f  callvirt instance valuetype [mscorlib]System.DateTime [System.Data]System.Data.IDataRecord::GetDateTime(int32)
0x5bda4  stloc.s  0xA
0x5bda6  ldc.i4.0
0x5bda7  stloc.s  0xB
0x5bda9  ldloc.s  4
0x5bdab  ldc.i4.6
0x5bdac  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5bdb1  brtrue.s loc_5BDBD
0x5bdb3  ldloc.s  4
0x5bdb5  ldc.i4.6
0x5bdb6  callvirt instance bool [System.Data]System.Data.IDataRecord::GetBoolean(int32)
0x5bdbb  stloc.s  0xB
0x5bdbd  ldloc.s  4
0x5bdbf  ldc.i4.7
0x5bdc0  callvirt instance valuetype [mscorlib]System.DateTime [System.Data]System.Data.IDataRecord::GetDateTime(int32)
0x5bdc5  stloc.s  0xC
0x5bdc7  ldc.i4.1
0x5bdc8  stloc.s  0xD
0x5bdca  ldloc.s  4
0x5bdcc  ldc.i4.8
0x5bdcd  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5bdd2  brtrue.s loc_5BDDE
0x5bdd4  ldloc.s  4
0x5bdd6  ldc.i4.8
0x5bdd7  callvirt instance bool [System.Data]System.Data.IDataRecord::GetBoolean(int32)
0x5bddc  stloc.s  0xD
0x5bdde  ldloc.s  4
0x5bde0  ldc.i4.s 9
0x5bde2  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0x5bde7  stloc.s  0xE
0x5bde9  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x5bdee  stloc.s  0xF
0x5bdf0  ldloc.s  4
0x5bdf2  ldc.i4.s 0xA
0x5bdf4  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5bdf9  brtrue.s loc_5BE06
0x5bdfb  ldloc.s  4
0x5bdfd  ldc.i4.s 0xA
0x5bdff  callvirt instance valuetype [mscorlib]System.DateTime [System.Data]System.Data.IDataRecord::GetDateTime(int32)
0x5be04  stloc.s  0xF
0x5be06  ldnull
0x5be07  stloc.s  0x10
0x5be09  ldloc.s  4
0x5be0b  ldc.i4.s 0xB
0x5be0d  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5be12  brtrue.s loc_5BE1F
0x5be14  ldloc.s  4
0x5be16  ldc.i4.s 0xB
0x5be18  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0x5be1d  stloc.s  0x10
0x5be1f  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x5be24  stloc.s  0x11
0x5be26  ldloc.s  4
0x5be28  ldc.i4.s 0xC
0x5be2a  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5be2f  brtrue.s loc_5BE3C
0x5be31  ldloc.s  4
0x5be33  ldc.i4.s 0xC
0x5be35  callvirt instance valuetype [mscorlib]System.DateTime [System.Data]System.Data.IDataRecord::GetDateTime(int32)
0x5be3a  stloc.s  0x11
0x5be3c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5be41  stloc.s  0x12
0x5be43  ldloc.s  4
0x5be45  ldc.i4.s 0xD
0x5be47  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5be4c  brtrue.s loc_5BE59
0x5be4e  ldloc.s  4
0x5be50  ldc.i4.s 0xD
0x5be52  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.IDataRecord::GetGuid(int32)
0x5be57  stloc.s  0x12
0x5be59  ldc.i4.0
0x5be5a  stloc.s  0x13
0x5be5c  ldloc.s  4
0x5be5e  ldc.i4.s 0xE
0x5be60  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5be65  brtrue.s loc_5BE72
0x5be67  ldloc.s  4
0x5be69  ldc.i4.s 0xE
0x5be6b  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0x5be70  stloc.s  0x13
0x5be72  ldc.i4.0
0x5be73  stloc.s  0x14
0x5be75  ldloc.s  4
0x5be77  ldc.i4.s 0xF
0x5be79  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5be7e  brtrue.s loc_5BE8B
0x5be80  ldloc.s  4
0x5be82  ldc.i4.s 0xF
0x5be84  callvirt instance bool [System.Data]System.Data.IDataRecord::GetBoolean(int32)
0x5be89  stloc.s  0x14
0x5be8b  ldloc.s  4
0x5be8d  ldc.i4.s 0x10
0x5be8f  callvirt instance valuetype [mscorlib]System.DateTime [System.Data]System.Data.IDataRecord::GetDateTime(int32)
0x5be94  stloc.s  0x15
0x5be96  ldnull
0x5be97  stloc.s  0x16
0x5be99  ldloc.s  4
0x5be9b  ldc.i4.s 0x11
0x5be9d  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5bea2  brtrue.s loc_5BEAF
0x5bea4  ldloc.s  4
0x5bea6  ldc.i4.s 0x11
0x5bea8  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0x5bead  stloc.s  0x16
0x5beaf  ldnull
0x5beb0  stloc.s  0x17
0x5beb2  ldloc.s  4
0x5beb4  ldc.i4.s 0x12
0x5beb6  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5bebb  brtrue   loc_5BF53
0x5bec0  ldloc.s  4
0x5bec2  ldc.i4.s 0x13
0x5bec4  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5bec9  brtrue.s loc_5BEF7
0x5becb  ldloc.s  4
0x5becd  ldc.i4.s 0x14
0x5becf  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5bed4  brtrue.s loc_5BEF7
0x5bed6  ldloc.s  4
0x5bed8  ldc.i4.s 0x15
0x5beda  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5bedf  brtrue.s loc_5BEF7
0x5bee1  ldloc.s  4
0x5bee3  ldc.i4.s 0x16
0x5bee5  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5beea  brtrue.s loc_5BEF7
0x5beec  ldloc.s  4
0x5beee  ldc.i4.s 0x17
0x5bef0  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x5bef5  brfalse.s loc_5BF02
0x5bef7  ldstr    aSessionContain// "Session contains only partial page prop"...
0x5befc  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x5bf01  throw
0x5bf02  ldloc.s  4
0x5bf04  ldc.i4.s 0x12
0x5bf06  callvirt instance float64 [System.Data]System.Data.IDataRecord::GetDouble(int32)
0x5bf0b  ldloc.s  4
0x5bf0d  ldc.i4.s 0x13
0x5bf0f  callvirt instance float64 [System.Data]System.Data.IDataRecord::GetDouble(int32)
0x5bf14  stloc.s  0x26
0x5bf16  ldloc.s  4
0x5bf18  ldc.i4.s 0x14
0x5bf1a  callvirt instance float64 [System.Data]System.Data.IDataRecord::GetDouble(int32)
0x5bf1f  stloc.s  0x27
0x5bf21  ldloc.s  4
0x5bf23  ldc.i4.s 0x15
0x5bf25  callvirt instance float64 [System.Data]System.Data.IDataRecord::GetDouble(int32)
0x5bf2a  stloc.s  0x28
0x5bf2c  ldloc.s  4
0x5bf2e  ldc.i4.s 0x16
0x5bf30  callvirt instance float64 [System.Data]System.Data.IDataRecord::GetDouble(int32)
0x5bf35  stloc.s  0x29
0x5bf37  ldloc.s  4
0x5bf39  ldc.i4.s 0x17
0x5bf3b  callvirt instance float64 [System.Data]System.Data.IDataRecord::GetDouble(int32)
0x5bf40  stloc.s  0x2A
  ... truncated ...
```
