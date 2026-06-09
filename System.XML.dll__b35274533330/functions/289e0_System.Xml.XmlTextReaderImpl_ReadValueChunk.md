# System.Xml.XmlTextReaderImpl::ReadValueChunk

- ea: `0x289e0`
- end: `0x28bf4`
- name: `System.Xml.XmlTextReaderImpl::ReadValueChunk`
- size: `532`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config`

## callees

- `0xf0f0`
- `0x22930`
- `0x289e0`
- `0x29740`
- `0x2d4b0`
- `0x324e0`
- `0x622f0`
- `0xfeb70`
- `0xfeb80`
- `0xfec30`

## string_xrefs

- `0x289f2`: `Xml_InvalidReadValueChunk`
- `0x28b0e`: `Xml_NotEnoughSpaceForSurrogatePair`
- `0x28bc4`: `Xml_NotEnoughSpaceForSurrogatePair`

## pseudocode

```c

```

## disassembly

```asm
0x289e0  ldarg.0
0x289e1  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x289e6  ldfld    valuetype System.Xml.XmlNodeType NodeData::type
0x289eb  call     bool System.Xml.XmlReader::HasValueInternal(valuetype System.Xml.XmlNodeType nodeType)
0x289f0  brtrue.s loc_28A1B
0x289f2  ldstr    aXmlInvalidread_1// "Xml_InvalidReadValueChunk"
0x289f7  ldc.i4.1
0x289f8  newarr   [mscorlib]System.Object
0x289fd  dup
0x289fe  ldc.i4.0
0x289ff  ldarg.0
0x28a00  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x28a05  ldfld    valuetype System.Xml.XmlNodeType NodeData::type
0x28a0a  box      System.Xml.XmlNodeType
0x28a0f  stelem.ref
0x28a10  call     string System.Xml.Res::GetString(string name, object[] args)
0x28a15  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x28a1a  throw
0x28a1b  ldarg.1
0x28a1c  brtrue.s loc_28A29
0x28a1e  ldstr    aBuffer// "buffer"
0x28a23  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x28a28  throw
0x28a29  ldarg.3
0x28a2a  ldc.i4.0
0x28a2b  bge.s    loc_28A38
0x28a2d  ldstr    aCount// "count"
0x28a32  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x28a37  throw
0x28a38  ldarg.2
0x28a39  ldc.i4.0
0x28a3a  bge.s    loc_28A47
0x28a3c  ldstr    aIndex// "index"
0x28a41  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x28a46  throw
0x28a47  ldarg.1
0x28a48  ldlen
0x28a49  conv.i4
0x28a4a  ldarg.2
0x28a4b  sub
0x28a4c  ldarg.3
0x28a4d  bge.s    loc_28A5A
0x28a4f  ldstr    aCount// "count"
0x28a54  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x28a59  throw
0x28a5a  ldarg.0
0x28a5b  ldfld    valuetype ParsingFunction System.Xml.XmlTextReaderImpl::parsingFunction
0x28a60  ldc.i4.s 0x17
0x28a62  beq.s    loc_28AB2
0x28a64  ldarg.0
0x28a65  ldfld    valuetype System.Xml.ReadState System.Xml.XmlTextReaderImpl::readState
0x28a6a  ldc.i4.1
0x28a6b  beq.s    loc_28A6F
0x28a6d  ldc.i4.0
0x28a6e  ret
0x28a6f  ldarg.0
0x28a70  ldfld    valuetype ParsingFunction System.Xml.XmlTextReaderImpl::parsingFunction
0x28a75  ldc.i4.s 0x15
0x28a77  bne.un.s loc_28A83
0x28a79  ldarg.0
0x28a7a  ldc.i4.s 0xB
0x28a7c  stfld    valuetype IncrementalReadState System.Xml.XmlTextReaderImpl::incReadState
0x28a81  br.s     loc_28AA3
0x28a83  ldarg.0
0x28a84  ldc.i4.s 0xA
0x28a86  stfld    valuetype IncrementalReadState System.Xml.XmlTextReaderImpl::incReadState
0x28a8b  ldarg.0
0x28a8c  ldarg.0
0x28a8d  ldfld    valuetype ParsingFunction System.Xml.XmlTextReaderImpl::nextParsingFunction
0x28a92  stfld    valuetype ParsingFunction System.Xml.XmlTextReaderImpl::nextNextParsingFunction
0x28a97  ldarg.0
0x28a98  ldarg.0
0x28a99  ldfld    valuetype ParsingFunction System.Xml.XmlTextReaderImpl::parsingFunction
0x28a9e  stfld    valuetype ParsingFunction System.Xml.XmlTextReaderImpl::nextParsingFunction
0x28aa3  ldarg.0
0x28aa4  ldc.i4.s 0x17
0x28aa6  stfld    valuetype ParsingFunction System.Xml.XmlTextReaderImpl::parsingFunction
0x28aab  ldarg.0
0x28aac  ldc.i4.0
0x28aad  stfld    int32 System.Xml.XmlTextReaderImpl::readValueOffset
0x28ab2  ldarg.3
0x28ab3  brtrue.s loc_28AB7
0x28ab5  ldc.i4.0
0x28ab6  ret
0x28ab7  ldc.i4.0
0x28ab8  stloc.0
0x28ab9  ldarg.0
0x28aba  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x28abf  ldarg.0
0x28ac0  ldfld    int32 System.Xml.XmlTextReaderImpl::readValueOffset
0x28ac5  ldarg.1
0x28ac6  ldarg.2
0x28ac7  ldloc.0
0x28ac8  add
0x28ac9  ldarg.3
0x28aca  ldloc.0
0x28acb  sub
0x28acc  callvirt instance int32 NodeData::CopyTo(int32 valueOffset, char[] buffer, int32 offset, int32 length)
0x28ad1  stloc.1
0x28ad2  ldloc.0
0x28ad3  ldloc.1
0x28ad4  add
0x28ad5  stloc.0
0x28ad6  ldarg.0
0x28ad7  ldarg.0
0x28ad8  ldfld    int32 System.Xml.XmlTextReaderImpl::readValueOffset
0x28add  ldloc.1
0x28ade  add
0x28adf  stfld    int32 System.Xml.XmlTextReaderImpl::readValueOffset
0x28ae4  ldloc.0
0x28ae5  ldarg.3
0x28ae6  bne.un.s loc_28B1A
0x28ae8  ldarg.1
0x28ae9  ldarg.2
0x28aea  ldarg.3
0x28aeb  add
0x28aec  ldc.i4.1
0x28aed  sub
0x28aee  ldelem.u2
0x28aef  stloc.2
0x28af0  ldloc.2
0x28af1  call     bool System.Xml.XmlCharType::IsHighSurrogate(int32 ch)
0x28af6  brfalse.s loc_28B18
0x28af8  ldloc.0
0x28af9  ldc.i4.1
0x28afa  sub
0x28afb  stloc.0
0x28afc  ldarg.0
0x28afd  ldarg.0
0x28afe  ldfld    int32 System.Xml.XmlTextReaderImpl::readValueOffset
0x28b03  ldc.i4.1
0x28b04  sub
0x28b05  stfld    int32 System.Xml.XmlTextReaderImpl::readValueOffset
0x28b0a  ldloc.0
0x28b0b  brtrue.s loc_28B18
0x28b0d  ldarg.0
0x28b0e  ldstr    aXmlNotenoughsp// "Xml_NotEnoughSpaceForSurrogatePair"
0x28b13  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res)
0x28b18  ldloc.0
0x28b19  ret
0x28b1a  ldarg.0
0x28b1b  ldfld    valuetype IncrementalReadState System.Xml.XmlTextReaderImpl::incReadState
0x28b20  ldc.i4.s 0xB
0x28b22  bne.un   loc_28BF2
0x28b27  ldarg.0
0x28b28  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x28b2d  ldsfld   string [mscorlib]System.String::Empty
0x28b32  callvirt instance void NodeData::SetValue(string value)
0x28b37  ldc.i4.0
0x28b38  stloc.3
0x28b39  ldc.i4.0
0x28b3a  stloc.s  4
0x28b3c  ldc.i4.0
0x28b3d  stloc.s  5
0x28b3f  br.s     loc_28B8A
0x28b41  ldc.i4.0
0x28b42  stloc.s  6
0x28b44  ldarg.0
0x28b45  ldloca.s 4
0x28b47  ldloca.s 5
0x28b49  ldloca.s 6
0x28b4b  call     instance bool System.Xml.XmlTextReaderImpl::ParseText([out] int32& startPos, [out] int32& endPos, int32& outOrChars)
0x28b50  stloc.3
0x28b51  ldarg.3
0x28b52  ldloc.0
0x28b53  sub
0x28b54  stloc.s  7
0x28b56  ldloc.s  7
0x28b58  ldloc.s  5
0x28b5a  ldloc.s  4
0x28b5c  sub
0x28b5d  ble.s    loc_28B66
0x28b5f  ldloc.s  5
0x28b61  ldloc.s  4
0x28b63  sub
0x28b64  stloc.s  7
0x28b66  ldarg.0
0x28b67  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x28b6c  ldfld    char[] ParsingState::chars
0x28b71  ldloc.s  4
0x28b73  ldarg.1
0x28b74  ldarg.2
0x28b75  ldloc.0
0x28b76  add
0x28b77  ldloc.s  7
0x28b79  call     void System.Xml.XmlTextReaderImpl::BlockCopyChars(char[] src, int32 srcOffset, char[] dst, int32 dstOffset, int32 count)
0x28b7e  ldloc.0
0x28b7f  ldloc.s  7
0x28b81  add
0x28b82  stloc.0
0x28b83  ldloc.s  4
0x28b85  ldloc.s  7
0x28b87  add
0x28b88  stloc.s  4
0x28b8a  ldloc.0
0x28b8b  ldarg.3
0x28b8c  bge.s    loc_28B91
0x28b8e  ldloc.3
0x28b8f  brfalse.s loc_28B41
0x28b91  ldarg.0
0x28b92  ldloc.3
0x28b93  brtrue.s loc_28B99
0x28b95  ldc.i4.s 0xB
0x28b97  br.s     loc_28B9B
0x28b99  ldc.i4.s 0xA
0x28b9b  stfld    valuetype IncrementalReadState System.Xml.XmlTextReaderImpl::incReadState
0x28ba0  ldloc.0
0x28ba1  ldarg.3
0x28ba2  bne.un.s loc_28BCE
0x28ba4  ldarg.1
0x28ba5  ldarg.2
0x28ba6  ldarg.3
0x28ba7  add
0x28ba8  ldc.i4.1
0x28ba9  sub
0x28baa  ldelem.u2
0x28bab  stloc.s  8
0x28bad  ldloc.s  8
0x28baf  call     bool System.Xml.XmlCharType::IsHighSurrogate(int32 ch)
0x28bb4  brfalse.s loc_28BCE
0x28bb6  ldloc.0
0x28bb7  ldc.i4.1
0x28bb8  sub
0x28bb9  stloc.0
0x28bba  ldloc.s  4
0x28bbc  ldc.i4.1
0x28bbd  sub
0x28bbe  stloc.s  4
0x28bc0  ldloc.0
0x28bc1  brtrue.s loc_28BCE
0x28bc3  ldarg.0
0x28bc4  ldstr    aXmlNotenoughsp// "Xml_NotEnoughSpaceForSurrogatePair"
0x28bc9  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res)
0x28bce  ldarg.0
0x28bcf  ldc.i4.0
0x28bd0  stfld    int32 System.Xml.XmlTextReaderImpl::readValueOffset
0x28bd5  ldarg.0
0x28bd6  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x28bdb  ldarg.0
0x28bdc  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x28be1  ldfld    char[] ParsingState::chars
0x28be6  ldloc.s  4
0x28be8  ldloc.s  5
0x28bea  ldloc.s  4
0x28bec  sub
0x28bed  callvirt instance void NodeData::SetValue(char[] chars, int32 startPos, int32 len)
0x28bf2  ldloc.0
0x28bf3  ret
```
