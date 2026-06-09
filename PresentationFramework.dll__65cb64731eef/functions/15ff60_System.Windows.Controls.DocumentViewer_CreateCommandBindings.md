# System.Windows.Controls.DocumentViewer::CreateCommandBindings

- ea: `0x15ff60`
- end: `0x1602db`
- name: `System.Windows.Controls.DocumentViewer::CreateCommandBindings`
- size: `891`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x15ee50`

## callees

- `0x38c40`
- `0x15f4f0`
- `0x23e9b0`
- `0x23e9c0`
- `0x23e9e0`
- `0x23ea20`

## string_xrefs

- `0x15ff7a`: `DocumentViewerViewThumbnailsCommandText`
- `0x15ff84`: `ViewThumbnailsCommand`
- `0x15ffb4`: `DocumentViewerViewFitToWidthCommandText`
- `0x15ffbe`: `FitToWidthCommand`
- `0x15fff6`: `DocumentViewerViewFitToHeightCommandText`
- `0x160000`: `FitToHeightCommand`
- `0x160030`: `DocumentViewerViewFitToMaxPagesAcrossCommandText`
- `0x16003a`: `FitToMaxPagesAcrossCommand`

## pseudocode

```c

```

## disassembly

```asm
0x15ff60  ldnull
0x15ff61  ldftn    void System.Windows.Controls.DocumentViewer::ExecutedRoutedEventHandler(object target, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs args)
0x15ff67  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x15ff6c  stloc.0
0x15ff6d  ldnull
0x15ff6e  ldftn    void System.Windows.Controls.DocumentViewer::QueryEnabledHandler(object target, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs args)
0x15ff74  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x15ff79  stloc.1
0x15ff7a  ldstr    aDocumentviewer_2// "DocumentViewerViewThumbnailsCommandText"
0x15ff7f  call     string System.Windows.SR::Get(string id)
0x15ff84  ldstr    aViewthumbnails// "ViewThumbnailsCommand"
0x15ff89  ldtoken  System.Windows.Controls.DocumentViewer
0x15ff8e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15ff93  ldnull
0x15ff94  newobj   instance void [PresentationCore]System.Windows.Input.RoutedUICommand::.ctor(string, string, class [mscorlib]System.Type, class [PresentationCore]System.Windows.Input.InputGestureCollection)
0x15ff99  stsfld   class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Controls.DocumentViewer::_viewThumbnailsCommand
0x15ff9e  ldtoken  System.Windows.Controls.DocumentViewer
0x15ffa3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15ffa8  ldsfld   class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Controls.DocumentViewer::_viewThumbnailsCommand
0x15ffad  ldloc.0
0x15ffae  ldloc.1
0x15ffaf  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler)
0x15ffb4  ldstr    aDocumentviewer_3// "DocumentViewerViewFitToWidthCommandText"
0x15ffb9  call     string System.Windows.SR::Get(string id)
0x15ffbe  ldstr    aFittowidthcomm// "FitToWidthCommand"
0x15ffc3  ldtoken  System.Windows.Controls.DocumentViewer
0x15ffc8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15ffcd  ldnull
0x15ffce  newobj   instance void [PresentationCore]System.Windows.Input.RoutedUICommand::.ctor(string, string, class [mscorlib]System.Type, class [PresentationCore]System.Windows.Input.InputGestureCollection)
0x15ffd3  stsfld   class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Controls.DocumentViewer::_fitToWidthCommand
0x15ffd8  ldtoken  System.Windows.Controls.DocumentViewer
0x15ffdd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15ffe2  ldsfld   class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Controls.DocumentViewer::_fitToWidthCommand
0x15ffe7  ldloc.0
0x15ffe8  ldloc.1
0x15ffe9  ldc.i4.s 0x24
0x15ffeb  ldc.i4.2
0x15ffec  newobj   instance void [PresentationCore]System.Windows.Input.KeyGesture::.ctor(valuetype [WindowsBase]System.Windows.Input.Key, valuetype [WindowsBase]System.Windows.Input.ModifierKeys)
0x15fff1  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, class [PresentationCore]System.Windows.Input.InputGesture inputGesture)
0x15fff6  ldstr    aDocumentviewer_4// "DocumentViewerViewFitToHeightCommandTex"...
0x15fffb  call     string System.Windows.SR::Get(string id)
0x160000  ldstr    aFittoheightcom// "FitToHeightCommand"
0x160005  ldtoken  System.Windows.Controls.DocumentViewer
0x16000a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16000f  ldnull
0x160010  newobj   instance void [PresentationCore]System.Windows.Input.RoutedUICommand::.ctor(string, string, class [mscorlib]System.Type, class [PresentationCore]System.Windows.Input.InputGestureCollection)
0x160015  stsfld   class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Controls.DocumentViewer::_fitToHeightCommand
0x16001a  ldtoken  System.Windows.Controls.DocumentViewer
0x16001f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x160024  ldsfld   class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Controls.DocumentViewer::_fitToHeightCommand
0x160029  ldloc.0
0x16002a  ldloc.1
0x16002b  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler)
0x160030  ldstr    aDocumentviewer_5// "DocumentViewerViewFitToMaxPagesAcrossCo"...
0x160035  call     string System.Windows.SR::Get(string id)
0x16003a  ldstr    aFittomaxpagesa// "FitToMaxPagesAcrossCommand"
0x16003f  ldtoken  System.Windows.Controls.DocumentViewer
0x160044  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x160049  ldnull
0x16004a  newobj   instance void [PresentationCore]System.Windows.Input.RoutedUICommand::.ctor(string, string, class [mscorlib]System.Type, class [PresentationCore]System.Windows.Input.InputGestureCollection)
0x16004f  stsfld   class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Controls.DocumentViewer::_fitToMaxPagesAcrossCommand
0x160054  ldtoken  System.Windows.Controls.DocumentViewer
0x160059  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16005e  ldsfld   class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Controls.DocumentViewer::_fitToMaxPagesAcrossCommand
0x160063  ldloc.0
0x160064  ldloc.1
0x160065  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler)
0x16006a  ldtoken  System.Windows.Controls.DocumentViewer
0x16006f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x160074  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.ApplicationCommands::get_Find()
0x160079  ldloc.0
0x16007a  ldloc.1
0x16007b  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler)
0x160080  ldtoken  System.Windows.Controls.DocumentViewer
0x160085  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16008a  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.ComponentCommands::get_ScrollPageUp()
0x16008f  ldloc.0
0x160090  ldloc.1
0x160091  ldc.i4.s 0x13
0x160093  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, valuetype [WindowsBase]System.Windows.Input.Key key)
0x160098  ldtoken  System.Windows.Controls.DocumentViewer
0x16009d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1600a2  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.ComponentCommands::get_ScrollPageDown()
0x1600a7  ldloc.0
0x1600a8  ldloc.1
0x1600a9  ldc.i4.s 0x14
0x1600ab  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, valuetype [WindowsBase]System.Windows.Input.Key key)
0x1600b0  ldtoken  System.Windows.Controls.DocumentViewer
0x1600b5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1600ba  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.ComponentCommands::get_ScrollPageLeft()
0x1600bf  ldloc.0
0x1600c0  ldloc.1
0x1600c1  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler)
0x1600c6  ldtoken  System.Windows.Controls.DocumentViewer
0x1600cb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1600d0  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.ComponentCommands::get_ScrollPageRight()
0x1600d5  ldloc.0
0x1600d6  ldloc.1
0x1600d7  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler)
0x1600dc  ldtoken  System.Windows.Controls.DocumentViewer
0x1600e1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1600e6  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.ComponentCommands::get_MoveUp()
0x1600eb  ldloc.0
0x1600ec  ldloc.1
0x1600ed  ldc.i4.s 0x18
0x1600ef  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, valuetype [WindowsBase]System.Windows.Input.Key key)
0x1600f4  ldtoken  System.Windows.Controls.DocumentViewer
0x1600f9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1600fe  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.ComponentCommands::get_MoveDown()
0x160103  ldloc.0
0x160104  ldloc.1
0x160105  ldc.i4.s 0x1A
0x160107  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, valuetype [WindowsBase]System.Windows.Input.Key key)
0x16010c  ldtoken  System.Windows.Controls.DocumentViewer
0x160111  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x160116  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.ComponentCommands::get_MoveLeft()
0x16011b  ldloc.0
0x16011c  ldloc.1
0x16011d  ldc.i4.s 0x17
0x16011f  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, valuetype [WindowsBase]System.Windows.Input.Key key)
0x160124  ldtoken  System.Windows.Controls.DocumentViewer
0x160129  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16012e  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.ComponentCommands::get_MoveRight()
0x160133  ldloc.0
0x160134  ldloc.1
0x160135  ldc.i4.s 0x19
0x160137  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, valuetype [WindowsBase]System.Windows.Input.Key key)
0x16013c  ldtoken  System.Windows.Controls.DocumentViewer
0x160141  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x160146  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.NavigationCommands::get_Zoom()
0x16014b  ldloc.0
0x16014c  ldloc.1
0x16014d  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler)
0x160152  ldtoken  System.Windows.Controls.DocumentViewer
0x160157  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16015c  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.NavigationCommands::get_IncreaseZoom()
0x160161  ldloc.0
0x160162  ldloc.1
0x160163  ldc.i4.s 0x55
0x160165  ldc.i4.2
0x160166  newobj   instance void [PresentationCore]System.Windows.Input.KeyGesture::.ctor(valuetype [WindowsBase]System.Windows.Input.Key, valuetype [WindowsBase]System.Windows.Input.ModifierKeys)
0x16016b  ldc.i4.s 0x55
0x16016d  ldc.i4.6
0x16016e  newobj   instance void [PresentationCore]System.Windows.Input.KeyGesture::.ctor(valuetype [WindowsBase]System.Windows.Input.Key, valuetype [WindowsBase]System.Windows.Input.ModifierKeys)
0x160173  ldc.i4   0x8D
0x160178  ldc.i4.2
0x160179  newobj   instance void [PresentationCore]System.Windows.Input.KeyGesture::.ctor(valuetype [WindowsBase]System.Windows.Input.Key, valuetype [WindowsBase]System.Windows.Input.ModifierKeys)
0x16017e  ldc.i4   0x8D
0x160183  ldc.i4.6
0x160184  newobj   instance void [PresentationCore]System.Windows.Input.KeyGesture::.ctor(valuetype [WindowsBase]System.Windows.Input.Key, valuetype [WindowsBase]System.Windows.Input.ModifierKeys)
0x160189  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, class [PresentationCore]System.Windows.Input.InputGesture inputGesture, class [PresentationCore]System.Windows.Input.InputGesture inputGesture2, class [PresentationCore]System.Windows.Input.InputGesture inputGesture3, class [PresentationCore]System.Windows.Input.InputGesture inputGesture4)
0x16018e  ldtoken  System.Windows.Controls.DocumentViewer
0x160193  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x160198  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.NavigationCommands::get_DecreaseZoom()
0x16019d  ldloc.0
0x16019e  ldloc.1
0x16019f  ldc.i4.s 0x57
0x1601a1  ldc.i4.2
0x1601a2  newobj   instance void [PresentationCore]System.Windows.Input.KeyGesture::.ctor(valuetype [WindowsBase]System.Windows.Input.Key, valuetype [WindowsBase]System.Windows.Input.ModifierKeys)
0x1601a7  ldc.i4.s 0x57
0x1601a9  ldc.i4.6
0x1601aa  newobj   instance void [PresentationCore]System.Windows.Input.KeyGesture::.ctor(valuetype [WindowsBase]System.Windows.Input.Key, valuetype [WindowsBase]System.Windows.Input.ModifierKeys)
0x1601af  ldc.i4   0x8F
0x1601b4  ldc.i4.2
0x1601b5  newobj   instance void [PresentationCore]System.Windows.Input.KeyGesture::.ctor(valuetype [WindowsBase]System.Windows.Input.Key, valuetype [WindowsBase]System.Windows.Input.ModifierKeys)
0x1601ba  ldc.i4   0x8F
0x1601bf  ldc.i4.6
0x1601c0  newobj   instance void [PresentationCore]System.Windows.Input.KeyGesture::.ctor(valuetype [WindowsBase]System.Windows.Input.Key, valuetype [WindowsBase]System.Windows.Input.ModifierKeys)
0x1601c5  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, class [PresentationCore]System.Windows.Input.InputGesture inputGesture, class [PresentationCore]System.Windows.Input.InputGesture inputGesture2, class [PresentationCore]System.Windows.Input.InputGesture inputGesture3, class [PresentationCore]System.Windows.Input.InputGesture inputGesture4)
0x1601ca  ldtoken  System.Windows.Controls.DocumentViewer
0x1601cf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1601d4  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.NavigationCommands::get_PreviousPage()
0x1601d9  ldloc.0
0x1601da  ldloc.1
0x1601db  ldc.i4.s 0x13
0x1601dd  ldc.i4.2
0x1601de  newobj   instance void [PresentationCore]System.Windows.Input.KeyGesture::.ctor(valuetype [WindowsBase]System.Windows.Input.Key, valuetype [WindowsBase]System.Windows.Input.ModifierKeys)
0x1601e3  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, class [PresentationCore]System.Windows.Input.InputGesture inputGesture)
0x1601e8  ldtoken  System.Windows.Controls.DocumentViewer
0x1601ed  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1601f2  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.NavigationCommands::get_NextPage()
0x1601f7  ldloc.0
0x1601f8  ldloc.1
0x1601f9  ldc.i4.s 0x14
0x1601fb  ldc.i4.2
0x1601fc  newobj   instance void [PresentationCore]System.Windows.Input.KeyGesture::.ctor(valuetype [WindowsBase]System.Windows.Input.Key, valuetype [WindowsBase]System.Windows.Input.ModifierKeys)
0x160201  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, class [PresentationCore]System.Windows.Input.InputGesture inputGesture)
0x160206  ldtoken  System.Windows.Controls.DocumentViewer
0x16020b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x160210  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.NavigationCommands::get_FirstPage()
0x160215  ldloc.0
0x160216  ldloc.1
0x160217  ldc.i4.s 0x16
0x160219  ldc.i4.2
0x16021a  newobj   instance void [PresentationCore]System.Windows.Input.KeyGesture::.ctor(valuetype [WindowsBase]System.Windows.Input.Key, valuetype [WindowsBase]System.Windows.Input.ModifierKeys)
0x16021f  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, class [PresentationCore]System.Windows.Input.InputGesture inputGesture)
0x160224  ldtoken  System.Windows.Controls.DocumentViewer
0x160229  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16022e  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.NavigationCommands::get_LastPage()
0x160233  ldloc.0
0x160234  ldloc.1
0x160235  ldc.i4.s 0x15
0x160237  ldc.i4.2
0x160238  newobj   instance void [PresentationCore]System.Windows.Input.KeyGesture::.ctor(valuetype [WindowsBase]System.Windows.Input.Key, valuetype [WindowsBase]System.Windows.Input.ModifierKeys)
0x16023d  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, class [PresentationCore]System.Windows.Input.InputGesture inputGesture)
0x160242  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.NavigationCommands::get_Zoom()
0x160247  ldc.i4.s 0x23
0x160249  ldc.i4.2
0x16024a  newobj   instance void [PresentationCore]System.Windows.Input.KeyGesture::.ctor(valuetype [WindowsBase]System.Windows.Input.Key, valuetype [WindowsBase]System.Windows.Input.ModifierKeys)
0x16024f  newobj   instance void [PresentationCore]System.Windows.Input.InputBinding::.ctor(class [System]System.Windows.Input.ICommand, class [PresentationCore]System.Windows.Input.InputGesture)
0x160254  stloc.2
0x160255  ldloc.2
0x160256  ldc.r8   100.0
0x16025f  box      [mscorlib]System.Double
0x160264  callvirt instance void [PresentationCore]System.Windows.Input.InputBinding::set_CommandParameter(object)
0x160269  ldtoken  System.Windows.Controls.DocumentViewer
0x16026e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x160273  ldloc.2
0x160274  call     void [PresentationCore]System.Windows.Input.CommandManager::RegisterClassInputBinding(class [mscorlib]System.Type, class [PresentationCore]System.Windows.Input.InputBinding)
0x160279  call     class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Controls.DocumentViewer::get_FitToMaxPagesAcrossCommand()
0x16027e  ldc.i4.s 0x25
0x160280  ldc.i4.2
0x160281  newobj   instance void [PresentationCore]System.Windows.Input.KeyGesture::.ctor(valuetype [WindowsBase]System.Windows.Input.Key, valuetype [WindowsBase]System.Windows.Input.ModifierKeys)
0x160286  newobj   instance void [PresentationCore]System.Windows.Input.InputBinding::.ctor(class [System]System.Windows.Input.ICommand, class [PresentationCore]System.Windows.Input.InputGesture)
0x16028b  stloc.3
0x16028c  ldloc.3
0x16028d  ldc.i4.1
0x16028e  box      [mscorlib]System.Int32
0x160293  callvirt instance void [PresentationCore]System.Windows.Input.InputBinding::set_CommandParameter(object)
0x160298  ldtoken  System.Windows.Controls.DocumentViewer
0x16029d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1602a2  ldloc.3
0x1602a3  call     void [PresentationCore]System.Windows.Input.CommandManager::RegisterClassInputBinding(class [mscorlib]System.Type, class [PresentationCore]System.Windows.Input.InputBinding)
0x1602a8  call     class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Controls.DocumentViewer::get_FitToMaxPagesAcrossCommand()
0x1602ad  ldc.i4.s 0x26
0x1602af  ldc.i4.2
0x1602b0  newobj   instance void [PresentationCore]System.Windows.Input.KeyGesture::.ctor(valuetype [WindowsBase]System.Windows.Input.Key, valuetype [WindowsBase]System.Windows.Input.ModifierKeys)
0x1602b5  newobj   instance void [PresentationCore]System.Windows.Input.InputBinding::.ctor(class [System]System.Windows.Input.ICommand, class [PresentationCore]System.Windows.Input.InputGesture)
0x1602ba  stloc.s  4
0x1602bc  ldloc.s  4
0x1602be  ldc.i4.2
0x1602bf  box      [mscorlib]System.Int32
0x1602c4  callvirt instance void [PresentationCore]System.Windows.Input.InputBinding::set_CommandParameter(object)
0x1602c9  ldtoken  System.Windows.Controls.DocumentViewer
0x1602ce  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1602d3  ldloc.s  4
0x1602d5  call     void [PresentationCore]System.Windows.Input.CommandManager::RegisterClassInputBinding(class [mscorlib]System.Type, class [PresentationCore]System.Windows.Input.InputBinding)
0x1602da  ret
```
