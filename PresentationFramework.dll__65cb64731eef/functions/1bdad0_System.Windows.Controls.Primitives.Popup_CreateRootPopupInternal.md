# System.Windows.Controls.Primitives.Popup::CreateRootPopupInternal

- ea: `0x1bdad0`
- end: `0x1bdc9f`
- name: `System.Windows.Controls.Primitives.Popup::CreateRootPopupInternal`
- size: `463`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x19b380`
- `0x1bdac0`

## callees

- `0x109e0`
- `0x17f10`
- `0x38c70`
- `0x75300`
- `0x75560`
- `0x75790`
- `0x1bd2c0`
- `0x1bdad0`

## string_xrefs

- `0x1bdc78`: `IsOpen`
- `0x1bdc03`: `StaysOpen`
- `0x1bdaf8`: `CreateRootPopup_ChildHasLogicalParent`
- `0x1bdb20`: `CreateRootPopup_ChildHasVisualParent`

## pseudocode

```c

```

## disassembly

```asm
0x1bdad0  ldarg.0
0x1bdad1  brtrue.s loc_1BDADE
0x1bdad3  ldstr    aPopup_0// "popup"
0x1bdad8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1bdadd  throw
0x1bdade  ldarg.1
0x1bdadf  brtrue.s loc_1BDAEC
0x1bdae1  ldstr    aChild// "child"
0x1bdae6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1bdaeb  throw
0x1bdaec  ldnull
0x1bdaed  stloc.0
0x1bdaee  ldarg.1
0x1bdaef  call     class [WindowsBase]System.Windows.DependencyObject System.Windows.LogicalTreeHelper::GetParent(class [WindowsBase]System.Windows.DependencyObject current)
0x1bdaf4  dup
0x1bdaf5  stloc.0
0x1bdaf6  brfalse.s loc_1BDB16
0x1bdaf8  ldstr    aCreaterootpopu// "CreateRootPopup_ChildHasLogicalParent"
0x1bdafd  ldc.i4.2
0x1bdafe  newarr   [mscorlib]System.Object
0x1bdb03  dup
0x1bdb04  ldc.i4.0
0x1bdb05  ldarg.1
0x1bdb06  stelem.ref
0x1bdb07  dup
0x1bdb08  ldc.i4.1
0x1bdb09  ldloc.0
0x1bdb0a  stelem.ref
0x1bdb0b  call     string System.Windows.SR::Get(string id, object[] args)
0x1bdb10  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1bdb15  throw
0x1bdb16  ldarg.1
0x1bdb17  call     class [WindowsBase]System.Windows.DependencyObject [PresentationCore]System.Windows.Media.VisualTreeHelper::GetParent(class [WindowsBase]System.Windows.DependencyObject)
0x1bdb1c  dup
0x1bdb1d  stloc.0
0x1bdb1e  brfalse.s loc_1BDB3E
0x1bdb20  ldstr    aCreaterootpopu_0// "CreateRootPopup_ChildHasVisualParent"
0x1bdb25  ldc.i4.2
0x1bdb26  newarr   [mscorlib]System.Object
0x1bdb2b  dup
0x1bdb2c  ldc.i4.0
0x1bdb2d  ldarg.1
0x1bdb2e  stelem.ref
0x1bdb2f  dup
0x1bdb30  ldc.i4.1
0x1bdb31  ldloc.0
0x1bdb32  stelem.ref
0x1bdb33  call     string System.Windows.SR::Get(string id, object[] args)
0x1bdb38  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1bdb3d  throw
0x1bdb3e  ldstr    aPlacementtarge// "PlacementTarget"
0x1bdb43  newobj   instance void System.Windows.Data.Binding::.ctor(string path)
0x1bdb48  stloc.1
0x1bdb49  ldloc.1
0x1bdb4a  ldc.i4.1
0x1bdb4b  callvirt instance void System.Windows.Data.Binding::set_Mode(valuetype System.Windows.Data.BindingMode value)
0x1bdb50  ldloc.1
0x1bdb51  ldarg.1
0x1bdb52  callvirt instance void System.Windows.Data.Binding::set_Source(object value)
0x1bdb57  ldarg.0
0x1bdb58  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.Popup::PlacementTargetProperty
0x1bdb5d  ldloc.1
0x1bdb5e  callvirt instance class System.Windows.Data.BindingExpressionBase System.Windows.FrameworkElement::SetBinding(class [WindowsBase]System.Windows.DependencyProperty dp, class System.Windows.Data.BindingBase binding)
0x1bdb63  pop
0x1bdb64  ldarg.0
0x1bdb65  ldarg.1
0x1bdb66  callvirt instance void System.Windows.Controls.Primitives.Popup::set_Child(class [PresentationCore]System.Windows.UIElement value)
0x1bdb6b  ldstr    aVerticaloffset// "VerticalOffset"
0x1bdb70  newobj   instance void System.Windows.Data.Binding::.ctor(string path)
0x1bdb75  stloc.1
0x1bdb76  ldloc.1
0x1bdb77  ldc.i4.1
0x1bdb78  callvirt instance void System.Windows.Data.Binding::set_Mode(valuetype System.Windows.Data.BindingMode value)
0x1bdb7d  ldloc.1
0x1bdb7e  ldarg.1
0x1bdb7f  callvirt instance void System.Windows.Data.Binding::set_Source(object value)
0x1bdb84  ldarg.0
0x1bdb85  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.Popup::VerticalOffsetProperty
0x1bdb8a  ldloc.1
0x1bdb8b  callvirt instance class System.Windows.Data.BindingExpressionBase System.Windows.FrameworkElement::SetBinding(class [WindowsBase]System.Windows.DependencyProperty dp, class System.Windows.Data.BindingBase binding)
0x1bdb90  pop
0x1bdb91  ldstr    aHorizontaloffs// "HorizontalOffset"
0x1bdb96  newobj   instance void System.Windows.Data.Binding::.ctor(string path)
0x1bdb9b  stloc.1
0x1bdb9c  ldloc.1
0x1bdb9d  ldc.i4.1
0x1bdb9e  callvirt instance void System.Windows.Data.Binding::set_Mode(valuetype System.Windows.Data.BindingMode value)
0x1bdba3  ldloc.1
0x1bdba4  ldarg.1
0x1bdba5  callvirt instance void System.Windows.Data.Binding::set_Source(object value)
0x1bdbaa  ldarg.0
0x1bdbab  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.Popup::HorizontalOffsetProperty
0x1bdbb0  ldloc.1
0x1bdbb1  callvirt instance class System.Windows.Data.BindingExpressionBase System.Windows.FrameworkElement::SetBinding(class [WindowsBase]System.Windows.DependencyProperty dp, class System.Windows.Data.BindingBase binding)
0x1bdbb6  pop
0x1bdbb7  ldstr    aPlacementrecta// "PlacementRectangle"
0x1bdbbc  newobj   instance void System.Windows.Data.Binding::.ctor(string path)
0x1bdbc1  stloc.1
0x1bdbc2  ldloc.1
0x1bdbc3  ldc.i4.1
0x1bdbc4  callvirt instance void System.Windows.Data.Binding::set_Mode(valuetype System.Windows.Data.BindingMode value)
0x1bdbc9  ldloc.1
0x1bdbca  ldarg.1
0x1bdbcb  callvirt instance void System.Windows.Data.Binding::set_Source(object value)
0x1bdbd0  ldarg.0
0x1bdbd1  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.Popup::PlacementRectangleProperty
0x1bdbd6  ldloc.1
0x1bdbd7  callvirt instance class System.Windows.Data.BindingExpressionBase System.Windows.FrameworkElement::SetBinding(class [WindowsBase]System.Windows.DependencyProperty dp, class System.Windows.Data.BindingBase binding)
0x1bdbdc  pop
0x1bdbdd  ldstr    aPlacement// "Placement"
0x1bdbe2  newobj   instance void System.Windows.Data.Binding::.ctor(string path)
0x1bdbe7  stloc.1
0x1bdbe8  ldloc.1
0x1bdbe9  ldc.i4.1
0x1bdbea  callvirt instance void System.Windows.Data.Binding::set_Mode(valuetype System.Windows.Data.BindingMode value)
0x1bdbef  ldloc.1
0x1bdbf0  ldarg.1
0x1bdbf1  callvirt instance void System.Windows.Data.Binding::set_Source(object value)
0x1bdbf6  ldarg.0
0x1bdbf7  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.Popup::PlacementProperty
0x1bdbfc  ldloc.1
0x1bdbfd  callvirt instance class System.Windows.Data.BindingExpressionBase System.Windows.FrameworkElement::SetBinding(class [WindowsBase]System.Windows.DependencyProperty dp, class System.Windows.Data.BindingBase binding)
0x1bdc02  pop
0x1bdc03  ldstr    aStaysopen// "StaysOpen"
0x1bdc08  newobj   instance void System.Windows.Data.Binding::.ctor(string path)
0x1bdc0d  stloc.1
0x1bdc0e  ldloc.1
0x1bdc0f  ldc.i4.1
0x1bdc10  callvirt instance void System.Windows.Data.Binding::set_Mode(valuetype System.Windows.Data.BindingMode value)
0x1bdc15  ldloc.1
0x1bdc16  ldarg.1
0x1bdc17  callvirt instance void System.Windows.Data.Binding::set_Source(object value)
0x1bdc1c  ldarg.0
0x1bdc1d  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.Popup::StaysOpenProperty
0x1bdc22  ldloc.1
0x1bdc23  callvirt instance class System.Windows.Data.BindingExpressionBase System.Windows.FrameworkElement::SetBinding(class [WindowsBase]System.Windows.DependencyProperty dp, class System.Windows.Data.BindingBase binding)
0x1bdc28  pop
0x1bdc29  ldstr    aCustompopuppla// "CustomPopupPlacementCallback"
0x1bdc2e  newobj   instance void System.Windows.Data.Binding::.ctor(string path)
0x1bdc33  stloc.1
0x1bdc34  ldloc.1
0x1bdc35  ldc.i4.1
0x1bdc36  callvirt instance void System.Windows.Data.Binding::set_Mode(valuetype System.Windows.Data.BindingMode value)
0x1bdc3b  ldloc.1
0x1bdc3c  ldarg.1
0x1bdc3d  callvirt instance void System.Windows.Data.Binding::set_Source(object value)
0x1bdc42  ldarg.0
0x1bdc43  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.Popup::CustomPopupPlacementCallbackProperty
0x1bdc48  ldloc.1
0x1bdc49  callvirt instance class System.Windows.Data.BindingExpressionBase System.Windows.FrameworkElement::SetBinding(class [WindowsBase]System.Windows.DependencyProperty dp, class System.Windows.Data.BindingBase binding)
0x1bdc4e  pop
0x1bdc4f  ldarg.2
0x1bdc50  brfalse.s loc_1BDC78
0x1bdc52  ldstr    aFromkeyboard// "FromKeyboard"
0x1bdc57  newobj   instance void System.Windows.Data.Binding::.ctor(string path)
0x1bdc5c  stloc.1
0x1bdc5d  ldloc.1
0x1bdc5e  ldc.i4.1
0x1bdc5f  callvirt instance void System.Windows.Data.Binding::set_Mode(valuetype System.Windows.Data.BindingMode value)
0x1bdc64  ldloc.1
0x1bdc65  ldarg.1
0x1bdc66  callvirt instance void System.Windows.Data.Binding::set_Source(object value)
0x1bdc6b  ldarg.0
0x1bdc6c  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.Popup::TreatMousePlacementAsBottomProperty
0x1bdc71  ldloc.1
0x1bdc72  callvirt instance class System.Windows.Data.BindingExpressionBase System.Windows.FrameworkElement::SetBinding(class [WindowsBase]System.Windows.DependencyProperty dp, class System.Windows.Data.BindingBase binding)
0x1bdc77  pop
0x1bdc78  ldstr    aIsopen// "IsOpen"
0x1bdc7d  newobj   instance void System.Windows.Data.Binding::.ctor(string path)
0x1bdc82  stloc.1
0x1bdc83  ldloc.1
0x1bdc84  ldc.i4.1
0x1bdc85  callvirt instance void System.Windows.Data.Binding::set_Mode(valuetype System.Windows.Data.BindingMode value)
0x1bdc8a  ldloc.1
0x1bdc8b  ldarg.1
0x1bdc8c  callvirt instance void System.Windows.Data.Binding::set_Source(object value)
0x1bdc91  ldarg.0
0x1bdc92  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.Popup::IsOpenProperty
0x1bdc97  ldloc.1
0x1bdc98  callvirt instance class System.Windows.Data.BindingExpressionBase System.Windows.FrameworkElement::SetBinding(class [WindowsBase]System.Windows.DependencyProperty dp, class System.Windows.Data.BindingBase binding)
0x1bdc9d  pop
0x1bdc9e  ret
```
