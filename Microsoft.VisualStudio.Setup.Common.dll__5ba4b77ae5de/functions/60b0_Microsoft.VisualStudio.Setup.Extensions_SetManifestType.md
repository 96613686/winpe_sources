# Microsoft.VisualStudio.Setup.Extensions::SetManifestType

- ea: `0x60b0`
- end: `0x6128`
- name: `Microsoft.VisualStudio.Setup.Extensions::SetManifestType`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x2af0`
- `0x2b60`
- `0x60b0`
- `0x6d30`
- `0x6d40`
- `0xc1a0`

## string_xrefs

- `0x60b1`: `manifest`
- `0x6104`: `manifestType`

## pseudocode

```c

```

## disassembly

```asm
0x60b0  ldarg.0
0x60b1  ldstr    aManifest// "manifest"
0x60b6  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x60bb  ldarg.0
0x60bc  callvirt instance class Microsoft.VisualStudio.Setup.CatalogInfo Microsoft.VisualStudio.Setup.IManifest::get_Info()
0x60c1  brtrue.s loc_60CE
0x60c3  ldarg.0
0x60c4  newobj   instance void Microsoft.VisualStudio.Setup.CatalogInfo::.ctor()
0x60c9  callvirt instance void Microsoft.VisualStudio.Setup.IManifest::set_Info(class Microsoft.VisualStudio.Setup.CatalogInfo value)
0x60ce  ldtoken  mvar<u1>
0x60d3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x60d8  ldarg.1
0x60d9  box      mvar<u1>
0x60de  call     bool [mscorlib]System.Enum::IsDefined(class [mscorlib]System.Type, object)
0x60e3  brtrue.s loc_610F
0x60e5  ldstr    aTheValue0IsNot// "The value '{0}' is not defined for {1}"
0x60ea  ldarg.1
0x60eb  box      mvar<u1>
0x60f0  ldtoken  mvar<u1>
0x60f5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x60fa  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x60ff  call     string [mscorlib]System.String::Format(string, object, object)
0x6104  ldstr    aManifesttype_0// "manifestType"
0x6109  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x610e  throw
0x610f  ldarg.0
0x6110  callvirt instance class Microsoft.VisualStudio.Setup.CatalogInfo Microsoft.VisualStudio.Setup.IManifest::get_Info()
0x6115  ldarga.s 1
0x6117  constrained. mvar<u1>
0x611d  callvirt instance string [mscorlib]System.Object::ToString()
0x6122  callvirt instance void Microsoft.VisualStudio.Setup.CatalogInfo::set_ManifestType(string value)
0x6127  ret
```
