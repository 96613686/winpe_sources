# Microsoft.ManagementConsole.ScopeNode::OnNodeSyncManagerRemove

- ea: `0x1ea0`
- end: `0x1edd`
- name: `Microsoft.ManagementConsole.ScopeNode::OnNodeSyncManagerRemove`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1350`

## callees

- `0x1ea0`
- `0x1ee0`
- `0x7560`

## pseudocode

```c

```

## disassembly

```asm
0x1ea0  ldarg.0
0x1ea1  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ManagementConsole.CustomStatus> Microsoft.ManagementConsole.ScopeNode::_customStatusList
0x1ea6  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ManagementConsole.CustomStatus>::GetEnumerator()
0x1eab  stloc.1
0x1eac  br.s     loc_1EBC
0x1eae  ldloca.s 1
0x1eb0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ManagementConsole.CustomStatus>::get_Current()
0x1eb5  stloc.0
0x1eb6  ldloc.0
0x1eb7  callvirt instance void Microsoft.ManagementConsole.CustomStatus::DetachRequestStatus()
0x1ebc  ldloca.s 1
0x1ebe  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ManagementConsole.CustomStatus>::MoveNext()
0x1ec3  brtrue.s loc_1EAE
0x1ec5  leave.s  loc_1ED5
0x1ec7  ldloca.s 1
0x1ec9  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ManagementConsole.CustomStatus>
0x1ecf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ed4  endfinally
0x1ed5  ldarg.0
0x1ed6  ldc.i4.0
0x1ed7  call     instance void Microsoft.ManagementConsole.ScopeNode::UpdateViewDescriptionSubscription(bool fSubscribe)
0x1edc  ret
```
