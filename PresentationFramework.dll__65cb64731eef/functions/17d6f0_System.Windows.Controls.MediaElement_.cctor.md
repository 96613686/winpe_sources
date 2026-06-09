# System.Windows.Controls.MediaElement::.cctor

- ea: `0x17d6f0`
- end: `0x17da0f`
- name: `System.Windows.Controls.MediaElement::.cctor`
- size: `799`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x159e0`
- `0x15a40`
- `0x15a50`
- `0x17da10`
- `0x24e850`

## string_xrefs

- `0x17d8ef`: `MediaOpened`
- `0x17d95b`: `ScriptCommand`

## pseudocode

```c

```

## disassembly

```asm
0x17d6f0  ldstr    aSource_0// "Source"
0x17d6f5  ldtoken  [System]System.Uri
0x17d6fa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d6ff  ldtoken  System.Windows.Controls.MediaElement
0x17d704  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d709  ldnull
0x17d70a  ldc.i4.s 0x11
0x17d70c  ldnull
0x17d70d  ldftn    void System.Windows.Controls.AVElementHelper::OnSourceChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x17d713  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x17d718  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x17d71d  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x17d722  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.MediaElement::SourceProperty
0x17d727  ldstr    aVolume// "Volume"
0x17d72c  ldtoken  [mscorlib]System.Double
0x17d731  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d736  ldtoken  System.Windows.Controls.MediaElement
0x17d73b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d740  ldc.r8   0.5
0x17d749  box      [mscorlib]System.Double
0x17d74e  ldc.i4.0
0x17d74f  ldnull
0x17d750  ldftn    void System.Windows.Controls.MediaElement::VolumePropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x17d756  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x17d75b  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x17d760  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x17d765  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.MediaElement::VolumeProperty
0x17d76a  ldstr    aBalance// "Balance"
0x17d76f  ldtoken  [mscorlib]System.Double
0x17d774  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d779  ldtoken  System.Windows.Controls.MediaElement
0x17d77e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d783  ldc.r8   0.0
0x17d78c  box      [mscorlib]System.Double
0x17d791  ldc.i4.0
0x17d792  ldnull
0x17d793  ldftn    void System.Windows.Controls.MediaElement::BalancePropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x17d799  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x17d79e  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x17d7a3  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x17d7a8  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.MediaElement::BalanceProperty
0x17d7ad  ldstr    aIsmuted// "IsMuted"
0x17d7b2  ldtoken  [mscorlib]System.Boolean
0x17d7b7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d7bc  ldtoken  System.Windows.Controls.MediaElement
0x17d7c1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d7c6  ldc.i4.0
0x17d7c7  box      [mscorlib]System.Boolean
0x17d7cc  ldc.i4.0
0x17d7cd  ldnull
0x17d7ce  ldftn    void System.Windows.Controls.MediaElement::IsMutedPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x17d7d4  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x17d7d9  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x17d7de  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x17d7e3  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.MediaElement::IsMutedProperty
0x17d7e8  ldstr    aScrubbingenabl// "ScrubbingEnabled"
0x17d7ed  ldtoken  [mscorlib]System.Boolean
0x17d7f2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d7f7  ldtoken  System.Windows.Controls.MediaElement
0x17d7fc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d801  ldc.i4.0
0x17d802  box      [mscorlib]System.Boolean
0x17d807  ldc.i4.0
0x17d808  ldnull
0x17d809  ldftn    void System.Windows.Controls.MediaElement::ScrubbingEnabledPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x17d80f  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x17d814  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x17d819  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x17d81e  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.MediaElement::ScrubbingEnabledProperty
0x17d823  ldstr    aUnloadedbehavi// "UnloadedBehavior"
0x17d828  ldtoken  System.Windows.Controls.MediaState
0x17d82d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d832  ldtoken  System.Windows.Controls.MediaElement
0x17d837  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d83c  ldc.i4.2
0x17d83d  box      System.Windows.Controls.MediaState
0x17d842  ldc.i4.0
0x17d843  ldnull
0x17d844  ldftn    void System.Windows.Controls.MediaElement::UnloadedBehaviorPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x17d84a  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x17d84f  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x17d854  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x17d859  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.MediaElement::UnloadedBehaviorProperty
0x17d85e  ldstr    aLoadedbehavior// "LoadedBehavior"
0x17d863  ldtoken  System.Windows.Controls.MediaState
0x17d868  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d86d  ldtoken  System.Windows.Controls.MediaElement
0x17d872  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d877  ldc.i4.1
0x17d878  box      System.Windows.Controls.MediaState
0x17d87d  ldc.i4.0
0x17d87e  ldnull
0x17d87f  ldftn    void System.Windows.Controls.MediaElement::LoadedBehaviorPropertyChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x17d885  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x17d88a  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x17d88f  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::Register(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x17d894  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.MediaElement::LoadedBehaviorProperty
0x17d899  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Viewbox::StretchProperty
0x17d89e  ldtoken  System.Windows.Controls.MediaElement
0x17d8a3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d8a8  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::AddOwner(class [mscorlib]System.Type)
0x17d8ad  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.MediaElement::StretchProperty
0x17d8b2  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Viewbox::StretchDirectionProperty
0x17d8b7  ldtoken  System.Windows.Controls.MediaElement
0x17d8bc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d8c1  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::AddOwner(class [mscorlib]System.Type)
0x17d8c6  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.MediaElement::StretchDirectionProperty
0x17d8cb  ldstr    aMediafailed// "MediaFailed"
0x17d8d0  ldc.i4.1
0x17d8d1  ldtoken  class [mscorlib]System.EventHandler`1<class System.Windows.ExceptionRoutedEventArgs>
0x17d8d6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d8db  ldtoken  System.Windows.Controls.MediaElement
0x17d8e0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d8e5  call     class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.EventManager::RegisterRoutedEvent(string, valuetype [PresentationCore]System.Windows.RoutingStrategy, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x17d8ea  stsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.MediaElement::MediaFailedEvent
0x17d8ef  ldstr    aMediaopened// "MediaOpened"
0x17d8f4  ldc.i4.1
0x17d8f5  ldtoken  [PresentationCore]System.Windows.RoutedEventHandler
0x17d8fa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d8ff  ldtoken  System.Windows.Controls.MediaElement
0x17d904  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d909  call     class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.EventManager::RegisterRoutedEvent(string, valuetype [PresentationCore]System.Windows.RoutingStrategy, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x17d90e  stsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.MediaElement::MediaOpenedEvent
0x17d913  ldstr    aBufferingstart// "BufferingStarted"
0x17d918  ldc.i4.1
0x17d919  ldtoken  [PresentationCore]System.Windows.RoutedEventHandler
0x17d91e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d923  ldtoken  System.Windows.Controls.MediaElement
0x17d928  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d92d  call     class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.EventManager::RegisterRoutedEvent(string, valuetype [PresentationCore]System.Windows.RoutingStrategy, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x17d932  stsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.MediaElement::BufferingStartedEvent
0x17d937  ldstr    aBufferingended// "BufferingEnded"
0x17d93c  ldc.i4.1
0x17d93d  ldtoken  [PresentationCore]System.Windows.RoutedEventHandler
0x17d942  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d947  ldtoken  System.Windows.Controls.MediaElement
0x17d94c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d951  call     class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.EventManager::RegisterRoutedEvent(string, valuetype [PresentationCore]System.Windows.RoutingStrategy, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x17d956  stsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.MediaElement::BufferingEndedEvent
0x17d95b  ldstr    aScriptcommand// "ScriptCommand"
0x17d960  ldc.i4.1
0x17d961  ldtoken  class [mscorlib]System.EventHandler`1<class System.Windows.MediaScriptCommandRoutedEventArgs>
0x17d966  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d96b  ldtoken  System.Windows.Controls.MediaElement
0x17d970  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d975  call     class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.EventManager::RegisterRoutedEvent(string, valuetype [PresentationCore]System.Windows.RoutingStrategy, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x17d97a  stsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.MediaElement::ScriptCommandEvent
0x17d97f  ldstr    aMediaended// "MediaEnded"
0x17d984  ldc.i4.1
0x17d985  ldtoken  [PresentationCore]System.Windows.RoutedEventHandler
0x17d98a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d98f  ldtoken  System.Windows.Controls.MediaElement
0x17d994  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d999  call     class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.EventManager::RegisterRoutedEvent(string, valuetype [PresentationCore]System.Windows.RoutingStrategy, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x17d99e  stsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.MediaElement::MediaEndedEvent
0x17d9a3  call     class System.Windows.Style System.Windows.Controls.MediaElement::CreateDefaultStyles()
0x17d9a8  stloc.0
0x17d9a9  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.FrameworkElement::StyleProperty
0x17d9ae  ldtoken  System.Windows.Controls.MediaElement
0x17d9b3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d9b8  ldloc.0
0x17d9b9  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x17d9be  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x17d9c3  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.MediaElement::StretchProperty
0x17d9c8  ldtoken  System.Windows.Controls.MediaElement
0x17d9cd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d9d2  ldc.i4.2
0x17d9d3  box      [PresentationCore]System.Windows.Media.Stretch
0x17d9d8  ldc.i4.1
0x17d9d9  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags)
0x17d9de  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x17d9e3  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.MediaElement::StretchDirectionProperty
0x17d9e8  ldtoken  System.Windows.Controls.MediaElement
0x17d9ed  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d9f2  ldc.i4.2
0x17d9f3  box      System.Windows.Controls.StretchDirection
0x17d9f8  ldc.i4.1
0x17d9f9  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags)
0x17d9fe  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x17da03  ldc.i4   0x100000
0x17da08  conv.i8
0x17da09  call     void MS.Internal.Telemetry.PresentationFramework.ControlsTraceLogger::AddControl(valuetype MS.Internal.Telemetry.PresentationFramework.TelemetryControls control)
0x17da0e  ret
```
