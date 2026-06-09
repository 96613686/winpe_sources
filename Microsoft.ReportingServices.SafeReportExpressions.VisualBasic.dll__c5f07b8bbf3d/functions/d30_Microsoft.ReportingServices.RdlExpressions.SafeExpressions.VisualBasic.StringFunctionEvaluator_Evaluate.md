# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasic.StringFunctionEvaluator::Evaluate

- ea: `0xd30`
- end: `0x1313`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasic.StringFunctionEvaluator::Evaluate`
- size: `1507`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x8f0`
- `0xd30`
- `0x1440`

## pseudocode

```c

```

## disassembly

```asm
0xd30  ldarg.0
0xd31  ldarg.2
0xd32  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasic.ArithmeticEvaluator::ValidateStrongType(class [mscorlib]System.Collections.Generic.List`1<object> arguments)
0xd37  ldarg.1
0xd38  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0xd3d  stloc.1
0xd3e  ldloc.1
0xd3f  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0xd44  stloc.2
0xd45  ldloc.2
0xd46  ldc.i4   0x4D5FC294
0xd4b  bgt.un.s loc_DB9
0xd4d  ldloc.2
0xd4e  ldc.i4   0x103C2070
0xd53  bgt.un.s loc_D7B
0xd55  ldloc.2
0xd56  ldc.i4   0x82C7E87
0xd5b  beq      loc_EB3
0xd60  ldloc.2
0xd61  ldc.i4   0x845EB45
0xd66  beq      loc_F37
0xd6b  ldloc.2
0xd6c  ldc.i4   0x103C2070
0xd71  beq      loc_F0B
0xd76  br       loc_1300
0xd7b  ldloc.2
0xd7c  ldc.i4   0x34C13FF9
0xd81  bgt.un.s loc_D9E
0xd83  ldloc.2
0xd84  ldc.i4   0x1B97D785
0xd89  beq      loc_F21
0xd8e  ldloc.2
0xd8f  ldc.i4   0x34C13FF9
0xd94  beq      loc_EDF
0xd99  br       loc_1300
0xd9e  ldloc.2
0xd9f  ldc.i4   0x3C0A63FC
0xda4  beq      loc_E9D
0xda9  ldloc.2
0xdaa  ldc.i4   0x4D5FC294
0xdaf  beq      loc_E45
0xdb4  br       loc_1300
0xdb9  ldloc.2
0xdba  ldc.i4   0x74B902F9
0xdbf  bgt.un.s loc_DE4
0xdc1  ldloc.2
0xdc2  ldc.i4   0x63744EF3
0xdc7  beq      loc_EC9
0xdcc  ldloc.2
0xdcd  ldc.i4   0x64AD8A0A
0xdd2  beq.s    loc_E19
0xdd4  ldloc.2
0xdd5  ldc.i4   0x74B902F9
0xdda  beq      loc_E87
0xddf  br       loc_1300
0xde4  ldloc.2
0xde5  ldc.i4   0x90BF98F9
0xdea  bgt.un.s loc_E04
0xdec  ldloc.2
0xded  ldc.i4   0x77FD3309
0xdf2  beq      loc_EF5
0xdf7  ldloc.2
0xdf8  ldc.i4   0x90BF98F9
0xdfd  beq.s    loc_E5B
0xdff  br       loc_1300
0xe04  ldloc.2
0xe05  ldc.i4   0x9747C2D2
0xe0a  beq.s    loc_E71
0xe0c  ldloc.2
0xe0d  ldc.i4   0xDA30D067
0xe12  beq.s    loc_E2F
0xe14  br       loc_1300
0xe19  ldloc.1
0xe1a  ldstr    aAsc// "ASC"
0xe1f  ldc.i4.0
0xe20  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0xe25  brfalse  loc_F4D
0xe2a  br       loc_1300
0xe2f  ldloc.1
0xe30  ldstr    aAscw// "ASCW"
0xe35  ldc.i4.0
0xe36  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0xe3b  brfalse  loc_FA7
0xe40  br       loc_1300
0xe45  ldloc.1
0xe46  ldstr    aChr// "CHR"
0xe4b  ldc.i4.0
0xe4c  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0xe51  brfalse  loc_1001
0xe56  br       loc_1300
0xe5b  ldloc.1
0xe5c  ldstr    aChrw// "CHRW"
0xe61  ldc.i4.0
0xe62  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0xe67  brfalse  loc_101D
0xe6c  br       loc_1300
0xe71  ldloc.1
0xe72  ldstr    aFormat// "FORMAT"
0xe77  ldc.i4.0
0xe78  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0xe7d  brfalse  loc_1039
0xe82  br       loc_1300
0xe87  ldloc.1
0xe88  ldstr    aJoin// "JOIN"
0xe8d  ldc.i4.0
0xe8e  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0xe93  brfalse  loc_1081
0xe98  br       loc_1300
0xe9d  ldloc.1
0xe9e  ldstr    aUcase// "UCASE"
0xea3  ldc.i4.0
0xea4  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0xea9  brfalse  loc_116B
0xeae  br       loc_1300
0xeb3  ldloc.1
0xeb4  ldstr    aLcase// "LCASE"
0xeb9  ldc.i4.0
0xeba  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0xebf  brfalse  loc_11C7
0xec4  br       loc_1300
0xec9  ldloc.1
0xeca  ldstr    aLtrim// "LTRIM"
0xecf  ldc.i4.0
0xed0  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0xed5  brfalse  loc_1223
0xeda  br       loc_1300
0xedf  ldloc.1
0xee0  ldstr    aRtrim// "RTRIM"
0xee5  ldc.i4.0
0xee6  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0xeeb  brfalse  loc_123A
0xef0  br       loc_1300
0xef5  ldloc.1
0xef6  ldstr    aTrim// "TRIM"
0xefb  ldc.i4.0
0xefc  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0xf01  brfalse  loc_1251
0xf06  br       loc_1300
0xf0b  ldloc.1
0xf0c  ldstr    aLeft// "LEFT"
0xf11  ldc.i4.0
0xf12  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0xf17  brfalse  loc_1268
0xf1c  br       loc_1300
0xf21  ldloc.1
0xf22  ldstr    aRight// "RIGHT"
0xf27  ldc.i4.0
0xf28  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0xf2d  brfalse  loc_128B
0xf32  br       loc_1300
0xf37  ldloc.1
0xf38  ldstr    aMid// "MID"
0xf3d  ldc.i4.0
0xf3e  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0xf43  brfalse  loc_12AB
0xf48  br       loc_1300
0xf4d  ldnull
0xf4e  ldtoken  [Microsoft.VisualBasic]Microsoft.VisualBasic.Strings
0xf53  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf58  ldstr    aAsc_0// "Asc"
0xf5d  ldc.i4.1
0xf5e  newarr   [mscorlib]System.Object
0xf63  dup
0xf64  ldc.i4.0
0xf65  ldarg.2
0xf66  dup
0xf67  stloc.3
0xf68  ldc.i4.0
0xf69  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<object>::get_Item(!!T0)
0xf6e  stelem.ref
0xf6f  dup
0xf70  stloc.s  4
0xf72  ldnull
0xf73  ldnull
0xf74  ldc.i4.1
0xf75  newarr   [mscorlib]System.Boolean
0xf7a  dup
0xf7b  ldc.i4.0
0xf7c  ldc.i4.1
0xf7d  stelem.i1
0xf7e  dup
0xf7f  stloc.s  5
0xf81  call     object [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.NewLateBinding::LateGet(object, class [mscorlib]System.Type, string, object[], string[], class [mscorlib]System.Type[], bool[])
0xf86  ldloc.s  5
0xf88  ldc.i4.0
0xf89  ldelem.u1
0xf8a  brfalse.s loc_FA1
0xf8c  ldloc.3
0xf8d  ldc.i4.0
0xf8e  ldloc.s  4
0xf90  ldc.i4.0
0xf91  ldelem.ref
0xf92  call     object [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::GetObjectValue(object)
0xf97  call     object [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::GetObjectValue(object)
0xf9c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<object>::set_Item(int32, var<u1>)
0xfa1  stloc.0
0xfa2  br       loc_1311
0xfa7  ldnull
0xfa8  ldtoken  [Microsoft.VisualBasic]Microsoft.VisualBasic.Strings
0xfad  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xfb2  ldstr    aAscw_0// "AscW"
0xfb7  ldc.i4.1
0xfb8  newarr   [mscorlib]System.Object
0xfbd  dup
0xfbe  ldc.i4.0
0xfbf  ldarg.2
0xfc0  dup
0xfc1  stloc.3
0xfc2  ldc.i4.0
0xfc3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<object>::get_Item(!!T0)
0xfc8  stelem.ref
0xfc9  dup
0xfca  stloc.s  4
0xfcc  ldnull
0xfcd  ldnull
0xfce  ldc.i4.1
0xfcf  newarr   [mscorlib]System.Boolean
0xfd4  dup
0xfd5  ldc.i4.0
0xfd6  ldc.i4.1
0xfd7  stelem.i1
0xfd8  dup
0xfd9  stloc.s  5
0xfdb  call     object [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.NewLateBinding::LateGet(object, class [mscorlib]System.Type, string, object[], string[], class [mscorlib]System.Type[], bool[])
0xfe0  ldloc.s  5
0xfe2  ldc.i4.0
0xfe3  ldelem.u1
0xfe4  brfalse.s loc_FFB
0xfe6  ldloc.3
0xfe7  ldc.i4.0
0xfe8  ldloc.s  4
0xfea  ldc.i4.0
0xfeb  ldelem.ref
0xfec  call     object [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::GetObjectValue(object)
0xff1  call     object [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::GetObjectValue(object)
0xff6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<object>::set_Item(int32, var<u1>)
0xffb  stloc.0
0xffc  br       loc_1311
0x1001  ldarg.2
0x1002  ldc.i4.0
0x1003  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<object>::get_Item(!!T0)
0x1008  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Conversions::ToInteger(object)
0x100d  call     char [Microsoft.VisualBasic]Microsoft.VisualBasic.Strings::Chr(int32)
0x1012  box      [mscorlib]System.Char
0x1017  stloc.0
0x1018  br       loc_1311
0x101d  ldarg.2
0x101e  ldc.i4.0
0x101f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<object>::get_Item(!!T0)
0x1024  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Conversions::ToInteger(object)
0x1029  call     char [Microsoft.VisualBasic]Microsoft.VisualBasic.Strings::ChrW(int32)
0x102e  box      [mscorlib]System.Char
0x1033  stloc.0
0x1034  br       loc_1311
0x1039  ldarg.2
0x103a  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<object>::get_Count()
0x103f  ldc.i4.1
0x1040  bne.un.s loc_105E
0x1042  ldarg.2
0x1043  ldc.i4.0
0x1044  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<object>::get_Item(!!T0)
0x1049  call     object [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::GetObjectValue(object)
0x104e  ldstr    asc_2504// ""
0x1053  call     string [Microsoft.VisualBasic]Microsoft.VisualBasic.Strings::Format(object, string)
0x1058  stloc.0
0x1059  br       loc_1311
0x105e  ldarg.2
0x105f  ldc.i4.0
0x1060  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<object>::get_Item(!!T0)
0x1065  call     object [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::GetObjectValue(object)
0x106a  ldarg.2
0x106b  ldc.i4.1
0x106c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<object>::get_Item(!!T0)
0x1071  call     string [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Conversions::ToString(object)
0x1076  call     string [Microsoft.VisualBasic]Microsoft.VisualBasic.Strings::Format(object, string)
0x107b  stloc.0
0x107c  br       loc_1311
0x1081  ldarg.2
0x1082  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<object>::get_Count()
0x1087  ldc.i4.1
0x1088  bne.un.s loc_10E4
0x108a  ldnull
0x108b  ldtoken  [Microsoft.VisualBasic]Microsoft.VisualBasic.Strings
0x1090  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1095  ldstr    aJoin_0// "Join"
0x109a  ldc.i4.1
0x109b  newarr   [mscorlib]System.Object
0x10a0  dup
0x10a1  ldc.i4.0
0x10a2  ldarg.2
0x10a3  dup
0x10a4  stloc.3
0x10a5  ldc.i4.0
0x10a6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<object>::get_Item(!!T0)
0x10ab  stelem.ref
0x10ac  dup
0x10ad  stloc.s  4
0x10af  ldnull
0x10b0  ldnull
0x10b1  ldc.i4.1
  ... truncated ...
```
