# Microsoft.ReportingServices.Utilities.ProcessUtilities::SetProcessAffinity

- ea: `0x27d0`
- end: `0x280e`
- name: `Microsoft.ReportingServices.Utilities.ProcessUtilities::SetProcessAffinity`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1110`
- `0x1120`
- `0x1150`
- `0x1160`
- `0x27d0`

## pseudocode

```c

```

## disassembly

```asm
0x27d0  ldc.i4.0
0x27d1  stloc.1
0x27d2  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void* GetCurrentProcess()
0x27d7  stloc.2
0x27d8  ldloc.2
0x27d9  ldarg.0
0x27da  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) int32 SetProcessAffinityMask(void* nativeString, unsigned int64 cchSize)
0x27df  brtrue.s loc_27FC
0x27e1  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 GetLastError()
0x27e6  stloc.0
0x27e7  ldloc.0
0x27e8  ldc.i4.0
0x27e9  bgt.s    loc_27EE
0x27eb  ldloc.0
0x27ec  br.s     loc_27FB
0x27ee  ldloc.0
0x27ef  ldc.i4   0xFFFF
0x27f4  and
0x27f5  ldc.i4   0x80070000
0x27fa  or
0x27fb  stloc.1
0x27fc  ldloc.2
0x27fd  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) int32 CloseHandle(void* nativeString)
0x2802  pop
0x2803  ldloc.1
0x2804  ldc.i4.0
0x2805  bge.s    loc_280D
0x2807  ldloc.1
0x2808  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x280d  ret
```
