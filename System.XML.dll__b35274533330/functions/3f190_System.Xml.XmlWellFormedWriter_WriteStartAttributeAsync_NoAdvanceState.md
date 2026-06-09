# System.Xml.XmlWellFormedWriter::WriteStartAttributeAsync_NoAdvanceState

- ea: `0x3f190`
- end: `0x3f3ab`
- name: `System.Xml.XmlWellFormedWriter::WriteStartAttributeAsync_NoAdvanceState`
- size: `539`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x3f110`
- `0x111930`

## callees

- `0x3ded0`
- `0x3dfa0`
- `0x3e770`
- `0x3e7d0`
- `0x3e830`
- `0x3e890`
- `0x3e9a0`
- `0x3ec00`
- `0x3f190`
- `0x40970`
- `0x41210`
- `0x62370`

## string_xrefs

- `0x3f2e0`: `http://www.w3.org/XML/1998/namespace`
- `0x3f1a4`: `http://www.w3.org/2000/xmlns/`
- `0x3f212`: `http://www.w3.org/2000/xmlns/`
- `0x3f29a`: `http://www.w3.org/2000/xmlns/`
- `0x3f197`: `xmlns`
- `0x3f1fc`: `xmlns`
- `0x3f284`: `xmlns`
- `0x3f2ec`: `Xml_XmlPrefix`
- `0x3f21e`: `Xml_XmlnsPrefix`
- `0x3f2a6`: `Xml_XmlnsPrefix`

## pseudocode

```c

```

## disassembly

```asm
0x3f190  ldarg.1
0x3f191  brtrue.s loc_3F1C3
0x3f193  ldarg.3
0x3f194  brfalse.s loc_3F1B9
0x3f196  ldarg.2
0x3f197  ldstr    aXmlns// "xmlns"
0x3f19c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3f1a1  brfalse.s loc_3F1B0
0x3f1a3  ldarg.3
0x3f1a4  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x3f1a9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3f1ae  brtrue.s loc_3F1B9
0x3f1b0  ldarg.0
0x3f1b1  ldarg.3
0x3f1b2  callvirt instance string System.Xml.XmlWriter::LookupPrefix(string ns)
0x3f1b7  starg.s  1
0x3f1b9  ldarg.1
0x3f1ba  brtrue.s loc_3F1C3
0x3f1bc  ldsfld   string [mscorlib]System.String::Empty
0x3f1c1  starg.s  1
0x3f1c3  ldarg.3
0x3f1c4  brtrue.s loc_3F1E5
0x3f1c6  ldarg.1
0x3f1c7  brfalse.s loc_3F1DB
0x3f1c9  ldarg.1
0x3f1ca  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3f1cf  ldc.i4.0
0x3f1d0  ble.s    loc_3F1DB
0x3f1d2  ldarg.0
0x3f1d3  ldarg.1
0x3f1d4  call     instance string System.Xml.XmlWellFormedWriter::LookupNamespace(string prefix)
0x3f1d9  starg.s  3
0x3f1db  ldarg.3
0x3f1dc  brtrue.s loc_3F1E5
0x3f1de  ldsfld   string [mscorlib]System.String::Empty
0x3f1e3  starg.s  3
0x3f1e5  ldarg.1
0x3f1e6  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3f1eb  brtrue   loc_3F275
0x3f1f0  ldarg.2
0x3f1f1  ldc.i4.0
0x3f1f2  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x3f1f7  ldc.i4.s 0x78
0x3f1f9  bne.un.s loc_3F245
0x3f1fb  ldarg.2
0x3f1fc  ldstr    aXmlns// "xmlns"
0x3f201  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3f206  brfalse.s loc_3F245
0x3f208  ldarg.3
0x3f209  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3f20e  ldc.i4.0
0x3f20f  ble.s    loc_3F22E
0x3f211  ldarg.3
0x3f212  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x3f217  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x3f21c  brfalse.s loc_3F22E
0x3f21e  ldstr    aXmlXmlnsprefix// "Xml_XmlnsPrefix"
0x3f223  call     string System.Xml.Res::GetString(string name)
0x3f228  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x3f22d  throw
0x3f22e  ldarg.0
0x3f22f  ldsfld   string [mscorlib]System.String::Empty
0x3f234  stfld    string System.Xml.XmlWellFormedWriter::curDeclPrefix
0x3f239  ldarg.0
0x3f23a  ldc.i4.1
0x3f23b  call     instance void System.Xml.XmlWellFormedWriter::SetSpecialAttribute(valuetype SpecialAttribute special)
0x3f240  br       loc_3F36E
0x3f245  ldarg.3
0x3f246  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3f24b  ldc.i4.0
0x3f24c  ble      loc_3F35E
0x3f251  ldarg.0
0x3f252  ldarg.3
0x3f253  callvirt instance string System.Xml.XmlWriter::LookupPrefix(string ns)
0x3f258  starg.s  1
0x3f25a  ldarg.1
0x3f25b  brfalse.s loc_3F268
0x3f25d  ldarg.1
0x3f25e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3f263  brtrue   loc_3F35E
0x3f268  ldarg.0
0x3f269  call     instance string System.Xml.XmlWellFormedWriter::GeneratePrefix()
0x3f26e  starg.s  1
0x3f270  br       loc_3F35E
0x3f275  ldarg.1
0x3f276  ldc.i4.0
0x3f277  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x3f27c  ldc.i4.s 0x78
0x3f27e  bne.un   loc_3F32A
0x3f283  ldarg.1
0x3f284  ldstr    aXmlns// "xmlns"
0x3f289  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3f28e  brfalse.s loc_3F2C9
0x3f290  ldarg.3
0x3f291  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3f296  ldc.i4.0
0x3f297  ble.s    loc_3F2B6
0x3f299  ldarg.3
0x3f29a  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x3f29f  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x3f2a4  brfalse.s loc_3F2B6
0x3f2a6  ldstr    aXmlXmlnsprefix// "Xml_XmlnsPrefix"
0x3f2ab  call     string System.Xml.Res::GetString(string name)
0x3f2b0  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x3f2b5  throw
0x3f2b6  ldarg.0
0x3f2b7  ldarg.2
0x3f2b8  stfld    string System.Xml.XmlWellFormedWriter::curDeclPrefix
0x3f2bd  ldarg.0
0x3f2be  ldc.i4.2
0x3f2bf  call     instance void System.Xml.XmlWellFormedWriter::SetSpecialAttribute(valuetype SpecialAttribute special)
0x3f2c4  br       loc_3F36E
0x3f2c9  ldarg.1
0x3f2ca  ldstr    aXml// "xml"
0x3f2cf  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3f2d4  brfalse.s loc_3F32A
0x3f2d6  ldarg.3
0x3f2d7  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3f2dc  ldc.i4.0
0x3f2dd  ble.s    loc_3F2FC
0x3f2df  ldarg.3
0x3f2e0  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x3f2e5  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x3f2ea  brfalse.s loc_3F2FC
0x3f2ec  ldstr    aXmlXmlprefix// "Xml_XmlPrefix"
0x3f2f1  call     string System.Xml.Res::GetString(string name)
0x3f2f6  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x3f2fb  throw
0x3f2fc  ldarg.2
0x3f2fd  ldstr    aSpace// "space"
0x3f302  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3f307  brtrue.s loc_3F318
0x3f309  ldarg.2
0x3f30a  ldstr    aLang// "lang"
0x3f30f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3f314  brtrue.s loc_3F321
0x3f316  br.s     loc_3F32A
0x3f318  ldarg.0
0x3f319  ldc.i4.3
0x3f31a  call     instance void System.Xml.XmlWellFormedWriter::SetSpecialAttribute(valuetype SpecialAttribute special)
0x3f31f  br.s     loc_3F36E
0x3f321  ldarg.0
0x3f322  ldc.i4.4
0x3f323  call     instance void System.Xml.XmlWellFormedWriter::SetSpecialAttribute(valuetype SpecialAttribute special)
0x3f328  br.s     loc_3F36E
0x3f32a  ldarg.0
0x3f32b  ldarg.1
0x3f32c  call     instance void System.Xml.XmlWellFormedWriter::CheckNCName(string ncname)
0x3f331  ldarg.3
0x3f332  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3f337  brtrue.s loc_3F342
0x3f339  ldsfld   string [mscorlib]System.String::Empty
0x3f33e  starg.s  1
0x3f340  br.s     loc_3F35E
0x3f342  ldarg.0
0x3f343  ldarg.1
0x3f344  call     instance string System.Xml.XmlWellFormedWriter::LookupLocalNamespace(string prefix)
0x3f349  stloc.0
0x3f34a  ldloc.0
0x3f34b  brfalse.s loc_3F35E
0x3f34d  ldloc.0
0x3f34e  ldarg.3
0x3f34f  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x3f354  brfalse.s loc_3F35E
0x3f356  ldarg.0
0x3f357  call     instance string System.Xml.XmlWellFormedWriter::GeneratePrefix()
0x3f35c  starg.s  1
0x3f35e  ldarg.1
0x3f35f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3f364  brfalse.s loc_3F36E
0x3f366  ldarg.0
0x3f367  ldarg.1
0x3f368  ldarg.3
0x3f369  call     instance void System.Xml.XmlWellFormedWriter::PushNamespaceImplicit(string prefix, string ns)
0x3f36e  ldarg.0
0x3f36f  ldarg.1
0x3f370  ldarg.2
0x3f371  ldarg.3
0x3f372  call     instance void System.Xml.XmlWellFormedWriter::AddAttribute(string prefix, string localName, string namespaceName)
0x3f377  ldarg.0
0x3f378  ldfld    valuetype SpecialAttribute System.Xml.XmlWellFormedWriter::specAttr
0x3f37d  brtrue.s loc_3F396
0x3f37f  ldarg.0
0x3f380  ldarg.0
0x3f381  ldfld    class System.Xml.XmlWriter System.Xml.XmlWellFormedWriter::writer
0x3f386  ldarg.1
0x3f387  ldarg.2
0x3f388  ldarg.3
0x3f389  callvirt instance class [mscorlib]System.Threading.Tasks.Task System.Xml.XmlWriter::WriteStartAttributeAsync(string prefix, string localName, string ns)
0x3f38e  call     instance class [mscorlib]System.Threading.Tasks.Task System.Xml.XmlWellFormedWriter::TryReturnTask(class [mscorlib]System.Threading.Tasks.Task task)
0x3f393  stloc.1
0x3f394  leave.s  loc_3F3A9
0x3f396  ldsfld   class [mscorlib]System.Threading.Tasks.Task System.Xml.AsyncHelper::DoneTask
0x3f39b  stloc.1
0x3f39c  leave.s  loc_3F3A9
0x3f39e  pop
0x3f39f  ldarg.0
0x3f3a0  ldc.i4.s 0x10
0x3f3a2  stfld    valuetype State System.Xml.XmlWellFormedWriter::currentState
0x3f3a7  rethrow
0x3f3a9  ldloc.1
0x3f3aa  ret
```
