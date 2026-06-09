# System.Windows.Documents.TextEditor::RegisterCommandHandlers

- ea: `0x104c00`
- end: `0x104dee`
- name: `System.Windows.Documents.TextEditor::RegisterCommandHandlers`
- size: `494`
- prototype: ``
- caller_count: `5`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1649c0`
- `0x183390`
- `0x1890a0`
- `0x196e60`
- `0x1bb020`

## callees

- `0x38c40`
- `0x38c70`
- `0x104c00`
- `0x105f40`
- `0x106890`
- `0x106ed0`
- `0x107d90`
- `0x108110`
- `0x1086f0`
- `0x109210`
- `0x109470`
- `0x10bdb0`
- `0x10c2d0`
- `0x10c5f0`
- `0x23ea00`
- `0x23eaa0`

## string_xrefs

- `0x104c56`: `TextEditorCanNotRegisterCommandHandler`

## pseudocode

```c

```

## disassembly

```asm
0x104c00  ldsfld   class [mscorlib]System.Collections.ArrayList System.Windows.Documents.TextEditor::_registeredEditingTypes
0x104c05  ldnull
0x104c06  cgt.un
0x104c08  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool)
0x104c0d  ldsfld   class [mscorlib]System.Collections.ArrayList System.Windows.Documents.TextEditor::_registeredEditingTypes
0x104c12  stloc.0
0x104c13  ldc.i4.0
0x104c14  stloc.1
0x104c15  ldloc.0
0x104c16  ldloca.s 1
0x104c18  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x104c1d  ldc.i4.0
0x104c1e  stloc.2
0x104c1f  br.s     loc_104C91
0x104c21  ldsfld   class [mscorlib]System.Collections.ArrayList System.Windows.Documents.TextEditor::_registeredEditingTypes
0x104c26  ldloc.2
0x104c27  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x104c2c  castclass [mscorlib]System.Type
0x104c31  ldarg.0
0x104c32  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x104c37  brfalse.s loc_104C3E
0x104c39  leave    loc_104DED
0x104c3e  ldarg.0
0x104c3f  ldsfld   class [mscorlib]System.Collections.ArrayList System.Windows.Documents.TextEditor::_registeredEditingTypes
0x104c44  ldloc.2
0x104c45  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x104c4a  castclass [mscorlib]System.Type
0x104c4f  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x104c54  brfalse.s loc_104C8D
0x104c56  ldstr    aTexteditorcann// "TextEditorCanNotRegisterCommandHandler"
0x104c5b  ldc.i4.2
0x104c5c  newarr   [mscorlib]System.Object
0x104c61  dup
0x104c62  ldc.i4.0
0x104c63  ldsfld   class [mscorlib]System.Collections.ArrayList System.Windows.Documents.TextEditor::_registeredEditingTypes
0x104c68  ldloc.2
0x104c69  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x104c6e  castclass [mscorlib]System.Type
0x104c73  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x104c78  stelem.ref
0x104c79  dup
0x104c7a  ldc.i4.1
0x104c7b  ldarg.0
0x104c7c  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x104c81  stelem.ref
0x104c82  call     string System.Windows.SR::Get(string id, object[] args)
0x104c87  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x104c8c  throw
0x104c8d  ldloc.2
0x104c8e  ldc.i4.1
0x104c8f  add
0x104c90  stloc.2
0x104c91  ldloc.2
0x104c92  ldsfld   class [mscorlib]System.Collections.ArrayList System.Windows.Documents.TextEditor::_registeredEditingTypes
0x104c97  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x104c9c  blt.s    loc_104C21
0x104c9e  ldsfld   class [mscorlib]System.Collections.ArrayList System.Windows.Documents.TextEditor::_registeredEditingTypes
0x104ca3  ldarg.0
0x104ca4  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x104ca9  pop
0x104caa  leave.s  loc_104CB6
0x104cac  ldloc.1
0x104cad  brfalse.s loc_104CB5
0x104caf  ldloc.0
0x104cb0  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x104cb5  endfinally
0x104cb6  ldarg.0
0x104cb7  ldarg.3
0x104cb8  call     void System.Windows.Documents.TextEditorMouse::_RegisterClassHandlers(class [mscorlib]System.Type controlType, bool registerEventListeners)
0x104cbd  ldarg.2
0x104cbe  brtrue.s loc_104CC7
0x104cc0  ldarg.0
0x104cc1  ldarg.3
0x104cc2  call     void System.Windows.Documents.TextEditorTyping::_RegisterClassHandlers(class [mscorlib]System.Type controlType, bool registerEventListeners)
0x104cc7  ldarg.0
0x104cc8  ldarg.2
0x104cc9  ldarg.3
0x104cca  call     void System.Windows.Documents.TextEditorDragDrop::_RegisterClassHandlers(class [mscorlib]System.Type controlType, bool readOnly, bool registerEventListeners)
0x104ccf  ldarg.0
0x104cd0  ldarg.1
0x104cd1  ldarg.2
0x104cd2  ldarg.3
0x104cd3  call     void System.Windows.Documents.TextEditorCopyPaste::_RegisterClassHandlers(class [mscorlib]System.Type controlType, bool acceptsRichContent, bool readOnly, bool registerEventListeners)
0x104cd8  ldarg.0
0x104cd9  ldarg.3
0x104cda  call     void System.Windows.Documents.TextEditorSelection::_RegisterClassHandlers(class [mscorlib]System.Type controlType, bool registerEventListeners)
0x104cdf  ldarg.2
0x104ce0  brtrue.s loc_104CEA
0x104ce2  ldarg.0
0x104ce3  ldarg.1
0x104ce4  ldarg.3
0x104ce5  call     void System.Windows.Documents.TextEditorParagraphs::_RegisterClassHandlers(class [mscorlib]System.Type controlType, bool acceptsRichContent, bool registerEventListeners)
0x104cea  ldarg.0
0x104ceb  ldarg.3
0x104cec  call     void System.Windows.Documents.TextEditorContextMenu::_RegisterClassHandlers(class [mscorlib]System.Type controlType, bool registerEventListeners)
0x104cf1  ldarg.2
0x104cf2  brtrue.s loc_104CFB
0x104cf4  ldarg.0
0x104cf5  ldarg.3
0x104cf6  call     void System.Windows.Documents.TextEditorSpelling::_RegisterClassHandlers(class [mscorlib]System.Type controlType, bool registerEventListeners)
0x104cfb  ldarg.1
0x104cfc  brfalse.s loc_104D1D
0x104cfe  ldarg.2
0x104cff  brtrue.s loc_104D1D
0x104d01  ldarg.0
0x104d02  ldarg.3
0x104d03  call     void System.Windows.Documents.TextEditorCharacters::_RegisterClassHandlers(class [mscorlib]System.Type controlType, bool registerEventListeners)
0x104d08  ldarg.0
0x104d09  ldarg.3
0x104d0a  call     void System.Windows.Documents.TextEditorLists::_RegisterClassHandlers(class [mscorlib]System.Type controlType, bool registerEventListeners)
0x104d0f  ldsfld   bool System.Windows.Documents.TextEditor::_isTableEditingEnabled
0x104d14  brfalse.s loc_104D1D
0x104d16  ldarg.0
0x104d17  ldarg.3
0x104d18  call     void System.Windows.Documents.TextEditorTables::_RegisterClassHandlers(class [mscorlib]System.Type controlType, bool registerEventListeners)
0x104d1d  ldarg.3
0x104d1e  brfalse.s loc_104D65
0x104d20  ldarg.0
0x104d21  ldsfld   class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.Input.Keyboard::GotKeyboardFocusEvent
0x104d26  ldnull
0x104d27  ldftn    void System.Windows.Documents.TextEditor::OnGotKeyboardFocus(object sender, class [PresentationCore]System.Windows.Input.KeyboardFocusChangedEventArgs e)
0x104d2d  newobj   instance void [PresentationCore]System.Windows.Input.KeyboardFocusChangedEventHandler::.ctor(object, native int)
0x104d32  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate)
0x104d37  ldarg.0
0x104d38  ldsfld   class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.Input.Keyboard::LostKeyboardFocusEvent
0x104d3d  ldnull
0x104d3e  ldftn    void System.Windows.Documents.TextEditor::OnLostKeyboardFocus(object sender, class [PresentationCore]System.Windows.Input.KeyboardFocusChangedEventArgs e)
0x104d44  newobj   instance void [PresentationCore]System.Windows.Input.KeyboardFocusChangedEventHandler::.ctor(object, native int)
0x104d49  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate)
0x104d4e  ldarg.0
0x104d4f  ldsfld   class [PresentationCore]System.Windows.RoutedEvent [PresentationCore]System.Windows.UIElement::LostFocusEvent
0x104d54  ldnull
0x104d55  ldftn    void System.Windows.Documents.TextEditor::OnLostFocus(object sender, class [PresentationCore]System.Windows.RoutedEventArgs e)
0x104d5b  newobj   instance void [PresentationCore]System.Windows.RoutedEventHandler::.ctor(object, native int)
0x104d60  call     void [PresentationCore]System.Windows.EventManager::RegisterClassHandler(class [mscorlib]System.Type, class [PresentationCore]System.Windows.RoutedEvent, class [mscorlib]System.Delegate)
0x104d65  ldarg.2
0x104d66  brtrue   loc_104DED
0x104d6b  ldarg.0
0x104d6c  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.ApplicationCommands::get_Undo()
0x104d71  ldnull
0x104d72  ldftn    void System.Windows.Documents.TextEditor::OnUndo(object target, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs args)
0x104d78  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x104d7d  ldnull
0x104d7e  ldftn    void System.Windows.Documents.TextEditor::OnQueryStatusUndo(object sender, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs args)
0x104d84  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x104d89  ldstr    aKeyundo// "KeyUndo"
0x104d8e  call     string System.Windows.SR::Get(string id)
0x104d93  ldstr    aKeyundodisplay// "KeyUndoDisplayString"
0x104d98  call     string System.Windows.SR::Get(string id)
0x104d9d  call     class [PresentationCore]System.Windows.Input.KeyGesture [PresentationCore]System.Windows.Input.KeyGesture::CreateFromResourceStrings(string, string)
0x104da2  ldstr    aKeyaltundo// "KeyAltUndo"
0x104da7  call     string System.Windows.SR::Get(string id)
0x104dac  ldstr    aKeyaltundodisp// "KeyAltUndoDisplayString"
0x104db1  call     string System.Windows.SR::Get(string id)
0x104db6  call     class [PresentationCore]System.Windows.Input.KeyGesture [PresentationCore]System.Windows.Input.KeyGesture::CreateFromResourceStrings(string, string)
0x104dbb  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, class [PresentationCore]System.Windows.Input.InputGesture inputGesture, class [PresentationCore]System.Windows.Input.InputGesture inputGesture2)
0x104dc0  ldarg.0
0x104dc1  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.ApplicationCommands::get_Redo()
0x104dc6  ldnull
0x104dc7  ldftn    void System.Windows.Documents.TextEditor::OnRedo(object target, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs args)
0x104dcd  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x104dd2  ldnull
0x104dd3  ldftn    void System.Windows.Documents.TextEditor::OnQueryStatusRedo(object sender, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs args)
0x104dd9  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x104dde  ldstr    aKeyredo// "KeyRedo"
0x104de3  ldstr    aKeyredodisplay// "KeyRedoDisplayString"
0x104de8  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, string srid1, string srid2)
0x104ded  ret
```
