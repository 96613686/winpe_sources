# Microsoft.ManagementConsole.ScopeNodeCollection::set_ContainerNode

- ea: `0x5a10`
- end: `0x5a59`
- name: `Microsoft.ManagementConsole.ScopeNodeCollection::set_ContainerNode`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x15f0`

## callees

- `0x1960`
- `0x5a10`

## pseudocode

```c

```

## disassembly

```asm
0x5a10  ldarg.0
0x5a11  ldarg.1
0x5a12  stfld    class Microsoft.ManagementConsole.ScopeNode Microsoft.ManagementConsole.ScopeNodeCollection::_containerNode
0x5a17  ldarg.0
0x5a18  call     instance class [mscorlib]System.Collections.ArrayList [mscorlib]System.Collections.CollectionBase::get_InnerList()
0x5a1d  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x5a22  stloc.1
0x5a23  br.s     loc_5A3D
0x5a25  ldloc.1
0x5a26  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5a2b  castclass Microsoft.ManagementConsole.ScopeNode
0x5a30  stloc.0
0x5a31  ldloc.0
0x5a32  ldarg.0
0x5a33  ldfld    class Microsoft.ManagementConsole.ScopeNode Microsoft.ManagementConsole.ScopeNodeCollection::_containerNode
0x5a38  callvirt instance void Microsoft.ManagementConsole.ScopeNode::SetParent(class Microsoft.ManagementConsole.ScopeNode parent)
0x5a3d  ldloc.1
0x5a3e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5a43  brtrue.s loc_5A25
0x5a45  leave.s  loc_5A58
0x5a47  ldloc.1
0x5a48  isinst   [mscorlib]System.IDisposable
0x5a4d  stloc.2
0x5a4e  ldloc.2
0x5a4f  brfalse.s loc_5A57
0x5a51  ldloc.2
0x5a52  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5a57  endfinally
0x5a58  ret
```
