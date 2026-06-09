# System.Xaml.XamlXmlWriter::WriteDeferredNamespaces

- ea: `0xfdf0`
- end: `0xfe7b`
- name: `System.Xaml.XamlXmlWriter::WriteDeferredNamespaces`
- size: `139`
- prototype: ``
- caller_count: `12`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x2d240`
- `0x2d4a0`
- `0x2d4c0`
- `0x2d680`
- `0x2ddf0`
- `0x2de50`
- `0x2df10`
- `0x2df70`
- `0x2e100`
- `0x2e140`
- `0x2e1d0`
- `0x2e250`

## callees

- `0xfdf0`
- `0x2cb70`
- `0x2ccb0`

## string_xrefs

- `0xfe48`: `xmlns`

## pseudocode

```c

```

## disassembly

```asm
0xfdf0  ldarg.0
0xfdf1  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0xfdf6  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Frame>::Peek()
0xfdfb  stloc.0
0xfdfc  ldloc.0
0xfdfd  callvirt instance valuetype System.Xaml.XamlNodeType Frame::get_AllocatingNodeType()
0xfe02  ldarg.1
0xfe03  beq.s    loc_FE29
0xfe05  ldarg.0
0xfe06  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0xfe0b  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Frame>::Pop()
0xfe10  stloc.2
0xfe11  ldarg.0
0xfe12  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0xfe17  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Frame>::Peek()
0xfe1c  stloc.0
0xfe1d  ldarg.0
0xfe1e  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0xfe23  ldloc.2
0xfe24  callvirt instance void class [System]System.Collections.Generic.Stack`1<class Frame>::Push(var<u1>)
0xfe29  ldloc.0
0xfe2a  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>> Frame::GetSortedPrefixMap()
0xfe2f  stloc.1
0xfe30  ldloc.1
0xfe31  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::GetEnumerator()
0xfe36  stloc.3
0xfe37  br.s     loc_FE61
0xfe39  ldloca.s 3
0xfe3b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::get_Current()
0xfe40  stloc.s  4
0xfe42  ldarg.0
0xfe43  ldfld    class [System.Xml]System.Xml.XmlWriter System.Xaml.XamlXmlWriter::output
0xfe48  ldstr    aXmlns// "xmlns"
0xfe4d  ldloca.s 4
0xfe4f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0xfe54  ldnull
0xfe55  ldloca.s 4
0xfe57  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0xfe5c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0xfe61  ldloca.s 3
0xfe63  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::MoveNext()
0xfe68  brtrue.s loc_FE39
0xfe6a  leave.s  loc_FE7A
0xfe6c  ldloca.s 3
0xfe6e  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>
0xfe74  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xfe79  endfinally
0xfe7a  ret
```
