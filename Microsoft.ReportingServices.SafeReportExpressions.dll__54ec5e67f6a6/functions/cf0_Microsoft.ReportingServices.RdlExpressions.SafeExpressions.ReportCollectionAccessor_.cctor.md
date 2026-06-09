# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ReportCollectionAccessor::.cctor

- ea: `0xcf0`
- end: `0xd4f`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ReportCollectionAccessor::.cctor`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0xcf0  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0xcf5  dup
0xcf6  ldstr    aAggregates// "AGGREGATES"
0xcfb  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xd00  pop
0xd01  dup
0xd02  ldstr    aFields// "FIELDS"
0xd07  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xd0c  pop
0xd0d  dup
0xd0e  ldstr    aGlobals// "GLOBALS"
0xd13  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xd18  pop
0xd19  dup
0xd1a  ldstr    aLookups// "LOOKUPS"
0xd1f  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xd24  pop
0xd25  dup
0xd26  ldstr    aParameters// "PARAMETERS"
0xd2b  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xd30  pop
0xd31  dup
0xd32  ldstr    aUser// "USER"
0xd37  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xd3c  pop
0xd3d  dup
0xd3e  ldstr    aVariables// "VARIABLES"
0xd43  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xd48  pop
0xd49  stsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ReportCollectionAccessor::SupportedCollections
0xd4e  ret
```
