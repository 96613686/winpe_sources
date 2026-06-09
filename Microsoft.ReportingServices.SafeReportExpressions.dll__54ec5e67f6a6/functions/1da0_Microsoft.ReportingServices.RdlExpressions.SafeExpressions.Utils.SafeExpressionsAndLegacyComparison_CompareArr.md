# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareArraysByType

- ea: `0x1da0`
- end: `0x1dad`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareArraysByType`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1da0  ldarg.1
0x1da1  ldarg.2
0x1da2  call     class [mscorlib]System.Collections.IEqualityComparer [mscorlib]System.Collections.StructuralComparisons::get_StructuralEqualityComparer()
0x1da7  callvirt instance bool [mscorlib]System.Collections.IStructuralEquatable::Equals(object, class [mscorlib]System.Collections.IEqualityComparer)
0x1dac  ret
```
