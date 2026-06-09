# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ValidateAndNormalizeUsers

- ea: `0x71c0`
- end: `0x7238`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ValidateAndNormalizeUsers`
- size: `120`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x1ee90`
- `0x1f010`

## callees

- `0x6840`
- `0x6870`
- `0x71c0`
- `0x12db0`

## pseudocode

```c

```

## disassembly

```asm
0x71c0  ldarg.2
0x71c1  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x71c6  call     valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType Microsoft.ReportingServices.Portal.Services.Extensions.IdentityExtensions::ToAuthenticationType(class [mscorlib]System.Security.Principal.IIdentity identity)
0x71cb  stloc.0
0x71cc  ldc.i4.1
0x71cd  ldloc.0
0x71ce  bne.un.s loc_7237
0x71d0  ldarg.1
0x71d1  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment>::GetEnumerator()
0x71d6  stloc.1
0x71d7  br.s     loc_7223
0x71d9  ldloc.1
0x71da  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment>::get_Current()
0x71df  stloc.2
0x71e0  ldarg.0
0x71e1  ldloc.2
0x71e2  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment::get_GroupUserName()
0x71e7  call     instance unsigned int8[] Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetSidFromUserName(string userName)
0x71ec  stloc.3
0x71ed  ldarg.0
0x71ee  ldloc.3
0x71ef  call     instance string Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetPrincipalNameFromSid(unsigned int8[] sidBytes)
0x71f4  stloc.s  4
0x71f6  ldloc.s  4
0x71f8  brfalse.s loc_7202
0x71fa  ldloc.2
0x71fb  ldloc.s  4
0x71fd  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment::set_GroupUserName(string)
0x7202  leave.s  loc_7223
0x7204  pop
0x7205  ldarg.0
0x7206  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_logger
0x720b  ldc.i4.3
0x720c  ldstr    aUnknownusernam// "UnknownUserNameException when normalizi"...
0x7211  ldloc.2
0x7212  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment::get_GroupUserName()
0x7217  call     string [mscorlib]System.String::Format(string, object)
0x721c  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x7221  leave.s  loc_7223
0x7223  ldloc.1
0x7224  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7229  brtrue.s loc_71D9
0x722b  leave.s  loc_7237
0x722d  ldloc.1
0x722e  brfalse.s loc_7236
0x7230  ldloc.1
0x7231  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7236  endfinally
0x7237  ret
```
