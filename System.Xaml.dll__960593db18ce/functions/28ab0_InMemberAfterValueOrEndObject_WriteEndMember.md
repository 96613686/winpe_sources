# InMemberAfterValueOrEndObject::WriteEndMember

- ea: `0x28ab0`
- end: `0x28afe`
- name: `InMemberAfterValueOrEndObject::WriteEndMember`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x11f20`
- `0x28230`
- `0x287e0`
- `0x28ab0`

## string_xrefs

- `0x28abd`: `XamlMarkupExtensionWriterInputInvalid`
- `0x28ae2`: `XamlMarkupExtensionWriterInputInvalid`

## pseudocode

```c

```

## disassembly

```asm
0x28ab0  ldarg.1
0x28ab1  ldfld    class [System]System.Collections.Generic.Stack`1<class Node> System.Xaml.XamlMarkupExtensionWriter::nodes
0x28ab6  callvirt instance int32 class [System]System.Collections.Generic.Stack`1<class Node>::get_Count()
0x28abb  brtrue.s loc_28ACD
0x28abd  ldstr    aXamlmarkupexte_1// "XamlMarkupExtensionWriterInputInvalid"
0x28ac2  call     string System.Xaml.SR::Get(string id)
0x28ac7  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x28acc  throw
0x28acd  ldarg.1
0x28ace  ldfld    class [System]System.Collections.Generic.Stack`1<class Node> System.Xaml.XamlMarkupExtensionWriter::nodes
0x28ad3  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Node>::Pop()
0x28ad8  stloc.0
0x28ad9  ldloc.0
0x28ada  callvirt instance valuetype System.Xaml.XamlNodeType Node::get_NodeType()
0x28adf  ldc.i4.4
0x28ae0  beq.s    loc_28AF2
0x28ae2  ldstr    aXamlmarkupexte_1// "XamlMarkupExtensionWriterInputInvalid"
0x28ae7  call     string System.Xaml.SR::Get(string id)
0x28aec  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x28af1  throw
0x28af2  ldarg.1
0x28af3  call     class WriterState InObjectAfterMember::get_State()
0x28af8  stfld    class WriterState System.Xaml.XamlMarkupExtensionWriter::currentState
0x28afd  ret
```
