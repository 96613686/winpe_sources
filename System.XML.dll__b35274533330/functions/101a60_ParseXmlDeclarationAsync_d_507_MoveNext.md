# <ParseXmlDeclarationAsync>d__507::MoveNext

- ea: `0x101a60`
- end: `0x102932`
- name: `<ParseXmlDeclarationAsync>d__507::MoveNext`
- size: `3794`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config`

## callees

- `0xef80`
- `0x10e60`
- `0x29740`
- `0x29750`
- `0x29770`
- `0x2a2e0`
- `0x2fd60`
- `0x313a0`
- `0x313d0`
- `0x33190`
- `0x331f0`
- `0x33200`
- `0x34dd0`
- `0x34eb0`
- `0xfe500`
- `0xfe510`
- `0xfeab0`
- `0xfeac0`
- `0xfeb20`
- `0xfeb70`
- `0xfeb80`
- `0x101a60`

## string_xrefs

- `0x101db4`: `Xml_EncodingSwitchAfterResetState`
- `0x102832`: `Xml_EncodingSwitchAfterResetState`
- `0x101b41`: `<?xml`
- `0x101ce0`: `Xml_InvalidXmlDecl`
- `0x102115`: `Xml_InvalidXmlDecl`
- `0x1025c2`: `Xml_InvalidXmlDecl`
- `0x102715`: `Xml_InvalidXmlDecl`
- `0x101ce7`: `Xml_InvalidTextDecl`
- `0x101d53`: `Xml_InvalidTextDecl`
- `0x10211c`: `Xml_InvalidTextDecl`
- `0x10271c`: `Xml_InvalidTextDecl`
- `0x1024d8`: `Xml_InvalidVersionNumber`
- `0x102700`: `Xml_UnclosedQuote`
- `0x1027b1`: `Xml_UnexpectedEOF1`

## pseudocode

```c

```

## disassembly

```asm
0x101a60  ldarg.0
0x101a61  ldfld    int32 <ParseXmlDeclarationAsync>d__507::<>1__state
0x101a66  stloc.0
0x101a67  ldarg.0
0x101a68  ldfld    class System.Xml.XmlTextReaderImpl <ParseXmlDeclarationAsync>d__507::<>4__this
0x101a6d  stloc.1
0x101a6e  ldloc.0
0x101a6f  switch   loc_101AE2, loc_101C56, loc_101E3B, loc_101EAB, loc_101F65, loc_1021F4, loc_1022DE, loc_1026D2, loc_10277F, loc_1028B4
0x101a9c  br.s     loc_101B0D
0x101a9e  ldloc.1
0x101a9f  call     instance class [mscorlib]System.Threading.Tasks.Task`1<int32> System.Xml.XmlTextReaderImpl::ReadDataAsync()
0x101aa4  ldc.i4.0
0x101aa5  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<int32>::ConfigureAwait(!!T0)
0x101aaa  stloc.s  5
0x101aac  ldloca.s 5
0x101aae  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<int32>::GetAwaiter()
0x101ab3  stloc.s  4
0x101ab5  ldloca.s 4
0x101ab7  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>::get_IsCompleted()
0x101abc  brtrue.s loc_101AFF
0x101abe  ldarg.0
0x101abf  ldc.i4.0
0x101ac0  dup
0x101ac1  stloc.0
0x101ac2  stfld    int32 <ParseXmlDeclarationAsync>d__507::<>1__state
0x101ac7  ldarg.0
0x101ac8  ldloc.s  4
0x101aca  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <ParseXmlDeclarationAsync>d__507::<>u__1
0x101acf  ldarg.0
0x101ad0  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <ParseXmlDeclarationAsync>d__507::<>t__builder
0x101ad5  ldloca.s 4
0x101ad7  ldarg.0
0x101ad8  call     T0x2B0001DF
0x101add  leave    loc_102931
0x101ae2  ldarg.0
0x101ae3  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <ParseXmlDeclarationAsync>d__507::<>u__1
0x101ae8  stloc.s  4
0x101aea  ldarg.0
0x101aeb  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <ParseXmlDeclarationAsync>d__507::<>u__1
0x101af0  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>
0x101af6  ldarg.0
0x101af7  ldc.i4.m1
0x101af8  dup
0x101af9  stloc.0
0x101afa  stfld    int32 <ParseXmlDeclarationAsync>d__507::<>1__state
0x101aff  ldloca.s 4
0x101b01  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>::GetResult()
0x101b06  stloc.3
0x101b07  ldloc.3
0x101b08  brfalse  loc_1027C7
0x101b0d  ldloc.1
0x101b0e  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x101b13  ldfld    int32 ParsingState::charsUsed
0x101b18  ldloc.1
0x101b19  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x101b1e  ldfld    int32 ParsingState::charPos
0x101b23  sub
0x101b24  ldc.i4.6
0x101b25  blt      loc_101A9E
0x101b2a  ldloc.1
0x101b2b  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x101b30  ldfld    char[] ParsingState::chars
0x101b35  ldloc.1
0x101b36  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x101b3b  ldfld    int32 ParsingState::charPos
0x101b40  ldc.i4.5
0x101b41  ldstr    aXml_1// "<?xml"
0x101b46  call     bool System.Xml.XmlConvert::StrEqual(char[] chars, int32 strPos1, int32 strLen1, string str2)
0x101b4b  brfalse  loc_1027C7
0x101b50  ldloc.1
0x101b51  ldflda   valuetype System.Xml.XmlCharType System.Xml.XmlTextReaderImpl::xmlCharType
0x101b56  ldloc.1
0x101b57  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x101b5c  ldfld    char[] ParsingState::chars
0x101b61  ldloc.1
0x101b62  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x101b67  ldfld    int32 ParsingState::charPos
0x101b6c  ldc.i4.5
0x101b6d  add
0x101b6e  ldelem.u2
0x101b6f  call     instance bool System.Xml.XmlCharType::IsNameSingleChar(char ch)
0x101b74  brtrue   loc_1027C7
0x101b79  ldarg.0
0x101b7a  ldfld    bool <ParseXmlDeclarationAsync>d__507::isTextDecl
0x101b7f  brtrue.s loc_101BB7
0x101b81  ldloc.1
0x101b82  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x101b87  ldloc.1
0x101b88  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x101b8d  call     instance int32 ParsingState::get_LineNo()
0x101b92  ldloc.1
0x101b93  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x101b98  call     instance int32 ParsingState::get_LinePos()
0x101b9d  ldc.i4.2
0x101b9e  add
0x101b9f  callvirt instance void NodeData::SetLineInfo(int32 lineNo, int32 linePos)
0x101ba4  ldloc.1
0x101ba5  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x101baa  ldc.i4.s 0x11
0x101bac  ldloc.1
0x101bad  ldfld    string System.Xml.XmlTextReaderImpl::Xml
0x101bb2  callvirt instance void NodeData::SetNamedNode(valuetype System.Xml.XmlNodeType type, string localName)
0x101bb7  ldloc.1
0x101bb8  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x101bbd  ldflda   int32 ParsingState::charPos
0x101bc2  dup
0x101bc3  ldind.i4
0x101bc4  ldc.i4.5
0x101bc5  add
0x101bc6  stind.i4
0x101bc7  ldarg.0
0x101bc8  ldarg.0
0x101bc9  ldfld    bool <ParseXmlDeclarationAsync>d__507::isTextDecl
0x101bce  brtrue.s loc_101BD8
0x101bd0  ldloc.1
0x101bd1  ldfld    class [mscorlib]System.Text.StringBuilder System.Xml.XmlTextReaderImpl::stringBuilder
0x101bd6  br.s     loc_101BDD
0x101bd8  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x101bdd  stfld    class [mscorlib]System.Text.StringBuilder <ParseXmlDeclarationAsync>d__507::<sb>5__2
0x101be2  ldarg.0
0x101be3  ldc.i4.0
0x101be4  stfld    int32 <ParseXmlDeclarationAsync>d__507::<xmlDeclState>5__3
0x101be9  ldarg.0
0x101bea  ldnull
0x101beb  stfld    class [mscorlib]System.Text.Encoding <ParseXmlDeclarationAsync>d__507::<encoding>5__4
0x101bf0  ldarg.0
0x101bf1  ldarg.0
0x101bf2  ldfld    class [mscorlib]System.Text.StringBuilder <ParseXmlDeclarationAsync>d__507::<sb>5__2
0x101bf7  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x101bfc  stfld    int32 <ParseXmlDeclarationAsync>d__507::<originalSbLen>5__5
0x101c01  ldloc.1
0x101c02  ldarg.0
0x101c03  ldfld    int32 <ParseXmlDeclarationAsync>d__507::<xmlDeclState>5__3
0x101c08  brfalse.s loc_101C12
0x101c0a  ldarg.0
0x101c0b  ldfld    class [mscorlib]System.Text.StringBuilder <ParseXmlDeclarationAsync>d__507::<sb>5__2
0x101c10  br.s     loc_101C13
0x101c12  ldnull
0x101c13  call     instance class [mscorlib]System.Threading.Tasks.Task`1<int32> System.Xml.XmlTextReaderImpl::EatWhitespacesAsync(class [mscorlib]System.Text.StringBuilder sb)
0x101c18  ldc.i4.0
0x101c19  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<int32>::ConfigureAwait(!!T0)
0x101c1e  stloc.s  5
0x101c20  ldloca.s 5
0x101c22  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<int32>::GetAwaiter()
0x101c27  stloc.s  0xA
0x101c29  ldloca.s 0xA
0x101c2b  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>::get_IsCompleted()
0x101c30  brtrue.s loc_101C73
0x101c32  ldarg.0
0x101c33  ldc.i4.1
0x101c34  dup
0x101c35  stloc.0
0x101c36  stfld    int32 <ParseXmlDeclarationAsync>d__507::<>1__state
0x101c3b  ldarg.0
0x101c3c  ldloc.s  0xA
0x101c3e  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <ParseXmlDeclarationAsync>d__507::<>u__1
0x101c43  ldarg.0
0x101c44  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <ParseXmlDeclarationAsync>d__507::<>t__builder
0x101c49  ldloca.s 0xA
0x101c4b  ldarg.0
0x101c4c  call     T0x2B0001DF
0x101c51  leave    loc_102931
0x101c56  ldarg.0
0x101c57  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <ParseXmlDeclarationAsync>d__507::<>u__1
0x101c5c  stloc.s  0xA
0x101c5e  ldarg.0
0x101c5f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <ParseXmlDeclarationAsync>d__507::<>u__1
0x101c64  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>
0x101c6a  ldarg.0
0x101c6b  ldc.i4.m1
0x101c6c  dup
0x101c6d  stloc.0
0x101c6e  stfld    int32 <ParseXmlDeclarationAsync>d__507::<>1__state
0x101c73  ldloca.s 0xA
0x101c75  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>::GetResult()
0x101c7a  stloc.s  9
0x101c7c  ldloc.s  9
0x101c7e  stloc.s  6
0x101c80  ldloc.1
0x101c81  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x101c86  ldfld    char[] ParsingState::chars
0x101c8b  ldloc.1
0x101c8c  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x101c91  ldfld    int32 ParsingState::charPos
0x101c96  ldelem.u2
0x101c97  ldc.i4.s 0x3F
0x101c99  bne.un   loc_101F0A
0x101c9e  ldarg.0
0x101c9f  ldfld    class [mscorlib]System.Text.StringBuilder <ParseXmlDeclarationAsync>d__507::<sb>5__2
0x101ca4  ldarg.0
0x101ca5  ldfld    int32 <ParseXmlDeclarationAsync>d__507::<originalSbLen>5__5
0x101caa  callvirt instance void [mscorlib]System.Text.StringBuilder::set_Length(int32)
0x101caf  ldloc.1
0x101cb0  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x101cb5  ldfld    char[] ParsingState::chars
0x101cba  ldloc.1
0x101cbb  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x101cc0  ldfld    int32 ParsingState::charPos
0x101cc5  ldc.i4.1
0x101cc6  add
0x101cc7  ldelem.u2
0x101cc8  ldc.i4.s 0x3E
0x101cca  bne.un   loc_101EE2
0x101ccf  ldarg.0
0x101cd0  ldfld    int32 <ParseXmlDeclarationAsync>d__507::<xmlDeclState>5__3
0x101cd5  brtrue.s loc_101CF1
0x101cd7  ldloc.1
0x101cd8  ldarg.0
0x101cd9  ldfld    bool <ParseXmlDeclarationAsync>d__507::isTextDecl
0x101cde  brtrue.s loc_101CE7
0x101ce0  ldstr    aXmlInvalidxmld// "Xml_InvalidXmlDecl"
0x101ce5  br.s     loc_101CEC
0x101ce7  ldstr    aXmlInvalidtext// "Xml_InvalidTextDecl"
0x101cec  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res)
0x101cf1  ldloc.1
0x101cf2  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x101cf7  ldflda   int32 ParsingState::charPos
0x101cfc  dup
0x101cfd  ldind.i4
0x101cfe  ldc.i4.2
0x101cff  add
0x101d00  stind.i4
0x101d01  ldarg.0
0x101d02  ldfld    bool <ParseXmlDeclarationAsync>d__507::isTextDecl
0x101d07  brtrue.s loc_101D3F
0x101d09  ldloc.1
0x101d0a  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x101d0f  ldarg.0
0x101d10  ldfld    class [mscorlib]System.Text.StringBuilder <ParseXmlDeclarationAsync>d__507::<sb>5__2
0x101d15  callvirt instance string [mscorlib]System.Object::ToString()
0x101d1a  callvirt instance void NodeData::SetValue(string value)
0x101d1f  ldarg.0
0x101d20  ldfld    class [mscorlib]System.Text.StringBuilder <ParseXmlDeclarationAsync>d__507::<sb>5__2
0x101d25  ldc.i4.0
0x101d26  callvirt instance void [mscorlib]System.Text.StringBuilder::set_Length(int32)
0x101d2b  ldloc.1
0x101d2c  ldloc.1
0x101d2d  ldfld    valuetype ParsingFunction System.Xml.XmlTextReaderImpl::parsingFunction
0x101d32  stfld    valuetype ParsingFunction System.Xml.XmlTextReaderImpl::nextParsingFunction
0x101d37  ldloc.1
0x101d38  ldc.i4.s 9
0x101d3a  stfld    valuetype ParsingFunction System.Xml.XmlTextReaderImpl::parsingFunction
0x101d3f  ldarg.0
0x101d40  ldfld    class [mscorlib]System.Text.Encoding <ParseXmlDeclarationAsync>d__507::<encoding>5__4
0x101d45  brtrue   loc_101E61
0x101d4a  ldarg.0
0x101d4b  ldfld    bool <ParseXmlDeclarationAsync>d__507::isTextDecl
0x101d50  brfalse.s loc_101D5D
0x101d52  ldloc.1
0x101d53  ldstr    aXmlInvalidtext// "Xml_InvalidTextDecl"
0x101d58  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res)
0x101d5d  ldloc.1
0x101d5e  ldfld    bool System.Xml.XmlTextReaderImpl::afterResetState
0x101d63  brfalse.s loc_101DE2
0x101d65  ldloc.1
0x101d66  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x101d6b  ldfld    class [mscorlib]System.Text.Encoding ParsingState::encoding
0x101d70  callvirt instance string [mscorlib]System.Text.Encoding::get_WebName()
0x101d75  stloc.s  0xB
0x101d77  ldloc.s  0xB
0x101d79  ldstr    aUtf8// "utf-8"
0x101d7e  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x101d83  brfalse.s loc_101DE2
0x101d85  ldloc.s  0xB
0x101d87  ldstr    aUtf16// "utf-16"
0x101d8c  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x101d91  brfalse.s loc_101DE2
0x101d93  ldloc.s  0xB
0x101d95  ldstr    aUtf16be// "utf-16BE"
0x101d9a  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x101d9f  brfalse.s loc_101DE2
0x101da1  ldloc.1
0x101da2  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x101da7  ldfld    class [mscorlib]System.Text.Encoding ParsingState::encoding
0x101dac  isinst   System.Xml.Ucs4Encoding
0x101db1  brtrue.s loc_101DE2
0x101db3  ldloc.1
0x101db4  ldstr    aXmlEncodingswi// "Xml_EncodingSwitchAfterResetState"
0x101db9  ldloc.1
0x101dba  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x101dbf  ldfld    class [mscorlib]System.Text.Encoding ParsingState::encoding
0x101dc4  ldstr    aA// "A"
0x101dc9  callvirt instance int32 [mscorlib]System.Text.Encoding::GetByteCount(string)
0x101dce  ldc.i4.1
0x101dcf  beq.s    loc_101DD8
0x101dd1  ldstr    aUtf16_0// "UTF-16"
0x101dd6  br.s     loc_101DDD
0x101dd8  ldstr    aUtf8_0// "UTF-8"
0x101ddd  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res, string arg)
0x101de2  ldloc.1
0x101de3  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x101de8  ldfld    class [mscorlib]System.Text.Decoder ParsingState::decoder
0x101ded  isinst   System.Xml.SafeAsciiDecoder
0x101df2  brfalse  loc_101ECF
0x101df7  ldloc.1
0x101df8  call     instance class [mscorlib]System.Threading.Tasks.Task System.Xml.XmlTextReaderImpl::SwitchEncodingToUTF8Async()
0x101dfd  ldc.i4.0
0x101dfe  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x101e03  stloc.s  0xD
0x101e05  ldloca.s 0xD
  ... truncated ...
```
