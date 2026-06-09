# MS.Internal.PrintWin32Thunk.PrinterThunkHandler::CreateSpoolStream

- ea: `0x6ed0`
- end: `0x6f06`
- name: `MS.Internal.PrintWin32Thunk.PrinterThunkHandler::CreateSpoolStream`
- size: `54`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x65c0`
- `0x6610`

## callees

- `0x6ed0`

## pseudocode

```c

```

## disassembly

```asm
0x6ed0  ldarg.0
0x6ed1  ldfld    bool MS.Internal.PrintWin32Thunk.PrinterThunkHandler::isInPartialTrust
0x6ed6  brfalse.s loc_6EE3
0x6ed8  ldc.i4.2
0x6ed9  newobj   instance void [mscorlib]System.Security.Permissions.SecurityPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.SecurityPermissionFlag)
0x6ede  callvirt instance void [mscorlib]System.Security.CodeAccessPermission::Assert()
0x6ee3  nop
0x6ee4  ldarg.1
0x6ee5  ldc.i4.0
0x6ee6  newobj   instance void [mscorlib]Microsoft.Win32.SafeHandles.SafeFileHandle::.ctor(native int, bool)
0x6eeb  ldc.i4.3
0x6eec  newobj   instance void [mscorlib]System.IO.FileStream::.ctor(class [mscorlib]Microsoft.Win32.SafeHandles.SafeFileHandle, valuetype [mscorlib]System.IO.FileAccess)
0x6ef1  stloc.0
0x6ef2  leave.s  loc_6F04
0x6ef4  ldarg.0
0x6ef5  ldfld    bool MS.Internal.PrintWin32Thunk.PrinterThunkHandler::isInPartialTrust
0x6efa  brfalse.s loc_6F01
0x6efc  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x6f01  endfinally
0x6f02  ldnull
0x6f03  ret
0x6f04  ldloc.0
0x6f05  ret
```
