# System.Net.Http.Formatting.XmlMediaTypeFormatter::RemoveSerializer

- ea: `0x91f0`
- end: `0x9213`
- name: `System.Net.Http.Formatting.XmlMediaTypeFormatter::RemoveSerializer`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x91f0`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x91f0  ldarg.1
0x91f1  ldnull
0x91f2  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x91f7  brfalse.s loc_9204
0x91f9  ldstr    aType// "type"
0x91fe  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x9203  throw
0x9204  ldarg.0
0x9205  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, object> System.Net.Http.Formatting.XmlMediaTypeFormatter::_serializerCache
0x920a  ldarg.1
0x920b  ldloca.s 0
0x920d  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, object>::TryRemove(var<u1>, !!T0)
0x9212  ret
```
