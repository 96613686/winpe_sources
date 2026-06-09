# Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::VariantToObject

- ea: `0x33e70`
- end: `0x340bc`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::VariantToObject`
- size: `588`
- prototype: ``
- caller_count: `15`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x29df0`
- `0x33810`
- `0x33970`
- `0x3b8e0`
- `0x3ca40`
- `0x3cc00`
- `0x4ecd0`
- `0x4edf0`
- `0x4eec0`
- `0x4f530`
- `0x4fa90`
- `0x4fcb0`
- `0x51a00`
- `0x7ddf0`
- `0x7e140`

## callees

- `0x13510`
- `0x33e70`

## string_xrefs

- `0x34095`: `Use VariantSidToUserName method `

## pseudocode

```c

```

## disassembly

```asm
0x33e70  ldnull
0x33e71  stloc.0
0x33e72  ldarg.0
0x33e73  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::type
0x33e78  stloc.2
0x33e79  ldloc.2
0x33e7a  switch   loc_33F14, loc_34044, loc_33F3B, loc_33F52, loc_33F9D, loc_33F6A, loc_33FAE, loc_33F7B, loc_33FBF, loc_33F8C, loc_33FD0, loc_33FE1, loc_33FF2, loc_33F1B, loc_340A0, loc_34058, loc_340A0, loc_34003, loc_34021, loc_34095, loc_33FBF, loc_33FD0, loc_340A0, loc_340A0, loc_340A0, loc_340A0, loc_340A0, loc_340A0, loc_340A0, loc_340A0, loc_340A0, loc_340A0, loc_340A0, loc_340A0, loc_340A0, loc_34044
0x33f0f  br       loc_340A0
0x33f14  ldnull
0x33f15  stloc.0
0x33f16  br       loc_340A0
0x33f1b  ldarg.0
0x33f1c  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::Int32Val
0x33f21  brtrue.s loc_33F2F
0x33f23  ldc.i4.0
0x33f24  box      [mscorlib]System.Boolean
0x33f29  stloc.0
0x33f2a  br       loc_340A0
0x33f2f  ldc.i4.1
0x33f30  box      [mscorlib]System.Boolean
0x33f35  stloc.0
0x33f36  br       loc_340A0
0x33f3b  ldsfld   string [mscorlib]System.String::Empty
0x33f40  stloc.0
0x33f41  ldarg.0
0x33f42  ldfld    native int Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::EvtHandle
0x33f47  call     string [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStringAnsi(native int)
0x33f4c  stloc.0
0x33f4d  br       loc_340A0
0x33f52  ldc.i4.0
0x33f53  box      [mscorlib]System.SByte
0x33f58  stloc.0
0x33f59  ldarg.0
0x33f5a  ldfld    int8 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::SByteVal
0x33f5f  box      [mscorlib]System.SByte
0x33f64  stloc.0
0x33f65  br       loc_340A0
0x33f6a  ldarg.0
0x33f6b  ldfld    int16 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::Int16Val
0x33f70  box      [mscorlib]System.Int16
0x33f75  stloc.0
0x33f76  br       loc_340A0
0x33f7b  ldarg.0
0x33f7c  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::Int32Val
0x33f81  box      [mscorlib]System.Int32
0x33f86  stloc.0
0x33f87  br       loc_340A0
0x33f8c  ldarg.0
0x33f8d  ldfld    int64 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::Int64Val
0x33f92  box      [mscorlib]System.Int64
0x33f97  stloc.0
0x33f98  br       loc_340A0
0x33f9d  ldarg.0
0x33f9e  ldfld    unsigned int8 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::ByteVal
0x33fa3  box      [mscorlib]System.Byte
0x33fa8  stloc.0
0x33fa9  br       loc_340A0
0x33fae  ldarg.0
0x33faf  ldfld    unsigned int16 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::UInt16Val
0x33fb4  box      [mscorlib]System.UInt16
0x33fb9  stloc.0
0x33fba  br       loc_340A0
0x33fbf  ldarg.0
0x33fc0  ldfld    unsigned int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::UInt32Val
0x33fc5  box      [mscorlib]System.UInt32
0x33fca  stloc.0
0x33fcb  br       loc_340A0
0x33fd0  ldarg.0
0x33fd1  ldfld    unsigned int64 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::UInt64Val
0x33fd6  box      [mscorlib]System.UInt64
0x33fdb  stloc.0
0x33fdc  br       loc_340A0
0x33fe1  ldarg.0
0x33fe2  ldfld    float32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::SingleVal
0x33fe7  box      [mscorlib]System.Single
0x33fec  stloc.0
0x33fed  br       loc_340A0
0x33ff2  ldarg.0
0x33ff3  ldfld    float64 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::DoubleVal
0x33ff8  box      [mscorlib]System.Double
0x33ffd  stloc.0
0x33ffe  br       loc_340A0
0x34003  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x34008  box      [mscorlib]System.DateTime
0x3400d  stloc.0
0x3400e  ldarg.0
0x3400f  ldfld    unsigned int64 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::FileTimeVal
0x34014  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::FromFileTime(int64)
0x34019  box      [mscorlib]System.DateTime
0x3401e  stloc.0
0x3401f  br.s     loc_340A0
0x34021  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x34026  box      [mscorlib]System.DateTime
0x3402b  stloc.0
0x3402c  ldarg.0
0x3402d  ldfld    native int Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::SysTimeVal
0x34032  call     int64 [mscorlib]System.IntPtr::op_Explicit(native int)
0x34037  newobj   instance void [mscorlib]System.DateTime::.ctor(int64)
0x3403c  box      [mscorlib]System.DateTime
0x34041  stloc.0
0x34042  br.s     loc_340A0
0x34044  ldsfld   string [mscorlib]System.String::Empty
0x34049  stloc.0
0x3404a  ldarg.0
0x3404b  ldfld    native int Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::StringVal
0x34050  call     string [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStringAuto(native int)
0x34055  stloc.0
0x34056  br.s     loc_340A0
0x34058  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3405d  box      [mscorlib]System.Guid
0x34062  stloc.0
0x34063  ldc.i4.s 0x10
0x34065  newarr   [mscorlib]System.Byte
0x3406a  stloc.1
0x3406b  ldc.i4.0
0x3406c  stloc.3
0x3406d  br.s     loc_34082
0x3406f  ldloc.1
0x34070  ldloc.3
0x34071  ldarg.0
0x34072  ldfld    native int Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::GuidVal
0x34077  ldloc.3
0x34078  call     unsigned int8 [mscorlib]System.Runtime.InteropServices.Marshal::ReadByte(native int, int32)
0x3407d  stelem.i1
0x3407e  ldloc.3
0x3407f  ldc.i4.1
0x34080  add
0x34081  stloc.3
0x34082  ldloc.3
0x34083  ldc.i4.s 0x10
0x34085  blt.s    loc_3406F
0x34087  ldloc.1
0x34088  newobj   instance void [mscorlib]System.Guid::.ctor(unsigned int8[])
0x3408d  box      [mscorlib]System.Guid
0x34092  stloc.0
0x34093  br.s     loc_340A0
0x34095  ldstr    aUseVariantsidt// "Use VariantSidToUserName method "
0x3409a  ldc.i4.m1
0x3409b  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x340a0  leave.s  loc_340BA
0x340a2  pop
0x340a3  leave.s  loc_340BA
0x340a5  pop
0x340a6  leave.s  loc_340BA
0x340a8  pop
0x340a9  leave.s  loc_340BA
0x340ab  pop
0x340ac  leave.s  loc_340BA
0x340ae  pop
0x340af  leave.s  loc_340BA
0x340b1  pop
0x340b2  leave.s  loc_340BA
0x340b4  pop
0x340b5  leave.s  loc_340BA
0x340b7  pop
0x340b8  leave.s  loc_340BA
0x340ba  ldloc.0
0x340bb  ret
```
