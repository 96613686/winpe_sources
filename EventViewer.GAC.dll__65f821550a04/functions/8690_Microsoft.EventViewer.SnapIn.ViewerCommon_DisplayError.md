# Microsoft.EventViewer.SnapIn.ViewerCommon::DisplayError

- ea: `0x8690`
- end: `0x869b`
- name: `Microsoft.EventViewer.SnapIn.ViewerCommon::DisplayError`
- size: `11`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x5f0`
- `0x6f0`
- `0x13f0`
- `0x3cb0`

## callees

- `0x86a0`

## pseudocode

```c

```

## disassembly

```asm
0x8690  ldarg.0
0x8691  ldarg.1
0x8692  ldc.i4.s 0x10
0x8694  ldarg.2
0x8695  call     void Microsoft.EventViewer.SnapIn.ViewerCommon::DisplayMessage(string caption, string text, valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon icon, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console con)
0x869a  ret
```
