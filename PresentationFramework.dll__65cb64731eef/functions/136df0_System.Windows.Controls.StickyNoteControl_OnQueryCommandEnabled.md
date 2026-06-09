# System.Windows.Controls.StickyNoteControl::_OnQueryCommandEnabled

- ea: `0x136df0`
- end: `0x136e77`
- name: `System.Windows.Controls.StickyNoteControl::_OnQueryCommandEnabled`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x135c30`
- `0x136df0`
- `0x23e850`

## string_xrefs

- `0x136e07`: `Unexpected Commands`
- `0x136e24`: `Unknown Commands`
- `0x136e6c`: `Unknown command.`

## pseudocode

```c

```

## disassembly

```asm
0x136df0  ldarg.1
0x136df1  callvirt instance class [System]System.Windows.Input.ICommand [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs::get_Command()
0x136df6  castclass [PresentationCore]System.Windows.Input.RoutedCommand
0x136dfb  stloc.0
0x136dfc  ldarg.0
0x136dfd  isinst   System.Windows.Controls.StickyNoteControl
0x136e02  stloc.1
0x136e03  ldloc.1
0x136e04  ldnull
0x136e05  cgt.un
0x136e07  ldstr    aUnexpectedComm// "Unexpected Commands"
0x136e0c  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x136e11  ldloc.0
0x136e12  ldsfld   class [PresentationCore]System.Windows.Input.RoutedCommand System.Windows.Controls.StickyNoteControl::DeleteNoteCommand
0x136e17  beq.s    loc_136E23
0x136e19  ldloc.0
0x136e1a  ldsfld   class [PresentationCore]System.Windows.Input.RoutedCommand System.Windows.Controls.StickyNoteControl::InkCommand
0x136e1f  ceq
0x136e21  br.s     loc_136E24
0x136e23  ldc.i4.1
0x136e24  ldstr    aUnknownCommand// "Unknown Commands"
0x136e29  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x136e2e  ldloc.0
0x136e2f  ldsfld   class [PresentationCore]System.Windows.Input.RoutedCommand System.Windows.Controls.StickyNoteControl::DeleteNoteCommand
0x136e34  bne.un.s loc_136E46
0x136e36  ldarg.1
0x136e37  ldloc.1
0x136e38  ldfld    class MS.Internal.Annotations.IAttachedAnnotation System.Windows.Controls.StickyNoteControl::_attachedAnnotation
0x136e3d  ldnull
0x136e3e  cgt.un
0x136e40  callvirt instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs::set_CanExecute(bool)
0x136e45  ret
0x136e46  ldloc.0
0x136e47  ldsfld   class [PresentationCore]System.Windows.Input.RoutedCommand System.Windows.Controls.StickyNoteControl::InkCommand
0x136e4c  bne.un.s loc_136E6B
0x136e4e  ldloc.1
0x136e4f  callvirt instance class MS.Internal.Controls.StickyNote.StickyNoteContentControl System.Windows.Controls.StickyNoteControl::get_Content()
0x136e54  stloc.2
0x136e55  ldarg.1
0x136e56  ldloc.2
0x136e57  brfalse.s loc_136E64
0x136e59  ldloc.2
0x136e5a  callvirt instance valuetype System.Windows.Controls.StickyNoteType MS.Internal.Controls.StickyNote.StickyNoteContentControl::get_Type()
0x136e5f  ldc.i4.1
0x136e60  ceq
0x136e62  br.s     loc_136E65
0x136e64  ldc.i4.0
0x136e65  callvirt instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs::set_CanExecute(bool)
0x136e6a  ret
0x136e6b  ldc.i4.0
0x136e6c  ldstr    aUnknownCommand_0// "Unknown command."
0x136e71  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x136e76  ret
```
