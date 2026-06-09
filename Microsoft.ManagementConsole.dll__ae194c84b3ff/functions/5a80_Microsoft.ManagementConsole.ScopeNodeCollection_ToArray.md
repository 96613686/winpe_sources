# Microsoft.ManagementConsole.ScopeNodeCollection::ToArray

- ea: `0x5a80`
- end: `0x5a9b`
- name: `Microsoft.ManagementConsole.ScopeNodeCollection::ToArray`
- size: `27`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x10b0`
- `0x11f0`
- `0x4150`

## pseudocode

```c

```

## disassembly

```asm
0x5a80  ldarg.0
0x5a81  call     instance class [mscorlib]System.Collections.ArrayList [mscorlib]System.Collections.CollectionBase::get_InnerList()
0x5a86  ldtoken  Microsoft.ManagementConsole.ScopeNode
0x5a8b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5a90  callvirt instance class [mscorlib]System.Array [mscorlib]System.Collections.ArrayList::ToArray(class [mscorlib]System.Type)
0x5a95  castclass class Microsoft.ManagementConsole.ScopeNode[]
0x5a9a  ret
```
