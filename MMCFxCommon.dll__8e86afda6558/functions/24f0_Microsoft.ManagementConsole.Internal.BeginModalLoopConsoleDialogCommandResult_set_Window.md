# Microsoft.ManagementConsole.Internal.BeginModalLoopConsoleDialogCommandResult::set_Window

- ea: `0x24f0`
- end: `0x2506`
- name: `Microsoft.ManagementConsole.Internal.BeginModalLoopConsoleDialogCommandResult::set_Window`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x24f0`

## pseudocode

```c

```

## disassembly

```asm
0x24f0  ldarg.1
0x24f1  brtrue.s loc_24FE
0x24f3  ldstr    aValue// "value"
0x24f8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x24fd  throw
0x24fe  ldarg.0
0x24ff  ldarg.1
0x2500  stfld    class [System.Windows.Forms]System.Windows.Forms.IWin32Window Microsoft.ManagementConsole.Internal.BeginModalLoopConsoleDialogCommandResult::_window
0x2505  ret
```
