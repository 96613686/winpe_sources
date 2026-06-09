# Microsoft.BIServer.BIService.SafeUnmanagedMemoryHandle::ReleaseHandle

- ea: `0x2600`
- end: `0x262c`
- name: `Microsoft.BIServer.BIService.SafeUnmanagedMemoryHandle::ReleaseHandle`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x2600`

## pseudocode

```c

```

## disassembly

```asm
0x2600  ldarg.0
0x2601  ldfld    native int [mscorlib]System.Runtime.InteropServices.SafeHandle::handle
0x2606  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x260b  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x2610  brfalse.s loc_262A
0x2612  ldarg.0
0x2613  ldfld    native int [mscorlib]System.Runtime.InteropServices.SafeHandle::handle
0x2618  call     void [mscorlib]System.Runtime.InteropServices.Marshal::FreeHGlobal(native int)
0x261d  ldarg.0
0x261e  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x2623  stfld    native int [mscorlib]System.Runtime.InteropServices.SafeHandle::handle
0x2628  ldc.i4.1
0x2629  ret
0x262a  ldc.i4.0
0x262b  ret
```
