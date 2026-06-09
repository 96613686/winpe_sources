# System.Xml.XmlCharCheckingReader::Read

- ea: `0x1a490`
- end: `0x1a816`
- name: `System.Xml.XmlCharCheckingReader::Read`
- size: `902`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config`

## callees

- `0xf280`
- `0x128e0`
- `0x1a490`
- `0x1ab30`
- `0x1ab40`
- `0x1ab50`
- `0x1ab80`
- `0x1ab90`
- `0x1abc0`
- `0x1abd0`
- `0x214b0`
- `0x214c0`
- `0x21500`
- `0x21520`
- `0x21540`
- `0x21b60`
- `0x21c20`
- `0x21c30`
- `0x21c40`
- `0x21c60`
- `0x21c90`

## string_xrefs

- `0x1a791`: `Xml_InvalidCharacter`
- `0x1a555`: `Xml_DtdIsProhibitedEx`
- `0x1a6ff`: `Xml_DtdIsProhibitedEx`

## pseudocode

```c

```

## disassembly

```asm
0x1a490  ldarg.0
0x1a491  ldfld    valuetype State System.Xml.XmlCharCheckingReader::state
0x1a496  stloc.1
0x1a497  ldloc.1
0x1a498  switch   loc_1A4AF, loc_1A4C7, loc_1A4C5, loc_1A4D4
0x1a4ad  br.s     loc_1A4E3
0x1a4af  ldarg.0
0x1a4b0  ldc.i4.3
0x1a4b1  stfld    valuetype State System.Xml.XmlCharCheckingReader::state
0x1a4b6  ldarg.0
0x1a4b7  ldfld    class System.Xml.XmlReader System.Xml.XmlWrappingReader::reader
0x1a4bc  callvirt instance valuetype System.Xml.ReadState System.Xml.XmlReader::get_ReadState()
0x1a4c1  brtrue.s loc_1A4E5
0x1a4c3  br.s     loc_1A4D4
0x1a4c5  ldc.i4.0
0x1a4c6  ret
0x1a4c7  ldarg.0
0x1a4c8  call     instance void System.Xml.XmlCharCheckingReader::FinishReadBinary()
0x1a4cd  ldarg.0
0x1a4ce  ldc.i4.3
0x1a4cf  stfld    valuetype State System.Xml.XmlCharCheckingReader::state
0x1a4d4  ldarg.0
0x1a4d5  ldfld    class System.Xml.XmlReader System.Xml.XmlWrappingReader::reader
0x1a4da  callvirt instance bool System.Xml.XmlReader::Read()
0x1a4df  brtrue.s loc_1A4E5
0x1a4e1  ldc.i4.0
0x1a4e2  ret
0x1a4e3  ldc.i4.0
0x1a4e4  ret
0x1a4e5  ldarg.0
0x1a4e6  ldfld    class System.Xml.XmlReader System.Xml.XmlWrappingReader::reader
0x1a4eb  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x1a4f0  stloc.0
0x1a4f1  ldarg.0
0x1a4f2  ldfld    bool System.Xml.XmlCharCheckingReader::checkCharacters
0x1a4f7  brtrue.s loc_1A578
0x1a4f9  ldloc.0
0x1a4fa  ldc.i4.7
0x1a4fb  sub
0x1a4fc  switch   loc_1A53D, loc_1A51F, loc_1A576, loc_1A54C, loc_1A576, loc_1A576, loc_1A52E
0x1a51d  br.s     loc_1A576
0x1a51f  ldarg.0
0x1a520  ldfld    bool System.Xml.XmlCharCheckingReader::ignoreComments
0x1a525  brfalse.s loc_1A576
0x1a527  ldarg.0
0x1a528  callvirt instance bool System.Xml.XmlReader::Read()
0x1a52d  ret
0x1a52e  ldarg.0
0x1a52f  ldfld    bool System.Xml.XmlCharCheckingReader::ignoreWhitespace
0x1a534  brfalse.s loc_1A576
0x1a536  ldarg.0
0x1a537  callvirt instance bool System.Xml.XmlReader::Read()
0x1a53c  ret
0x1a53d  ldarg.0
0x1a53e  ldfld    bool System.Xml.XmlCharCheckingReader::ignorePis
0x1a543  brfalse.s loc_1A576
0x1a545  ldarg.0
0x1a546  callvirt instance bool System.Xml.XmlReader::Read()
0x1a54b  ret
0x1a54c  ldarg.0
0x1a54d  ldfld    valuetype System.Xml.DtdProcessing System.Xml.XmlCharCheckingReader::dtdProcessing
0x1a552  brtrue.s loc_1A566
0x1a554  ldarg.0
0x1a555  ldstr    aXmlDtdisprohib// "Xml_DtdIsProhibitedEx"
0x1a55a  ldsfld   string [mscorlib]System.String::Empty
0x1a55f  call     instance void System.Xml.XmlCharCheckingReader::Throw(string res, string arg)
0x1a564  br.s     loc_1A576
0x1a566  ldarg.0
0x1a567  ldfld    valuetype System.Xml.DtdProcessing System.Xml.XmlCharCheckingReader::dtdProcessing
0x1a56c  ldc.i4.1
0x1a56d  bne.un.s loc_1A576
0x1a56f  ldarg.0
0x1a570  callvirt instance bool System.Xml.XmlReader::Read()
0x1a575  ret
0x1a576  ldc.i4.1
0x1a577  ret
0x1a578  ldloc.0
0x1a579  ldc.i4.1
0x1a57a  sub
0x1a57b  switch   loc_1A5C1, loc_1A80D, loc_1A643, loc_1A643, loc_1A664, loc_1A80D, loc_1A685, loc_1A6C6, loc_1A80D, loc_1A6F6, loc_1A80D, loc_1A80D, loc_1A7A4, loc_1A7CE, loc_1A7E9
0x1a5bc  br       loc_1A80D
0x1a5c1  ldarg.0
0x1a5c2  ldfld    bool System.Xml.XmlCharCheckingReader::checkCharacters
0x1a5c7  brfalse  loc_1A80D
0x1a5cc  ldarg.0
0x1a5cd  ldarg.0
0x1a5ce  ldfld    class System.Xml.XmlReader System.Xml.XmlWrappingReader::reader
0x1a5d3  callvirt instance string System.Xml.XmlReader::get_Prefix()
0x1a5d8  ldarg.0
0x1a5d9  ldfld    class System.Xml.XmlReader System.Xml.XmlWrappingReader::reader
0x1a5de  callvirt instance string System.Xml.XmlReader::get_LocalName()
0x1a5e3  call     instance void System.Xml.XmlCharCheckingReader::ValidateQName(string prefix, string localName)
0x1a5e8  ldarg.0
0x1a5e9  ldfld    class System.Xml.XmlReader System.Xml.XmlWrappingReader::reader
0x1a5ee  callvirt instance bool System.Xml.XmlReader::MoveToFirstAttribute()
0x1a5f3  brfalse  loc_1A80D
0x1a5f8  ldarg.0
0x1a5f9  ldarg.0
0x1a5fa  ldfld    class System.Xml.XmlReader System.Xml.XmlWrappingReader::reader
0x1a5ff  callvirt instance string System.Xml.XmlReader::get_Prefix()
0x1a604  ldarg.0
0x1a605  ldfld    class System.Xml.XmlReader System.Xml.XmlWrappingReader::reader
0x1a60a  callvirt instance string System.Xml.XmlReader::get_LocalName()
0x1a60f  call     instance void System.Xml.XmlCharCheckingReader::ValidateQName(string prefix, string localName)
0x1a614  ldarg.0
0x1a615  ldarg.0
0x1a616  ldfld    class System.Xml.XmlReader System.Xml.XmlWrappingReader::reader
0x1a61b  callvirt instance string System.Xml.XmlReader::get_Value()
0x1a620  call     instance void System.Xml.XmlCharCheckingReader::CheckCharacters(string value)
0x1a625  ldarg.0
0x1a626  ldfld    class System.Xml.XmlReader System.Xml.XmlWrappingReader::reader
0x1a62b  callvirt instance bool System.Xml.XmlReader::MoveToNextAttribute()
0x1a630  brtrue.s loc_1A5F8
0x1a632  ldarg.0
0x1a633  ldfld    class System.Xml.XmlReader System.Xml.XmlWrappingReader::reader
0x1a638  callvirt instance bool System.Xml.XmlReader::MoveToElement()
0x1a63d  pop
0x1a63e  br       loc_1A80D
0x1a643  ldarg.0
0x1a644  ldfld    bool System.Xml.XmlCharCheckingReader::checkCharacters
0x1a649  brfalse  loc_1A80D
0x1a64e  ldarg.0
0x1a64f  ldarg.0
0x1a650  ldfld    class System.Xml.XmlReader System.Xml.XmlWrappingReader::reader
0x1a655  callvirt instance string System.Xml.XmlReader::get_Value()
0x1a65a  call     instance void System.Xml.XmlCharCheckingReader::CheckCharacters(string value)
0x1a65f  br       loc_1A80D
0x1a664  ldarg.0
0x1a665  ldfld    bool System.Xml.XmlCharCheckingReader::checkCharacters
0x1a66a  brfalse  loc_1A80D
0x1a66f  ldarg.0
0x1a670  ldarg.0
0x1a671  ldfld    class System.Xml.XmlReader System.Xml.XmlWrappingReader::reader
0x1a676  callvirt instance string System.Xml.XmlReader::get_Name()
0x1a67b  call     instance void System.Xml.XmlCharCheckingReader::ValidateQName(string name)
0x1a680  br       loc_1A80D
0x1a685  ldarg.0
0x1a686  ldfld    bool System.Xml.XmlCharCheckingReader::ignorePis
0x1a68b  brfalse.s loc_1A694
0x1a68d  ldarg.0
0x1a68e  callvirt instance bool System.Xml.XmlReader::Read()
0x1a693  ret
0x1a694  ldarg.0
0x1a695  ldfld    bool System.Xml.XmlCharCheckingReader::checkCharacters
0x1a69a  brfalse  loc_1A80D
0x1a69f  ldarg.0
0x1a6a0  ldarg.0
0x1a6a1  ldfld    class System.Xml.XmlReader System.Xml.XmlWrappingReader::reader
0x1a6a6  callvirt instance string System.Xml.XmlReader::get_Name()
0x1a6ab  call     instance void System.Xml.XmlCharCheckingReader::ValidateQName(string name)
0x1a6b0  ldarg.0
0x1a6b1  ldarg.0
0x1a6b2  ldfld    class System.Xml.XmlReader System.Xml.XmlWrappingReader::reader
0x1a6b7  callvirt instance string System.Xml.XmlReader::get_Value()
0x1a6bc  call     instance void System.Xml.XmlCharCheckingReader::CheckCharacters(string value)
0x1a6c1  br       loc_1A80D
0x1a6c6  ldarg.0
0x1a6c7  ldfld    bool System.Xml.XmlCharCheckingReader::ignoreComments
0x1a6cc  brfalse.s loc_1A6D5
0x1a6ce  ldarg.0
0x1a6cf  callvirt instance bool System.Xml.XmlReader::Read()
0x1a6d4  ret
0x1a6d5  ldarg.0
0x1a6d6  ldfld    bool System.Xml.XmlCharCheckingReader::checkCharacters
0x1a6db  brfalse  loc_1A80D
0x1a6e0  ldarg.0
0x1a6e1  ldarg.0
0x1a6e2  ldfld    class System.Xml.XmlReader System.Xml.XmlWrappingReader::reader
0x1a6e7  callvirt instance string System.Xml.XmlReader::get_Value()
0x1a6ec  call     instance void System.Xml.XmlCharCheckingReader::CheckCharacters(string value)
0x1a6f1  br       loc_1A80D
0x1a6f6  ldarg.0
0x1a6f7  ldfld    valuetype System.Xml.DtdProcessing System.Xml.XmlCharCheckingReader::dtdProcessing
0x1a6fc  brtrue.s loc_1A710
0x1a6fe  ldarg.0
0x1a6ff  ldstr    aXmlDtdisprohib// "Xml_DtdIsProhibitedEx"
0x1a704  ldsfld   string [mscorlib]System.String::Empty
0x1a709  call     instance void System.Xml.XmlCharCheckingReader::Throw(string res, string arg)
0x1a70e  br.s     loc_1A720
0x1a710  ldarg.0
0x1a711  ldfld    valuetype System.Xml.DtdProcessing System.Xml.XmlCharCheckingReader::dtdProcessing
0x1a716  ldc.i4.1
0x1a717  bne.un.s loc_1A720
0x1a719  ldarg.0
0x1a71a  callvirt instance bool System.Xml.XmlReader::Read()
0x1a71f  ret
0x1a720  ldarg.0
0x1a721  ldfld    bool System.Xml.XmlCharCheckingReader::checkCharacters
0x1a726  brfalse  loc_1A80D
0x1a72b  ldarg.0
0x1a72c  ldarg.0
0x1a72d  ldfld    class System.Xml.XmlReader System.Xml.XmlWrappingReader::reader
0x1a732  callvirt instance string System.Xml.XmlReader::get_Name()
0x1a737  call     instance void System.Xml.XmlCharCheckingReader::ValidateQName(string name)
0x1a73c  ldarg.0
0x1a73d  ldarg.0
0x1a73e  ldfld    class System.Xml.XmlReader System.Xml.XmlWrappingReader::reader
0x1a743  callvirt instance string System.Xml.XmlReader::get_Value()
0x1a748  call     instance void System.Xml.XmlCharCheckingReader::CheckCharacters(string value)
0x1a74d  ldarg.0
0x1a74e  ldfld    class System.Xml.XmlReader System.Xml.XmlWrappingReader::reader
0x1a753  ldstr    aSystem_0// "SYSTEM"
0x1a758  callvirt instance string System.Xml.XmlReader::GetAttribute(string name)
0x1a75d  stloc.2
0x1a75e  ldloc.2
0x1a75f  brfalse.s loc_1A768
0x1a761  ldarg.0
0x1a762  ldloc.2
0x1a763  call     instance void System.Xml.XmlCharCheckingReader::CheckCharacters(string value)
0x1a768  ldarg.0
0x1a769  ldfld    class System.Xml.XmlReader System.Xml.XmlWrappingReader::reader
0x1a76e  ldstr    aPublic_0// "PUBLIC"
0x1a773  callvirt instance string System.Xml.XmlReader::GetAttribute(string name)
0x1a778  stloc.2
0x1a779  ldloc.2
0x1a77a  brfalse  loc_1A80D
0x1a77f  ldarg.0
0x1a780  ldflda   valuetype System.Xml.XmlCharType System.Xml.XmlCharCheckingReader::xmlCharType
0x1a785  ldloc.2
0x1a786  call     instance int32 System.Xml.XmlCharType::IsPublicId(string str)
0x1a78b  dup
0x1a78c  stloc.3
0x1a78d  ldc.i4.0
0x1a78e  blt.s    loc_1A80D
0x1a790  ldarg.0
0x1a791  ldstr    aXmlInvalidchar// "Xml_InvalidCharacter"
0x1a796  ldloc.2
0x1a797  ldloc.3
0x1a798  call     string[] System.Xml.XmlException::BuildCharExceptionArgs(string data, int32 invCharIndex)
0x1a79d  call     instance void System.Xml.XmlCharCheckingReader::Throw(string res, string[] args)
0x1a7a2  br.s     loc_1A80D
0x1a7a4  ldarg.0
0x1a7a5  ldfld    bool System.Xml.XmlCharCheckingReader::ignoreWhitespace
0x1a7aa  brfalse.s loc_1A7B3
0x1a7ac  ldarg.0
0x1a7ad  callvirt instance bool System.Xml.XmlReader::Read()
0x1a7b2  ret
0x1a7b3  ldarg.0
0x1a7b4  ldfld    bool System.Xml.XmlCharCheckingReader::checkCharacters
0x1a7b9  brfalse.s loc_1A80D
0x1a7bb  ldarg.0
0x1a7bc  ldarg.0
0x1a7bd  ldfld    class System.Xml.XmlReader System.Xml.XmlWrappingReader::reader
0x1a7c2  callvirt instance string System.Xml.XmlReader::get_Value()
0x1a7c7  call     instance void System.Xml.XmlCharCheckingReader::CheckWhitespace(string value)
0x1a7cc  br.s     loc_1A80D
0x1a7ce  ldarg.0
0x1a7cf  ldfld    bool System.Xml.XmlCharCheckingReader::checkCharacters
0x1a7d4  brfalse.s loc_1A80D
0x1a7d6  ldarg.0
0x1a7d7  ldarg.0
0x1a7d8  ldfld    class System.Xml.XmlReader System.Xml.XmlWrappingReader::reader
0x1a7dd  callvirt instance string System.Xml.XmlReader::get_Value()
0x1a7e2  call     instance void System.Xml.XmlCharCheckingReader::CheckWhitespace(string value)
0x1a7e7  br.s     loc_1A80D
0x1a7e9  ldarg.0
0x1a7ea  ldfld    bool System.Xml.XmlCharCheckingReader::checkCharacters
0x1a7ef  brfalse.s loc_1A80D
0x1a7f1  ldarg.0
0x1a7f2  ldarg.0
0x1a7f3  ldfld    class System.Xml.XmlReader System.Xml.XmlWrappingReader::reader
0x1a7f8  callvirt instance string System.Xml.XmlReader::get_Prefix()
0x1a7fd  ldarg.0
0x1a7fe  ldfld    class System.Xml.XmlReader System.Xml.XmlWrappingReader::reader
0x1a803  callvirt instance string System.Xml.XmlReader::get_LocalName()
0x1a808  call     instance void System.Xml.XmlCharCheckingReader::ValidateQName(string prefix, string localName)
0x1a80d  ldarg.0
0x1a80e  ldloc.0
0x1a80f  stfld    valuetype System.Xml.XmlNodeType System.Xml.XmlCharCheckingReader::lastNodeType
0x1a814  ldc.i4.1
0x1a815  ret
```
