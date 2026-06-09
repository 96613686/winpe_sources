# Microsoft.ManagementConsole.ResultNodeCollection::Replace

- ea: `0x6060`
- end: `0x607c`
- name: `Microsoft.ManagementConsole.ResultNodeCollection::Replace`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xc990`

## callees

- `0x6010`

## pseudocode

```c

```

## disassembly

```asm
0x6060  ldarg.0
0x6061  ldc.i4.1
0x6062  stfld    bool Microsoft.ManagementConsole.ResultNodeCollection::_ignoreChanges
0x6067  ldarg.0
0x6068  call     instance void [mscorlib]System.Collections.CollectionBase::Clear()
0x606d  ldarg.0
0x606e  ldarg.1
0x606f  call     instance void Microsoft.ManagementConsole.ResultNodeCollection::AddRange(class Microsoft.ManagementConsole.ResultNode[] items)
0x6074  ldarg.0
0x6075  ldc.i4.0
0x6076  stfld    bool Microsoft.ManagementConsole.ResultNodeCollection::_ignoreChanges
0x607b  ret
```
