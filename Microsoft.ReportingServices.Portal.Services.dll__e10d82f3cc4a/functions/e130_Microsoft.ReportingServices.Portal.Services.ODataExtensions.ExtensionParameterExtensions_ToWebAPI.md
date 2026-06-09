# Microsoft.ReportingServices.Portal.Services.ODataExtensions.ExtensionParameterExtensions::ToWebAPI

- ea: `0xe130`
- end: `0xe1fa`
- name: `Microsoft.ReportingServices.Portal.Services.ODataExtensions.ExtensionParameterExtensions::ToWebAPI`
- size: `202`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0xe130`

## string_xrefs

- `0xe133`: `extensionParameter`

## pseudocode

```c

```

## disassembly

```asm
0xe130  ldarg.0
0xe131  brtrue.s loc_E13E
0xe133  ldstr    aExtensionparam// "extensionParameter"
0xe138  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xe13d  throw
0xe13e  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ExtensionParameter::.ctor()
0xe143  stloc.0
0xe144  ldloc.0
0xe145  ldarg.0
0xe146  callvirt instance string [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionParameter::get_Name()
0xe14b  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ExtensionParameter::set_Name(string)
0xe150  ldloc.0
0xe151  ldarg.0
0xe152  callvirt instance string [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionParameter::get_DisplayName()
0xe157  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ExtensionParameter::set_DisplayName(string)
0xe15c  ldloc.0
0xe15d  ldarg.0
0xe15e  callvirt instance bool [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionParameter::get_Encrypted()
0xe163  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ExtensionParameter::set_Encrypted(bool)
0xe168  ldloc.0
0xe169  ldarg.0
0xe16a  callvirt instance bool [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionParameter::get_IsPassword()
0xe16f  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ExtensionParameter::set_IsPassword(bool)
0xe174  ldloc.0
0xe175  ldarg.0
0xe176  callvirt instance bool [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionParameter::get_ReadOnly()
0xe17b  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ExtensionParameter::set_ReadOnly(bool)
0xe180  ldloc.0
0xe181  ldarg.0
0xe182  callvirt instance bool [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionParameter::get_Required()
0xe187  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ExtensionParameter::set_Required(bool)
0xe18c  ldloc.0
0xe18d  ldarg.0
0xe18e  callvirt instance string [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionParameter::get_Value()
0xe193  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ExtensionParameter::set_Value(string)
0xe198  ldloc.0
0xe199  ldarg.0
0xe19a  callvirt instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ValidValue[] [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionParameter::get_ValidValues()
0xe19f  brtrue.s loc_E1A9
0xe1a1  ldc.i4.0
0xe1a2  newarr   [Microsoft.ReportingServices.Portal.Interfaces]Model.ValidValue
0xe1a7  br.s     loc_E1D8
0xe1a9  ldarg.0
0xe1aa  callvirt instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ValidValue[] [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionParameter::get_ValidValues()
0xe1af  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ValidValue, class [Microsoft.ReportingServices.Portal.Interfaces]Model.ValidValue> <>c::<>9__0_0
0xe1b4  dup
0xe1b5  brtrue.s loc_E1CE
0xe1b7  pop
0xe1b8  ldsfld   class <>c <>c::<>9
0xe1bd  ldftn    instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ValidValue <>c::<ToWebAPI>b__0_0(class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ValidValue validValue)
0xe1c3  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ValidValue, class [Microsoft.ReportingServices.Portal.Interfaces]Model.ValidValue>::.ctor(object, native int)
0xe1c8  dup
0xe1c9  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ValidValue, class [Microsoft.ReportingServices.Portal.Interfaces]Model.ValidValue> <>c::<>9__0_0
0xe1ce  call     T0x2B0000C4
0xe1d3  call     T0x2B0000C5
0xe1d8  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ExtensionParameter::set_ValidValues(class [Microsoft.ReportingServices.Portal.Interfaces]Model.ValidValue[])
0xe1dd  ldloc.0
0xe1de  ldarg.0
0xe1df  callvirt instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ValidValue[] [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionParameter::get_ValidValues()
0xe1e4  ldnull
0xe1e5  ceq
0xe1e7  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ExtensionParameter::set_ValidValuesIsNull(bool)
0xe1ec  ldloc.0
0xe1ed  ldarg.0
0xe1ee  callvirt instance string [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionParameter::get_Error()
0xe1f3  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ExtensionParameter::set_Error(string)
0xe1f8  ldloc.0
0xe1f9  ret
```
