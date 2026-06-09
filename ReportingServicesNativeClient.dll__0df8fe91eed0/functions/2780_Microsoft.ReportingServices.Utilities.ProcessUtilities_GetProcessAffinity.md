# Microsoft.ReportingServices.Utilities.ProcessUtilities::GetProcessAffinity

- ea: `0x2780`
- end: `0x27c9`
- name: `Microsoft.ReportingServices.Utilities.ProcessUtilities::GetProcessAffinity`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1110`
- `0x1120`
- `0x1140`
- `0x1160`
- `0x2780`

## pseudocode

```c

```

## disassembly

```asm
0x2780  ldc.i4.0
0x2781  stloc.1
0x2782  ldc.i4.0
0x2783  conv.i8
0x2784  stloc.3
0x2785  ldc.i4.0
0x2786  conv.i8
0x2787  stloc.s  4
0x2789  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void* GetCurrentProcess()
0x278e  stloc.2
0x278f  ldloc.2
0x2790  ldloca.s 3
0x2792  ldloca.s 4
0x2794  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) int32 GetProcessAffinityMask(void* nativeString, unsigned int64* cchSize, [hasfieldmarshal] unsigned int64* value)
0x2799  brtrue.s loc_27B6
0x279b  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 GetLastError()
0x27a0  stloc.0
0x27a1  ldloc.0
0x27a2  ldc.i4.0
0x27a3  bgt.s    loc_27A8
0x27a5  ldloc.0
0x27a6  br.s     loc_27B5
0x27a8  ldloc.0
0x27a9  ldc.i4   0xFFFF
0x27ae  and
0x27af  ldc.i4   0x80070000
0x27b4  or
0x27b5  stloc.1
0x27b6  ldloc.2
0x27b7  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) int32 CloseHandle(void* nativeString)
0x27bc  pop
0x27bd  ldloc.1
0x27be  ldc.i4.0
0x27bf  bge.s    loc_27C7
0x27c1  ldloc.1
0x27c2  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x27c7  ldloc.3
0x27c8  ret
```
