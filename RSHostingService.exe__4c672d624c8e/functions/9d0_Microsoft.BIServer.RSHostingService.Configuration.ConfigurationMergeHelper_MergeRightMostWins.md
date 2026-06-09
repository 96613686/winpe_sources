# Microsoft.BIServer.RSHostingService.Configuration.ConfigurationMergeHelper::MergeRightMostWins

- ea: `0x9d0`
- end: `0x9f3`
- name: `Microsoft.BIServer.RSHostingService.Configuration.ConfigurationMergeHelper::MergeRightMostWins`
- size: `35`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x10e0`
- `0x3390`

## callees

- `0x9d0`
- `0xa00`

## pseudocode

```c

```

## disassembly

```asm
0x9d0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x9d5  stloc.0
0x9d6  ldarg.0
0x9d7  stloc.1
0x9d8  ldc.i4.0
0x9d9  stloc.2
0x9da  br.s     loc_9EB
0x9dc  ldloc.1
0x9dd  ldloc.2
0x9de  ldelem.ref
0x9df  stloc.3
0x9e0  ldloc.0
0x9e1  ldloc.3
0x9e2  call     void Microsoft.BIServer.RSHostingService.Configuration.ConfigurationMergeHelper::MergeValuesFromSourceIntoTarget(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> target, class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, string> source)
0x9e7  ldloc.2
0x9e8  ldc.i4.1
0x9e9  add
0x9ea  stloc.2
0x9eb  ldloc.2
0x9ec  ldloc.1
0x9ed  ldlen
0x9ee  conv.i4
0x9ef  blt.s    loc_9DC
0x9f1  ldloc.0
0x9f2  ret
```
