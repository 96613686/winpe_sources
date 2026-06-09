# Frame::AssignNamespacePrefix

- ea: `0x2cc30`
- end: `0x2cc9b`
- name: `Frame::AssignNamespacePrefix`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0xfb40`

## callees

- `0x8860`
- `0x11f50`
- `0x2cc30`

## string_xrefs

- `0x2cc3e`: `XamlXmlWriterPrefixAlreadyDefinedInCurrentScope`
- `0x2cc66`: `XamlXmlWriterNamespaceAlreadyHasPrefixInCurrentScope`

## pseudocode

```c

```

## disassembly

```asm
0x2cc30  ldarg.0
0x2cc31  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Frame::prefixMap
0x2cc36  ldarg.2
0x2cc37  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x2cc3c  brfalse.s loc_2CC58
0x2cc3e  ldstr    aXamlxmlwriterp// "XamlXmlWriterPrefixAlreadyDefinedInCurr"...
0x2cc43  ldc.i4.1
0x2cc44  newarr   [mscorlib]System.Object
0x2cc49  dup
0x2cc4a  ldc.i4.0
0x2cc4b  ldarg.2
0x2cc4c  stelem.ref
0x2cc4d  call     string System.Xaml.SR::Get(string id, object[] args)
0x2cc52  newobj   instance void System.Xaml.XamlXmlWriterException::.ctor(string message)
0x2cc57  throw
0x2cc58  ldarg.0
0x2cc59  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Frame::namespaceMap
0x2cc5e  ldarg.1
0x2cc5f  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x2cc64  brfalse.s loc_2CC80
0x2cc66  ldstr    aXamlxmlwritern// "XamlXmlWriterNamespaceAlreadyHasPrefixI"...
0x2cc6b  ldc.i4.1
0x2cc6c  newarr   [mscorlib]System.Object
0x2cc71  dup
0x2cc72  ldc.i4.0
0x2cc73  ldarg.1
0x2cc74  stelem.ref
0x2cc75  call     string System.Xaml.SR::Get(string id, object[] args)
0x2cc7a  newobj   instance void System.Xaml.XamlXmlWriterException::.ctor(string message)
0x2cc7f  throw
0x2cc80  ldarg.0
0x2cc81  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Frame::prefixMap
0x2cc86  ldarg.2
0x2cc87  ldarg.1
0x2cc88  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x2cc8d  ldarg.0
0x2cc8e  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Frame::namespaceMap
0x2cc93  ldarg.1
0x2cc94  ldarg.2
0x2cc95  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x2cc9a  ret
```
