# System.Windows.Xps.Packaging.XpsInterleavingPolicy::Commit

- ea: `0x23f10`
- end: `0x23f5d`
- name: `System.Windows.Xps.Packaging.XpsInterleavingPolicy::Commit`
- size: `77`
- prototype: ``
- caller_count: `8`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2eb80`
- `0x2ec60`
- `0x2ed50`
- `0x2ef40`
- `0x2efc0`
- `0x2f0d0`
- `0x2f1e0`
- `0x2f2f0`

## callees

- `0x23f10`
- `0x24200`
- `0x24390`
- `0x243d0`
- `0x24560`

## pseudocode

```c

```

## disassembly

```asm
0x23f10  ldarg.1
0x23f11  brtrue.s loc_23F1E
0x23f13  ldstr    aNode// "node"
0x23f18  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x23f1d  throw
0x23f1e  ldarg.0
0x23f1f  ldfld    class [mscorlib]System.Collections.Hashtable System.Windows.Xps.Packaging.XpsInterleavingPolicy::_flushOrderItems
0x23f24  ldarg.1
0x23f25  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x23f2a  callvirt instance bool [mscorlib]System.Collections.Hashtable::ContainsKey(object)
0x23f2f  brfalse.s loc_23F39
0x23f31  ldarg.0
0x23f32  ldfld    valuetype System.Windows.Xps.Packaging.PackageInterleavingOrder System.Windows.Xps.Packaging.XpsInterleavingPolicy::_interleavingType
0x23f37  brtrue.s loc_23F47
0x23f39  ldarg.0
0x23f3a  ldarg.1
0x23f3b  call     instance void System.Windows.Xps.Packaging.XpsInterleavingPolicy::RemoveNode(class System.Windows.Xps.Packaging.INode node)
0x23f40  ldarg.1
0x23f41  callvirt instance void System.Windows.Xps.Packaging.INode::CommitInternal()
0x23f46  ret
0x23f47  ldarg.0
0x23f48  ldarg.1
0x23f49  call     instance void System.Windows.Xps.Packaging.XpsInterleavingPolicy::MarkNodeCommited(class System.Windows.Xps.Packaging.INode node)
0x23f4e  ldarg.0
0x23f4f  ldfld    bool System.Windows.Xps.Packaging.XpsInterleavingPolicy::_flushOnSubsetComplete
0x23f54  brtrue.s loc_23F5C
0x23f56  ldarg.0
0x23f57  call     instance void System.Windows.Xps.Packaging.XpsInterleavingPolicy::Flush()
0x23f5c  ret
```
