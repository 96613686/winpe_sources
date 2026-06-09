# Microsoft.ReportingServices.Diagnostics.ResourceUtilities::get_TooMuchMemory

- ea: `0xb110`
- end: `0xb126`
- name: `Microsoft.ReportingServices.Diagnostics.ResourceUtilities::get_TooMuchMemory`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0xa9e0`
- `0xb0c0`
- `0xb110`
- `0xb130`

## pseudocode

```c

```

## disassembly

```asm
0xb110  call     bool Microsoft.ReportingServices.Diagnostics.Globals::get_NoMemoryThrottling()
0xb115  brtrue.s loc_B124
0xb117  call     int64 Microsoft.ReportingServices.Diagnostics.ResourceUtilities::get_PrivateMBytes()
0xb11c  call     int64 Microsoft.ReportingServices.Diagnostics.ResourceUtilities::get_MaxMemoryThresholdMB()
0xb121  cgt
0xb123  ret
0xb124  ldc.i4.0
0xb125  ret
```
