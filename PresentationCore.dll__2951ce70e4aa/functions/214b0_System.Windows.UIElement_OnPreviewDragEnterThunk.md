# System.Windows.UIElement::OnPreviewDragEnterThunk

- ea: `0x214b0`
- end: `0x214f4`
- name: `System.Windows.UIElement::OnPreviewDragEnterThunk`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x17f60`
- `0x214b0`
- `0x22520`
- `0x28080`
- `0x2cc20`

## string_xrefs

- `0x214b9`: `Unexpected: Event has already been handled.`

## pseudocode

```c

```

## disassembly

```asm
0x214b0  ldarg.1
0x214b1  callvirt instance bool System.Windows.RoutedEventArgs::get_Handled()
0x214b6  ldc.i4.0
0x214b7  ceq
0x214b9  ldstr    aUnexpectedEven// "Unexpected: Event has already been hand"...
0x214be  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x214c3  ldarg.0
0x214c4  isinst   System.Windows.UIElement
0x214c9  stloc.1
0x214ca  ldloc.1
0x214cb  brfalse.s loc_214D5
0x214cd  ldloc.1
0x214ce  ldarg.1
0x214cf  callvirt instance void System.Windows.UIElement::OnPreviewDragEnter(class System.Windows.DragEventArgs e)
0x214d4  ret
0x214d5  ldarg.0
0x214d6  isinst   System.Windows.ContentElement
0x214db  stloc.0
0x214dc  ldloc.0
0x214dd  brfalse.s loc_214E7
0x214df  ldloc.0
0x214e0  ldarg.1
0x214e1  callvirt instance void System.Windows.ContentElement::OnPreviewDragEnter(class System.Windows.DragEventArgs e)
0x214e6  ret
0x214e7  ldarg.0
0x214e8  castclass System.Windows.UIElement3D
0x214ed  ldarg.1
0x214ee  callvirt instance void System.Windows.UIElement3D::OnPreviewDragEnter(class System.Windows.DragEventArgs e)
0x214f3  ret
```
