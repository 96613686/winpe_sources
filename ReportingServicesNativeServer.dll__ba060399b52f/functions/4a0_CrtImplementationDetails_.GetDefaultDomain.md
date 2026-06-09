# ::<CrtImplementationDetails>.GetDefaultDomain

- ea: `0x4a0`
- end: `0x4d6`
- name: `::<CrtImplementationDetails>.GetDefaultDomain`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x4e0`

## callees

- `0x430`
- `0x490`
- `0x4a0`

## pseudocode

```c

```

## disassembly

```asm
0x4a0  ldc.i4.0
0x4a1  conv.i8
0x4a2  stloc.1
0x4a3  ldloca.s 1
0x4a5  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 __get_default_appdomain(valuetype IUnknown** ppUnk)
0x4aa  stloc.0
0x4ab  ldloc.0
0x4ac  ldc.i4.0
0x4ad  blt.s    loc_4CC
0x4af  ldloca.s 3
0x4b1  ldloc.1
0x4b2  call     instance void [mscorlib]System.IntPtr::.ctor(void*)
0x4b7  ldloc.3
0x4b8  call     object [mscorlib]System.Runtime.InteropServices.Marshal::GetObjectForIUnknown(native int)
0x4bd  castclass [mscorlib]System.AppDomain
0x4c2  stloc.2
0x4c3  leave.s  loc_4D4
0x4c5  ldloc.1
0x4c6  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void __release_appdomain(valuetype IUnknown* ppUnk)
0x4cb  endfinally
0x4cc  ldloc.0
0x4cd  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x4d2  ldnull
0x4d3  ret
0x4d4  ldloc.2
0x4d5  ret
```
