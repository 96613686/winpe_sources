# Microsoft.ReportingServices.Modeling.ModelGeneration.RuleSet::GetTypeMappings

- ea: `0x2ada0`
- end: `0x2aee1`
- name: `Microsoft.ReportingServices.Modeling.ModelGeneration.RuleSet::GetTypeMappings`
- size: `321`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2af10`

## callees

- `0x2aef0`

## string_xrefs

- `0x2adbb`: `CreateEntityRule`
- `0x2add0`: `CreateColumnEntityRule`
- `0x2ade5`: `CreateCountAttributeRule`
- `0x2adfa`: `CreateAttributeRule`
- `0x2ae0f`: `CreateVariationAttributeRule`
- `0x2ae24`: `CreateRoleRule`

## pseudocode

```c

```

## disassembly

```asm
0x2ada0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.Xml]System.Xml.XmlQualifiedName, class [mscorlib]System.Type>::.ctor()
0x2ada5  dup
0x2ada6  ldstr    aEvaluatedsvite// "EvaluateDsvItemRule"
0x2adab  ldtoken  Microsoft.ReportingServices.Modeling.ModelGeneration.EvaluateDsvItemRule
0x2adb0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2adb5  call     void Microsoft.ReportingServices.Modeling.ModelGeneration.RuleSet::AddTypeMapping(class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.Xml]System.Xml.XmlQualifiedName, class [mscorlib]System.Type> dict, string name, class [mscorlib]System.Type type)
0x2adba  dup
0x2adbb  ldstr    aCreateentityru// "CreateEntityRule"
0x2adc0  ldtoken  Microsoft.ReportingServices.Modeling.ModelGeneration.CreateEntityRule
0x2adc5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2adca  call     void Microsoft.ReportingServices.Modeling.ModelGeneration.RuleSet::AddTypeMapping(class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.Xml]System.Xml.XmlQualifiedName, class [mscorlib]System.Type> dict, string name, class [mscorlib]System.Type type)
0x2adcf  dup
0x2add0  ldstr    aCreatecolumnen// "CreateColumnEntityRule"
0x2add5  ldtoken  Microsoft.ReportingServices.Modeling.ModelGeneration.CreateColumnEntityRule
0x2adda  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2addf  call     void Microsoft.ReportingServices.Modeling.ModelGeneration.RuleSet::AddTypeMapping(class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.Xml]System.Xml.XmlQualifiedName, class [mscorlib]System.Type> dict, string name, class [mscorlib]System.Type type)
0x2ade4  dup
0x2ade5  ldstr    aCreatecountatt// "CreateCountAttributeRule"
0x2adea  ldtoken  Microsoft.ReportingServices.Modeling.ModelGeneration.CreateCountAttributeRule
0x2adef  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2adf4  call     void Microsoft.ReportingServices.Modeling.ModelGeneration.RuleSet::AddTypeMapping(class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.Xml]System.Xml.XmlQualifiedName, class [mscorlib]System.Type> dict, string name, class [mscorlib]System.Type type)
0x2adf9  dup
0x2adfa  ldstr    aCreateattribut// "CreateAttributeRule"
0x2adff  ldtoken  Microsoft.ReportingServices.Modeling.ModelGeneration.CreateAttributeRule
0x2ae04  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2ae09  call     void Microsoft.ReportingServices.Modeling.ModelGeneration.RuleSet::AddTypeMapping(class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.Xml]System.Xml.XmlQualifiedName, class [mscorlib]System.Type> dict, string name, class [mscorlib]System.Type type)
0x2ae0e  dup
0x2ae0f  ldstr    aCreatevariatio// "CreateVariationAttributeRule"
0x2ae14  ldtoken  Microsoft.ReportingServices.Modeling.ModelGeneration.CreateVariationAttributeRule
0x2ae19  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2ae1e  call     void Microsoft.ReportingServices.Modeling.ModelGeneration.RuleSet::AddTypeMapping(class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.Xml]System.Xml.XmlQualifiedName, class [mscorlib]System.Type> dict, string name, class [mscorlib]System.Type type)
0x2ae23  dup
0x2ae24  ldstr    aCreaterolerule// "CreateRoleRule"
0x2ae29  ldtoken  Microsoft.ReportingServices.Modeling.ModelGeneration.CreateRoleRule
0x2ae2e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2ae33  call     void Microsoft.ReportingServices.Modeling.ModelGeneration.RuleSet::AddTypeMapping(class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.Xml]System.Xml.XmlQualifiedName, class [mscorlib]System.Type> dict, string name, class [mscorlib]System.Type type)
0x2ae38  dup
0x2ae39  ldstr    aSetentityprope// "SetEntityPropertiesRule"
0x2ae3e  ldtoken  Microsoft.ReportingServices.Modeling.ModelGeneration.SetEntityPropertiesRule
0x2ae43  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2ae48  call     void Microsoft.ReportingServices.Modeling.ModelGeneration.RuleSet::AddTypeMapping(class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.Xml]System.Xml.XmlQualifiedName, class [mscorlib]System.Type> dict, string name, class [mscorlib]System.Type type)
0x2ae4d  dup
0x2ae4e  ldstr    aSetentityattri// "SetEntityAttributesRule"
0x2ae53  ldtoken  Microsoft.ReportingServices.Modeling.ModelGeneration.SetEntityAttributesRule
0x2ae58  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2ae5d  call     void Microsoft.ReportingServices.Modeling.ModelGeneration.RuleSet::AddTypeMapping(class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.Xml]System.Xml.XmlQualifiedName, class [mscorlib]System.Type> dict, string name, class [mscorlib]System.Type type)
0x2ae62  dup
0x2ae63  ldstr    aSetattributepr// "SetAttributePropertiesRule"
0x2ae68  ldtoken  Microsoft.ReportingServices.Modeling.ModelGeneration.SetAttributePropertiesRule
0x2ae6d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2ae72  call     void Microsoft.ReportingServices.Modeling.ModelGeneration.RuleSet::AddTypeMapping(class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.Xml]System.Xml.XmlQualifiedName, class [mscorlib]System.Type> dict, string name, class [mscorlib]System.Type type)
0x2ae77  dup
0x2ae78  ldstr    aFiltergroup// "FilterGroup"
0x2ae7d  ldtoken  Microsoft.ReportingServices.Modeling.ModelGeneration.FilterGroup
0x2ae82  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2ae87  call     void Microsoft.ReportingServices.Modeling.ModelGeneration.RuleSet::AddTypeMapping(class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.Xml]System.Xml.XmlQualifiedName, class [mscorlib]System.Type> dict, string name, class [mscorlib]System.Type type)
0x2ae8c  dup
0x2ae8d  ldstr    aPropertyfilter// "PropertyFilter"
0x2ae92  ldtoken  Microsoft.ReportingServices.Modeling.ModelGeneration.PropertyFilter
0x2ae97  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2ae9c  call     void Microsoft.ReportingServices.Modeling.ModelGeneration.RuleSet::AddTypeMapping(class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.Xml]System.Xml.XmlQualifiedName, class [mscorlib]System.Type> dict, string name, class [mscorlib]System.Type type)
0x2aea1  dup
0x2aea2  ldstr    aNamefilter// "NameFilter"
0x2aea7  ldtoken  Microsoft.ReportingServices.Modeling.ModelGeneration.NameFilter
0x2aeac  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2aeb1  call     void Microsoft.ReportingServices.Modeling.ModelGeneration.RuleSet::AddTypeMapping(class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.Xml]System.Xml.XmlQualifiedName, class [mscorlib]System.Type> dict, string name, class [mscorlib]System.Type type)
0x2aeb6  dup
0x2aeb7  ldstr    aRowcountfilter// "RowCountFilter"
0x2aebc  ldtoken  Microsoft.ReportingServices.Modeling.ModelGeneration.RowCountFilter
0x2aec1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2aec6  call     void Microsoft.ReportingServices.Modeling.ModelGeneration.RuleSet::AddTypeMapping(class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.Xml]System.Xml.XmlQualifiedName, class [mscorlib]System.Type> dict, string name, class [mscorlib]System.Type type)
0x2aecb  dup
0x2aecc  ldstr    aFieldcountfilt// "FieldCountFilter"
0x2aed1  ldtoken  Microsoft.ReportingServices.Modeling.ModelGeneration.FieldCountFilter
0x2aed6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2aedb  call     void Microsoft.ReportingServices.Modeling.ModelGeneration.RuleSet::AddTypeMapping(class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.Xml]System.Xml.XmlQualifiedName, class [mscorlib]System.Type> dict, string name, class [mscorlib]System.Type type)
0x2aee0  ret
```
