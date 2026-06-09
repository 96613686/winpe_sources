# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteOpenCloseParanTokenProperties

- ea: `0x2d20`
- end: `0x2d51`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteOpenCloseParanTokenProperties`
- size: `49`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x2bd0`
- `0x2c30`
- `0x2ca0`

## string_xrefs

- `0x2d21`: `OpenParenToken`
- `0x2d39`: `CloseParenToken`

## pseudocode

```c

```

## disassembly

```asm
0x2d20  ldarg.1
0x2d21  ldstr    aOpenparentoken// "OpenParenToken"
0x2d26  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0x2d2b  ldarg.1
0x2d2c  ldarga.s 2
0x2d2e  call     instance string [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken::get_Text()
0x2d33  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteValue(string)
0x2d38  ldarg.1
0x2d39  ldstr    aCloseparentoke// "CloseParenToken"
0x2d3e  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0x2d43  ldarg.1
0x2d44  ldarga.s 3
0x2d46  call     instance string [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken::get_Text()
0x2d4b  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteValue(string)
0x2d50  ret
```
