# PathNodeEqualityComparer::GetHashCode

- ea: `0x3aff0`
- end: `0x3b00a`
- name: `PathNodeEqualityComparer::GetHashCode`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x97d0`
- `0x3aff0`

## string_xrefs

- `0x3aff3`: `TryGetSecurityFilterCondition.PathNodeEqualityComparer: path node is null.`

## pseudocode

```c

```

## disassembly

```asm
0x3aff0  ldarg.1
0x3aff1  brtrue.s loc_3AFFE
0x3aff3  ldstr    aTrygetsecurity_4// "TryGetSecurityFilterCondition.PathNodeE"...
0x3aff8  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x3affd  throw
0x3affe  ldarg.1
0x3afff  ldfld    class Microsoft.ReportingServices.Modeling.PathItem PathNode::m_pathItem
0x3b004  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x3b009  ret
```
