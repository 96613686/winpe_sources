# Microsoft.BIServer.Configuration.RegistryStoreMemory::DeleteValue

- ea: `0x28f0`
- end: `0x2915`
- name: `Microsoft.BIServer.Configuration.RegistryStoreMemory::DeleteValue`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2870`
- `0x28f0`

## pseudocode

```c

```

## disassembly

```asm
0x28f0  ldarg.0
0x28f1  ldarg.1
0x28f2  ldarg.2
0x28f3  call     instance string Microsoft.BIServer.Configuration.RegistryStoreMemory::GetKey(string parent, string keyName)
0x28f8  stloc.0
0x28f9  ldarg.0
0x28fa  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.BIServer.Configuration.RegistryStoreMemory::_items
0x28ff  ldloc.0
0x2900  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x2905  brfalse.s loc_2914
0x2907  ldarg.0
0x2908  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.BIServer.Configuration.RegistryStoreMemory::_items
0x290d  ldloc.0
0x290e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Remove(var<u1>)
0x2913  pop
0x2914  ret
```
