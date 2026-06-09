# Microsoft.ReportingServices.Modeling.ModelGeneration.CreateAttributeRule::Microsoft.ReportingServices.Modeling.ModelGeneration.IColumnProcessingRule.Process

- ea: `0x26110`
- end: `0x2621a`
- name: `Microsoft.ReportingServices.Modeling.ModelGeneration.CreateAttributeRule::Microsoft.ReportingServices.Modeling.ModelGeneration.IColumnProcessingRule.Process`
- size: `266`
- prototype: ``
- caller_count: `0`
- callee_count: `33`
- tags: `service_task, broker_com_uri`

## callees

- `0xc3d0`
- `0xd990`
- `0xe390`
- `0xe430`
- `0xe510`
- `0xec70`
- `0xf020`
- `0xf040`
- `0xf080`
- `0xf0e0`
- `0xf260`
- `0xf410`
- `0x10800`
- `0x13a70`
- `0x26040`
- `0x26060`
- `0x26110`
- `0x26220`
- `0x278f0`
- `0x27920`
- `0x27980`
- `0x27990`
- `0x279a0`
- `0x27a70`
- `0x29710`
- `0x29720`
- `0x29760`
- `0x29820`
- `0x29840`
- `0x29ab0`
- `0x2a8e0`
- `0x2d490`
- `0x2d620`

## pseudocode

```c

```

## disassembly

```asm
0x26110  ldarg.0
0x26111  call     instance class Microsoft.ReportingServices.Modeling.ModelGeneration.ExistingBindingContext Microsoft.ReportingServices.Modeling.ModelGeneration.Rule::get_BindingContext()
0x26116  ldarg.1
0x26117  callvirt instance class Microsoft.ReportingServices.Modeling.DsvTable Microsoft.ReportingServices.Modeling.DsvColumn::get_Table()
0x2611c  callvirt instance class Microsoft.ReportingServices.Modeling.ModelGeneration.ExistingTableBindingInfo Microsoft.ReportingServices.Modeling.ModelGeneration.ExistingBindingContext::GetBindingInfo(class Microsoft.ReportingServices.Modeling.DsvTable dsvTable)
0x26121  callvirt instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelGeneration.ExistingTableBindingInfo::get_Entity()
0x26126  stloc.0
0x26127  ldloc.0
0x26128  brtrue.s loc_2613F
0x2612a  ldarg.0
0x2612b  ldc.i4.1
0x2612c  newarr   [mscorlib]System.String
0x26131  dup
0x26132  ldc.i4.0
0x26133  call     string Microsoft.ReportingServices.Modeling.ModelGeneration.SR::get_Rules_ParentEntityDoesNotExist()
0x26138  stelem.ref
0x26139  call     instance class Microsoft.ReportingServices.Modeling.ModelGeneration.RuleProcessResult Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule::ProcessSkipped(string[] messages)
0x2613e  ret
0x2613f  ldarg.2
0x26140  callvirt instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelGeneration.ExistingColumnBindingInfo::get_Entity()
0x26145  brfalse.s loc_26154
0x26147  ldarg.0
0x26148  ldarg.2
0x26149  callvirt instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelGeneration.ExistingColumnBindingInfo::get_Entity()
0x2614e  call     instance class Microsoft.ReportingServices.Modeling.ModelGeneration.RuleProcessResult Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule::ProcessFoundExistingModelItem(class Microsoft.ReportingServices.Modeling.ModelItem item)
0x26153  ret
0x26154  ldarg.2
0x26155  callvirt instance class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.ModelGeneration.ExistingColumnBindingInfo::get_Attribute()
0x2615a  brfalse.s loc_26169
0x2615c  ldarg.0
0x2615d  ldarg.2
0x2615e  callvirt instance class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.ModelGeneration.ExistingColumnBindingInfo::get_Attribute()
0x26163  call     instance class Microsoft.ReportingServices.Modeling.ModelGeneration.RuleProcessResult Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule::ProcessFoundExistingModelItem(class Microsoft.ReportingServices.Modeling.ModelItem item)
0x26168  ret
0x26169  ldarg.1
0x2616a  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.DataType> Microsoft.ReportingServices.Modeling.DsvColumn::get_ModelingDataType()
0x2616f  stloc.2
0x26170  ldloca.s 2
0x26172  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.DataType>::get_HasValue()
0x26177  brtrue.s loc_26194
0x26179  ldarg.0
0x2617a  ldc.i4.1
0x2617b  newarr   [mscorlib]System.String
0x26180  dup
0x26181  ldc.i4.0
0x26182  ldarg.1
0x26183  callvirt instance class [mscorlib]System.Type Microsoft.ReportingServices.Modeling.DsvColumn::get_DataType()
0x26188  call     string Microsoft.ReportingServices.Modeling.ModelGeneration.SR::Rules_UnsupportedDataType(class [mscorlib]System.Type type)
0x2618d  stelem.ref
0x2618e  call     instance class Microsoft.ReportingServices.Modeling.ModelGeneration.RuleProcessResult Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule::ProcessSkipped(string[] messages)
0x26193  ret
0x26194  newobj   instance void Microsoft.ReportingServices.Modeling.ModelAttribute::.ctor()
0x26199  stloc.1
0x2619a  ldloc.0
0x2619b  callvirt instance class Microsoft.ReportingServices.Modeling.ModelFieldFolderItemCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_Fields()
0x261a0  ldloc.1
0x261a1  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.ModelFieldFolderItem>::Add(var<u1>)
0x261a6  ldloc.1
0x261a7  ldarg.0
0x261a8  ldarg.1
0x261a9  call     instance string Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule::CreateModelItemName(class Microsoft.ReportingServices.Modeling.DsvItem dsvItem)
0x261ae  callvirt instance void Microsoft.ReportingServices.Modeling.ModelItem::set_Name(string value)
0x261b3  ldloc.1
0x261b4  ldarg.1
0x261b5  callvirt instance string Microsoft.ReportingServices.Modeling.DsvItem::get_Name()
0x261ba  newobj   instance void Microsoft.ReportingServices.Modeling.ColumnBinding::.ctor(string name)
0x261bf  callvirt instance void Microsoft.ReportingServices.Modeling.ModelAttribute::set_Binding(class Microsoft.ReportingServices.Modeling.ColumnBinding value)
0x261c4  ldloc.1
0x261c5  callvirt instance void Microsoft.ReportingServices.Modeling.ModelAttribute::UpdateFromBinding()
0x261ca  ldarg.0
0x261cb  ldloc.1
0x261cc  call     instance void Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule::MoveFieldSortedByOrdinal(class Microsoft.ReportingServices.Modeling.ModelField field)
0x261d1  ldarg.0
0x261d2  ldloc.1
0x261d3  ldarg.0
0x261d4  call     instance class [System.Xml]System.Xml.XPath.IXPathNavigable Microsoft.ReportingServices.Modeling.ModelGeneration.AttributeRuleBase::get_AttributeFragment()
0x261d9  ldarg.0
0x261da  call     instance class [System.Xml]System.Xml.XPath.IXPathNavigable Microsoft.ReportingServices.Modeling.ModelGeneration.AttributeRuleBase::get_FolderFragment()
0x261df  call     instance void Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule::FinalizeModelItem(class Microsoft.ReportingServices.Modeling.ModelItem item, class [System.Xml]System.Xml.XPath.IXPathNavigable fragment, class [System.Xml]System.Xml.XPath.IXPathNavigable folderFragment)
0x261e4  ldloc.1
0x261e5  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelAttribute::get_IsWidthSet()
0x261ea  brtrue.s loc_26204
0x261ec  ldloc.1
0x261ed  ldarg.1
0x261ee  ldloc.1
0x261ef  callvirt instance string Microsoft.ReportingServices.Modeling.ModelAttribute::get_Format()
0x261f4  ldloc.1
0x261f5  callvirt instance class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.Modeling.ModelAttribute::get_DataCulture()
0x261fa  call     int32 Microsoft.ReportingServices.Modeling.ModelGeneration.CreateAttributeRule::CalculateWidth(class Microsoft.ReportingServices.Modeling.DsvColumn column, string format, class [mscorlib]System.Globalization.CultureInfo culture)
0x261ff  callvirt instance void Microsoft.ReportingServices.Modeling.ModelAttribute::set_Width(int32 value)
0x26204  ldarg.2
0x26205  ldloc.1
0x26206  callvirt instance void Microsoft.ReportingServices.Modeling.ModelGeneration.ExistingColumnBindingInfo::set_Attribute(class Microsoft.ReportingServices.Modeling.ModelAttribute value)
0x2620b  ldarg.2
0x2620c  ldc.i4.1
0x2620d  callvirt instance void Microsoft.ReportingServices.Modeling.ModelGeneration.ExistingBindingInfo::set_EvaluateDependentRules(bool value)
0x26212  ldarg.0
0x26213  ldloc.1
0x26214  call     instance class Microsoft.ReportingServices.Modeling.ModelGeneration.RuleProcessResult Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule::ProcessCreatedModelItem(class Microsoft.ReportingServices.Modeling.ModelItem createdItem)
0x26219  ret
```
