# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasic.BinaryExpressionEvaluator::Evaluate

- ea: `0x950`
- end: `0xb2f`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasic.BinaryExpressionEvaluator::Evaluate`
- size: `479`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xe0`
- `0x950`

## pseudocode

```c

```

## disassembly

```asm
0x950  ldarg.0
0x951  ldarg.1
0x952  call     object [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::GetObjectValue(object)
0x957  call     instance object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasic.ArithmeticEvaluator::CastToStrongType(object value)
0x95c  call     object [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::GetObjectValue(object)
0x961  stloc.1
0x962  ldarg.0
0x963  ldarg.2
0x964  call     object [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::GetObjectValue(object)
0x969  call     instance object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasic.ArithmeticEvaluator::CastToStrongType(object value)
0x96e  call     object [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::GetObjectValue(object)
0x973  stloc.2
0x974  ldarg.3
0x975  stloc.3
0x976  ldloc.3
0x977  ldc.i4   0x133
0x97c  sub
0x97d  switch   loc_9EF, loc_B0D, loc_ACB, loc_A32, loc_A83, loc_B17, loc_B17, loc_A5A, loc_A90, loc_B03, loc_A25, loc_AC1, loc_A3F, loc_AD5, loc_A9D, loc_AAB, loc_A75, loc_A67, loc_B17, loc_B17, loc_AB6, loc_AE0, loc_A4D, loc_9FC, loc_AEA, loc_A09
0x9ea  br       loc_B17
0x9ef  ldloc.1
0x9f0  ldloc.2
0x9f1  call     object [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::AddObject(object, object)
0x9f6  stloc.0
0x9f7  br       loc_B2D
0x9fc  ldloc.1
0x9fd  ldloc.2
0x9fe  call     object [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::AndObject(object, object)
0xa03  stloc.0
0xa04  br       loc_B2D
0xa09  ldloc.1
0xa0a  call     bool [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Conversions::ToBoolean(object)
0xa0f  brfalse.s loc_A19
0xa11  ldloc.2
0xa12  call     bool [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Conversions::ToBoolean(object)
0xa17  br.s     loc_A1A
0xa19  ldc.i4.0
0xa1a  box      [mscorlib]System.Boolean
0xa1f  stloc.0
0xa20  br       loc_B2D
0xa25  ldloc.1
0xa26  ldloc.2
0xa27  call     object [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::ConcatenateObject(object, object)
0xa2c  stloc.0
0xa2d  br       loc_B2D
0xa32  ldloc.1
0xa33  ldloc.2
0xa34  call     object [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::DivideObject(object, object)
0xa39  stloc.0
0xa3a  br       loc_B2D
0xa3f  ldloc.1
0xa40  ldloc.2
0xa41  ldc.i4.0
0xa42  call     object [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareObjectEqual(object, object, bool)
0xa47  stloc.0
0xa48  br       loc_B2D
0xa4d  ldloc.1
0xa4e  ldloc.2
0xa4f  call     object [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::XorObject(object, object)
0xa54  stloc.0
0xa55  br       loc_B2D
0xa5a  ldloc.1
0xa5b  ldloc.2
0xa5c  call     object [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::ExponentObject(object, object)
0xa61  stloc.0
0xa62  br       loc_B2D
0xa67  ldloc.1
0xa68  ldloc.2
0xa69  ldc.i4.0
0xa6a  call     object [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareObjectGreater(object, object, bool)
0xa6f  stloc.0
0xa70  br       loc_B2D
0xa75  ldloc.1
0xa76  ldloc.2
0xa77  ldc.i4.0
0xa78  call     object [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareObjectGreaterEqual(object, object, bool)
0xa7d  stloc.0
0xa7e  br       loc_B2D
0xa83  ldloc.1
0xa84  ldloc.2
0xa85  call     object [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::IntDivideObject(object, object)
0xa8a  stloc.0
0xa8b  br       loc_B2D
0xa90  ldloc.1
0xa91  ldloc.2
0xa92  call     object [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::LeftShiftObject(object, object)
0xa97  stloc.0
0xa98  br       loc_B2D
0xa9d  ldloc.1
0xa9e  ldloc.2
0xa9f  ldc.i4.0
0xaa0  call     object [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareObjectLess(object, object, bool)
0xaa5  stloc.0
0xaa6  br       loc_B2D
0xaab  ldloc.1
0xaac  ldloc.2
0xaad  ldc.i4.0
0xaae  call     object [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareObjectLessEqual(object, object, bool)
0xab3  stloc.0
0xab4  br.s     loc_B2D
0xab6  ldloc.1
0xab7  ldloc.2
0xab8  ldc.i4.0
0xab9  call     object [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.LikeOperator::LikeObject(object, object, valuetype [Microsoft.VisualBasic]Microsoft.VisualBasic.CompareMethod)
0xabe  stloc.0
0xabf  br.s     loc_B2D
0xac1  ldloc.1
0xac2  ldloc.2
0xac3  call     object [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::ModObject(object, object)
0xac8  stloc.0
0xac9  br.s     loc_B2D
0xacb  ldloc.1
0xacc  ldloc.2
0xacd  call     object [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::MultiplyObject(object, object)
0xad2  stloc.0
0xad3  br.s     loc_B2D
0xad5  ldloc.1
0xad6  ldloc.2
0xad7  ldc.i4.0
0xad8  call     object [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareObjectNotEqual(object, object, bool)
0xadd  stloc.0
0xade  br.s     loc_B2D
0xae0  ldloc.1
0xae1  ldloc.2
0xae2  call     object [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::OrObject(object, object)
0xae7  stloc.0
0xae8  br.s     loc_B2D
0xaea  ldloc.1
0xaeb  call     bool [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Conversions::ToBoolean(object)
0xaf0  brtrue.s loc_AFA
0xaf2  ldloc.2
0xaf3  call     bool [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Conversions::ToBoolean(object)
0xaf8  br.s     loc_AFB
0xafa  ldc.i4.1
0xafb  box      [mscorlib]System.Boolean
0xb00  stloc.0
0xb01  br.s     loc_B2D
0xb03  ldloc.1
0xb04  ldloc.2
0xb05  call     object [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::RightShiftObject(object, object)
0xb0a  stloc.0
0xb0b  br.s     loc_B2D
0xb0d  ldloc.1
0xb0e  ldloc.2
0xb0f  call     object [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::SubtractObject(object, object)
0xb14  stloc.0
0xb15  br.s     loc_B2D
0xb17  ldstr    aBinaryExpressi// "Binary Expression Evaluator: Syntax kin"...
0xb1c  ldarg.3
0xb1d  box      [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.SyntaxKind
0xb22  call     string [mscorlib]System.String::Format(string, object)
0xb27  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0xb2c  throw
0xb2d  ldloc.0
0xb2e  ret
```
