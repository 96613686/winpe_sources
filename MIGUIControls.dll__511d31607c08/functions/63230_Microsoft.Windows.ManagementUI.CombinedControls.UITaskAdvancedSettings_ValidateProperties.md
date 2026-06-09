# Microsoft.Windows.ManagementUI.CombinedControls.UITaskAdvancedSettings::ValidateProperties

- ea: `0x63230`
- end: `0x63307`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.UITaskAdvancedSettings::ValidateProperties`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x65010`

## callees

- `0x12ed0`
- `0x1b9a0`
- `0x62e60`
- `0x62e80`
- `0x62f00`
- `0x63230`

## string_xrefs

- `0x6327d`: `UITaskAdvancedSettings`
- `0x632aa`: `UITaskAdvancedSettings`
- `0x632f5`: `UITaskAdvancedSettings`

## pseudocode

```c

```

## disassembly

```asm
0x63230  ldsfld   valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::MinValue
0x63235  ldarg.0
0x63236  call     instance valuetype [mscorlib]System.TimeSpan Microsoft.Windows.ManagementUI.CombinedControls.UITaskAdvancedSettings::get_RestartInterval()
0x6323b  call     bool [mscorlib]System.TimeSpan::op_Inequality(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x63240  brfalse.s loc_632BB
0x63242  ldc.i4.0
0x63243  ldarg.0
0x63244  call     instance valuetype [mscorlib]System.TimeSpan Microsoft.Windows.ManagementUI.CombinedControls.UITaskAdvancedSettings::get_RestartInterval()
0x63249  stloc.0
0x6324a  ldloca.s 0
0x6324c  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.Windows.ManagementUI.CombinedControls.UITaskAdvancedSettings::RestartIntervalMinimum
0x63251  call     instance int32 [mscorlib]System.TimeSpan::CompareTo(valuetype [mscorlib]System.TimeSpan)
0x63256  bgt.s    loc_6326E
0x63258  ldc.i4.0
0x63259  ldarg.0
0x6325a  call     instance valuetype [mscorlib]System.TimeSpan Microsoft.Windows.ManagementUI.CombinedControls.UITaskAdvancedSettings::get_RestartInterval()
0x6325f  stloc.0
0x63260  ldloca.s 0
0x63262  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.Windows.ManagementUI.CombinedControls.UITaskAdvancedSettings::RestartIntervalMaximum
0x63267  call     instance int32 [mscorlib]System.TimeSpan::CompareTo(valuetype [mscorlib]System.TimeSpan)
0x6326c  bge.s    loc_6328E
0x6326e  ldstr    aTsvalidationms_10// "TSValidationMsgRestartIntervalOutOfRang"...
0x63273  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x63278  ldc.i4   0x80041318
0x6327d  ldstr    aUitaskadvanced// "UITaskAdvancedSettings"
0x63282  ldstr    aRestartinterva// "RestartInterval"
0x63287  ldnull
0x63288  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.UIValidationException::.ctor(string message, unsigned int32 hResult, string inSectionName, string inPropertyName, string inPropertyId)
0x6328d  throw
0x6328e  ldsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.UITaskAdvancedSettings::RestartCountMinimum
0x63293  ldarg.0
0x63294  call     instance int32 Microsoft.Windows.ManagementUI.CombinedControls.UITaskAdvancedSettings::get_RestartCount()
0x63299  ble.s    loc_632BB
0x6329b  ldstr    aTsvalidationms_11// "TSValidationMsgRestartCountOutOfRange"
0x632a0  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x632a5  ldc.i4   0x80041318
0x632aa  ldstr    aUitaskadvanced// "UITaskAdvancedSettings"
0x632af  ldstr    aRestartcount// "RestartCount"
0x632b4  ldnull
0x632b5  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.UIValidationException::.ctor(string message, unsigned int32 hResult, string inSectionName, string inPropertyName, string inPropertyId)
0x632ba  throw
0x632bb  ldarg.0
0x632bc  call     instance valuetype [mscorlib]System.TimeSpan Microsoft.Windows.ManagementUI.CombinedControls.UITaskAdvancedSettings::get_ExecutionTimeLimit()
0x632c1  stloc.0
0x632c2  ldloca.s 0
0x632c4  ldsfld   valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::MinValue
0x632c9  call     instance int32 [mscorlib]System.TimeSpan::CompareTo(valuetype [mscorlib]System.TimeSpan)
0x632ce  brfalse.s loc_63306
0x632d0  ldc.i4.0
0x632d1  ldarg.0
0x632d2  call     instance valuetype [mscorlib]System.TimeSpan Microsoft.Windows.ManagementUI.CombinedControls.UITaskAdvancedSettings::get_ExecutionTimeLimit()
0x632d7  stloc.0
0x632d8  ldloca.s 0
0x632da  ldsfld   valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Zero
0x632df  call     instance int32 [mscorlib]System.TimeSpan::CompareTo(valuetype [mscorlib]System.TimeSpan)
0x632e4  blt.s    loc_63306
0x632e6  ldstr    aTsvalidationms_4// "TSValidationMsgExecutionLimitOutOfRange"
0x632eb  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x632f0  ldc.i4   0x80041318
0x632f5  ldstr    aUitaskadvanced// "UITaskAdvancedSettings"
0x632fa  ldstr    aExecutiontimel// "ExecutionTimeLimit"
0x632ff  ldnull
0x63300  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.UIValidationException::.ctor(string message, unsigned int32 hResult, string inSectionName, string inPropertyName, string inPropertyId)
0x63305  throw
0x63306  ret
```
