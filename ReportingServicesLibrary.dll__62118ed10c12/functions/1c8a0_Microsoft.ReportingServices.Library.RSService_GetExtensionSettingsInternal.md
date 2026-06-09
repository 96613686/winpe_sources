# Microsoft.ReportingServices.Library.RSService::GetExtensionSettingsInternal

- ea: `0x1c8a0`
- end: `0x1c8ea`
- name: `Microsoft.ReportingServices.Library.RSService::GetExtensionSettingsInternal`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1c870`

## callees

- `0x157f0`
- `0x1c8a0`

## string_xrefs

- `0x1c8a3`: `Extension`
- `0x1c8c1`: `Extension`

## pseudocode

```c

```

## disassembly

```asm
0x1c8a0  ldarg.1
0x1c8a1  brtrue.s loc_1C8AE
0x1c8a3  ldstr    aExtension_0// "Extension"
0x1c8a8  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidParameterException::.ctor(string)
0x1c8ad  throw
0x1c8ae  ldarg.1
0x1c8af  ldstr    aDelivery// "Delivery"
0x1c8b4  call     class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IExtension [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::GetNewInstanceExtensionClass(string, string)
0x1c8b9  isinst   [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IDeliveryExtension
0x1c8be  dup
0x1c8bf  brtrue.s loc_1C8CC
0x1c8c1  ldstr    aExtension_0// "Extension"
0x1c8c6  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidParameterException::.ctor(string)
0x1c8cb  throw
0x1c8cc  ldc.i4.1
0x1c8cd  ldarg.0
0x1c8ce  ldnull
0x1c8cf  call     class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Library.ProviderManager::InitDeliveryExtension(class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IDeliveryExtension extension, bool isPrivileged, class Microsoft.ReportingServices.Library.RSService rsService, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath itemPath)
0x1c8d4  stloc.0
0x1c8d5  leave.s  loc_1C8E8
0x1c8d7  dup
0x1c8d8  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException
0x1c8dd  brfalse.s loc_1C8E1
0x1c8df  rethrow
0x1c8e1  ldnull
0x1c8e2  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(class [mscorlib]System.Exception, string)
0x1c8e7  throw
0x1c8e8  ldloc.0
0x1c8e9  ret
```
