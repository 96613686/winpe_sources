# Microsoft.ReportingServices.Modeling.FunctionNode::ResolveStaticAndCompile

- ea: `0x1ab10`
- end: `0x1ac04`
- name: `Microsoft.ReportingServices.Modeling.FunctionNode::ResolveStaticAndCompile`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1a670`

## callees

- `0x84f0`
- `0x8580`
- `0x85d0`
- `0x85e0`
- `0x85f0`
- `0x8600`
- `0x97d0`
- `0x186b0`
- `0x18fe0`
- `0x1a0b0`
- `0x1ab10`
- `0x210c0`

## string_xrefs

- `0x1abc6`: `Failed to compile static function: `

## pseudocode

```c

```

## disassembly

```asm
0x1ab10  ldarg.1
0x1ab11  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldResolveStaticFunctions()
0x1ab16  brtrue.s loc_1AB1A
0x1ab18  ldnull
0x1ab19  ret
0x1ab1a  ldarg.1
0x1ab1b  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldPersist()
0x1ab20  brtrue.s loc_1AB2D
0x1ab22  ldstr    aNormalizeWitho// "Normalize without persist."
0x1ab27  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1ab2c  throw
0x1ab2d  ldnull
0x1ab2e  stloc.0
0x1ab2f  ldarg.2
0x1ab30  callvirt instance valuetype Microsoft.ReportingServices.Modeling.FunctionName Microsoft.ReportingServices.Modeling.FunctionInfo::get_FunctionName()
0x1ab35  stloc.1
0x1ab36  ldloc.1
0x1ab37  ldc.i4.s 0x2E
0x1ab39  bgt.un.s loc_1AB47
0x1ab3b  ldloc.1
0x1ab3c  ldc.i4.s 0x2D
0x1ab3e  beq.s    loc_1AB79
0x1ab40  ldloc.1
0x1ab41  ldc.i4.s 0x2E
0x1ab43  beq.s    loc_1AB8C
0x1ab45  br.s     loc_1AB9F
0x1ab47  ldloc.1
0x1ab48  ldc.i4.s 0x41
0x1ab4a  beq.s    loc_1AB53
0x1ab4c  ldloc.1
0x1ab4d  ldc.i4.s 0x42
0x1ab4f  beq.s    loc_1AB66
0x1ab51  br.s     loc_1AB9F
0x1ab53  ldarg.1
0x1ab54  callvirt instance class Microsoft.ReportingServices.Modeling.ExpressionNode Microsoft.ReportingServices.Modeling.CompilationContext::get_UserID()
0x1ab59  callvirt instance class Microsoft.ReportingServices.Modeling.ExpressionNode Microsoft.ReportingServices.Modeling.ExpressionNode::Clone()
0x1ab5e  newobj   instance void Microsoft.ReportingServices.Modeling.Expression::.ctor(class Microsoft.ReportingServices.Modeling.ExpressionNode node)
0x1ab63  stloc.0
0x1ab64  br.s     loc_1ABC3
0x1ab66  ldarg.1
0x1ab67  callvirt instance class Microsoft.ReportingServices.Modeling.ExpressionNode Microsoft.ReportingServices.Modeling.CompilationContext::get_UserCulture()
0x1ab6c  callvirt instance class Microsoft.ReportingServices.Modeling.ExpressionNode Microsoft.ReportingServices.Modeling.ExpressionNode::Clone()
0x1ab71  newobj   instance void Microsoft.ReportingServices.Modeling.Expression::.ctor(class Microsoft.ReportingServices.Modeling.ExpressionNode node)
0x1ab76  stloc.0
0x1ab77  br.s     loc_1ABC3
0x1ab79  ldarg.1
0x1ab7a  callvirt instance class Microsoft.ReportingServices.Modeling.ExpressionNode Microsoft.ReportingServices.Modeling.CompilationContext::get_Now()
0x1ab7f  callvirt instance class Microsoft.ReportingServices.Modeling.ExpressionNode Microsoft.ReportingServices.Modeling.ExpressionNode::Clone()
0x1ab84  newobj   instance void Microsoft.ReportingServices.Modeling.Expression::.ctor(class Microsoft.ReportingServices.Modeling.ExpressionNode node)
0x1ab89  stloc.0
0x1ab8a  br.s     loc_1ABC3
0x1ab8c  ldarg.1
0x1ab8d  callvirt instance class Microsoft.ReportingServices.Modeling.ExpressionNode Microsoft.ReportingServices.Modeling.CompilationContext::get_Today()
0x1ab92  callvirt instance class Microsoft.ReportingServices.Modeling.ExpressionNode Microsoft.ReportingServices.Modeling.ExpressionNode::Clone()
0x1ab97  newobj   instance void Microsoft.ReportingServices.Modeling.Expression::.ctor(class Microsoft.ReportingServices.Modeling.ExpressionNode node)
0x1ab9c  stloc.0
0x1ab9d  br.s     loc_1ABC3
0x1ab9f  ldstr    aUnrecognizedSt// "Unrecognized static function: "
0x1aba4  ldarg.2
0x1aba5  callvirt instance valuetype Microsoft.ReportingServices.Modeling.FunctionName Microsoft.ReportingServices.Modeling.FunctionInfo::get_FunctionName()
0x1abaa  stloc.2
0x1abab  ldloca.s 2
0x1abad  constrained. Microsoft.ReportingServices.Modeling.FunctionName
0x1abb3  callvirt instance string [mscorlib]System.Object::ToString()
0x1abb8  call     string [mscorlib]System.String::Concat(string, string)
0x1abbd  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1abc2  throw
0x1abc3  ldloc.0
0x1abc4  brtrue.s loc_1ABEA
0x1abc6  ldstr    aFailedToCompil_0// "Failed to compile static function: "
0x1abcb  ldarg.2
0x1abcc  callvirt instance valuetype Microsoft.ReportingServices.Modeling.FunctionName Microsoft.ReportingServices.Modeling.FunctionInfo::get_FunctionName()
0x1abd1  stloc.1
0x1abd2  ldloca.s 1
0x1abd4  constrained. Microsoft.ReportingServices.Modeling.FunctionName
0x1abda  callvirt instance string [mscorlib]System.Object::ToString()
0x1abdf  call     string [mscorlib]System.String::Concat(string, string)
0x1abe4  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1abe9  throw
0x1abea  ldloc.0
0x1abeb  ldarg.1
0x1abec  ldsfld   valuetype Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags::None
0x1abf1  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType> Microsoft.ReportingServices.Modeling.Expression::Compile(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, valuetype Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags flags)
0x1abf6  stloc.3
0x1abf7  ldloca.s 3
0x1abf9  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::get_HasValue()
0x1abfe  brtrue.s loc_1AC02
0x1ac00  ldnull
0x1ac01  ret
0x1ac02  ldloc.0
0x1ac03  ret
```
