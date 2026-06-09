# NGenTask.TaskExecutive::Run

- ea: `0x2c0`
- end: `0x303`
- name: `NGenTask.TaskExecutive::Run`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x2990`

## callees

- `0x2c0`
- `0x310`
- `0x1e30`

## pseudocode

```c

```

## disassembly

```asm
0x2c0  ldarg.0
0x2c1  call     instance bool NGenTask.TaskExecutive::IsBatteryLowOrCritical()
0x2c6  brfalse.s loc_2CE
0x2c8  ldc.i4   0x800710E0
0x2cd  ret
0x2ce  ldarg.0
0x2cf  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x2d4  stfld    valuetype [mscorlib]System.DateTime NGenTask.TaskExecutive::m_startTime
0x2d9  ldarg.0
0x2da  ldarg.1
0x2db  call     instance int32 NGenTask.TaskExecutive::RunInternal(string[] args)
0x2e0  stloc.0
0x2e1  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x2e6  stloc.1
0x2e7  ldarg.0
0x2e8  ldfld    class [mscorlib]System.Threading.Timer NGenTask.TaskExecutive::m_criticalTaskTimer
0x2ed  brfalse.s loc_301
0x2ef  ldarg.0
0x2f0  ldfld    class [mscorlib]System.Threading.Timer NGenTask.TaskExecutive::m_criticalTaskTimer
0x2f5  callvirt instance void [mscorlib]System.Threading.Timer::Dispose()
0x2fa  ldarg.0
0x2fb  ldnull
0x2fc  stfld    class [mscorlib]System.Threading.Timer NGenTask.TaskExecutive::m_criticalTaskTimer
0x301  ldloc.0
0x302  ret
```
