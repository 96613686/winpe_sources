# Microsoft.ManagementConsole.Advanced.WaitDialog::UpdateProgress

- ea: `0x7b30`
- end: `0x7b95`
- name: `Microsoft.ManagementConsole.Advanced.WaitDialog::UpdateProgress`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x75b0`
- `0x7680`
- `0x7b30`

## pseudocode

```c

```

## disassembly

```asm
0x7b30  ldarg.0
0x7b31  ldfld    object Microsoft.ManagementConsole.Advanced.WaitDialog::_syncRoot
0x7b36  dup
0x7b37  stloc.0
0x7b38  call     void [mscorlib]System.Threading.Monitor::Enter(object)
0x7b3d  ldarg.0
0x7b3e  ldfld    bool Microsoft.ManagementConsole.Advanced.WaitDialog::_isDisposed
0x7b43  brfalse.s loc_7B51
0x7b45  ldarg.0
0x7b46  call     instance string Microsoft.ManagementConsole.Advanced.WaitDialog::get_Name()
0x7b4b  newobj   instance void [mscorlib]System.ObjectDisposedException::.ctor(string)
0x7b50  throw
0x7b51  ldarg.0
0x7b52  ldarg.1
0x7b53  stfld    int32 Microsoft.ManagementConsole.Advanced.WaitDialog::_workProcessed
0x7b58  ldarg.0
0x7b59  ldarg.2
0x7b5a  stfld    int32 Microsoft.ManagementConsole.Advanced.WaitDialog::_totalWork
0x7b5f  ldarg.0
0x7b60  ldarg.3
0x7b61  stfld    string Microsoft.ManagementConsole.Advanced.WaitDialog::_statusText
0x7b66  ldarg.0
0x7b67  ldfld    class Microsoft.ManagementConsole.Advanced.IWaitDialog Microsoft.ManagementConsole.Advanced.WaitDialog::_coreWaitDialog
0x7b6c  brfalse.s loc_7B8B
0x7b6e  ldarg.0
0x7b6f  ldfld    class Microsoft.ManagementConsole.Advanced.IWaitDialog Microsoft.ManagementConsole.Advanced.WaitDialog::_coreWaitDialog
0x7b74  ldarg.0
0x7b75  ldfld    int32 Microsoft.ManagementConsole.Advanced.WaitDialog::_workProcessed
0x7b7a  ldarg.0
0x7b7b  ldfld    int32 Microsoft.ManagementConsole.Advanced.WaitDialog::_totalWork
0x7b80  ldarg.0
0x7b81  ldfld    string Microsoft.ManagementConsole.Advanced.WaitDialog::_statusText
0x7b86  callvirt instance void Microsoft.ManagementConsole.Advanced.IWaitDialog::UpdateProgress(int32 workProcessed, int32 totalWork, [hasfieldmarshal] string statusText)
0x7b8b  leave.s  loc_7B94
0x7b8d  ldloc.0
0x7b8e  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x7b93  endfinally
0x7b94  ret
```
