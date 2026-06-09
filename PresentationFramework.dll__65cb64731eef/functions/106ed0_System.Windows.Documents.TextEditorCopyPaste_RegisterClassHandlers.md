# System.Windows.Documents.TextEditorCopyPaste::_RegisterClassHandlers

- ea: `0x106ed0`
- end: `0x107036`
- name: `System.Windows.Documents.TextEditorCopyPaste::_RegisterClassHandlers`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x104c00`

## callees

- `0x38c40`
- `0xd0b30`
- `0xd0b40`
- `0x106ed0`
- `0x23e9c0`
- `0x23ea00`
- `0x23eaa0`

## string_xrefs

- `0x106eee`: `KeyCopy`
- `0x106ef8`: `KeyCopyDisplayString`
- `0x106f46`: `KeyCopyFormat`
- `0x106f4b`: `KeyCopyFormatDisplayString`
- `0x106f92`: `KeyShiftDelete`
- `0x106f9c`: `KeyShiftDeleteDisplayString`

## pseudocode

```c

```

## disassembly

```asm
0x106ed0  ldarg.0
0x106ed1  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.ApplicationCommands::get_Copy()
0x106ed6  ldnull
0x106ed7  ldftn    void System.Windows.Documents.TextEditorCopyPaste::OnCopy(object target, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs args)
0x106edd  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x106ee2  ldnull
0x106ee3  ldftn    void System.Windows.Documents.TextEditorCopyPaste::OnQueryStatusCopy(object target, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs args)
0x106ee9  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x106eee  ldstr    aKeycopy// "KeyCopy"
0x106ef3  call     string System.Windows.SR::Get(string id)
0x106ef8  ldstr    aKeycopydisplay// "KeyCopyDisplayString"
0x106efd  call     string System.Windows.SR::Get(string id)
0x106f02  call     class [PresentationCore]System.Windows.Input.KeyGesture [PresentationCore]System.Windows.Input.KeyGesture::CreateFromResourceStrings(string, string)
0x106f07  ldstr    aKeyctrlinsert// "KeyCtrlInsert"
0x106f0c  call     string System.Windows.SR::Get(string id)
0x106f11  ldstr    aKeyctrlinsertd// "KeyCtrlInsertDisplayString"
0x106f16  call     string System.Windows.SR::Get(string id)
0x106f1b  call     class [PresentationCore]System.Windows.Input.KeyGesture [PresentationCore]System.Windows.Input.KeyGesture::CreateFromResourceStrings(string, string)
0x106f20  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, class [PresentationCore]System.Windows.Input.InputGesture inputGesture, class [PresentationCore]System.Windows.Input.InputGesture inputGesture2)
0x106f25  ldarg.1
0x106f26  brfalse.s loc_106F55
0x106f28  ldarg.0
0x106f29  call     class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Documents.EditingCommands::get_CopyFormat()
0x106f2e  ldnull
0x106f2f  ldftn    void System.Windows.Documents.TextEditorCopyPaste::OnCopyFormat(object sender, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs args)
0x106f35  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x106f3a  ldnull
0x106f3b  ldftn    void System.Windows.Documents.TextEditorCopyPaste::OnQueryStatusCopyFormat(object target, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs args)
0x106f41  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x106f46  ldstr    aKeycopyformat// "KeyCopyFormat"
0x106f4b  ldstr    aKeycopyformatd// "KeyCopyFormatDisplayString"
0x106f50  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, string srid1, string srid2)
0x106f55  ldarg.2
0x106f56  brtrue   loc_107035
0x106f5b  ldarg.0
0x106f5c  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.ApplicationCommands::get_Cut()
0x106f61  ldnull
0x106f62  ldftn    void System.Windows.Documents.TextEditorCopyPaste::OnCut(object target, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs args)
0x106f68  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x106f6d  ldnull
0x106f6e  ldftn    void System.Windows.Documents.TextEditorCopyPaste::OnQueryStatusCut(object target, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs args)
0x106f74  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x106f79  ldstr    aKeycut// "KeyCut"
0x106f7e  call     string System.Windows.SR::Get(string id)
0x106f83  ldstr    aKeycutdisplays// "KeyCutDisplayString"
0x106f88  call     string System.Windows.SR::Get(string id)
0x106f8d  call     class [PresentationCore]System.Windows.Input.KeyGesture [PresentationCore]System.Windows.Input.KeyGesture::CreateFromResourceStrings(string, string)
0x106f92  ldstr    aKeyshiftdelete// "KeyShiftDelete"
0x106f97  call     string System.Windows.SR::Get(string id)
0x106f9c  ldstr    aKeyshiftdelete_0// "KeyShiftDeleteDisplayString"
0x106fa1  call     string System.Windows.SR::Get(string id)
0x106fa6  call     class [PresentationCore]System.Windows.Input.KeyGesture [PresentationCore]System.Windows.Input.KeyGesture::CreateFromResourceStrings(string, string)
0x106fab  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, class [PresentationCore]System.Windows.Input.InputGesture inputGesture, class [PresentationCore]System.Windows.Input.InputGesture inputGesture2)
0x106fb0  ldnull
0x106fb1  ldftn    void System.Windows.Documents.TextEditorCopyPaste::OnPaste(object target, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs args)
0x106fb7  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x106fbc  stloc.0
0x106fbd  ldnull
0x106fbe  ldftn    void System.Windows.Documents.TextEditorCopyPaste::OnQueryStatusPaste(object target, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs args)
0x106fc4  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x106fc9  stloc.1
0x106fca  ldstr    aKeyshiftinsert// "KeyShiftInsert"
0x106fcf  call     string System.Windows.SR::Get(string id)
0x106fd4  ldstr    aKeyshiftinsert_0// "KeyShiftInsertDisplayString"
0x106fd9  call     string System.Windows.SR::Get(string id)
0x106fde  call     class [PresentationCore]System.Windows.Input.KeyGesture [PresentationCore]System.Windows.Input.KeyGesture::CreateFromResourceStrings(string, string)
0x106fe3  stloc.2
0x106fe4  ldc.i4.2
0x106fe5  newobj   instance void [mscorlib]System.Security.Permissions.UIPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.UIPermissionClipboard)
0x106fea  call     instance void [mscorlib]System.Security.CodeAccessPermission::Assert()
0x106fef  ldarg.0
0x106ff0  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.ApplicationCommands::get_Paste()
0x106ff5  ldloc.0
0x106ff6  ldloc.1
0x106ff7  ldloc.2
0x106ff8  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, class [PresentationCore]System.Windows.Input.InputGesture inputGesture)
0x106ffd  leave.s  loc_107005
0x106fff  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x107004  endfinally
0x107005  ldarg.1
0x107006  brfalse.s loc_107035
0x107008  ldarg.0
0x107009  call     class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Documents.EditingCommands::get_PasteFormat()
0x10700e  ldnull
0x10700f  ldftn    void System.Windows.Documents.TextEditorCopyPaste::OnPasteFormat(object sender, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs args)
0x107015  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x10701a  ldnull
0x10701b  ldftn    void System.Windows.Documents.TextEditorCopyPaste::OnQueryStatusPasteFormat(object target, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs args)
0x107021  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x107026  ldstr    aKeypasteformat// "KeyPasteFormat"
0x10702b  ldstr    aKeypasteformat_0// "KeyPasteFormatDisplayString"
0x107030  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, string srid1, string srid2)
0x107035  ret
```
