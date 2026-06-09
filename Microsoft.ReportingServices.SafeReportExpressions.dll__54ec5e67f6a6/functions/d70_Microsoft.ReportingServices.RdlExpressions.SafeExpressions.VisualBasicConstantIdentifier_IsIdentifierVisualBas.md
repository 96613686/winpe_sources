# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasicConstantIdentifier::IsIdentifierVisualBasicConstant

- ea: `0xd70`
- end: `0xd83`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasicConstantIdentifier::IsIdentifierVisualBasicConstant`
- size: `19`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0xfe0`
- `0x2da0`

## pseudocode

```c

```

## disassembly

```asm
0xd70  ldarg.1
0xd71  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0xd76  stloc.0
0xd77  ldsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasicConstantIdentifier::VisualBasicConstants
0xd7c  ldloc.0
0xd7d  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Contains(var<u1>)
0xd82  ret
```
