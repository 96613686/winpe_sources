# Microsoft.ReportingServices.Library.Security::get_AuthorizationExtension

- ea: `0x48b00`
- end: `0x48b31`
- name: `Microsoft.ReportingServices.Library.Security::get_AuthorizationExtension`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x4b0b0`

## callees

- `0x10020`
- `0x48b00`

## string_xrefs

- `0x48b13`: `Security`
- `0x48b25`: `Could not load Authorization extension`

## pseudocode

```c

```

## disassembly

```asm
0x48b00  call     valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType Microsoft.ReportingServices.Library.WebConfigUtil::get_WebServerAuthMode()
0x48b05  stloc.0
0x48b06  ldloca.s 0
0x48b08  constrained. [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType
0x48b0e  callvirt instance string [mscorlib]System.Object::ToString()
0x48b13  ldstr    aSecurity_0// "Security"
0x48b18  call     class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IExtension [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::GetNewInstanceExtensionClass(string, string)
0x48b1d  isinst   [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IAuthorizationExtension
0x48b22  dup
0x48b23  brtrue.s loc_48B30
0x48b25  ldstr    aCouldNotLoadAu// "Could not load Authorization extension"
0x48b2a  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(string)
0x48b2f  throw
0x48b30  ret
```
