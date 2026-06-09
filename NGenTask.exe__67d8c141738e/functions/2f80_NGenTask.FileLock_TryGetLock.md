# NGenTask.FileLock::TryGetLock

- ea: `0x2f80`
- end: `0x2ff2`
- name: `NGenTask.FileLock::TryGetLock`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0xf20`

## callees

- `0x2f80`
- `0x31d0`

## pseudocode

```c

```

## disassembly

```asm
0x2f80  ldarg.0
0x2f81  ldfld    bool NGenTask.FileLock::m_Disposed
0x2f86  brtrue.s loc_2F9D
0x2f88  ldarg.0
0x2f89  ldfld    class [mscorlib]Microsoft.Win32.SafeHandles.SafeFileHandle NGenTask.FileLock::m_FileLock
0x2f8e  brfalse.s loc_2FA3
0x2f90  ldarg.0
0x2f91  ldfld    class [mscorlib]Microsoft.Win32.SafeHandles.SafeFileHandle NGenTask.FileLock::m_FileLock
0x2f96  callvirt instance bool [mscorlib]System.Runtime.InteropServices.SafeHandle::get_IsInvalid()
0x2f9b  brtrue.s loc_2FA3
0x2f9d  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0x2fa2  throw
0x2fa3  ldarg.0
0x2fa4  ldarg.1
0x2fa5  ldc.i4   0x40000000
0x2faa  ldc.i4.0
0x2fab  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x2fb0  ldc.i4.2
0x2fb1  ldc.i4   0x4000000
0x2fb6  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x2fbb  call     class [mscorlib]Microsoft.Win32.SafeHandles.SafeFileHandle NGenTask.Win32Native::CreateFile(string lpFileName, unsigned int32 dwDesiredAccess, unsigned int32 dwShareMode, native int lpSecurityAttributes, unsigned int32 dwCreationDisposition, unsigned int32 dwFlagsAndAttributes, native int hTemplateFile)
0x2fc0  stfld    class [mscorlib]Microsoft.Win32.SafeHandles.SafeFileHandle NGenTask.FileLock::m_FileLock
0x2fc5  ldarg.0
0x2fc6  ldfld    class [mscorlib]Microsoft.Win32.SafeHandles.SafeFileHandle NGenTask.FileLock::m_FileLock
0x2fcb  callvirt instance bool [mscorlib]System.Runtime.InteropServices.SafeHandle::get_IsInvalid()
0x2fd0  brtrue.s loc_2FD4
0x2fd2  ldc.i4.1
0x2fd3  ret
0x2fd4  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetHRForLastWin32Error()
0x2fd9  stloc.0
0x2fda  ldloc.0
0x2fdb  ldc.i4   0x80070020
0x2fe0  beq.s    loc_2FF0
0x2fe2  ldloc.0
0x2fe3  ldc.i4   0x80070005
0x2fe8  beq.s    loc_2FF0
0x2fea  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor()
0x2fef  throw
0x2ff0  ldc.i4.0
0x2ff1  ret
```
