# Microsoft.ReportingServices.Portal.Services.ODataExtensions.ExtensionSettingsExtensions::ToSoapClass

- ea: `0xe4c0`
- end: `0xe527`
- name: `Microsoft.ReportingServices.Portal.Services.ODataExtensions.ExtensionSettingsExtensions::ToSoapClass`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0xe4c0`

## string_xrefs

- `0xe4c3`: `extensionSettings`

## pseudocode

```c

```

## disassembly

```asm
0xe4c0  ldarg.0
0xe4c1  brtrue.s loc_E4CE
0xe4c3  ldstr    aExtensionsetti// "extensionSettings"
0xe4c8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xe4cd  throw
0xe4ce  newobj   instance void [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionSettings::.ctor()
0xe4d3  stloc.0
0xe4d4  ldloc.0
0xe4d5  ldarg.0
0xe4d6  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.ExtensionSettings::get_Extension()
0xe4db  callvirt instance void [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionSettings::set_Extension(string)
0xe4e0  ldloc.0
0xe4e1  ldarg.0
0xe4e2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue> [Microsoft.ReportingServices.Portal.Interfaces]Model.ExtensionSettings::get_ParameterValues()
0xe4e7  brtrue.s loc_E4F1
0xe4e9  ldc.i4.0
0xe4ea  newarr   [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ParameterValueOrFieldReference
0xe4ef  br.s     loc_E520
0xe4f1  ldarg.0
0xe4f2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue> [Microsoft.ReportingServices.Portal.Interfaces]Model.ExtensionSettings::get_ParameterValues()
0xe4f7  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue, class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ParameterValueOrFieldReference> <>c::<>9__0_0
0xe4fc  dup
0xe4fd  brtrue.s loc_E516
0xe4ff  pop
0xe500  ldsfld   class <>c <>c::<>9
0xe505  ldftn    instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ParameterValueOrFieldReference <>c::<ToSoapClass>b__0_0(class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue parameterValue)
0xe50b  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue, class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ParameterValueOrFieldReference>::.ctor(object, native int)
0xe510  dup
0xe511  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue, class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ParameterValueOrFieldReference> <>c::<>9__0_0
0xe516  call     T0x2B000069
0xe51b  call     T0x2B00006A
0xe520  callvirt instance void [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionSettings::set_ParameterValues(class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ParameterValueOrFieldReference[])
0xe525  ldloc.0
0xe526  ret
```
