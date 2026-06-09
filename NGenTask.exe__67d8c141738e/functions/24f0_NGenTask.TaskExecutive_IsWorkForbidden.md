# NGenTask.TaskExecutive::IsWorkForbidden

- ea: `0x24f0`
- end: `0x2528`
- name: `NGenTask.TaskExecutive::IsWorkForbidden`
- size: `56`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x310`
- `0x1ad0`
- `0x25c0`

## callees

- `0x21e0`
- `0x2290`
- `0x24f0`
- `0x2c30`

## string_xrefs

- `0x24f9`: `Pending reboot flag is set.  Task will not do any work until the computer reboots.`
- `0x2514`: `Task is paused.  Task will not do any work until the computer reboots or 'ngen queue continue' is run`

## pseudocode

```c

```

## disassembly

```asm
0x24f0  ldarg.0
0x24f1  call     instance bool NGenTask.TaskExecutive::IsPostRebootFlagSet()
0x24f6  brfalse.s loc_250B
0x24f8  ldc.i4.m1
0x24f9  ldstr    aPendingRebootF// "Pending reboot flag is set.  Task will "...
0x24fe  ldc.i4.0
0x24ff  newarr   [mscorlib]System.Object
0x2504  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x2509  ldc.i4.1
0x250a  ret
0x250b  ldarg.0
0x250c  call     instance bool NGenTask.TaskExecutive::IsTaskPaused()
0x2511  brfalse.s loc_2526
0x2513  ldc.i4.m1
0x2514  ldstr    aTaskIsPausedTa// "Task is paused.  Task will not do any w"...
0x2519  ldc.i4.0
0x251a  newarr   [mscorlib]System.Object
0x251f  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x2524  ldc.i4.1
0x2525  ret
0x2526  ldc.i4.0
0x2527  ret
```
