# System.Windows.TemplateContent::AutoAliasContentPresenter

- ea: `0x2dea0`
- end: `0x2e058`
- name: `System.Windows.TemplateContent::AutoAliasContentPresenter`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x2cbe0`

## callees

- `0x1e7d0`
- `0x2c620`
- `0x2dea0`
- `0x38c70`

## string_xrefs

- `0x2dece`: `Template`
- `0x2dee0`: `TemplateSelector`

## pseudocode

```c

```

## disassembly

```asm
0x2dea0  ldarg.1
0x2dea1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2dea6  brfalse.s loc_2DEB3
0x2dea8  ldarg.s  0xA
0x2deaa  brtrue.s loc_2DEB3
0x2deac  ldstr    aContent// "Content"
0x2deb1  starg.s  1
0x2deb3  ldarg.1
0x2deb4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2deb9  brtrue   loc_2E057
0x2debe  ldarg.s  9
0x2dec0  brtrue   loc_2E057
0x2dec5  ldarg.1
0x2dec6  ldarg.0
0x2dec7  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::FromName(string, class [mscorlib]System.Type)
0x2decc  stloc.0
0x2decd  ldarg.1
0x2dece  ldstr    aTemplate// "Template"
0x2ded3  call     string [mscorlib]System.String::Concat(string, string)
0x2ded8  ldarg.0
0x2ded9  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::FromName(string, class [mscorlib]System.Type)
0x2dede  stloc.1
0x2dedf  ldarg.1
0x2dee0  ldstr    aTemplateselect// "TemplateSelector"
0x2dee5  call     string [mscorlib]System.String::Concat(string, string)
0x2deea  ldarg.0
0x2deeb  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::FromName(string, class [mscorlib]System.Type)
0x2def0  stloc.2
0x2def1  ldarg.1
0x2def2  ldstr    aStringformat// "StringFormat"
0x2def7  call     string [mscorlib]System.String::Concat(string, string)
0x2defc  ldarg.0
0x2defd  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::FromName(string, class [mscorlib]System.Type)
0x2df02  stloc.3
0x2df03  ldloc.0
0x2df04  ldnull
0x2df05  ceq
0x2df07  ldarg.s  0xA
0x2df09  and
0x2df0a  brfalse.s loc_2DF2A
0x2df0c  ldstr    aMissingcontent// "MissingContentSource"
0x2df11  ldc.i4.2
0x2df12  newarr   [mscorlib]System.Object
0x2df17  dup
0x2df18  ldc.i4.0
0x2df19  ldarg.1
0x2df1a  stelem.ref
0x2df1b  dup
0x2df1c  ldc.i4.1
0x2df1d  ldarg.0
0x2df1e  stelem.ref
0x2df1f  call     string System.Windows.SR::Get(string id, object[] args)
0x2df24  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2df29  throw
0x2df2a  ldloc.0
0x2df2b  brfalse.s loc_2DF70
0x2df2d  ldloca.s 4
0x2df2f  initobj  System.Windows.PropertyValue
0x2df35  ldloca.s 4
0x2df37  ldc.i4.5
0x2df38  stfld    valuetype System.Windows.PropertyValueType System.Windows.PropertyValue::ValueType
0x2df3d  ldloca.s 4
0x2df3f  ldarg.2
0x2df40  stfld    string System.Windows.PropertyValue::ChildName
0x2df45  ldloca.s 4
0x2df47  ldloc.0
0x2df48  newobj   instance void System.Windows.TemplateBindingExtension::.ctor(class [WindowsBase]System.Windows.DependencyProperty property)
0x2df4d  stfld    object System.Windows.PropertyValue::ValueInternal
0x2df52  ldloca.s 4
0x2df54  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ContentPresenter::ContentProperty
0x2df59  stfld    class [WindowsBase]System.Windows.DependencyProperty System.Windows.PropertyValue::Property
0x2df5e  ldloca.s 4
0x2df60  ldarg.3
0x2df61  ldarg.s  4
0x2df63  ldarg.s  5
0x2df65  ldarg.s  6
0x2df67  ldarg.s  8
0x2df69  ldarg.s  7
0x2df6b  call     void System.Windows.StyleHelper::UpdateTables(valuetype System.Windows.PropertyValue& propertyValue, valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype System.Windows.ChildRecord>& childRecordFromChildIndex, valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype MS.Utility.ItemStructMap`1<valuetype System.Windows.TriggerSourceRecord>>& triggerSourceRecordFromChildIndex, valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype System.Windows.ChildPropertyDependent>& resourceDependents, class [System]System.Collections.Specialized.HybridDictionary& dataTriggerRecordFromBinding, class [System]System.Collections.Specialized.HybridDictionary childIndexFromChildName, bool& hasInstanceValues)
0x2df70  ldarg.s  0xB
0x2df72  brtrue   loc_2E057
0x2df77  ldarg.s  0xC
0x2df79  brtrue   loc_2E057
0x2df7e  ldarg.s  0xD
0x2df80  brtrue   loc_2E057
0x2df85  ldloc.1
0x2df86  brfalse.s loc_2DFCB
0x2df88  ldloca.s 5
0x2df8a  initobj  System.Windows.PropertyValue
0x2df90  ldloca.s 5
0x2df92  ldc.i4.5
0x2df93  stfld    valuetype System.Windows.PropertyValueType System.Windows.PropertyValue::ValueType
0x2df98  ldloca.s 5
0x2df9a  ldarg.2
0x2df9b  stfld    string System.Windows.PropertyValue::ChildName
0x2dfa0  ldloca.s 5
0x2dfa2  ldloc.1
0x2dfa3  newobj   instance void System.Windows.TemplateBindingExtension::.ctor(class [WindowsBase]System.Windows.DependencyProperty property)
0x2dfa8  stfld    object System.Windows.PropertyValue::ValueInternal
0x2dfad  ldloca.s 5
0x2dfaf  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ContentPresenter::ContentTemplateProperty
0x2dfb4  stfld    class [WindowsBase]System.Windows.DependencyProperty System.Windows.PropertyValue::Property
0x2dfb9  ldloca.s 5
0x2dfbb  ldarg.3
0x2dfbc  ldarg.s  4
0x2dfbe  ldarg.s  5
0x2dfc0  ldarg.s  6
0x2dfc2  ldarg.s  8
0x2dfc4  ldarg.s  7
0x2dfc6  call     void System.Windows.StyleHelper::UpdateTables(valuetype System.Windows.PropertyValue& propertyValue, valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype System.Windows.ChildRecord>& childRecordFromChildIndex, valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype MS.Utility.ItemStructMap`1<valuetype System.Windows.TriggerSourceRecord>>& triggerSourceRecordFromChildIndex, valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype System.Windows.ChildPropertyDependent>& resourceDependents, class [System]System.Collections.Specialized.HybridDictionary& dataTriggerRecordFromBinding, class [System]System.Collections.Specialized.HybridDictionary childIndexFromChildName, bool& hasInstanceValues)
0x2dfcb  ldloc.2
0x2dfcc  brfalse.s loc_2E011
0x2dfce  ldloca.s 6
0x2dfd0  initobj  System.Windows.PropertyValue
0x2dfd6  ldloca.s 6
0x2dfd8  ldc.i4.5
0x2dfd9  stfld    valuetype System.Windows.PropertyValueType System.Windows.PropertyValue::ValueType
0x2dfde  ldloca.s 6
0x2dfe0  ldarg.2
0x2dfe1  stfld    string System.Windows.PropertyValue::ChildName
0x2dfe6  ldloca.s 6
0x2dfe8  ldloc.2
0x2dfe9  newobj   instance void System.Windows.TemplateBindingExtension::.ctor(class [WindowsBase]System.Windows.DependencyProperty property)
0x2dfee  stfld    object System.Windows.PropertyValue::ValueInternal
0x2dff3  ldloca.s 6
0x2dff5  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ContentPresenter::ContentTemplateSelectorProperty
0x2dffa  stfld    class [WindowsBase]System.Windows.DependencyProperty System.Windows.PropertyValue::Property
0x2dfff  ldloca.s 6
0x2e001  ldarg.3
0x2e002  ldarg.s  4
0x2e004  ldarg.s  5
0x2e006  ldarg.s  6
0x2e008  ldarg.s  8
0x2e00a  ldarg.s  7
0x2e00c  call     void System.Windows.StyleHelper::UpdateTables(valuetype System.Windows.PropertyValue& propertyValue, valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype System.Windows.ChildRecord>& childRecordFromChildIndex, valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype MS.Utility.ItemStructMap`1<valuetype System.Windows.TriggerSourceRecord>>& triggerSourceRecordFromChildIndex, valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype System.Windows.ChildPropertyDependent>& resourceDependents, class [System]System.Collections.Specialized.HybridDictionary& dataTriggerRecordFromBinding, class [System]System.Collections.Specialized.HybridDictionary childIndexFromChildName, bool& hasInstanceValues)
0x2e011  ldloc.3
0x2e012  brfalse.s loc_2E057
0x2e014  ldloca.s 7
0x2e016  initobj  System.Windows.PropertyValue
0x2e01c  ldloca.s 7
0x2e01e  ldc.i4.5
0x2e01f  stfld    valuetype System.Windows.PropertyValueType System.Windows.PropertyValue::ValueType
0x2e024  ldloca.s 7
0x2e026  ldarg.2
0x2e027  stfld    string System.Windows.PropertyValue::ChildName
0x2e02c  ldloca.s 7
0x2e02e  ldloc.3
0x2e02f  newobj   instance void System.Windows.TemplateBindingExtension::.ctor(class [WindowsBase]System.Windows.DependencyProperty property)
0x2e034  stfld    object System.Windows.PropertyValue::ValueInternal
0x2e039  ldloca.s 7
0x2e03b  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ContentPresenter::ContentStringFormatProperty
0x2e040  stfld    class [WindowsBase]System.Windows.DependencyProperty System.Windows.PropertyValue::Property
0x2e045  ldloca.s 7
0x2e047  ldarg.3
0x2e048  ldarg.s  4
0x2e04a  ldarg.s  5
0x2e04c  ldarg.s  6
0x2e04e  ldarg.s  8
0x2e050  ldarg.s  7
0x2e052  call     void System.Windows.StyleHelper::UpdateTables(valuetype System.Windows.PropertyValue& propertyValue, valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype System.Windows.ChildRecord>& childRecordFromChildIndex, valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype MS.Utility.ItemStructMap`1<valuetype System.Windows.TriggerSourceRecord>>& triggerSourceRecordFromChildIndex, valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype System.Windows.ChildPropertyDependent>& resourceDependents, class [System]System.Collections.Specialized.HybridDictionary& dataTriggerRecordFromBinding, class [System]System.Collections.Specialized.HybridDictionary childIndexFromChildName, bool& hasInstanceValues)
0x2e057  ret
```
