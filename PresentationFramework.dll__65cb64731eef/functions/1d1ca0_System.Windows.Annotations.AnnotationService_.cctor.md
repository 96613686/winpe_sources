# System.Windows.Annotations.AnnotationService::.cctor

- ea: `0x1d1ca0`
- end: `0x1d219a`
- name: `System.Windows.Annotations.AnnotationService::.cctor`
- size: `1274`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x15a40`
- `0x38c40`
- `0x1cff70`

## string_xrefs

- `0x1d1ca0`: `CreateHighlight`
- `0x1d1caa`: `CreateHighlight`
- `0x1d1cc4`: `CreateTextNote`
- `0x1d1cce`: `CreateTextStickyNote`
- `0x1d1ce8`: `CreateInkNote`
- `0x1d1cf2`: `CreateInkStickyNote`
- `0x1d1d30`: `DeleteNotes`
- `0x1d1d3a`: `DeleteStickyNotes`
- `0x1d1d54`: `DeleteAnnotations`
- `0x1d1d5e`: `DeleteAnnotations`
- `0x1d1dd9`: `Service`

## pseudocode

```c

```

## disassembly

```asm
0x1d1ca0  ldstr    aCreatehighligh// "CreateHighlight"
0x1d1ca5  call     string System.Windows.SR::Get(string id)
0x1d1caa  ldstr    aCreatehighligh// "CreateHighlight"
0x1d1caf  ldtoken  System.Windows.Annotations.AnnotationService
0x1d1cb4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d1cb9  ldnull
0x1d1cba  newobj   instance void [PresentationCore]System.Windows.Input.RoutedUICommand::.ctor(string, string, class [mscorlib]System.Type, class [PresentationCore]System.Windows.Input.InputGestureCollection)
0x1d1cbf  stsfld   class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Annotations.AnnotationService::CreateHighlightCommand
0x1d1cc4  ldstr    aCreatetextnote// "CreateTextNote"
0x1d1cc9  call     string System.Windows.SR::Get(string id)
0x1d1cce  ldstr    aCreatetextstic// "CreateTextStickyNote"
0x1d1cd3  ldtoken  System.Windows.Annotations.AnnotationService
0x1d1cd8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d1cdd  ldnull
0x1d1cde  newobj   instance void [PresentationCore]System.Windows.Input.RoutedUICommand::.ctor(string, string, class [mscorlib]System.Type, class [PresentationCore]System.Windows.Input.InputGestureCollection)
0x1d1ce3  stsfld   class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Annotations.AnnotationService::CreateTextStickyNoteCommand
0x1d1ce8  ldstr    aCreateinknote// "CreateInkNote"
0x1d1ced  call     string System.Windows.SR::Get(string id)
0x1d1cf2  ldstr    aCreateinkstick// "CreateInkStickyNote"
0x1d1cf7  ldtoken  System.Windows.Annotations.AnnotationService
0x1d1cfc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d1d01  ldnull
0x1d1d02  newobj   instance void [PresentationCore]System.Windows.Input.RoutedUICommand::.ctor(string, string, class [mscorlib]System.Type, class [PresentationCore]System.Windows.Input.InputGestureCollection)
0x1d1d07  stsfld   class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Annotations.AnnotationService::CreateInkStickyNoteCommand
0x1d1d0c  ldstr    aClearhighlight// "ClearHighlight"
0x1d1d11  call     string System.Windows.SR::Get(string id)
0x1d1d16  ldstr    aClearhighlight_0// "ClearHighlights"
0x1d1d1b  ldtoken  System.Windows.Annotations.AnnotationService
0x1d1d20  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d1d25  ldnull
0x1d1d26  newobj   instance void [PresentationCore]System.Windows.Input.RoutedUICommand::.ctor(string, string, class [mscorlib]System.Type, class [PresentationCore]System.Windows.Input.InputGestureCollection)
0x1d1d2b  stsfld   class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Annotations.AnnotationService::ClearHighlightsCommand
0x1d1d30  ldstr    aDeletenotes// "DeleteNotes"
0x1d1d35  call     string System.Windows.SR::Get(string id)
0x1d1d3a  ldstr    aDeletestickyno// "DeleteStickyNotes"
0x1d1d3f  ldtoken  System.Windows.Annotations.AnnotationService
0x1d1d44  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d1d49  ldnull
0x1d1d4a  newobj   instance void [PresentationCore]System.Windows.Input.RoutedUICommand::.ctor(string, string, class [mscorlib]System.Type, class [PresentationCore]System.Windows.Input.InputGestureCollection)
0x1d1d4f  stsfld   class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Annotations.AnnotationService::DeleteStickyNotesCommand
0x1d1d54  ldstr    aDeleteannotati// "DeleteAnnotations"
0x1d1d59  call     string System.Windows.SR::Get(string id)
0x1d1d5e  ldstr    aDeleteannotati// "DeleteAnnotations"
0x1d1d63  ldtoken  System.Windows.Annotations.AnnotationService
0x1d1d68  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d1d6d  ldnull
0x1d1d6e  newobj   instance void [PresentationCore]System.Windows.Input.RoutedUICommand::.ctor(string, string, class [mscorlib]System.Type, class [PresentationCore]System.Windows.Input.InputGestureCollection)
0x1d1d73  stsfld   class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Annotations.AnnotationService::DeleteAnnotationsCommand
0x1d1d78  ldstr    aChooser// "Chooser"
0x1d1d7d  ldtoken  System.Windows.Annotations.AnnotationComponentChooser
0x1d1d82  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d1d87  ldtoken  System.Windows.Annotations.AnnotationService
0x1d1d8c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d1d91  newobj   instance void System.Windows.Annotations.AnnotationComponentChooser::.ctor()
0x1d1d96  ldc.i4.s 0x60
0x1d1d98  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags)
0x1d1d9d  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1d1da2  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Annotations.AnnotationService::ChooserProperty
0x1d1da7  ldsfld   class [WindowsBase]System.Windows.DependencyProperty MS.Internal.Annotations.Anchoring.LocatorManager::SubTreeProcessorIdProperty
0x1d1dac  ldtoken  System.Windows.Annotations.AnnotationService
0x1d1db1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d1db6  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::AddOwner(class [mscorlib]System.Type)
0x1d1dbb  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Annotations.AnnotationService::SubTreeProcessorIdProperty
0x1d1dc0  ldsfld   class [WindowsBase]System.Windows.DependencyProperty MS.Internal.Annotations.Anchoring.DataIdProcessor::DataIdProperty
0x1d1dc5  ldtoken  System.Windows.Annotations.AnnotationService
0x1d1dca  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d1dcf  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::AddOwner(class [mscorlib]System.Type)
0x1d1dd4  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Annotations.AnnotationService::DataIdProperty
0x1d1dd9  ldstr    aService_0// "Service"
0x1d1dde  ldtoken  System.Windows.Annotations.AnnotationService
0x1d1de3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d1de8  ldtoken  System.Windows.Annotations.AnnotationService
0x1d1ded  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d1df2  ldnull
0x1d1df3  ldc.i4.s 0x60
0x1d1df5  newobj   instance void System.Windows.FrameworkPropertyMetadata::.ctor(object defaultValue, valuetype System.Windows.FrameworkPropertyMetadataOptions flags)
0x1d1dfa  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type, class [WindowsBase]System.Windows.PropertyMetadata)
0x1d1dff  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Annotations.AnnotationService::ServiceProperty
0x1d1e04  ldstr    aAttachedannota_2// "AttachedAnnotations"
0x1d1e09  ldtoken  class [mscorlib]System.Collections.Generic.IList`1<class MS.Internal.Annotations.IAttachedAnnotation>
0x1d1e0e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d1e13  ldtoken  System.Windows.Annotations.AnnotationService
0x1d1e18  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d1e1d  call     class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.DependencyProperty::RegisterAttached(string, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1d1e22  stsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Annotations.AnnotationService::AttachedAnnotationsProperty
0x1d1e27  ldtoken  System.Windows.Controls.Primitives.DocumentViewerBase
0x1d1e2c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d1e31  ldsfld   class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Annotations.AnnotationService::CreateHighlightCommand
0x1d1e36  ldnull
0x1d1e37  ldftn    void System.Windows.Annotations.AnnotationHelper::OnCreateHighlightCommand(object sender, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs e)
0x1d1e3d  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x1d1e42  ldnull
0x1d1e43  ldftn    void System.Windows.Annotations.AnnotationHelper::OnQueryCreateHighlightCommand(object sender, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs e)
0x1d1e49  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x1d1e4e  newobj   instance void [PresentationCore]System.Windows.Input.CommandBinding::.ctor(class [System]System.Windows.Input.ICommand, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler)
0x1d1e53  call     void [PresentationCore]System.Windows.Input.CommandManager::RegisterClassCommandBinding(class [mscorlib]System.Type, class [PresentationCore]System.Windows.Input.CommandBinding)
0x1d1e58  ldtoken  System.Windows.Controls.Primitives.DocumentViewerBase
0x1d1e5d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d1e62  ldsfld   class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Annotations.AnnotationService::CreateTextStickyNoteCommand
0x1d1e67  ldnull
0x1d1e68  ldftn    void System.Windows.Annotations.AnnotationHelper::OnCreateTextStickyNoteCommand(object sender, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs e)
0x1d1e6e  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x1d1e73  ldnull
0x1d1e74  ldftn    void System.Windows.Annotations.AnnotationHelper::OnQueryCreateTextStickyNoteCommand(object sender, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs e)
0x1d1e7a  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x1d1e7f  newobj   instance void [PresentationCore]System.Windows.Input.CommandBinding::.ctor(class [System]System.Windows.Input.ICommand, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler)
0x1d1e84  call     void [PresentationCore]System.Windows.Input.CommandManager::RegisterClassCommandBinding(class [mscorlib]System.Type, class [PresentationCore]System.Windows.Input.CommandBinding)
0x1d1e89  ldtoken  System.Windows.Controls.Primitives.DocumentViewerBase
0x1d1e8e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d1e93  ldsfld   class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Annotations.AnnotationService::CreateInkStickyNoteCommand
0x1d1e98  ldnull
0x1d1e99  ldftn    void System.Windows.Annotations.AnnotationHelper::OnCreateInkStickyNoteCommand(object sender, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs e)
0x1d1e9f  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x1d1ea4  ldnull
0x1d1ea5  ldftn    void System.Windows.Annotations.AnnotationHelper::OnQueryCreateInkStickyNoteCommand(object sender, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs e)
0x1d1eab  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x1d1eb0  newobj   instance void [PresentationCore]System.Windows.Input.CommandBinding::.ctor(class [System]System.Windows.Input.ICommand, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler)
0x1d1eb5  call     void [PresentationCore]System.Windows.Input.CommandManager::RegisterClassCommandBinding(class [mscorlib]System.Type, class [PresentationCore]System.Windows.Input.CommandBinding)
0x1d1eba  ldtoken  System.Windows.Controls.Primitives.DocumentViewerBase
0x1d1ebf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d1ec4  ldsfld   class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Annotations.AnnotationService::ClearHighlightsCommand
0x1d1ec9  ldnull
0x1d1eca  ldftn    void System.Windows.Annotations.AnnotationHelper::OnClearHighlightsCommand(object sender, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs e)
0x1d1ed0  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x1d1ed5  ldnull
0x1d1ed6  ldftn    void System.Windows.Annotations.AnnotationHelper::OnQueryClearHighlightsCommand(object sender, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs e)
0x1d1edc  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x1d1ee1  newobj   instance void [PresentationCore]System.Windows.Input.CommandBinding::.ctor(class [System]System.Windows.Input.ICommand, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler)
0x1d1ee6  call     void [PresentationCore]System.Windows.Input.CommandManager::RegisterClassCommandBinding(class [mscorlib]System.Type, class [PresentationCore]System.Windows.Input.CommandBinding)
0x1d1eeb  ldtoken  System.Windows.Controls.Primitives.DocumentViewerBase
0x1d1ef0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d1ef5  ldsfld   class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Annotations.AnnotationService::DeleteStickyNotesCommand
0x1d1efa  ldnull
0x1d1efb  ldftn    void System.Windows.Annotations.AnnotationHelper::OnDeleteStickyNotesCommand(object sender, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs e)
0x1d1f01  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x1d1f06  ldnull
0x1d1f07  ldftn    void System.Windows.Annotations.AnnotationHelper::OnQueryDeleteStickyNotesCommand(object sender, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs e)
0x1d1f0d  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x1d1f12  newobj   instance void [PresentationCore]System.Windows.Input.CommandBinding::.ctor(class [System]System.Windows.Input.ICommand, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler)
0x1d1f17  call     void [PresentationCore]System.Windows.Input.CommandManager::RegisterClassCommandBinding(class [mscorlib]System.Type, class [PresentationCore]System.Windows.Input.CommandBinding)
0x1d1f1c  ldtoken  System.Windows.Controls.Primitives.DocumentViewerBase
0x1d1f21  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d1f26  ldsfld   class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Annotations.AnnotationService::DeleteAnnotationsCommand
0x1d1f2b  ldnull
0x1d1f2c  ldftn    void System.Windows.Annotations.AnnotationHelper::OnDeleteAnnotationsCommand(object sender, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs e)
0x1d1f32  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x1d1f37  ldnull
0x1d1f38  ldftn    void System.Windows.Annotations.AnnotationHelper::OnQueryDeleteAnnotationsCommand(object sender, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs e)
0x1d1f3e  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x1d1f43  newobj   instance void [PresentationCore]System.Windows.Input.CommandBinding::.ctor(class [System]System.Windows.Input.ICommand, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler)
0x1d1f48  call     void [PresentationCore]System.Windows.Input.CommandManager::RegisterClassCommandBinding(class [mscorlib]System.Type, class [PresentationCore]System.Windows.Input.CommandBinding)
0x1d1f4d  ldtoken  System.Windows.Controls.FlowDocumentScrollViewer
0x1d1f52  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d1f57  ldsfld   class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Annotations.AnnotationService::CreateHighlightCommand
0x1d1f5c  ldnull
0x1d1f5d  ldftn    void System.Windows.Annotations.AnnotationHelper::OnCreateHighlightCommand(object sender, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs e)
0x1d1f63  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x1d1f68  ldnull
0x1d1f69  ldftn    void System.Windows.Annotations.AnnotationHelper::OnQueryCreateHighlightCommand(object sender, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs e)
0x1d1f6f  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x1d1f74  newobj   instance void [PresentationCore]System.Windows.Input.CommandBinding::.ctor(class [System]System.Windows.Input.ICommand, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler)
0x1d1f79  call     void [PresentationCore]System.Windows.Input.CommandManager::RegisterClassCommandBinding(class [mscorlib]System.Type, class [PresentationCore]System.Windows.Input.CommandBinding)
0x1d1f7e  ldtoken  System.Windows.Controls.FlowDocumentScrollViewer
0x1d1f83  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d1f88  ldsfld   class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Annotations.AnnotationService::CreateTextStickyNoteCommand
0x1d1f8d  ldnull
0x1d1f8e  ldftn    void System.Windows.Annotations.AnnotationHelper::OnCreateTextStickyNoteCommand(object sender, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs e)
0x1d1f94  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x1d1f99  ldnull
0x1d1f9a  ldftn    void System.Windows.Annotations.AnnotationHelper::OnQueryCreateTextStickyNoteCommand(object sender, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs e)
0x1d1fa0  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x1d1fa5  newobj   instance void [PresentationCore]System.Windows.Input.CommandBinding::.ctor(class [System]System.Windows.Input.ICommand, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler)
0x1d1faa  call     void [PresentationCore]System.Windows.Input.CommandManager::RegisterClassCommandBinding(class [mscorlib]System.Type, class [PresentationCore]System.Windows.Input.CommandBinding)
0x1d1faf  ldtoken  System.Windows.Controls.FlowDocumentScrollViewer
0x1d1fb4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d1fb9  ldsfld   class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Annotations.AnnotationService::CreateInkStickyNoteCommand
0x1d1fbe  ldnull
0x1d1fbf  ldftn    void System.Windows.Annotations.AnnotationHelper::OnCreateInkStickyNoteCommand(object sender, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs e)
0x1d1fc5  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x1d1fca  ldnull
0x1d1fcb  ldftn    void System.Windows.Annotations.AnnotationHelper::OnQueryCreateInkStickyNoteCommand(object sender, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs e)
0x1d1fd1  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x1d1fd6  newobj   instance void [PresentationCore]System.Windows.Input.CommandBinding::.ctor(class [System]System.Windows.Input.ICommand, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler)
0x1d1fdb  call     void [PresentationCore]System.Windows.Input.CommandManager::RegisterClassCommandBinding(class [mscorlib]System.Type, class [PresentationCore]System.Windows.Input.CommandBinding)
0x1d1fe0  ldtoken  System.Windows.Controls.FlowDocumentScrollViewer
0x1d1fe5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d1fea  ldsfld   class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Annotations.AnnotationService::ClearHighlightsCommand
0x1d1fef  ldnull
0x1d1ff0  ldftn    void System.Windows.Annotations.AnnotationHelper::OnClearHighlightsCommand(object sender, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs e)
0x1d1ff6  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x1d1ffb  ldnull
0x1d1ffc  ldftn    void System.Windows.Annotations.AnnotationHelper::OnQueryClearHighlightsCommand(object sender, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs e)
0x1d2002  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x1d2007  newobj   instance void [PresentationCore]System.Windows.Input.CommandBinding::.ctor(class [System]System.Windows.Input.ICommand, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler)
0x1d200c  call     void [PresentationCore]System.Windows.Input.CommandManager::RegisterClassCommandBinding(class [mscorlib]System.Type, class [PresentationCore]System.Windows.Input.CommandBinding)
0x1d2011  ldtoken  System.Windows.Controls.FlowDocumentScrollViewer
0x1d2016  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d201b  ldsfld   class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Annotations.AnnotationService::DeleteStickyNotesCommand
0x1d2020  ldnull
0x1d2021  ldftn    void System.Windows.Annotations.AnnotationHelper::OnDeleteStickyNotesCommand(object sender, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs e)
0x1d2027  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x1d202c  ldnull
0x1d202d  ldftn    void System.Windows.Annotations.AnnotationHelper::OnQueryDeleteStickyNotesCommand(object sender, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs e)
0x1d2033  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x1d2038  newobj   instance void [PresentationCore]System.Windows.Input.CommandBinding::.ctor(class [System]System.Windows.Input.ICommand, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler)
0x1d203d  call     void [PresentationCore]System.Windows.Input.CommandManager::RegisterClassCommandBinding(class [mscorlib]System.Type, class [PresentationCore]System.Windows.Input.CommandBinding)
0x1d2042  ldtoken  System.Windows.Controls.FlowDocumentScrollViewer
0x1d2047  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d204c  ldsfld   class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Annotations.AnnotationService::DeleteAnnotationsCommand
0x1d2051  ldnull
0x1d2052  ldftn    void System.Windows.Annotations.AnnotationHelper::OnDeleteAnnotationsCommand(object sender, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs e)
0x1d2058  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x1d205d  ldnull
0x1d205e  ldftn    void System.Windows.Annotations.AnnotationHelper::OnQueryDeleteAnnotationsCommand(object sender, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs e)
0x1d2064  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x1d2069  newobj   instance void [PresentationCore]System.Windows.Input.CommandBinding::.ctor(class [System]System.Windows.Input.ICommand, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler)
0x1d206e  call     void [PresentationCore]System.Windows.Input.CommandManager::RegisterClassCommandBinding(class [mscorlib]System.Type, class [PresentationCore]System.Windows.Input.CommandBinding)
0x1d2073  ldtoken  System.Windows.Controls.FlowDocumentReader
0x1d2078  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d207d  ldsfld   class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Annotations.AnnotationService::CreateHighlightCommand
0x1d2082  ldnull
0x1d2083  ldftn    void System.Windows.Annotations.AnnotationHelper::OnCreateHighlightCommand(object sender, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs e)
0x1d2089  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x1d208e  ldnull
0x1d208f  ldftn    void System.Windows.Annotations.AnnotationHelper::OnQueryCreateHighlightCommand(object sender, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs e)
0x1d2095  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x1d209a  newobj   instance void [PresentationCore]System.Windows.Input.CommandBinding::.ctor(class [System]System.Windows.Input.ICommand, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler)
0x1d209f  call     void [PresentationCore]System.Windows.Input.CommandManager::RegisterClassCommandBinding(class [mscorlib]System.Type, class [PresentationCore]System.Windows.Input.CommandBinding)
0x1d20a4  ldtoken  System.Windows.Controls.FlowDocumentReader
0x1d20a9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d20ae  ldsfld   class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Annotations.AnnotationService::CreateTextStickyNoteCommand
0x1d20b3  ldnull
0x1d20b4  ldftn    void System.Windows.Annotations.AnnotationHelper::OnCreateTextStickyNoteCommand(object sender, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs e)
0x1d20ba  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x1d20bf  ldnull
0x1d20c0  ldftn    void System.Windows.Annotations.AnnotationHelper::OnQueryCreateTextStickyNoteCommand(object sender, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs e)
0x1d20c6  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x1d20cb  newobj   instance void [PresentationCore]System.Windows.Input.CommandBinding::.ctor(class [System]System.Windows.Input.ICommand, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler)
0x1d20d0  call     void [PresentationCore]System.Windows.Input.CommandManager::RegisterClassCommandBinding(class [mscorlib]System.Type, class [PresentationCore]System.Windows.Input.CommandBinding)
0x1d20d5  ldtoken  System.Windows.Controls.FlowDocumentReader
0x1d20da  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d20df  ldsfld   class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Annotations.AnnotationService::CreateInkStickyNoteCommand
0x1d20e4  ldnull
0x1d20e5  ldftn    void System.Windows.Annotations.AnnotationHelper::OnCreateInkStickyNoteCommand(object sender, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs e)
0x1d20eb  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x1d20f0  ldnull
0x1d20f1  ldftn    void System.Windows.Annotations.AnnotationHelper::OnQueryCreateInkStickyNoteCommand(object sender, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs e)
0x1d20f7  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x1d20fc  newobj   instance void [PresentationCore]System.Windows.Input.CommandBinding::.ctor(class [System]System.Windows.Input.ICommand, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler)
0x1d2101  call     void [PresentationCore]System.Windows.Input.CommandManager::RegisterClassCommandBinding(class [mscorlib]System.Type, class [PresentationCore]System.Windows.Input.CommandBinding)
0x1d2106  ldtoken  System.Windows.Controls.FlowDocumentReader
0x1d210b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d2110  ldsfld   class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Annotations.AnnotationService::ClearHighlightsCommand
0x1d2115  ldnull
0x1d2116  ldftn    void System.Windows.Annotations.AnnotationHelper::OnClearHighlightsCommand(object sender, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs e)
0x1d211c  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x1d2121  ldnull
0x1d2122  ldftn    void System.Windows.Annotations.AnnotationHelper::OnQueryClearHighlightsCommand(object sender, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs e)
0x1d2128  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x1d212d  newobj   instance void [PresentationCore]System.Windows.Input.CommandBinding::.ctor(class [System]System.Windows.Input.ICommand, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler)
0x1d2132  call     void [PresentationCore]System.Windows.Input.CommandManager::RegisterClassCommandBinding(class [mscorlib]System.Type, class [PresentationCore]System.Windows.Input.CommandBinding)
0x1d2137  ldtoken  System.Windows.Controls.FlowDocumentReader
0x1d213c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d2141  ldsfld   class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Annotations.AnnotationService::DeleteStickyNotesCommand
0x1d2146  ldnull
0x1d2147  ldftn    void System.Windows.Annotations.AnnotationHelper::OnDeleteStickyNotesCommand(object sender, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs e)
0x1d214d  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x1d2152  ldnull
0x1d2153  ldftn    void System.Windows.Annotations.AnnotationHelper::OnQueryDeleteStickyNotesCommand(object sender, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs e)
0x1d2159  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x1d215e  newobj   instance void [PresentationCore]System.Windows.Input.CommandBinding::.ctor(class [System]System.Windows.Input.ICommand, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler)
0x1d2163  call     void [PresentationCore]System.Windows.Input.CommandManager::RegisterClassCommandBinding(class [mscorlib]System.Type, class [PresentationCore]System.Windows.Input.CommandBinding)
0x1d2168  ldtoken  System.Windows.Controls.FlowDocumentReader
0x1d216d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d2172  ldsfld   class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Annotations.AnnotationService::DeleteAnnotationsCommand
0x1d2177  ldnull
0x1d2178  ldftn    void System.Windows.Annotations.AnnotationHelper::OnDeleteAnnotationsCommand(object sender, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs e)
0x1d217e  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x1d2183  ldnull
0x1d2184  ldftn    void System.Windows.Annotations.AnnotationHelper::OnQueryDeleteAnnotationsCommand(object sender, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs e)
0x1d218a  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x1d218f  newobj   instance void [PresentationCore]System.Windows.Input.CommandBinding::.ctor(class [System]System.Windows.Input.ICommand, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler)
0x1d2194  call     void [PresentationCore]System.Windows.Input.CommandManager::RegisterClassCommandBinding(class [mscorlib]System.Type, class [PresentationCore]System.Windows.Input.CommandBinding)
0x1d2199  ret
```
