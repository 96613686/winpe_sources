# System.Windows.Shell.ThumbButtonInfo::.cctor

- ea: `0x3a7f0`
- end: `0x3aa34`
- name: `System.Windows.Shell.ThumbButtonInfo::.cctor`
- size: `580`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x3a94a`: `Command`
- `0x3a983`: `CommandParameter`
- `0x3a9bc`: `CommandTarget`

## pseudocode

```c

```

## disassembly

```asm
0x3a7f0  ldstr    aVisibility// "Visibility"
0x3a7f5  ldtoken  [PresentationCore]System.Windows.Visibility
0x3a7fa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3a7ff  ldtoken  System.Windows.Shell.ThumbButtonInfo
0x3a804  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3a809  ldc.i4.0
0x3a80a  box      [PresentationCore]System.Windows.Visibility
0x3a80f  newobj   instance void [WindowsBase]System.Windows.PropertyMetadata::.ctor(object)
0x3a814  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x3a819  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Shell.ThumbButtonInfo::VisibilityProperty
0x3a81e  ldstr    aDismisswhencli// "DismissWhenClicked"
0x3a823  ldtoken  [mscorlib]System.Boolean
0x3a828  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3a82d  ldtoken  System.Windows.Shell.ThumbButtonInfo
0x3a832  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3a837  ldc.i4.0
0x3a838  box      [mscorlib]System.Boolean
0x3a83d  newobj   instance void [WindowsBase]System.Windows.PropertyMetadata::.ctor(object)
0x3a842  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x3a847  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Shell.ThumbButtonInfo::DismissWhenClickedProperty
0x3a84c  ldstr    aImagesource// "ImageSource"
0x3a851  ldtoken  [PresentationCore]System.Windows.Media.ImageSource
0x3a856  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3a85b  ldtoken  System.Windows.Shell.ThumbButtonInfo
0x3a860  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3a865  ldnull
0x3a866  newobj   instance void [WindowsBase]System.Windows.PropertyMetadata::.ctor(class [WindowsBase]System.Windows.PropertyChangedCallback)
0x3a86b  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x3a870  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Shell.ThumbButtonInfo::ImageSourceProperty
0x3a875  ldstr    aIsbackgroundvi// "IsBackgroundVisible"
0x3a87a  ldtoken  [mscorlib]System.Boolean
0x3a87f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3a884  ldtoken  System.Windows.Shell.ThumbButtonInfo
0x3a889  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3a88e  ldc.i4.1
0x3a88f  box      [mscorlib]System.Boolean
0x3a894  newobj   instance void [WindowsBase]System.Windows.PropertyMetadata::.ctor(object)
0x3a899  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x3a89e  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Shell.ThumbButtonInfo::IsBackgroundVisibleProperty
0x3a8a3  ldstr    aDescription// "Description"
0x3a8a8  ldtoken  [mscorlib]System.String
0x3a8ad  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3a8b2  ldtoken  System.Windows.Shell.ThumbButtonInfo
0x3a8b7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3a8bc  ldsfld   string [mscorlib]System.String::Empty
0x3a8c1  ldnull
0x3a8c2  ldnull
0x3a8c3  ldftn    object System.Windows.Shell.ThumbButtonInfo::CoerceDescription(class [WindowsBase]System.Windows.DependencyObject d, object value)
0x3a8c9  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x3a8ce  newobj   instance void [WindowsBase]System.Windows.PropertyMetadata::.ctor(object, class [WindowsBase]System.Windows.PropertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback)
0x3a8d3  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x3a8d8  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Shell.ThumbButtonInfo::DescriptionProperty
0x3a8dd  ldstr    aIsenabled// "IsEnabled"
0x3a8e2  ldtoken  [mscorlib]System.Boolean
0x3a8e7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3a8ec  ldtoken  System.Windows.Shell.ThumbButtonInfo
0x3a8f1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3a8f6  ldc.i4.1
0x3a8f7  box      [mscorlib]System.Boolean
0x3a8fc  ldnull
0x3a8fd  ldsfld   class <>c <>c::<>9
0x3a902  ldftn    instance object <>c::<.cctor>b__58_0(class [WindowsBase]System.Windows.DependencyObject d, object e)
0x3a908  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x3a90d  newobj   instance void [WindowsBase]System.Windows.PropertyMetadata::.ctor(object, class [WindowsBase]System.Windows.PropertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback)
0x3a912  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x3a917  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Shell.ThumbButtonInfo::IsEnabledProperty
0x3a91c  ldstr    aIsinteractive// "IsInteractive"
0x3a921  ldtoken  [mscorlib]System.Boolean
0x3a926  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3a92b  ldtoken  System.Windows.Shell.ThumbButtonInfo
0x3a930  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3a935  ldc.i4.1
0x3a936  box      [mscorlib]System.Boolean
0x3a93b  newobj   instance void [WindowsBase]System.Windows.PropertyMetadata::.ctor(object)
0x3a940  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x3a945  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Shell.ThumbButtonInfo::IsInteractiveProperty
0x3a94a  ldstr    aCommand// "Command"
0x3a94f  ldtoken  [System]System.Windows.Input.ICommand
0x3a954  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3a959  ldtoken  System.Windows.Shell.ThumbButtonInfo
0x3a95e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3a963  ldnull
0x3a964  ldsfld   class <>c <>c::<>9
0x3a969  ldftn    instance void <>c::<.cctor>b__58_1(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x3a96f  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x3a974  newobj   instance void [WindowsBase]System.Windows.PropertyMetadata::.ctor(object, class [WindowsBase]System.Windows.PropertyChangedCallback)
0x3a979  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x3a97e  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Shell.ThumbButtonInfo::CommandProperty
0x3a983  ldstr    aCommandparamet// "CommandParameter"
0x3a988  ldtoken  [mscorlib]System.Object
0x3a98d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3a992  ldtoken  System.Windows.Shell.ThumbButtonInfo
0x3a997  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3a99c  ldnull
0x3a99d  ldsfld   class <>c <>c::<>9
0x3a9a2  ldftn    instance void <>c::<.cctor>b__58_2(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x3a9a8  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x3a9ad  newobj   instance void [WindowsBase]System.Windows.PropertyMetadata::.ctor(object, class [WindowsBase]System.Windows.PropertyChangedCallback)
0x3a9b2  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x3a9b7  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Shell.ThumbButtonInfo::CommandParameterProperty
0x3a9bc  ldstr    aCommandtarget// "CommandTarget"
0x3a9c1  ldtoken  [PresentationCore]System.Windows.IInputElement
0x3a9c6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3a9cb  ldtoken  System.Windows.Shell.ThumbButtonInfo
0x3a9d0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3a9d5  ldnull
0x3a9d6  ldsfld   class <>c <>c::<>9
0x3a9db  ldftn    instance void <>c::<.cctor>b__58_3(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x3a9e1  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x3a9e6  newobj   instance void [WindowsBase]System.Windows.PropertyMetadata::.ctor(object, class [WindowsBase]System.Windows.PropertyChangedCallback)
0x3a9eb  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x3a9f0  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Shell.ThumbButtonInfo::CommandTargetProperty
0x3a9f5  ldstr    aCanexecute// "_CanExecute"
0x3a9fa  ldtoken  [mscorlib]System.Boolean
0x3a9ff  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3aa04  ldtoken  System.Windows.Shell.ThumbButtonInfo
0x3aa09  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3aa0e  ldc.i4.1
0x3aa0f  box      [mscorlib]System.Boolean
0x3aa14  ldsfld   class <>c <>c::<>9
0x3aa19  ldftn    instance void <>c::<.cctor>b__58_4(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x3aa1f  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x3aa24  newobj   instance void [WindowsBase]System.Windows.PropertyMetadata::.ctor(object, class [WindowsBase]System.Windows.PropertyChangedCallback)
0x3aa29  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x3aa2e  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Shell.ThumbButtonInfo::_CanExecuteProperty
0x3aa33  ret
```
