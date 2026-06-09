# Microsoft.ReportingServices.Library.RSService::ValidateExtensionSettings

- ea: `0x1c690`
- end: `0x1c716`
- name: `Microsoft.ReportingServices.Library.RSService::ValidateExtensionSettings`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x40510`

## callees

- `0xc340`
- `0xc420`
- `0xc560`
- `0x157f0`
- `0x1c690`
- `0x1c720`
- `0x1e3e0`
- `0x1e460`

## string_xrefs

- `0x1c693`: `Extension`
- `0x1c6c4`: `Extension`

## pseudocode

```c

```

## disassembly

```asm
0x1c690  ldarg.1
0x1c691  brtrue.s loc_1C69E
0x1c693  ldstr    aExtension_0// "Extension"
0x1c698  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidParameterException::.ctor(string)
0x1c69d  throw
0x1c69e  ldarg.0
0x1c69f  call     instance void Microsoft.ReportingServices.Library.RSService::WillDisconnectStorage()
0x1c6a4  ldarg.1
0x1c6a5  ldstr    aDelivery// "Delivery"
0x1c6aa  call     class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IExtension [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::GetNewInstanceExtensionClass(string, string)
0x1c6af  newobj   instance void Microsoft.ReportingServices.Library.Settings::.ctor()
0x1c6b4  stloc.1
0x1c6b5  ldloc.1
0x1c6b6  ldarg.2
0x1c6b7  callvirt instance void Microsoft.ReportingServices.Library.Settings::FromSoapParameterValueArray(class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] parameters)
0x1c6bc  dup
0x1c6bd  isinst   [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IDeliveryExtension
0x1c6c2  brtrue.s loc_1C6CF
0x1c6c4  ldstr    aExtension_0// "Extension"
0x1c6c9  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidParameterException::.ctor(string)
0x1c6ce  throw
0x1c6cf  castclass [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IDeliveryExtension
0x1c6d4  ldarg.3
0x1c6d5  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath::.ctor(string)
0x1c6da  stloc.2
0x1c6db  dup
0x1c6dc  ldc.i4.1
0x1c6dd  ldarg.0
0x1c6de  ldloc.2
0x1c6df  call     class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Library.ProviderManager::InitDeliveryExtension(class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IDeliveryExtension extension, bool isPrivileged, class Microsoft.ReportingServices.Library.RSService rsService, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath itemPath)
0x1c6e4  pop
0x1c6e5  ldloc.1
0x1c6e6  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Library.Settings::get_SettingsArray()
0x1c6eb  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IDeliveryExtension::ValidateUserData(class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[])
0x1c6f0  stloc.0
0x1c6f1  ldarg.0
0x1c6f2  ldloc.0
0x1c6f3  ldc.i4.0
0x1c6f4  call     instance class Microsoft.ReportingServices.Library.Soap.ExtensionParameter[] Microsoft.ReportingServices.Library.RSService::CLRSettingToSoapSettingArray(class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] settings, bool doReturnValue)
0x1c6f9  stloc.3
0x1c6fa  leave.s  loc_1C714
0x1c6fc  dup
0x1c6fd  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException
0x1c702  brfalse.s loc_1C706
0x1c704  rethrow
0x1c706  ldnull
0x1c707  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(class [mscorlib]System.Exception, string)
0x1c70c  throw
0x1c70d  ldarg.0
0x1c70e  call     instance void Microsoft.ReportingServices.Library.RSService::DisconnectStorage()
0x1c713  endfinally
0x1c714  ldloc.3
0x1c715  ret
```
