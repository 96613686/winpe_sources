# NativeZLibDLLStub::LoadZLibDLL

- ea: `0x5c6b0`
- end: `0x5c70e`
- name: `NativeZLibDLLStub::LoadZLibDLL`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x5c800`

## callees

- `0x5bc70`
- `0x5c6b0`

## string_xrefs

- `0x5c6c2`: `clrcompression.dll`
- `0x5c6d5`: `clrcompression.dll`

## pseudocode

```c

```

## disassembly

```asm
0x5c6b0  ldc.i4.1
0x5c6b1  newobj   instance void [mscorlib]System.Security.Permissions.FileIOPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x5c6b6  call     instance void [mscorlib]System.Security.CodeAccessPermission::Assert()
0x5c6bb  call     string [mscorlib]System.Runtime.InteropServices.RuntimeEnvironment::GetRuntimeDirectory()
0x5c6c0  stloc.0
0x5c6c1  ldloc.0
0x5c6c2  ldstr    aClrcompression// "clrcompression.dll"
0x5c6c7  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x5c6cc  stloc.1
0x5c6cd  ldloc.1
0x5c6ce  call     bool [mscorlib]System.IO.File::Exists(string)
0x5c6d3  brtrue.s loc_5C6E0
0x5c6d5  ldstr    aClrcompression// "clrcompression.dll"
0x5c6da  newobj   instance void [mscorlib]System.DllNotFoundException::.ctor(string)
0x5c6df  throw
0x5c6e0  ldloc.1
0x5c6e1  call     class SafeLibraryHandle NativeMethods::LoadLibrary(string libPath)
0x5c6e6  stloc.2
0x5c6e7  ldloc.2
0x5c6e8  callvirt instance bool [mscorlib]System.Runtime.InteropServices.SafeHandle::get_IsInvalid()
0x5c6ed  brfalse.s loc_5C707
0x5c6ef  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetHRForLastWin32Error()
0x5c6f4  stloc.3
0x5c6f5  ldloc.3
0x5c6f6  ldc.i4.m1
0x5c6f7  newobj   instance void [mscorlib]System.IntPtr::.ctor(int32)
0x5c6fc  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32, native int)
0x5c701  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0x5c706  throw
0x5c707  ldloc.2
0x5c708  stsfld   class SafeLibraryHandle ZLibStreamHandle::zlibLibraryHandle
0x5c70d  ret
```
