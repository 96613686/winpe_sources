# Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::WriteToStore

- ea: `0x5060`
- end: `0x5391`
- name: `Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::WriteToStore`
- size: `817`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x80`
- `0x290`
- `0x4a50`
- `0x4a70`
- `0x4ad0`
- `0x4af0`
- `0x4b00`
- `0x4b10`
- `0x5000`
- `0x5060`
- `0x53c0`
- `0x53e0`
- `0x5760`
- `0x5770`

## string_xrefs

- `0x512d`: `Extension`
- `0x5165`: `Extension`
- `0x519a`: `Extension`
- `0x52c4`: `{0:B}\Extensions\Namespace`
- `0x531d`: `{0:B}\Extensions\PropertySheet`

## pseudocode

```c

```

## disassembly

```asm
0x5060  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x5065  ldstr    aSoftwareMicros// "SOFTWARE\\Microsoft\\MMC\\SnapIns\\"
0x506a  ldc.i4.1
0x506b  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0x5070  stloc.0
0x5071  ldloc.0
0x5072  ldarg.0
0x5073  call     instance string Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::get_Id()
0x5078  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::CreateSubKey(string)
0x507d  stloc.1
0x507e  ldarg.0
0x507f  ldfld    valuetype DWordProperty[] Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::_dWordProperties
0x5084  stloc.s  0xE
0x5086  ldc.i4.0
0x5087  stloc.s  0xF
0x5089  br.s     loc_50BD
0x508b  ldloc.s  0xE
0x508d  ldloc.s  0xF
0x508f  ldelema  DWordProperty
0x5094  ldobj    DWordProperty
0x5099  stloc.2
0x509a  ldloca.s 2
0x509c  call     instance bool DWordProperty::IsSet()
0x50a1  brfalse.s loc_50B7
0x50a3  ldloc.1
0x50a4  ldloca.s 2
0x50a6  ldfld    string DWordProperty::Name
0x50ab  ldloca.s 2
0x50ad  call     instance int32 DWordProperty::GetValue()
0x50b2  call     void Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::SetRegistryDWordValue(class [mscorlib]Microsoft.Win32.RegistryKey key, string name, int32 value)
0x50b7  ldloc.s  0xF
0x50b9  ldc.i4.1
0x50ba  add
0x50bb  stloc.s  0xF
0x50bd  ldloc.s  0xF
0x50bf  ldloc.s  0xE
0x50c1  ldlen
0x50c2  conv.i4
0x50c3  blt.s    loc_508B
0x50c5  ldarg.0
0x50c6  ldfld    valuetype StringProperty[] Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::_stringProperties
0x50cb  stloc.s  0x10
0x50cd  ldc.i4.0
0x50ce  stloc.s  0x11
0x50d0  br.s     loc_5102
0x50d2  ldloc.s  0x10
0x50d4  ldloc.s  0x11
0x50d6  ldelema  StringProperty
0x50db  ldobj    StringProperty
0x50e0  stloc.3
0x50e1  ldloc.1
0x50e2  ldloca.s 3
0x50e4  ldfld    string StringProperty::Name
0x50e9  ldloca.s 3
0x50eb  ldfld    string StringProperty::Value
0x50f0  ldloca.s 3
0x50f2  ldfld    bool StringProperty::Optional
0x50f7  call     void Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::SetRegistryStringValue(class [mscorlib]Microsoft.Win32.RegistryKey key, string name, string value, bool optional)
0x50fc  ldloc.s  0x11
0x50fe  ldc.i4.1
0x50ff  add
0x5100  stloc.s  0x11
0x5102  ldloc.s  0x11
0x5104  ldloc.s  0x10
0x5106  ldlen
0x5107  conv.i4
0x5108  blt.s    loc_50D2
0x510a  ldarg.0
0x510b  call     instance valuetype Microsoft.ManagementConsole.Internal.SnapInType Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::get_SnapInType()
0x5110  brtrue.s loc_5123
0x5112  ldloc.1
0x5113  ldstr    aStandalone// "Standalone"
0x5118  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::CreateSubKey(string)
0x511d  pop
0x511e  br       loc_51D5
0x5123  ldarg.0
0x5124  call     instance valuetype Microsoft.ManagementConsole.Internal.SnapInType Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::get_SnapInType()
0x5129  ldc.i4.1
0x512a  bne.un.s loc_515B
0x512c  ldloc.1
0x512d  ldstr    aExtension// "Extension"
0x5132  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::CreateSubKey(string)
0x5137  stloc.s  4
0x5139  ldloc.s  4
0x513b  ldsfld   string [mscorlib]System.String::Empty
0x5140  ldstr    aNamespace// "Namespace"
0x5145  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x514a  leave    loc_51D5
0x514f  ldloc.s  4
0x5151  brfalse.s loc_515A
0x5153  ldloc.s  4
0x5155  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x515a  endfinally
0x515b  ldarg.0
0x515c  call     instance valuetype Microsoft.ManagementConsole.Internal.SnapInType Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::get_SnapInType()
0x5161  ldc.i4.2
0x5162  bne.un.s loc_5190
0x5164  ldloc.1
0x5165  ldstr    aExtension// "Extension"
0x516a  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::CreateSubKey(string)
0x516f  stloc.s  5
0x5171  ldloc.s  5
0x5173  ldsfld   string [mscorlib]System.String::Empty
0x5178  ldstr    aActionspane// "ActionsPane"
0x517d  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x5182  leave.s  loc_51D5
0x5184  ldloc.s  5
0x5186  brfalse.s loc_518F
0x5188  ldloc.s  5
0x518a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x518f  endfinally
0x5190  ldarg.0
0x5191  call     instance valuetype Microsoft.ManagementConsole.Internal.SnapInType Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::get_SnapInType()
0x5196  ldc.i4.3
0x5197  bne.un.s loc_51C5
0x5199  ldloc.1
0x519a  ldstr    aExtension// "Extension"
0x519f  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::CreateSubKey(string)
0x51a4  stloc.s  6
0x51a6  ldloc.s  6
0x51a8  ldsfld   string [mscorlib]System.String::Empty
0x51ad  ldstr    aPropertysheet// "PropertySheet"
0x51b2  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x51b7  leave.s  loc_51D5
0x51b9  ldloc.s  6
0x51bb  brfalse.s loc_51C4
0x51bd  ldloc.s  6
0x51bf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x51c4  endfinally
0x51c5  call     string Microsoft.ManagementConsole.Internal.Strings::get_SnapInRegistrationInfoUnknownSnapInType()
0x51ca  call     string Microsoft.ManagementConsole.Internal.Utility::LoadResourceString(string resourceName)
0x51cf  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x51d4  throw
0x51d5  ldloc.1
0x51d6  ldstr    aNodetypes// "NodeTypes"
0x51db  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::CreateSubKey(string)
0x51e0  stloc.s  7
0x51e2  ldarg.0
0x51e3  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ManagementConsole.Internal.NodeType> Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::get_NodeTypes()
0x51e8  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ManagementConsole.Internal.NodeType>::GetEnumerator()
0x51ed  stloc.s  0x12
0x51ef  br.s     loc_5237
0x51f1  ldloca.s 0x12
0x51f3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ManagementConsole.Internal.NodeType>::get_Current()
0x51f8  stloc.s  8
0x51fa  ldloc.s  7
0x51fc  ldloc.s  8
0x51fe  callvirt instance valuetype [mscorlib]System.Guid Microsoft.ManagementConsole.Internal.NodeType::get_Guid()
0x5203  stloc.s  0x13
0x5205  ldloca.s 0x13
0x5207  ldstr    aB// "B"
0x520c  ldnull
0x520d  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x5212  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::CreateSubKey(string)
0x5217  stloc.s  9
0x5219  ldloc.s  9
0x521b  ldnull
0x521c  ldloc.s  8
0x521e  callvirt instance string Microsoft.ManagementConsole.Internal.NodeType::get_Description()
0x5223  ldc.i4.1
0x5224  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object, valuetype [mscorlib]Microsoft.Win32.RegistryValueKind)
0x5229  leave.s  loc_5237
0x522b  ldloc.s  9
0x522d  brfalse.s loc_5236
0x522f  ldloc.s  9
0x5231  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5236  endfinally
0x5237  ldloca.s 0x12
0x5239  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ManagementConsole.Internal.NodeType>::MoveNext()
0x523e  brtrue.s loc_51F1
0x5240  leave.s  loc_5250
0x5242  ldloca.s 0x12
0x5244  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ManagementConsole.Internal.NodeType>
0x524a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x524f  endfinally
0x5250  leave.s  loc_525E
0x5252  ldloc.s  7
0x5254  brfalse.s loc_525D
0x5256  ldloc.s  7
0x5258  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x525d  endfinally
0x525e  leave.s  loc_526A
0x5260  ldloc.1
0x5261  brfalse.s loc_5269
0x5263  ldloc.1
0x5264  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5269  endfinally
0x526a  leave.s  loc_5276
0x526c  ldloc.0
0x526d  brfalse.s loc_5275
0x526f  ldloc.0
0x5270  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5275  endfinally
0x5276  ldarg.0
0x5277  call     instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::get_ExtendedNodeTypes()
0x527c  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x5281  ldc.i4.0
0x5282  ble      loc_5390
0x5287  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x528c  ldstr    aSoftwareMicros_0// "SOFTWARE\\Microsoft\\MMC\\NodeTypes\\"
0x5291  ldc.i4.1
0x5292  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0x5297  stloc.s  0xA
0x5299  ldarg.0
0x529a  call     instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::get_ExtendedNodeTypes()
0x529f  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x52a4  stloc.s  0x14
0x52a6  br       loc_5366
0x52ab  ldloca.s 0x14
0x52ad  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::get_Current()
0x52b2  stloc.s  0xB
0x52b4  ldarg.0
0x52b5  call     instance valuetype Microsoft.ManagementConsole.Internal.SnapInType Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::get_SnapInType()
0x52ba  ldc.i4.1
0x52bb  bne.un.s loc_530D
0x52bd  ldloc.s  0xA
0x52bf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x52c4  ldstr    a0BExtensionsNa// "{0:B}\\Extensions\\Namespace"
0x52c9  ldc.i4.1
0x52ca  newarr   [mscorlib]System.Object
0x52cf  stloc.s  0x15
0x52d1  ldloc.s  0x15
0x52d3  ldc.i4.0
0x52d4  ldloc.s  0xB
0x52d6  box      [mscorlib]System.Guid
0x52db  stelem.ref
0x52dc  ldloc.s  0x15
0x52de  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x52e3  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::CreateSubKey(string)
0x52e8  stloc.s  0xC
0x52ea  ldloc.s  0xC
0x52ec  ldarg.0
0x52ed  call     instance string Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::get_Id()
0x52f2  ldarg.0
0x52f3  ldc.i4.s 0xA
0x52f5  call     instance string Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::GetStringProperty(valuetype StringValueKey key)
0x52fa  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x52ff  leave.s  loc_5366
0x5301  ldloc.s  0xC
0x5303  brfalse.s loc_530C
0x5305  ldloc.s  0xC
0x5307  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x530c  endfinally
0x530d  ldarg.0
0x530e  call     instance valuetype Microsoft.ManagementConsole.Internal.SnapInType Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::get_SnapInType()
0x5313  ldc.i4.3
0x5314  bne.un.s loc_5366
0x5316  ldloc.s  0xA
0x5318  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x531d  ldstr    a0BExtensionsPr// "{0:B}\\Extensions\\PropertySheet"
0x5322  ldc.i4.1
0x5323  newarr   [mscorlib]System.Object
0x5328  stloc.s  0x16
0x532a  ldloc.s  0x16
0x532c  ldc.i4.0
0x532d  ldloc.s  0xB
0x532f  box      [mscorlib]System.Guid
0x5334  stelem.ref
0x5335  ldloc.s  0x16
0x5337  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x533c  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::CreateSubKey(string)
0x5341  stloc.s  0xD
0x5343  ldloc.s  0xD
0x5345  ldarg.0
0x5346  call     instance string Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::get_Id()
0x534b  ldarg.0
0x534c  ldc.i4.s 0xA
0x534e  call     instance string Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::GetStringProperty(valuetype StringValueKey key)
0x5353  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x5358  leave.s  loc_5366
0x535a  ldloc.s  0xD
0x535c  brfalse.s loc_5365
0x535e  ldloc.s  0xD
0x5360  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5365  endfinally
0x5366  ldloca.s 0x14
0x5368  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::MoveNext()
0x536d  brtrue   loc_52AB
0x5372  leave.s  loc_5382
0x5374  ldloca.s 0x14
0x5376  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>
0x537c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5381  endfinally
0x5382  leave.s  loc_5390
0x5384  ldloc.s  0xA
0x5386  brfalse.s loc_538F
0x5388  ldloc.s  0xA
0x538a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x538f  endfinally
0x5390  ret
```
