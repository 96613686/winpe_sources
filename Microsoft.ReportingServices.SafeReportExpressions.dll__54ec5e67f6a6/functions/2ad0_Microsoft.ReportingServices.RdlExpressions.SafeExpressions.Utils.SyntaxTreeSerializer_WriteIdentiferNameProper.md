# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteIdentiferNameProperties

- ea: `0x2ad0`
- end: `0x2b09`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteIdentiferNameProperties`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x2a10`

## callees

- `0x2ad0`
- `0x2b10`
- `0x2da0`

## pseudocode

```c

```

## disassembly

```asm
0x2ad0  ldarg.2
0x2ad1  callvirt instance valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.IdentifierNameSyntax::get_Identifier()
0x2ad6  stloc.1
0x2ad7  ldloca.s 1
0x2ad9  call     instance string [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken::get_Text()
0x2ade  stloc.0
0x2adf  ldarg.0
0x2ae0  ldloc.0
0x2ae1  call     instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::IsKnownIdentifierName(string identifierName)
0x2ae6  brtrue.s loc_2AF6
0x2ae8  ldarg.0
0x2ae9  ldarg.2
0x2aea  callvirt instance class [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxNode [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxNode::get_Parent()
0x2aef  call     instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::IsSimpleMemberAccessExpression(class [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxNode syntax)
0x2af4  brfalse.s loc_2B08
0x2af6  ldarg.1
0x2af7  ldstr    aIdentifiername// "IdentifierName"
0x2afc  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0x2b01  ldarg.1
0x2b02  ldloc.0
0x2b03  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteValue(string)
0x2b08  ret
```
