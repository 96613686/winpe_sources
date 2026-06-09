# Microsoft.ReportingServices.Modeling.SemanticModel::.ctor_0

- ea: `0x169c0`
- end: `0x16a3d`
- name: `Microsoft.ReportingServices.Modeling.SemanticModel::.ctor_0`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x174d0`

## callees

- `0x7f30`
- `0x97d0`
- `0x9cf0`
- `0x13920`
- `0x169c0`
- `0x16aa0`
- `0x16ad0`
- `0x16b80`
- `0x34690`

## string_xrefs

- `0x169f1`: `baseModel is not compiled`

## pseudocode

```c

```

## disassembly

```asm
0x169c0  ldarg.0
0x169c1  newobj   instance void Microsoft.ReportingServices.Modeling.XmlNamespacePrefixCollection::.ctor()
0x169c6  stfld    class Microsoft.ReportingServices.Modeling.XmlNamespacePrefixCollection Microsoft.ReportingServices.Modeling.SemanticModel::m_namespacePrefixes
0x169cb  ldarg.0
0x169cc  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.Modeling.QName, class Microsoft.ReportingServices.Modeling.ModelItem>::.ctor()
0x169d1  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.Modeling.QName, class Microsoft.ReportingServices.Modeling.ModelItem> Microsoft.ReportingServices.Modeling.SemanticModel::m_allItems
0x169d6  ldarg.0
0x169d7  newobj   instance void LookupItemStack::.ctor()
0x169dc  stfld    class LookupItemStack Microsoft.ReportingServices.Modeling.SemanticModel::m_lookupItemStack
0x169e1  ldarg.0
0x169e2  ldarg.1
0x169e3  ldc.i4.0
0x169e4  call     instance void Microsoft.ReportingServices.Modeling.ModelItem::.ctor(class Microsoft.ReportingServices.Modeling.ModelItem baseItem, bool markAsHidden)
0x169e9  ldarg.1
0x169ea  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelingObject::get_IsCompiled()
0x169ef  brtrue.s loc_169FC
0x169f1  ldstr    aBasemodelIsNot// "baseModel is not compiled"
0x169f6  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x169fb  throw
0x169fc  ldarg.2
0x169fd  brtrue.s loc_16A0A
0x169ff  ldstr    aIncludeitemIsN// "includeItem is null."
0x16a04  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x16a09  throw
0x16a0a  ldarg.0
0x16a0b  ldarg.2
0x16a0c  stfld    class [mscorlib]System.Predicate`1<class Microsoft.ReportingServices.Modeling.ModelItem> Microsoft.ReportingServices.Modeling.SemanticModel::m_includeItem
0x16a11  ldarg.0
0x16a12  ldarg.3
0x16a13  stfld    class [mscorlib]System.Predicate`1<class Microsoft.ReportingServices.Modeling.ModelItem> Microsoft.ReportingServices.Modeling.SemanticModel::m_itemInPerspective
0x16a18  ldarg.0
0x16a19  ldarg.1
0x16a1a  callvirt instance string Microsoft.ReportingServices.Modeling.SemanticModel::get_Version()
0x16a1f  stfld    string Microsoft.ReportingServices.Modeling.SemanticModel::m_version
0x16a24  ldarg.0
0x16a25  ldarg.1
0x16a26  callvirt instance class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.Modeling.SemanticModel::get_Culture()
0x16a2b  stfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.Modeling.SemanticModel::m_culture
0x16a30  ldarg.0
0x16a31  ldarg.1
0x16a32  callvirt instance class Microsoft.ReportingServices.Modeling.XmlNamespacePrefixCollection Microsoft.ReportingServices.Modeling.SemanticModel::get_NamespacePrefixes()
0x16a37  stfld    class Microsoft.ReportingServices.Modeling.XmlNamespacePrefixCollection Microsoft.ReportingServices.Modeling.SemanticModel::m_namespacePrefixes
0x16a3c  ret
```
