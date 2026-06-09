# Microsoft.ReportingServices.Modeling.DrillthroughContext::Microsoft.ReportingServices.Modeling.IXmlLoadable.LoadXmlElement

- ea: `0x18040`
- end: `0x180cd`
- name: `Microsoft.ReportingServices.Modeling.DrillthroughContext::Microsoft.ReportingServices.Modeling.IXmlLoadable.LoadXmlElement`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xa760`
- `0xa7b0`
- `0xab20`
- `0x18040`
- `0x1ddf0`
- `0x1e180`
- `0x23440`
- `0x34e50`
- `0x34ef0`

## string_xrefs

- `0x1806d`: `SelectedPath`

## pseudocode

```c

```

## disassembly

```asm
0x18040  ldarg.1
0x18041  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_IsDefaultNamespace()
0x18046  brfalse  loc_180CB
0x1804b  ldarg.1
0x1804c  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_LocalName()
0x18051  stloc.0
0x18052  ldloc.0
0x18053  ldstr    aSemanticquery// "SemanticQuery"
0x18058  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1805d  brtrue.s loc_18088
0x1805f  ldloc.0
0x18060  ldstr    aSelecteditems// "SelectedItems"
0x18065  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1806a  brtrue.s loc_18096
0x1806c  ldloc.0
0x1806d  ldstr    aSelectedpath// "SelectedPath"
0x18072  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18077  brtrue.s loc_180A4
0x18079  ldloc.0
0x1807a  ldstr    aGroupingvalues// "GroupingValues"
0x1807f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18084  brtrue.s loc_180BD
0x18086  br.s     loc_180CB
0x18088  ldarg.0
0x18089  ldfld    class Microsoft.ReportingServices.Modeling.SemanticQuery Microsoft.ReportingServices.Modeling.DrillthroughContext::m_sourceQuery
0x1808e  ldarg.1
0x1808f  callvirt instance void Microsoft.ReportingServices.Modeling.SemanticQuery::Load(class Microsoft.ReportingServices.Modeling.ModelingXmlReader xr)
0x18094  ldc.i4.1
0x18095  ret
0x18096  ldarg.1
0x18097  ldarg.0
0x18098  newobj   instance void SelectedItemsLoader::.ctor(class Microsoft.ReportingServices.Modeling.DrillthroughContext item)
0x1809d  callvirt instance void Microsoft.ReportingServices.Modeling.ModelingXmlReader::LoadObject(class Microsoft.ReportingServices.Modeling.IXmlLoadable obj)
0x180a2  ldc.i4.1
0x180a3  ret
0x180a4  ldarg.0
0x180a5  newobj   instance void Microsoft.ReportingServices.Modeling.ExpressionPath::.ctor()
0x180aa  stfld    class Microsoft.ReportingServices.Modeling.ExpressionPath Microsoft.ReportingServices.Modeling.DrillthroughContext::m_selectedPath
0x180af  ldarg.0
0x180b0  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionPath Microsoft.ReportingServices.Modeling.DrillthroughContext::m_selectedPath
0x180b5  ldarg.1
0x180b6  callvirt instance void Microsoft.ReportingServices.Modeling.ExpressionPath::Load(class Microsoft.ReportingServices.Modeling.ModelingXmlReader xr)
0x180bb  ldc.i4.1
0x180bc  ret
0x180bd  ldarg.1
0x180be  ldarg.0
0x180bf  newobj   instance void GroupingValuesLoader::.ctor(class Microsoft.ReportingServices.Modeling.DrillthroughContext item)
0x180c4  callvirt instance void Microsoft.ReportingServices.Modeling.ModelingXmlReader::LoadObject(class Microsoft.ReportingServices.Modeling.IXmlLoadable obj)
0x180c9  ldc.i4.1
0x180ca  ret
0x180cb  ldc.i4.0
0x180cc  ret
```
