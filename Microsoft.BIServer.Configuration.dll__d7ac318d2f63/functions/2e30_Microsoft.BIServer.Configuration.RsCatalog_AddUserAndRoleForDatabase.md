# Microsoft.BIServer.Configuration.RsCatalog::AddUserAndRoleForDatabase

- ea: `0x2e30`
- end: `0x2ec0`
- name: `Microsoft.BIServer.Configuration.RsCatalog::AddUserAndRoleForDatabase`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x2dd0`

## callees

- `0x2e30`
- `0x2ec0`

## string_xrefs

- `0x2e66`: `\n            select sysusers.name as DbUser from sys.sysusers\n            join sys.syslogins on sysusers.sid = syslogins.sid\n            where syslogins.name = @LoginName\n        `
- `0x2e75`: `\n            IF NOT EXISTS\n                (SELECT name\n                 FROM sys.database_principals\n                 WHERE name = '{0}')\n            BEGIN\n                CREATE USER [{0}] FOR LOGIN [{0}] \n            END\n        `

## pseudocode

```c

```

## disassembly

```asm
0x2e30  ldstr    aUse// "use "
0x2e35  ldarg.1
0x2e36  call     string [mscorlib]System.String::Concat(string, string)
0x2e3b  stloc.0
0x2e3c  ldarg.0
0x2e3d  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess Microsoft.BIServer.Configuration.RsCatalog::_conn
0x2e42  ldloc.0
0x2e43  ldnull
0x2e44  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess::ExecuteNonQuery(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x2e49  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x2e4e  stloc.1
0x2e4f  ldloc.1
0x2e50  ldstr    aLoginname// "LoginName"
0x2e55  ldarg.2
0x2e56  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials::get_DomainUser()
0x2e5b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2e60  ldarg.0
0x2e61  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess Microsoft.BIServer.Configuration.RsCatalog::_conn
0x2e66  ldstr    aSelectSysusers// "\r\n            select sysusers.name as"...
0x2e6b  ldloc.1
0x2e6c  callvirt T0x2B00002B
0x2e71  stloc.2
0x2e72  ldloc.2
0x2e73  brtrue.s loc_2E9A
0x2e75  ldstr    aIfNotExistsSel_0// "\r\n            IF NOT EXISTS\r\n      "...
0x2e7a  ldarg.2
0x2e7b  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials::get_DomainUser()
0x2e80  call     string [mscorlib]System.String::Format(string, object)
0x2e85  stloc.0
0x2e86  ldarg.0
0x2e87  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess Microsoft.BIServer.Configuration.RsCatalog::_conn
0x2e8c  ldloc.0
0x2e8d  ldnull
0x2e8e  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess::ExecuteNonQuery(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x2e93  ldarg.2
0x2e94  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials::get_DomainUser()
0x2e99  stloc.2
0x2e9a  ldloc.2
0x2e9b  ldstr    aDbo// "dbo"
0x2ea0  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x2ea5  brfalse.s loc_2EBF
0x2ea7  ldarg.0
0x2ea8  ldstr    aRsexecrole// "RSExecRole"
0x2ead  ldloc.2
0x2eae  call     instance void Microsoft.BIServer.Configuration.RsCatalog::AddRole(string roleName, string memberName)
0x2eb3  ldarg.0
0x2eb4  ldstr    aDbOwner// "db_owner"
0x2eb9  ldloc.2
0x2eba  call     instance void Microsoft.BIServer.Configuration.RsCatalog::AddRole(string roleName, string memberName)
0x2ebf  ret
```
