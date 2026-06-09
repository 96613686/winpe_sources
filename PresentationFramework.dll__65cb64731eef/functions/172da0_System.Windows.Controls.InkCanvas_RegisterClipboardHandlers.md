# System.Windows.Controls.InkCanvas::_RegisterClipboardHandlers

- ea: `0x172da0`
- end: `0x172e5b`
- name: `System.Windows.Controls.InkCanvas::_RegisterClipboardHandlers`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x170c80`

## callees

- `0x38c40`
- `0x172da0`
- `0x23e9c0`
- `0x23eaa0`

## string_xrefs

- `0x172dc9`: `KeyShiftDelete`
- `0x172dce`: `KeyShiftDeleteDisplayString`

## pseudocode

```c

```

## disassembly

```asm
0x172da0  ldtoken  System.Windows.Controls.InkCanvas
0x172da5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x172daa  stloc.0
0x172dab  ldloc.0
0x172dac  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.ApplicationCommands::get_Cut()
0x172db1  ldnull
0x172db2  ldftn    void System.Windows.Controls.InkCanvas::_OnCommandExecuted(object sender, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs args)
0x172db8  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x172dbd  ldnull
0x172dbe  ldftn    void System.Windows.Controls.InkCanvas::_OnQueryCommandEnabled(object sender, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs args)
0x172dc4  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x172dc9  ldstr    aKeyshiftdelete// "KeyShiftDelete"
0x172dce  ldstr    aKeyshiftdelete_0// "KeyShiftDeleteDisplayString"
0x172dd3  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, string srid1, string srid2)
0x172dd8  ldloc.0
0x172dd9  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.ApplicationCommands::get_Copy()
0x172dde  ldnull
0x172ddf  ldftn    void System.Windows.Controls.InkCanvas::_OnCommandExecuted(object sender, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs args)
0x172de5  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x172dea  ldnull
0x172deb  ldftn    void System.Windows.Controls.InkCanvas::_OnQueryCommandEnabled(object sender, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs args)
0x172df1  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x172df6  ldstr    aKeyctrlinsert// "KeyCtrlInsert"
0x172dfb  ldstr    aKeyctrlinsertd// "KeyCtrlInsertDisplayString"
0x172e00  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, string srid1, string srid2)
0x172e05  ldnull
0x172e06  ldftn    void System.Windows.Controls.InkCanvas::_OnCommandExecuted(object sender, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs args)
0x172e0c  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x172e11  stloc.1
0x172e12  ldnull
0x172e13  ldftn    void System.Windows.Controls.InkCanvas::_OnQueryCommandEnabled(object sender, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs args)
0x172e19  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x172e1e  stloc.2
0x172e1f  ldstr    aKeyshiftinsert// "KeyShiftInsert"
0x172e24  call     string System.Windows.SR::Get(string id)
0x172e29  ldstr    aKeyshiftinsert_0// "KeyShiftInsertDisplayString"
0x172e2e  call     string System.Windows.SR::Get(string id)
0x172e33  call     class [PresentationCore]System.Windows.Input.KeyGesture [PresentationCore]System.Windows.Input.KeyGesture::CreateFromResourceStrings(string, string)
0x172e38  stloc.3
0x172e39  ldc.i4.2
0x172e3a  newobj   instance void [mscorlib]System.Security.Permissions.UIPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.UIPermissionClipboard)
0x172e3f  call     instance void [mscorlib]System.Security.CodeAccessPermission::Assert()
0x172e44  ldloc.0
0x172e45  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.ApplicationCommands::get_Paste()
0x172e4a  ldloc.1
0x172e4b  ldloc.2
0x172e4c  ldloc.3
0x172e4d  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, class [PresentationCore]System.Windows.Input.InputGesture inputGesture)
0x172e52  leave.s  loc_172E5A
0x172e54  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x172e59  endfinally
0x172e5a  ret
```
