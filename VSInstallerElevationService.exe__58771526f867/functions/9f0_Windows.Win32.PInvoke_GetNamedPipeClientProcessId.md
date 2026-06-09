# Windows.Win32.PInvoke::GetNamedPipeClientProcessId

- ea: `0x9f0`
- end: `0xa37`
- name: `Windows.Win32.PInvoke::GetNamedPipeClientProcessId`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1070`

## callees

- `0x9f0`
- `0xa40`
- `0xb90`

## pseudocode

```c

```

## disassembly

```asm
0x9f0  ldc.i4.0
0x9f1  stloc.0
0x9f2  ldarg.1
0x9f3  stloc.2
0x9f4  ldloc.2
0x9f5  conv.u
0x9f6  stloc.1
0x9f7  ldarg.0
0x9f8  brfalse.s loc_A10
0x9fa  ldarg.0
0x9fb  ldloca.s 0
0x9fd  callvirt instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::DangerousAddRef(bool&)
0xa02  ldarg.0
0xa03  callvirt instance native int [mscorlib]System.Runtime.InteropServices.SafeHandle::DangerousGetHandle()
0xa08  call     valuetype Windows.Win32.Foundation.HANDLE Windows.Win32.Foundation.HANDLE::op_Explicit(native int value)
0xa0d  stloc.3
0xa0e  br.s     loc_A1B
0xa10  ldstr    aPipe// "Pipe"
0xa15  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa1a  throw
0xa1b  ldloc.3
0xa1c  ldloc.1
0xa1d  call     valuetype Windows.Win32.Foundation.BOOL Windows.Win32.PInvoke::GetNamedPipeClientProcessId(valuetype Windows.Win32.Foundation.HANDLE Pipe, unsigned int32* ClientProcessId)
0xa22  stloc.s  4
0xa24  leave.s  loc_A34
0xa26  ldc.i4.0
0xa27  conv.u
0xa28  stloc.2
0xa29  endfinally
0xa2a  ldloc.0
0xa2b  brfalse.s loc_A33
0xa2d  ldarg.0
0xa2e  callvirt instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::DangerousRelease()
0xa33  endfinally
0xa34  ldloc.s  4
0xa36  ret
```
