# System.Windows.Controls.StickyNoteControl::_OnCommandExecuted

- ea: `0x136d50`
- end: `0x136de6`
- name: `System.Windows.Controls.StickyNoteControl::_OnCommandExecuted`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x38c40`
- `0x135c30`
- `0x136140`
- `0x136d50`
- `0x23e850`

## string_xrefs

- `0x136d67`: `Unexpected Commands`
- `0x136d84`: `Unknown Commands`
- `0x136db8`: `CannotProcessInkCommand`

## pseudocode

```c

```

## disassembly

```asm
0x136d50  ldarg.1
0x136d51  callvirt instance class [System]System.Windows.Input.ICommand [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs::get_Command()
0x136d56  castclass [PresentationCore]System.Windows.Input.RoutedCommand
0x136d5b  stloc.0
0x136d5c  ldarg.0
0x136d5d  isinst   System.Windows.Controls.StickyNoteControl
0x136d62  stloc.1
0x136d63  ldloc.1
0x136d64  ldnull
0x136d65  cgt.un
0x136d67  ldstr    aUnexpectedComm// "Unexpected Commands"
0x136d6c  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x136d71  ldloc.0
0x136d72  ldsfld   class [PresentationCore]System.Windows.Input.RoutedCommand System.Windows.Controls.StickyNoteControl::DeleteNoteCommand
0x136d77  beq.s    loc_136D83
0x136d79  ldloc.0
0x136d7a  ldsfld   class [PresentationCore]System.Windows.Input.RoutedCommand System.Windows.Controls.StickyNoteControl::InkCommand
0x136d7f  ceq
0x136d81  br.s     loc_136D84
0x136d83  ldc.i4.1
0x136d84  ldstr    aUnknownCommand// "Unknown Commands"
0x136d89  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x136d8e  ldloc.0
0x136d8f  ldsfld   class [PresentationCore]System.Windows.Input.RoutedCommand System.Windows.Controls.StickyNoteControl::DeleteNoteCommand
0x136d94  bne.un.s loc_136D9D
0x136d96  ldloc.1
0x136d97  callvirt instance void System.Windows.Controls.StickyNoteControl::DeleteStickyNote()
0x136d9c  ret
0x136d9d  ldloc.0
0x136d9e  ldsfld   class [PresentationCore]System.Windows.Input.RoutedCommand System.Windows.Controls.StickyNoteControl::InkCommand
0x136da3  bne.un.s loc_136DE5
0x136da5  ldloc.1
0x136da6  callvirt instance class MS.Internal.Controls.StickyNote.StickyNoteContentControl System.Windows.Controls.StickyNoteControl::get_Content()
0x136dab  stloc.2
0x136dac  ldloc.2
0x136dad  brfalse.s loc_136DB8
0x136daf  ldloc.2
0x136db0  callvirt instance valuetype System.Windows.Controls.StickyNoteType MS.Internal.Controls.StickyNote.StickyNoteContentControl::get_Type()
0x136db5  ldc.i4.1
0x136db6  beq.s    loc_136DC8
0x136db8  ldstr    aCannotprocessi// "CannotProcessInkCommand"
0x136dbd  call     string System.Windows.SR::Get(string id)
0x136dc2  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x136dc7  throw
0x136dc8  ldarg.1
0x136dc9  callvirt instance object [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs::get_Parameter()
0x136dce  unbox.any System.Windows.Controls.InkCanvasEditingMode
0x136dd3  stloc.3
0x136dd4  ldloc.1
0x136dd5  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Controls.StickyNoteControl::InkEditingModeProperty
0x136dda  ldloc.3
0x136ddb  box      System.Windows.Controls.InkCanvasEditingMode
0x136de0  callvirt instance void [WindowsBase]System.Windows.DependencyObject::SetValue(class [WindowsBase]System.Windows.DependencyProperty, object)
0x136de5  ret
```
