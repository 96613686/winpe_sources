# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::GetExtensionSettings

- ea: `0x149e0`
- end: `0x14a11`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::GetExtensionSettings`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x21490`

## callees

- `0x23020`

## string_xrefs

- `0x149f5`: `GetExtensionSettings`

## pseudocode

```c

```

## disassembly

```asm
0x149e0  newobj   instance void <>c__DisplayClass66_0::.ctor()
0x149e5  stloc.0
0x149e6  ldloc.0
0x149e7  ldarg.0
0x149e8  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass66_0::<>4__this
0x149ed  ldloc.0
0x149ee  ldarg.1
0x149ef  stfld    string <>c__DisplayClass66_0::extension
0x149f4  ldarg.0
0x149f5  ldstr    aGetextensionse// "GetExtensionSettings"
0x149fa  ldloc.0
0x149fb  ldftn    instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionParameter[] <>c__DisplayClass66_0::<GetExtensionSettings>b__0()
0x14a01  newobj   instance void class SoapMethod<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionParameter[]>::.ctor(object, native int)
0x14a06  newobj   instance void class SoapMethodWrapper`1<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionParameter[]>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x14a0b  callvirt instance var<u1> class SoapMethodWrapper`1<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionParameter[]>::ExecuteMethod()
0x14a10  ret
```
