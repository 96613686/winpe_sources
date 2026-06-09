# Microsoft.VisualStudio.Setup.Extensions::GetSelectedState

- ea: `0x5a40`
- end: `0x5a56`
- name: `Microsoft.VisualStudio.Setup.Extensions::GetSelectedState`
- size: `22`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x152f0`
- `0x15460`
- `0x1bea0`
- `0x1d170`
- `0x1d200`

## callees

- `0x59a0`
- `0x5a40`
- `0x8320`

## pseudocode

```c

```

## disassembly

```asm
0x5a40  ldarg.0
0x5a41  call     bool Microsoft.VisualStudio.Setup.Extensions::IsSelectable(class Microsoft.VisualStudio.Setup.IPackage package)
0x5a46  brtrue.s loc_5A4A
0x5a48  ldc.i4.0
0x5a49  ret
0x5a4a  ldarg.0
0x5a4b  castclass Microsoft.VisualStudio.Setup.ISelectablePackage
0x5a50  callvirt instance valuetype Microsoft.VisualStudio.Setup.SelectedState Microsoft.VisualStudio.Setup.ISelectablePackage::get_SelectedState()
0x5a55  ret
```
