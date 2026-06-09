# InObject::WriteNonPositionalParameterMember

- ea: `0x28630`
- end: `0x28732`
- name: `InObject::WriteNonPositionalParameterMember`
- size: `258`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: ``

## callers

- `0x28780`
- `0x28800`

## callees

- `0x9f10`
- `0xa3f0`
- `0xa4c0`
- `0xa590`
- `0xa6c0`
- `0xa6e0`
- `0xd070`
- `0xd110`
- `0xd130`
- `0xf950`
- `0x28380`
- `0x284e0`
- `0x28630`
- `0x289d0`

## pseudocode

```c

```

## disassembly

```asm
0x28630  ldarg.2
0x28631  call     bool System.Xaml.XamlXmlWriter::IsImplicit(class System.Xaml.XamlMember xamlMember)
0x28636  brtrue.s loc_2865A
0x28638  ldarg.2
0x28639  callvirt instance bool System.Xaml.XamlMember::get_IsDirective()
0x2863e  brfalse.s loc_28662
0x28640  ldarg.2
0x28641  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_Type()
0x28646  callvirt instance bool System.Xaml.XamlType::get_IsCollection()
0x2864b  brtrue.s loc_2865A
0x2864d  ldarg.2
0x2864e  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_Type()
0x28653  callvirt instance bool System.Xaml.XamlType::get_IsDictionary()
0x28658  brfalse.s loc_28662
0x2865a  ldarg.1
0x2865b  ldc.i4.1
0x2865c  stfld    bool System.Xaml.XamlMarkupExtensionWriter::failed
0x28661  ret
0x28662  ldarg.2
0x28663  callvirt instance bool System.Xaml.XamlMember::get_IsDirective()
0x28668  brfalse.s loc_2869E
0x2866a  ldarg.1
0x2866b  ldfld    class [mscorlib]System.Text.StringBuilder System.Xaml.XamlMarkupExtensionWriter::sb
0x28670  ldarg.0
0x28671  callvirt instance string InObject::get_Delimiter()
0x28676  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2867b  pop
0x2867c  ldarg.0
0x2867d  ldarg.1
0x2867e  ldarg.1
0x2867f  ldarg.2
0x28680  callvirt instance string System.Xaml.XamlMarkupExtensionWriter::LookupPrefix(class System.Xaml.XamlMember property)
0x28685  call     instance void WriterState::WritePrefix(class System.Xaml.XamlMarkupExtensionWriter writer, string prefix)
0x2868a  ldarg.1
0x2868b  ldfld    class [mscorlib]System.Text.StringBuilder System.Xaml.XamlMarkupExtensionWriter::sb
0x28690  ldarg.2
0x28691  callvirt instance string System.Xaml.XamlMember::get_Name()
0x28696  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2869b  pop
0x2869c  br.s     loc_28715
0x2869e  ldarg.2
0x2869f  callvirt instance bool System.Xaml.XamlMember::get_IsAttachable()
0x286a4  brfalse.s loc_286F1
0x286a6  ldarg.1
0x286a7  ldfld    class [mscorlib]System.Text.StringBuilder System.Xaml.XamlMarkupExtensionWriter::sb
0x286ac  ldarg.0
0x286ad  callvirt instance string InObject::get_Delimiter()
0x286b2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x286b7  pop
0x286b8  ldarg.0
0x286b9  ldarg.1
0x286ba  ldarg.1
0x286bb  ldarg.2
0x286bc  callvirt instance string System.Xaml.XamlMarkupExtensionWriter::LookupPrefix(class System.Xaml.XamlMember property)
0x286c1  call     instance void WriterState::WritePrefix(class System.Xaml.XamlMarkupExtensionWriter writer, string prefix)
0x286c6  ldarg.2
0x286c7  callvirt instance class System.Xaml.XamlType System.Xaml.XamlMember::get_DeclaringType()
0x286cc  callvirt instance string System.Xaml.XamlType::get_Name()
0x286d1  ldstr    asc_37256// "."
0x286d6  ldarg.2
0x286d7  callvirt instance string System.Xaml.XamlMember::get_Name()
0x286dc  call     string [mscorlib]System.String::Concat(string, string, string)
0x286e1  stloc.0
0x286e2  ldarg.1
0x286e3  ldfld    class [mscorlib]System.Text.StringBuilder System.Xaml.XamlMarkupExtensionWriter::sb
0x286e8  ldloc.0
0x286e9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x286ee  pop
0x286ef  br.s     loc_28715
0x286f1  ldarg.1
0x286f2  ldfld    class [mscorlib]System.Text.StringBuilder System.Xaml.XamlMarkupExtensionWriter::sb
0x286f7  ldarg.0
0x286f8  callvirt instance string InObject::get_Delimiter()
0x286fd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x28702  pop
0x28703  ldarg.1
0x28704  ldfld    class [mscorlib]System.Text.StringBuilder System.Xaml.XamlMarkupExtensionWriter::sb
0x28709  ldarg.2
0x2870a  callvirt instance string System.Xaml.XamlMember::get_Name()
0x2870f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x28714  pop
0x28715  ldarg.1
0x28716  ldfld    class [mscorlib]System.Text.StringBuilder System.Xaml.XamlMarkupExtensionWriter::sb
0x2871b  ldstr    asc_39626// "="
0x28720  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x28725  pop
0x28726  ldarg.1
0x28727  call     class WriterState InMember::get_State()
0x2872c  stfld    class WriterState System.Xaml.XamlMarkupExtensionWriter::currentState
0x28731  ret
```
