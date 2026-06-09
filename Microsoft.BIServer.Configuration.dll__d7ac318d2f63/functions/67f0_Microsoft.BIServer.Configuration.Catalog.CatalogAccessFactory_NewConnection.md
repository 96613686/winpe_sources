# Microsoft.BIServer.Configuration.Catalog.CatalogAccessFactory::NewConnection

- ea: `0x67f0`
- end: `0x6872`
- name: `Microsoft.BIServer.Configuration.Catalog.CatalogAccessFactory::NewConnection`
- size: `130`
- prototype: ``
- caller_count: `7`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6080`
- `0x6880`
- `0x69d0`
- `0x78c0`
- `0x79b0`
- `0x7aa0`
- `0x7b90`

## callees

- `0xe40`
- `0xf00`
- `0xf40`
- `0xf80`
- `0xfc0`
- `0xff0`
- `0x67b0`
- `0x67f0`

## pseudocode

```c

```

## disassembly

```asm
0x67f0  call     class Microsoft.BIServer.Configuration.ConfigReader Microsoft.BIServer.Configuration.ConfigReader::get_Current()
0x67f5  callvirt instance string Microsoft.BIServer.Configuration.ConfigReader::get_RsConnectionString()
0x67fa  stloc.0
0x67fb  ldloc.0
0x67fc  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x6801  brfalse.s loc_680E
0x6803  ldstr    aRsConnectionSt// "RS Connection String not set"
0x6808  newobj   instance void Microsoft.BIServer.Configuration.Exceptions.ConfigException::.ctor(string message)
0x680d  throw
0x680e  call     class Microsoft.BIServer.Configuration.ConfigReader Microsoft.BIServer.Configuration.ConfigReader::get_Current()
0x6813  callvirt instance valuetype Microsoft.BIServer.Configuration.CatalogConnectionType Microsoft.BIServer.Configuration.ConfigReader::get_ConnectionType()
0x6818  ldc.i4.1
0x6819  bne.un.s loc_6869
0x681b  call     class Microsoft.BIServer.Configuration.ConfigReader Microsoft.BIServer.Configuration.ConfigReader::get_Current()
0x6820  callvirt instance string Microsoft.BIServer.Configuration.ConfigReader::get_CatalogDomain()
0x6825  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x682a  brtrue.s loc_6869
0x682c  call     class Microsoft.BIServer.Configuration.ConfigReader Microsoft.BIServer.Configuration.ConfigReader::get_Current()
0x6831  callvirt instance string Microsoft.BIServer.Configuration.ConfigReader::get_CatalogDomain()
0x6836  call     class Microsoft.BIServer.Configuration.ConfigReader Microsoft.BIServer.Configuration.ConfigReader::get_Current()
0x683b  callvirt instance string Microsoft.BIServer.Configuration.ConfigReader::get_CatalogUser()
0x6840  call     class Microsoft.BIServer.Configuration.ConfigReader Microsoft.BIServer.Configuration.ConfigReader::get_Current()
0x6845  callvirt instance string Microsoft.BIServer.Configuration.ConfigReader::get_CatalogCred()
0x684a  ldc.i4.0
0x684b  newobj   instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials::.ctor(string, string, string, valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountType)
0x6850  call     class [mscorlib]System.IDisposable [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ImpersonationContext::EnterUserContext(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials)
0x6855  stloc.1
0x6856  ldloc.0
0x6857  newobj   instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::.ctor(string)
0x685c  stloc.2
0x685d  leave.s  loc_6870
0x685f  ldloc.1
0x6860  brfalse.s loc_6868
0x6862  ldloc.1
0x6863  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6868  endfinally
0x6869  ldloc.0
0x686a  newobj   instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::.ctor(string)
0x686f  ret
0x6870  ldloc.2
0x6871  ret
```
