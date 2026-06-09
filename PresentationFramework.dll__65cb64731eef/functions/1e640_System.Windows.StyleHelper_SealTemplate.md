# System.Windows.StyleHelper::SealTemplate

- ea: `0x1e640`
- end: `0x1e7d0`
- name: `System.Windows.StyleHelper::SealTemplate`
- size: `400`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x16530`

## callees

- `0x14f70`
- `0x16520`
- `0x165e0`
- `0x171a0`
- `0x1a2d0`
- `0x1e640`
- `0x1ece0`
- `0x1ed50`
- `0x21040`
- `0x31370`
- `0x38c70`

## string_xrefs

- `0x1e6e4`: `CannotHavePropertyInTemplate`
- `0x1e716`: `CannotHavePropertyInTemplate`
- `0x1e748`: `CannotHavePropertyInTemplate`
- `0x1e77a`: `CannotHavePropertyInTemplate`
- `0x1e7ac`: `CannotHavePropertyInTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x1e640  ldarg.1
0x1e641  ldind.u1
0x1e642  brfalse.s loc_1E645
0x1e644  ret
0x1e645  ldarg.0
0x1e646  brfalse.s loc_1E64E
0x1e648  ldarg.0
0x1e649  callvirt instance void System.Windows.FrameworkTemplate::ProcessTemplateBeforeSeal()
0x1e64e  ldarg.2
0x1e64f  brfalse.s loc_1E658
0x1e651  ldarg.2
0x1e652  ldarg.0
0x1e653  callvirt instance void System.Windows.FrameworkElementFactory::Seal(class System.Windows.FrameworkTemplate ownerTemplate)
0x1e658  ldarg.3
0x1e659  brfalse.s loc_1E661
0x1e65b  ldarg.3
0x1e65c  callvirt instance void System.Windows.TriggerCollection::Seal()
0x1e661  ldarg.s  4
0x1e663  brfalse.s loc_1E66D
0x1e665  ldarg.s  4
0x1e667  ldc.i4.1
0x1e668  callvirt instance void System.Windows.ResourceDictionary::set_IsReadOnly(bool value)
0x1e66d  ldarg.2
0x1e66e  brfalse.s loc_1E684
0x1e670  ldarg.2
0x1e671  ldarg.s  6
0x1e673  ldarg.s  7
0x1e675  ldarg.s  9
0x1e677  ldarg.s  0xA
0x1e679  ldarg.s  0xC
0x1e67b  ldarg.s  5
0x1e67d  ldarg.s  0xD
0x1e67f  call     void System.Windows.StyleHelper::ProcessTemplateContentFromFEF(class System.Windows.FrameworkElementFactory factory, valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype System.Windows.ChildRecord>& childRecordFromChildIndex, valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype MS.Utility.ItemStructMap`1<valuetype System.Windows.TriggerSourceRecord>>& triggerSourceRecordFromChildIndex, valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype System.Windows.ChildPropertyDependent>& resourceDependents, valuetype [WindowsBase]MS.Utility.ItemStructList`1<valuetype System.Windows.ChildEventDependent>& eventDependents, class [System]System.Collections.Specialized.HybridDictionary& dataTriggerRecordFromBinding, class [System]System.Collections.Specialized.HybridDictionary childIndexFromChildID, bool& hasInstanceValues)
0x1e684  ldc.i4.0
0x1e685  stloc.0
0x1e686  ldarg.3
0x1e687  ldarg.0
0x1e688  ldarg.s  6
0x1e68a  ldarg.s  7
0x1e68c  ldarg.s  8
0x1e68e  ldarg.s  9
0x1e690  ldarg.s  0xA
0x1e692  ldarg.s  0xC
0x1e694  ldarg.s  5
0x1e696  ldarg.s  0xD
0x1e698  ldarg.s  0xB
0x1e69a  ldarg.2
0x1e69b  ldarg.s  0xE
0x1e69d  ldarg.0
0x1e69e  ldflda   valuetype [WindowsBase]MS.Utility.FrugalMap System.Windows.FrameworkTemplate::PropertyTriggersWithActions
0x1e6a3  ldarg.0
0x1e6a4  ldflda   class [System]System.Collections.Specialized.HybridDictionary System.Windows.FrameworkTemplate::DataTriggersWithActions
0x1e6a9  ldloca.s 0
0x1e6ab  call     void System.Windows.StyleHelper::ProcessTemplateTriggers(class System.Windows.TriggerCollection triggers, class System.Windows.FrameworkTemplate frameworkTemplate, valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype System.Windows.ChildRecord>& childRecordFromChildIndex, valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype MS.Utility.ItemStructMap`1<valuetype System.Windows.TriggerSourceRecord>>& triggerSourceRecordFromChildIndex, valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype System.Windows.ContainerDependent>& containerDependents, valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype System.Windows.ChildPropertyDependent>& resourceDependents, valuetype [WindowsBase]MS.Utility.ItemStructList`1<valuetype System.Windows.ChildEventDependent>& eventDependents, class [System]System.Collections.Specialized.HybridDictionary& dataTriggerRecordFromBinding, class [System]System.Collections.Specialized.HybridDictionary childIndexFromChildID, bool& hasInstanceValues, class [System]System.Collections.Specialized.HybridDictionary& triggerActions, class System.Windows.FrameworkElementFactory templateRoot, class [PresentationCore]System.Windows.EventHandlersStore& eventHandlersStore, valuetype [WindowsBase]MS.Utility.FrugalMap& propertyTriggersWithActions, class [System]System.Collections.Specialized.HybridDictionary& dataTriggersWithActions, bool& hasLoadedChangeHandler)
0x1e6b0  ldarg.0
0x1e6b1  ldloc.0
0x1e6b2  callvirt instance void System.Windows.FrameworkTemplate::set_HasLoadedChangeHandler(bool value)
0x1e6b7  ldarg.0
0x1e6b8  callvirt instance void System.Windows.FrameworkTemplate::SetResourceReferenceState()
0x1e6bd  ldarg.1
0x1e6be  ldc.i4.1
0x1e6bf  stind.i1
0x1e6c0  ldarg.0
0x1e6c1  callvirt instance void [WindowsBase]System.Windows.Threading.DispatcherObject::DetachFromDispatcher()
0x1e6c6  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Control::TemplateProperty
0x1e6cb  ldarg.s  8
0x1e6cd  ldc.i4.1
0x1e6ce  call     bool System.Windows.StyleHelper::IsSetOnContainer(class [WindowsBase]System.Windows.DependencyProperty dp, valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype System.Windows.ContainerDependent>& containerDependents, bool alsoFromTriggers)
0x1e6d3  brtrue.s loc_1E6E4
0x1e6d5  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ContentPresenter::TemplateProperty
0x1e6da  ldarg.s  8
0x1e6dc  ldc.i4.1
0x1e6dd  call     bool System.Windows.StyleHelper::IsSetOnContainer(class [WindowsBase]System.Windows.DependencyProperty dp, valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype System.Windows.ContainerDependent>& containerDependents, bool alsoFromTriggers)
0x1e6e2  brfalse.s loc_1E707
0x1e6e4  ldstr    aCannothaveprop_0// "CannotHavePropertyInTemplate"
0x1e6e9  ldc.i4.1
0x1e6ea  newarr   [mscorlib]System.Object
0x1e6ef  dup
0x1e6f0  ldc.i4.0
0x1e6f1  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Control::TemplateProperty
0x1e6f6  callvirt instance string [WindowsBase]System.Windows.DependencyProperty::get_Name()
0x1e6fb  stelem.ref
0x1e6fc  call     string System.Windows.SR::Get(string id, object[] args)
0x1e701  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1e706  throw
0x1e707  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.FrameworkElement::StyleProperty
0x1e70c  ldarg.s  8
0x1e70e  ldc.i4.1
0x1e70f  call     bool System.Windows.StyleHelper::IsSetOnContainer(class [WindowsBase]System.Windows.DependencyProperty dp, valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype System.Windows.ContainerDependent>& containerDependents, bool alsoFromTriggers)
0x1e714  brfalse.s loc_1E739
0x1e716  ldstr    aCannothaveprop_0// "CannotHavePropertyInTemplate"
0x1e71b  ldc.i4.1
0x1e71c  newarr   [mscorlib]System.Object
0x1e721  dup
0x1e722  ldc.i4.0
0x1e723  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.FrameworkElement::StyleProperty
0x1e728  callvirt instance string [WindowsBase]System.Windows.DependencyProperty::get_Name()
0x1e72d  stelem.ref
0x1e72e  call     string System.Windows.SR::Get(string id, object[] args)
0x1e733  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1e738  throw
0x1e739  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.FrameworkElement::DefaultStyleKeyProperty
0x1e73e  ldarg.s  8
0x1e740  ldc.i4.1
0x1e741  call     bool System.Windows.StyleHelper::IsSetOnContainer(class [WindowsBase]System.Windows.DependencyProperty dp, valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype System.Windows.ContainerDependent>& containerDependents, bool alsoFromTriggers)
0x1e746  brfalse.s loc_1E76B
0x1e748  ldstr    aCannothaveprop_0// "CannotHavePropertyInTemplate"
0x1e74d  ldc.i4.1
0x1e74e  newarr   [mscorlib]System.Object
0x1e753  dup
0x1e754  ldc.i4.0
0x1e755  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.FrameworkElement::DefaultStyleKeyProperty
0x1e75a  callvirt instance string [WindowsBase]System.Windows.DependencyProperty::get_Name()
0x1e75f  stelem.ref
0x1e760  call     string System.Windows.SR::Get(string id, object[] args)
0x1e765  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1e76a  throw
0x1e76b  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.FrameworkElement::OverridesDefaultStyleProperty
0x1e770  ldarg.s  8
0x1e772  ldc.i4.1
0x1e773  call     bool System.Windows.StyleHelper::IsSetOnContainer(class [WindowsBase]System.Windows.DependencyProperty dp, valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype System.Windows.ContainerDependent>& containerDependents, bool alsoFromTriggers)
0x1e778  brfalse.s loc_1E79D
0x1e77a  ldstr    aCannothaveprop_0// "CannotHavePropertyInTemplate"
0x1e77f  ldc.i4.1
0x1e780  newarr   [mscorlib]System.Object
0x1e785  dup
0x1e786  ldc.i4.0
0x1e787  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.FrameworkElement::OverridesDefaultStyleProperty
0x1e78c  callvirt instance string [WindowsBase]System.Windows.DependencyProperty::get_Name()
0x1e791  stelem.ref
0x1e792  call     string System.Windows.SR::Get(string id, object[] args)
0x1e797  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1e79c  throw
0x1e79d  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.FrameworkElement::NameProperty
0x1e7a2  ldarg.s  8
0x1e7a4  ldc.i4.1
0x1e7a5  call     bool System.Windows.StyleHelper::IsSetOnContainer(class [WindowsBase]System.Windows.DependencyProperty dp, valuetype [WindowsBase]MS.Utility.FrugalStructList`1<valuetype System.Windows.ContainerDependent>& containerDependents, bool alsoFromTriggers)
0x1e7aa  brfalse.s loc_1E7CF
0x1e7ac  ldstr    aCannothaveprop_0// "CannotHavePropertyInTemplate"
0x1e7b1  ldc.i4.1
0x1e7b2  newarr   [mscorlib]System.Object
0x1e7b7  dup
0x1e7b8  ldc.i4.0
0x1e7b9  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.FrameworkElement::NameProperty
0x1e7be  callvirt instance string [WindowsBase]System.Windows.DependencyProperty::get_Name()
0x1e7c3  stelem.ref
0x1e7c4  call     string System.Windows.SR::Get(string id, object[] args)
0x1e7c9  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1e7ce  throw
0x1e7cf  ret
```
