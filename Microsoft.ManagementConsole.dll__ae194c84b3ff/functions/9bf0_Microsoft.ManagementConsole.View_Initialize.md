# Microsoft.ManagementConsole.View::Initialize

- ea: `0x9bf0`
- end: `0x9c2b`
- name: `Microsoft.ManagementConsole.View::Initialize`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x98f0`

## callees

- `0x9bf0`

## string_xrefs

- `0x9bf3`: `scopeNode`

## pseudocode

```c

```

## disassembly

```asm
0x9bf0  ldarg.1
0x9bf1  brtrue.s loc_9BFE
0x9bf3  ldstr    aScopenode// "scopeNode"
0x9bf8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x9bfd  throw
0x9bfe  ldarg.s  4
0x9c00  brtrue.s loc_9C0D
0x9c02  ldstr    aViewdescriptio_4// "viewDescription"
0x9c07  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x9c0c  throw
0x9c0d  ldarg.0
0x9c0e  ldarg.2
0x9c0f  stfld    int32 Microsoft.ManagementConsole.View::_componentId
0x9c14  ldarg.0
0x9c15  ldarg.1
0x9c16  stfld    class Microsoft.ManagementConsole.ScopeNode Microsoft.ManagementConsole.View::_scopeNode
0x9c1b  ldarg.0
0x9c1c  ldarg.3
0x9c1d  stfld    int32 Microsoft.ManagementConsole.View::_viewInstanceId
0x9c22  ldarg.0
0x9c23  ldarg.s  4
0x9c25  stfld    class Microsoft.ManagementConsole.ViewDescription Microsoft.ManagementConsole.View::_viewDescription
0x9c2a  ret
```
