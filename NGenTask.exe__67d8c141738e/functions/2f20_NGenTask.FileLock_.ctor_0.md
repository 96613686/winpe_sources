# NGenTask.FileLock::.ctor_0

- ea: `0x2f20`
- end: `0x2f7b`
- name: `NGenTask.FileLock::.ctor_0`
- size: `91`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0xf20`
- `0x1ad0`

## callees

- `0x2f20`
- `0x31d0`

## pseudocode

```c

```

## disassembly

```asm
0x2f20  ldarg.0
0x2f21  call     instance void [mscorlib]System.Object::.ctor()
0x2f26  ldarg.0
0x2f27  ldarg.1
0x2f28  ldc.i4   0x40000000
0x2f2d  ldc.i4.0
0x2f2e  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x2f33  ldc.i4.2
0x2f34  ldc.i4   0x4000000
0x2f39  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x2f3e  call     class [mscorlib]Microsoft.Win32.SafeHandles.SafeFileHandle NGenTask.Win32Native::CreateFile(string lpFileName, unsigned int32 dwDesiredAccess, unsigned int32 dwShareMode, native int lpSecurityAttributes, unsigned int32 dwCreationDisposition, unsigned int32 dwFlagsAndAttributes, native int hTemplateFile)
0x2f43  stfld    class [mscorlib]Microsoft.Win32.SafeHandles.SafeFileHandle NGenTask.FileLock::m_FileLock
0x2f48  ldarg.0
0x2f49  ldfld    class [mscorlib]Microsoft.Win32.SafeHandles.SafeFileHandle NGenTask.FileLock::m_FileLock
0x2f4e  callvirt instance bool [mscorlib]System.Runtime.InteropServices.SafeHandle::get_IsInvalid()
0x2f53  brtrue.s loc_2F56
0x2f55  ret
0x2f56  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetHRForLastWin32Error()
0x2f5b  stloc.0
0x2f5c  ldloc.0
0x2f5d  ldc.i4   0x80070020
0x2f62  beq.s    loc_2F6C
0x2f64  ldloc.0
0x2f65  ldc.i4   0x80070005
0x2f6a  bne.un.s loc_2F75
0x2f6c  ldc.i4.s 0x64
0x2f6e  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x2f73  br.s     loc_2F26
0x2f75  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor()
0x2f7a  throw
```
