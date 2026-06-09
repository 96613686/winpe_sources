# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteLiteralExpressionSyntaxProperties

- ea: `0x2b30`
- end: `0x2baf`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteLiteralExpressionSyntaxProperties`
- size: `127`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2a10`

## callees

- `0x2b30`
- `0x2d60`

## pseudocode

```c

```

## disassembly

```asm
0x2b30  ldarg.2
0x2b31  callvirt instance valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.LiteralExpressionSyntax::get_Token()
0x2b36  stloc.0
0x2b37  ldloca.s 0
0x2b39  call     instance object [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken::get_Value()
0x2b3e  brtrue.s loc_2B41
0x2b40  ret
0x2b41  ldloca.s 0
0x2b43  call     instance object [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken::get_Value()
0x2b48  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2b4d  stloc.1
0x2b4e  ldloca.s 0
0x2b50  call     instance string [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken::get_ValueText()
0x2b55  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2b5a  stloc.2
0x2b5b  ldarg.1
0x2b5c  ldstr    aValuetype// "ValueType"
0x2b61  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0x2b66  ldarg.1
0x2b67  ldloc.1
0x2b68  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x2b6d  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteValue(string)
0x2b72  ldarg.1
0x2b73  ldstr    aValuelength// "ValueLength"
0x2b78  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0x2b7d  ldarg.1
0x2b7e  ldloc.2
0x2b7f  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteValue(int32)
0x2b84  ldarg.0
0x2b85  ldloc.1
0x2b86  call     instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::IsFloatingPointNumber(class [mscorlib]System.Type valueType)
0x2b8b  brfalse.s loc_2BAE
0x2b8d  ldloca.s 0
0x2b8f  call     instance string [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken::get_ValueText()
0x2b94  ldc.i4.s 0x2E
0x2b96  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x2b9b  stloc.3
0x2b9c  ldarg.1
0x2b9d  ldstr    aDecimalpointin// "DecimalPointIndex"
0x2ba2  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0x2ba7  ldarg.1
0x2ba8  ldloc.3
0x2ba9  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteValue(int32)
0x2bae  ret
```
