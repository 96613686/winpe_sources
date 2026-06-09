# Microsoft.BIServer.Configuration.RegistryStoreMemory::SetTypeHelper

- ea: `0x2930`
- end: `0x2963`
- name: `Microsoft.BIServer.Configuration.RegistryStoreMemory::SetTypeHelper`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2920`
- `0x2970`

## callees

- `0x2870`
- `0x2930`

## pseudocode

```c

```

## disassembly

```asm
0x2930  ldarg.0
0x2931  ldarg.1
0x2932  ldarg.2
0x2933  call     instance string Microsoft.BIServer.Configuration.RegistryStoreMemory::GetKey(string parent, string keyName)
0x2938  stloc.0
0x2939  ldarg.0
0x293a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.BIServer.Configuration.RegistryStoreMemory::_items
0x293f  ldloc.0
0x2940  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x2945  brtrue.s loc_2955
0x2947  ldarg.0
0x2948  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.BIServer.Configuration.RegistryStoreMemory::_items
0x294d  ldloc.0
0x294e  ldarg.3
0x294f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2954  ret
0x2955  ldarg.0
0x2956  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.BIServer.Configuration.RegistryStoreMemory::_items
0x295b  ldloc.0
0x295c  ldarg.3
0x295d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2962  ret
```
