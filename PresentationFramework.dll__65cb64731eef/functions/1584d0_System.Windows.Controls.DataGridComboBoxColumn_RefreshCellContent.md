# System.Windows.Controls.DataGridComboBoxColumn::RefreshCellContent

- ea: `0x1584d0`
- end: `0x1585e9`
- name: `System.Windows.Controls.DataGridComboBoxColumn::RefreshCellContent`
- size: `281`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x143550`
- `0x14fd60`
- `0x14fe50`
- `0x154200`
- `0x158180`
- `0x1581f0`
- `0x158240`
- `0x1583f0`
- `0x1584d0`
- `0x159090`

## string_xrefs

- `0x158543`: `SelectedValuePath`
- `0x158550`: `DisplayMemberPath`

## pseudocode

```c

```

## disassembly

```asm
0x1584d0  ldarg.1
0x1584d1  isinst   System.Windows.Controls.DataGridCell
0x1584d6  stloc.0
0x1584d7  ldloc.0
0x1584d8  brfalse  loc_1585E0
0x1584dd  ldloc.0
0x1584de  callvirt instance bool System.Windows.Controls.DataGridCell::get_IsEditing()
0x1584e3  stloc.1
0x1584e4  ldarg.2
0x1584e5  ldstr    aElementstyle// "ElementStyle"
0x1584ea  ldc.i4.4
0x1584eb  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x1584f0  brtrue.s loc_1584F5
0x1584f2  ldloc.1
0x1584f3  brfalse.s loc_158508
0x1584f5  ldarg.2
0x1584f6  ldstr    aEditingelement// "EditingElementStyle"
0x1584fb  ldc.i4.4
0x1584fc  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x158501  ldc.i4.0
0x158502  ceq
0x158504  ldloc.1
0x158505  and
0x158506  brfalse.s loc_15850F
0x158508  ldloc.0
0x158509  callvirt instance void System.Windows.Controls.DataGridCell::BuildVisualTree()
0x15850e  ret
0x15850f  ldloc.0
0x158510  callvirt instance object System.Windows.Controls.ContentControl::get_Content()
0x158515  isinst   System.Windows.Controls.ComboBox
0x15851a  stloc.2
0x15851b  ldarg.2
0x15851c  ldstr    aSelecteditembi// "SelectedItemBinding"
0x158521  call     bool [mscorlib]System.String::op_Equality(string, string)
0x158526  brtrue.s loc_15856B
0x158528  ldarg.2
0x158529  ldstr    aSelectedvalueb// "SelectedValueBinding"
0x15852e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x158533  brtrue.s loc_15857D
0x158535  ldarg.2
0x158536  ldstr    aTextbinding// "TextBinding"
0x15853b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x158540  brtrue.s loc_15858F
0x158542  ldarg.2
0x158543  ldstr    aSelectedvaluep// "SelectedValuePath"
0x158548  call     bool [mscorlib]System.String::op_Equality(string, string)
0x15854d  brtrue.s loc_1585A1
0x15854f  ldarg.2
0x158550  ldstr    aDisplaymemberp// "DisplayMemberPath"
0x158555  call     bool [mscorlib]System.String::op_Equality(string, string)
0x15855a  brtrue.s loc_1585B3
0x15855c  ldarg.2
0x15855d  ldstr    aItemssource// "ItemsSource"
0x158562  call     bool [mscorlib]System.String::op_Equality(string, string)
0x158567  brtrue.s loc_1585C5
0x158569  br.s     loc_1585D7
0x15856b  ldarg.0
0x15856c  callvirt instance class System.Windows.Data.BindingBase System.Windows.Controls.DataGridComboBoxColumn::get_SelectedItemBinding()
0x158571  ldloc.2
0x158572  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.Selector::SelectedItemProperty
0x158577  call     void System.Windows.Controls.DataGridComboBoxColumn::ApplyBinding(class System.Windows.Data.BindingBase binding, class [WindowsBase]System.Windows.DependencyObject target, class [WindowsBase]System.Windows.DependencyProperty property)
0x15857c  ret
0x15857d  ldarg.0
0x15857e  callvirt instance class System.Windows.Data.BindingBase System.Windows.Controls.DataGridComboBoxColumn::get_SelectedValueBinding()
0x158583  ldloc.2
0x158584  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.Selector::SelectedValueProperty
0x158589  call     void System.Windows.Controls.DataGridComboBoxColumn::ApplyBinding(class System.Windows.Data.BindingBase binding, class [WindowsBase]System.Windows.DependencyObject target, class [WindowsBase]System.Windows.DependencyProperty property)
0x15858e  ret
0x15858f  ldarg.0
0x158590  callvirt instance class System.Windows.Data.BindingBase System.Windows.Controls.DataGridComboBoxColumn::get_TextBinding()
0x158595  ldloc.2
0x158596  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ComboBox::TextProperty
0x15859b  call     void System.Windows.Controls.DataGridComboBoxColumn::ApplyBinding(class System.Windows.Data.BindingBase binding, class [WindowsBase]System.Windows.DependencyObject target, class [WindowsBase]System.Windows.DependencyProperty property)
0x1585a0  ret
0x1585a1  ldarg.0
0x1585a2  ldloc.2
0x1585a3  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Primitives.Selector::SelectedValuePathProperty
0x1585a8  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridComboBoxColumn::SelectedValuePathProperty
0x1585ad  call     void System.Windows.Controls.DataGridHelper::SyncColumnProperty(class [WindowsBase]System.Windows.DependencyObject column, class [WindowsBase]System.Windows.DependencyObject content, class [WindowsBase]System.Windows.DependencyProperty contentProperty, class [WindowsBase]System.Windows.DependencyProperty columnProperty)
0x1585b2  ret
0x1585b3  ldarg.0
0x1585b4  ldloc.2
0x1585b5  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ItemsControl::DisplayMemberPathProperty
0x1585ba  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridComboBoxColumn::DisplayMemberPathProperty
0x1585bf  call     void System.Windows.Controls.DataGridHelper::SyncColumnProperty(class [WindowsBase]System.Windows.DependencyObject column, class [WindowsBase]System.Windows.DependencyObject content, class [WindowsBase]System.Windows.DependencyProperty contentProperty, class [WindowsBase]System.Windows.DependencyProperty columnProperty)
0x1585c4  ret
0x1585c5  ldarg.0
0x1585c6  ldloc.2
0x1585c7  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ItemsControl::ItemsSourceProperty
0x1585cc  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridComboBoxColumn::ItemsSourceProperty
0x1585d1  call     void System.Windows.Controls.DataGridHelper::SyncColumnProperty(class [WindowsBase]System.Windows.DependencyObject column, class [WindowsBase]System.Windows.DependencyObject content, class [WindowsBase]System.Windows.DependencyProperty contentProperty, class [WindowsBase]System.Windows.DependencyProperty columnProperty)
0x1585d6  ret
0x1585d7  ldarg.0
0x1585d8  ldarg.1
0x1585d9  ldarg.2
0x1585da  call     instance void System.Windows.Controls.DataGridColumn::RefreshCellContent(class System.Windows.FrameworkElement element, string propertyName)
0x1585df  ret
0x1585e0  ldarg.0
0x1585e1  ldarg.1
0x1585e2  ldarg.2
0x1585e3  call     instance void System.Windows.Controls.DataGridColumn::RefreshCellContent(class System.Windows.FrameworkElement element, string propertyName)
0x1585e8  ret
```
