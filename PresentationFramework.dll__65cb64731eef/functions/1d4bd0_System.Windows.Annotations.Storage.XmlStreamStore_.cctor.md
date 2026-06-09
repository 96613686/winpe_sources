# System.Windows.Annotations.Storage.XmlStreamStore::.cctor

- ea: `0x1d4bd0`
- end: `0x1d4c2f`
- name: `System.Windows.Annotations.Storage.XmlStreamStore::.cctor`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2474b0`

## string_xrefs

- `0x1d4c1e`: `http://schemas.microsoft.com/winfx/2006/xaml/presentation`
- `0x1d4c09`: `http://schemas.microsoft.com/windows/annotations/2003/11/base`
- `0x1d4bf4`: `http://schemas.microsoft.com/windows/annotations/2003/11/core`

## pseudocode

```c

```

## disassembly

```asm
0x1d4bd0  ldtoken  System.Windows.Annotations.Annotation
0x1d4bd5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1d4bda  newobj   instance void MS.Internal.Annotations.Serializer::.ctor(class [mscorlib]System.Type type)
0x1d4bdf  stsfld   class MS.Internal.Annotations.Serializer System.Windows.Annotations.Storage.XmlStreamStore::_serializer
0x1d4be4  ldc.i4.6
0x1d4be5  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri>>::.ctor(int32)
0x1d4bea  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri>> System.Windows.Annotations.Storage.XmlStreamStore::_predefinedNamespaces
0x1d4bef  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri>> System.Windows.Annotations.Storage.XmlStreamStore::_predefinedNamespaces
0x1d4bf4  ldstr    aHttpSchemasMic_13// "http://schemas.microsoft.com/windows/an"...
0x1d4bf9  newobj   instance void [System]System.Uri::.ctor(string)
0x1d4bfe  ldnull
0x1d4bff  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri>>::Add(var<u1>, !!T0)
0x1d4c04  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri>> System.Windows.Annotations.Storage.XmlStreamStore::_predefinedNamespaces
0x1d4c09  ldstr    aHttpSchemasMic_12// "http://schemas.microsoft.com/windows/an"...
0x1d4c0e  newobj   instance void [System]System.Uri::.ctor(string)
0x1d4c13  ldnull
0x1d4c14  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri>>::Add(var<u1>, !!T0)
0x1d4c19  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri>> System.Windows.Annotations.Storage.XmlStreamStore::_predefinedNamespaces
0x1d4c1e  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/winfx/2006"...
0x1d4c23  newobj   instance void [System]System.Uri::.ctor(string)
0x1d4c28  ldnull
0x1d4c29  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri>>::Add(var<u1>, !!T0)
0x1d4c2e  ret
```
