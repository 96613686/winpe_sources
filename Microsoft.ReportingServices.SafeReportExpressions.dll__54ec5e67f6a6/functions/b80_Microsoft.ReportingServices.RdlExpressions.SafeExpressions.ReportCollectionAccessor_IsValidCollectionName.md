# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ReportCollectionAccessor::IsValidCollectionName

- ea: `0xb80`
- end: `0xb93`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ReportCollectionAccessor::IsValidCollectionName`
- size: `19`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1370`
- `0x2da0`

## pseudocode

```c

```

## disassembly

```asm
0xb80  ldarg.1
0xb81  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0xb86  stloc.0
0xb87  ldsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ReportCollectionAccessor::SupportedCollections
0xb8c  ldloc.0
0xb8d  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Contains(var<u1>)
0xb92  ret
```
