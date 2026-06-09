# Microsoft.ReportingServices.Portal.Services.ODataExtensions.ExtensionExtension::ToWebApiModel

- ea: `0xed70`
- end: `0xee0b`
- name: `Microsoft.ReportingServices.Portal.Services.ODataExtensions.ExtensionExtension::ToWebApiModel`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0xed60`
- `0xed70`

## string_xrefs

- `0xed73`: `soapExtension`

## pseudocode

```c

```

## disassembly

```asm
0xed70  ldarg.0
0xed71  brtrue.s loc_ED7E
0xed73  ldstr    aSoapextension// "soapExtension"
0xed78  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xed7d  throw
0xed7e  ldc.i4.4
0xed7f  stloc.0
0xed80  ldarg.0
0xed81  callvirt instance string [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Extension::get_ExtensionTypeName()
0xed86  stloc.2
0xed87  ldloc.2
0xed88  ldstr    aData// "Data"
0xed8d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xed92  brtrue.s loc_EDB0
0xed94  ldloc.2
0xed95  ldstr    aDelivery// "Delivery"
0xed9a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xed9f  brtrue.s loc_EDB4
0xeda1  ldloc.2
0xeda2  ldstr    aRender// "Render"
0xeda7  call     bool [mscorlib]System.String::op_Equality(string, string)
0xedac  brtrue.s loc_EDB8
0xedae  br.s     loc_EDBA
0xedb0  ldc.i4.3
0xedb1  stloc.0
0xedb2  br.s     loc_EDBA
0xedb4  ldc.i4.0
0xedb5  stloc.0
0xedb6  br.s     loc_EDBA
0xedb8  ldc.i4.2
0xedb9  stloc.0
0xedba  ldnull
0xedbb  stloc.1
0xedbc  ldloc.0
0xedbd  brtrue.s loc_EDD8
0xedbf  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DeliveryExtension::.ctor()
0xedc4  dup
0xedc5  ldarg.0
0xedc6  callvirt instance string [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Extension::get_Name()
0xedcb  call     bool Microsoft.ReportingServices.Portal.Services.ODataExtensions.ExtensionExtension::IsImmutableKnownDeliveryExtension(string extensionName)
0xedd0  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DeliveryExtension::set_IsImmutable(bool)
0xedd5  stloc.1
0xedd6  br.s     loc_EDDE
0xedd8  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Extension::.ctor()
0xeddd  stloc.1
0xedde  ldloc.1
0xeddf  ldloc.0
0xede0  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Extension::set_ExtensionType(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ExtensionType)
0xede5  ldloc.1
0xede6  ldarg.0
0xede7  callvirt instance string [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Extension::get_Name()
0xedec  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Extension::set_Name(string)
0xedf1  ldloc.1
0xedf2  ldarg.0
0xedf3  callvirt instance string [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Extension::get_LocalizedName()
0xedf8  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Extension::set_LocalizedName(string)
0xedfd  ldloc.1
0xedfe  ldarg.0
0xedff  callvirt instance bool [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Extension::get_Visible()
0xee04  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Extension::set_Visible(bool)
0xee09  ldloc.1
0xee0a  ret
```
