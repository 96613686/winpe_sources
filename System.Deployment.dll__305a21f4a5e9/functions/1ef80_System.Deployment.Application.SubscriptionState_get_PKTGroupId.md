# System.Deployment.Application.SubscriptionState::get_PKTGroupId

- ea: `0x1ef80`
- end: `0x1ef9f`
- name: `System.Deployment.Application.SubscriptionState::get_PKTGroupId`
- size: `31`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0xe080`
- `0x1f9c0`

## callees

- `0xda40`
- `0xdc90`

## string_xrefs

- `0x1ef92`: `publicKeyToken`

## pseudocode

```c

```

## disassembly

```asm
0x1ef80  ldarg.0
0x1ef81  ldfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::_subId
0x1ef86  callvirt instance object System.Deployment.Application.DefinitionIdentity::Clone()
0x1ef8b  castclass System.Deployment.Application.DefinitionIdentity
0x1ef90  stloc.0
0x1ef91  ldloc.0
0x1ef92  ldstr    aPublickeytoken// "publicKeyToken"
0x1ef97  ldnull
0x1ef98  callvirt instance void System.Deployment.Application.DefinitionIdentity::set_Item(string name, string value)
0x1ef9d  ldloc.0
0x1ef9e  ret
```
