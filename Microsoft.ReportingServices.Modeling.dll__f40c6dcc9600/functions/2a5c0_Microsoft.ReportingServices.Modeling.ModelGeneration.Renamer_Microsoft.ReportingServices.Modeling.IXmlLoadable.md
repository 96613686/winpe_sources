# Microsoft.ReportingServices.Modeling.ModelGeneration.Renamer::Microsoft.ReportingServices.Modeling.IXmlLoadable.LoadXmlAttribute

- ea: `0x2a5c0`
- end: `0x2a609`
- name: `Microsoft.ReportingServices.Modeling.ModelGeneration.Renamer::Microsoft.ReportingServices.Modeling.IXmlLoadable.LoadXmlAttribute`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xa760`
- `0xa7b0`
- `0xaa40`
- `0x2a4f0`
- `0x2a540`
- `0x2a5c0`

## string_xrefs

- `0x2a5dd`: `replace`

## pseudocode

```c

```

## disassembly

```asm
0x2a5c0  ldarg.1
0x2a5c1  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_IsDefaultNamespace()
0x2a5c6  brfalse.s loc_2A607
0x2a5c8  ldarg.1
0x2a5c9  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_LocalName()
0x2a5ce  stloc.0
0x2a5cf  ldloc.0
0x2a5d0  ldstr    aMatch// "match"
0x2a5d5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2a5da  brtrue.s loc_2A5EB
0x2a5dc  ldloc.0
0x2a5dd  ldstr    aReplace// "replace"
0x2a5e2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2a5e7  brtrue.s loc_2A5F9
0x2a5e9  br.s     loc_2A607
0x2a5eb  ldarg.0
0x2a5ec  ldarg.1
0x2a5ed  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadValueAsString()
0x2a5f2  call     instance void Microsoft.ReportingServices.Modeling.ModelGeneration.Renamer::set_MatchPattern(string value)
0x2a5f7  ldc.i4.1
0x2a5f8  ret
0x2a5f9  ldarg.0
0x2a5fa  ldarg.1
0x2a5fb  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadValueAsString()
0x2a600  call     instance void Microsoft.ReportingServices.Modeling.ModelGeneration.Renamer::set_ReplacePattern(string value)
0x2a605  ldc.i4.1
0x2a606  ret
0x2a607  ldc.i4.0
0x2a608  ret
```
