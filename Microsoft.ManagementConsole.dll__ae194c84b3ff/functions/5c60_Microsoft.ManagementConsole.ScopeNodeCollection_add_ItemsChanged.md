# Microsoft.ManagementConsole.ScopeNodeCollection::add_ItemsChanged

- ea: `0x5c60`
- end: `0x5c78`
- name: `Microsoft.ManagementConsole.ScopeNodeCollection::add_ItemsChanged`
- size: `24`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1230`
- `0x4110`

## pseudocode

```c

```

## disassembly

```asm
0x5c60  ldarg.0
0x5c61  ldarg.0
0x5c62  ldfld    class ScopeNodeCollectionEventHandler Microsoft.ManagementConsole.ScopeNodeCollection::ItemsChanged
0x5c67  ldarg.1
0x5c68  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Combine(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x5c6d  castclass ScopeNodeCollectionEventHandler
0x5c72  stfld    class ScopeNodeCollectionEventHandler Microsoft.ManagementConsole.ScopeNodeCollection::ItemsChanged
0x5c77  ret
```
