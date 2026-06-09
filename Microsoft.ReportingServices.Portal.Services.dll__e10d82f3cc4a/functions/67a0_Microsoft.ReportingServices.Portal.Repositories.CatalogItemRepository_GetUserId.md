# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetUserId

- ea: `0x67a0`
- end: `0x67ee`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetUserId`
- size: `78`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x6940`
- `0x73b0`
- `0x1e6d0`

## callees

- `0x67a0`
- `0x6840`

## pseudocode

```c

```

## disassembly

```asm
0x67a0  ldc.i4.1
0x67a1  ldarg.2
0x67a2  bne.un.s loc_67C0
0x67a4  ldarg.0
0x67a5  ldarg.1
0x67a6  call     instance unsigned int8[] Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetSidFromUserName(string userName)
0x67ab  stloc.0
0x67ac  ldarg.0
0x67ad  ldfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_catalogAccessor
0x67b2  ldloc.0
0x67b3  ldarg.1
0x67b4  ldarg.2
0x67b5  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<valuetype [mscorlib]System.Guid> [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataAccessor::GetUserID(unsigned int8[], string, int32)
0x67ba  callvirt instance var<u1> class [mscorlib]System.Threading.Tasks.Task`1<valuetype [mscorlib]System.Guid>::get_Result()
0x67bf  ret
0x67c0  ldarg.2
0x67c1  call     class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IAuthenticationExtension2 [ReportingServicesLibrary]Microsoft.ReportingServices.Library.AuthenticationExtensionFactory::GetAuthenticationExtension(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType)
0x67c6  ldarg.1
0x67c7  callvirt instance bool [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IAuthenticationExtension2::IsValidPrincipalName(string)
0x67cc  brtrue.s loc_67D5
0x67ce  ldarg.1
0x67cf  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.UnknownUserNameException::.ctor(string)
0x67d4  throw
0x67d5  ldarg.0
0x67d6  ldfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_catalogAccessor
0x67db  ldc.i4.0
0x67dc  newarr   [mscorlib]System.Byte
0x67e1  ldarg.1
0x67e2  ldarg.2
0x67e3  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<valuetype [mscorlib]System.Guid> [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataAccessor::GetUserID(unsigned int8[], string, int32)
0x67e8  callvirt instance var<u1> class [mscorlib]System.Threading.Tasks.Task`1<valuetype [mscorlib]System.Guid>::get_Result()
0x67ed  ret
```
