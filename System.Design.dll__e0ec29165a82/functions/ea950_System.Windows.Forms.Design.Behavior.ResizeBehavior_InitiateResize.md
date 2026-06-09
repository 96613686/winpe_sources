# System.Windows.Forms.Design.Behavior.ResizeBehavior::InitiateResize

- ea: `0xea950`
- end: `0xeac24`
- name: `System.Windows.Forms.Design.Behavior.ResizeBehavior::InitiateResize`
- size: `724`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0xeaf70`

## callees

- `0x8eec0`
- `0xa29d0`
- `0xe4a60`
- `0xe4af0`
- `0xe5330`
- `0xe6940`
- `0xea5b0`
- `0xea950`

## string_xrefs

- `0xeaab7`: `BehaviorServiceResizeControl`
- `0xeaad0`: `BehaviorServiceResizeControls`

## pseudocode

```c

```

## disassembly

```asm
0xea950  ldarg.0
0xea951  call     instance class System.Windows.Forms.Design.Behavior.BehaviorService System.Windows.Forms.Design.Behavior.ResizeBehavior::get_BehaviorService()
0xea956  callvirt instance bool System.Windows.Forms.Design.Behavior.BehaviorService::get_UseSnapLines()
0xea95b  stloc.0
0xea95c  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xea961  stloc.1
0xea962  ldarg.0
0xea963  ldfld    class [mscorlib]System.IServiceProvider System.Windows.Forms.Design.Behavior.ResizeBehavior::serviceProvider
0xea968  ldtoken  [System]System.ComponentModel.Design.IDesignerHost
0xea96d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xea972  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0xea977  isinst   [System]System.ComponentModel.Design.IDesignerHost
0xea97c  stloc.2
0xea97d  ldc.i4.0
0xea97e  stloc.s  4
0xea980  br       loc_EAA2E
0xea985  ldarg.0
0xea986  ldfld    valuetype ResizeComponent[] System.Windows.Forms.Design.Behavior.ResizeBehavior::resizeComponents
0xea98b  ldloc.s  4
0xea98d  ldelema  ResizeComponent
0xea992  ldarg.0
0xea993  ldfld    valuetype ResizeComponent[] System.Windows.Forms.Design.Behavior.ResizeBehavior::resizeComponents
0xea998  ldloc.s  4
0xea99a  ldelema  ResizeComponent
0xea99f  ldfld    object ResizeComponent::resizeControl
0xea9a4  castclass [System.Windows.Forms]System.Windows.Forms.Control
0xea9a9  callvirt instance valuetype [System.Drawing]System.Drawing.Rectangle [System.Windows.Forms]System.Windows.Forms.Control::get_Bounds()
0xea9ae  stfld    valuetype [System.Drawing]System.Drawing.Rectangle ResizeComponent::resizeBounds
0xea9b3  ldloc.0
0xea9b4  brfalse.s loc_EA9CF
0xea9b6  ldloc.1
0xea9b7  ldarg.0
0xea9b8  ldfld    valuetype ResizeComponent[] System.Windows.Forms.Design.Behavior.ResizeBehavior::resizeComponents
0xea9bd  ldloc.s  4
0xea9bf  ldelema  ResizeComponent
0xea9c4  ldfld    object ResizeComponent::resizeControl
0xea9c9  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xea9ce  pop
0xea9cf  ldloc.2
0xea9d0  brfalse.s loc_EAA28
0xea9d2  ldloc.2
0xea9d3  ldarg.0
0xea9d4  ldfld    valuetype ResizeComponent[] System.Windows.Forms.Design.Behavior.ResizeBehavior::resizeComponents
0xea9d9  ldloc.s  4
0xea9db  ldelema  ResizeComponent
0xea9e0  ldfld    object ResizeComponent::resizeControl
0xea9e5  isinst   [System]System.ComponentModel.Component
0xea9ea  callvirt instance class [System]System.ComponentModel.Design.IDesigner [System]System.ComponentModel.Design.IDesignerHost::GetDesigner(class [System]System.ComponentModel.IComponent)
0xea9ef  isinst   System.Windows.Forms.Design.ControlDesigner
0xea9f4  stloc.s  5
0xea9f6  ldloc.s  5
0xea9f8  brfalse.s loc_EAA15
0xea9fa  ldarg.0
0xea9fb  ldfld    valuetype ResizeComponent[] System.Windows.Forms.Design.Behavior.ResizeBehavior::resizeComponents
0xeaa00  ldloc.s  4
0xeaa02  ldelema  ResizeComponent
0xeaa07  ldloc.s  5
0xeaa09  callvirt instance valuetype System.Windows.Forms.Design.SelectionRules System.Windows.Forms.Design.ControlDesigner::get_SelectionRules()
0xeaa0e  stfld    valuetype System.Windows.Forms.Design.SelectionRules ResizeComponent::resizeRules
0xeaa13  br.s     loc_EAA28
0xeaa15  ldarg.0
0xeaa16  ldfld    valuetype ResizeComponent[] System.Windows.Forms.Design.Behavior.ResizeBehavior::resizeComponents
0xeaa1b  ldloc.s  4
0xeaa1d  ldelema  ResizeComponent
0xeaa22  ldc.i4.0
0xeaa23  stfld    valuetype System.Windows.Forms.Design.SelectionRules ResizeComponent::resizeRules
0xeaa28  ldloc.s  4
0xeaa2a  ldc.i4.1
0xeaa2b  add
0xeaa2c  stloc.s  4
0xeaa2e  ldloc.s  4
0xeaa30  ldarg.0
0xeaa31  ldfld    valuetype ResizeComponent[] System.Windows.Forms.Design.Behavior.ResizeBehavior::resizeComponents
0xeaa36  ldlen
0xeaa37  conv.i4
0xeaa38  blt      loc_EA985
0xeaa3d  ldarg.0
0xeaa3e  call     instance class System.Windows.Forms.Design.Behavior.BehaviorService System.Windows.Forms.Design.Behavior.ResizeBehavior::get_BehaviorService()
0xeaa43  ldc.i4.0
0xeaa44  callvirt instance void System.Windows.Forms.Design.Behavior.BehaviorService::EnableAllAdorners(bool enabled)
0xeaa49  ldarg.0
0xeaa4a  ldfld    class [mscorlib]System.IServiceProvider System.Windows.Forms.Design.Behavior.ResizeBehavior::serviceProvider
0xeaa4f  ldtoken  [System]System.ComponentModel.Design.IDesignerHost
0xeaa54  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xeaa59  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0xeaa5e  castclass [System]System.ComponentModel.Design.IDesignerHost
0xeaa63  stloc.3
0xeaa64  ldloc.3
0xeaa65  brfalse  loc_EAB00
0xeaa6a  ldarg.0
0xeaa6b  ldfld    valuetype ResizeComponent[] System.Windows.Forms.Design.Behavior.ResizeBehavior::resizeComponents
0xeaa70  ldlen
0xeaa71  conv.i4
0xeaa72  ldc.i4.1
0xeaa73  bne.un.s loc_EAAD0
0xeaa75  ldarg.0
0xeaa76  ldfld    valuetype ResizeComponent[] System.Windows.Forms.Design.Behavior.ResizeBehavior::resizeComponents
0xeaa7b  ldc.i4.0
0xeaa7c  ldelema  ResizeComponent
0xeaa81  ldfld    object ResizeComponent::resizeControl
0xeaa86  call     string [System]System.ComponentModel.TypeDescriptor::GetComponentName(object)
0xeaa8b  stloc.s  7
0xeaa8d  ldloc.s  7
0xeaa8f  brfalse.s loc_EAA9A
0xeaa91  ldloc.s  7
0xeaa93  callvirt instance int32 [mscorlib]System.String::get_Length()
0xeaa98  brtrue.s loc_EAAB7
0xeaa9a  ldarg.0
0xeaa9b  ldfld    valuetype ResizeComponent[] System.Windows.Forms.Design.Behavior.ResizeBehavior::resizeComponents
0xeaaa0  ldc.i4.0
0xeaaa1  ldelema  ResizeComponent
0xeaaa6  ldfld    object ResizeComponent::resizeControl
0xeaaab  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xeaab0  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xeaab5  stloc.s  7
0xeaab7  ldstr    aBehaviorservic_4// "BehaviorServiceResizeControl"
0xeaabc  ldc.i4.1
0xeaabd  newarr   [mscorlib]System.Object
0xeaac2  dup
0xeaac3  ldc.i4.0
0xeaac4  ldloc.s  7
0xeaac6  stelem.ref
0xeaac7  call     string System.Design.SR::GetString(string name, object[] args)
0xeaacc  stloc.s  6
0xeaace  br.s     loc_EAAF2
0xeaad0  ldstr    aBehaviorservic_5// "BehaviorServiceResizeControls"
0xeaad5  ldc.i4.1
0xeaad6  newarr   [mscorlib]System.Object
0xeaadb  dup
0xeaadc  ldc.i4.0
0xeaadd  ldarg.0
0xeaade  ldfld    valuetype ResizeComponent[] System.Windows.Forms.Design.Behavior.ResizeBehavior::resizeComponents
0xeaae3  ldlen
0xeaae4  conv.i4
0xeaae5  box      [mscorlib]System.Int32
0xeaaea  stelem.ref
0xeaaeb  call     string System.Design.SR::GetString(string name, object[] args)
0xeaaf0  stloc.s  6
0xeaaf2  ldarg.0
0xeaaf3  ldloc.3
0xeaaf4  ldloc.s  6
0xeaaf6  callvirt instance class [System]System.ComponentModel.Design.DesignerTransaction [System]System.ComponentModel.Design.IDesignerHost::CreateTransaction(string)
0xeaafb  stfld    class [System]System.ComponentModel.Design.DesignerTransaction System.Windows.Forms.Design.Behavior.ResizeBehavior::resizeTransaction
0xeab00  ldarg.0
0xeab01  ldc.i4.1
0xeab02  stfld    bool System.Windows.Forms.Design.Behavior.ResizeBehavior::initialResize
0xeab07  ldloc.0
0xeab08  brfalse.s loc_EAB22
0xeab0a  ldarg.0
0xeab0b  ldarg.0
0xeab0c  ldfld    class [mscorlib]System.IServiceProvider System.Windows.Forms.Design.Behavior.ResizeBehavior::serviceProvider
0xeab11  ldloc.1
0xeab12  ldc.i4.1
0xeab13  newobj   instance void System.Windows.Forms.Design.Behavior.DragAssistanceManager::.ctor(class [mscorlib]System.IServiceProvider serviceProvider, class [mscorlib]System.Collections.ArrayList dragComponents, bool resizing)
0xeab18  stfld    class System.Windows.Forms.Design.Behavior.DragAssistanceManager System.Windows.Forms.Design.Behavior.ResizeBehavior::dragManager
0xeab1d  br       loc_EAC1C
0xeab22  ldarg.0
0xeab23  ldfld    valuetype ResizeComponent[] System.Windows.Forms.Design.Behavior.ResizeBehavior::resizeComponents
0xeab28  ldlen
0xeab29  brfalse  loc_EAC1C
0xeab2e  ldarg.0
0xeab2f  ldfld    valuetype ResizeComponent[] System.Windows.Forms.Design.Behavior.ResizeBehavior::resizeComponents
0xeab34  ldc.i4.0
0xeab35  ldelema  ResizeComponent
0xeab3a  ldfld    object ResizeComponent::resizeControl
0xeab3f  isinst   [System.Windows.Forms]System.Windows.Forms.Control
0xeab44  stloc.s  8
0xeab46  ldloc.s  8
0xeab48  brfalse  loc_EAC1C
0xeab4d  ldloc.s  8
0xeab4f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control::get_Parent()
0xeab54  brfalse  loc_EAC1C
0xeab59  ldloc.s  8
0xeab5b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control::get_Parent()
0xeab60  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0xeab65  ldstr    aSnaptogrid// "SnapToGrid"
0xeab6a  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0xeab6f  stloc.s  9
0xeab71  ldloc.s  9
0xeab73  brfalse  loc_EAC1C
0xeab78  ldloc.s  9
0xeab7a  ldloc.s  8
0xeab7c  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control::get_Parent()
0xeab81  callvirt instance object [System]System.ComponentModel.PropertyDescriptor::GetValue(object)
0xeab86  unbox.any [mscorlib]System.Boolean
0xeab8b  brfalse  loc_EAC1C
0xeab90  ldloc.s  8
0xeab92  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control::get_Parent()
0xeab97  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0xeab9c  ldstr    aGridsize// "GridSize"
0xeaba1  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0xeaba6  stloc.s  0xA
0xeaba8  ldloc.s  0xA
0xeabaa  brfalse.s loc_EAC1C
0xeabac  ldarg.0
0xeabad  ldloc.s  0xA
0xeabaf  ldloc.s  8
0xeabb1  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control::get_Parent()
0xeabb6  callvirt instance object [System]System.ComponentModel.PropertyDescriptor::GetValue(object)
0xeabbb  unbox.any [System.Drawing]System.Drawing.Size
0xeabc0  stfld    valuetype [System.Drawing]System.Drawing.Size System.Windows.Forms.Design.Behavior.ResizeBehavior::parentGridSize
0xeabc5  ldarg.0
0xeabc6  ldarg.0
0xeabc7  ldfld    class System.Windows.Forms.Design.Behavior.BehaviorService System.Windows.Forms.Design.Behavior.ResizeBehavior::behaviorService
0xeabcc  ldloc.s  8
0xeabce  callvirt instance valuetype [System.Drawing]System.Drawing.Point System.Windows.Forms.Design.Behavior.BehaviorService::ControlToAdornerWindow(class [System.Windows.Forms]System.Windows.Forms.Control c)
0xeabd3  stfld    valuetype [System.Drawing]System.Drawing.Point System.Windows.Forms.Design.Behavior.ResizeBehavior::parentLocation
0xeabd8  ldarg.0
0xeabd9  ldflda   valuetype [System.Drawing]System.Drawing.Point System.Windows.Forms.Design.Behavior.ResizeBehavior::parentLocation
0xeabde  dup
0xeabdf  call     instance int32 [System.Drawing]System.Drawing.Point::get_X()
0xeabe4  ldloc.s  8
0xeabe6  callvirt instance valuetype [System.Drawing]System.Drawing.Point [System.Windows.Forms]System.Windows.Forms.Control::get_Location()
0xeabeb  stloc.s  0xB
0xeabed  ldloca.s 0xB
0xeabef  call     instance int32 [System.Drawing]System.Drawing.Point::get_X()
0xeabf4  sub
0xeabf5  call     instance void [System.Drawing]System.Drawing.Point::set_X(int32)
0xeabfa  ldarg.0
0xeabfb  ldflda   valuetype [System.Drawing]System.Drawing.Point System.Windows.Forms.Design.Behavior.ResizeBehavior::parentLocation
0xeac00  dup
0xeac01  call     instance int32 [System.Drawing]System.Drawing.Point::get_Y()
0xeac06  ldloc.s  8
0xeac08  callvirt instance valuetype [System.Drawing]System.Drawing.Point [System.Windows.Forms]System.Windows.Forms.Control::get_Location()
0xeac0d  stloc.s  0xB
0xeac0f  ldloca.s 0xB
0xeac11  call     instance int32 [System.Drawing]System.Drawing.Point::get_Y()
0xeac16  sub
0xeac17  call     instance void [System.Drawing]System.Drawing.Point::set_Y(int32)
0xeac1c  ldarg.0
0xeac1d  ldc.i4.0
0xeac1e  stfld    bool System.Windows.Forms.Design.Behavior.ResizeBehavior::captureLost
0xeac23  ret
```
