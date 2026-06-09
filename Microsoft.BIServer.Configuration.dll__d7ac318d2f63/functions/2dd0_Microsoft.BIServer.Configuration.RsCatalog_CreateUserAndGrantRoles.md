# Microsoft.BIServer.Configuration.RsCatalog::CreateUserAndGrantRoles

- ea: `0x2dd0`
- end: `0x2e2b`
- name: `Microsoft.BIServer.Configuration.RsCatalog::CreateUserAndGrantRoles`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2e30`

## string_xrefs

- `0x2e02`: `TempDB`
- `0x2dd0`: `\n            IF NOT EXISTS \n                (SELECT name  \n                 FROM master.sys.server_principals\n                 WHERE name = '{0}')\n            BEGIN\n                CREATE LOGIN [{0}] from windows\n            END\n        `

## pseudocode

```c

```

## disassembly

```asm
0x2dd0  ldstr    aIfNotExistsSel// "\r\n            IF NOT EXISTS \r\n     "...
0x2dd5  ldarg.1
0x2dd6  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials::get_DomainUser()
0x2ddb  call     string [mscorlib]System.String::Format(string, object)
0x2de0  stloc.0
0x2de1  ldarg.0
0x2de2  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess Microsoft.BIServer.Configuration.RsCatalog::_conn
0x2de7  ldloc.0
0x2de8  ldnull
0x2de9  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess::ExecuteNonQuery(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x2dee  ldarg.0
0x2def  ldarg.0
0x2df0  ldfld    string Microsoft.BIServer.Configuration.RsCatalog::_reportServerDatabaseName
0x2df5  ldarg.1
0x2df6  call     instance void Microsoft.BIServer.Configuration.RsCatalog::AddUserAndRoleForDatabase(string databaseName, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials accountCredentials)
0x2dfb  ldarg.0
0x2dfc  ldarg.0
0x2dfd  ldfld    string Microsoft.BIServer.Configuration.RsCatalog::_reportServerDatabaseName
0x2e02  ldstr    aTempdb// "TempDB"
0x2e07  call     string [mscorlib]System.String::Concat(string, string)
0x2e0c  ldarg.1
0x2e0d  call     instance void Microsoft.BIServer.Configuration.RsCatalog::AddUserAndRoleForDatabase(string databaseName, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials accountCredentials)
0x2e12  ldarg.0
0x2e13  ldstr    aMaster// "master"
0x2e18  ldarg.1
0x2e19  call     instance void Microsoft.BIServer.Configuration.RsCatalog::AddUserAndRoleForDatabase(string databaseName, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials accountCredentials)
0x2e1e  ldarg.0
0x2e1f  ldstr    aMsdb// "msdb"
0x2e24  ldarg.1
0x2e25  call     instance void Microsoft.BIServer.Configuration.RsCatalog::AddUserAndRoleForDatabase(string databaseName, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials accountCredentials)
0x2e2a  ret
```
