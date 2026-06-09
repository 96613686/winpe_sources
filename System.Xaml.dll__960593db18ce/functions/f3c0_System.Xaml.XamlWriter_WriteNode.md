# System.Xaml.XamlWriter::WriteNode

- ea: `0xf3c0`
- end: `0xf457`
- name: `System.Xaml.XamlWriter::WriteNode`
- size: `151`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: ``

## callers

- `0x7370`
- `0xcc00`

## callees

- `0xb320`
- `0xb340`
- `0xb350`
- `0xb360`
- `0xb370`
- `0xf340`
- `0xf350`
- `0xf360`
- `0xf370`
- `0xf380`
- `0xf390`
- `0xf3a0`
- `0xf3c0`
- `0x11f20`

## string_xrefs

- `0xf3c3`: `reader`

## pseudocode

```c

```

## disassembly

```asm
0xf3c0  ldarg.1
0xf3c1  brtrue.s loc_F3CE
0xf3c3  ldstr    aReader// "reader"
0xf3c8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf3cd  throw
0xf3ce  ldarg.1
0xf3cf  callvirt instance valuetype System.Xaml.XamlNodeType System.Xaml.XamlReader::get_NodeType()
0xf3d4  stloc.0
0xf3d5  ldloc.0
0xf3d6  switch   loc_F456, loc_F40A, loc_F417, loc_F41E, loc_F425, loc_F432, loc_F439, loc_F3FD
0xf3fb  br.s     loc_F446
0xf3fd  ldarg.0
0xf3fe  ldarg.1
0xf3ff  callvirt instance class System.Xaml.NamespaceDeclaration System.Xaml.XamlReader::get_Namespace()
0xf404  callvirt instance void System.Xaml.XamlWriter::WriteNamespace(class System.Xaml.NamespaceDeclaration namespaceDeclaration)
0xf409  ret
0xf40a  ldarg.0
0xf40b  ldarg.1
0xf40c  callvirt instance class System.Xaml.XamlType System.Xaml.XamlReader::get_Type()
0xf411  callvirt instance void System.Xaml.XamlWriter::WriteStartObject(class System.Xaml.XamlType type)
0xf416  ret
0xf417  ldarg.0
0xf418  callvirt instance void System.Xaml.XamlWriter::WriteGetObject()
0xf41d  ret
0xf41e  ldarg.0
0xf41f  callvirt instance void System.Xaml.XamlWriter::WriteEndObject()
0xf424  ret
0xf425  ldarg.0
0xf426  ldarg.1
0xf427  callvirt instance class System.Xaml.XamlMember System.Xaml.XamlReader::get_Member()
0xf42c  callvirt instance void System.Xaml.XamlWriter::WriteStartMember(class System.Xaml.XamlMember xamlMember)
0xf431  ret
0xf432  ldarg.0
0xf433  callvirt instance void System.Xaml.XamlWriter::WriteEndMember()
0xf438  ret
0xf439  ldarg.0
0xf43a  ldarg.1
0xf43b  callvirt instance object System.Xaml.XamlReader::get_Value()
0xf440  callvirt instance void System.Xaml.XamlWriter::WriteValue(object value)
0xf445  ret
0xf446  ldstr    aMissingcasexam// "MissingCaseXamlNodes"
0xf44b  call     string System.Xaml.SR::Get(string id)
0xf450  newobj   instance void [mscorlib]System.NotImplementedException::.ctor(string)
0xf455  throw
0xf456  ret
```
