# Microsoft.ManagementConsole.ScopeNode::OnNodeSyncManagerAdd

- ea: `0x1e60`
- end: `0x1e9d`
- name: `Microsoft.ManagementConsole.ScopeNode::OnNodeSyncManagerAdd`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1230`

## callees

- `0x1e60`
- `0x1ee0`
- `0x74e0`

## pseudocode

```c

```

## disassembly

```asm
0x1e60  ldarg.0
0x1e61  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ManagementConsole.CustomStatus> Microsoft.ManagementConsole.ScopeNode::_customStatusList
0x1e66  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ManagementConsole.CustomStatus>::GetEnumerator()
0x1e6b  stloc.1
0x1e6c  br.s     loc_1E7C
0x1e6e  ldloca.s 1
0x1e70  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ManagementConsole.CustomStatus>::get_Current()
0x1e75  stloc.0
0x1e76  ldloc.0
0x1e77  callvirt instance void Microsoft.ManagementConsole.CustomStatus::AttachRequestStatus()
0x1e7c  ldloca.s 1
0x1e7e  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ManagementConsole.CustomStatus>::MoveNext()
0x1e83  brtrue.s loc_1E6E
0x1e85  leave.s  loc_1E95
0x1e87  ldloca.s 1
0x1e89  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ManagementConsole.CustomStatus>
0x1e8f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e94  endfinally
0x1e95  ldarg.0
0x1e96  ldc.i4.1
0x1e97  call     instance void Microsoft.ManagementConsole.ScopeNode::UpdateViewDescriptionSubscription(bool fSubscribe)
0x1e9c  ret
```
