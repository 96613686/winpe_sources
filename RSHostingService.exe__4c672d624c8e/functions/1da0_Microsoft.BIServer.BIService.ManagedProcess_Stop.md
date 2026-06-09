# Microsoft.BIServer.BIService.ManagedProcess::Stop

- ea: `0x1da0`
- end: `0x1dd3`
- name: `Microsoft.BIServer.BIService.ManagedProcess::Stop`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18e0`
- `0x1a20`

## callees

- `0x1da0`
- `0x1de0`

## pseudocode

```c

```

## disassembly

```asm
0x1da0  ldarg.0
0x1da1  ldfld    class [System]System.Diagnostics.Process Microsoft.BIServer.BIService.ManagedProcess::_process
0x1da6  brfalse.s loc_1DD2
0x1da8  ldarg.0
0x1da9  ldfld    class [System]System.Diagnostics.Process Microsoft.BIServer.BIService.ManagedProcess::_process
0x1dae  callvirt instance bool [System]System.Diagnostics.Process::get_HasExited()
0x1db3  brtrue.s loc_1DD2
0x1db5  ldarg.0
0x1db6  ldfld    class [System]System.Diagnostics.Process Microsoft.BIServer.BIService.ManagedProcess::_process
0x1dbb  ldarg.0
0x1dbc  ldftn    instance void Microsoft.BIServer.BIService.ManagedProcess::ProcessExitedHandler(object sender, class [mscorlib]System.EventArgs e)
0x1dc2  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x1dc7  callvirt instance void [System]System.Diagnostics.Process::remove_Exited(class [mscorlib]System.EventHandler)
0x1dcc  ldarg.0
0x1dcd  call     instance void Microsoft.BIServer.BIService.ManagedProcess::Kill()
0x1dd2  ret
```
