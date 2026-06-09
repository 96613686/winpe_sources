# NGenTask.TaskExecutive::ParentStopEventListener

- ea: `0x19d0`
- end: `0x19e3`
- name: `NGenTask.TaskExecutive::ParentStopEventListener`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0xec0`

## pseudocode

```c

```

## disassembly

```asm
0x19d0  ldarg.0
0x19d1  ldfld    class [mscorlib]System.Threading.ManualResetEvent NGenTask.TaskExecutive::m_parentStopEvent
0x19d6  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne()
0x19db  pop
0x19dc  ldarg.0
0x19dd  call     instance void NGenTask.TaskExecutive::Stop()
0x19e2  ret
```
