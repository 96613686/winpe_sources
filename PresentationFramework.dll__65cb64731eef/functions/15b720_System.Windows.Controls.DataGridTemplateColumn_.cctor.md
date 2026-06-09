# System.Windows.Controls.DataGridTemplateColumn::.cctor

- ea: `0x15b720`
- end: `0x15b840`
- name: `System.Windows.Controls.DataGridTemplateColumn::.cctor`
- size: `288`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x159f0`
- `0x15a00`
- `0x15a20`

## string_xrefs

- `0x15b720`: `CellTemplate`
- `0x15b755`: `CellTemplateSelector`
- `0x15b78a`: `CellEditingTemplate`
- `0x15b7bf`: `CellEditingTemplateSelector`

## pseudocode

```c

```

## disassembly

```asm
0x15b720  ldstr    aCelltemplate// "CellTemplate"
0x15b725  ldtoken  System.Windows.DataTemplate
0x15b72a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15b72f  ldtoken  System.Windows.Controls.DataGridTemplateColumn
0x15b734  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15b739  ldnull
0x15b73a  ldnull
0x15b73b  ldftn    void System.Windows.Controls.DataGridColumn::NotifyPropertyChangeForRefreshContent(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x15b741  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x15b746  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x15b74b  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x15b750  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridTemplateColumn::CellTemplateProperty
0x15b755  ldstr    aCelltemplatese// "CellTemplateSelector"
0x15b75a  ldtoken  System.Windows.Controls.DataTemplateSelector
0x15b75f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15b764  ldtoken  System.Windows.Controls.DataGridTemplateColumn
0x15b769  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15b76e  ldnull
0x15b76f  ldnull
0x15b770  ldftn    void System.Windows.Controls.DataGridColumn::NotifyPropertyChangeForRefreshContent(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x15b776  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x15b77b  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x15b780  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x15b785  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridTemplateColumn::CellTemplateSelectorProperty
0x15b78a  ldstr    aCelleditingtem// "CellEditingTemplate"
0x15b78f  ldtoken  System.Windows.DataTemplate
0x15b794  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15b799  ldtoken  System.Windows.Controls.DataGridTemplateColumn
0x15b79e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15b7a3  ldnull
0x15b7a4  ldnull
0x15b7a5  ldftn    void System.Windows.Controls.DataGridColumn::NotifyPropertyChangeForRefreshContent(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x15b7ab  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x15b7b0  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x15b7b5  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x15b7ba  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridTemplateColumn::CellEditingTemplateProperty
0x15b7bf  ldstr    aCelleditingtem_0// "CellEditingTemplateSelector"
0x15b7c4  ldtoken  System.Windows.Controls.DataTemplateSelector
0x15b7c9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15b7ce  ldtoken  System.Windows.Controls.DataGridTemplateColumn
0x15b7d3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15b7d8  ldnull
0x15b7d9  ldnull
0x15b7da  ldftn    void System.Windows.Controls.DataGridColumn::NotifyPropertyChangeForRefreshContent(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x15b7e0  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x15b7e5  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x15b7ea  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x15b7ef  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridTemplateColumn::CellEditingTemplateSelectorProperty
0x15b7f4  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridColumn::CanUserSortProperty
0x15b7f9  ldtoken  System.Windows.Controls.DataGridTemplateColumn
0x15b7fe  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15b803  ldnull
0x15b804  ldnull
0x15b805  ldftn    object System.Windows.Controls.DataGridTemplateColumn::OnCoerceTemplateColumnCanUserSort(class [WindowsBase]System.Windows.DependencyObject d, object baseValue)
0x15b80b  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x15b810  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x15b815  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x15b81a  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridColumn::SortMemberPathProperty
0x15b81f  ldtoken  System.Windows.Controls.DataGridTemplateColumn
0x15b824  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15b829  ldnull
0x15b82a  ldftn    void System.Windows.Controls.DataGridTemplateColumn::OnTemplateColumnSortMemberPathChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x15b830  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x15b835  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x15b83a  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x15b83f  ret
```
