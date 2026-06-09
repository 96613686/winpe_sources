# Microsoft.ManagementConsole.NodeSubItemDisplayNameCollection::remove_Changed

- ea: `0x5e50`
- end: `0x5e68`
- name: `Microsoft.ManagementConsole.NodeSubItemDisplayNameCollection::remove_Changed`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x5f0`

## pseudocode

```c

```

## disassembly

```asm
0x5e50  ldarg.0
0x5e51  ldarg.0
0x5e52  ldfld    class NodeSubItemDisplayNameCollectionEventHandler Microsoft.ManagementConsole.NodeSubItemDisplayNameCollection::Changed
0x5e57  ldarg.1
0x5e58  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Remove(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x5e5d  castclass NodeSubItemDisplayNameCollectionEventHandler
0x5e62  stfld    class NodeSubItemDisplayNameCollectionEventHandler Microsoft.ManagementConsole.NodeSubItemDisplayNameCollection::Changed
0x5e67  ret
```
