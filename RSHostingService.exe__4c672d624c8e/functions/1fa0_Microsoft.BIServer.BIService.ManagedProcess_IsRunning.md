# Microsoft.BIServer.BIService.ManagedProcess::IsRunning

- ea: `0x1fa0`
- end: `0x1fe2`
- name: `Microsoft.BIServer.BIService.ManagedProcess::IsRunning`
- size: `66`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1c50`
- `0x1de0`
- `0x1f10`

## callees

- `0x1fa0`
- `0x3bb0`

## pseudocode

```c

```

## disassembly

```asm
0x1fa0  ldarg.0
0x1fa1  ldfld    class [System]System.Diagnostics.Process Microsoft.BIServer.BIService.ManagedProcess::_process
0x1fa6  brtrue.s loc_1FAA
0x1fa8  ldc.i4.0
0x1fa9  ret
0x1faa  nop
0x1fab  newobj   instance void <>c__DisplayClass22_0::.ctor()
0x1fb0  stloc.0
0x1fb1  ldloc.0
0x1fb2  ldarg.0
0x1fb3  ldfld    class [System]System.Diagnostics.Process Microsoft.BIServer.BIService.ManagedProcess::_process
0x1fb8  callvirt instance int32 [System]System.Diagnostics.Process::get_Id()
0x1fbd  stfld    int32 <>c__DisplayClass22_0::procId
0x1fc2  call     class [System]System.Diagnostics.Process[] [System]System.Diagnostics.Process::GetProcesses()
0x1fc7  ldloc.0
0x1fc8  ldftn    instance bool <>c__DisplayClass22_0::<IsRunning>b__0(class [System]System.Diagnostics.Process x)
0x1fce  newobj   instance void class [mscorlib]System.Func`2<class [System]System.Diagnostics.Process, bool>::.ctor(object, native int)
0x1fd3  call     T0x2B000017
0x1fd8  stloc.1
0x1fd9  leave.s  loc_1FE0
0x1fdb  pop
0x1fdc  ldc.i4.0
0x1fdd  stloc.1
0x1fde  leave.s  loc_1FE0
0x1fe0  ldloc.1
0x1fe1  ret
```
