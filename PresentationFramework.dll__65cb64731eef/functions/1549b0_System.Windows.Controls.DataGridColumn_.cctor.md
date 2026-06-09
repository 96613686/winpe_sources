# System.Windows.Controls.DataGridColumn::.cctor

- ea: `0x1549b0`
- end: `0x154f4d`
- name: `System.Windows.Controls.DataGridColumn::.cctor`
- size: `1437`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x159e0`
- `0x159f0`
- `0x15a20`
- `0x15a30`
- `0x159960`

## string_xrefs

- `0x154a5b`: `HeaderTemplate`
- `0x154a90`: `HeaderTemplateSelector`
- `0x154b06`: `IsReadOnly`
- `0x154d0b`: `SortMemberPath`

## pseudocode

```c

```

## disassembly

```asm
0x1549b0  ldstr    aHeader// "Header"
0x1549b5  ldtoken  [mscorlib]System.Object
0x1549ba  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1549bf  ldtoken  System.Windows.Controls.DataGridColumn
0x1549c4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1549c9  ldnull
0x1549ca  ldnull
0x1549cb  ldftn    void System.Windows.Controls.DataGridColumn::OnNotifyColumnHeaderPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x1549d1  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x1549d6  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x1549db  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1549e0  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridColumn::HeaderProperty
0x1549e5  ldstr    aHeaderstyle// "HeaderStyle"
0x1549ea  ldtoken  System.Windows.Style
0x1549ef  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1549f4  ldtoken  System.Windows.Controls.DataGridColumn
0x1549f9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1549fe  ldnull
0x1549ff  ldnull
0x154a00  ldftn    void System.Windows.Controls.DataGridColumn::OnNotifyColumnHeaderPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x154a06  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x154a0b  ldnull
0x154a0c  ldftn    object System.Windows.Controls.DataGridColumn::OnCoerceHeaderStyle(class [WindowsBase]System.Windows.DependencyObject d, object baseValue)
0x154a12  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x154a17  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x154a1c  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x154a21  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridColumn::HeaderStyleProperty
0x154a26  ldstr    aHeaderstringfo// "HeaderStringFormat"
0x154a2b  ldtoken  [mscorlib]System.String
0x154a30  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154a35  ldtoken  System.Windows.Controls.DataGridColumn
0x154a3a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154a3f  ldnull
0x154a40  ldnull
0x154a41  ldftn    void System.Windows.Controls.DataGridColumn::OnNotifyColumnHeaderPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x154a47  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x154a4c  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x154a51  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x154a56  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridColumn::HeaderStringFormatProperty
0x154a5b  ldstr    aHeadertemplate// "HeaderTemplate"
0x154a60  ldtoken  System.Windows.DataTemplate
0x154a65  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154a6a  ldtoken  System.Windows.Controls.DataGridColumn
0x154a6f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154a74  ldnull
0x154a75  ldnull
0x154a76  ldftn    void System.Windows.Controls.DataGridColumn::OnNotifyColumnHeaderPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x154a7c  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x154a81  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x154a86  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x154a8b  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridColumn::HeaderTemplateProperty
0x154a90  ldstr    aHeadertemplate_0// "HeaderTemplateSelector"
0x154a95  ldtoken  System.Windows.Controls.DataTemplateSelector
0x154a9a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154a9f  ldtoken  System.Windows.Controls.DataGridColumn
0x154aa4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154aa9  ldnull
0x154aaa  ldnull
0x154aab  ldftn    void System.Windows.Controls.DataGridColumn::OnNotifyColumnHeaderPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x154ab1  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x154ab6  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x154abb  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x154ac0  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridColumn::HeaderTemplateSelectorProperty
0x154ac5  ldstr    aCellstyle// "CellStyle"
0x154aca  ldtoken  System.Windows.Style
0x154acf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154ad4  ldtoken  System.Windows.Controls.DataGridColumn
0x154ad9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154ade  ldnull
0x154adf  ldnull
0x154ae0  ldftn    void System.Windows.Controls.DataGridColumn::OnNotifyCellPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x154ae6  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x154aeb  ldnull
0x154aec  ldftn    object System.Windows.Controls.DataGridColumn::OnCoerceCellStyle(class [WindowsBase]System.Windows.DependencyObject d, object baseValue)
0x154af2  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x154af7  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x154afc  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x154b01  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridColumn::CellStyleProperty
0x154b06  ldstr    aIsreadonly// "IsReadOnly"
0x154b0b  ldtoken  [mscorlib]System.Boolean
0x154b10  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154b15  ldtoken  System.Windows.Controls.DataGridColumn
0x154b1a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154b1f  ldc.i4.0
0x154b20  box      [mscorlib]System.Boolean
0x154b25  ldnull
0x154b26  ldftn    void System.Windows.Controls.DataGridColumn::OnNotifyCellPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x154b2c  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x154b31  ldnull
0x154b32  ldftn    object System.Windows.Controls.DataGridColumn::OnCoerceIsReadOnly(class [WindowsBase]System.Windows.DependencyObject d, object baseValue)
0x154b38  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x154b3d  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x154b42  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x154b47  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridColumn::IsReadOnlyProperty
0x154b4c  ldstr    aWidth// "Width"
0x154b51  ldtoken  System.Windows.Controls.DataGridLength
0x154b56  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154b5b  ldtoken  System.Windows.Controls.DataGridColumn
0x154b60  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154b65  call     valuetype System.Windows.Controls.DataGridLength System.Windows.Controls.DataGridLength::get_Auto()
0x154b6a  box      System.Windows.Controls.DataGridLength
0x154b6f  ldnull
0x154b70  ldftn    void System.Windows.Controls.DataGridColumn::OnWidthPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x154b76  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x154b7b  ldnull
0x154b7c  ldftn    object System.Windows.Controls.DataGridColumn::OnCoerceWidth(class [WindowsBase]System.Windows.DependencyObject d, object baseValue)
0x154b82  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x154b87  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x154b8c  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x154b91  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridColumn::WidthProperty
0x154b96  ldstr    aMinwidth// "MinWidth"
0x154b9b  ldtoken  [mscorlib]System.Double
0x154ba0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154ba5  ldtoken  System.Windows.Controls.DataGridColumn
0x154baa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154baf  ldc.r8   20.0
0x154bb8  box      [mscorlib]System.Double
0x154bbd  ldnull
0x154bbe  ldftn    void System.Windows.Controls.DataGridColumn::OnMinWidthPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x154bc4  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x154bc9  ldnull
0x154bca  ldftn    object System.Windows.Controls.DataGridColumn::OnCoerceMinWidth(class [WindowsBase]System.Windows.DependencyObject d, object baseValue)
0x154bd0  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x154bd5  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x154bda  ldnull
0x154bdb  ldftn    bool System.Windows.Controls.DataGridColumn::ValidateMinWidth(object v)
0x154be1  newobj   instance void [WindowsBase]System.Windows.ValidateValueCallback::.ctor(object, native int)
0x154be6  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata, class [WindowsBase]System.Windows.ValidateValueCallback)
0x154beb  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridColumn::MinWidthProperty
0x154bf0  ldstr    aMaxwidth// "MaxWidth"
0x154bf5  ldtoken  [mscorlib]System.Double
0x154bfa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154bff  ldtoken  System.Windows.Controls.DataGridColumn
0x154c04  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154c09  ldc.r8   +Inf
0x154c12  box      [mscorlib]System.Double
0x154c17  ldnull
0x154c18  ldftn    void System.Windows.Controls.DataGridColumn::OnMaxWidthPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x154c1e  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x154c23  ldnull
0x154c24  ldftn    object System.Windows.Controls.DataGridColumn::OnCoerceMaxWidth(class [WindowsBase]System.Windows.DependencyObject d, object baseValue)
0x154c2a  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x154c2f  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x154c34  ldnull
0x154c35  ldftn    bool System.Windows.Controls.DataGridColumn::ValidateMaxWidth(object v)
0x154c3b  newobj   instance void [WindowsBase]System.Windows.ValidateValueCallback::.ctor(object, native int)
0x154c40  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata, class [WindowsBase]System.Windows.ValidateValueCallback)
0x154c45  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridColumn::MaxWidthProperty
0x154c4a  ldstr    aActualwidth// "ActualWidth"
0x154c4f  ldtoken  [mscorlib]System.Double
0x154c54  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154c59  ldtoken  System.Windows.Controls.DataGridColumn
0x154c5e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154c63  ldc.r8   0.0
0x154c6c  box      [mscorlib]System.Double
0x154c71  ldnull
0x154c72  ldnull
0x154c73  ldftn    object System.Windows.Controls.DataGridColumn::OnCoerceActualWidth(class [WindowsBase]System.Windows.DependencyObject d, object baseValue)
0x154c79  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x154c7e  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x154c83  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x154c88  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.DataGridColumn::ActualWidthPropertyKey
0x154c8d  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.DataGridColumn::ActualWidthPropertyKey
0x154c92  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x154c97  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridColumn::ActualWidthProperty
0x154c9c  ldstr    aOriginalvalue// "OriginalValue"
0x154ca1  ldtoken  [mscorlib]System.Object
0x154ca6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154cab  ldtoken  System.Windows.Controls.DataGridColumn
0x154cb0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154cb5  ldnull
0x154cb6  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x154cbb  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x154cc0  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridColumn::OriginalValueProperty
0x154cc5  ldstr    aDisplayindex_0// "DisplayIndex"
0x154cca  ldtoken  [mscorlib]System.Int32
0x154ccf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154cd4  ldtoken  System.Windows.Controls.DataGridColumn
0x154cd9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154cde  ldc.i4.m1
0x154cdf  box      [mscorlib]System.Int32
0x154ce4  ldnull
0x154ce5  ldftn    void System.Windows.Controls.DataGridColumn::DisplayIndexChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x154ceb  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x154cf0  ldnull
0x154cf1  ldftn    object System.Windows.Controls.DataGridColumn::OnCoerceDisplayIndex(class [WindowsBase]System.Windows.DependencyObject d, object baseValue)
0x154cf7  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x154cfc  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x154d01  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x154d06  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridColumn::DisplayIndexProperty
0x154d0b  ldstr    aSortmemberpath// "SortMemberPath"
0x154d10  ldtoken  [mscorlib]System.String
0x154d15  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154d1a  ldtoken  System.Windows.Controls.DataGridColumn
0x154d1f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154d24  ldsfld   string [mscorlib]System.String::Empty
0x154d29  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x154d2e  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x154d33  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridColumn::SortMemberPathProperty
0x154d38  ldstr    aCanusersort// "CanUserSort"
0x154d3d  ldtoken  [mscorlib]System.Boolean
0x154d42  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154d47  ldtoken  System.Windows.Controls.DataGridColumn
0x154d4c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154d51  ldc.i4.1
0x154d52  box      [mscorlib]System.Boolean
0x154d57  ldnull
0x154d58  ldftn    void System.Windows.Controls.DataGridColumn::OnCanUserSortPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x154d5e  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x154d63  ldnull
0x154d64  ldftn    object System.Windows.Controls.DataGridColumn::OnCoerceCanUserSort(class [WindowsBase]System.Windows.DependencyObject d, object baseValue)
0x154d6a  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x154d6f  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x154d74  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x154d79  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridColumn::CanUserSortProperty
0x154d7e  ldstr    aSortdirection// "SortDirection"
0x154d83  ldtoken  valuetype [mscorlib]System.Nullable`1<valuetype [System]System.ComponentModel.ListSortDirection>
0x154d88  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154d8d  ldtoken  System.Windows.Controls.DataGridColumn
0x154d92  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154d97  ldnull
0x154d98  ldnull
0x154d99  ldftn    void System.Windows.Controls.DataGridColumn::OnNotifySortPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x154d9f  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x154da4  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x154da9  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x154dae  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridColumn::SortDirectionProperty
0x154db3  ldstr    aIsautogenerate// "IsAutoGenerated"
0x154db8  ldtoken  [mscorlib]System.Boolean
0x154dbd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154dc2  ldtoken  System.Windows.Controls.DataGridColumn
0x154dc7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154dcc  ldc.i4.0
0x154dcd  box      [mscorlib]System.Boolean
0x154dd2  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x154dd7  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x154ddc  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.DataGridColumn::IsAutoGeneratedPropertyKey
0x154de1  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.DataGridColumn::IsAutoGeneratedPropertyKey
0x154de6  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x154deb  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridColumn::IsAutoGeneratedProperty
0x154df0  ldstr    aIsfrozen// "IsFrozen"
0x154df5  ldtoken  [mscorlib]System.Boolean
0x154dfa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154dff  ldtoken  System.Windows.Controls.DataGridColumn
0x154e04  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154e09  ldc.i4.0
0x154e0a  box      [mscorlib]System.Boolean
0x154e0f  ldnull
0x154e10  ldftn    void System.Windows.Controls.DataGridColumn::OnNotifyFrozenPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x154e16  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x154e1b  ldnull
0x154e1c  ldftn    object System.Windows.Controls.DataGridColumn::OnCoerceIsFrozen(class [WindowsBase]System.Windows.DependencyObject d, object baseValue)
0x154e22  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x154e27  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x154e2c  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x154e31  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.DataGridColumn::IsFrozenPropertyKey
0x154e36  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.DataGridColumn::IsFrozenPropertyKey
0x154e3b  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x154e40  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridColumn::IsFrozenProperty
0x154e45  ldstr    aCanuserreorder_0// "CanUserReorder"
0x154e4a  ldtoken  [mscorlib]System.Boolean
0x154e4f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154e54  ldtoken  System.Windows.Controls.DataGridColumn
0x154e59  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154e5e  ldc.i4.1
0x154e5f  box      [mscorlib]System.Boolean
0x154e64  ldnull
0x154e65  ldftn    void System.Windows.Controls.DataGridColumn::OnNotifyColumnPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x154e6b  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x154e70  ldnull
0x154e71  ldftn    object System.Windows.Controls.DataGridColumn::OnCoerceCanUserReorder(class [WindowsBase]System.Windows.DependencyObject d, object baseValue)
0x154e77  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x154e7c  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x154e81  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x154e86  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridColumn::CanUserReorderProperty
0x154e8b  ldstr    aDragindicators// "DragIndicatorStyle"
0x154e90  ldtoken  System.Windows.Style
0x154e95  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154e9a  ldtoken  System.Windows.Controls.DataGridColumn
0x154e9f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154ea4  ldnull
0x154ea5  ldnull
0x154ea6  ldftn    void System.Windows.Controls.DataGridColumn::OnNotifyColumnPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x154eac  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x154eb1  ldnull
0x154eb2  ldftn    object System.Windows.Controls.DataGridColumn::OnCoerceDragIndicatorStyle(class [WindowsBase]System.Windows.DependencyObject d, object baseValue)
0x154eb8  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x154ebd  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x154ec2  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x154ec7  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.DataGridColumn::DragIndicatorStyleProperty
0x154ecc  ldstr    aCanuserresize// "CanUserResize"
0x154ed1  ldtoken  [mscorlib]System.Boolean
0x154ed6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154edb  ldtoken  System.Windows.Controls.DataGridColumn
0x154ee0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x154ee5  ldc.i4.1
0x154ee6  box      [mscorlib]System.Boolean
0x154eeb  ldnull
0x154eec  ldftn    void System.Windows.Controls.DataGridColumn::OnNotifyColumnHeaderPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x154ef2  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
  ... truncated ...
```
