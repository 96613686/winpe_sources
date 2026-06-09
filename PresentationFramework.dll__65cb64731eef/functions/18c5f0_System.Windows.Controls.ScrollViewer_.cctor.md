# System.Windows.Controls.ScrollViewer::.cctor

- ea: `0x18c5f0`
- end: `0x18cb93`
- name: `System.Windows.Controls.ScrollViewer::.cctor`
- size: `1443`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x159e0`
- `0x15a20`
- `0x15a40`
- `0x19e60`
- `0x18bec0`
- `0x18c0a0`
- `0x24e850`

## string_xrefs

- `0x18c693`: `ComputedHorizontalScrollBarVisibility`
- `0x18c6d0`: `ComputedVerticalScrollBarVisibility`

## pseudocode

```c

```

## disassembly

```asm
0x18c5f0  ldstr    aCancontentscro// "CanContentScroll"
0x18c5f5  ldtoken  [mscorlib]System.Boolean
0x18c5fa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18c5ff  ldtoken  System.Windows.Controls.ScrollViewer
0x18c604  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18c609  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::FalseBox
0x18c60e  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x18c613  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x18c618  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ScrollViewer::CanContentScrollProperty
0x18c61d  ldstr    aHorizontalscro_2// "HorizontalScrollBarVisibility"
0x18c622  ldtoken  System.Windows.Controls.ScrollBarVisibility
0x18c627  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18c62c  ldtoken  System.Windows.Controls.ScrollViewer
0x18c631  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18c636  ldc.i4.0
0x18c637  box      System.Windows.Controls.ScrollBarVisibility
0x18c63c  ldc.i4.1
0x18c63d  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags)
0x18c642  ldnull
0x18c643  ldftn    bool System.Windows.Controls.ScrollViewer::IsValidScrollBarVisibility(object o)
0x18c649  newobj   instance void [WindowsBase]System.Windows.ValidateValueCallback::.ctor(object, native int)
0x18c64e  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata, class [WindowsBase]System.Windows.ValidateValueCallback)
0x18c653  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ScrollViewer::HorizontalScrollBarVisibilityProperty
0x18c658  ldstr    aVerticalscroll_2// "VerticalScrollBarVisibility"
0x18c65d  ldtoken  System.Windows.Controls.ScrollBarVisibility
0x18c662  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18c667  ldtoken  System.Windows.Controls.ScrollViewer
0x18c66c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18c671  ldc.i4.3
0x18c672  box      System.Windows.Controls.ScrollBarVisibility
0x18c677  ldc.i4.1
0x18c678  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags)
0x18c67d  ldnull
0x18c67e  ldftn    bool System.Windows.Controls.ScrollViewer::IsValidScrollBarVisibility(object o)
0x18c684  newobj   instance void [WindowsBase]System.Windows.ValidateValueCallback::.ctor(object, native int)
0x18c689  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata, class [WindowsBase]System.Windows.ValidateValueCallback)
0x18c68e  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ScrollViewer::VerticalScrollBarVisibilityProperty
0x18c693  ldstr    aComputedhorizo// "ComputedHorizontalScrollBarVisibility"
0x18c698  ldtoken  [PresentationCore]System.Windows.Visibility
0x18c69d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18c6a2  ldtoken  System.Windows.Controls.ScrollViewer
0x18c6a7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18c6ac  ldc.i4.0
0x18c6ad  box      [PresentationCore]System.Windows.Visibility
0x18c6b2  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x18c6b7  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x18c6bc  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ScrollViewer::ComputedHorizontalScrollBarVisibilityPropertyKey
0x18c6c1  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ScrollViewer::ComputedHorizontalScrollBarVisibilityPropertyKey
0x18c6c6  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x18c6cb  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ScrollViewer::ComputedHorizontalScrollBarVisibilityProperty
0x18c6d0  ldstr    aComputedvertic// "ComputedVerticalScrollBarVisibility"
0x18c6d5  ldtoken  [PresentationCore]System.Windows.Visibility
0x18c6da  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18c6df  ldtoken  System.Windows.Controls.ScrollViewer
0x18c6e4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18c6e9  ldc.i4.0
0x18c6ea  box      [PresentationCore]System.Windows.Visibility
0x18c6ef  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x18c6f4  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x18c6f9  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ScrollViewer::ComputedVerticalScrollBarVisibilityPropertyKey
0x18c6fe  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ScrollViewer::ComputedVerticalScrollBarVisibilityPropertyKey
0x18c703  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x18c708  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ScrollViewer::ComputedVerticalScrollBarVisibilityProperty
0x18c70d  ldstr    aVerticaloffset// "VerticalOffset"
0x18c712  ldtoken  [mscorlib]System.Double
0x18c717  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18c71c  ldtoken  System.Windows.Controls.ScrollViewer
0x18c721  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18c726  ldc.r8   0.0
0x18c72f  box      [mscorlib]System.Double
0x18c734  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x18c739  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x18c73e  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ScrollViewer::VerticalOffsetPropertyKey
0x18c743  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ScrollViewer::VerticalOffsetPropertyKey
0x18c748  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x18c74d  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ScrollViewer::VerticalOffsetProperty
0x18c752  ldstr    aHorizontaloffs// "HorizontalOffset"
0x18c757  ldtoken  [mscorlib]System.Double
0x18c75c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18c761  ldtoken  System.Windows.Controls.ScrollViewer
0x18c766  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18c76b  ldc.r8   0.0
0x18c774  box      [mscorlib]System.Double
0x18c779  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x18c77e  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x18c783  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ScrollViewer::HorizontalOffsetPropertyKey
0x18c788  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ScrollViewer::HorizontalOffsetPropertyKey
0x18c78d  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x18c792  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ScrollViewer::HorizontalOffsetProperty
0x18c797  ldstr    aContentvertica// "ContentVerticalOffset"
0x18c79c  ldtoken  [mscorlib]System.Double
0x18c7a1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18c7a6  ldtoken  System.Windows.Controls.ScrollViewer
0x18c7ab  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18c7b0  ldc.r8   0.0
0x18c7b9  box      [mscorlib]System.Double
0x18c7be  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x18c7c3  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x18c7c8  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ScrollViewer::ContentVerticalOffsetPropertyKey
0x18c7cd  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ScrollViewer::ContentVerticalOffsetPropertyKey
0x18c7d2  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x18c7d7  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ScrollViewer::ContentVerticalOffsetProperty
0x18c7dc  ldstr    aContenthorizon// "ContentHorizontalOffset"
0x18c7e1  ldtoken  [mscorlib]System.Double
0x18c7e6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18c7eb  ldtoken  System.Windows.Controls.ScrollViewer
0x18c7f0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18c7f5  ldc.r8   0.0
0x18c7fe  box      [mscorlib]System.Double
0x18c803  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x18c808  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x18c80d  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ScrollViewer::ContentHorizontalOffsetPropertyKey
0x18c812  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ScrollViewer::ContentHorizontalOffsetPropertyKey
0x18c817  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x18c81c  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ScrollViewer::ContentHorizontalOffsetProperty
0x18c821  ldstr    aExtentwidth// "ExtentWidth"
0x18c826  ldtoken  [mscorlib]System.Double
0x18c82b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18c830  ldtoken  System.Windows.Controls.ScrollViewer
0x18c835  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18c83a  ldc.r8   0.0
0x18c843  box      [mscorlib]System.Double
0x18c848  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x18c84d  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x18c852  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ScrollViewer::ExtentWidthPropertyKey
0x18c857  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ScrollViewer::ExtentWidthPropertyKey
0x18c85c  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x18c861  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ScrollViewer::ExtentWidthProperty
0x18c866  ldstr    aExtentheight// "ExtentHeight"
0x18c86b  ldtoken  [mscorlib]System.Double
0x18c870  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18c875  ldtoken  System.Windows.Controls.ScrollViewer
0x18c87a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18c87f  ldc.r8   0.0
0x18c888  box      [mscorlib]System.Double
0x18c88d  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x18c892  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x18c897  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ScrollViewer::ExtentHeightPropertyKey
0x18c89c  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ScrollViewer::ExtentHeightPropertyKey
0x18c8a1  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x18c8a6  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ScrollViewer::ExtentHeightProperty
0x18c8ab  ldstr    aScrollablewidt// "ScrollableWidth"
0x18c8b0  ldtoken  [mscorlib]System.Double
0x18c8b5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18c8ba  ldtoken  System.Windows.Controls.ScrollViewer
0x18c8bf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18c8c4  ldc.r8   0.0
0x18c8cd  box      [mscorlib]System.Double
0x18c8d2  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x18c8d7  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x18c8dc  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ScrollViewer::ScrollableWidthPropertyKey
0x18c8e1  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ScrollViewer::ScrollableWidthPropertyKey
0x18c8e6  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x18c8eb  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ScrollViewer::ScrollableWidthProperty
0x18c8f0  ldstr    aScrollableheig// "ScrollableHeight"
0x18c8f5  ldtoken  [mscorlib]System.Double
0x18c8fa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18c8ff  ldtoken  System.Windows.Controls.ScrollViewer
0x18c904  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18c909  ldc.r8   0.0
0x18c912  box      [mscorlib]System.Double
0x18c917  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x18c91c  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x18c921  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ScrollViewer::ScrollableHeightPropertyKey
0x18c926  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ScrollViewer::ScrollableHeightPropertyKey
0x18c92b  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x18c930  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ScrollViewer::ScrollableHeightProperty
0x18c935  ldstr    aViewportwidth// "ViewportWidth"
0x18c93a  ldtoken  [mscorlib]System.Double
0x18c93f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18c944  ldtoken  System.Windows.Controls.ScrollViewer
0x18c949  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18c94e  ldc.r8   0.0
0x18c957  box      [mscorlib]System.Double
0x18c95c  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x18c961  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x18c966  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ScrollViewer::ViewportWidthPropertyKey
0x18c96b  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ScrollViewer::ViewportWidthPropertyKey
0x18c970  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x18c975  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ScrollViewer::ViewportWidthProperty
0x18c97a  ldstr    aViewportheight// "ViewportHeight"
0x18c97f  ldtoken  [mscorlib]System.Double
0x18c984  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18c989  ldtoken  System.Windows.Controls.ScrollViewer
0x18c98e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18c993  ldc.r8   0.0
0x18c99c  box      [mscorlib]System.Double
0x18c9a1  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x18c9a6  call     class [WindowsBase]System.Windows.DependencyPropertyKey [WindowsBase]System.Windows.DependencyProperty::RegisterReadOnly(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x18c9ab  stsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ScrollViewer::ViewportHeightPropertyKey
0x18c9b0  ldsfld   class [WindowsBase]System.Windows.DependencyPropertyKey System.Windows.Controls.ScrollViewer::ViewportHeightPropertyKey
0x18c9b5  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyPropertyKey::get_DependencyProperty()
0x18c9ba  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ScrollViewer::ViewportHeightProperty
0x18c9bf  ldstr    aIsdeferredscro// "IsDeferredScrollingEnabled"
0x18c9c4  ldtoken  [mscorlib]System.Boolean
0x18c9c9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18c9ce  ldtoken  System.Windows.Controls.ScrollViewer
0x18c9d3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18c9d8  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::FalseBox
0x18c9dd  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x18c9e2  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x18c9e7  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ScrollViewer::IsDeferredScrollingEnabledProperty
0x18c9ec  ldstr    aScrollchanged// "ScrollChanged"
0x18c9f1  ldc.i4.1
0x18c9f2  ldtoken  System.Windows.Controls.ScrollChangedEventHandler
0x18c9f7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18c9fc  ldtoken  System.Windows.Controls.ScrollViewer
0x18ca01  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18ca06  call     class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.EventManager::RegisterRoutedEvent(string, valuetype [PresentationCore]System.Windows.RoutingStrategy, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x18ca0b  stsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.Controls.ScrollViewer::ScrollChangedEvent
0x18ca10  ldstr    aPanningmode// "PanningMode"
0x18ca15  ldtoken  System.Windows.Controls.PanningMode
0x18ca1a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18ca1f  ldtoken  System.Windows.Controls.ScrollViewer
0x18ca24  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18ca29  ldc.i4.0
0x18ca2a  box      System.Windows.Controls.PanningMode
0x18ca2f  ldnull
0x18ca30  ldftn    void System.Windows.Controls.ScrollViewer::OnPanningModeChanged(class [WindowsBase]System.Windows.DependencyObject d, valuetype [WindowsBase]System.Windows.DependencyPropertyChangedEventArgs e)
0x18ca36  newobj   instance void [WindowsBase]System.Windows.PropertyChangedCallback::.ctor(object, native int)
0x18ca3b  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, class [WindowsBase]System.Windows.PropertyChangedCallback propertyChangedCallback)
0x18ca40  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x18ca45  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ScrollViewer::PanningModeProperty
0x18ca4a  ldstr    aPanningdeceler// "PanningDeceleration"
0x18ca4f  ldtoken  [mscorlib]System.Double
0x18ca54  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18ca59  ldtoken  System.Windows.Controls.ScrollViewer
0x18ca5e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18ca63  ldc.r8   0.001
0x18ca6c  box      [mscorlib]System.Double
0x18ca71  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x18ca76  ldnull
0x18ca77  ldftn    bool System.Windows.Controls.ScrollViewer::CheckFiniteNonNegative(object value)
0x18ca7d  newobj   instance void [WindowsBase]System.Windows.ValidateValueCallback::.ctor(object, native int)
0x18ca82  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata, class [WindowsBase]System.Windows.ValidateValueCallback)
0x18ca87  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ScrollViewer::PanningDecelerationProperty
0x18ca8c  ldstr    aPanningratio// "PanningRatio"
0x18ca91  ldtoken  [mscorlib]System.Double
0x18ca96  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18ca9b  ldtoken  System.Windows.Controls.ScrollViewer
0x18caa0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18caa5  ldc.r8   1.0
0x18caae  box      [mscorlib]System.Double
0x18cab3  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x18cab8  ldnull
0x18cab9  ldftn    bool System.Windows.Controls.ScrollViewer::CheckFiniteNonNegative(object value)
0x18cabf  newobj   instance void [WindowsBase]System.Windows.ValidateValueCallback::.ctor(object, native int)
0x18cac4  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata, class [WindowsBase]System.Windows.ValidateValueCallback)
0x18cac9  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.ScrollViewer::PanningRatioProperty
0x18cace  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.FrameworkElement::DefaultStyleKeyProperty
0x18cad3  ldtoken  System.Windows.Controls.ScrollViewer
0x18cad8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18cadd  ldtoken  System.Windows.Controls.ScrollViewer
0x18cae2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18cae7  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x18caec  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x18caf1  ldtoken  System.Windows.Controls.ScrollViewer
0x18caf6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18cafb  call     class [WindowsBase]System.Windows.DependencyObjectType [WindowsBase]System.Windows.DependencyObjectType::FromSystemTypeInternal(class [mscorlib]System.Type)
0x18cb00  stsfld   class [WindowsBase]System.Windows.DependencyObjectType System.Windows.Controls.ScrollViewer::_dType
0x18cb05  call     void System.Windows.Controls.ScrollViewer::InitializeCommands()
0x18cb0a  call     class System.Windows.Controls.ControlTemplate System.Windows.Controls.ScrollViewer::CreateDefaultControlTemplate()
0x18cb0f  stloc.0
0x18cb10  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Control::TemplateProperty
0x18cb15  ldtoken  System.Windows.Controls.ScrollViewer
0x18cb1a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18cb1f  ldloc.0
0x18cb20  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x18cb25  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x18cb2a  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.Control::IsTabStopProperty
0x18cb2f  ldtoken  System.Windows.Controls.ScrollViewer
0x18cb34  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18cb39  ldsfld   object [WindowsBase]MS.Internal.KnownBoxes.BooleanBoxes::FalseBox
0x18cb3e  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x18cb43  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x18cb48  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Input.KeyboardNavigation::DirectionalNavigationProperty
0x18cb4d  ldtoken  System.Windows.Controls.ScrollViewer
0x18cb52  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18cb57  ldc.i4.5
0x18cb58  box      System.Windows.Input.KeyboardNavigationMode
0x18cb5d  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue)
0x18cb62  callvirt instance void [WindowsBase]System.Windows.DependencyProperty::OverrideMetadata(class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x18cb67  ldtoken  System.Windows.Controls.ScrollViewer
0x18cb6c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18cb71  ldsfld   class [PresentationCore]System.Windows.RoutedEvent System.Windows.FrameworkElement::RequestBringIntoViewEvent
0x18cb76  ldnull
0x18cb77  ldftn    void System.Windows.Controls.ScrollViewer::OnRequestBringIntoView(object sender, class System.Windows.RequestBringIntoViewEventArgs e)
0x18cb7d  newobj   instance void System.Windows.RequestBringIntoViewEventHandler::.ctor(object object, native int method)
0x18cb82  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate)
0x18cb87  ldc.i4   0x8000000
0x18cb8c  conv.i8
0x18cb8d  call     void MS.Internal.Telemetry.PresentationFramework.ControlsTraceLogger::AddControl(valuetype MS.Internal.Telemetry.PresentationFramework.TelemetryControls control)
0x18cb92  ret
```
