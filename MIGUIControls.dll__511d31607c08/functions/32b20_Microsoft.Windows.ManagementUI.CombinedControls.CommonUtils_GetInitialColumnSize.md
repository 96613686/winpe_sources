# Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::GetInitialColumnSize

- ea: `0x32b20`
- end: `0x32d36`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::GetInitialColumnSize`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x32ab0`

## callees

- `0x12ed0`
- `0x32b20`

## string_xrefs

- `0x32b75`: `Computer`
- `0x32c35`: `ProcessId`
- `0x32c50`: `ThreadId`

## pseudocode

```c

```

## disassembly

```asm
0x32b20  ldc.i4.s 0x3C
0x32b22  stloc.0
0x32b23  ldarg.0
0x32b24  ldstr    aEventid// "EventId"
0x32b29  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x32b2e  ldc.i4.0
0x32b2f  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x32b34  brtrue.s loc_32B3E
0x32b36  ldc.i4.s 0x32
0x32b38  stloc.0
0x32b39  br       loc_32D34
0x32b3e  ldarg.0
0x32b3f  ldstr    aTimegenerated// "TimeGenerated"
0x32b44  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x32b49  ldc.i4.0
0x32b4a  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x32b4f  brtrue.s loc_32B59
0x32b51  ldc.i4.s 0x3C
0x32b53  stloc.0
0x32b54  br       loc_32D34
0x32b59  ldarg.0
0x32b5a  ldstr    aChannel// "Channel"
0x32b5f  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x32b64  ldc.i4.0
0x32b65  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x32b6a  brtrue.s loc_32B74
0x32b6c  ldc.i4.s 0x50
0x32b6e  stloc.0
0x32b6f  br       loc_32D34
0x32b74  ldarg.0
0x32b75  ldstr    aComputer// "Computer"
0x32b7a  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x32b7f  ldc.i4.0
0x32b80  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x32b85  brtrue.s loc_32B92
0x32b87  ldc.i4   0xAA
0x32b8c  stloc.0
0x32b8d  br       loc_32D34
0x32b92  ldarg.0
0x32b93  ldstr    aUserid// "UserId"
0x32b98  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x32b9d  ldc.i4.0
0x32b9e  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x32ba3  brtrue.s loc_32BAD
0x32ba5  ldc.i4.s 0x32
0x32ba7  stloc.0
0x32ba8  br       loc_32D34
0x32bad  ldarg.0
0x32bae  ldstr    aKeywords// "Keywords"
0x32bb3  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x32bb8  ldc.i4.0
0x32bb9  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x32bbe  brtrue.s loc_32BC8
0x32bc0  ldc.i4.s 0x46
0x32bc2  stloc.0
0x32bc3  br       loc_32D34
0x32bc8  ldarg.0
0x32bc9  ldstr    aOpcode// "OpCode"
0x32bce  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x32bd3  ldc.i4.0
0x32bd4  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x32bd9  brtrue.s loc_32BE3
0x32bdb  ldc.i4.s 0x6E
0x32bdd  stloc.0
0x32bde  br       loc_32D34
0x32be3  ldarg.0
0x32be4  ldstr    aCategory// "Category"
0x32be9  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x32bee  ldc.i4.0
0x32bef  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x32bf4  brtrue.s loc_32BFE
0x32bf6  ldc.i4.s 0x64
0x32bf8  stloc.0
0x32bf9  br       loc_32D34
0x32bfe  ldarg.0
0x32bff  ldstr    aLevel// "Level"
0x32c04  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x32c09  ldc.i4.0
0x32c0a  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x32c0f  brtrue.s loc_32C19
0x32c11  ldc.i4.s 0x32
0x32c13  stloc.0
0x32c14  br       loc_32D34
0x32c19  ldarg.0
0x32c1a  ldstr    aEventsource// "EventSource"
0x32c1f  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x32c24  ldc.i4.0
0x32c25  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x32c2a  brtrue.s loc_32C34
0x32c2c  ldc.i4.s 0x5A
0x32c2e  stloc.0
0x32c2f  br       loc_32D34
0x32c34  ldarg.0
0x32c35  ldstr    aProcessid// "ProcessId"
0x32c3a  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x32c3f  ldc.i4.0
0x32c40  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x32c45  brtrue.s loc_32C4F
0x32c47  ldc.i4.s 0x46
0x32c49  stloc.0
0x32c4a  br       loc_32D34
0x32c4f  ldarg.0
0x32c50  ldstr    aThreadid// "ThreadId"
0x32c55  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x32c5a  ldc.i4.0
0x32c5b  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x32c60  brtrue.s loc_32C6A
0x32c62  ldc.i4.s 0x46
0x32c64  stloc.0
0x32c65  br       loc_32D34
0x32c6a  ldarg.0
0x32c6b  ldstr    aCorrelationid// "CorrelationId"
0x32c70  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x32c75  ldc.i4.0
0x32c76  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x32c7b  brtrue.s loc_32C85
0x32c7d  ldc.i4.s 0x55
0x32c7f  stloc.0
0x32c80  br       loc_32D34
0x32c85  ldarg.0
0x32c86  ldstr    aRelativecorrel// "RelativeCorrelationId"
0x32c8b  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x32c90  ldc.i4.0
0x32c91  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x32c96  brtrue.s loc_32CA3
0x32c98  ldc.i4   0x8C
0x32c9d  stloc.0
0x32c9e  br       loc_32D34
0x32ca3  ldarg.0
0x32ca4  ldstr    aEventsourcenam// "EventSourceName"
0x32ca9  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x32cae  ldc.i4.0
0x32caf  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x32cb4  brtrue.s loc_32CBE
0x32cb6  ldc.i4   0x8C
0x32cbb  stloc.0
0x32cbc  br.s     loc_32D34
0x32cbe  ldarg.0
0x32cbf  ldstr    aProcessorid// "ProcessorId"
0x32cc4  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x32cc9  ldc.i4.0
0x32cca  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x32ccf  brtrue.s loc_32CD6
0x32cd1  ldc.i4.s 0x5A
0x32cd3  stloc.0
0x32cd4  br.s     loc_32D34
0x32cd6  ldarg.0
0x32cd7  ldstr    aSessionid// "SessionId"
0x32cdc  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x32ce1  ldc.i4.0
0x32ce2  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x32ce7  brtrue.s loc_32CEE
0x32ce9  ldc.i4.s 0x46
0x32ceb  stloc.0
0x32cec  br.s     loc_32D34
0x32cee  ldarg.0
0x32cef  ldstr    aKerneltime// "KernelTime"
0x32cf4  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x32cf9  ldc.i4.0
0x32cfa  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x32cff  brtrue.s loc_32D06
0x32d01  ldc.i4.s 0x50
0x32d03  stloc.0
0x32d04  br.s     loc_32D34
0x32d06  ldarg.0
0x32d07  ldstr    aUsertime// "UserTime"
0x32d0c  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x32d11  ldc.i4.0
0x32d12  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x32d17  brtrue.s loc_32D1E
0x32d19  ldc.i4.s 0x46
0x32d1b  stloc.0
0x32d1c  br.s     loc_32D34
0x32d1e  ldarg.0
0x32d1f  ldstr    aProcessortime// "ProcessorTime"
0x32d24  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x32d29  ldc.i4.0
0x32d2a  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x32d2f  brtrue.s loc_32D34
0x32d31  ldc.i4.s 0x64
0x32d33  stloc.0
0x32d34  ldloc.0
0x32d35  ret
```
