# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteNodeSpecificProperties

- ea: `0x2a10`
- end: `0x2ac2`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteNodeSpecificProperties`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x2900`

## callees

- `0x2a10`
- `0x2ad0`
- `0x2b30`
- `0x2bb0`
- `0x2bc0`
- `0x2bd0`
- `0x2c30`
- `0x2c90`
- `0x2ca0`
- `0x2cc0`

## pseudocode

```c

```

## disassembly

```asm
0x2a10  ldarg.2
0x2a11  isinst   [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.IdentifierNameSyntax
0x2a16  stloc.0
0x2a17  ldloc.0
0x2a18  brfalse.s loc_2A22
0x2a1a  ldarg.0
0x2a1b  ldarg.1
0x2a1c  ldloc.0
0x2a1d  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteIdentiferNameProperties(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.IdentifierNameSyntax syntax)
0x2a22  ldarg.2
0x2a23  isinst   [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.LiteralExpressionSyntax
0x2a28  stloc.1
0x2a29  ldloc.1
0x2a2a  brfalse.s loc_2A34
0x2a2c  ldarg.0
0x2a2d  ldarg.1
0x2a2e  ldloc.1
0x2a2f  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteLiteralExpressionSyntaxProperties(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.LiteralExpressionSyntax syntax)
0x2a34  ldarg.2
0x2a35  isinst   [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.BinaryExpressionSyntax
0x2a3a  stloc.2
0x2a3b  ldloc.2
0x2a3c  brfalse.s loc_2A46
0x2a3e  ldarg.0
0x2a3f  ldarg.1
0x2a40  ldloc.2
0x2a41  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteBinaryExpressionSyntaxProperties(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.BinaryExpressionSyntax syntax)
0x2a46  ldarg.2
0x2a47  isinst   [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.MemberAccessExpressionSyntax
0x2a4c  stloc.3
0x2a4d  ldloc.3
0x2a4e  brfalse.s loc_2A58
0x2a50  ldarg.0
0x2a51  ldarg.1
0x2a52  ldloc.3
0x2a53  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteMemberAccessExpressionSyntaxProperties(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.MemberAccessExpressionSyntax syntax)
0x2a58  ldarg.2
0x2a59  isinst   [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ArgumentListSyntax
0x2a5e  stloc.s  4
0x2a60  ldloc.s  4
0x2a62  brfalse.s loc_2A6D
0x2a64  ldarg.0
0x2a65  ldarg.1
0x2a66  ldloc.s  4
0x2a68  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteArgumentListSyntaxProperties(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ArgumentListSyntax syntax)
0x2a6d  ldarg.2
0x2a6e  isinst   [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.TernaryConditionalExpressionSyntax
0x2a73  stloc.s  5
0x2a75  ldloc.s  5
0x2a77  brfalse.s loc_2A82
0x2a79  ldarg.0
0x2a7a  ldarg.1
0x2a7b  ldloc.s  5
0x2a7d  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteTernaryConditionalExpressionSyntaxProperties(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.TernaryConditionalExpressionSyntax syntax)
0x2a82  ldarg.2
0x2a83  isinst   [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.UnaryExpressionSyntax
0x2a88  stloc.s  6
0x2a8a  ldloc.s  6
0x2a8c  brfalse.s loc_2A97
0x2a8e  ldarg.0
0x2a8f  ldarg.1
0x2a90  ldloc.s  6
0x2a92  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteUnaryExpressionSyntaxProperties(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.UnaryExpressionSyntax syntax)
0x2a97  ldarg.2
0x2a98  isinst   [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ParenthesizedExpressionSyntax
0x2a9d  stloc.s  7
0x2a9f  ldloc.s  7
0x2aa1  brfalse.s loc_2AAC
0x2aa3  ldarg.0
0x2aa4  ldarg.1
0x2aa5  ldloc.s  7
0x2aa7  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteParenthesizedExpressionSyntaxProperties(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ParenthesizedExpressionSyntax syntax)
0x2aac  ldarg.2
0x2aad  isinst   [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.CollectionInitializerSyntax
0x2ab2  stloc.s  8
0x2ab4  ldloc.s  8
0x2ab6  brfalse.s loc_2AC1
0x2ab8  ldarg.0
0x2ab9  ldarg.1
0x2aba  ldloc.s  8
0x2abc  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteCollectionInitializerSyntaxProperties(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.CollectionInitializerSyntax syntax)
0x2ac1  ret
```
