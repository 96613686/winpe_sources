# System.Xml.XmlEncodedRawTextWriter::ValidateContentChars

- ea: `0x1ddc0`
- end: `0x1df0e`
- name: `System.Xml.XmlEncodedRawTextWriter::ValidateContentChars`
- size: `334`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1bab0`
- `0x1fd30`

## callees

- `0xf000`
- `0xf0f0`
- `0xf110`
- `0xf1a0`
- `0x128e0`
- `0x1ddc0`
- `0x622f0`
- `0x62370`

## string_xrefs

- `0x1de91`: `Xml_InvalidSurrogateMissingLowChar`
- `0x1deac`: `Xml_InvalidSurrogateHighChar`
- `0x1de49`: `Xml_InvalidCharacter`
- `0x1ddd4`: `Xml_IndentCharsNotWhitespace`
- `0x1deed`: `Xml_InvalidCharsInIndent`

## pseudocode

```c

```

## disassembly

```asm
0x1ddc0  ldarg.3
0x1ddc1  brfalse.s loc_1DDEE
0x1ddc3  ldarg.0
0x1ddc4  ldflda   valuetype System.Xml.XmlCharType System.Xml.XmlEncodedRawTextWriter::xmlCharType
0x1ddc9  ldarg.1
0x1ddca  call     instance bool System.Xml.XmlCharType::IsOnlyWhitespace(string str)
0x1ddcf  brtrue   loc_1DF0D
0x1ddd4  ldstr    aXmlIndentchars// "Xml_IndentCharsNotWhitespace"
0x1ddd9  ldc.i4.1
0x1ddda  newarr   [mscorlib]System.Object
0x1dddf  dup
0x1dde0  ldc.i4.0
0x1dde1  ldarg.2
0x1dde2  stelem.ref
0x1dde3  call     string System.Xml.Res::GetString(string name, object[] args)
0x1dde8  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x1dded  throw
0x1ddee  ldnull
0x1ddef  stloc.0
0x1ddf0  ldc.i4.0
0x1ddf1  stloc.1
0x1ddf2  br       loc_1DEE0
0x1ddf7  ldarg.0
0x1ddf8  ldflda   valuetype System.Xml.XmlCharType System.Xml.XmlEncodedRawTextWriter::xmlCharType
0x1ddfd  ldarg.1
0x1ddfe  ldloc.1
0x1ddff  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x1de04  call     instance bool System.Xml.XmlCharType::IsTextChar(char ch)
0x1de09  brtrue   loc_1DEDC
0x1de0e  ldarg.1
0x1de0f  ldloc.1
0x1de10  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x1de15  stloc.2
0x1de16  ldloc.2
0x1de17  ldc.i4.s 0x26
0x1de19  bgt.un.s loc_1DE3F
0x1de1b  ldloc.2
0x1de1c  ldc.i4.s 9
0x1de1e  sub
0x1de1f  switch   loc_1DEDC, loc_1DEDC, loc_1DE62, loc_1DE62, loc_1DEDC
0x1de38  ldloc.2
0x1de39  ldc.i4.s 0x26
0x1de3b  beq.s    loc_1DE49
0x1de3d  br.s     loc_1DE62
0x1de3f  ldloc.2
0x1de40  ldc.i4.s 0x3C
0x1de42  beq.s    loc_1DE49
0x1de44  ldloc.2
0x1de45  ldc.i4.s 0x5D
0x1de47  bne.un.s loc_1DE62
0x1de49  ldstr    aXmlInvalidchar// "Xml_InvalidCharacter"
0x1de4e  ldarg.1
0x1de4f  ldloc.1
0x1de50  call     string[] System.Xml.XmlException::BuildCharExceptionArgs(string data, int32 invCharIndex)
0x1de55  stloc.3
0x1de56  ldloc.3
0x1de57  call     string System.Xml.Res::GetString(string name, object[] args)
0x1de5c  stloc.0
0x1de5d  br       loc_1DEED
0x1de62  ldarg.1
0x1de63  ldloc.1
0x1de64  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x1de69  call     bool System.Xml.XmlCharType::IsHighSurrogate(int32 ch)
0x1de6e  brfalse.s loc_1DE9E
0x1de70  ldloc.1
0x1de71  ldc.i4.1
0x1de72  add
0x1de73  ldarg.1
0x1de74  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1de79  bge.s    loc_1DE91
0x1de7b  ldarg.1
0x1de7c  ldloc.1
0x1de7d  ldc.i4.1
0x1de7e  add
0x1de7f  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x1de84  call     bool System.Xml.XmlCharType::IsLowSurrogate(int32 ch)
0x1de89  brfalse.s loc_1DE91
0x1de8b  ldloc.1
0x1de8c  ldc.i4.1
0x1de8d  add
0x1de8e  stloc.1
0x1de8f  br.s     loc_1DEDC
0x1de91  ldstr    aXmlInvalidsurr// "Xml_InvalidSurrogateMissingLowChar"
0x1de96  call     string System.Xml.Res::GetString(string name)
0x1de9b  stloc.0
0x1de9c  br.s     loc_1DEED
0x1de9e  ldarg.1
0x1de9f  ldloc.1
0x1dea0  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x1dea5  call     bool System.Xml.XmlCharType::IsLowSurrogate(int32 ch)
0x1deaa  brfalse.s loc_1DEDC
0x1deac  ldstr    aXmlInvalidsurr_1// "Xml_InvalidSurrogateHighChar"
0x1deb1  ldc.i4.1
0x1deb2  newarr   [mscorlib]System.Object
0x1deb7  dup
0x1deb8  ldc.i4.0
0x1deb9  ldarg.1
0x1deba  ldloc.1
0x1debb  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x1dec0  stloc.s  4
0x1dec2  ldloca.s 4
0x1dec4  ldstr    aX_0// "X"
0x1dec9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1dece  call     instance string [mscorlib]System.UInt32::ToString(string, class [mscorlib]System.IFormatProvider)
0x1ded3  stelem.ref
0x1ded4  call     string System.Xml.Res::GetString(string name, object[] args)
0x1ded9  stloc.0
0x1deda  br.s     loc_1DEED
0x1dedc  ldloc.1
0x1dedd  ldc.i4.1
0x1dede  add
0x1dedf  stloc.1
0x1dee0  ldloc.1
0x1dee1  ldarg.1
0x1dee2  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1dee7  blt      loc_1DDF7
0x1deec  ret
0x1deed  ldstr    aXmlInvalidchar_1// "Xml_InvalidCharsInIndent"
0x1def2  ldc.i4.2
0x1def3  newarr   [mscorlib]System.String
0x1def8  dup
0x1def9  ldc.i4.0
0x1defa  ldarg.2
0x1defb  stelem.ref
0x1defc  dup
0x1defd  ldc.i4.1
0x1defe  ldloc.0
0x1deff  stelem.ref
0x1df00  stloc.3
0x1df01  ldloc.3
0x1df02  call     string System.Xml.Res::GetString(string name, object[] args)
0x1df07  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x1df0c  throw
0x1df0d  ret
```
