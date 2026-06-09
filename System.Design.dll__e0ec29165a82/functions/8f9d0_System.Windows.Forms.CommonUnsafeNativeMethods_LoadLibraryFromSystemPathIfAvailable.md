# System.Windows.Forms.CommonUnsafeNativeMethods::LoadLibraryFromSystemPathIfAvailable

- ea: `0x8f9d0`
- end: `0x8fa27`
- name: `System.Windows.Forms.CommonUnsafeNativeMethods::LoadLibraryFromSystemPathIfAvailable`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x8f8d0`

## callees

- `0x8f980`
- `0x8f990`
- `0x8f9a0`
- `0x8f9b0`
- `0x8f9d0`

## string_xrefs

- `0x8f9d6`: `kernel32.dll`
- `0x8f9f5`: `AddDllDirectory`

## pseudocode

```c

```

## disassembly

```asm
0x8f9d0  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x8f9d5  stloc.0
0x8f9d6  ldstr    aKernel32Dll// "kernel32.dll"
0x8f9db  call     native int System.Windows.Forms.CommonUnsafeNativeMethods::GetModuleHandle(string modName)
0x8f9e0  stloc.1
0x8f9e1  ldloc.1
0x8f9e2  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x8f9e7  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x8f9ec  brfalse.s loc_8FA25
0x8f9ee  ldnull
0x8f9ef  ldloc.1
0x8f9f0  newobj   instance void [mscorlib]System.Runtime.InteropServices.HandleRef::.ctor(object, native int)
0x8f9f5  ldstr    aAdddlldirector// "AddDllDirectory"
0x8f9fa  call     native int System.Windows.Forms.CommonUnsafeNativeMethods::GetProcAddress(valuetype [mscorlib]System.Runtime.InteropServices.HandleRef hModule, string lpProcName)
0x8f9ff  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x8fa04  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x8fa09  brfalse.s loc_8FA1E
0x8fa0b  ldarg.0
0x8fa0c  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x8fa11  ldc.i4   0x800
0x8fa16  call     native int System.Windows.Forms.CommonUnsafeNativeMethods::LoadLibraryEx(string lpModuleName, native int hFile, unsigned int32 dwFlags)
0x8fa1b  stloc.0
0x8fa1c  br.s     loc_8FA25
0x8fa1e  ldarg.0
0x8fa1f  call     native int System.Windows.Forms.CommonUnsafeNativeMethods::LoadLibrary(string libname)
0x8fa24  stloc.0
0x8fa25  ldloc.0
0x8fa26  ret
```
