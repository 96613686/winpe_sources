# System.Windows.StyleHelper::ProcessTemplateTriggers

- ea: `0x1ed50`
- end: `0x1ef5a`
- name: `System.Windows.StyleHelper::ProcessTemplateTriggers`
- size: `522`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: ``

## callers

- `0x1e640`

## callees

- `0x9290`
- `0x92f0`
- `0xa0c0`
- `0x18650`
- `0x18890`
- `0x1e7d0`
- `0x1ebc0`
- `0x1ed50`
- `0x1ef60`
- `0x1efd0`
- `0x21760`
- `0x217d0`
- `0x21ac0`
- `0x30510`
- `0x30ec0`
- `0x30f20`
- `0x31260`
- `0x38c70`

## string_xrefs

- `0x1eeec`: `UnsupportedTriggerInTemplate`
- `0x1ef2a`: `UnsupportedTriggerInTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x1ed50  ldarg.0
0x1ed51  brfalse  loc_1EF59
0x1ed56  ldarg.0
0x1ed57  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Windows.TriggerBase>::get_Count()
0x1ed5c  stloc.0
0x1ed5d  ldc.i4.0
0x1ed5e  stloc.1
0x1ed5f  br       loc_1EF52
0x1ed64  ldarg.0
0x1ed65  ldloc.1
0x1ed66  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Windows.TriggerBase>::get_Item(!!T0)
0x1ed6b  stloc.2
0x1ed6c  ldloc.2
0x1ed6d  ldloca.s 3
0x1ed6f  ldloca.s 4
0x1ed71  ldloca.s 5
0x1ed73  ldloca.s 6
0x1ed75  ldloca.s 7
0x1ed77  call     void System.Windows.StyleHelper::DetermineTriggerType(class System.Windows.TriggerBase triggerBase, [out] class System.Windows.Trigger& trigger, [out] class System.Windows.MultiTrigger& multiTrigger, [out] class System.Windows.DataTrigger& dataTrigger, [out] class System.Windows.MultiDataTrigger& multiDataTrigger, [out] class System.Windows.EventTrigger& eventTrigger)
0x1ed7c  ldloc.3
0x1ed7d  brtrue.s loc_1ED8E
0x1ed7f  ldloc.s  4
0x1ed81  brtrue.s loc_1ED8E
0x1ed83  ldloc.s  5
0x1ed85  brtrue.s loc_1ED8E
0x1ed87  ldloc.s  6
0x1ed89  brfalse  loc_1EF10
0x1ed8e  ldloc.2
0x1ed8f  callvirt instance valuetype System.Windows.TriggerCondition[] System.Windows.TriggerBase::get_TriggerConditions()
0x1ed94  stloc.s  8
0x1ed96  ldc.i4.0
0x1ed97  stloc.s  9
0x1ed99  br.s     loc_1EDC4
0x1ed9b  ldloc.s  8
0x1ed9d  ldloc.s  9
0x1ed9f  ldelema  System.Windows.TriggerCondition
0x1eda4  ldloc.s  8
0x1eda6  ldloc.s  9
0x1eda8  ldelema  System.Windows.TriggerCondition
0x1edad  ldfld    string System.Windows.TriggerCondition::SourceName
0x1edb2  ldarg.s  8
0x1edb4  call     int32 System.Windows.StyleHelper::QueryChildIndexFromChildName(string childName, class [System]System.Collections.Specialized.HybridDictionary childIndexFromChildName)
0x1edb9  stfld    int32 System.Windows.TriggerCondition::SourceChildIndex
0x1edbe  ldloc.s  9
0x1edc0  ldc.i4.1
0x1edc1  add
0x1edc2  stloc.s  9
0x1edc4  ldloc.s  9
0x1edc6  ldloc.s  8
0x1edc8  ldlen
0x1edc9  conv.i4
0x1edca  blt.s    loc_1ED9B
0x1edcc  ldc.i4.0
0x1edcd  stloc.s  0xA
0x1edcf  br.s     loc_1EE19
0x1edd1  ldloc.2
0x1edd2  ldflda   valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype System.Windows.PropertyValue> System.Windows.TriggerBase::PropertyValues
0x1edd7  ldloc.s  0xA
0x1edd9  call     instance var<u1> valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype System.Windows.PropertyValue>::get_Item(!!T0)
0x1edde  stloc.s  0xB
0x1ede0  ldloc.s  0xB
0x1ede2  ldfld    string System.Windows.PropertyValue::ChildName
0x1ede7  ldstr    aSelf// "~Self"
0x1edec  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1edf1  brfalse.s loc_1EE02
0x1edf3  ldloc.s  0xB
0x1edf5  ldfld    class [WindowsBase]System.Windows.DependencyProperty System.Windows.PropertyValue::Property
0x1edfa  ldc.i4.1
0x1edfb  ldarg.s  4
0x1edfd  call     void System.Windows.StyleHelper::AddContainerDependent(class [WindowsBase]System.Windows.DependencyProperty dp, bool fromVisualTrigger, valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype System.Windows.ContainerDependent>& containerDependents)
0x1ee02  ldloca.s 0xB
0x1ee04  ldarg.2
0x1ee05  ldarg.3
0x1ee06  ldarg.s  5
0x1ee08  ldarg.s  7
0x1ee0a  ldarg.s  8
0x1ee0c  ldarg.s  9
0x1ee0e  call     void System.Windows.StyleHelper::UpdateTables(valuetype System.Windows.PropertyValue& propertyValue, valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype System.Windows.ChildRecord>& childRecordFromChildIndex, valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype MS.Utility.ItemStructMap`1<valuetype System.Windows.TriggerSourceRecord>>& triggerSourceRecordFromChildIndex, valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype System.Windows.ChildPropertyDependent>& resourceDependents, class [System]System.Collections.Specialized.HybridDictionary& dataTriggerRecordFromBinding, class [System]System.Collections.Specialized.HybridDictionary childIndexFromChildName, bool& hasInstanceValues)
0x1ee13  ldloc.s  0xA
0x1ee15  ldc.i4.1
0x1ee16  add
0x1ee17  stloc.s  0xA
0x1ee19  ldloc.s  0xA
0x1ee1b  ldloc.2
0x1ee1c  ldflda   valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype System.Windows.PropertyValue> System.Windows.TriggerBase::PropertyValues
0x1ee21  call     instance int32 valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype System.Windows.PropertyValue>::get_Count()
0x1ee26  blt.s    loc_1EDD1
0x1ee28  ldloc.2
0x1ee29  callvirt instance bool System.Windows.TriggerBase::get_HasEnterActions()
0x1ee2e  brtrue.s loc_1EE3B
0x1ee30  ldloc.2
0x1ee31  callvirt instance bool System.Windows.TriggerBase::get_HasExitActions()
0x1ee36  brfalse  loc_1EF4E
0x1ee3b  ldloc.3
0x1ee3c  brfalse.s loc_1EE51
0x1ee3e  ldloc.2
0x1ee3f  ldloc.3
0x1ee40  callvirt instance class [WindowsBase]System.Windows.DependencyProperty System.Windows.Trigger::get_Property()
0x1ee45  ldarg.s  0xD
0x1ee47  call     void System.Windows.StyleHelper::AddPropertyTriggerWithAction(class System.Windows.TriggerBase triggerBase, class [WindowsBase]System.Windows.DependencyProperty property, valuetype [WindowsBase]MS.Utility.FrugalMap& triggersWithActions)
0x1ee4c  br       loc_1EF4E
0x1ee51  ldloc.s  4
0x1ee53  brfalse.s loc_1EE94
0x1ee55  ldc.i4.0
0x1ee56  stloc.s  0xC
0x1ee58  br.s     loc_1EE7F
0x1ee5a  ldloc.s  4
0x1ee5c  callvirt instance class System.Windows.ConditionCollection System.Windows.MultiTrigger::get_Conditions()
0x1ee61  ldloc.s  0xC
0x1ee63  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Windows.Condition>::get_Item(!!T0)
0x1ee68  stloc.s  0xD
0x1ee6a  ldloc.2
0x1ee6b  ldloc.s  0xD
0x1ee6d  callvirt instance class [WindowsBase]System.Windows.DependencyProperty System.Windows.Condition::get_Property()
0x1ee72  ldarg.s  0xD
0x1ee74  call     void System.Windows.StyleHelper::AddPropertyTriggerWithAction(class System.Windows.TriggerBase triggerBase, class [WindowsBase]System.Windows.DependencyProperty property, valuetype [WindowsBase]MS.Utility.FrugalMap& triggersWithActions)
0x1ee79  ldloc.s  0xC
0x1ee7b  ldc.i4.1
0x1ee7c  add
0x1ee7d  stloc.s  0xC
0x1ee7f  ldloc.s  0xC
0x1ee81  ldloc.s  4
0x1ee83  callvirt instance class System.Windows.ConditionCollection System.Windows.MultiTrigger::get_Conditions()
0x1ee88  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Windows.Condition>::get_Count()
0x1ee8d  blt.s    loc_1EE5A
0x1ee8f  br       loc_1EF4E
0x1ee94  ldloc.s  5
0x1ee96  brfalse.s loc_1EEAC
0x1ee98  ldloc.2
0x1ee99  ldloc.s  5
0x1ee9b  callvirt instance class System.Windows.Data.BindingBase System.Windows.DataTrigger::get_Binding()
0x1eea0  ldarg.s  0xE
0x1eea2  call     void System.Windows.StyleHelper::AddDataTriggerWithAction(class System.Windows.TriggerBase triggerBase, class System.Windows.Data.BindingBase binding, class [System]System.Collections.Specialized.HybridDictionary& dataTriggersWithActions)
0x1eea7  br       loc_1EF4E
0x1eeac  ldloc.s  6
0x1eeae  brfalse.s loc_1EEEC
0x1eeb0  ldc.i4.0
0x1eeb1  stloc.s  0xE
0x1eeb3  br.s     loc_1EEDA
0x1eeb5  ldloc.s  6
0x1eeb7  callvirt instance class System.Windows.ConditionCollection System.Windows.MultiDataTrigger::get_Conditions()
0x1eebc  ldloc.s  0xE
0x1eebe  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Windows.Condition>::get_Item(!!T0)
0x1eec3  stloc.s  0xF
0x1eec5  ldloc.2
0x1eec6  ldloc.s  0xF
0x1eec8  callvirt instance class System.Windows.Data.BindingBase System.Windows.Condition::get_Binding()
0x1eecd  ldarg.s  0xE
0x1eecf  call     void System.Windows.StyleHelper::AddDataTriggerWithAction(class System.Windows.TriggerBase triggerBase, class System.Windows.Data.BindingBase binding, class [System]System.Collections.Specialized.HybridDictionary& dataTriggersWithActions)
0x1eed4  ldloc.s  0xE
0x1eed6  ldc.i4.1
0x1eed7  add
0x1eed8  stloc.s  0xE
0x1eeda  ldloc.s  0xE
0x1eedc  ldloc.s  6
0x1eede  callvirt instance class System.Windows.ConditionCollection System.Windows.MultiDataTrigger::get_Conditions()
0x1eee3  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Windows.Condition>::get_Count()
0x1eee8  blt.s    loc_1EEB5
0x1eeea  br.s     loc_1EF4E
0x1eeec  ldstr    aUnsupportedtri_0// "UnsupportedTriggerInTemplate"
0x1eef1  ldc.i4.1
0x1eef2  newarr   [mscorlib]System.Object
0x1eef7  dup
0x1eef8  ldc.i4.0
0x1eef9  ldloc.2
0x1eefa  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1eeff  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x1ef04  stelem.ref
0x1ef05  call     string System.Windows.SR::Get(string id, object[] args)
0x1ef0a  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1ef0f  throw
0x1ef10  ldloc.s  7
0x1ef12  brfalse.s loc_1EF2A
0x1ef14  ldloc.s  7
0x1ef16  ldarg.s  8
0x1ef18  ldarg.s  0xA
0x1ef1a  ldarg.s  6
0x1ef1c  ldarg.s  0xB
0x1ef1e  ldarg.1
0x1ef1f  ldarg.s  0xC
0x1ef21  ldarg.s  0xF
0x1ef23  call     void System.Windows.StyleHelper::ProcessEventTrigger(class System.Windows.EventTrigger eventTrigger, class [System]System.Collections.Specialized.HybridDictionary childIndexFromChildName, class [System]System.Collections.Specialized.HybridDictionary& triggerActions, valuetype [WindowsBase]MS.Utility.ItemStructList`1<valuetype System.Windows.ChildEventDependent>& eventDependents, class System.Windows.FrameworkElementFactory templateRoot, class System.Windows.FrameworkTemplate frameworkTemplate, class [PresentationCore]System.Windows.EventHandlersStore& eventHandlersStore, bool& hasLoadedChangeHandler)
0x1ef28  br.s     loc_1EF4E
0x1ef2a  ldstr    aUnsupportedtri_0// "UnsupportedTriggerInTemplate"
0x1ef2f  ldc.i4.1
0x1ef30  newarr   [mscorlib]System.Object
0x1ef35  dup
0x1ef36  ldc.i4.0
0x1ef37  ldloc.2
0x1ef38  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1ef3d  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x1ef42  stelem.ref
0x1ef43  call     string System.Windows.SR::Get(string id, object[] args)
0x1ef48  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1ef4d  throw
0x1ef4e  ldloc.1
0x1ef4f  ldc.i4.1
0x1ef50  add
0x1ef51  stloc.1
0x1ef52  ldloc.1
0x1ef53  ldloc.0
0x1ef54  blt      loc_1ED64
0x1ef59  ret
```
