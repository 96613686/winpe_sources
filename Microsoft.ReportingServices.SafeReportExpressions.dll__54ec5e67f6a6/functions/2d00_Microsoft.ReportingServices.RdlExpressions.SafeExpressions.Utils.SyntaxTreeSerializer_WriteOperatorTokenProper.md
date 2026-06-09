# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteOperatorTokenProperty

- ea: `0x2d00`
- end: `0x2d19`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteOperatorTokenProperty`
- size: `25`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x2bb0`
- `0x2bc0`
- `0x2c90`

## string_xrefs

- `0x2d01`: `OperatorToken`

## pseudocode

```c

```

## disassembly

```asm
0x2d00  ldarg.1
0x2d01  ldstr    aOperatortoken// "OperatorToken"
0x2d06  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0x2d0b  ldarg.1
0x2d0c  ldarga.s 2
0x2d0e  call     instance string [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken::get_Text()
0x2d13  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteValue(string)
0x2d18  ret
```
