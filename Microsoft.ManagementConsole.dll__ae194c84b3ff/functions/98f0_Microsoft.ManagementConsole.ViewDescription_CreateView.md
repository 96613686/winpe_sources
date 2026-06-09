# Microsoft.ManagementConsole.ViewDescription::CreateView

- ea: `0x98f0`
- end: `0x9920`
- name: `Microsoft.ManagementConsole.ViewDescription::CreateView`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x8be0`

## callees

- `0x98f0`
- `0x9bf0`
- `0xb2f0`

## string_xrefs

- `0x98f3`: `scopeNode`

## pseudocode

```c

```

## disassembly

```asm
0x98f0  ldarg.1
0x98f1  brtrue.s loc_98FE
0x98f3  ldstr    aScopenode// "scopeNode"
0x98f8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x98fd  throw
0x98fe  ldarg.0
0x98ff  ldfld    class [mscorlib]System.Type Microsoft.ManagementConsole.ViewDescription::_viewType
0x9904  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x9909  castclass Microsoft.ManagementConsole.View
0x990e  stloc.0
0x990f  ldloc.0
0x9910  ldarg.1
0x9911  ldarg.2
0x9912  ldarg.3
0x9913  ldarg.0
0x9914  callvirt instance void Microsoft.ManagementConsole.View::Initialize(class Microsoft.ManagementConsole.ScopeNode scopeNode, int32 componentId, int32 viewInstanceId, class Microsoft.ManagementConsole.ViewDescription viewDescription)
0x9919  ldloc.0
0x991a  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IMessageClient Microsoft.ManagementConsole.View::get_MessageClient()
0x991f  ret
```
