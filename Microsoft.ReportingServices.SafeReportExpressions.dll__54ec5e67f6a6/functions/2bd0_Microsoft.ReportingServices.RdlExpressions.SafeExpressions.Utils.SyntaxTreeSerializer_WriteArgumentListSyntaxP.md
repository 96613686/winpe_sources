# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteArgumentListSyntaxProperties

- ea: `0x2bd0`
- end: `0x2c22`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteArgumentListSyntaxProperties`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2a10`

## callees

- `0x2d20`

## pseudocode

```c

```

## disassembly

```asm
0x2bd0  ldarg.0
0x2bd1  ldarg.1
0x2bd2  ldarg.2
0x2bd3  callvirt instance valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ArgumentListSyntax::get_OpenParenToken()
0x2bd8  ldarg.2
0x2bd9  callvirt instance valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ArgumentListSyntax::get_CloseParenToken()
0x2bde  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteOpenCloseParanTokenProperties(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken openParanToken, valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken closeParanToken)
0x2be3  ldarg.1
0x2be4  ldstr    aArgumentcount// "ArgumentCount"
0x2be9  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0x2bee  ldarg.1
0x2bef  ldarg.2
0x2bf0  callvirt instance valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SeparatedSyntaxList`1<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ArgumentSyntax> [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ArgumentListSyntax::get_Arguments()
0x2bf5  stloc.0
0x2bf6  ldloca.s 0
0x2bf8  call     instance int32 valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SeparatedSyntaxList`1<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ArgumentSyntax>::get_Count()
0x2bfd  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteValue(int32)
0x2c02  ldarg.1
0x2c03  ldstr    aSeparatorcount// "SeparatorCount"
0x2c08  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0x2c0d  ldarg.1
0x2c0e  ldarg.2
0x2c0f  callvirt instance valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SeparatedSyntaxList`1<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ArgumentSyntax> [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ArgumentListSyntax::get_Arguments()
0x2c14  stloc.0
0x2c15  ldloca.s 0
0x2c17  call     instance int32 valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SeparatedSyntaxList`1<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ArgumentSyntax>::get_SeparatorCount()
0x2c1c  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteValue(int32)
0x2c21  ret
```
