# System.Windows.Controls.VirtualizingPanel::.cctor

- ea: `0x1a0e80`
- end: `0x1a1064`
- name: `System.Windows.Controls.VirtualizingPanel::.cctor`
- size: `484`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x159e0`
- `0x15a50`
- `0x15a60`
- `0x186490`

## string_xrefs

- `0x1a0f78`: `CacheLength`
- `0x1a0fcc`: `CacheLengthUnit`
- `0x1a1035`: `ShouldCacheContainerSize`

## pseudocode

```c

```

## disassembly

```asm
0x1a0e80  ldstr    aIsvirtualizing_0// "IsVirtualizing"
0x1a0e85  ldtoken  [mscorlib]System.Boolean
0x1a0e8a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a0e8f  ldtoken  System.Windows.Controls.VirtualizingPanel
0x1a0e94  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a0e99  ldc.i4.1
0x1a0e9a  box      [mscorlib]System.Boolean
0x1a0e9f  ldc.i4.1
0x1a0ea0  ldnull
0x1a0ea1  ldftn    void System.Windows.Controls.VirtualizingPanel::OnVirtualizationPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x1a0ea7  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x1a0eac  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x1a0eb1  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1a0eb6  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.VirtualizingPanel::IsVirtualizingProperty
0x1a0ebb  ldstr    aVirtualization// "VirtualizationMode"
0x1a0ec0  ldtoken  System.Windows.Controls.VirtualizationMode
0x1a0ec5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a0eca  ldtoken  System.Windows.Controls.VirtualizingPanel
0x1a0ecf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a0ed4  ldc.i4.0
0x1a0ed5  box      System.Windows.Controls.VirtualizationMode
0x1a0eda  ldc.i4.1
0x1a0edb  ldnull
0x1a0edc  ldftn    void System.Windows.Controls.VirtualizingPanel::OnVirtualizationPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x1a0ee2  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x1a0ee7  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x1a0eec  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1a0ef1  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.VirtualizingPanel::VirtualizationModeProperty
0x1a0ef6  ldstr    aIsvirtualizing_1// "IsVirtualizingWhenGrouping"
0x1a0efb  ldtoken  [mscorlib]System.Boolean
0x1a0f00  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a0f05  ldtoken  System.Windows.Controls.VirtualizingPanel
0x1a0f0a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a0f0f  ldc.i4.0
0x1a0f10  box      [mscorlib]System.Boolean
0x1a0f15  ldc.i4.1
0x1a0f16  ldnull
0x1a0f17  ldftn    void System.Windows.Controls.VirtualizingPanel::OnVirtualizationPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x1a0f1d  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x1a0f22  ldnull
0x1a0f23  ldftn    object System.Windows.Controls.VirtualizingPanel::CoerceIsVirtualizingWhenGrouping(class [WindowsBase]System.Windows.DependencyObject d, object baseValue)
0x1a0f29  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x1a0f2e  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x1a0f33  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1a0f38  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.VirtualizingPanel::IsVirtualizingWhenGroupingProperty
0x1a0f3d  ldstr    aScrollunit// "ScrollUnit"
0x1a0f42  ldtoken  System.Windows.Controls.ScrollUnit
0x1a0f47  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a0f4c  ldtoken  System.Windows.Controls.VirtualizingPanel
0x1a0f51  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a0f56  ldc.i4.1
0x1a0f57  box      System.Windows.Controls.ScrollUnit
0x1a0f5c  ldc.i4.1
0x1a0f5d  ldnull
0x1a0f5e  ldftn    void System.Windows.Controls.VirtualizingPanel::OnVirtualizationPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x1a0f64  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x1a0f69  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x1a0f6e  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1a0f73  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.VirtualizingPanel::ScrollUnitProperty
0x1a0f78  ldstr    aCachelength// "CacheLength"
0x1a0f7d  ldtoken  System.Windows.Controls.VirtualizationCacheLength
0x1a0f82  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a0f87  ldtoken  System.Windows.Controls.VirtualizingPanel
0x1a0f8c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a0f91  ldc.r8   1.0
0x1a0f9a  newobj   instance void System.Windows.Controls.VirtualizationCacheLength::.ctor(float64 cacheBeforeAndAfterViewport)
0x1a0f9f  box      System.Windows.Controls.VirtualizationCacheLength
0x1a0fa4  ldc.i4.1
0x1a0fa5  ldnull
0x1a0fa6  ldftn    void System.Windows.Controls.VirtualizingPanel::OnVirtualizationPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x1a0fac  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x1a0fb1  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x1a0fb6  ldnull
0x1a0fb7  ldftn    bool System.Windows.Controls.VirtualizingPanel::ValidateCacheSizeBeforeOrAfterViewport(object value)
0x1a0fbd  newobj   instance void [WindowsBase]System.Windows.ValidateValueCallback::.ctor(object, native int)
0x1a0fc2  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata, class [WindowsBase]System.Windows.ValidateValueCallback)
0x1a0fc7  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.VirtualizingPanel::CacheLengthProperty
0x1a0fcc  ldstr    aCachelengthuni// "CacheLengthUnit"
0x1a0fd1  ldtoken  System.Windows.Controls.VirtualizationCacheLengthUnit
0x1a0fd6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a0fdb  ldtoken  System.Windows.Controls.VirtualizingPanel
0x1a0fe0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a0fe5  ldc.i4.2
0x1a0fe6  box      System.Windows.Controls.VirtualizationCacheLengthUnit
0x1a0feb  ldc.i4.1
0x1a0fec  ldnull
0x1a0fed  ldftn    void System.Windows.Controls.VirtualizingPanel::OnVirtualizationPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x1a0ff3  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x1a0ff8  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x1a0ffd  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1a1002  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.VirtualizingPanel::CacheLengthUnitProperty
0x1a1007  ldstr    aIscontainervir// "IsContainerVirtualizable"
0x1a100c  ldtoken  [mscorlib]System.Boolean
0x1a1011  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a1016  ldtoken  System.Windows.Controls.VirtualizingPanel
0x1a101b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a1020  ldc.i4.1
0x1a1021  box      [mscorlib]System.Boolean
0x1a1026  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x1a102b  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1a1030  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.VirtualizingPanel::IsContainerVirtualizableProperty
0x1a1035  ldstr    aShouldcachecon// "ShouldCacheContainerSize"
0x1a103a  ldtoken  [mscorlib]System.Boolean
0x1a103f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a1044  ldtoken  System.Windows.Controls.VirtualizingPanel
0x1a1049  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a104e  ldc.i4.1
0x1a104f  box      [mscorlib]System.Boolean
0x1a1054  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x1a1059  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1a105e  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.VirtualizingPanel::ShouldCacheContainerSizeProperty
0x1a1063  ret
```
