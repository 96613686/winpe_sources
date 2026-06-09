# System.Xml.XmlTextReaderImpl::CheckEncoding

- ea: `0x2a2e0`
- end: `0x2a41b`
- name: `System.Xml.XmlTextReaderImpl::CheckEncoding`
- size: `315`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x2ab60`
- `0x101a60`

## callees

- `0x29770`
- `0x297f0`
- `0x29890`
- `0x2a2e0`

## string_xrefs

- `0x2a3ca`: `Xml_UnknownEncoding`
- `0x2a3da`: `Xml_UnknownEncoding`
- `0x2a380`: `Xml_EncodingSwitchAfterResetState`
- `0x2a40e`: `Xml_EncodingSwitchAfterResetState`
- `0x2a38e`: `Xml_MissingByteOrderMark`

## pseudocode

```c

```

## disassembly

```asm
0x2a2e0  ldarg.0
0x2a2e1  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2a2e6  ldfld    class [mscorlib]System.IO.Stream ParsingState::stream
0x2a2eb  brtrue.s loc_2A2F9
0x2a2ed  ldarg.0
0x2a2ee  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2a2f3  ldfld    class [mscorlib]System.Text.Encoding ParsingState::encoding
0x2a2f8  ret
0x2a2f9  ldarg.1
0x2a2fa  ldstr    aUcs2// "ucs-2"
0x2a2ff  ldc.i4.5
0x2a300  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x2a305  brfalse.s loc_2A331
0x2a307  ldarg.1
0x2a308  ldstr    aUtf16// "utf-16"
0x2a30d  ldc.i4.5
0x2a30e  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x2a313  brfalse.s loc_2A331
0x2a315  ldarg.1
0x2a316  ldstr    aIso10646Ucs2// "iso-10646-ucs-2"
0x2a31b  ldc.i4.5
0x2a31c  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x2a321  brfalse.s loc_2A331
0x2a323  ldarg.1
0x2a324  ldstr    aUcs4// "ucs-4"
0x2a329  ldc.i4.5
0x2a32a  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x2a32f  brtrue.s loc_2A3A4
0x2a331  ldarg.0
0x2a332  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2a337  ldfld    class [mscorlib]System.Text.Encoding ParsingState::encoding
0x2a33c  callvirt instance string [mscorlib]System.Text.Encoding::get_WebName()
0x2a341  ldstr    aUtf16be// "utf-16BE"
0x2a346  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x2a34b  brfalse.s loc_2A398
0x2a34d  ldarg.0
0x2a34e  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2a353  ldfld    class [mscorlib]System.Text.Encoding ParsingState::encoding
0x2a358  callvirt instance string [mscorlib]System.Text.Encoding::get_WebName()
0x2a35d  ldstr    aUtf16// "utf-16"
0x2a362  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x2a367  brfalse.s loc_2A398
0x2a369  ldarg.1
0x2a36a  ldstr    aUcs4// "ucs-4"
0x2a36f  ldc.i4.5
0x2a370  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x2a375  brfalse.s loc_2A398
0x2a377  ldarg.0
0x2a378  ldfld    bool System.Xml.XmlTextReaderImpl::afterResetState
0x2a37d  brfalse.s loc_2A38D
0x2a37f  ldarg.0
0x2a380  ldstr    aXmlEncodingswi// "Xml_EncodingSwitchAfterResetState"
0x2a385  ldarg.1
0x2a386  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res, string arg)
0x2a38b  br.s     loc_2A398
0x2a38d  ldarg.0
0x2a38e  ldstr    aXmlMissingbyte// "Xml_MissingByteOrderMark"
0x2a393  call     instance void System.Xml.XmlTextReaderImpl::ThrowWithoutLineInfo(string res)
0x2a398  ldarg.0
0x2a399  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2a39e  ldfld    class [mscorlib]System.Text.Encoding ParsingState::encoding
0x2a3a3  ret
0x2a3a4  ldnull
0x2a3a5  stloc.0
0x2a3a6  ldarg.1
0x2a3a7  ldstr    aUtf8// "utf-8"
0x2a3ac  ldc.i4.5
0x2a3ad  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x2a3b2  brtrue.s loc_2A3BE
0x2a3b4  ldc.i4.1
0x2a3b5  ldc.i4.1
0x2a3b6  newobj   instance void [mscorlib]System.Text.UTF8Encoding::.ctor(bool, bool)
0x2a3bb  stloc.0
0x2a3bc  br.s     loc_2A3E8
0x2a3be  nop
0x2a3bf  ldarg.1
0x2a3c0  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::GetEncoding(string)
0x2a3c5  stloc.0
0x2a3c6  leave.s  loc_2A3E8
0x2a3c8  stloc.1
0x2a3c9  ldarg.0
0x2a3ca  ldstr    aXmlUnknownenco// "Xml_UnknownEncoding"
0x2a3cf  ldarg.1
0x2a3d0  ldloc.1
0x2a3d1  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res, string arg, class [mscorlib]System.Exception innerException)
0x2a3d6  leave.s  loc_2A3E8
0x2a3d8  stloc.2
0x2a3d9  ldarg.0
0x2a3da  ldstr    aXmlUnknownenco// "Xml_UnknownEncoding"
0x2a3df  ldarg.1
0x2a3e0  ldloc.2
0x2a3e1  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res, string arg, class [mscorlib]System.Exception innerException)
0x2a3e6  leave.s  loc_2A3E8
0x2a3e8  ldarg.0
0x2a3e9  ldfld    bool System.Xml.XmlTextReaderImpl::afterResetState
0x2a3ee  brfalse.s loc_2A419
0x2a3f0  ldarg.0
0x2a3f1  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x2a3f6  ldfld    class [mscorlib]System.Text.Encoding ParsingState::encoding
0x2a3fb  callvirt instance string [mscorlib]System.Text.Encoding::get_WebName()
0x2a400  ldloc.0
0x2a401  callvirt instance string [mscorlib]System.Text.Encoding::get_WebName()
0x2a406  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x2a40b  brfalse.s loc_2A419
0x2a40d  ldarg.0
0x2a40e  ldstr    aXmlEncodingswi// "Xml_EncodingSwitchAfterResetState"
0x2a413  ldarg.1
0x2a414  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res, string arg)
0x2a419  ldloc.0
0x2a41a  ret
```
