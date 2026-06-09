# NGenTask.FileLock::Dispose_0

- ea: `0x3030`
- end: `0x305d`
- name: `NGenTask.FileLock::Dispose_0`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x3020`

## callees

- `0x3030`

## pseudocode

```c

```

## disassembly

```asm
0x3030  ldarg.0
0x3031  ldfld    bool NGenTask.FileLock::m_Disposed
0x3036  brtrue.s loc_305C
0x3038  ldarg.1
0x3039  brfalse.s loc_304E
0x303b  ldarg.0
0x303c  ldfld    class [mscorlib]Microsoft.Win32.SafeHandles.SafeFileHandle NGenTask.FileLock::m_FileLock
0x3041  brfalse.s loc_304E
0x3043  ldarg.0
0x3044  ldfld    class [mscorlib]Microsoft.Win32.SafeHandles.SafeFileHandle NGenTask.FileLock::m_FileLock
0x3049  callvirt instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Dispose()
0x304e  ldarg.0
0x304f  ldnull
0x3050  stfld    class [mscorlib]Microsoft.Win32.SafeHandles.SafeFileHandle NGenTask.FileLock::m_FileLock
0x3055  ldarg.0
0x3056  ldc.i4.1
0x3057  stfld    bool NGenTask.FileLock::m_Disposed
0x305c  ret
```
