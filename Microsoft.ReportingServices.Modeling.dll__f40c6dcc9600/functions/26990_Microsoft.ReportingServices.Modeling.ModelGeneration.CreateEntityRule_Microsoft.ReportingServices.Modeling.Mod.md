# Microsoft.ReportingServices.Modeling.ModelGeneration.CreateEntityRule::Microsoft.ReportingServices.Modeling.ModelGeneration.ITableProcessingRule.Process

- ea: `0x26990`
- end: `0x26adf`
- name: `Microsoft.ReportingServices.Modeling.ModelGeneration.CreateEntityRule::Microsoft.ReportingServices.Modeling.ModelGeneration.ITableProcessingRule.Process`
- size: `335`
- prototype: ``
- caller_count: `0`
- callee_count: `33`
- tags: `service_task, broker_com_uri`

## callees

- `0xc060`
- `0xce20`
- `0xd990`
- `0xdf60`
- `0xe050`
- `0xe390`
- `0xe510`
- `0x103b0`
- `0x105a0`
- `0x108d0`
- `0x13a60`
- `0x13a70`
- `0x16b00`
- `0x16b60`
- `0x25640`
- `0x25660`
- `0x26990`
- `0x27520`
- `0x27540`
- `0x278f0`
- `0x27920`
- `0x27930`
- `0x29700`
- `0x29720`
- `0x29760`
- `0x29820`
- `0x29840`
- `0x29a70`
- `0x2a8b0`
- `0x2a8c0`
- `0x2d4b0`
- `0x2d4c0`
- `0x2d620`

## pseudocode

```c

```

## disassembly

```asm
0x26990  ldarg.1
0x26991  callvirt instance string Microsoft.ReportingServices.Modeling.DsvTable::get_DataSourceID()
0x26996  brfalse.s loc_269CA
0x26998  ldarg.1
0x26999  callvirt instance string Microsoft.ReportingServices.Modeling.DsvTable::get_DataSourceID()
0x2699e  ldarg.0
0x2699f  call     instance class Microsoft.ReportingServices.Modeling.SemanticModel Microsoft.ReportingServices.Modeling.ModelGeneration.Rule::get_Model()
0x269a4  callvirt instance class Microsoft.ReportingServices.Modeling.DataSourceView Microsoft.ReportingServices.Modeling.SemanticModel::get_DataSourceView()
0x269a9  callvirt instance string Microsoft.ReportingServices.Modeling.DataSourceView::get_DataSourceID()
0x269ae  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x269b3  brfalse.s loc_269CA
0x269b5  ldarg.0
0x269b6  ldc.i4.1
0x269b7  newarr   [mscorlib]System.String
0x269bc  dup
0x269bd  ldc.i4.0
0x269be  call     string Microsoft.ReportingServices.Modeling.ModelGeneration.SR::get_CreateEntityRule_NonPrimaryDataSource()
0x269c3  stelem.ref
0x269c4  call     instance class Microsoft.ReportingServices.Modeling.ModelGeneration.RuleProcessResult Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule::ProcessFailed(string[] messages)
0x269c9  ret
0x269ca  ldarg.1
0x269cb  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class Microsoft.ReportingServices.Modeling.DsvColumn> Microsoft.ReportingServices.Modeling.DsvTable::get_PrimaryKey()
0x269d0  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class Microsoft.ReportingServices.Modeling.DsvColumn>::get_Count()
0x269d5  brtrue.s loc_269EC
0x269d7  ldarg.0
0x269d8  ldc.i4.1
0x269d9  newarr   [mscorlib]System.String
0x269de  dup
0x269df  ldc.i4.0
0x269e0  call     string Microsoft.ReportingServices.Modeling.ModelGeneration.SR::get_CreateEntityRule_NoPrimaryKey()
0x269e5  stelem.ref
0x269e6  call     instance class Microsoft.ReportingServices.Modeling.ModelGeneration.RuleProcessResult Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule::ProcessFailed(string[] messages)
0x269eb  ret
0x269ec  ldarg.1
0x269ed  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class Microsoft.ReportingServices.Modeling.DsvColumn> Microsoft.ReportingServices.Modeling.DsvTable::get_PrimaryKey()
0x269f2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class Microsoft.ReportingServices.Modeling.DsvColumn>::GetEnumerator()
0x269f7  stloc.1
0x269f8  br.s     loc_26A32
0x269fa  ldloc.1
0x269fb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.ReportingServices.Modeling.DsvColumn>::get_Current()
0x26a00  stloc.2
0x26a01  ldloc.2
0x26a02  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.DataType> Microsoft.ReportingServices.Modeling.DsvColumn::get_ModelingDataType()
0x26a07  stloc.3
0x26a08  ldloca.s 3
0x26a0a  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.DataType>::get_HasValue()
0x26a0f  brtrue.s loc_26A32
0x26a11  ldarg.0
0x26a12  ldc.i4.1
0x26a13  newarr   [mscorlib]System.String
0x26a18  dup
0x26a19  ldc.i4.0
0x26a1a  ldloc.2
0x26a1b  callvirt instance class [mscorlib]System.Type Microsoft.ReportingServices.Modeling.DsvColumn::get_DataType()
0x26a20  call     string Microsoft.ReportingServices.Modeling.ModelGeneration.SR::Rules_UnsupportedDataType(class [mscorlib]System.Type type)
0x26a25  stelem.ref
0x26a26  call     instance class Microsoft.ReportingServices.Modeling.ModelGeneration.RuleProcessResult Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule::ProcessFailed(string[] messages)
0x26a2b  stloc.s  4
0x26a2d  leave    loc_26ADC
0x26a32  ldloc.1
0x26a33  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x26a38  brtrue.s loc_269FA
0x26a3a  leave.s  loc_26A46
0x26a3c  ldloc.1
0x26a3d  brfalse.s loc_26A45
0x26a3f  ldloc.1
0x26a40  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26a45  endfinally
0x26a46  ldarg.2
0x26a47  callvirt instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelGeneration.ExistingTableBindingInfo::get_Entity()
0x26a4c  brfalse.s loc_26A5B
0x26a4e  ldarg.0
0x26a4f  ldarg.2
0x26a50  callvirt instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelGeneration.ExistingTableBindingInfo::get_Entity()
0x26a55  call     instance class Microsoft.ReportingServices.Modeling.ModelGeneration.RuleProcessResult Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule::ProcessFoundExistingModelItem(class Microsoft.ReportingServices.Modeling.ModelItem item)
0x26a5a  ret
0x26a5b  newobj   instance void Microsoft.ReportingServices.Modeling.ModelEntity::.ctor()
0x26a60  stloc.0
0x26a61  ldloc.0
0x26a62  ldarg.0
0x26a63  ldarg.1
0x26a64  call     instance string Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule::CreateModelItemName(class Microsoft.ReportingServices.Modeling.DsvItem dsvItem)
0x26a69  ldarg.0
0x26a6a  call     instance class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.Modeling.ModelGeneration.Rule::get_StringCulture()
0x26a6f  call     string Microsoft.ReportingServices.Modeling.StringManipulation::GetSingular(string noun, class [mscorlib]System.Globalization.CultureInfo culture)
0x26a74  callvirt instance void Microsoft.ReportingServices.Modeling.ModelItem::set_Name(string value)
0x26a79  ldloc.0
0x26a7a  ldloc.0
0x26a7b  callvirt instance string Microsoft.ReportingServices.Modeling.ModelItem::get_Name()
0x26a80  ldarg.0
0x26a81  call     instance class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.Modeling.ModelGeneration.Rule::get_StringCulture()
0x26a86  call     string Microsoft.ReportingServices.Modeling.StringManipulation::GetPlural(string singular, class [mscorlib]System.Globalization.CultureInfo culture)
0x26a8b  callvirt instance void Microsoft.ReportingServices.Modeling.ModelEntity::set_CollectionName(string value)
0x26a90  ldloc.0
0x26a91  ldarg.1
0x26a92  callvirt instance string Microsoft.ReportingServices.Modeling.DsvItem::get_Name()
0x26a97  newobj   instance void Microsoft.ReportingServices.Modeling.TableBinding::.ctor(string name)
0x26a9c  callvirt instance void Microsoft.ReportingServices.Modeling.ModelEntity::set_Binding(class Microsoft.ReportingServices.Modeling.Binding value)
0x26aa1  ldarg.0
0x26aa2  ldloc.0
0x26aa3  ldarg.0
0x26aa4  call     instance class Microsoft.ReportingServices.Modeling.SemanticModel Microsoft.ReportingServices.Modeling.ModelGeneration.Rule::get_Model()
0x26aa9  callvirt instance class Microsoft.ReportingServices.Modeling.ModelEntityFolderItemCollection Microsoft.ReportingServices.Modeling.SemanticModel::get_Entities()
0x26aae  call     instance void Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule::InsertItemSortedByName(class Microsoft.ReportingServices.Modeling.ModelItem item, class Microsoft.ReportingServices.Modeling.IOwnedModelItemCollection coll)
0x26ab3  ldarg.0
0x26ab4  ldloc.0
0x26ab5  ldarg.0
0x26ab6  call     instance class [System.Xml]System.Xml.XPath.IXPathNavigable Microsoft.ReportingServices.Modeling.ModelGeneration.EntityRuleBase::get_EntityFragment()
0x26abb  ldarg.0
0x26abc  call     instance class [System.Xml]System.Xml.XPath.IXPathNavigable Microsoft.ReportingServices.Modeling.ModelGeneration.EntityRuleBase::get_FolderFragment()
0x26ac1  call     instance void Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule::FinalizeModelItem(class Microsoft.ReportingServices.Modeling.ModelItem item, class [System.Xml]System.Xml.XPath.IXPathNavigable fragment, class [System.Xml]System.Xml.XPath.IXPathNavigable folderFragment)
0x26ac6  ldarg.2
0x26ac7  ldloc.0
0x26ac8  callvirt instance void Microsoft.ReportingServices.Modeling.ModelGeneration.ExistingTableBindingInfo::set_Entity(class Microsoft.ReportingServices.Modeling.ModelEntity value)
0x26acd  ldarg.2
0x26ace  ldc.i4.1
0x26acf  callvirt instance void Microsoft.ReportingServices.Modeling.ModelGeneration.ExistingBindingInfo::set_EvaluateDependentRules(bool value)
0x26ad4  ldarg.0
0x26ad5  ldloc.0
0x26ad6  call     instance class Microsoft.ReportingServices.Modeling.ModelGeneration.RuleProcessResult Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule::ProcessCreatedModelItem(class Microsoft.ReportingServices.Modeling.ModelItem createdItem)
0x26adb  ret
0x26adc  ldloc.s  4
0x26ade  ret
```
