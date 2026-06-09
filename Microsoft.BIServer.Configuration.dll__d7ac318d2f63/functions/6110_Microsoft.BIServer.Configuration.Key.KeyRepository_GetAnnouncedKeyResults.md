# Microsoft.BIServer.Configuration.Key.KeyRepository::GetAnnouncedKeyResults

- ea: `0x6110`
- end: `0x619f`
- name: `Microsoft.BIServer.Configuration.Key.KeyRepository::GetAnnouncedKeyResults`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x60e0`

## callees

- `0x6110`

## string_xrefs

- `0x6127`: `InstallationID`

## pseudocode

```c

```

## disassembly

```asm
0x6110  ldarg.0
0x6111  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess Microsoft.BIServer.Configuration.Key.KeyRepository::_sql
0x6116  ldstr    aGetannouncedke// "GetAnnouncedKey"
0x611b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess::PrepareStoredProcedure(string)
0x6120  stloc.0
0x6121  ldloc.0
0x6122  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::get_Parameters()
0x6127  ldstr    aInstallationid// "InstallationID"
0x612c  ldarg.1
0x612d  box      [mscorlib]System.Guid
0x6132  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6137  pop
0x6138  ldloc.0
0x6139  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::ExecuteReader()
0x613e  stloc.1
0x613f  ldloc.1
0x6140  callvirt instance bool [System.Data]System.Data.Common.DbDataReader::Read()
0x6145  brfalse.s loc_6180
0x6147  ldarg.0
0x6148  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess Microsoft.BIServer.Configuration.Key.KeyRepository::_sql
0x614d  ldloc.1
0x614e  ldc.i4.0
0x614f  callvirt instance unsigned int8[] [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess::GetBinaryOrNullColumn(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32)
0x6154  stloc.2
0x6155  ldarg.0
0x6156  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess Microsoft.BIServer.Configuration.Key.KeyRepository::_sql
0x615b  ldloc.1
0x615c  ldc.i4.1
0x615d  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess::GetStringOrNullColumn(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32)
0x6162  stloc.3
0x6163  ldarg.0
0x6164  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess Microsoft.BIServer.Configuration.Key.KeyRepository::_sql
0x6169  ldloc.1
0x616a  ldc.i4.2
0x616b  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess::GetStringOrNullColumn(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlDataReader, int32)
0x6170  stloc.s  4
0x6172  ldarg.1
0x6173  ldloc.3
0x6174  ldloc.s  4
0x6176  ldloc.2
0x6177  newobj   instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.InstallationInfo::.ctor(valuetype [mscorlib]System.Guid, string, string, unsigned int8[])
0x617c  stloc.s  5
0x617e  leave.s  loc_619C
0x6180  leave.s  loc_6196
0x6182  ldloc.1
0x6183  brfalse.s loc_618B
0x6185  ldloc.1
0x6186  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x618b  endfinally
0x618c  ldloc.0
0x618d  brfalse.s loc_6195
0x618f  ldloc.0
0x6190  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6195  endfinally
0x6196  newobj   instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.Exceptions.SymmetricKeyNotInitializedException::.ctor()
0x619b  throw
0x619c  ldloc.s  5
0x619e  ret
```
