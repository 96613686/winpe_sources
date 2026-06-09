# System.Net.Http.Formatting.XmlMediaTypeFormatter::SetSerializerInternal

- ea: `0x9660`
- end: `0x968d`
- name: `System.Net.Http.Formatting.XmlMediaTypeFormatter::SetSerializerInternal`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x9630`

## callees

- `0xd810`

## pseudocode

```c

```

## disassembly

```asm
0x9660  newobj   instance void <>c__DisplayClass44_0::.ctor()
0x9665  stloc.0
0x9666  ldloc.0
0x9667  ldarg.2
0x9668  stfld    object <>c__DisplayClass44_0::serializer
0x966d  ldarg.0
0x966e  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, object> System.Net.Http.Formatting.XmlMediaTypeFormatter::_serializerCache
0x9673  ldarg.1
0x9674  ldloc.0
0x9675  ldfld    object <>c__DisplayClass44_0::serializer
0x967a  ldloc.0
0x967b  ldftn    instance object <>c__DisplayClass44_0::<SetSerializerInternal>b__0(class [mscorlib]System.Type key, object value)
0x9681  newobj   instance void class [mscorlib]System.Func`3<class [mscorlib]System.Type, object, object>::.ctor(object, native int)
0x9686  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Type, object>::AddOrUpdate(void, var<u1>, !!T0)
0x968b  pop
0x968c  ret
```
