# Microsoft.ManagementConsole.ScopeNodeCollection::ItemChanged

- ea: `0x5b20`
- end: `0x5b47`
- name: `Microsoft.ManagementConsole.ScopeNodeCollection::ItemChanged`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x5c40`

## pseudocode

```c

```

## disassembly

```asm
0x5b20  ldarg.0
0x5b21  call     instance class [mscorlib]System.Collections.IList [mscorlib]System.Collections.CollectionBase::get_List()
0x5b26  ldarg.1
0x5b27  callvirt instance int32 [mscorlib]System.Collections.IList::IndexOf(object)
0x5b2c  stloc.0
0x5b2d  ldarg.0
0x5b2e  ldloc.0
0x5b2f  ldc.i4.1
0x5b30  newarr   Microsoft.ManagementConsole.ScopeNode
0x5b35  stloc.1
0x5b36  ldloc.1
0x5b37  ldc.i4.0
0x5b38  ldarg.1
0x5b39  castclass Microsoft.ManagementConsole.ScopeNode
0x5b3e  stelem.ref
0x5b3f  ldloc.1
0x5b40  ldc.i4.2
0x5b41  call     instance void Microsoft.ManagementConsole.ScopeNodeCollection::Notify(int32 index, class Microsoft.ManagementConsole.ScopeNode[] items, valuetype Microsoft.ManagementConsole.ScopeNodeCollectionChangeType action)
0x5b46  ret
```
