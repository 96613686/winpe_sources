# System.Windows.UIElement::OnDragEnterThunk

- ea: `0x21500`
- end: `0x21544`
- name: `System.Windows.UIElement::OnDragEnterThunk`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x17f90`
- `0x21500`
- `0x22550`
- `0x280b0`
- `0x2cc20`

## string_xrefs

- `0x21509`: `Unexpected: Event has already been handled.`

## pseudocode

```c

```

## disassembly

```asm
0x21500  ldarg.1
0x21501  callvirt instance bool System.Windows.RoutedEventArgs::get_Handled()
0x21506  ldc.i4.0
0x21507  ceq
0x21509  ldstr    aUnexpectedEven// "Unexpected: Event has already been hand"...
0x2150e  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x21513  ldarg.0
0x21514  isinst   System.Windows.UIElement
0x21519  stloc.1
0x2151a  ldloc.1
0x2151b  brfalse.s loc_21525
0x2151d  ldloc.1
0x2151e  ldarg.1
0x2151f  callvirt instance void System.Windows.UIElement::OnDragEnter(class System.Windows.DragEventArgs e)
0x21524  ret
0x21525  ldarg.0
0x21526  isinst   System.Windows.ContentElement
0x2152b  stloc.0
0x2152c  ldloc.0
0x2152d  brfalse.s loc_21537
0x2152f  ldloc.0
0x21530  ldarg.1
0x21531  callvirt instance void System.Windows.ContentElement::OnDragEnter(class System.Windows.DragEventArgs e)
0x21536  ret
0x21537  ldarg.0
0x21538  castclass System.Windows.UIElement3D
0x2153d  ldarg.1
0x2153e  callvirt instance void System.Windows.UIElement3D::OnDragEnter(class System.Windows.DragEventArgs e)
0x21543  ret
```
