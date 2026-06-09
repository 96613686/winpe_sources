# Microsoft.BIServer.Configuration.RegistryStoreMemory::DeleteSubKey

- ea: `0x2880`
- end: `0x28e5`
- name: `Microsoft.BIServer.Configuration.RegistryStoreMemory::DeleteSubKey`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2880`
- `0x71d0`

## pseudocode

```c

```

## disassembly

```asm
0x2880  newobj   instance void <>c__DisplayClass2_0::.ctor()
0x2885  stloc.0
0x2886  ldloc.0
0x2887  ldarg.1
0x2888  brtrue.s loc_288D
0x288a  ldarg.2
0x288b  br.s     loc_2899
0x288d  ldarg.1
0x288e  ldstr    asc_94A6// "\\"
0x2893  ldarg.2
0x2894  call     string [mscorlib]System.String::Concat(string, string, string)
0x2899  stfld    string <>c__DisplayClass2_0::path
0x289e  ldarg.0
0x289f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.BIServer.Configuration.RegistryStoreMemory::_items
0x28a4  ldloc.0
0x28a5  ldftn    instance bool <>c__DisplayClass2_0::<DeleteSubKey>b__0(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object> kvp)
0x28ab  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>, bool>::.ctor(object, native int)
0x28b0  call     T0x2B000027
0x28b5  call     T0x2B000028
0x28ba  stloc.1
0x28bb  ldc.i4.0
0x28bc  stloc.2
0x28bd  br.s     loc_28DE
0x28bf  ldloc.1
0x28c0  ldloc.2
0x28c1  ldelem   valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>
0x28c6  stloc.3
0x28c7  ldarg.0
0x28c8  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.BIServer.Configuration.RegistryStoreMemory::_items
0x28cd  ldloca.s 3
0x28cf  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x28d4  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Remove(var<u1>)
0x28d9  pop
0x28da  ldloc.2
0x28db  ldc.i4.1
0x28dc  add
0x28dd  stloc.2
0x28de  ldloc.2
0x28df  ldloc.1
0x28e0  ldlen
0x28e1  conv.i4
0x28e2  blt.s    loc_28BF
0x28e4  ret
```
