# InPositionalParametersAfterValue::WriteEndMember

- ea: `0x28950`
- end: `0x28993`
- name: `InPositionalParametersAfterValue::WriteEndMember`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x8b80`
- `0xb2f0`
- `0x11f20`
- `0x281f0`
- `0x28230`
- `0x287e0`
- `0x28950`

## string_xrefs

- `0x28977`: `XamlMarkupExtensionWriterInputInvalid`

## pseudocode

```c

```

## disassembly

```asm
0x28950  ldarg.1
0x28951  ldfld    class [System]System.Collections.Generic.Stack`1<class Node> System.Xaml.XamlMarkupExtensionWriter::nodes
0x28956  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Node>::Pop()
0x2895b  stloc.0
0x2895c  ldloc.0
0x2895d  callvirt instance valuetype System.Xaml.XamlNodeType Node::get_NodeType()
0x28962  ldc.i4.4
0x28963  bne.un.s loc_28977
0x28965  ldloc.0
0x28966  callvirt instance class System.Xaml.XamlMember Node::get_XamlProperty()
0x2896b  call     class System.Xaml.XamlDirective System.Xaml.XamlLanguage::get_PositionalParameters()
0x28970  call     bool System.Xaml.XamlMember::op_Inequality(class System.Xaml.XamlMember xamlMember1, class System.Xaml.XamlMember xamlMember2)
0x28975  brfalse.s loc_28987
0x28977  ldstr    aXamlmarkupexte_1// "XamlMarkupExtensionWriterInputInvalid"
0x2897c  call     string System.Xaml.SR::Get(string id)
0x28981  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x28986  throw
0x28987  ldarg.1
0x28988  call     class WriterState InObjectAfterMember::get_State()
0x2898d  stfld    class WriterState System.Xaml.XamlMarkupExtensionWriter::currentState
0x28992  ret
```
