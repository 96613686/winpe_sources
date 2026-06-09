# Microsoft.BIServer.Configuration.RegistryStoreMemory::GetValueHelper

- ea: `0x2990`
- end: `0x29b6`
- name: `Microsoft.BIServer.Configuration.RegistryStoreMemory::GetValueHelper`
- size: `38`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2980`
- `0x29c0`

## callees

- `0x2870`
- `0x2990`

## pseudocode

```c

```

## disassembly

```asm
0x2990  ldarg.0
0x2991  ldarg.1
0x2992  ldarg.2
0x2993  call     instance string Microsoft.BIServer.Configuration.RegistryStoreMemory::GetKey(string parent, string keyName)
0x2998  stloc.0
0x2999  ldarg.0
0x299a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.BIServer.Configuration.RegistryStoreMemory::_items
0x299f  ldloc.0
0x29a0  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x29a5  brfalse.s loc_29B4
0x29a7  ldarg.0
0x29a8  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.BIServer.Configuration.RegistryStoreMemory::_items
0x29ad  ldloc.0
0x29ae  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x29b3  ret
0x29b4  ldnull
0x29b5  ret
```
