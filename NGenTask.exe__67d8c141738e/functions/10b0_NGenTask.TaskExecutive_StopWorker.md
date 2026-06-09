# NGenTask.TaskExecutive::StopWorker

- ea: `0x10b0`
- end: `0x111e`
- name: `NGenTask.TaskExecutive::StopWorker`
- size: `110`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `service_task`

## callers

- `0xec0`
- `0x1080`
- `0x2910`

## callees

- `0x10b0`
- `0x2c60`
- `0x30a0`
- `0x30d0`
- `0x30e0`
- `0x3110`

## pseudocode

```c

```

## disassembly

```asm
0x10b0  ldarg.0
0x10b1  ldfld    class NGenTask.ChildProcess NGenTask.TaskExecutive::m_childProcess
0x10b6  brfalse.s loc_111D
0x10b8  ldarg.0
0x10b9  ldfld    class NGenTask.ChildProcess NGenTask.TaskExecutive::m_childProcess
0x10be  callvirt instance bool NGenTask.ChildProcess::get_HasExited()
0x10c3  brtrue.s loc_111D
0x10c5  ldarg.0
0x10c6  ldfld    class [mscorlib]System.Threading.ManualResetEvent NGenTask.TaskExecutive::m_childStopEvent
0x10cb  brfalse.s loc_10FA
0x10cd  ldarg.0
0x10ce  ldfld    class NGenTask.ChildProcess NGenTask.TaskExecutive::m_childProcess
0x10d3  callvirt instance valuetype ProcessType NGenTask.ChildProcess::get_Type()
0x10d8  ldc.i4.1
0x10d9  bne.un.s loc_10FA
0x10db  ldarg.0
0x10dc  ldfld    class [mscorlib]System.Threading.ManualResetEvent NGenTask.TaskExecutive::m_childStopEvent
0x10e1  callvirt instance bool [mscorlib]System.Threading.EventWaitHandle::Set()
0x10e6  brfalse.s loc_10FA
0x10e8  ldarg.0
0x10e9  ldfld    class NGenTask.ChildProcess NGenTask.TaskExecutive::m_childProcess
0x10ee  ldc.i4   0x3E8
0x10f3  callvirt instance bool NGenTask.ChildProcess::WaitForExit(int32 timeout)
0x10f8  brtrue.s loc_111D
0x10fa  nop
0x10fb  ldarg.0
0x10fc  ldfld    class NGenTask.ChildProcess NGenTask.TaskExecutive::m_childProcess
0x1101  callvirt instance void NGenTask.ChildProcess::Kill()
0x1106  leave.s  loc_111D
0x1108  stloc.0
0x1109  ldc.i4.0
0x110a  ldloc.0
0x110b  ldstr    aErrorStoppingW// "Error stopping worker"
0x1110  ldc.i4.0
0x1111  newarr   [mscorlib]System.Object
0x1116  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x111b  leave.s  loc_111D
0x111d  ret
```
