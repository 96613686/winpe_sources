# System.Windows.Controls.GridViewColumn::.cctor

- ea: `0x16a4c0`
- end: `0x16a666`
- name: `System.Windows.Controls.GridViewColumn::.cctor`
- size: `422`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x159f0`
- `0x15a20`

## string_xrefs

- `0x16a528`: `HeaderTemplate`
- `0x16a55c`: `HeaderTemplateSelector`
- `0x16a5c5`: `CellTemplate`
- `0x16a5f9`: `CellTemplateSelector`

## pseudocode

```c

```

## disassembly

```asm
0x16a4c0  ldstr    aHeader// "Header"
0x16a4c5  ldtoken  [mscorlib]System.Object
0x16a4ca  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16a4cf  ldtoken  System.Windows.Controls.GridViewColumn
0x16a4d4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16a4d9  ldnull
0x16a4da  ldftn    void System.Windows.Controls.GridViewColumn::OnHeaderChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x16a4e0  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x16a4e5  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x16a4ea  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x16a4ef  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.GridViewColumn::HeaderProperty
0x16a4f4  ldstr    aHeadercontaine// "HeaderContainerStyle"
0x16a4f9  ldtoken  System.Windows.Style
0x16a4fe  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16a503  ldtoken  System.Windows.Controls.GridViewColumn
0x16a508  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16a50d  ldnull
0x16a50e  ldftn    void System.Windows.Controls.GridViewColumn::OnHeaderContainerStyleChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x16a514  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x16a519  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x16a51e  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x16a523  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.GridViewColumn::HeaderContainerStyleProperty
0x16a528  ldstr    aHeadertemplate// "HeaderTemplate"
0x16a52d  ldtoken  System.Windows.DataTemplate
0x16a532  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16a537  ldtoken  System.Windows.Controls.GridViewColumn
0x16a53c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16a541  ldnull
0x16a542  ldftn    void System.Windows.Controls.GridViewColumn::OnHeaderTemplateChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x16a548  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x16a54d  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x16a552  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x16a557  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.GridViewColumn::HeaderTemplateProperty
0x16a55c  ldstr    aHeadertemplate_0// "HeaderTemplateSelector"
0x16a561  ldtoken  System.Windows.Controls.DataTemplateSelector
0x16a566  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16a56b  ldtoken  System.Windows.Controls.GridViewColumn
0x16a570  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16a575  ldnull
0x16a576  ldftn    void System.Windows.Controls.GridViewColumn::OnHeaderTemplateSelectorChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x16a57c  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x16a581  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x16a586  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x16a58b  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.GridViewColumn::HeaderTemplateSelectorProperty
0x16a590  ldstr    aHeaderstringfo// "HeaderStringFormat"
0x16a595  ldtoken  [mscorlib]System.String
0x16a59a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16a59f  ldtoken  System.Windows.Controls.GridViewColumn
0x16a5a4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16a5a9  ldnull
0x16a5aa  ldnull
0x16a5ab  ldftn    void System.Windows.Controls.GridViewColumn::OnHeaderStringFormatChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x16a5b1  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x16a5b6  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x16a5bb  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x16a5c0  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.GridViewColumn::HeaderStringFormatProperty
0x16a5c5  ldstr    aCelltemplate// "CellTemplate"
0x16a5ca  ldtoken  System.Windows.DataTemplate
0x16a5cf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16a5d4  ldtoken  System.Windows.Controls.GridViewColumn
0x16a5d9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16a5de  ldnull
0x16a5df  ldftn    void System.Windows.Controls.GridViewColumn::OnCellTemplateChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x16a5e5  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x16a5ea  newobj   instance void [WindowsBase]System.Windows.PropertyMetadata::.ctor(class [WindowsBase]System.Windows.PropertyChangedCallback)
0x16a5ef  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x16a5f4  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.GridViewColumn::CellTemplateProperty
0x16a5f9  ldstr    aCelltemplatese// "CellTemplateSelector"
0x16a5fe  ldtoken  System.Windows.Controls.DataTemplateSelector
0x16a603  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16a608  ldtoken  System.Windows.Controls.GridViewColumn
0x16a60d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16a612  ldnull
0x16a613  ldftn    void System.Windows.Controls.GridViewColumn::OnCellTemplateSelectorChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x16a619  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x16a61e  newobj   instance void [WindowsBase]System.Windows.PropertyMetadata::.ctor(class [WindowsBase]System.Windows.PropertyChangedCallback)
0x16a623  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x16a628  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.GridViewColumn::CellTemplateSelectorProperty
0x16a62d  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.FrameworkElement::WidthProperty
0x16a632  ldtoken  System.Windows.Controls.GridViewColumn
0x16a637  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16a63c  ldc.r8   NaN
0x16a645  box      [mscorlib]System.Double
0x16a64a  ldnull
0x16a64b  ldftn    void System.Windows.Controls.GridViewColumn::OnWidthChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x16a651  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x16a656  newobj   instance void [WindowsBase]System.Windows.PropertyMetadata::.ctor(object, class [WindowsBase]System.Windows.PropertyChangedCallback)
0x16a65b  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::AddOwner(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x16a660  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.GridViewColumn::WidthProperty
0x16a665  ret
```
