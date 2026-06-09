# Microsoft.ReportingServices.Utilities.MetaUtil::IsAnonymousAllowed

- ea: `0x26b0`
- end: `0x26df`
- name: `Microsoft.ReportingServices.Utilities.MetaUtil::IsAnonymousAllowed`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1100`
- `0x1130`
- `0x26b0`

## pseudocode

```c

```

## disassembly

```asm
0x26b0  ldc.i4.0
0x26b1  stloc.2
0x26b2  ldarg.1
0x26b3  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::StringToHGlobalUni(string)
0x26b8  stloc.3
0x26b9  ldloca.s 3
0x26bb  call     instance void* [mscorlib]System.IntPtr::ToPointer()
0x26c0  stloc.0
0x26c1  ldloc.0
0x26c2  ldloca.s 2
0x26c4  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 AllowsAnonymous(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) unsigned int16* nativeString, bool* cchSize)
0x26c9  stloc.1
0x26ca  ldloc.0
0x26cb  brfalse.s loc_26D3
0x26cd  ldloc.0
0x26ce  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void CoTaskMemFree(void* nativeString)
0x26d3  ldloc.1
0x26d4  ldc.i4.0
0x26d5  bge.s    loc_26DD
0x26d7  ldloc.1
0x26d8  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x26dd  ldloc.2
0x26de  ret
```
