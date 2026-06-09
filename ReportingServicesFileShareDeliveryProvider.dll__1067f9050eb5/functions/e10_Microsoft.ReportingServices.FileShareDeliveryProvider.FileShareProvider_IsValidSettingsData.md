# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::IsValidSettingsData

- ea: `0xe10`
- end: `0x1265`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::IsValidSettingsData`
- size: `1109`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x460`
- `0xe10`
- `0x18e0`
- `0x34f0`
- `0x3c50`
- `0x3c60`
- `0x3c70`
- `0x3c80`
- `0x3c90`
- `0x3ca0`
- `0x3cb0`
- `0x3cd0`
- `0x3cf0`
- `0x3d50`
- `0x3e10`
- `0x3e20`
- `0x3e30`
- `0x3e40`
- `0x3e60`

## string_xrefs

- `0xfba`: `WRITEMODE`

## pseudocode

```c

```

## disassembly

```asm
0xe10  ldc.i4.1
0xe11  stloc.0
0xe12  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0xe17  stloc.1
0xe18  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xe1d  stloc.2
0xe1e  ldsfld   string [mscorlib]System.String::Empty
0xe23  stloc.3
0xe24  ldarg.1
0xe25  stloc.s  4
0xe27  ldc.i4.0
0xe28  stloc.s  5
0xe2a  br       loc_11D4
0xe2f  ldloc.s  4
0xe31  ldloc.s  5
0xe33  ldelem.ref
0xe34  stloc.s  6
0xe36  ldloc.s  6
0xe38  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Field()
0xe3d  brfalse.s loc_E55
0xe3f  ldloc.s  6
0xe41  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Field()
0xe46  ldsfld   string [mscorlib]System.String::Empty
0xe4b  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe50  brfalse  loc_1158
0xe55  nop
0xe56  ldloc.s  6
0xe58  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Value()
0xe5d  brtrue.s loc_E77
0xe5f  ldloc.s  6
0xe61  ldloc.s  6
0xe63  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Name()
0xe68  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::NullSetting(string setting)
0xe6d  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Error(string)
0xe72  br       loc_1119
0xe77  ldloc.s  6
0xe79  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Name()
0xe7e  brtrue.s loc_EA4
0xe80  ldloc.s  6
0xe82  ldsfld   string [mscorlib]System.String::Empty
0xe87  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Name(string)
0xe8c  ldloc.s  6
0xe8e  ldloc.s  6
0xe90  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Name()
0xe95  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::UnKnownSetting(string setting)
0xe9a  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Error(string)
0xe9f  br       loc_1119
0xea4  ldloc.s  6
0xea6  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Name()
0xeab  stloc.s  7
0xead  ldloc.s  7
0xeaf  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0xeb4  stloc.s  8
0xeb6  ldloc.s  8
0xeb8  ldc.i4   0x6DA38F76
0xebd  bgt.un.s loc_EFC
0xebf  ldloc.s  8
0xec1  ldc.i4   0x38DF525F
0xec6  bgt.un.s loc_EE2
0xec8  ldloc.s  8
0xeca  ldc.i4   0x21102718
0xecf  beq.s    loc_F4A
0xed1  ldloc.s  8
0xed3  ldc.i4   0x38DF525F
0xed8  beq      loc_FB8
0xedd  br       loc_1106
0xee2  ldloc.s  8
0xee4  ldc.i4   0x3EB270B8
0xee9  beq      loc_FCE
0xeee  ldloc.s  8
0xef0  ldc.i4   0x6DA38F76
0xef5  beq.s    loc_F76
0xef7  br       loc_1106
0xefc  ldloc.s  8
0xefe  ldc.i4   0xAB95F408
0xf03  bgt.un.s loc_F1F
0xf05  ldloc.s  8
0xf07  ldc.i4   0x71098DA5
0xf0c  beq      loc_FA2
0xf11  ldloc.s  8
0xf13  ldc.i4   0xAB95F408
0xf18  beq.s    loc_F60
0xf1a  br       loc_1106
0xf1f  ldloc.s  8
0xf21  ldc.i4   0xD2BF7DD0
0xf26  beq.s    loc_F8C
0xf28  ldloc.s  8
0xf2a  ldc.i4   0xD4C5EDB9
0xf2f  bne.un   loc_1106
0xf34  ldloc.s  7
0xf36  ldstr    aUsername// "USERNAME"
0xf3b  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf40  brtrue   loc_FE4
0xf45  br       loc_1106
0xf4a  ldloc.s  7
0xf4c  ldstr    aPassword// "PASSWORD"
0xf51  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf56  brtrue   loc_1000
0xf5b  br       loc_1106
0xf60  ldloc.s  7
0xf62  ldstr    aFilename// "FILENAME"
0xf67  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf6c  brtrue   loc_101C
0xf71  br       loc_1106
0xf76  ldloc.s  7
0xf78  ldstr    aPath// "PATH"
0xf7d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf82  brtrue   loc_105D
0xf87  br       loc_1106
0xf8c  ldloc.s  7
0xf8e  ldstr    aFileextn// "FILEEXTN"
0xf93  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf98  brtrue   loc_109B
0xf9d  br       loc_1106
0xfa2  ldloc.s  7
0xfa4  ldstr    aRenderFormat// "RENDER_FORMAT"
0xfa9  call     bool [mscorlib]System.String::op_Equality(string, string)
0xfae  brtrue   loc_10BA
0xfb3  br       loc_1106
0xfb8  ldloc.s  7
0xfba  ldstr    aWritemode// "WRITEMODE"
0xfbf  call     bool [mscorlib]System.String::op_Equality(string, string)
0xfc4  brtrue   loc_1119
0xfc9  br       loc_1106
0xfce  ldloc.s  7
0xfd0  ldstr    aDefaultcredent// "DEFAULTCREDENTIALS"
0xfd5  call     bool [mscorlib]System.String::op_Equality(string, string)
0xfda  brtrue   loc_10D6
0xfdf  br       loc_1106
0xfe4  ldloc.s  6
0xfe6  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Value()
0xfeb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xff0  brfalse  loc_1119
0xff5  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_NoUserName()
0xffa  stloc.3
0xffb  br       loc_1119
0x1000  ldloc.s  6
0x1002  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Value()
0x1007  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x100c  brfalse  loc_1119
0x1011  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_NoPassword()
0x1016  stloc.3
0x1017  br       loc_1119
0x101c  ldloc.s  6
0x101e  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Value()
0x1023  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1028  brtrue.s loc_103B
0x102a  ldloc.s  6
0x102c  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_NoFileName()
0x1031  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Error(string)
0x1036  br       loc_1119
0x103b  ldloc.s  6
0x103d  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Value()
0x1042  call     bool Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ValidateFileName(string FileName)
0x1047  brtrue   loc_1119
0x104c  ldloc.s  6
0x104e  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_InvalidFileName()
0x1053  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Error(string)
0x1058  br       loc_1119
0x105d  ldloc.s  6
0x105f  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Value()
0x1064  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1069  brtrue.s loc_107C
0x106b  ldloc.s  6
0x106d  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_NoPath()
0x1072  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Error(string)
0x1077  br       loc_1119
0x107c  ldloc.s  6
0x107e  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Value()
0x1083  call     bool Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::IsValidPath(string pathname)
0x1088  brtrue   loc_1119
0x108d  ldloc.s  6
0x108f  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_UNCPathNotValid()
0x1094  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Error(string)
0x1099  br.s     loc_1119
0x109b  nop
0x109c  ldloc.s  6
0x109e  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Value()
0x10a3  call     bool [mscorlib]System.Boolean::Parse(string)
0x10a8  pop
0x10a9  leave.s  loc_1119
0x10ab  pop
0x10ac  ldloc.s  6
0x10ae  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_InvalidFileExt()
0x10b3  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Error(string)
0x10b8  leave.s  loc_1119
0x10ba  ldloc.s  6
0x10bc  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Value()
0x10c1  callvirt instance int32 [mscorlib]System.String::get_Length()
0x10c6  brtrue.s loc_1119
0x10c8  ldloc.s  6
0x10ca  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_MissingRenderFormat()
0x10cf  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Error(string)
0x10d4  br.s     loc_1119
0x10d6  nop
0x10d7  ldloc.s  6
0x10d9  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Value()
0x10de  call     bool [mscorlib]System.Boolean::Parse(string)
0x10e3  brtrue.s loc_10F5
0x10e5  ldloc.3
0x10e6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10eb  brtrue.s loc_10F5
0x10ed  ldloc.s  6
0x10ef  ldloc.3
0x10f0  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Error(string)
0x10f5  leave.s  loc_1119
0x10f7  pop
0x10f8  ldloc.s  6
0x10fa  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_InvalidCredentialsSource()
0x10ff  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Error(string)
0x1104  leave.s  loc_1119
0x1106  ldloc.s  6
0x1108  ldloc.s  6
0x110a  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Name()
0x110f  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::UnKnownSetting(string setting)
0x1114  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Error(string)
0x1119  leave.s  loc_1158
0x111b  stloc.s  9
0x111d  ldloc.s  6
0x111f  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_InvalidAttributeValue()
0x1124  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Error(string)
0x1129  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_tracer
0x112e  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x1133  brfalse.s loc_1156
0x1135  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_tracer
0x113a  ldc.i4.1
0x113b  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::get_InvalidAttributeValue()
0x1140  ldstr    asc_52DC// ", "
0x1145  ldloc.s  9
0x1147  callvirt instance string [mscorlib]System.Object::ToString()
0x114c  call     string [mscorlib]System.String::Concat(string, string, string)
0x1151  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x1156  leave.s  loc_1158
0x1158  ldloc.1
0x1159  ldloc.s  6
0x115b  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Name()
0x1160  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x1165  brfalse.s loc_1198
0x1167  ldloc.s  6
0x1169  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Error()
0x116e  brfalse.s loc_1183
0x1170  ldloc.s  6
0x1172  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Error()
0x1177  ldsfld   string [mscorlib]System.String::Empty
0x117c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1181  brfalse.s loc_11AC
0x1183  ldloc.s  6
0x1185  ldloc.s  6
0x1187  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Name()
0x118c  call     string Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareError::DuplicateSetting(string setting)
0x1191  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Error(string)
0x1196  br.s     loc_11AC
0x1198  ldloc.1
0x1199  ldloc.s  6
0x119b  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Name()
0x11a0  ldloc.s  6
0x11a2  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Name()
0x11a7  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x11ac  ldloc.s  6
0x11ae  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Error()
0x11b3  brfalse.s loc_11C5
0x11b5  ldloc.s  6
0x11b7  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Error()
0x11bc  callvirt instance int32 [mscorlib]System.String::get_Length()
0x11c1  brfalse.s loc_11C5
0x11c3  ldc.i4.0
0x11c4  stloc.0
0x11c5  ldloc.2
0x11c6  ldloc.s  6
0x11c8  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x11cd  pop
0x11ce  ldloc.s  5
0x11d0  ldc.i4.1
0x11d1  add
0x11d2  stloc.s  5
0x11d4  ldloc.s  5
0x11d6  ldloc.s  4
0x11d8  ldlen
0x11d9  conv.i4
0x11da  blt      loc_E2F
0x11df  ldarg.0
0x11e0  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::get_ExtensionSettings()
0x11e5  stloc.s  4
0x11e7  ldc.i4.0
0x11e8  stloc.s  5
0x11ea  br.s     loc_1244
0x11ec  ldloc.s  4
0x11ee  ldloc.s  5
0x11f0  ldelem.ref
0x11f1  stloc.s  0xA
0x11f3  ldloc.s  0xA
0x11f5  callvirt instance bool [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Required()
0x11fa  brfalse.s loc_123E
0x11fc  ldloc.1
0x11fd  ldloc.s  0xA
0x11ff  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Name()
0x1204  callvirt instance bool [mscorlib]System.Collections.Hashtable::Contains(object)
0x1209  brtrue.s loc_123E
0x120b  newobj   instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::.ctor()
0x1210  stloc.s  0xB
  ... truncated ...
```
