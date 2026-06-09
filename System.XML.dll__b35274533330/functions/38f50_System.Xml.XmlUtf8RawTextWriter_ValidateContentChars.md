# System.Xml.XmlUtf8RawTextWriter::ValidateContentChars

- ea: `0x38f50`
- end: `0x3909e`
- name: `System.Xml.XmlUtf8RawTextWriter::ValidateContentChars`
- size: `334`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x370c0`
- `0x3acd0`

## callees

- `0xf000`
- `0xf0f0`
- `0xf110`
- `0xf1a0`
- `0x128e0`
- `0x38f50`
- `0x622f0`
- `0x62370`

## string_xrefs

- `0x39021`: `Xml_InvalidSurrogateMissingLowChar`
- `0x3903c`: `Xml_InvalidSurrogateHighChar`
- `0x38fd9`: `Xml_InvalidCharacter`
- `0x38f64`: `Xml_IndentCharsNotWhitespace`
- `0x3907d`: `Xml_InvalidCharsInIndent`

## pseudocode

```c

```

## disassembly

```asm
0x38f50  ldarg.3
0x38f51  brfalse.s loc_38F7E
0x38f53  ldarg.0
0x38f54  ldflda   valuetype System.Xml.XmlCharType System.Xml.XmlUtf8RawTextWriter::xmlCharType
0x38f59  ldarg.1
0x38f5a  call     instance bool System.Xml.XmlCharType::IsOnlyWhitespace(string str)
0x38f5f  brtrue   loc_3909D
0x38f64  ldstr    aXmlIndentchars// "Xml_IndentCharsNotWhitespace"
0x38f69  ldc.i4.1
0x38f6a  newarr   [mscorlib]System.Object
0x38f6f  dup
0x38f70  ldc.i4.0
0x38f71  ldarg.2
0x38f72  stelem.ref
0x38f73  call     string System.Xml.Res::GetString(string name, object[] args)
0x38f78  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x38f7d  throw
0x38f7e  ldnull
0x38f7f  stloc.0
0x38f80  ldc.i4.0
0x38f81  stloc.1
0x38f82  br       loc_39070
0x38f87  ldarg.0
0x38f88  ldflda   valuetype System.Xml.XmlCharType System.Xml.XmlUtf8RawTextWriter::xmlCharType
0x38f8d  ldarg.1
0x38f8e  ldloc.1
0x38f8f  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x38f94  call     instance bool System.Xml.XmlCharType::IsTextChar(char ch)
0x38f99  brtrue   loc_3906C
0x38f9e  ldarg.1
0x38f9f  ldloc.1
0x38fa0  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x38fa5  stloc.2
0x38fa6  ldloc.2
0x38fa7  ldc.i4.s 0x26
0x38fa9  bgt.un.s loc_38FCF
0x38fab  ldloc.2
0x38fac  ldc.i4.s 9
0x38fae  sub
0x38faf  switch   loc_3906C, loc_3906C, loc_38FF2, loc_38FF2, loc_3906C
0x38fc8  ldloc.2
0x38fc9  ldc.i4.s 0x26
0x38fcb  beq.s    loc_38FD9
0x38fcd  br.s     loc_38FF2
0x38fcf  ldloc.2
0x38fd0  ldc.i4.s 0x3C
0x38fd2  beq.s    loc_38FD9
0x38fd4  ldloc.2
0x38fd5  ldc.i4.s 0x5D
0x38fd7  bne.un.s loc_38FF2
0x38fd9  ldstr    aXmlInvalidchar// "Xml_InvalidCharacter"
0x38fde  ldarg.1
0x38fdf  ldloc.1
0x38fe0  call     string[] System.Xml.XmlException::BuildCharExceptionArgs(string data, int32 invCharIndex)
0x38fe5  stloc.3
0x38fe6  ldloc.3
0x38fe7  call     string System.Xml.Res::GetString(string name, object[] args)
0x38fec  stloc.0
0x38fed  br       loc_3907D
0x38ff2  ldarg.1
0x38ff3  ldloc.1
0x38ff4  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x38ff9  call     bool System.Xml.XmlCharType::IsHighSurrogate(int32 ch)
0x38ffe  brfalse.s loc_3902E
0x39000  ldloc.1
0x39001  ldc.i4.1
0x39002  add
0x39003  ldarg.1
0x39004  callvirt instance int32 [mscorlib]System.String::get_Length()
0x39009  bge.s    loc_39021
0x3900b  ldarg.1
0x3900c  ldloc.1
0x3900d  ldc.i4.1
0x3900e  add
0x3900f  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x39014  call     bool System.Xml.XmlCharType::IsLowSurrogate(int32 ch)
0x39019  brfalse.s loc_39021
0x3901b  ldloc.1
0x3901c  ldc.i4.1
0x3901d  add
0x3901e  stloc.1
0x3901f  br.s     loc_3906C
0x39021  ldstr    aXmlInvalidsurr// "Xml_InvalidSurrogateMissingLowChar"
0x39026  call     string System.Xml.Res::GetString(string name)
0x3902b  stloc.0
0x3902c  br.s     loc_3907D
0x3902e  ldarg.1
0x3902f  ldloc.1
0x39030  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x39035  call     bool System.Xml.XmlCharType::IsLowSurrogate(int32 ch)
0x3903a  brfalse.s loc_3906C
0x3903c  ldstr    aXmlInvalidsurr_1// "Xml_InvalidSurrogateHighChar"
0x39041  ldc.i4.1
0x39042  newarr   [mscorlib]System.Object
0x39047  dup
0x39048  ldc.i4.0
0x39049  ldarg.1
0x3904a  ldloc.1
0x3904b  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x39050  stloc.s  4
0x39052  ldloca.s 4
0x39054  ldstr    aX_0// "X"
0x39059  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3905e  call     instance string [mscorlib]System.UInt32::ToString(string, class [mscorlib]System.IFormatProvider)
0x39063  stelem.ref
0x39064  call     string System.Xml.Res::GetString(string name, object[] args)
0x39069  stloc.0
0x3906a  br.s     loc_3907D
0x3906c  ldloc.1
0x3906d  ldc.i4.1
0x3906e  add
0x3906f  stloc.1
0x39070  ldloc.1
0x39071  ldarg.1
0x39072  callvirt instance int32 [mscorlib]System.String::get_Length()
0x39077  blt      loc_38F87
0x3907c  ret
0x3907d  ldstr    aXmlInvalidchar_1// "Xml_InvalidCharsInIndent"
0x39082  ldc.i4.2
0x39083  newarr   [mscorlib]System.String
0x39088  dup
0x39089  ldc.i4.0
0x3908a  ldarg.2
0x3908b  stelem.ref
0x3908c  dup
0x3908d  ldc.i4.1
0x3908e  ldloc.0
0x3908f  stelem.ref
0x39090  stloc.3
0x39091  ldloc.3
0x39092  call     string System.Xml.Res::GetString(string name, object[] args)
0x39097  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x3909c  throw
0x3909d  ret
```
