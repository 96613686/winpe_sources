# System.Windows.Documents.TextEditorTyping::_RegisterClassHandlers

- ea: `0x10c5f0`
- end: `0x10c869`
- name: `System.Windows.Documents.TextEditorTyping::_RegisterClassHandlers`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x104c00`

## callees

- `0x38c40`
- `0xd0660`
- `0xd0670`
- `0xd0680`
- `0xd0690`
- `0xd06a0`
- `0xd06b0`
- `0xd06c0`
- `0xd06d0`
- `0xd06e0`
- `0xd09c0`
- `0xd09d0`
- `0x10c5f0`
- `0x23ea00`
- `0x23eaa0`

## string_xrefs

- `0x10c715`: `KeyDelete`
- `0x10c71a`: `KeyDeleteDisplayString`
- `0x10c737`: `KeyDeleteNextWord`
- `0x10c73c`: `KeyDeleteNextWordDisplayString`
- `0x10c759`: `KeyDeletePreviousWord`
- `0x10c75e`: `KeyDeletePreviousWordDisplayString`

## pseudocode

```c

```

## disassembly

```asm
0x10c5f0  ldarg.1
0x10c5f1  brfalse.s loc_10C64F
0x10c5f3  ldarg.0
0x10c5f4  ldsfld   class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.Input.Keyboard::PreviewKeyDownEvent
0x10c5f9  ldnull
0x10c5fa  ldftn    void System.Windows.Documents.TextEditorTyping::OnPreviewKeyDown(object sender, class [PresentationCore]System.Windows.Input.KeyEventArgs e)
0x10c600  newobj   instance void [PresentationCore]System.Windows.Input.KeyEventHandler::.ctor(object, native int)
0x10c605  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate)
0x10c60a  ldarg.0
0x10c60b  ldsfld   class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.Input.Keyboard::KeyDownEvent
0x10c610  ldnull
0x10c611  ldftn    void System.Windows.Documents.TextEditorTyping::OnKeyDown(object sender, class [PresentationCore]System.Windows.Input.KeyEventArgs e)
0x10c617  newobj   instance void [PresentationCore]System.Windows.Input.KeyEventHandler::.ctor(object, native int)
0x10c61c  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate)
0x10c621  ldarg.0
0x10c622  ldsfld   class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.Input.Keyboard::KeyUpEvent
0x10c627  ldnull
0x10c628  ldftn    void System.Windows.Documents.TextEditorTyping::OnKeyUp(object sender, class [PresentationCore]System.Windows.Input.KeyEventArgs e)
0x10c62e  newobj   instance void [PresentationCore]System.Windows.Input.KeyEventHandler::.ctor(object, native int)
0x10c633  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate)
0x10c638  ldarg.0
0x10c639  ldsfld   class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.Input.TextCompositionManager::TextInputEvent
0x10c63e  ldnull
0x10c63f  ldftn    void System.Windows.Documents.TextEditorTyping::OnTextInput(object sender, class [PresentationCore]System.Windows.Input.TextCompositionEventArgs e)
0x10c645  newobj   instance void [PresentationCore]System.Windows.Input.TextCompositionEventHandler::.ctor(object, native int)
0x10c64a  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate)
0x10c64f  ldnull
0x10c650  ldftn    void System.Windows.Documents.TextEditorTyping::OnEnterBreak(object sender, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs args)
0x10c656  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x10c65b  stloc.0
0x10c65c  ldnull
0x10c65d  ldftn    void System.Windows.Documents.TextEditorTyping::OnSpace(object sender, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs e)
0x10c663  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x10c668  stloc.1
0x10c669  ldnull
0x10c66a  ldftn    void System.Windows.Documents.TextEditorTyping::OnQueryStatusNYI(object target, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs args)
0x10c670  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x10c675  stloc.2
0x10c676  ldnull
0x10c677  ldftn    void System.Windows.Documents.TextEditorTyping::OnQueryStatusEnterBreak(object sender, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs args)
0x10c67d  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x10c682  stloc.3
0x10c683  ldarg.0
0x10c684  ldsfld   class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.Input.Mouse::MouseMoveEvent
0x10c689  ldnull
0x10c68a  ldftn    void System.Windows.Documents.TextEditorTyping::OnMouseMove(object sender, class [PresentationCore]System.Windows.Input.MouseEventArgs e)
0x10c690  newobj   instance void [PresentationCore]System.Windows.Input.MouseEventHandler::.ctor(object, native int)
0x10c695  ldc.i4.1
0x10c696  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate, bool)
0x10c69b  ldarg.0
0x10c69c  ldsfld   class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.Input.Mouse::MouseLeaveEvent
0x10c6a1  ldnull
0x10c6a2  ldftn    void System.Windows.Documents.TextEditorTyping::OnMouseLeave(object sender, class [PresentationCore]System.Windows.Input.MouseEventArgs e)
0x10c6a8  newobj   instance void [PresentationCore]System.Windows.Input.MouseEventHandler::.ctor(object, native int)
0x10c6ad  ldc.i4.1
0x10c6ae  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate, bool)
0x10c6b3  ldarg.0
0x10c6b4  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.ApplicationCommands::get_CorrectionList()
0x10c6b9  ldnull
0x10c6ba  ldftn    void System.Windows.Documents.TextEditorTyping::OnCorrectionList(object target, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs args)
0x10c6c0  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x10c6c5  ldnull
0x10c6c6  ldftn    void System.Windows.Documents.TextEditorTyping::OnQueryStatusCorrectionList(object target, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs args)
0x10c6cc  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x10c6d1  ldstr    aKeycorrectionl// "KeyCorrectionList"
0x10c6d6  ldstr    aKeycorrectionl_0// "KeyCorrectionListDisplayString"
0x10c6db  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, string srid1, string srid2)
0x10c6e0  ldarg.0
0x10c6e1  call     class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Documents.EditingCommands::get_ToggleInsert()
0x10c6e6  ldnull
0x10c6e7  ldftn    void System.Windows.Documents.TextEditorTyping::OnToggleInsert(object target, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs args)
0x10c6ed  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x10c6f2  ldloc.2
0x10c6f3  ldstr    aKeytoggleinser// "KeyToggleInsert"
0x10c6f8  ldstr    aKeytoggleinser_0// "KeyToggleInsertDisplayString"
0x10c6fd  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, string srid1, string srid2)
0x10c702  ldarg.0
0x10c703  call     class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Documents.EditingCommands::get_Delete()
0x10c708  ldnull
0x10c709  ldftn    void System.Windows.Documents.TextEditorTyping::OnDelete(object sender, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs args)
0x10c70f  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x10c714  ldloc.2
0x10c715  ldstr    aKeydelete// "KeyDelete"
0x10c71a  ldstr    aKeydeletedispl// "KeyDeleteDisplayString"
0x10c71f  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, string srid1, string srid2)
0x10c724  ldarg.0
0x10c725  call     class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Documents.EditingCommands::get_DeleteNextWord()
0x10c72a  ldnull
0x10c72b  ldftn    void System.Windows.Documents.TextEditorTyping::OnDeleteNextWord(object sender, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs args)
0x10c731  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x10c736  ldloc.2
0x10c737  ldstr    aKeydeletenextw// "KeyDeleteNextWord"
0x10c73c  ldstr    aKeydeletenextw_0// "KeyDeleteNextWordDisplayString"
0x10c741  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, string srid1, string srid2)
0x10c746  ldarg.0
0x10c747  call     class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Documents.EditingCommands::get_DeletePreviousWord()
0x10c74c  ldnull
0x10c74d  ldftn    void System.Windows.Documents.TextEditorTyping::OnDeletePreviousWord(object sender, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs args)
0x10c753  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x10c758  ldloc.2
0x10c759  ldstr    aKeydeleteprevi// "KeyDeletePreviousWord"
0x10c75e  ldstr    aKeydeleteprevi_0// "KeyDeletePreviousWordDisplayString"
0x10c763  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, string srid1, string srid2)
0x10c768  ldarg.0
0x10c769  call     class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Documents.EditingCommands::get_EnterParagraphBreak()
0x10c76e  ldloc.0
0x10c76f  ldloc.3
0x10c770  ldstr    aKeyenterparagr// "KeyEnterParagraphBreak"
0x10c775  ldstr    aKeyenterparagr_0// "KeyEnterParagraphBreakDisplayString"
0x10c77a  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, string srid1, string srid2)
0x10c77f  ldarg.0
0x10c780  call     class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Documents.EditingCommands::get_EnterLineBreak()
0x10c785  ldloc.0
0x10c786  ldloc.3
0x10c787  ldstr    aKeyenterlinebr// "KeyEnterLineBreak"
0x10c78c  ldstr    aKeyenterlinebr_0// "KeyEnterLineBreakDisplayString"
0x10c791  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, string srid1, string srid2)
0x10c796  ldarg.0
0x10c797  call     class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Documents.EditingCommands::get_TabForward()
0x10c79c  ldnull
0x10c79d  ldftn    void System.Windows.Documents.TextEditorTyping::OnTabForward(object sender, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs args)
0x10c7a3  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x10c7a8  ldnull
0x10c7a9  ldftn    void System.Windows.Documents.TextEditorTyping::OnQueryStatusTabForward(object sender, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs args)
0x10c7af  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x10c7b4  ldstr    aKeytabforward// "KeyTabForward"
0x10c7b9  ldstr    aKeytabforwardd// "KeyTabForwardDisplayString"
0x10c7be  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, string srid1, string srid2)
0x10c7c3  ldarg.0
0x10c7c4  call     class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Documents.EditingCommands::get_TabBackward()
0x10c7c9  ldnull
0x10c7ca  ldftn    void System.Windows.Documents.TextEditorTyping::OnTabBackward(object sender, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs args)
0x10c7d0  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x10c7d5  ldnull
0x10c7d6  ldftn    void System.Windows.Documents.TextEditorTyping::OnQueryStatusTabBackward(object sender, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs args)
0x10c7dc  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x10c7e1  ldstr    aKeytabbackward// "KeyTabBackward"
0x10c7e6  ldstr    aKeytabbackward_0// "KeyTabBackwardDisplayString"
0x10c7eb  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, string srid1, string srid2)
0x10c7f0  ldarg.0
0x10c7f1  call     class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Documents.EditingCommands::get_Space()
0x10c7f6  ldloc.1
0x10c7f7  ldloc.2
0x10c7f8  ldstr    aKeyspace// "KeySpace"
0x10c7fd  ldstr    aKeyspacedispla// "KeySpaceDisplayString"
0x10c802  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, string srid1, string srid2)
0x10c807  ldarg.0
0x10c808  call     class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Documents.EditingCommands::get_ShiftSpace()
0x10c80d  ldloc.1
0x10c80e  ldloc.2
0x10c80f  ldstr    aKeyshiftspace// "KeyShiftSpace"
0x10c814  ldstr    aKeyshiftspaced// "KeyShiftSpaceDisplayString"
0x10c819  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, string srid1, string srid2)
0x10c81e  ldarg.0
0x10c81f  call     class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Documents.EditingCommands::get_Backspace()
0x10c824  ldnull
0x10c825  ldftn    void System.Windows.Documents.TextEditorTyping::OnBackspace(object sender, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs args)
0x10c82b  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x10c830  ldloc.2
0x10c831  ldstr    aKeybackspace// "KeyBackspace"
0x10c836  call     string System.Windows.SR::Get(string id)
0x10c83b  ldstr    aKeybackspacedi// "KeyBackspaceDisplayString"
0x10c840  call     string System.Windows.SR::Get(string id)
0x10c845  call     class [PresentationCore]System.Windows.Input.KeyGesture [PresentationCore]System.Windows.Input.KeyGesture::CreateFromResourceStrings(string, string)
0x10c84a  ldstr    aKeyshiftbacksp// "KeyShiftBackspace"
0x10c84f  call     string System.Windows.SR::Get(string id)
0x10c854  ldstr    aKeyshiftbacksp_0// "KeyShiftBackspaceDisplayString"
0x10c859  call     string System.Windows.SR::Get(string id)
0x10c85e  call     class [PresentationCore]System.Windows.Input.KeyGesture [PresentationCore]System.Windows.Input.KeyGesture::CreateFromResourceStrings(string, string)
0x10c863  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, class [PresentationCore]System.Windows.Input.InputGesture inputGesture, class [PresentationCore]System.Windows.Input.InputGesture inputGesture2)
0x10c868  ret
```
