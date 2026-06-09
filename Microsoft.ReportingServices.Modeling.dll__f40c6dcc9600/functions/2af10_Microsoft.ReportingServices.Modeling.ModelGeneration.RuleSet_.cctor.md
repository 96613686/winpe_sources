# Microsoft.ReportingServices.Modeling.ModelGeneration.RuleSet::.cctor

- ea: `0x2af10`
- end: `0x2af75`
- name: `Microsoft.ReportingServices.Modeling.ModelGeneration.RuleSet::.cctor`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x2ada0`

## string_xrefs

- `0x2af47`: `.SRRuleTokens`

## pseudocode

```c

```

## disassembly

```asm
0x2af10  ldstr    aResnameW// "\\(\\$(?<resName>\\w+)\\)"
0x2af15  ldc.i4   0x208
0x2af1a  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x2af1f  stsfld   class [System]System.Text.RegularExpressions.Regex Microsoft.ReportingServices.Modeling.ModelGeneration.RuleSet::m_displayCultureTokenRegex
0x2af24  ldstr    aResnameW_0// "\\{\\$(?<resName>\\w+)\\}"
0x2af29  ldc.i4   0x208
0x2af2e  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x2af33  stsfld   class [System]System.Text.RegularExpressions.Regex Microsoft.ReportingServices.Modeling.ModelGeneration.RuleSet::m_modelCultureTokenRegex
0x2af38  ldtoken  Microsoft.ReportingServices.Modeling.ModelGeneration.RuleSet
0x2af3d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2af42  callvirt instance string [mscorlib]System.Type::get_Namespace()
0x2af47  ldstr    aSrruletokens// ".SRRuleTokens"
0x2af4c  call     string [mscorlib]System.String::Concat(string, string)
0x2af51  ldtoken  Microsoft.ReportingServices.Modeling.ModelGeneration.RuleSet
0x2af56  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2af5b  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x2af60  newobj   instance void [mscorlib]System.Resources.ResourceManager::.ctor(string, class [mscorlib]System.Reflection.Assembly)
0x2af65  stsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.ReportingServices.Modeling.ModelGeneration.RuleSet::m_ruleTokenRes
0x2af6a  call     class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.Xml]System.Xml.XmlQualifiedName, class [mscorlib]System.Type> Microsoft.ReportingServices.Modeling.ModelGeneration.RuleSet::GetTypeMappings()
0x2af6f  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.Xml]System.Xml.XmlQualifiedName, class [mscorlib]System.Type> Microsoft.ReportingServices.Modeling.ModelGeneration.RuleSet::m_typeMappings
0x2af74  ret
```
