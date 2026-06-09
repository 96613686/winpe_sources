# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetPrincipalNameFromSid

- ea: `0x6870`
- end: `0x68ac`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetPrincipalNameFromSid`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x71c0`

## callees

- `0x6870`

## string_xrefs

- `0x6899`: `Invalid name returned by authentication extension`

## pseudocode

```c

```

## disassembly

```asm
0x6870  ldnull
0x6871  stloc.0
0x6872  ldc.i4.1
0x6873  call     class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IAuthenticationExtension2 [ReportingServicesLibrary]Microsoft.ReportingServices.Library.AuthenticationExtensionFactory::GetAuthenticationExtension(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType)
0x6878  isinst   [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IWindowsAuthenticationExtension2
0x687d  stloc.1
0x687e  ldloc.1
0x687f  brfalse.s loc_68AA
0x6881  ldloc.1
0x6882  ldarg.1
0x6883  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IWindowsAuthenticationExtension2::SidToPrincipalName(unsigned int8[])
0x6888  stloc.0
0x6889  ldloc.0
0x688a  brfalse.s loc_68AA
0x688c  ldloc.0
0x688d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x6892  ldc.i4   0x104
0x6897  ble.s    loc_68AA
0x6899  ldstr    aInvalidNameRet// "Invalid name returned by authentication"...
0x689e  ldloc.0
0x689f  call     string [mscorlib]System.String::Concat(string, string)
0x68a4  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(string)
0x68a9  throw
0x68aa  ldloc.0
0x68ab  ret
```
