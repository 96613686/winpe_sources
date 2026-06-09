# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteTernaryConditionalExpressionSyntaxProperties

- ea: `0x2c30`
- end: `0x2c82`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteTernaryConditionalExpressionSyntaxProperties`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2a10`

## callees

- `0x2d20`

## string_xrefs

- `0x2c44`: `FirstCommaToken`
- `0x2c63`: `SecondCommaToken`

## pseudocode

```c

```

## disassembly

```asm
0x2c30  ldarg.0
0x2c31  ldarg.1
0x2c32  ldarg.2
0x2c33  callvirt instance valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.TernaryConditionalExpressionSyntax::get_OpenParenToken()
0x2c38  ldarg.2
0x2c39  callvirt instance valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.TernaryConditionalExpressionSyntax::get_CloseParenToken()
0x2c3e  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteOpenCloseParanTokenProperties(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken openParanToken, valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken closeParanToken)
0x2c43  ldarg.1
0x2c44  ldstr    aFirstcommatoke// "FirstCommaToken"
0x2c49  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0x2c4e  ldarg.1
0x2c4f  ldarg.2
0x2c50  callvirt instance valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.TernaryConditionalExpressionSyntax::get_FirstCommaToken()
0x2c55  stloc.0
0x2c56  ldloca.s 0
0x2c58  call     instance string [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken::get_Text()
0x2c5d  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteValue(string)
0x2c62  ldarg.1
0x2c63  ldstr    aSecondcommatok// "SecondCommaToken"
0x2c68  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0x2c6d  ldarg.1
0x2c6e  ldarg.2
0x2c6f  callvirt instance valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.TernaryConditionalExpressionSyntax::get_SecondCommaToken()
0x2c74  stloc.0
0x2c75  ldloca.s 0
0x2c77  call     instance string [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken::get_Text()
0x2c7c  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteValue(string)
0x2c81  ret
```
