# Microsoft.ReportingServices.Library.ConnectionConfig::ImpersonateCatUser

- ea: `0x7c50`
- end: `0x7cac`
- name: `Microsoft.ReportingServices.Library.ConnectionConfig::ImpersonateCatUser`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x3970`

## callees

- `0x7c50`
- `0x7cb0`

## pseudocode

```c

```

## disassembly

```asm
0x7c50  ldarg.0
0x7c51  ldfld    object Microsoft.ReportingServices.Library.ConnectionConfig::_catUserSync
0x7c56  stloc.0
0x7c57  ldc.i4.0
0x7c58  stloc.1
0x7c59  ldloc.0
0x7c5a  ldloca.s 1
0x7c5c  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x7c61  ldarg.0
0x7c62  ldfld    class [mscorlib]System.Security.Principal.WindowsIdentity Microsoft.ReportingServices.Library.ConnectionConfig::_catUser
0x7c67  brtrue.s loc_7C92
0x7c69  ldarg.0
0x7c6a  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x7c6f  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_CatalogUser()
0x7c74  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x7c79  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_CatalogDomain()
0x7c7e  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x7c83  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_CatalogCred()
0x7c88  call     class [mscorlib]System.Security.Principal.WindowsIdentity Microsoft.ReportingServices.Library.ConnectionConfig::GetImpersonationUser(string userName, string domain, string userPwd)
0x7c8d  stfld    class [mscorlib]System.Security.Principal.WindowsIdentity Microsoft.ReportingServices.Library.ConnectionConfig::_catUser
0x7c92  ldarg.0
0x7c93  ldfld    class [mscorlib]System.Security.Principal.WindowsIdentity Microsoft.ReportingServices.Library.ConnectionConfig::_catUser
0x7c98  callvirt instance class [mscorlib]System.Security.Principal.WindowsImpersonationContext [mscorlib]System.Security.Principal.WindowsIdentity::Impersonate()
0x7c9d  stloc.2
0x7c9e  leave.s  loc_7CAA
0x7ca0  ldloc.1
0x7ca1  brfalse.s loc_7CA9
0x7ca3  ldloc.0
0x7ca4  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x7ca9  endfinally
0x7caa  ldloc.2
0x7cab  ret
```
