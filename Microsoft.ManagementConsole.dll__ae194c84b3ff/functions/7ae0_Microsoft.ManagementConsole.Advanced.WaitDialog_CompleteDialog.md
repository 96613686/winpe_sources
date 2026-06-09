# Microsoft.ManagementConsole.Advanced.WaitDialog::CompleteDialog

- ea: `0x7ae0`
- end: `0x7b25`
- name: `Microsoft.ManagementConsole.Advanced.WaitDialog::CompleteDialog`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x75d0`
- `0x7680`
- `0x7ae0`

## pseudocode

```c

```

## disassembly

```asm
0x7ae0  ldarg.0
0x7ae1  ldfld    object Microsoft.ManagementConsole.Advanced.WaitDialog::_syncRoot
0x7ae6  dup
0x7ae7  stloc.0
0x7ae8  call     void [mscorlib]System.Threading.Monitor::Enter(object)
0x7aed  ldarg.0
0x7aee  ldfld    bool Microsoft.ManagementConsole.Advanced.WaitDialog::_isDisposed
0x7af3  brfalse.s loc_7B01
0x7af5  ldarg.0
0x7af6  call     instance string Microsoft.ManagementConsole.Advanced.WaitDialog::get_Name()
0x7afb  newobj   instance void [mscorlib]System.ObjectDisposedException::.ctor(string)
0x7b00  throw
0x7b01  ldarg.0
0x7b02  ldc.i4.1
0x7b03  stfld    bool Microsoft.ManagementConsole.Advanced.WaitDialog::_completed
0x7b08  ldarg.0
0x7b09  ldfld    class Microsoft.ManagementConsole.Advanced.IWaitDialog Microsoft.ManagementConsole.Advanced.WaitDialog::_coreWaitDialog
0x7b0e  brfalse.s loc_7B1B
0x7b10  ldarg.0
0x7b11  ldfld    class Microsoft.ManagementConsole.Advanced.IWaitDialog Microsoft.ManagementConsole.Advanced.WaitDialog::_coreWaitDialog
0x7b16  callvirt instance void Microsoft.ManagementConsole.Advanced.IWaitDialog::CompleteRequest()
0x7b1b  leave.s  loc_7B24
0x7b1d  ldloc.0
0x7b1e  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x7b23  endfinally
0x7b24  ret
```
