# System.Net.Http.Formatting.XmlMediaTypeFormatter::GetCachedSerializer

- ea: `0x9600`
- end: `0x9629`
- name: `System.Net.Http.Formatting.XmlMediaTypeFormatter::GetCachedSerializer`
- size: `41`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x9220`
- `0x9240`
- `0x9690`

## callees

- `0x9530`
- `0x9600`

## pseudocode

```c

```

## disassembly

```asm
0x9600  ldarg.0
0x9601  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, object> System.Net.Http.Formatting.XmlMediaTypeFormatter::_serializerCache
0x9606  ldarg.1
0x9607  ldloca.s 0
0x9609  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, object>::TryGetValue(var<u1>, !!T0)
0x960e  brtrue.s loc_9627
0x9610  ldarg.0
0x9611  ldarg.1
0x9612  ldarg.2
0x9613  call     instance object System.Net.Http.Formatting.XmlMediaTypeFormatter::CreateDefaultSerializer(class [mscorlib]System.Type type, bool throwOnError)
0x9618  stloc.0
0x9619  ldarg.0
0x961a  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, object> System.Net.Http.Formatting.XmlMediaTypeFormatter::_serializerCache
0x961f  ldarg.1
0x9620  ldloc.0
0x9621  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, object>::TryAdd(var<u1>, !!T0)
0x9626  pop
0x9627  ldloc.0
0x9628  ret
```
