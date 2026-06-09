# Microsoft.BIServer.Configuration.ConfigReader::<Init>b__57_2

- ea: `0x1bb0`
- end: `0x1bf2`
- name: `Microsoft.BIServer.Configuration.ConfigReader::<Init>b__57_2`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x13b0`
- `0x1430`
- `0x15d0`
- `0x3600`

## pseudocode

```c

```

## disassembly

```asm
0x1bb0  ldarg.0
0x1bb1  ldarg.0
0x1bb2  ldstr    aDsn// "Dsn"
0x1bb7  call     instance string Microsoft.BIServer.Configuration.ConfigReader::ReadString(string fieldName)
0x1bbc  ldstr    aDsn// "Dsn"
0x1bc1  call     instance string Microsoft.BIServer.Configuration.ConfigReader::DecryptConfigData(string encryptedData, string element)
0x1bc6  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnectionStringBuilder::.ctor(string)
0x1bcb  dup
0x1bcc  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::GetCurrentProcess()
0x1bd1  callvirt instance string [System]System.Diagnostics.Process::get_ProcessName()
0x1bd6  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnectionStringBuilder::set_ApplicationName(string)
0x1bdb  dup
0x1bdc  ldarg.0
0x1bdd  call     instance class Microsoft.BIServer.Configuration.ServiceSettings Microsoft.BIServer.Configuration.ConfigReader::GetServiceSettings()
0x1be2  callvirt instance int32 Microsoft.BIServer.Configuration.ServiceSettings::get_MaxCatalogConnectionPoolSizePerProcess()
0x1be7  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnectionStringBuilder::set_MaxPoolSize(int32)
0x1bec  callvirt instance string [System.Data]System.Data.Common.DbConnectionStringBuilder::get_ConnectionString()
0x1bf1  ret
```
