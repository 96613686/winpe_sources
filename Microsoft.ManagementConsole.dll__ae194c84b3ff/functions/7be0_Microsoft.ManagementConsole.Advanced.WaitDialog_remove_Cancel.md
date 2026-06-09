# Microsoft.ManagementConsole.Advanced.WaitDialog::remove_Cancel

- ea: `0x7be0`
- end: `0x7c17`
- name: `Microsoft.ManagementConsole.Advanced.WaitDialog::remove_Cancel`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x7680`
- `0x7be0`
- `0x7d90`

## pseudocode

```c

```

## disassembly

```asm
0x7be0  ldarg.0
0x7be1  ldfld    object Microsoft.ManagementConsole.Advanced.WaitDialog::_syncRoot
0x7be6  dup
0x7be7  stloc.0
0x7be8  call     void [mscorlib]System.Threading.Monitor::Enter(object)
0x7bed  ldarg.0
0x7bee  ldfld    bool Microsoft.ManagementConsole.Advanced.WaitDialog::_isDisposed
0x7bf3  brfalse.s loc_7C01
0x7bf5  ldarg.0
0x7bf6  call     instance string Microsoft.ManagementConsole.Advanced.WaitDialog::get_Name()
0x7bfb  newobj   instance void [mscorlib]System.ObjectDisposedException::.ctor(string)
0x7c00  throw
0x7c01  ldarg.0
0x7c02  ldfld    class WaitDialogCancelCallback Microsoft.ManagementConsole.Advanced.WaitDialog::_cancelCallback
0x7c07  ldarg.1
0x7c08  callvirt instance void WaitDialogCancelCallback::remove_Cancel(class [mscorlib]System.EventHandler value)
0x7c0d  leave.s  loc_7C16
0x7c0f  ldloc.0
0x7c10  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x7c15  endfinally
0x7c16  ret
```
