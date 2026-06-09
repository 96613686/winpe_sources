# Microsoft.ManagementConsole.ScopeNode::Activate

- ea: `0x1990`
- end: `0x19ba`
- name: `Microsoft.ManagementConsole.ScopeNode::Activate`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xe00`

## callees

- `0x1990`
- `0x7250`
- `0x73b0`

## pseudocode

```c

```

## disassembly

```asm
0x1990  ldarg.0
0x1991  ldfld    class [mscorlib]System.EventHandler Microsoft.ManagementConsole.ScopeNode::_actionsActivated
0x1996  brfalse.s loc_19B9
0x1998  ldarg.1
0x1999  newobj   instance void Microsoft.ManagementConsole.SyncStatus::.ctor(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus requestStatus)
0x199e  stloc.0
0x199f  ldarg.0
0x19a0  ldfld    class [mscorlib]System.EventHandler Microsoft.ManagementConsole.ScopeNode::_actionsActivated
0x19a5  ldarg.0
0x19a6  ldsfld   class [mscorlib]System.EventArgs Microsoft.ManagementConsole.ScopeNode::_eventArgs
0x19ab  callvirt instance void [mscorlib]System.EventHandler::Invoke(object, class [mscorlib]System.EventArgs)
0x19b0  leave.s  loc_19B9
0x19b2  ldloc.0
0x19b3  callvirt instance void Microsoft.ManagementConsole.Status::Close()
0x19b8  endfinally
0x19b9  ret
```
