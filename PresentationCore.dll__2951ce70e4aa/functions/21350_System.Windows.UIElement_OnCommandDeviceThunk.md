# System.Windows.UIElement::OnCommandDeviceThunk

- ea: `0x21350`
- end: `0x2136b`
- name: `System.Windows.UIElement::OnCommandDeviceThunk`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x2cc20`
- `0x316f0`

## string_xrefs

- `0x21359`: `Unexpected: Event has already been handled.`

## pseudocode

```c

```

## disassembly

```asm
0x21350  ldarg.1
0x21351  callvirt instance bool System.Windows.RoutedEventArgs::get_Handled()
0x21356  ldc.i4.0
0x21357  ceq
0x21359  ldstr    aUnexpectedEven// "Unexpected: Event has already been hand"...
0x2135e  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x21363  ldarg.0
0x21364  ldarg.1
0x21365  call     void System.Windows.Input.CommandManager::OnCommandDevice(object sender, class System.Windows.Input.CommandDeviceEventArgs e)
0x2136a  ret
```
