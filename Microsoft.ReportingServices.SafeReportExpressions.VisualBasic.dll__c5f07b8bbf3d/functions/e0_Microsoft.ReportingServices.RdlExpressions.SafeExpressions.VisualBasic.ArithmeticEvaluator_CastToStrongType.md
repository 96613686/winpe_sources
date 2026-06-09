# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasic.ArithmeticEvaluator::CastToStrongType

- ea: `0xe0`
- end: `0x8e8`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasic.ArithmeticEvaluator::CastToStrongType`
- size: `2056`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xe0`
- `0x8f0`
- `0x950`
- `0x1340`

## callees

- `0xe0`
- `0x1440`

## pseudocode

```c

```

## disassembly

```asm
0xe0  ldarg.1
0xe1  call     object [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::GetObjectValue(object)
0xe6  call     bool [Microsoft.VisualBasic]Microsoft.VisualBasic.Information::IsNothing(object)
0xeb  brfalse.s loc_F4
0xed  ldnull
0xee  stloc.0
0xef  br       loc_8E6
0xf4  ldarg.1
0xf5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xfa  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xff  stloc.1
0x100  ldloc.1
0x101  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x106  stloc.2
0x107  ldloc.2
0x108  ldc.i4   0x9018E81C
0x10d  bgt.un   loc_23B
0x112  ldloc.2
0x113  ldc.i4   0x2D9FADF1
0x118  bgt.un   loc_1AC
0x11d  ldloc.2
0x11e  ldc.i4   0x1BE5F611
0x123  bgt.un.s loc_163
0x125  ldloc.2
0x126  ldc.i4   0x19402A08
0x12b  bgt.un.s loc_148
0x12d  ldloc.2
0x12e  ldc.i4   0xE3007C3
0x133  beq      loc_377
0x138  ldloc.2
0x139  ldc.i4   0x19402A08
0x13e  beq      loc_5F5
0x143  br       loc_8D5
0x148  ldloc.2
0x149  ldc.i4   0x1A4DAF5F
0x14e  beq      loc_587
0x153  ldloc.2
0x154  ldc.i4   0x1BE5F611
0x159  beq      loc_5B3
0x15e  br       loc_8D5
0x163  ldloc.2
0x164  ldc.i4   0x2879E23D
0x169  bgt.un.s loc_186
0x16b  ldloc.2
0x16c  ldc.i4   0x2676D448
0x171  beq      loc_637
0x176  ldloc.2
0x177  ldc.i4   0x2879E23D
0x17c  beq      loc_3B9
0x181  br       loc_8D5
0x186  ldloc.2
0x187  ldc.i4   0x298E5E84
0x18c  beq      loc_545
0x191  ldloc.2
0x192  ldc.i4   0x2D4F0FCA
0x197  beq      loc_663
0x19c  ldloc.2
0x19d  ldc.i4   0x2D9FADF1
0x1a2  beq      loc_495
0x1a7  br       loc_8D5
0x1ac  ldloc.2
0x1ad  ldc.i4   0x604F4858
0x1b2  bgt.un.s loc_1F2
0x1b4  ldloc.2
0x1b5  ldc.i4   0x4EE6C772
0x1ba  bgt.un.s loc_1D7
0x1bc  ldloc.2
0x1bd  ldc.i4   0x46E3AFE2
0x1c2  beq      loc_4D7
0x1c7  ldloc.2
0x1c8  ldc.i4   0x4EE6C772
0x1cd  beq      loc_4C1
0x1d2  br       loc_8D5
0x1d7  ldloc.2
0x1d8  ldc.i4   0x4EF81093
0x1dd  beq      loc_571
0x1e2  ldloc.2
0x1e3  ldc.i4   0x604F4858
0x1e8  beq      loc_5C9
0x1ed  br       loc_8D5
0x1f2  ldloc.2
0x1f3  ldc.i4   0x89E4D0D8
0x1f8  bgt.un.s loc_215
0x1fa  ldloc.2
0x1fb  ldc.i4   0x75DC3AEC
0x200  beq      loc_5DF
0x205  ldloc.2
0x206  ldc.i4   0x89E4D0D8
0x20b  beq      loc_52F
0x210  br       loc_8D5
0x215  ldloc.2
0x216  ldc.i4   0x8B9578F9
0x21b  beq      loc_4AB
0x220  ldloc.2
0x221  ldc.i4   0x8E464C28
0x226  beq      loc_469
0x22b  ldloc.2
0x22c  ldc.i4   0x9018E81C
0x231  beq      loc_621
0x236  br       loc_8D5
0x23b  ldloc.2
0x23c  ldc.i4   0xD5AED7DD
0x241  bgt.un   loc_2D5
0x246  ldloc.2
0x247  ldc.i4   0xA5AAF4EC
0x24c  bgt.un.s loc_28C
0x24e  ldloc.2
0x24f  ldc.i4   0x9D813523
0x254  bgt.un.s loc_271
0x256  ldloc.2
0x257  ldc.i4   0x9BEC7490
0x25c  beq      loc_3E5
0x261  ldloc.2
0x262  ldc.i4   0x9D813523
0x267  beq      loc_3A3
0x26c  br       loc_8D5
0x271  ldloc.2
0x272  ldc.i4   0xA19A545F
0x277  beq      loc_4ED
0x27c  ldloc.2
0x27d  ldc.i4   0xA5AAF4EC
0x282  beq      loc_43D
0x287  br       loc_8D5
0x28c  ldloc.2
0x28d  ldc.i4   0xCB39993F
0x292  bgt.un.s loc_2AF
0x294  ldloc.2
0x295  ldc.i4   0xB22BE558
0x29a  beq      loc_453
0x29f  ldloc.2
0x2a0  ldc.i4   0xCB39993F
0x2a5  beq      loc_38D
0x2aa  br       loc_8D5
0x2af  ldloc.2
0x2b0  ldc.i4   0xD12A9F3C
0x2b5  beq      loc_47F
0x2ba  ldloc.2
0x2bb  ldc.i4   0xD2EC146C
0x2c0  beq      loc_519
0x2c5  ldloc.2
0x2c6  ldc.i4   0xD5AED7DD
0x2cb  beq      loc_3CF
0x2d0  br       loc_8D5
0x2d5  ldloc.2
0x2d6  ldc.i4   0xE58E64DA
0x2db  bgt.un.s loc_31B
0x2dd  ldloc.2
0x2de  ldc.i4   0xE0F51B96
0x2e3  bgt.un.s loc_300
0x2e5  ldloc.2
0x2e6  ldc.i4   0xD95E00C3
0x2eb  beq      loc_503
0x2f0  ldloc.2
0x2f1  ldc.i4   0xE0F51B96
0x2f6  beq      loc_411
0x2fb  br       loc_8D5
0x300  ldloc.2
0x301  ldc.i4   0xE123601C
0x306  beq      loc_60B
0x30b  ldloc.2
0x30c  ldc.i4   0xE58E64DA
0x311  beq      loc_64D
0x316  br       loc_8D5
0x31b  ldloc.2
0x31c  ldc.i4   0xEC62695E
0x321  bgt.un.s loc_33E
0x323  ldloc.2
0x324  ldc.i4   0xEA3B0224
0x329  beq      loc_3FB
0x32e  ldloc.2
0x32f  ldc.i4   0xEC62695E
0x334  beq      loc_427
0x339  br       loc_8D5
0x33e  ldloc.2
0x33f  ldc.i4   0xEC95435F
0x344  beq.s    loc_361
0x346  ldloc.2
0x347  ldc.i4   0xF1776509
0x34c  beq      loc_59D
0x351  ldloc.2
0x352  ldc.i4   0xFF5998F0
0x357  beq      loc_55B
0x35c  br       loc_8D5
0x361  ldloc.1
0x362  ldstr    aBoolean// "Boolean"
0x367  ldc.i4.0
0x368  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0x36d  brfalse  loc_679
0x372  br       loc_8D5
0x377  ldloc.1
0x378  ldstr    aBoolean_0// "Boolean[]"
0x37d  ldc.i4.0
0x37e  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0x383  brfalse  loc_68F
0x388  br       loc_8D5
0x38d  ldloc.1
0x38e  ldstr    aByte// "Byte"
0x393  ldc.i4.0
0x394  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0x399  brfalse  loc_69B
0x39e  br       loc_8D5
0x3a3  ldloc.1
0x3a4  ldstr    aByte_0// "Byte[]"
0x3a9  ldc.i4.0
0x3aa  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0x3af  brfalse  loc_6B1
0x3b4  br       loc_8D5
0x3b9  ldloc.1
0x3ba  ldstr    aChar// "Char"
0x3bf  ldc.i4.0
0x3c0  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0x3c5  brfalse  loc_6BD
0x3ca  br       loc_8D5
0x3cf  ldloc.1
0x3d0  ldstr    aChar_0// "Char[]"
0x3d5  ldc.i4.0
0x3d6  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0x3db  brfalse  loc_6D3
0x3e0  br       loc_8D5
0x3e5  ldloc.1
0x3e6  ldstr    aDatetime// "DateTime"
0x3eb  ldc.i4.0
0x3ec  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0x3f1  brfalse  loc_6DF
0x3f6  br       loc_8D5
0x3fb  ldloc.1
0x3fc  ldstr    aDatetime_0// "DateTime[]"
0x401  ldc.i4.0
0x402  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0x407  brfalse  loc_6F0
0x40c  br       loc_8D5
0x411  ldloc.1
0x412  ldstr    aDbnull// "DBNull"
0x417  ldc.i4.0
0x418  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0x41d  brfalse  loc_6FC
0x422  br       loc_8D5
0x427  ldloc.1
0x428  ldstr    aDbnull_0// "DBNull[]"
0x42d  ldc.i4.0
0x42e  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0x433  brfalse  loc_708
0x438  br       loc_8D5
0x43d  ldloc.1
0x43e  ldstr    aDecimal// "Decimal"
0x443  ldc.i4.0
0x444  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0x449  brfalse  loc_714
0x44e  br       loc_8D5
0x453  ldloc.1
0x454  ldstr    aDecimal_0// "Decimal[]"
0x459  ldc.i4.0
0x45a  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0x45f  brfalse  loc_72A
0x464  br       loc_8D5
0x469  ldloc.1
0x46a  ldstr    aDouble// "Double"
0x46f  ldc.i4.0
0x470  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0x475  brfalse  loc_736
0x47a  br       loc_8D5
0x47f  ldloc.1
0x480  ldstr    aDouble_0// "Double[]"
0x485  ldc.i4.0
0x486  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0x48b  brfalse  loc_74C
0x490  br       loc_8D5
0x495  ldloc.1
0x496  ldstr    aInt16// "Int16"
0x49b  ldc.i4.0
0x49c  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0x4a1  brfalse  loc_758
0x4a6  br       loc_8D5
0x4ab  ldloc.1
0x4ac  ldstr    aInt16_0// "Int16[]"
0x4b1  ldc.i4.0
0x4b2  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0x4b7  brfalse  loc_76E
0x4bc  br       loc_8D5
0x4c1  ldloc.1
0x4c2  ldstr    aUint16// "UInt16"
0x4c7  ldc.i4.0
0x4c8  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0x4cd  brfalse  loc_77A
0x4d2  br       loc_8D5
0x4d7  ldloc.1
0x4d8  ldstr    aUint16_0// "UInt16[]"
0x4dd  ldc.i4.0
0x4de  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0x4e3  brfalse  loc_790
0x4e8  br       loc_8D5
0x4ed  ldloc.1
0x4ee  ldstr    aInt32// "Int32"
0x4f3  ldc.i4.0
0x4f4  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0x4f9  brfalse  loc_79C
0x4fe  br       loc_8D5
0x503  ldloc.1
0x504  ldstr    aInt32_0// "Int32[]"
0x509  ldc.i4.0
  ... truncated ...
```
