# Microsoft.ManagementConsole.Internal.ScopeNodeInsert::set_ParentScopeNodeId

- ea: `0xfb0`
- end: `0xfcd`
- name: `Microsoft.ManagementConsole.Internal.ScopeNodeInsert::set_ParentScopeNodeId`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x58d0`

## callees

- `0xfb0`

## pseudocode

```c

```

## disassembly

```asm
0xfb0  ldarg.1
0xfb1  ldc.i4   0x7FFFFFFF
0xfb6  bne.un.s loc_FC3
0xfb8  ldstr    aValue// "value"
0xfbd  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0xfc2  throw
0xfc3  ldarg.0
0xfc4  ldarg.1
0xfc5  ldc.i4.1
0xfc6  add
0xfc7  stfld    int32 Microsoft.ManagementConsole.Internal.ScopeNodeInsert::_parentScopeNodeId
0xfcc  ret
```
