# WriterState::WriteMemberAsAttribute

- ea: `0x2ceb0`
- end: `0x2cf59`
- name: `WriterState::WriteMemberAsAttribute`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x2dd40`

## callees

- `0xa3f0`
- `0xa4c0`
- `0xa6c0`
- `0xa6e0`
- `0xa6f0`
- `0xef20`
- `0xfbf0`
- `0x10110`
- `0x2cb10`
- `0x2cb30`
- `0x2ceb0`
- `0x2cf90`

## pseudocode

```c

```

## disassembly

```asm
0x2ceb0  ldarg.0
0x2ceb1  ldfld    class [System]System.Collections.Generic.Stack`1<class Frame> System.Xaml.XamlXmlWriter::namespaceScopes
0x2ceb6  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class Frame>::Peek()
0x2cebb  stloc.0
0x2cebc  ldloc.0
0x2cebd  callvirt instance class System.Xaml.XamlType Frame::get_Type()
0x2cec2  stloc.1
0x2cec3  ldloc.0
0x2cec4  callvirt instance class System.Xaml.XamlMember Frame::get_Member()
0x2cec9  stloc.2
0x2ceca  ldloc.2
0x2cecb  callvirt instance string System.Xaml.XamlMember::get_Name()
0x2ced0  stloc.3
0x2ced1  ldloc.2
0x2ced2  callvirt instance bool System.Xaml.XamlMember::get_IsDirective()
0x2ced7  brfalse.s loc_2CEF5
0x2ced9  ldarg.0
0x2ceda  ldloc.2
0x2cedb  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> System.Xaml.XamlMember::GetXamlNamespaces()
0x2cee0  ldloca.s 4
0x2cee2  callvirt instance string System.Xaml.XamlXmlWriter::FindPrefix(class [mscorlib]System.Collections.Generic.IList`1<string> namespaces, [out] string& chosenNamespace)
0x2cee7  stloc.s  5
0x2cee9  ldarg.0
0x2ceea  ldloc.s  5
0x2ceec  ldloc.3
0x2ceed  ldloc.s  4
0x2ceef  call     void WriterState::WriteStartAttribute(class System.Xaml.XamlXmlWriter writer, string prefix, string local, string ns)
0x2cef4  ret
0x2cef5  ldloc.2
0x2cef6  callvirt instance bool System.Xaml.XamlMember::get_IsAttachable()
0x2cefb  brfalse.s loc_2CF4C
0x2cefd  ldarg.0
0x2cefe  ldloc.2
0x2ceff  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> System.Xaml.XamlMember::GetXamlNamespaces()
0x2cf04  ldloca.s 6
0x2cf06  callvirt instance string System.Xaml.XamlXmlWriter::FindPrefix(class [mscorlib]System.Collections.Generic.IList`1<string> namespaces, [out] string& chosenNamespace)
0x2cf0b  stloc.s  7
0x2cf0d  ldloc.2
0x2cf0e  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_DeclaringType()
0x2cf13  ldloc.1
0x2cf14  call     bool System.Xaml.XamlType::op_Equality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x2cf19  brfalse.s loc_2CF24
0x2cf1b  ldloc.2
0x2cf1c  callvirt instance string System.Xaml.XamlMember::get_Name()
0x2cf21  stloc.3
0x2cf22  br.s     loc_2CF40
0x2cf24  ldloc.2
0x2cf25  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_DeclaringType()
0x2cf2a  call     string System.Xaml.XamlXmlWriter::GetTypeName(class System.Xaml.XamlType type)
0x2cf2f  ldstr    asc_37256// "."
0x2cf34  ldloc.2
0x2cf35  callvirt instance string System.Xaml.XamlMember::get_Name()
0x2cf3a  call     string [mscorlib]System.String::Concat(string, string, string)
0x2cf3f  stloc.3
0x2cf40  ldarg.0
0x2cf41  ldloc.s  7
0x2cf43  ldloc.3
0x2cf44  ldloc.s  6
0x2cf46  call     void WriterState::WriteStartAttribute(class System.Xaml.XamlXmlWriter writer, string prefix, string local, string ns)
0x2cf4b  ret
0x2cf4c  ldarg.0
0x2cf4d  ldfld    class [System.Xml]System.Xml.XmlWriter System.Xaml.XamlXmlWriter::output
0x2cf52  ldloc.3
0x2cf53  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartAttribute(string)
0x2cf58  ret
```
