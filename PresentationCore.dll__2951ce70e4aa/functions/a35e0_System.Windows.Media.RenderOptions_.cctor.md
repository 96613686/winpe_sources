# System.Windows.Media.RenderOptions::.cctor

- ea: `0xa35e0`
- end: `0xa3737`
- name: `System.Windows.Media.RenderOptions::.cctor`
- size: `343`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x2e740`

## string_xrefs

- `0xa36c8`: `CacheInvalidationThresholdMinimum`
- `0xa36ff`: `CacheInvalidationThresholdMaximum`

## pseudocode

```c

```

## disassembly

```asm
0xa35e0  ldstr    aEdgemode// "EdgeMode"
0xa35e5  ldtoken  System.Windows.Media.EdgeMode
0xa35ea  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa35ef  ldtoken  System.Windows.Media.RenderOptions
0xa35f4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa35f9  ldc.i4.0
0xa35fa  box      System.Windows.Media.EdgeMode
0xa35ff  newobj   instance void System.Windows.UIPropertyMetadata::.ctor(object defaultValue)
0xa3604  ldnull
0xa3605  ldftn    bool System.Windows.Media.ValidateEnums::IsEdgeModeValid(object valueObject)
0xa360b  newobj   instance void [WindowsBase]System.Windows.ValidateValueCallback::.ctor(object, native int)
0xa3610  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata, class [WindowsBase]System.Windows.ValidateValueCallback)
0xa3615  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Media.RenderOptions::EdgeModeProperty
0xa361a  ldstr    aBitmapscalingm// "BitmapScalingMode"
0xa361f  ldtoken  System.Windows.Media.BitmapScalingMode
0xa3624  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa3629  ldtoken  System.Windows.Media.RenderOptions
0xa362e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa3633  ldc.i4.0
0xa3634  box      System.Windows.Media.BitmapScalingMode
0xa3639  newobj   instance void System.Windows.UIPropertyMetadata::.ctor(object defaultValue)
0xa363e  ldnull
0xa363f  ldftn    bool System.Windows.Media.ValidateEnums::IsBitmapScalingModeValid(object valueObject)
0xa3645  newobj   instance void [WindowsBase]System.Windows.ValidateValueCallback::.ctor(object, native int)
0xa364a  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata, class [WindowsBase]System.Windows.ValidateValueCallback)
0xa364f  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Media.RenderOptions::BitmapScalingModeProperty
0xa3654  ldstr    aCleartypehint// "ClearTypeHint"
0xa3659  ldtoken  System.Windows.Media.ClearTypeHint
0xa365e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa3663  ldtoken  System.Windows.Media.RenderOptions
0xa3668  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa366d  ldc.i4.0
0xa366e  box      System.Windows.Media.ClearTypeHint
0xa3673  newobj   instance void System.Windows.UIPropertyMetadata::.ctor(object defaultValue)
0xa3678  ldnull
0xa3679  ldftn    bool System.Windows.Media.ValidateEnums::IsClearTypeHintValid(object valueObject)
0xa367f  newobj   instance void [WindowsBase]System.Windows.ValidateValueCallback::.ctor(object, native int)
0xa3684  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata, class [WindowsBase]System.Windows.ValidateValueCallback)
0xa3689  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Media.RenderOptions::ClearTypeHintProperty
0xa368e  ldstr    aCachinghint// "CachingHint"
0xa3693  ldtoken  System.Windows.Media.CachingHint
0xa3698  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa369d  ldtoken  System.Windows.Media.RenderOptions
0xa36a2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa36a7  ldc.i4.0
0xa36a8  box      System.Windows.Media.CachingHint
0xa36ad  newobj   instance void System.Windows.UIPropertyMetadata::.ctor(object defaultValue)
0xa36b2  ldnull
0xa36b3  ldftn    bool System.Windows.Media.ValidateEnums::IsCachingHintValid(object valueObject)
0xa36b9  newobj   instance void [WindowsBase]System.Windows.ValidateValueCallback::.ctor(object, native int)
0xa36be  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata, class [WindowsBase]System.Windows.ValidateValueCallback)
0xa36c3  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Media.RenderOptions::CachingHintProperty
0xa36c8  ldstr    aCacheinvalidat// "CacheInvalidationThresholdMinimum"
0xa36cd  ldtoken  [mscorlib]System.Double
0xa36d2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa36d7  ldtoken  System.Windows.Media.RenderOptions
0xa36dc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa36e1  ldc.r8   0.707
0xa36ea  box      [mscorlib]System.Double
0xa36ef  newobj   instance void System.Windows.UIPropertyMetadata::.ctor(object defaultValue)
0xa36f4  ldnull
0xa36f5  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata, class [WindowsBase]System.Windows.ValidateValueCallback)
0xa36fa  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Media.RenderOptions::CacheInvalidationThresholdMinimumProperty
0xa36ff  ldstr    aCacheinvalidat_0// "CacheInvalidationThresholdMaximum"
0xa3704  ldtoken  [mscorlib]System.Double
0xa3709  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa370e  ldtoken  System.Windows.Media.RenderOptions
0xa3713  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa3718  ldc.r8   1.414
0xa3721  box      [mscorlib]System.Double
0xa3726  newobj   instance void System.Windows.UIPropertyMetadata::.ctor(object defaultValue)
0xa372b  ldnull
0xa372c  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata, class [WindowsBase]System.Windows.ValidateValueCallback)
0xa3731  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Media.RenderOptions::CacheInvalidationThresholdMaximumProperty
0xa3736  ret
```
