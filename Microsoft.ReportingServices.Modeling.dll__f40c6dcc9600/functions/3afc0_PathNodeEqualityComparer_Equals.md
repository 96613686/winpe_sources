# PathNodeEqualityComparer::Equals

- ea: `0x3afc0`
- end: `0x3afe3`
- name: `PathNodeEqualityComparer::Equals`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x97d0`
- `0x3afc0`

## string_xrefs

- `0x3afc6`: `TryGetSecurityFilterCondition.PathNodeEqualityComparer: At least one of path nodes is null.`

## pseudocode

```c

```

## disassembly

```asm
0x3afc0  ldarg.1
0x3afc1  brfalse.s loc_3AFC6
0x3afc3  ldarg.2
0x3afc4  brtrue.s loc_3AFD1
0x3afc6  ldstr    aTrygetsecurity_3// "TryGetSecurityFilterCondition.PathNodeE"...
0x3afcb  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x3afd0  throw
0x3afd1  ldarg.1
0x3afd2  ldfld    class Microsoft.ReportingServices.Modeling.PathItem PathNode::m_pathItem
0x3afd7  ldarg.2
0x3afd8  ldfld    class Microsoft.ReportingServices.Modeling.PathItem PathNode::m_pathItem
0x3afdd  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x3afe2  ret
```
