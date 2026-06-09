# MS.Internal.PrintWin32Thunk.PrinterThunkHandler::ThunkIsMetroDriverEnabled

- ea: `0x6db0`
- end: `0x6ec6`
- name: `MS.Internal.PrintWin32Thunk.PrinterThunkHandler::ThunkIsMetroDriverEnabled`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x11470`

## callees

- `0x5b70`
- `0x5c50`
- `0x5d20`
- `0x6db0`
- `0x8140`
- `0x172c0`
- `0x172e0`
- `0x172f0`

## string_xrefs

- `0x6e30`: `PipelineConfig.xml`

## pseudocode

```c

```

## disassembly

```asm
0x6db0  ldnull
0x6db1  stloc.s  4
0x6db3  ldc.i4.0
0x6db4  stloc.s  7
0x6db6  ldc.i4.0
0x6db7  stloc.3
0x6db8  ldarg.0
0x6db9  ldflda   native int [mscorlib]System.Runtime.InteropServices.SafeHandle::handle
0x6dbe  ldobj    [mscorlib]System.IntPtr
0x6dc3  ldnull
0x6dc4  ldc.i4.6
0x6dc5  call     class MS.Internal.PrintWin32Thunk.SafeMemoryHandle MS.Internal.PrintWin32Thunk.SafeMemoryHandle::get_Null()
0x6dca  ldc.i4.0
0x6dcb  ldloca.s 3
0x6dcd  call     bool MS.Internal.PrintWin32Thunk.Win32ApiThunk.UnsafeNativeMethods::InvokeGetPrinterDriver(native int A_0, string A_1, unsigned int32 A_2, class MS.Internal.PrintWin32Thunk.SafeMemoryHandle A_3, unsigned int32 A_4, unsigned int32* A_5)
0x6dd2  pop
0x6dd3  ldc.i4.s 0x7A
0x6dd5  call     void System.Printing.InternalPrintSystemException::ThrowIfLastErrorIsNot(int32 expectedLastWin32Error)
0x6dda  ldloc.3
0x6ddb  stloc.s  9
0x6ddd  ldloc.3
0x6dde  ldc.i4.0
0x6ddf  ble.un   loc_6EC3
0x6de4  ldloc.3
0x6de5  ldloca.s 4
0x6de7  call     bool MS.Internal.PrintWin32Thunk.SafeMemoryHandle::TryCreate([hasfieldmarshal] int32 value, class MS.Internal.PrintWin32Thunk.SafeMemoryHandle& byteCount)
0x6dec  brfalse  loc_6EBC
0x6df1  ldarg.0
0x6df2  ldflda   native int [mscorlib]System.Runtime.InteropServices.SafeHandle::handle
0x6df7  ldobj    [mscorlib]System.IntPtr
0x6dfc  ldnull
0x6dfd  ldc.i4.6
0x6dfe  ldloc.s  4
0x6e00  ldloc.s  9
0x6e02  ldloca.s 3
0x6e04  call     bool MS.Internal.PrintWin32Thunk.Win32ApiThunk.UnsafeNativeMethods::InvokeGetPrinterDriver(native int A_0, string A_1, unsigned int32 A_2, class MS.Internal.PrintWin32Thunk.SafeMemoryHandle A_3, unsigned int32 A_4, unsigned int32* A_5)
0x6e09  stloc.s  8
0x6e0b  ldloc.s  8
0x6e0d  brfalse  loc_6E9C
0x6e12  ldc.i4.2
0x6e13  newobj   instance void [mscorlib]System.Security.Permissions.SecurityPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.SecurityPermissionFlag)
0x6e18  callvirt instance void [mscorlib]System.Security.CodeAccessPermission::Assert()
0x6e1d  ldc.i4.0
0x6e1e  conv.i8
0x6e1f  stloc.2
0x6e20  ldloc.s  4
0x6e22  call     instance native int [mscorlib]System.Runtime.InteropServices.SafeHandle::DangerousGetHandle()
0x6e27  stloc.s  0xA
0x6e29  ldloca.s 0xA
0x6e2b  call     instance void* [mscorlib]System.IntPtr::ToPointer()
0x6e30  ldstr    aPipelineconfig// "PipelineConfig.xml"
0x6e35  stloc.s  6
0x6e37  ldc.i4.s 0x38
0x6e39  conv.i8
0x6e3a  add
0x6e3b  ldind.i8
0x6e3c  stloc.0
0x6e3d  ldloc.0
0x6e3e  brfalse.s loc_6E94
0x6e40  ldloc.0
0x6e41  ldind.u2
0x6e42  brfalse.s loc_6E94
0x6e44  ldloc.0
0x6e45  stloc.1
0x6e46  ldloc.1
0x6e47  unaligned. 1
0x6e4a  ldind.i2
0x6e4b  brfalse.s loc_6E54
0x6e4d  ldloc.1
0x6e4e  ldc.i4.2
0x6e4f  conv.i8
0x6e50  add
0x6e51  stloc.1
0x6e52  br.s     loc_6E46
0x6e54  ldloc.1
0x6e55  ldloc.0
0x6e56  sub
0x6e57  ldc.i4.1
0x6e58  shr
0x6e59  stloc.2
0x6e5a  ldloc.2
0x6e5b  ldloc.s  6
0x6e5d  call     instance int32 [mscorlib]System.String::get_Length()
0x6e62  conv.i8
0x6e63  sub
0x6e64  stloc.s  5
0x6e66  ldloc.s  5
0x6e68  ldc.i4.0
0x6e69  conv.i8
0x6e6a  ble.un.s loc_6E88
0x6e6c  ldc.i4.0
0x6e6d  ldloc.s  6
0x6e6f  ldloc.s  5
0x6e71  ldc.i4.2
0x6e72  conv.i8
0x6e73  mul
0x6e74  ldloc.0
0x6e75  add
0x6e76  newobj   instance void [mscorlib]System.String::.ctor(char*)
0x6e7b  ldc.i4.5
0x6e7c  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x6e81  bne.un.s loc_6E88
0x6e83  ldc.i4.1
0x6e84  stloc.s  7
0x6e86  br.s     loc_6E94
0x6e88  ldloc.2
0x6e89  ldc.i4.2
0x6e8a  conv.i8
0x6e8b  mul
0x6e8c  ldloc.0
0x6e8d  add
0x6e8e  ldc.i4.2
0x6e8f  conv.i8
0x6e90  add
0x6e91  stloc.0
0x6e92  br.s     loc_6E3D
0x6e94  leave.s  loc_6EA1
0x6e96  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x6e9b  endfinally
0x6e9c  call     void System.Printing.InternalPrintSystemException::ThrowLastError()
0x6ea1  ldc.i4.2
0x6ea2  newobj   instance void [mscorlib]System.Security.Permissions.SecurityPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.SecurityPermissionFlag)
0x6ea7  callvirt instance void [mscorlib]System.Security.CodeAccessPermission::Assert()
0x6eac  ldloc.s  4
0x6eae  callvirt instance bool MS.Internal.PrintWin32Thunk.SafeMemoryHandle::ReleaseHandle()
0x6eb3  pop
0x6eb4  leave.s  loc_6EC3
0x6eb6  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x6ebb  endfinally
0x6ebc  ldc.i4.s 0xE
0x6ebe  call     void System.Printing.InternalPrintSystemException::ThrowIfNotSuccess(int32 lastWin32Error)
0x6ec3  ldloc.s  7
0x6ec5  ret
```
