# InObject::UpdateStack

- ea: `0x285b0`
- end: `0x28625`
- name: `InObject::UpdateStack`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x28780`
- `0x28800`

## callees

- `0x9f50`
- `0x11f20`
- `0x28200`
- `0x28230`
- `0x28240`
- `0x28250`
- `0x28260`
- `0x28270`
- `0x285b0`

## string_xrefs

- `0x285bd`: `XamlMarkupExtensionWriterInputInvalid`
- `0x285e2`: `XamlMarkupExtensionWriterInputInvalid`

## pseudocode

```c

```

## disassembly

```asm
0x285b0  ldarg.1
0x285b1  ldfld    class [System]System.Collections.Generic.Stack`1<class Node> System.Xaml.XamlMarkupExtensionWriter::nodes
0x285b6  callvirt instance int32 class [System]System.Collections.Generic.Stack`1<class Node>::get_Count()
0x285bb  brtrue.s loc_285CD
0x285bd  ldstr    aXamlmarkupexte_1// "XamlMarkupExtensionWriterInputInvalid"
0x285c2  call     string System.Xaml.SR::Get(string id)
0x285c7  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x285cc  throw
0x285cd  ldarg.1
0x285ce  ldfld    class [System]System.Collections.Generic.Stack`1<class Node> System.Xaml.XamlMarkupExtensionWriter::nodes
0x285d3  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Node>::Peek()
0x285d8  stloc.0
0x285d9  ldloc.0
0x285da  callvirt instance valuetype System.Xaml.XamlNodeType Node::get_NodeType()
0x285df  ldc.i4.1
0x285e0  beq.s    loc_285F2
0x285e2  ldstr    aXamlmarkupexte_1// "XamlMarkupExtensionWriterInputInvalid"
0x285e7  call     string System.Xaml.SR::Get(string id)
0x285ec  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x285f1  throw
0x285f2  ldarg.1
0x285f3  ldloc.0
0x285f4  ldarg.2
0x285f5  callvirt instance void System.Xaml.XamlMarkupExtensionWriter::CheckMemberForUniqueness(class Node objectNode, class System.Xaml.XamlMember property)
0x285fa  ldarg.1
0x285fb  ldfld    class [System]System.Collections.Generic.Stack`1<class Node> System.Xaml.XamlMarkupExtensionWriter::nodes
0x28600  newobj   instance void Node::.ctor()
0x28605  dup
0x28606  ldc.i4.4
0x28607  callvirt instance void Node::set_NodeType(valuetype System.Xaml.XamlNodeType value)
0x2860c  dup
0x2860d  ldloc.0
0x2860e  callvirt instance class System.Xaml.XamlType Node::get_XamlType()
0x28613  callvirt instance void Node::set_XamlType(class System.Xaml.XamlType value)
0x28618  dup
0x28619  ldarg.2
0x2861a  callvirt instance void Node::set_XamlProperty(class System.Xaml.XamlMember value)
0x2861f  callvirt instance void class [System]System.Collections.Generic.Stack`1<class Node>::Push(var<u1>)
0x28624  ret
```
