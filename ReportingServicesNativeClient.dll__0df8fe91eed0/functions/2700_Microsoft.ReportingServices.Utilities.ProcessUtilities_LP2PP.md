# Microsoft.ReportingServices.Utilities.ProcessUtilities::LP2PP

- ea: `0x2700`
- end: `0x2716`
- name: `Microsoft.ReportingServices.Utilities.ProcessUtilities::LP2PP`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1170`
- `0x2700`

## pseudocode

```c

```

## disassembly

```asm
0x2700  ldc.i4.0
0x2701  conv.i8
0x2702  stloc.0
0x2703  ldloca.s 0
0x2705  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 GetProcessorInformation(unsigned int64* nativeString)
0x270a  ldc.i4.0
0x270b  blt.s    loc_2710
0x270d  ldloc.0
0x270e  br.s     loc_2712
0x2710  ldc.i4.1
0x2711  conv.i8
0x2712  stloc.0
0x2713  ldloc.0
0x2714  conv.i4
0x2715  ret
```
