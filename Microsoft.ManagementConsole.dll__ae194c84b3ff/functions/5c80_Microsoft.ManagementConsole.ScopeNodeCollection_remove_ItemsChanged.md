# Microsoft.ManagementConsole.ScopeNodeCollection::remove_ItemsChanged

- ea: `0x5c80`
- end: `0x5c98`
- name: `Microsoft.ManagementConsole.ScopeNodeCollection::remove_ItemsChanged`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1350`

## pseudocode

```c

```

## disassembly

```asm
0x5c80  ldarg.0
0x5c81  ldarg.0
0x5c82  ldfld    class ScopeNodeCollectionEventHandler Microsoft.ManagementConsole.ScopeNodeCollection::ItemsChanged
0x5c87  ldarg.1
0x5c88  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Remove(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x5c8d  castclass ScopeNodeCollectionEventHandler
0x5c92  stfld    class ScopeNodeCollectionEventHandler Microsoft.ManagementConsole.ScopeNodeCollection::ItemsChanged
0x5c97  ret
```
