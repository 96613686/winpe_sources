# Microsoft.Windows.ManagementUI.CombinedControls.CEventsCommon::GetColumnName

- ea: `0x36bc0`
- end: `0x36d9e`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.CEventsCommon::GetColumnName`
- size: `478`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x32ab0`
- `0x3e5a0`
- `0x3e920`

## callees

- `0x12ed0`
- `0x36a60`
- `0x36bc0`

## string_xrefs

- `0x36c8f`: `Computer`
- `0x36cc7`: `ProcessId`
- `0x36ccf`: `ThreadId`

## pseudocode

```c

```

## disassembly

```asm
0x36bc0  ldsfld   string [mscorlib]System.String::Empty
0x36bc5  stloc.0
0x36bc6  ldarg.0
0x36bc7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x36bcc  brtrue   loc_36D9C
0x36bd1  ldarg.0
0x36bd2  call     int32 Microsoft.Windows.ManagementUI.CombinedControls.CEventsCommon::GetColumnIdentifierForPath(string colPath)
0x36bd7  stloc.1
0x36bd8  ldloc.1
0x36bd9  ldc.i4.0
0x36bda  ble      loc_36D26
0x36bdf  ldsfld   string [mscorlib]System.String::Empty
0x36be4  stloc.2
0x36be5  ldloc.1
0x36be6  ldc.i4.1
0x36be7  sub
0x36be8  switch   loc_36C6E, loc_36C79, loc_36CEF, loc_36CF7, loc_36CFF, loc_36CC7, loc_36CCF, loc_36CD7, loc_36CDF, loc_36CE7, loc_36D07, loc_36D0F, loc_36D15, loc_36D15, loc_36D15, loc_36C84, loc_36C8F, loc_36C97, loc_36D15, loc_36D15, loc_36D15, loc_36D15, loc_36D15, loc_36C9F, loc_36CA7, loc_36D15, loc_36D15, loc_36CAF, loc_36D15, loc_36CB7, loc_36CBF
0x36c69  br       loc_36D15
0x36c6e  ldstr    aEventid// "EventId"
0x36c73  stloc.2
0x36c74  br       loc_36D15
0x36c79  ldstr    aTimegenerated// "TimeGenerated"
0x36c7e  stloc.2
0x36c7f  br       loc_36D15
0x36c84  ldstr    aChannel// "Channel"
0x36c89  stloc.2
0x36c8a  br       loc_36D15
0x36c8f  ldstr    aComputer// "Computer"
0x36c94  stloc.2
0x36c95  br.s     loc_36D15
0x36c97  ldstr    aUserid// "UserId"
0x36c9c  stloc.2
0x36c9d  br.s     loc_36D15
0x36c9f  ldstr    aKeywords// "Keywords"
0x36ca4  stloc.2
0x36ca5  br.s     loc_36D15
0x36ca7  ldstr    aOpcode// "OpCode"
0x36cac  stloc.2
0x36cad  br.s     loc_36D15
0x36caf  ldstr    aCategory// "Category"
0x36cb4  stloc.2
0x36cb5  br.s     loc_36D15
0x36cb7  ldstr    aLevel// "Level"
0x36cbc  stloc.2
0x36cbd  br.s     loc_36D15
0x36cbf  ldstr    aEventsource// "EventSource"
0x36cc4  stloc.2
0x36cc5  br.s     loc_36D15
0x36cc7  ldstr    aProcessid// "ProcessId"
0x36ccc  stloc.2
0x36ccd  br.s     loc_36D15
0x36ccf  ldstr    aThreadid// "ThreadId"
0x36cd4  stloc.2
0x36cd5  br.s     loc_36D15
0x36cd7  ldstr    aCorrelationid// "CorrelationId"
0x36cdc  stloc.2
0x36cdd  br.s     loc_36D15
0x36cdf  ldstr    aRelativecorrel// "RelativeCorrelationId"
0x36ce4  stloc.2
0x36ce5  br.s     loc_36D15
0x36ce7  ldstr    aEventsourcenam// "EventSourceName"
0x36cec  stloc.2
0x36ced  br.s     loc_36D15
0x36cef  ldstr    aProcessorid// "ProcessorId"
0x36cf4  stloc.2
0x36cf5  br.s     loc_36D15
0x36cf7  ldstr    aSessionid// "SessionId"
0x36cfc  stloc.2
0x36cfd  br.s     loc_36D15
0x36cff  ldstr    aKerneltime// "KernelTime"
0x36d04  stloc.2
0x36d05  br.s     loc_36D15
0x36d07  ldstr    aUsertime// "UserTime"
0x36d0c  stloc.2
0x36d0d  br.s     loc_36D15
0x36d0f  ldstr    aProcessortime// "ProcessorTime"
0x36d14  stloc.2
0x36d15  ldloc.2
0x36d16  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x36d1b  brtrue.s loc_36D9C
0x36d1d  ldloc.2
0x36d1e  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x36d23  stloc.0
0x36d24  br.s     loc_36D9C
0x36d26  ldstr    asc_AE8C4// "@"
0x36d2b  stloc.3
0x36d2c  ldstr    asc_AC608// "/"
0x36d31  stloc.s  4
0x36d33  ldstr    asc_AC608// "/"
0x36d38  stloc.s  5
0x36d3a  ldarg.0
0x36d3b  ldloc.3
0x36d3c  ldc.i4.5
0x36d3d  callvirt instance int32 [mscorlib]System.String::LastIndexOf(string, valuetype [mscorlib]System.StringComparison)
0x36d42  stloc.s  6
0x36d44  ldarg.0
0x36d45  ldloc.s  4
0x36d47  ldc.i4.5
0x36d48  callvirt instance int32 [mscorlib]System.String::LastIndexOf(string, valuetype [mscorlib]System.StringComparison)
0x36d4d  stloc.s  7
0x36d4f  ldarg.0
0x36d50  ldloc.s  5
0x36d52  ldc.i4.5
0x36d53  callvirt instance int32 [mscorlib]System.String::LastIndexOf(string, valuetype [mscorlib]System.StringComparison)
0x36d58  stloc.s  8
0x36d5a  ldloc.s  6
0x36d5c  ldc.i4.m1
0x36d5d  beq.s    loc_36D6A
0x36d5f  ldarg.0
0x36d60  ldloc.s  6
0x36d62  ldc.i4.1
0x36d63  add
0x36d64  callvirt instance string [mscorlib]System.String::Substring(int32)
0x36d69  stloc.0
0x36d6a  ldloc.s  7
0x36d6c  ldc.i4.m1
0x36d6d  beq.s    loc_36D80
0x36d6f  ldloc.s  7
0x36d71  ldloc.s  6
0x36d73  ble.s    loc_36D80
0x36d75  ldarg.0
0x36d76  ldloc.s  7
0x36d78  ldc.i4.1
0x36d79  add
0x36d7a  callvirt instance string [mscorlib]System.String::Substring(int32)
0x36d7f  stloc.0
0x36d80  ldloc.s  8
0x36d82  ldc.i4.m1
0x36d83  beq.s    loc_36D9C
0x36d85  ldloc.s  8
0x36d87  ldloc.s  6
0x36d89  ble.s    loc_36D9C
0x36d8b  ldloc.s  8
0x36d8d  ldloc.s  7
0x36d8f  ble.s    loc_36D9C
0x36d91  ldarg.0
0x36d92  ldloc.s  8
0x36d94  ldc.i4.1
0x36d95  add
0x36d96  callvirt instance string [mscorlib]System.String::Substring(int32)
0x36d9b  stloc.0
0x36d9c  ldloc.0
0x36d9d  ret
```
