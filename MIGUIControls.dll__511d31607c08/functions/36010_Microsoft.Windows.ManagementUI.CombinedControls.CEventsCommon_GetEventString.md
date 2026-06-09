# Microsoft.Windows.ManagementUI.CombinedControls.CEventsCommon::GetEventString

- ea: `0x36010`
- end: `0x36263`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.CEventsCommon::GetEventString`
- size: `595`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x22df0`
- `0x2c680`

## callees

- `0x12ed0`
- `0x13430`
- `0x33150`
- `0x33c10`
- `0x344c0`
- `0x36010`
- `0x3a9d0`
- `0x3a9e0`
- `0x3a9f0`
- `0x3aa00`
- `0x3aa20`
- `0x3aa40`
- `0x3aa50`
- `0x3aa60`
- `0x3ab00`
- `0x3ab10`

## string_xrefs

- `0x360f3`: `ClipTaskProp`
- `0x361b6`: `ClipComputerProp`
- `0x36217`: `ClipXmlProp`
- `0x36243`: `Invalid Xml`

## pseudocode

```c

```

## disassembly

```asm
0x36010  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x36015  stloc.0
0x36016  ldc.i4.s 0xF
0x36018  stloc.1
0x36019  ldarg.0
0x3601a  brfalse  loc_3625C
0x3601f  ldloc.0
0x36020  ldstr    aCliplognamepro// "ClipLogNameProp"
0x36025  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3602a  ldloc.1
0x3602b  callvirt instance string [mscorlib]System.String::PadRight(int32)
0x36030  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x36035  pop
0x36036  ldloc.0
0x36037  ldarg.0
0x36038  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.IEventBase::get_Channel()
0x3603d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x36042  pop
0x36043  ldloc.0
0x36044  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x36049  pop
0x3604a  ldloc.0
0x3604b  ldstr    aClipsourceprop// "ClipSourceProp"
0x36050  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x36055  ldloc.1
0x36056  callvirt instance string [mscorlib]System.String::PadRight(int32)
0x3605b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x36060  pop
0x36061  ldloc.0
0x36062  ldarg.0
0x36063  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.IEventBase::get_Source()
0x36068  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3606d  pop
0x3606e  ldloc.0
0x3606f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x36074  pop
0x36075  ldloc.0
0x36076  ldstr    aClipdateprop// "ClipDateProp"
0x3607b  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x36080  ldloc.1
0x36081  callvirt instance string [mscorlib]System.String::PadRight(int32)
0x36086  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3608b  pop
0x3608c  ldloc.0
0x3608d  ldarg.0
0x3608e  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Windows.ManagementUI.CombinedControls.IEventBase::get_TimeGenerated()
0x36093  call     string Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::GetDateTimeString(valuetype [mscorlib]System.DateTime dt)
0x36098  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3609d  pop
0x3609e  ldloc.0
0x3609f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x360a4  pop
0x360a5  ldloc.0
0x360a6  ldstr    aClipeventidpro// "ClipEventidProp"
0x360ab  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x360b0  ldloc.1
0x360b1  callvirt instance string [mscorlib]System.String::PadRight(int32)
0x360b6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x360bb  pop
0x360bc  ldloc.0
0x360bd  ldarg.0
0x360be  callvirt instance unsigned int16 Microsoft.Windows.ManagementUI.CombinedControls.IEventBase::get_EventId()
0x360c3  stloc.s  4
0x360c5  ldloca.s 4
0x360c7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x360cc  ldtoken  [mscorlib]System.UInt16
0x360d1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x360d6  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x360db  castclass [mscorlib]System.IFormatProvider
0x360e0  call     instance string [mscorlib]System.UInt16::ToString(class [mscorlib]System.IFormatProvider)
0x360e5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x360ea  pop
0x360eb  ldloc.0
0x360ec  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x360f1  pop
0x360f2  ldloc.0
0x360f3  ldstr    aCliptaskprop// "ClipTaskProp"
0x360f8  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x360fd  ldloc.1
0x360fe  callvirt instance string [mscorlib]System.String::PadRight(int32)
0x36103  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x36108  pop
0x36109  ldloc.0
0x3610a  ldarg.0
0x3610b  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.IEventBase::get_Category()
0x36110  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x36115  pop
0x36116  ldloc.0
0x36117  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x3611c  pop
0x3611d  ldloc.0
0x3611e  ldstr    aCliplevelprop// "ClipLevelProp"
0x36123  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x36128  ldloc.1
0x36129  callvirt instance string [mscorlib]System.String::PadRight(int32)
0x3612e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x36133  pop
0x36134  ldloc.0
0x36135  ldarg.0
0x36136  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.IEventBase::get_Level()
0x3613b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x36140  pop
0x36141  ldloc.0
0x36142  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x36147  pop
0x36148  ldloc.0
0x36149  ldstr    aClipkeywordpro// "ClipKeywordProp"
0x3614e  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x36153  ldloc.1
0x36154  callvirt instance string [mscorlib]System.String::PadRight(int32)
0x36159  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3615e  pop
0x3615f  ldloc.0
0x36160  ldarg.0
0x36161  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.IEventBase::get_Keywords()
0x36166  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3616b  pop
0x3616c  ldloc.0
0x3616d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x36172  pop
0x36173  ldloc.0
0x36174  ldstr    aClipuserprop// "ClipUserProp"
0x36179  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3617e  ldloc.1
0x3617f  callvirt instance string [mscorlib]System.String::PadRight(int32)
0x36184  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x36189  pop
0x3618a  ldarg.1
0x3618b  ldarg.0
0x3618c  call     string Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::GetUserId(string computerName, class Microsoft.Windows.ManagementUI.CombinedControls.IEventBase evt)
0x36191  stloc.2
0x36192  ldloc.0
0x36193  ldloc.2
0x36194  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x36199  brtrue.s loc_3619E
0x3619b  ldloc.2
0x3619c  br.s     loc_361A8
0x3619e  ldstr    aEmptyuser// "EMPTYUSER"
0x361a3  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x361a8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x361ad  pop
0x361ae  ldloc.0
0x361af  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x361b4  pop
0x361b5  ldloc.0
0x361b6  ldstr    aClipcomputerpr// "ClipComputerProp"
0x361bb  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x361c0  ldloc.1
0x361c1  callvirt instance string [mscorlib]System.String::PadRight(int32)
0x361c6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x361cb  pop
0x361cc  ldloc.0
0x361cd  ldarg.0
0x361ce  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.IEventBase::get_Computer()
0x361d3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x361d8  pop
0x361d9  ldarg.0
0x361da  isinst   Microsoft.Windows.ManagementUI.CombinedControls.ISystemEvent
0x361df  stloc.3
0x361e0  ldloc.3
0x361e1  brfalse.s loc_3625C
0x361e3  ldloc.0
0x361e4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x361e9  pop
0x361ea  ldloc.0
0x361eb  ldstr    aClipmessagepro// "ClipMessageProp"
0x361f0  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x361f5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x361fa  pop
0x361fb  ldloc.0
0x361fc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x36201  pop
0x36202  ldloc.0
0x36203  ldloc.3
0x36204  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ISystemEvent::get_Message()
0x36209  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3620e  pop
0x3620f  ldloc.0
0x36210  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x36215  pop
0x36216  ldloc.0
0x36217  ldstr    aClipxmlprop// "ClipXmlProp"
0x3621c  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x36221  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x36226  pop
0x36227  ldloc.0
0x36228  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x3622d  pop
0x3622e  ldloc.0
0x3622f  ldloc.3
0x36230  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ISystemEvent::get_RawEvent()
0x36235  call     string Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::ParseAndIndentXML(string sXml)
0x3623a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3623f  pop
0x36240  leave.s  loc_3625C
0x36242  pop
0x36243  ldstr    aInvalidXml// "Invalid Xml"
0x36248  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x3624d  ldloc.0
0x3624e  ldloc.3
0x3624f  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ISystemEvent::get_RawEvent()
0x36254  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x36259  pop
0x3625a  leave.s  loc_3625C
0x3625c  ldloc.0
0x3625d  callvirt instance string [mscorlib]System.Object::ToString()
0x36262  ret
```
