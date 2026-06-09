# System.Deployment.Application.Win32InterOp.SystemUtils::GetManifestFromPEResources

- ea: `0x236c0`
- end: `0x237db`
- name: `System.Deployment.Application.Win32InterOp.SystemUtils::GetManifestFromPEResources`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x25670`

## callees

- `0x1a260`
- `0x1a290`
- `0x1a2a0`
- `0x1a2b0`
- `0x1a2c0`
- `0x1a2d0`
- `0x236c0`
- `0x237e0`

## pseudocode

```c

```

## disassembly

```asm
0x236c0  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x236c5  stloc.0
0x236c6  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x236cb  stloc.1
0x236cc  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x236d1  stloc.2
0x236d2  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x236d7  stloc.3
0x236d8  ldloca.s 4
0x236da  ldc.i4.0
0x236db  call     instance void [mscorlib]System.IntPtr::.ctor(int32)
0x236e0  ldc.i4.2
0x236e1  stloc.s  5
0x236e3  ldnull
0x236e4  stloc.s  6
0x236e6  ldc.i4.0
0x236e7  stloc.s  7
0x236e9  ldarg.0
0x236ea  ldloc.s  4
0x236ec  ldloc.s  5
0x236ee  call     native int System.Deployment.Application.NativeMethods::LoadLibraryEx(string lpModuleName, native int hFile, unsigned int32 dwFlags)
0x236f3  stloc.1
0x236f4  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x236f9  stloc.s  7
0x236fb  ldloc.1
0x236fc  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x23701  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x23706  brfalse.s loc_23715
0x23708  ldloc.s  7
0x2370a  ldstr    aExWin32loadexc// "Ex_Win32LoadException"
0x2370f  ldarg.0
0x23710  call     void System.Deployment.Application.Win32InterOp.SystemUtils::Win32LoadExceptionHelper(int32 win32ErrorCode, string resourceId, string filePath)
0x23715  ldloc.1
0x23716  ldstr    a1_0// "#1"
0x2371b  ldstr    a24// "#24"
0x23720  call     native int System.Deployment.Application.NativeMethods::FindResource(native int hModule, string lpName, string lpType)
0x23725  stloc.0
0x23726  ldloc.0
0x23727  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x2372c  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x23731  brfalse.s loc_237AD
0x23733  ldloc.1
0x23734  ldloc.0
0x23735  call     unsigned int32 System.Deployment.Application.NativeMethods::SizeofResource(native int hModule, native int handle)
0x2373a  stloc.s  8
0x2373c  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x23741  stloc.s  7
0x23743  ldloc.s  8
0x23745  brtrue.s loc_23754
0x23747  ldloc.s  7
0x23749  ldstr    aExWin32resourc// "Ex_Win32ResourceLoadException"
0x2374e  ldarg.0
0x2374f  call     void System.Deployment.Application.Win32InterOp.SystemUtils::Win32LoadExceptionHelper(int32 win32ErrorCode, string resourceId, string filePath)
0x23754  ldloc.1
0x23755  ldloc.0
0x23756  call     native int System.Deployment.Application.NativeMethods::LoadResource(native int hModule, native int handle)
0x2375b  stloc.2
0x2375c  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x23761  stloc.s  7
0x23763  ldloc.2
0x23764  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x23769  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x2376e  brfalse.s loc_2377D
0x23770  ldloc.s  7
0x23772  ldstr    aExWin32resourc// "Ex_Win32ResourceLoadException"
0x23777  ldarg.0
0x23778  call     void System.Deployment.Application.Win32InterOp.SystemUtils::Win32LoadExceptionHelper(int32 win32ErrorCode, string resourceId, string filePath)
0x2377d  ldloc.2
0x2377e  call     native int System.Deployment.Application.NativeMethods::LockResource(native int hglobal)
0x23783  stloc.3
0x23784  ldloc.3
0x23785  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x2378a  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x2378f  brfalse.s loc_23799
0x23791  ldc.i4.s 0x21
0x23793  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x23798  throw
0x23799  ldloc.s  8
0x2379b  newarr   [mscorlib]System.Byte
0x237a0  stloc.s  6
0x237a2  ldloc.3
0x237a3  ldloc.s  6
0x237a5  ldc.i4.0
0x237a6  ldloc.s  8
0x237a8  call     void [mscorlib]System.Runtime.InteropServices.Marshal::Copy(native int, unsigned int8[], int32, int32)
0x237ad  leave.s  loc_237D8
0x237af  ldloc.1
0x237b0  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x237b5  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x237ba  brfalse.s loc_237D7
0x237bc  ldloc.1
0x237bd  call     bool System.Deployment.Application.NativeMethods::FreeLibrary(native int hModule)
0x237c2  stloc.s  9
0x237c4  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x237c9  stloc.s  7
0x237cb  ldloc.s  9
0x237cd  brtrue.s loc_237D7
0x237cf  ldloc.s  7
0x237d1  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x237d6  throw
0x237d7  endfinally
0x237d8  ldloc.s  6
0x237da  ret
```
