# Microsoft.ReportingServices.Utilities.ProcessUtilities::GetProcessTimes

- ea: `0x2720`
- end: `0x277c`
- name: `Microsoft.ReportingServices.Utilities.ProcessUtilities::GetProcessTimes`
- size: `92`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x10f0`
- `0x1110`
- `0x1120`
- `0x1160`
- `0x2720`
- `0x2810`

## pseudocode

```c

```

## disassembly

```asm
0x2720  ldc.i4.0
0x2721  stloc.1
0x2722  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void* GetCurrentProcess()
0x2727  stloc.2
0x2728  ldloc.2
0x2729  ldloca.s 8
0x272b  ldloca.s 7
0x272d  ldloca.s 6
0x272f  ldloca.s 5
0x2731  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) int32 GetProcessTimes(void* nativeString, valuetype _FILETIME* cchSize, [hasfieldmarshal] valuetype _FILETIME* value, [hasfieldmarshal] valuetype _FILETIME* value, valuetype _FILETIME* managedArray)
0x2736  brtrue.s loc_2755
0x2738  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 GetLastError()
0x273d  stloc.0
0x273e  ldloc.0
0x273f  ldc.i4.0
0x2740  bgt.s    loc_2745
0x2742  ldloc.0
0x2743  br.s     loc_2752
0x2745  ldloc.0
0x2746  ldc.i4   0xFFFF
0x274b  and
0x274c  ldc.i4   0x80070000
0x2751  or
0x2752  stloc.1
0x2753  br.s     loc_2769
0x2755  ldloc.s  6
0x2757  call     int64 Microsoft.ReportingServices.Utilities.ProcessUtilities::CombineFileTime(valuetype _FILETIME fileTime)
0x275c  stloc.s  4
0x275e  ldloc.s  5
0x2760  call     int64 Microsoft.ReportingServices.Utilities.ProcessUtilities::CombineFileTime(valuetype _FILETIME fileTime)
0x2765  ldloc.s  4
0x2767  add
0x2768  stloc.3
0x2769  ldloc.2
0x276a  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) int32 CloseHandle(void* nativeString)
0x276f  pop
0x2770  ldloc.1
0x2771  ldc.i4.0
0x2772  bge.s    loc_277A
0x2774  ldloc.1
0x2775  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x277a  ldloc.3
0x277b  ret
```
