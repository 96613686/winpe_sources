# System.Windows.Controls.ToolTipService::.cctor

- ea: `0x19b9c0`
- end: `0x19bd6e`
- name: `System.Windows.Controls.ToolTipService::.cctor`
- size: `942`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x159e0`
- `0x24a50`
- `0x19b9c0`
- `0x19bf10`
- `0x1d6230`

## string_xrefs

- `0x19bb38`: `IsOpen`
- `0x19bca1`: `ToolTipOpening`

## pseudocode

```c

```

## disassembly

```asm
0x19b9c0  ldstr    aTooltip// "ToolTip"
0x19b9c5  ldtoken  [mscorlib]System.Object
0x19b9ca  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19b9cf  ldtoken  System.Windows.Controls.ToolTipService
0x19b9d4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19b9d9  ldnull
0x19b9da  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x19b9df  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x19b9e4  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTipService::ToolTipProperty
0x19b9e9  ldstr    aHorizontaloffs// "HorizontalOffset"
0x19b9ee  ldtoken  [mscorlib]System.Double
0x19b9f3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19b9f8  ldtoken  System.Windows.Controls.ToolTipService
0x19b9fd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19ba02  ldc.r8   0.0
0x19ba0b  box      [mscorlib]System.Double
0x19ba10  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x19ba15  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x19ba1a  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTipService::HorizontalOffsetProperty
0x19ba1f  ldstr    aVerticaloffset// "VerticalOffset"
0x19ba24  ldtoken  [mscorlib]System.Double
0x19ba29  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19ba2e  ldtoken  System.Windows.Controls.ToolTipService
0x19ba33  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19ba38  ldc.r8   0.0
0x19ba41  box      [mscorlib]System.Double
0x19ba46  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x19ba4b  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x19ba50  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTipService::VerticalOffsetProperty
0x19ba55  ldstr    aHasdropshadow// "HasDropShadow"
0x19ba5a  ldtoken  [mscorlib]System.Boolean
0x19ba5f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19ba64  ldtoken  System.Windows.Controls.ToolTipService
0x19ba69  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19ba6e  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::FalseBox
0x19ba73  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x19ba78  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x19ba7d  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTipService::HasDropShadowProperty
0x19ba82  ldstr    aPlacementtarge// "PlacementTarget"
0x19ba87  ldtoken  [PresentationCore]System.Windows.UIElement
0x19ba8c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19ba91  ldtoken  System.Windows.Controls.ToolTipService
0x19ba96  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19ba9b  ldnull
0x19ba9c  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x19baa1  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x19baa6  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTipService::PlacementTargetProperty
0x19baab  ldstr    aPlacementrecta// "PlacementRectangle"
0x19bab0  ldtoken  [WindowsBase]System.Windows.Rect
0x19bab5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19baba  ldtoken  System.Windows.Controls.ToolTipService
0x19babf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19bac4  call     valuetype [WindowsBase]System.Windows.Rect [WindowsBase]System.Windows.Rect::get_Empty()
0x19bac9  box      [WindowsBase]System.Windows.Rect
0x19bace  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x19bad3  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x19bad8  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTipService::PlacementRectangleProperty
0x19badd  ldstr    aPlacement// "Placement"
0x19bae2  ldtoken  System.Windows.Controls.Primitives.PlacementMode
0x19bae7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19baec  ldtoken  System.Windows.Controls.ToolTipService
0x19baf1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19baf6  ldc.i4.7
0x19baf7  box      System.Windows.Controls.Primitives.PlacementMode
0x19bafc  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x19bb01  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x19bb06  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTipService::PlacementProperty
0x19bb0b  ldstr    aShowondisabled// "ShowOnDisabled"
0x19bb10  ldtoken  [mscorlib]System.Boolean
0x19bb15  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19bb1a  ldtoken  System.Windows.Controls.ToolTipService
0x19bb1f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19bb24  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::FalseBox
0x19bb29  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x19bb2e  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x19bb33  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTipService::ShowOnDisabledProperty
0x19bb38  ldstr    aIsopen// "IsOpen"
0x19bb3d  ldtoken  [mscorlib]System.Boolean
0x19bb42  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19bb47  ldtoken  System.Windows.Controls.ToolTipService
0x19bb4c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19bb51  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::FalseBox
0x19bb56  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x19bb5b  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterAttachedReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x19bb60  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ToolTipService::IsOpenPropertyKey
0x19bb65  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ToolTipService::IsOpenPropertyKey
0x19bb6a  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x19bb6f  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTipService::IsOpenProperty
0x19bb74  ldstr    aIsenabled// "IsEnabled"
0x19bb79  ldtoken  [mscorlib]System.Boolean
0x19bb7e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19bb83  ldtoken  System.Windows.Controls.ToolTipService
0x19bb88  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19bb8d  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::TrueBox
0x19bb92  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x19bb97  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x19bb9c  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTipService::IsEnabledProperty
0x19bba1  ldstr    aShowduration// "ShowDuration"
0x19bba6  ldtoken  [mscorlib]System.Int32
0x19bbab  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19bbb0  ldtoken  System.Windows.Controls.ToolTipService
0x19bbb5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19bbba  call     bool MS.Internal.FrameworkAppContextSwitches::get_OptOutOfWCAG21ToolTipBehavior()
0x19bbbf  brtrue.s loc_19BBC8
0x19bbc1  ldc.i4   0x7FFFFFFF
0x19bbc6  br.s     loc_19BBCD
0x19bbc8  ldc.i4   0x1388
0x19bbcd  box      [mscorlib]System.Int32
0x19bbd2  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x19bbd7  ldnull
0x19bbd8  ldftn    bool System.Windows.Controls.ToolTipService::PositiveValueValidation(object o)
0x19bbde  newobj   instance void [WindowsBase]System.Windows.ValidateValueCallback::.ctor(object, native int)
0x19bbe3  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata, class [WindowsBase]System.Windows.ValidateValueCallback)
0x19bbe8  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTipService::ShowDurationProperty
0x19bbed  ldstr    aInitialshowdel// "InitialShowDelay"
0x19bbf2  ldtoken  [mscorlib]System.Int32
0x19bbf7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19bbfc  ldtoken  System.Windows.Controls.ToolTipService
0x19bc01  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19bc06  call     bool MS.Internal.FrameworkAppContextSwitches::get_OptOutOfWCAG21ToolTipBehavior()
0x19bc0b  brtrue.s loc_19BC14
0x19bc0d  ldc.i4   0x3E8
0x19bc12  br.s     loc_19BC19
0x19bc14  call     int32 System.Windows.SystemParameters::get_MouseHoverTimeMilliseconds()
0x19bc19  box      [mscorlib]System.Int32
0x19bc1e  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x19bc23  ldnull
0x19bc24  ldftn    bool System.Windows.Controls.ToolTipService::PositiveValueValidation(object o)
0x19bc2a  newobj   instance void [WindowsBase]System.Windows.ValidateValueCallback::.ctor(object, native int)
0x19bc2f  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata, class [WindowsBase]System.Windows.ValidateValueCallback)
0x19bc34  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTipService::InitialShowDelayProperty
0x19bc39  ldstr    aBetweenshowdel// "BetweenShowDelay"
0x19bc3e  ldtoken  [mscorlib]System.Int32
0x19bc43  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19bc48  ldtoken  System.Windows.Controls.ToolTipService
0x19bc4d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19bc52  ldc.i4.s 0x64
0x19bc54  box      [mscorlib]System.Int32
0x19bc59  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x19bc5e  ldnull
0x19bc5f  ldftn    bool System.Windows.Controls.ToolTipService::PositiveValueValidation(object o)
0x19bc65  newobj   instance void [WindowsBase]System.Windows.ValidateValueCallback::.ctor(object, native int)
0x19bc6a  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata, class [WindowsBase]System.Windows.ValidateValueCallback)
0x19bc6f  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTipService::BetweenShowDelayProperty
0x19bc74  ldstr    aShowstooltipon// "ShowsToolTipOnKeyboardFocus"
0x19bc79  ldtoken  valuetype [mscorlib]System.Nullable`1<bool>
0x19bc7e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19bc83  ldtoken  System.Windows.Controls.ToolTipService
0x19bc88  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19bc8d  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.NullableBooleanBoxes::NullBox
0x19bc92  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x19bc97  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x19bc9c  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ToolTipService::ShowsToolTipOnKeyboardFocusProperty
0x19bca1  ldstr    aTooltipopening// "ToolTipOpening"
0x19bca6  ldc.i4.2
0x19bca7  ldtoken  System.Windows.Controls.ToolTipEventHandler
0x19bcac  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19bcb1  ldtoken  System.Windows.Controls.ToolTipService
0x19bcb6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19bcbb  call     class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.EventManager::RegisterRoutedEvent(string, valuetype [PresentationCore]System.Windows.RoutingStrategy, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x19bcc0  stsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.ToolTipService::ToolTipOpeningEvent
0x19bcc5  ldstr    aTooltipclosing// "ToolTipClosing"
0x19bcca  ldc.i4.2
0x19bccb  ldtoken  System.Windows.Controls.ToolTipEventHandler
0x19bcd0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19bcd5  ldtoken  System.Windows.Controls.ToolTipService
0x19bcda  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19bcdf  call     class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.EventManager::RegisterRoutedEvent(string, valuetype [PresentationCore]System.Windows.RoutingStrategy, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x19bce4  stsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.ToolTipService::ToolTipClosingEvent
0x19bce9  ldstr    aFindtooltip// "FindToolTip"
0x19bcee  ldc.i4.1
0x19bcef  ldtoken  System.Windows.Controls.FindToolTipEventHandler
0x19bcf4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19bcf9  ldtoken  System.Windows.Controls.ToolTipService
0x19bcfe  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19bd03  call     class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.EventManager::RegisterRoutedEvent(string, valuetype [PresentationCore]System.Windows.RoutingStrategy, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x19bd08  stsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.ToolTipService::FindToolTipEvent
0x19bd0d  ldtoken  [PresentationCore]System.Windows.UIElement
0x19bd12  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19bd17  ldsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.ToolTipService::FindToolTipEvent
0x19bd1c  ldnull
0x19bd1d  ldftn    void System.Windows.Controls.ToolTipService::OnFindToolTip(object sender, class System.Windows.Controls.FindToolTipEventArgs e)
0x19bd23  newobj   instance void System.Windows.Controls.FindToolTipEventHandler::.ctor(object object, native int method)
0x19bd28  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate)
0x19bd2d  ldtoken  [PresentationCore]System.Windows.ContentElement
0x19bd32  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19bd37  ldsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.ToolTipService::FindToolTipEvent
0x19bd3c  ldnull
0x19bd3d  ldftn    void System.Windows.Controls.ToolTipService::OnFindToolTip(object sender, class System.Windows.Controls.FindToolTipEventArgs e)
0x19bd43  newobj   instance void System.Windows.Controls.FindToolTipEventHandler::.ctor(object object, native int method)
0x19bd48  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate)
0x19bd4d  ldtoken  [PresentationCore]System.Windows.UIElement3D
0x19bd52  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19bd57  ldsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.ToolTipService::FindToolTipEvent
0x19bd5c  ldnull
0x19bd5d  ldftn    void System.Windows.Controls.ToolTipService::OnFindToolTip(object sender, class System.Windows.Controls.FindToolTipEventArgs e)
0x19bd63  newobj   instance void System.Windows.Controls.FindToolTipEventHandler::.ctor(object object, native int method)
0x19bd68  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate)
0x19bd6d  ret
```
