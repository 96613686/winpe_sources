# Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule::LoadXmlElement

- ea: `0x29f80`
- end: `0x29fb6`
- name: `Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule::LoadXmlElement`
- size: `54`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x26080`
- `0x26f30`
- `0x27190`
- `0x27560`
- `0x2be40`

## callees

- `0xa760`
- `0xa7b0`
- `0x29f80`
- `0x2a5a0`
- `0x2a980`

## string_xrefs

- `0x29f8e`: `renamer`

## pseudocode

```c

```

## disassembly

```asm
0x29f80  ldarg.1
0x29f81  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_IsDefaultNamespace()
0x29f86  brfalse.s loc_29FAD
0x29f88  ldarg.1
0x29f89  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_LocalName()
0x29f8e  ldstr    aRenamer// "renamer"
0x29f93  call     bool [mscorlib]System.String::op_Equality(string, string)
0x29f98  brfalse.s loc_29FAD
0x29f9a  ldarg.0
0x29f9b  ldfld    class Microsoft.ReportingServices.Modeling.ModelGeneration.RenamerCollection Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule::m_renamers
0x29fa0  ldarg.1
0x29fa1  call     class Microsoft.ReportingServices.Modeling.ModelGeneration.Renamer Microsoft.ReportingServices.Modeling.ModelGeneration.Renamer::FromReader(class Microsoft.ReportingServices.Modeling.ModelingXmlReader xr)
0x29fa6  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.ModelGeneration.Renamer>::Add(var<u1>)
0x29fab  ldc.i4.1
0x29fac  ret
0x29fad  ldarg.0
0x29fae  ldarg.1
0x29faf  ldarg.2
0x29fb0  call     instance bool Microsoft.ReportingServices.Modeling.ModelGeneration.Rule::LoadXmlElement(class Microsoft.ReportingServices.Modeling.ModelingXmlReader xr, class Microsoft.ReportingServices.Modeling.ModelGeneration.IXmlObjectFactory objectFactory)
0x29fb5  ret
```
