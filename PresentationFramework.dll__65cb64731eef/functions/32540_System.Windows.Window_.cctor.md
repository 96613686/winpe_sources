# System.Windows.Window::.cctor

- ea: `0x32540`
- end: `0x32cb2`
- name: `System.Windows.Window::.cctor`
- size: `1906`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x159e0`
- `0x159f0`
- `0x15a00`
- `0x15a20`
- `0x15a30`
- `0x15a40`
- `0x15a60`

## string_xrefs

- `0x32540`: `TaskbarItemInfo`
- `0x3271d`: `ShowInTaskbar`
- `0x3298c`: `IWindowService`
- `0x32c2d`: `TaskbarButtonCreated`
- `0x32c3c`: `WPF_ApplyTaskbarItemInfo`

## pseudocode

```c

```

## disassembly

```asm
0x32540  ldstr    aTaskbariteminf// "TaskbarItemInfo"
0x32545  ldtoken  System.Windows.Shell.TaskbarItemInfo
0x3254a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3254f  ldtoken  System.Windows.Window
0x32554  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x32559  ldnull
0x3255a  ldsfld   class <>c <>c::<>9
0x3255f  ldftn    instance void <>c::<.cctor>b__0_0(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x32565  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x3256a  ldnull
0x3256b  ldftn    object System.Windows.Window::VerifyAccessCoercion(class [WindowsBase]System.Windows.DependencyObject d, object value)
0x32571  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x32576  newobj   instance void [WindowsBase]System.Windows.PropertyMetadata::.ctor(object, class [WindowsBase]System.Windows.PropertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback)
0x3257b  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x32580  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Window::TaskbarItemInfoProperty
0x32585  ldstr    aAllowstranspar// "AllowsTransparency"
0x3258a  ldtoken  [mscorlib]System.Boolean
0x3258f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x32594  ldtoken  System.Windows.Window
0x32599  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3259e  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::FalseBox
0x325a3  ldnull
0x325a4  ldftn    void System.Windows.Window::OnAllowsTransparencyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x325aa  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x325af  ldnull
0x325b0  ldftn    object System.Windows.Window::CoerceAllowsTransparency(class [WindowsBase]System.Windows.DependencyObject d, object value)
0x325b6  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x325bb  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x325c0  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x325c5  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Window::AllowsTransparencyProperty
0x325ca  ldstr    aTitle_0// "Title"
0x325cf  ldtoken  [mscorlib]System.String
0x325d4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x325d9  ldtoken  System.Windows.Window
0x325de  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x325e3  ldsfld   string [mscorlib]System.String::Empty
0x325e8  ldnull
0x325e9  ldftn    void System.Windows.Window::_OnTitleChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x325ef  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x325f4  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x325f9  ldnull
0x325fa  ldftn    bool System.Windows.Window::_ValidateText(object value)
0x32600  newobj   instance void [WindowsBase]System.Windows.ValidateValueCallback::.ctor(object, native int)
0x32605  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata, class [WindowsBase]System.Windows.ValidateValueCallback)
0x3260a  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Window::TitleProperty
0x3260f  ldstr    aIcon_0// "Icon"
0x32614  ldtoken  [PresentationCore]System.Windows.Media.ImageSource
0x32619  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3261e  ldtoken  System.Windows.Window
0x32623  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x32628  ldnull
0x32629  ldftn    void System.Windows.Window::_OnIconChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x3262f  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x32634  ldnull
0x32635  ldftn    object System.Windows.Window::VerifyAccessCoercion(class [WindowsBase]System.Windows.DependencyObject d, object value)
0x3263b  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x32640  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x32645  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x3264a  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Window::IconProperty
0x3264f  ldstr    aSizetocontent// "SizeToContent"
0x32654  ldtoken  [PresentationCore]System.Windows.SizeToContent
0x32659  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3265e  ldtoken  System.Windows.Window
0x32663  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x32668  ldc.i4.0
0x32669  box      [PresentationCore]System.Windows.SizeToContent
0x3266e  ldnull
0x3266f  ldftn    void System.Windows.Window::_OnSizeToContentChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x32675  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x3267a  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x3267f  ldnull
0x32680  ldftn    bool System.Windows.Window::_ValidateSizeToContentCallback(object value)
0x32686  newobj   instance void [WindowsBase]System.Windows.ValidateValueCallback::.ctor(object, native int)
0x3268b  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata, class [WindowsBase]System.Windows.ValidateValueCallback)
0x32690  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Window::SizeToContentProperty
0x32695  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Canvas::TopProperty
0x3269a  ldtoken  System.Windows.Window
0x3269f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x326a4  ldc.r8   NaN
0x326ad  box      [mscorlib]System.Double
0x326b2  ldnull
0x326b3  ldftn    void System.Windows.Window::_OnTopChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x326b9  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x326be  ldnull
0x326bf  ldftn    object System.Windows.Window::CoerceTop(class [WindowsBase]System.Windows.DependencyObject d, object value)
0x326c5  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x326ca  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x326cf  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::AddOwner(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x326d4  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Window::TopProperty
0x326d9  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Canvas::LeftProperty
0x326de  ldtoken  System.Windows.Window
0x326e3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x326e8  ldc.r8   NaN
0x326f1  box      [mscorlib]System.Double
0x326f6  ldnull
0x326f7  ldftn    void System.Windows.Window::_OnLeftChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x326fd  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x32702  ldnull
0x32703  ldftn    object System.Windows.Window::CoerceLeft(class [WindowsBase]System.Windows.DependencyObject d, object value)
0x32709  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x3270e  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x32713  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::AddOwner(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x32718  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Window::LeftProperty
0x3271d  ldstr    aShowintaskbar// "ShowInTaskbar"
0x32722  ldtoken  [mscorlib]System.Boolean
0x32727  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3272c  ldtoken  System.Windows.Window
0x32731  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x32736  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::TrueBox
0x3273b  ldnull
0x3273c  ldftn    void System.Windows.Window::_OnShowInTaskbarChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x32742  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x32747  ldnull
0x32748  ldftn    object System.Windows.Window::VerifyAccessCoercion(class [WindowsBase]System.Windows.DependencyObject d, object value)
0x3274e  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x32753  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x32758  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x3275d  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Window::ShowInTaskbarProperty
0x32762  ldstr    aIsactive// "IsActive"
0x32767  ldtoken  [mscorlib]System.Boolean
0x3276c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x32771  ldtoken  System.Windows.Window
0x32776  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3277b  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::FalseBox
0x32780  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x32785  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x3278a  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Window::IsActivePropertyKey
0x3278f  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Window::IsActivePropertyKey
0x32794  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x32799  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Window::IsActiveProperty
0x3279e  ldstr    aWindowstyle// "WindowStyle"
0x327a3  ldtoken  System.Windows.WindowStyle
0x327a8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x327ad  ldtoken  System.Windows.Window
0x327b2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x327b7  ldc.i4.1
0x327b8  box      System.Windows.WindowStyle
0x327bd  ldnull
0x327be  ldftn    void System.Windows.Window::_OnWindowStyleChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x327c4  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x327c9  ldnull
0x327ca  ldftn    object System.Windows.Window::CoerceWindowStyle(class [WindowsBase]System.Windows.DependencyObject d, object value)
0x327d0  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x327d5  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x327da  ldnull
0x327db  ldftn    bool System.Windows.Window::_ValidateWindowStyleCallback(object value)
0x327e1  newobj   instance void [WindowsBase]System.Windows.ValidateValueCallback::.ctor(object, native int)
0x327e6  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata, class [WindowsBase]System.Windows.ValidateValueCallback)
0x327eb  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Window::WindowStyleProperty
0x327f0  ldstr    aWindowstate// "WindowState"
0x327f5  ldtoken  System.Windows.WindowState
0x327fa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x327ff  ldtoken  System.Windows.Window
0x32804  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x32809  ldc.i4.0
0x3280a  box      System.Windows.WindowState
0x3280f  ldc.i4   0x100
0x32814  ldnull
0x32815  ldftn    void System.Windows.Window::_OnWindowStateChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x3281b  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x32820  ldnull
0x32821  ldftn    object System.Windows.Window::VerifyAccessCoercion(class [WindowsBase]System.Windows.DependencyObject d, object value)
0x32827  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x3282c  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x32831  ldnull
0x32832  ldftn    bool System.Windows.Window::_ValidateWindowStateCallback(object value)
0x32838  newobj   instance void [WindowsBase]System.Windows.ValidateValueCallback::.ctor(object, native int)
0x3283d  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata, class [WindowsBase]System.Windows.ValidateValueCallback)
0x32842  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Window::WindowStateProperty
0x32847  ldstr    aResizemode// "ResizeMode"
0x3284c  ldtoken  System.Windows.ResizeMode
0x32851  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x32856  ldtoken  System.Windows.Window
0x3285b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x32860  ldc.i4.2
0x32861  box      System.Windows.ResizeMode
0x32866  ldc.i4.1
0x32867  ldnull
0x32868  ldftn    void System.Windows.Window::_OnResizeModeChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x3286e  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x32873  ldnull
0x32874  ldftn    object System.Windows.Window::VerifyAccessCoercion(class [WindowsBase]System.Windows.DependencyObject d, object value)
0x3287a  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x3287f  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x32884  ldnull
0x32885  ldftn    bool System.Windows.Window::_ValidateResizeModeCallback(object value)
0x3288b  newobj   instance void [WindowsBase]System.Windows.ValidateValueCallback::.ctor(object, native int)
0x32890  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata, class [WindowsBase]System.Windows.ValidateValueCallback)
0x32895  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Window::ResizeModeProperty
0x3289a  ldstr    aTopmost// "Topmost"
0x3289f  ldtoken  [mscorlib]System.Boolean
0x328a4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x328a9  ldtoken  System.Windows.Window
0x328ae  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x328b3  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::FalseBox
0x328b8  ldnull
0x328b9  ldftn    void System.Windows.Window::_OnTopmostChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x328bf  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x328c4  ldnull
0x328c5  ldftn    object System.Windows.Window::VerifyAccessCoercion(class [WindowsBase]System.Windows.DependencyObject d, object value)
0x328cb  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x328d0  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x328d5  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x328da  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Window::TopmostProperty
0x328df  ldstr    aShowactivated// "ShowActivated"
0x328e4  ldtoken  [mscorlib]System.Boolean
0x328e9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x328ee  ldtoken  System.Windows.Window
0x328f3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x328f8  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::TrueBox
0x328fd  ldnull
0x328fe  ldnull
0x328ff  ldftn    object System.Windows.Window::VerifyAccessCoercion(class [WindowsBase]System.Windows.DependencyObject d, object value)
0x32905  newobj   instance void [WindowsBase]System.Windows.CoerceValueCallback::.ctor(object, native int)
0x3290a  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback coerceValueCallback)
0x3290f  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x32914  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Window::ShowActivatedProperty
0x32919  ldstr    aDialogcancel// "DialogCancel"
0x3291e  ldtoken  System.Windows.Window
0x32923  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x32928  newobj   instance void [PresentationCore]System.Windows.Input.RoutedCommand::.ctor(string, class [mscorlib]System.Type)
0x3292d  stsfld   class [PresentationCore]System.Windows.Input.RoutedCommand System.Windows.Window::DialogCancelCommand
0x32932  newobj   instance void [mscorlib]System.Object::.ctor()
0x32937  stsfld   object System.Windows.Window::EVENT_SOURCEINITIALIZED
0x3293c  newobj   instance void [mscorlib]System.Object::.ctor()
0x32941  stsfld   object System.Windows.Window::EVENT_CLOSING
0x32946  newobj   instance void [mscorlib]System.Object::.ctor()
0x3294b  stsfld   object System.Windows.Window::EVENT_CLOSED
0x32950  newobj   instance void [mscorlib]System.Object::.ctor()
0x32955  stsfld   object System.Windows.Window::EVENT_ACTIVATED
0x3295a  newobj   instance void [mscorlib]System.Object::.ctor()
0x3295f  stsfld   object System.Windows.Window::EVENT_DEACTIVATED
0x32964  newobj   instance void [mscorlib]System.Object::.ctor()
0x32969  stsfld   object System.Windows.Window::EVENT_STATECHANGED
0x3296e  newobj   instance void [mscorlib]System.Object::.ctor()
0x32973  stsfld   object System.Windows.Window::EVENT_LOCATIONCHANGED
0x32978  newobj   instance void [mscorlib]System.Object::.ctor()
0x3297d  stsfld   object System.Windows.Window::EVENT_CONTENTRENDERED
0x32982  newobj   instance void [mscorlib]System.Object::.ctor()
0x32987  stsfld   object System.Windows.Window::EVENT_VISUALCHILDRENCHANGED
0x3298c  ldstr    aIwindowservice// "IWindowService"
0x32991  ldtoken  System.Windows.IWindowService
0x32996  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3299b  ldtoken  System.Windows.Window
0x329a0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x329a5  ldnull
0x329a6  ldc.i4.s 0x60
0x329a8  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags)
0x329ad  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x329b2  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Window::IWindowServiceProperty
0x329b7  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.FrameworkElement::HeightProperty
0x329bc  ldtoken  System.Windows.Window
0x329c1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x329c6  ldnull
0x329c7  ldftn    void System.Windows.Window::_OnHeightChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x329cd  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x329d2  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x329d7  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x329dc  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.FrameworkElement::MinHeightProperty
0x329e1  ldtoken  System.Windows.Window
0x329e6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x329eb  ldnull
0x329ec  ldftn    void System.Windows.Window::_OnMinHeightChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x329f2  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x329f7  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x329fc  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x32a01  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.FrameworkElement::MaxHeightProperty
0x32a06  ldtoken  System.Windows.Window
0x32a0b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x32a10  ldnull
0x32a11  ldftn    void System.Windows.Window::_OnMaxHeightChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x32a17  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x32a1c  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x32a21  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x32a26  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.FrameworkElement::WidthProperty
0x32a2b  ldtoken  System.Windows.Window
0x32a30  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x32a35  ldnull
0x32a36  ldftn    void System.Windows.Window::_OnWidthChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x32a3c  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x32a41  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x32a46  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x32a4b  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.FrameworkElement::MinWidthProperty
0x32a50  ldtoken  System.Windows.Window
0x32a55  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x32a5a  ldnull
0x32a5b  ldftn    void System.Windows.Window::_OnMinWidthChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x32a61  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x32a66  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x32a6b  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x32a70  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.FrameworkElement::MaxWidthProperty
0x32a75  ldtoken  System.Windows.Window
0x32a7a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x32a7f  ldnull
0x32a80  ldftn    void System.Windows.Window::_OnMaxWidthChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x32a86  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x32a8b  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x32a90  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x32a95  ldsfld   class [WindowsBase]System.Windows.DependencyProperty [PresentationCore]System.Windows.UIElement::VisibilityProperty
0x32a9a  ldtoken  System.Windows.Window
  ... truncated ...
```
