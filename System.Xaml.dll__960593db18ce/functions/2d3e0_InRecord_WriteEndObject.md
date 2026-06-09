# InRecord::WriteEndObject

- ea: `0x2d3e0`
- end: `0x2d45b`
- name: `InRecord::WriteEndObject`
- size: `123`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0xf6b0`
- `0x11f50`
- `0x2cb70`
- `0x2cb90`
- `0x2d190`
- `0x2d3e0`
- `0x2dc70`

## string_xrefs

- `0x2d40b`: `WriteEndObject`
- `0x2d3fe`: `XamlXmlWriterWriteNotSupportedInCurrentState`

## pseudocode

```c

```

## disassembly

```asm
0x2d3e0  ldarg.1
0x2d3e1  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0x2d3e6  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Frame>::Pop()
0x2d3eb  stloc.0
0x2d3ec  ldloc.0
0x2d3ed  callvirt instance valuetype System.Xaml.XamlNodeType Frame::get_AllocatingNodeType()
0x2d3f2  ldc.i4.1
0x2d3f3  beq.s    loc_2D41C
0x2d3f5  ldloc.0
0x2d3f6  callvirt instance valuetype System.Xaml.XamlNodeType Frame::get_AllocatingNodeType()
0x2d3fb  ldc.i4.2
0x2d3fc  beq.s    loc_2D41C
0x2d3fe  ldstr    aXamlxmlwriterw// "XamlXmlWriterWriteNotSupportedInCurrent"...
0x2d403  ldc.i4.1
0x2d404  newarr   [mscorlib]System.Object
0x2d409  dup
0x2d40a  ldc.i4.0
0x2d40b  ldstr    aWriteendobject// "WriteEndObject"
0x2d410  stelem.ref
0x2d411  call     string System.Xaml.SR::Get(string id, object[] args)
0x2d416  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d41b  throw
0x2d41c  ldloc.0
0x2d41d  callvirt instance bool Frame::get_IsObjectFromMember()
0x2d422  brtrue.s loc_2D42F
0x2d424  ldarg.1
0x2d425  ldfld    class [System.Xml]System.Xml.XmlWriter System.Xaml.XamlXmlWriter::output
0x2d42a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x2d42f  ldarg.1
0x2d430  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0x2d435  callvirt instance int32 class [System]System.Collections.Generic.Stack`1<class Frame>::get_Count()
0x2d43a  ldc.i4.0
0x2d43b  ble.s    loc_2D449
0x2d43d  ldarg.1
0x2d43e  call     class WriterState InMemberAfterEndObject::get_State()
0x2d443  stfld    class WriterState System.Xaml.XamlXmlWriter::currentState
0x2d448  ret
0x2d449  ldarg.1
0x2d44a  callvirt instance void System.Xaml.XamlXmlWriter::Flush()
0x2d44f  ldarg.1
0x2d450  call     class WriterState End::get_State()
0x2d455  stfld    class WriterState System.Xaml.XamlXmlWriter::currentState
0x2d45a  ret
```
