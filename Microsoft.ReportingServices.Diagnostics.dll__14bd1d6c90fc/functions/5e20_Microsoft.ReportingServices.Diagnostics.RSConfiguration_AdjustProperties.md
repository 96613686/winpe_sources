# Microsoft.ReportingServices.Diagnostics.RSConfiguration::AdjustProperties

- ea: `0x5e20`
- end: `0x5e71`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfiguration::AdjustProperties`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x4bd0`

## callees

- `0x17c0`
- `0x5e20`
- `0xcb00`

## pseudocode

```c

```

## disassembly

```asm
0x5e20  ldarg.1
0x5e21  ldc.i4.s 0x1C
0x5e23  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Item(void)
0x5e28  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x5e2d  castclass [mscorlib]System.String
0x5e32  stloc.0
0x5e33  ldloc.0
0x5e34  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5e39  brtrue.s loc_5E70
0x5e3b  ldloc.0
0x5e3c  call     valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType Microsoft.ReportingServices.Diagnostics.Sku::GetInstalledSku(string instanceId)
0x5e41  stloc.1
0x5e42  ldarg.1
0x5e43  ldc.i4.s 0x63
0x5e45  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::ContainsKey(var<u1>)
0x5e4a  brfalse.s loc_5E70
0x5e4c  ldarg.1
0x5e4d  ldc.i4.s 0x63
0x5e4f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::get_Item(void)
0x5e54  stloc.2
0x5e55  ldloc.2
0x5e56  brfalse.s loc_5E70
0x5e58  ldloc.2
0x5e59  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x5e5e  castclass [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration
0x5e63  dup
0x5e64  ldloc.1
0x5e65  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::AdjustRenderingExtensionsForSku(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration, valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType)
0x5e6a  ldloc.1
0x5e6b  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::AdjustDataExtensionsForSku(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration, valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType)
0x5e70  ret
```
