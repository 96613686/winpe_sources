# WriterState::WriteMemberAsElement

- ea: `0x2ce10`
- end: `0x2cea7`
- name: `WriterState::WriteMemberAsElement`
- size: `151`
- prototype: ``
- caller_count: `8`
- callee_count: `11`
- tags: ``

## callers

- `0x2d240`
- `0x2d4c0`
- `0x2ddf0`
- `0x2de50`
- `0x2df10`
- `0x2df70`
- `0x2e020`
- `0x2e250`

## callees

- `0xa3f0`
- `0xa4c0`
- `0xa6c0`
- `0xa6e0`
- `0xa6f0`
- `0xd6b0`
- `0xfbf0`
- `0x10110`
- `0x2cb10`
- `0x2cb30`
- `0x2ce10`

## pseudocode

```c

```

## disassembly

```asm
0x2ce10  ldarg.0
0x2ce11  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0x2ce16  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Frame>::Peek()
0x2ce1b  stloc.0
0x2ce1c  ldloc.0
0x2ce1d  callvirt instance class System.Xaml.XamlType Frame::get_Type()
0x2ce22  stloc.1
0x2ce23  ldloc.0
0x2ce24  callvirt instance class System.Xaml.XamlMember Frame::get_Member()
0x2ce29  stloc.2
0x2ce2a  ldloc.2
0x2ce2b  callvirt instance bool System.Xaml.XamlMember::get_IsAttachable()
0x2ce30  brtrue.s loc_2CE35
0x2ce32  ldloc.1
0x2ce33  br.s     loc_2CE3B
0x2ce35  ldloc.2
0x2ce36  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_DeclaringType()
0x2ce3b  stloc.s  4
0x2ce3d  ldloc.2
0x2ce3e  callvirt instance bool System.Xaml.XamlMember::get_IsAttachable()
0x2ce43  brtrue.s loc_2CE5D
0x2ce45  ldloc.2
0x2ce46  callvirt instance bool System.Xaml.XamlMember::get_IsDirective()
0x2ce4b  brtrue.s loc_2CE5D
0x2ce4d  ldarg.0
0x2ce4e  ldloc.1
0x2ce4f  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> System.Xaml.XamlType::GetXamlNamespaces()
0x2ce54  ldloca.s 3
0x2ce56  callvirt instance string System.Xaml.XamlXmlWriter::FindPrefix(class [mscorlib]System.Collections.Generic.IList`1<string> namespaces, [out] string& chosenNamespace)
0x2ce5b  br.s     loc_2CE6B
0x2ce5d  ldarg.0
0x2ce5e  ldloc.2
0x2ce5f  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> System.Xaml.XamlMember::GetXamlNamespaces()
0x2ce64  ldloca.s 3
0x2ce66  callvirt instance string System.Xaml.XamlXmlWriter::FindPrefix(class [mscorlib]System.Collections.Generic.IList`1<string> namespaces, [out] string& chosenNamespace)
0x2ce6b  stloc.s  5
0x2ce6d  ldloc.2
0x2ce6e  callvirt instance bool System.Xaml.XamlMember::get_IsDirective()
0x2ce73  brtrue.s loc_2CE8E
0x2ce75  ldloc.s  4
0x2ce77  call     string System.Xaml.XamlXmlWriter::GetTypeName(class System.Xaml.XamlType type)
0x2ce7c  ldstr    asc_37256// "."
0x2ce81  ldloc.2
0x2ce82  callvirt instance string System.Xaml.XamlMember::get_Name()
0x2ce87  call     string [mscorlib]System.String::Concat(string, string, string)
0x2ce8c  br.s     loc_2CE94
0x2ce8e  ldloc.2
0x2ce8f  callvirt instance string System.Xaml.XamlMember::get_Name()
0x2ce94  stloc.s  6
0x2ce96  ldarg.0
0x2ce97  ldfld    class [System.Xml]System.Xml.XmlWriter System.Xaml.XamlXmlWriter::output
0x2ce9c  ldloc.s  5
0x2ce9e  ldloc.s  6
0x2cea0  ldloc.3
0x2cea1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string, string)
0x2cea6  ret
```
