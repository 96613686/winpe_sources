# Microsoft.ManagementConsole.Internal.ConsoleDialogHost::ShowDialog_1

- ea: `0x6eb0`
- end: `0x6ed2`
- name: `Microsoft.ManagementConsole.Internal.ConsoleDialogHost::ShowDialog_1`
- size: `34`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x6980`
- `0xe590`

## callees

- `0x6eb0`
- `0x6fc0`
- `0x7060`

## string_xrefs

- `0x6eb3`: `commonDialog`

## pseudocode

```c

```

## disassembly

```asm
0x6eb0  ldarg.1
0x6eb1  brtrue.s loc_6EBE
0x6eb3  ldstr    aCommondialog// "commonDialog"
0x6eb8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6ebd  throw
0x6ebe  ldarg.0
0x6ebf  ldnull
0x6ec0  ldarg.1
0x6ec1  ldftn    instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult [System.Windows.Forms]System.Windows.Forms.CommonDialog::ShowDialog(class [System.Windows.Forms]System.Windows.Forms.IWin32Window)
0x6ec7  newobj   instance void ShowDialogCallback::.ctor(object object, native int method)
0x6ecc  call     instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.ManagementConsole.Internal.ConsoleDialogHost::ShowDialog(class Microsoft.ManagementConsole.Advanced.WaitCursor waitCursor, class ShowDialogCallback callback)
0x6ed1  ret
```
