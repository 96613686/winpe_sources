# Microsoft.ReportingServices.Library.ProviderManager::InitDeliveryExtension

- ea: `0x157f0`
- end: `0x1587f`
- name: `Microsoft.ReportingServices.Library.ProviderManager::InitDeliveryExtension`
- size: `143`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1cc0`
- `0x3d10`
- `0x11f60`
- `0x1c690`
- `0x1c8a0`
- `0x53960`
- `0x54cf0`

## callees

- `0x15700`
- `0x157f0`

## string_xrefs

- `0x15823`: `Delivery extension '{0}' specified an uninitialized (null) setting.`
- `0x15857`: `Delivery extension '{0}' specified a valid values list for the field '{1}' marked as a password.`

## pseudocode

```c

```

## disassembly

```asm
0x157f0  ldarg.0
0x157f1  ldarg.1
0x157f2  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IDeliveryExtension::set_IsPrivilegedUser(bool)
0x157f7  ldarg.0
0x157f8  ldarg.0
0x157f9  ldarg.2
0x157fa  ldarg.3
0x157fb  call     class Microsoft.ReportingServices.Library.DeliveryReportServerInfo Microsoft.ReportingServices.Library.ProviderManager::GetExtensionServerSettings(class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IDeliveryExtension extension, class Microsoft.ReportingServices.Library.RSService rsService, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath itemPath)
0x15800  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IDeliveryExtension::set_ReportServerInformation(class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation)
0x15805  ldarg.0
0x15806  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IDeliveryExtension::get_ExtensionSettings()
0x1580b  stloc.0
0x1580c  ldloc.0
0x1580d  brtrue.s loc_15811
0x1580f  ldnull
0x15810  ret
0x15811  ldloc.0
0x15812  stloc.1
0x15813  ldc.i4.0
0x15814  stloc.2
0x15815  br.s     loc_15877
0x15817  ldloc.1
0x15818  ldloc.2
0x15819  ldelem.ref
0x1581a  stloc.3
0x1581b  ldloc.3
0x1581c  brtrue.s loc_15839
0x1581e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15823  ldstr    aDeliveryExtens_0// "Delivery extension '{0}' specified an u"...
0x15828  ldarg.0
0x15829  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IExtension::get_LocalizedName()
0x1582e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x15833  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(string)
0x15838  throw
0x15839  ldloc.3
0x1583a  callvirt instance bool [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_IsPassword()
0x1583f  brfalse.s loc_15873
0x15841  ldloc.3
0x15842  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ValidValue[] [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_ValidValues()
0x15847  brfalse.s loc_15873
0x15849  ldloc.3
0x1584a  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ValidValue[] [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_ValidValues()
0x1584f  ldlen
0x15850  brfalse.s loc_15873
0x15852  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15857  ldstr    aDeliveryExtens_1// "Delivery extension '{0}' specified a va"...
0x1585c  ldarg.0
0x1585d  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IExtension::get_LocalizedName()
0x15862  ldloc.3
0x15863  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Name()
0x15868  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x1586d  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(string)
0x15872  throw
0x15873  ldloc.2
0x15874  ldc.i4.1
0x15875  add
0x15876  stloc.2
0x15877  ldloc.2
0x15878  ldloc.1
0x15879  ldlen
0x1587a  conv.i4
0x1587b  blt.s    loc_15817
0x1587d  ldloc.0
0x1587e  ret
```
