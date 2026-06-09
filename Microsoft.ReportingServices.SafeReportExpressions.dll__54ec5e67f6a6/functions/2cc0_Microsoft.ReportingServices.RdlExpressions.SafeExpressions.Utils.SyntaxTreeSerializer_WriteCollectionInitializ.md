# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteCollectionInitializerSyntaxProperties

- ea: `0x2cc0`
- end: `0x2cff`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteCollectionInitializerSyntaxProperties`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x2a10`

## pseudocode

```c

```

## disassembly

```asm
0x2cc0  ldarg.1
0x2cc1  ldstr    aItemcount// "ItemCount"
0x2cc6  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0x2ccb  ldarg.1
0x2ccc  ldarg.2
0x2ccd  callvirt instance valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SeparatedSyntaxList`1<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax> [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.CollectionInitializerSyntax::get_Initializers()
0x2cd2  stloc.0
0x2cd3  ldloca.s 0
0x2cd5  call     instance int32 valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SeparatedSyntaxList`1<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax>::get_Count()
0x2cda  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteValue(int32)
0x2cdf  ldarg.1
0x2ce0  ldstr    aSeparatorcount// "SeparatorCount"
0x2ce5  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0x2cea  ldarg.1
0x2ceb  ldarg.2
0x2cec  callvirt instance valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SeparatedSyntaxList`1<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax> [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.CollectionInitializerSyntax::get_Initializers()
0x2cf1  stloc.0
0x2cf2  ldloca.s 0
0x2cf4  call     instance int32 valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SeparatedSyntaxList`1<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax>::get_SeparatorCount()
0x2cf9  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteValue(int32)
0x2cfe  ret
```
