# Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::UpdateEventsListProgress

- ea: `0x28fd0`
- end: `0x29036`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::UpdateEventsListProgress`
- size: `102`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x28cd0`
- `0x29a00`

## callees

- `0x12ed0`
- `0x28fd0`

## string_xrefs

- `0x28fe3`: `SummaryPageReadingData_Wait`
- `0x29012`: `ReadingLogDataProgress`

## pseudocode

```c

```

## disassembly

```asm
0x28fd0  ldarg.0
0x28fd1  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::curChannel
0x28fd6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x28fdb  brfalse.s loc_28FF3
0x28fdd  ldarg.0
0x28fde  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::eventSummaryLabel
0x28fe3  ldstr    aSummarypagerea// "SummaryPageReadingData_Wait"
0x28fe8  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x28fed  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x28ff2  ret
0x28ff3  ldarg.0
0x28ff4  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::eventSummaryLabel
0x28ff9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x28ffe  ldtoken  [mscorlib]System.String
0x29003  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x29008  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x2900d  castclass [mscorlib]System.IFormatProvider
0x29012  ldstr    aReadinglogdata// "ReadingLogDataProgress"
0x29017  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x2901c  ldc.i4.1
0x2901d  newarr   [mscorlib]System.Object
0x29022  dup
0x29023  ldc.i4.0
0x29024  ldarg.0
0x29025  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::curChannel
0x2902a  stelem.ref
0x2902b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x29030  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x29035  ret
```
