# InObject::WriteEndObject

- ea: `0x284f0`
- end: `0x285ab`
- name: `InObject::WriteEndObject`
- size: `187`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x8b80`
- `0xb280`
- `0x11f20`
- `0x281f0`
- `0x28230`
- `0x28430`
- `0x284f0`
- `0x28930`
- `0x28aa0`

## string_xrefs

- `0x284fd`: `XamlMarkupExtensionWriterInputInvalid`
- `0x28522`: `XamlMarkupExtensionWriterInputInvalid`
- `0x28571`: `XamlMarkupExtensionWriterInputInvalid`

## pseudocode

```c

```

## disassembly

```asm
0x284f0  ldarg.1
0x284f1  ldfld    class [System]System.Collections.Generic.Stack`1<class Node> System.Xaml.XamlMarkupExtensionWriter::nodes
0x284f6  callvirt instance int32 class [System]System.Collections.Generic.Stack`1<class Node>::get_Count()
0x284fb  brtrue.s loc_2850D
0x284fd  ldstr    aXamlmarkupexte_1// "XamlMarkupExtensionWriterInputInvalid"
0x28502  call     string System.Xaml.SR::Get(string id)
0x28507  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2850c  throw
0x2850d  ldarg.1
0x2850e  ldfld    class [System]System.Collections.Generic.Stack`1<class Node> System.Xaml.XamlMarkupExtensionWriter::nodes
0x28513  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Node>::Pop()
0x28518  stloc.0
0x28519  ldloc.0
0x2851a  callvirt instance valuetype System.Xaml.XamlNodeType Node::get_NodeType()
0x2851f  ldc.i4.1
0x28520  beq.s    loc_28532
0x28522  ldstr    aXamlmarkupexte_1// "XamlMarkupExtensionWriterInputInvalid"
0x28527  call     string System.Xaml.SR::Get(string id)
0x2852c  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x28531  throw
0x28532  ldarg.1
0x28533  ldfld    class [mscorlib]System.Text.StringBuilder System.Xaml.XamlMarkupExtensionWriter::sb
0x28538  ldstr    asc_3809E// "}"
0x2853d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x28542  pop
0x28543  ldarg.1
0x28544  ldfld    class [System]System.Collections.Generic.Stack`1<class Node> System.Xaml.XamlMarkupExtensionWriter::nodes
0x28549  callvirt instance int32 class [System]System.Collections.Generic.Stack`1<class Node>::get_Count()
0x2854e  brtrue.s loc_2855C
0x28550  ldarg.1
0x28551  call     class WriterState Start::get_State()
0x28556  stfld    class WriterState System.Xaml.XamlMarkupExtensionWriter::currentState
0x2855b  ret
0x2855c  ldarg.1
0x2855d  ldfld    class [System]System.Collections.Generic.Stack`1<class Node> System.Xaml.XamlMarkupExtensionWriter::nodes
0x28562  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Node>::Peek()
0x28567  stloc.1
0x28568  ldloc.1
0x28569  callvirt instance valuetype System.Xaml.XamlNodeType Node::get_NodeType()
0x2856e  ldc.i4.4
0x2856f  beq.s    loc_28581
0x28571  ldstr    aXamlmarkupexte_1// "XamlMarkupExtensionWriterInputInvalid"
0x28576  call     string System.Xaml.SR::Get(string id)
0x2857b  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x28580  throw
0x28581  ldloc.1
0x28582  callvirt instance class System.Xaml.XamlMember Node::get_XamlProperty()
0x28587  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_PositionalParameters()
0x2858c  call     bool System.Xaml.XamlMember::op_Equality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x28591  brfalse.s loc_2859F
0x28593  ldarg.1
0x28594  call     class WriterState InPositionalParametersAfterValue::get_State()
0x28599  stfld    class WriterState System.Xaml.XamlMarkupExtensionWriter::currentState
0x2859e  ret
0x2859f  ldarg.1
0x285a0  call     class WriterState InMemberAfterValueOrEndObject::get_State()
0x285a5  stfld    class WriterState System.Xaml.XamlMarkupExtensionWriter::currentState
0x285aa  ret
```
