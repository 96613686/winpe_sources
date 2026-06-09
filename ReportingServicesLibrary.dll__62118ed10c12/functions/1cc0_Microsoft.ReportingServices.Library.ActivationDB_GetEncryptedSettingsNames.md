# Microsoft.ReportingServices.Library.ActivationDB::GetEncryptedSettingsNames

- ea: `0x1cc0`
- end: `0x1d88`
- name: `Microsoft.ReportingServices.Library.ActivationDB::GetEncryptedSettingsNames`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1c20`

## callees

- `0x1cc0`
- `0x157f0`

## string_xrefs

- `0x1d08`: `Reencryption: Failed to load extension. Not reencrypting settings for this extension in subscriptions. Extension='{0}'`
- `0x1d2e`: `Reencryption: Extension is not a delivery provider. Not reencrypting settings for this extension in subscriptions. Extension='{0}'`

## pseudocode

```c

```

## disassembly

```asm
0x1cc0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x1cc5  stloc.0
0x1cc6  ldarg.1
0x1cc7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1ccc  brtrue.s loc_1CDE
0x1cce  ldarg.0
0x1ccf  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>> Microsoft.ReportingServices.Library.ActivationDB::m_encryptedSettingsForExtension
0x1cd4  ldarg.1
0x1cd5  ldloca.s 0
0x1cd7  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>>::TryGetValue(var<u1>, !!T0)
0x1cdc  brfalse.s loc_1CE0
0x1cde  ldloc.0
0x1cdf  ret
0x1ce0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x1ce5  stloc.0
0x1ce6  ldarg.0
0x1ce7  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>> Microsoft.ReportingServices.Library.ActivationDB::m_encryptedSettingsForExtension
0x1cec  ldarg.1
0x1ced  ldloc.0
0x1cee  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>>::Add(var<u1>, !!T0)
0x1cf3  ldarg.1
0x1cf4  ldstr    aDelivery// "Delivery"
0x1cf9  call     class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IExtension [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::GetNewInstanceExtensionClass(string, string)
0x1cfe  stloc.1
0x1cff  ldloc.1
0x1d00  brtrue.s loc_1D1E
0x1d02  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0x1d07  ldc.i4.1
0x1d08  ldstr    aReencryptionFa_4// "Reencryption: Failed to load extension."...
0x1d0d  ldc.i4.1
0x1d0e  newarr   [mscorlib]System.Object
0x1d13  dup
0x1d14  ldc.i4.0
0x1d15  ldarg.1
0x1d16  stelem.ref
0x1d17  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1d1c  ldloc.0
0x1d1d  ret
0x1d1e  ldloc.1
0x1d1f  isinst   [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IDeliveryExtension
0x1d24  stloc.2
0x1d25  ldloc.2
0x1d26  brtrue.s loc_1D44
0x1d28  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CryptoTrace()
0x1d2d  ldc.i4.1
0x1d2e  ldstr    aReencryptionEx// "Reencryption: Extension is not a delive"...
0x1d33  ldc.i4.1
0x1d34  newarr   [mscorlib]System.Object
0x1d39  dup
0x1d3a  ldc.i4.0
0x1d3b  ldarg.1
0x1d3c  stelem.ref
0x1d3d  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1d42  ldloc.0
0x1d43  ret
0x1d44  ldloc.2
0x1d45  ldc.i4.1
0x1d46  ldnull
0x1d47  ldnull
0x1d48  call     class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Library.ProviderManager::InitDeliveryExtension(class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IDeliveryExtension extension, bool isPrivileged, class Microsoft.ReportingServices.Library.RSService rsService, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath itemPath)
0x1d4d  stloc.3
0x1d4e  ldloc.3
0x1d4f  brtrue.s loc_1D53
0x1d51  ldloc.0
0x1d52  ret
0x1d53  ldloc.3
0x1d54  stloc.s  4
0x1d56  ldc.i4.0
0x1d57  stloc.s  5
0x1d59  br.s     loc_1D7E
0x1d5b  ldloc.s  4
0x1d5d  ldloc.s  5
0x1d5f  ldelem.ref
0x1d60  stloc.s  6
0x1d62  ldloc.s  6
0x1d64  callvirt instance bool [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Encrypted()
0x1d69  brfalse.s loc_1D78
0x1d6b  ldloc.0
0x1d6c  ldloc.s  6
0x1d6e  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Name()
0x1d73  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1d78  ldloc.s  5
0x1d7a  ldc.i4.1
0x1d7b  add
0x1d7c  stloc.s  5
0x1d7e  ldloc.s  5
0x1d80  ldloc.s  4
0x1d82  ldlen
0x1d83  conv.i4
0x1d84  blt.s    loc_1D5B
0x1d86  ldloc.0
0x1d87  ret
```
