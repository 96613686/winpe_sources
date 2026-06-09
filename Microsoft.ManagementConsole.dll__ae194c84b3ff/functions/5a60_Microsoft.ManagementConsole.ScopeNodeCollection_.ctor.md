# Microsoft.ManagementConsole.ScopeNodeCollection::.ctor

- ea: `0x5a60`
- end: `0x5a71`
- name: `Microsoft.ManagementConsole.ScopeNodeCollection::.ctor`
- size: `17`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x15f0`
- `0x4110`

## callees

- `0x2bc0`

## pseudocode

```c

```

## disassembly

```asm
0x5a60  ldarg.0
0x5a61  ldtoken  Microsoft.ManagementConsole.ScopeNode
0x5a66  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5a6b  call     instance void Microsoft.ManagementConsole.BaseCollection::.ctor(class [mscorlib]System.Type type)
0x5a70  ret
```
