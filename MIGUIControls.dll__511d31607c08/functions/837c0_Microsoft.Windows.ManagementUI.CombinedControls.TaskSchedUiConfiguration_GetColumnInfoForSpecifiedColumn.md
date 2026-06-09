# Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::GetColumnInfoForSpecifiedColumn

- ea: `0x837c0`
- end: `0x838ca`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::GetColumnInfoForSpecifiedColumn`
- size: `266`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x83330`
- `0x83660`

## callees

- `0x12ed0`
- `0x837c0`

## string_xrefs

- `0x837da`: `ColumnTaskSchedulerName`
- `0x837fa`: `ColumnTaskSchedulerStatus`
- `0x8381a`: `ColumnTaskSchedulerTriggers`
- `0x8383a`: `ColumnTaskSchedulerNextRun`
- `0x83857`: `ColumnTaskSchedulerLastRun`
- `0x83874`: `ColumnTaskSchedulerLastResult`
- `0x83891`: `ColumnTaskSchedulerAuthor`
- `0x838ae`: `ColumnTaskSchedulerCreatedOn`

## pseudocode

```c

```

## disassembly

```asm
0x837c0  ldloca.s 0
0x837c2  initobj  ColumnInfo
0x837c8  ldloca.s 0
0x837ca  ldarg.1
0x837cb  stfld    string ColumnInfo::Name
0x837d0  ldloca.s 0
0x837d2  ldc.i4.s 0xFE
0x837d4  stfld    int32 ColumnInfo::Width
0x837d9  ldarg.1
0x837da  ldstr    aColumntasksche// "ColumnTaskSchedulerName"
0x837df  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x837e4  ldc.i4.5
0x837e5  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x837ea  brtrue.s loc_837F9
0x837ec  ldloca.s 0
0x837ee  ldc.i4.1
0x837ef  stfld    valuetype SupportedColumns ColumnInfo::Tag
0x837f4  br       loc_838C8
0x837f9  ldarg.1
0x837fa  ldstr    aColumntasksche_0// "ColumnTaskSchedulerStatus"
0x837ff  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x83804  ldc.i4.5
0x83805  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x8380a  brtrue.s loc_83819
0x8380c  ldloca.s 0
0x8380e  ldc.i4.2
0x8380f  stfld    valuetype SupportedColumns ColumnInfo::Tag
0x83814  br       loc_838C8
0x83819  ldarg.1
0x8381a  ldstr    aColumntasksche_1// "ColumnTaskSchedulerTriggers"
0x8381f  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x83824  ldc.i4.5
0x83825  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x8382a  brtrue.s loc_83839
0x8382c  ldloca.s 0
0x8382e  ldc.i4.3
0x8382f  stfld    valuetype SupportedColumns ColumnInfo::Tag
0x83834  br       loc_838C8
0x83839  ldarg.1
0x8383a  ldstr    aColumntasksche_2// "ColumnTaskSchedulerNextRun"
0x8383f  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x83844  ldc.i4.5
0x83845  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x8384a  brtrue.s loc_83856
0x8384c  ldloca.s 0
0x8384e  ldc.i4.4
0x8384f  stfld    valuetype SupportedColumns ColumnInfo::Tag
0x83854  br.s     loc_838C8
0x83856  ldarg.1
0x83857  ldstr    aColumntasksche_3// "ColumnTaskSchedulerLastRun"
0x8385c  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x83861  ldc.i4.5
0x83862  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x83867  brtrue.s loc_83873
0x83869  ldloca.s 0
0x8386b  ldc.i4.5
0x8386c  stfld    valuetype SupportedColumns ColumnInfo::Tag
0x83871  br.s     loc_838C8
0x83873  ldarg.1
0x83874  ldstr    aColumntasksche_4// "ColumnTaskSchedulerLastResult"
0x83879  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x8387e  ldc.i4.5
0x8387f  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x83884  brtrue.s loc_83890
0x83886  ldloca.s 0
0x83888  ldc.i4.6
0x83889  stfld    valuetype SupportedColumns ColumnInfo::Tag
0x8388e  br.s     loc_838C8
0x83890  ldarg.1
0x83891  ldstr    aColumntasksche_5// "ColumnTaskSchedulerAuthor"
0x83896  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x8389b  ldc.i4.5
0x8389c  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x838a1  brtrue.s loc_838AD
0x838a3  ldloca.s 0
0x838a5  ldc.i4.7
0x838a6  stfld    valuetype SupportedColumns ColumnInfo::Tag
0x838ab  br.s     loc_838C8
0x838ad  ldarg.1
0x838ae  ldstr    aColumntasksche_6// "ColumnTaskSchedulerCreatedOn"
0x838b3  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x838b8  ldc.i4.5
0x838b9  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x838be  brtrue.s loc_838C8
0x838c0  ldloca.s 0
0x838c2  ldc.i4.8
0x838c3  stfld    valuetype SupportedColumns ColumnInfo::Tag
0x838c8  ldloc.0
0x838c9  ret
```
