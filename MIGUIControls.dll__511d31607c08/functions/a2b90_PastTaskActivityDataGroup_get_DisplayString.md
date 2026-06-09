# PastTaskActivityDataGroup::get_DisplayString

- ea: `0xa2b90`
- end: `0xa2c7b`
- name: `PastTaskActivityDataGroup::get_DisplayString`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x7f130`

## callees

- `0x12ed0`
- `0xa2990`
- `0xa2a90`
- `0xa2b90`
- `0xa2c80`

## string_xrefs

- `0xa2c1e`: `LabelSingleTaskStatusEnded`
- `0xa2c5c`: `LabelSingleTaskStatusRunning`

## pseudocode

```c

```

## disassembly

```asm
0xa2b90  ldarg.0
0xa2b91  ldfld    class [mscorlib]System.Collections.ArrayList PastTaskActivityDataGroup::pastTaskActivityDataList
0xa2b96  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xa2b9b  brtrue.s loc_A2BA4
0xa2b9d  ldarg.0
0xa2b9e  call     instance string PastTaskActivityDataGroup::get_TaskName()
0xa2ba3  ret
0xa2ba4  ldarg.0
0xa2ba5  ldfld    bool PastTaskActivityDataGroup::isSorted
0xa2baa  brtrue.s loc_A2BBE
0xa2bac  ldarg.0
0xa2bad  ldfld    class [mscorlib]System.Collections.ArrayList PastTaskActivityDataGroup::pastTaskActivityDataList
0xa2bb2  callvirt instance void [mscorlib]System.Collections.ArrayList::Sort()
0xa2bb7  ldarg.0
0xa2bb8  ldc.i4.1
0xa2bb9  stfld    bool PastTaskActivityDataGroup::isSorted
0xa2bbe  ldarg.0
0xa2bbf  ldfld    class [mscorlib]System.Collections.ArrayList PastTaskActivityDataGroup::pastTaskActivityDataList
0xa2bc4  ldc.i4.0
0xa2bc5  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xa2bca  castclass PastTaskActivityData
0xa2bcf  stloc.0
0xa2bd0  ldloc.0
0xa2bd1  callvirt instance valuetype [mscorlib]System.DateTime PastTaskActivityData::get_EndTime()
0xa2bd6  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0xa2bdb  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xa2be0  brfalse.s loc_A2C57
0xa2be2  ldc.i4.1
0xa2be3  ldloc.0
0xa2be4  callvirt instance valuetype TaskStatusEnum PastTaskActivityData::get_TaskStatus()
0xa2be9  bne.un.s loc_A2BF8
0xa2beb  ldstr    aSucceeded// "succeeded"
0xa2bf0  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0xa2bf5  stloc.1
0xa2bf6  br.s     loc_A2C19
0xa2bf8  ldc.i4.3
0xa2bf9  ldloc.0
0xa2bfa  callvirt instance valuetype TaskStatusEnum PastTaskActivityData::get_TaskStatus()
0xa2bff  bne.un.s loc_A2C0E
0xa2c01  ldstr    aFailed// "failed"
0xa2c06  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0xa2c0b  stloc.1
0xa2c0c  br.s     loc_A2C19
0xa2c0e  ldstr    aTerminated// "terminated"
0xa2c13  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0xa2c18  stloc.1
0xa2c19  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xa2c1e  ldstr    aLabelsingletas// "LabelSingleTaskStatusEnded"
0xa2c23  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0xa2c28  ldc.i4.3
0xa2c29  newarr   [mscorlib]System.Object
0xa2c2e  dup
0xa2c2f  ldc.i4.0
0xa2c30  ldarg.0
0xa2c31  call     instance string PastTaskActivityDataGroup::get_TaskName()
0xa2c36  stelem.ref
0xa2c37  dup
0xa2c38  ldc.i4.1
0xa2c39  ldloc.1
0xa2c3a  stelem.ref
0xa2c3b  dup
0xa2c3c  ldc.i4.2
0xa2c3d  ldloc.0
0xa2c3e  callvirt instance valuetype [mscorlib]System.DateTime PastTaskActivityData::get_EndTime()
0xa2c43  stloc.2
0xa2c44  ldloca.s 2
0xa2c46  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xa2c4b  call     instance string [mscorlib]System.DateTime::ToString(class [mscorlib]System.IFormatProvider)
0xa2c50  stelem.ref
0xa2c51  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa2c56  ret
0xa2c57  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xa2c5c  ldstr    aLabelsingletas_0// "LabelSingleTaskStatusRunning"
0xa2c61  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0xa2c66  ldc.i4.1
0xa2c67  newarr   [mscorlib]System.Object
0xa2c6c  dup
0xa2c6d  ldc.i4.0
0xa2c6e  ldarg.0
0xa2c6f  call     instance string PastTaskActivityDataGroup::get_TaskName()
0xa2c74  stelem.ref
0xa2c75  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa2c7a  ret
```
