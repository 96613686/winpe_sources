# NGenTask.TaskExecutive::NgenClientInterruptStop

- ea: `0x1080`
- end: `0x10ab`
- name: `NGenTask.TaskExecutive::NgenClientInterruptStop`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x19f0`

## callees

- `0x1080`
- `0x10b0`

## pseudocode

```c

```

## disassembly

```asm
0x1080  ldarg.0
0x1081  ldfld    object NGenTask.TaskExecutive::m_stopLock
0x1086  stloc.0
0x1087  ldc.i4.0
0x1088  stloc.1
0x1089  ldloc.0
0x108a  ldloca.s 1
0x108c  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x1091  ldarg.0
0x1092  ldc.i4.1
0x1093  stfld    bool NGenTask.TaskExecutive::m_ngenClientInterrupt
0x1098  ldarg.0
0x1099  call     instance void NGenTask.TaskExecutive::StopWorker()
0x109e  leave.s  loc_10AA
0x10a0  ldloc.1
0x10a1  brfalse.s loc_10A9
0x10a3  ldloc.0
0x10a4  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x10a9  endfinally
0x10aa  ret
```
