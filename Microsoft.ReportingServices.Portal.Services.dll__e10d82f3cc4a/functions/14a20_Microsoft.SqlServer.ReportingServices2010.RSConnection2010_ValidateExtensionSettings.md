# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::ValidateExtensionSettings

- ea: `0x14a20`
- end: `0x14a5f`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::ValidateExtensionSettings`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x214d0`

## callees

- `0x23060`

## string_xrefs

- `0x14a43`: `ValidateExtensionSettings`

## pseudocode

```c

```

## disassembly

```asm
0x14a20  newobj   instance void <>c__DisplayClass67_0::.ctor()
0x14a25  stloc.0
0x14a26  ldloc.0
0x14a27  ldarg.0
0x14a28  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass67_0::<>4__this
0x14a2d  ldloc.0
0x14a2e  ldarg.1
0x14a2f  stfld    string <>c__DisplayClass67_0::extension
0x14a34  ldloc.0
0x14a35  ldarg.2
0x14a36  stfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ParameterValueOrFieldReference[] <>c__DisplayClass67_0::parameterValues
0x14a3b  ldloc.0
0x14a3c  ldarg.3
0x14a3d  stfld    string <>c__DisplayClass67_0::site
0x14a42  ldarg.0
0x14a43  ldstr    aValidateextens// "ValidateExtensionSettings"
0x14a48  ldloc.0
0x14a49  ldftn    instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionParameter[] <>c__DisplayClass67_0::<ValidateExtensionSettings>b__0()
0x14a4f  newobj   instance void class SoapMethod<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionParameter[]>::.ctor(object, native int)
0x14a54  newobj   instance void class SoapMethodWrapper`1<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionParameter[]>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x14a59  callvirt instance var<u1> class SoapMethodWrapper`1<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionParameter[]>::ExecuteMethod()
0x14a5e  ret
```
