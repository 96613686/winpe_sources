# NGenTask.TaskExecutive::RunNGenCommand

- ea: `0x25c0`
- end: `0x2608`
- name: `NGenTask.TaskExecutive::RunNGenCommand`
- size: `72`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x310`
- `0x12d0`
- `0x1400`
- `0x25c0`

## callees

- `0x24f0`
- `0x25c0`
- `0x2790`

## pseudocode

```c

```

## disassembly

```asm
0x25c0  ldarg.0
0x25c1  volatile.
0x25c3  ldfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool NGenTask.TaskExecutive::m_stopRequested
0x25c8  brtrue.s loc_25D2
0x25ca  ldarg.0
0x25cb  call     instance bool NGenTask.TaskExecutive::IsWorkForbidden()
0x25d0  brfalse.s loc_25D5
0x25d2  ldc.i4.s 0xFE
0x25d4  ret
0x25d5  ldarg.0
0x25d6  ldc.i4.0
0x25d7  stfld    bool NGenTask.TaskExecutive::m_ngenClientInterrupt
0x25dc  ldarg.0
0x25dd  ldarg.1
0x25de  ldarg.2
0x25df  ldarg.3
0x25e0  call     instance int32 NGenTask.TaskExecutive::RunNGenCommandNoRetry(string ngenCommand, string arguments, string container)
0x25e5  stloc.0
0x25e6  ldarg.0
0x25e7  volatile.
0x25e9  ldfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool NGenTask.TaskExecutive::m_stopRequested
0x25ee  brtrue.s loc_25F8
0x25f0  ldarg.0
0x25f1  ldfld    bool NGenTask.TaskExecutive::m_ngenClientInterrupt
0x25f6  brtrue.s loc_25FA
0x25f8  ldloc.0
0x25f9  ret
0x25fa  ldarg.0
0x25fb  ldfld    class [mscorlib]System.Threading.AutoResetEvent NGenTask.TaskExecutive::m_ngenInterruptFinishedEvent
0x2600  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne()
0x2605  pop
0x2606  br.s     NGenTask.TaskExecutive__RunNGenCommand
```
