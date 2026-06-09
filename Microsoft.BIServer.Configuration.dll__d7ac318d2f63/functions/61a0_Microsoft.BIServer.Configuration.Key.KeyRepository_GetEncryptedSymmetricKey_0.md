# Microsoft.BIServer.Configuration.Key.KeyRepository::GetEncryptedSymmetricKey_0

- ea: `0x61a0`
- end: `0x6333`
- name: `Microsoft.BIServer.Configuration.Key.KeyRepository::GetEncryptedSymmetricKey_0`
- size: `403`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x60e0`

## callees

- `0x61a0`

## string_xrefs

- `0x61ea`: `@InstallationID`
- `0x62f5`: `@InstallationID`
- `0x621d`: `@NumAnnouncedServices`
- `0x6246`: `Cannot read matching key for installation`

## pseudocode

```c

```

## disassembly

```asm
0x61a0  call     string [mscorlib]System.Environment::get_MachineName()
0x61a5  stloc.0
0x61a6  ldnull
0x61a7  stloc.1
0x61a8  ldnull
0x61a9  stloc.2
0x61aa  ldarg.0
0x61ab  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess Microsoft.BIServer.Configuration.Key.KeyRepository::_sql
0x61b0  ldstr    aAnnounceorgetk// "AnnounceOrGetKey"
0x61b5  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess::PrepareStoredProcedure(string)
0x61ba  stloc.3
0x61bb  ldloc.3
0x61bc  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::get_Parameters()
0x61c1  ldstr    aMachinename// "@MachineName"
0x61c6  ldloc.0
0x61c7  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x61cc  pop
0x61cd  ldloc.3
0x61ce  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::get_Parameters()
0x61d3  ldstr    aInstancename_1// "@InstanceName"
0x61d8  ldarg.1
0x61d9  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.InstallationInfo::get_InstanceName()
0x61de  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x61e3  pop
0x61e4  ldloc.3
0x61e5  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::get_Parameters()
0x61ea  ldstr    aInstallationid_0// "@InstallationID"
0x61ef  ldarg.1
0x61f0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.InstallationInfo::get_InstallationId()
0x61f5  box      [mscorlib]System.Guid
0x61fa  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x61ff  pop
0x6200  ldloc.3
0x6201  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::get_Parameters()
0x6206  ldstr    aPublickey// "@PublicKey"
0x620b  ldarg.1
0x620c  callvirt instance unsigned int8[] [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.InstallationInfo::get_PublicKey()
0x6211  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6216  pop
0x6217  ldloc.3
0x6218  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::get_Parameters()
0x621d  ldstr    aNumannouncedse// "@NumAnnouncedServices"
0x6222  ldc.i4.8
0x6223  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x6228  stloc.s  4
0x622a  ldloc.s  4
0x622c  ldc.i4.2
0x622d  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x6232  ldnull
0x6233  stloc.s  5
0x6235  ldloc.3
0x6236  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::ExecuteReader()
0x623b  stloc.s  6
0x623d  ldloc.s  6
0x623f  callvirt instance bool [System.Data]System.Data.Common.DbDataReader::Read()
0x6244  brtrue.s loc_6251
0x6246  ldstr    aCannotReadMatc// "Cannot read matching key for installati"...
0x624b  newobj   instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.Exceptions.DatabaseConfigurationException::.ctor(string)
0x6250  throw
0x6251  ldarg.0
0x6252  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess Microsoft.BIServer.Configuration.Key.KeyRepository::_sql
0x6257  ldloc.s  6
0x6259  ldc.i4.0
0x625a  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess::GetStringOrNullColumn(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32)
0x625f  stloc.s  5
0x6261  ldarg.0
0x6262  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess Microsoft.BIServer.Configuration.Key.KeyRepository::_sql
0x6267  ldloc.s  6
0x6269  ldc.i4.1
0x626a  callvirt instance unsigned int8[] [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess::GetBinaryOrNullColumn(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32)
0x626f  stloc.1
0x6270  ldarg.0
0x6271  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess Microsoft.BIServer.Configuration.Key.KeyRepository::_sql
0x6276  ldloc.s  6
0x6278  ldc.i4.2
0x6279  callvirt instance unsigned int8[] [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess::GetBinaryOrNullColumn(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32)
0x627e  stloc.2
0x627f  ldloc.s  6
0x6281  callvirt instance bool [System.Data]System.Data.Common.DbDataReader::Read()
0x6286  brfalse.s loc_6293
0x6288  ldstr    aMoreThanOneMat// "More than one matching key record prese"...
0x628d  newobj   instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.Exceptions.DatabaseConfigurationException::.ctor(string)
0x6292  throw
0x6293  leave.s  loc_62A1
0x6295  ldloc.s  6
0x6297  brfalse.s loc_62A0
0x6299  ldloc.s  6
0x629b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x62a0  endfinally
0x62a1  ldloc.s  4
0x62a3  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x62a8  unbox.any [mscorlib]System.Int32
0x62ad  ldc.i4.1
0x62ae  pop
0x62af  pop
0x62b0  ldloc.0
0x62b1  ldloc.s  5
0x62b3  ldc.i4.5
0x62b4  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x62b9  brtrue.s loc_6321
0x62bb  ldarg.1
0x62bc  callvirt instance unsigned int8[] [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.InstallationInfo::get_PublicKey()
0x62c1  ldloc.2
0x62c2  call     T0x2B000023
0x62c7  brfalse.s loc_6321
0x62c9  ldarg.0
0x62ca  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess Microsoft.BIServer.Configuration.Key.KeyRepository::_sql
0x62cf  ldstr    aSetmachinename// "SetMachineName"
0x62d4  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess::PrepareStoredProcedure(string)
0x62d9  stloc.s  7
0x62db  ldloc.s  7
0x62dd  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::get_Parameters()
0x62e2  ldstr    aMachinename// "@MachineName"
0x62e7  ldloc.0
0x62e8  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x62ed  pop
0x62ee  ldloc.s  7
0x62f0  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::get_Parameters()
0x62f5  ldstr    aInstallationid_0// "@InstallationID"
0x62fa  ldarg.1
0x62fb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.InstallationInfo::get_InstallationId()
0x6300  box      [mscorlib]System.Guid
0x6305  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x630a  pop
0x630b  ldloc.s  7
0x630d  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x6312  pop
0x6313  leave.s  loc_6321
0x6315  ldloc.s  7
0x6317  brfalse.s loc_6320
0x6319  ldloc.s  7
0x631b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6320  endfinally
0x6321  ldloc.1
0x6322  stloc.s  8
0x6324  leave.s  loc_6330
0x6326  ldloc.3
0x6327  brfalse.s loc_632F
0x6329  ldloc.3
0x632a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x632f  endfinally
0x6330  ldloc.s  8
0x6332  ret
```
