# <ReadValueChunkAsync>d__490::MoveNext

- ea: `0x100440`
- end: `0x100819`
- name: `<ReadValueChunkAsync>d__490::MoveNext`
- size: `985`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0xf0f0`
- `0x22930`
- `0x29740`
- `0x324e0`
- `0x32510`
- `0x342a0`
- `0x622f0`
- `0xfeb70`
- `0xfeb80`
- `0xfec30`
- `0x100440`

## string_xrefs

- `0x10046c`: `Xml_InvalidReadValueChunk`
- `0x10060b`: `Xml_NotEnoughSpaceForSurrogatePair`
- `0x1007b4`: `Xml_NotEnoughSpaceForSurrogatePair`

## pseudocode

```c

```

## disassembly

```asm
0x100440  ldarg.0
0x100441  ldfld    int32 <ReadValueChunkAsync>d__490::<>1__state
0x100446  stloc.0
0x100447  ldarg.0
0x100448  ldfld    class System.Xml.XmlTextReaderImpl <ReadValueChunkAsync>d__490::<>4__this
0x10044d  stloc.1
0x10044e  ldloc.0
0x10044f  brfalse  loc_100695
0x100454  ldloc.1
0x100455  call     instance void System.Xml.XmlTextReaderImpl::CheckAsyncCall()
0x10045a  ldloc.1
0x10045b  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x100460  ldfld    valuetype System.Xml.XmlNodeType NodeData::type
0x100465  call     bool System.Xml.XmlReader::HasValueInternal(valuetype System.Xml.XmlNodeType nodeType)
0x10046a  brtrue.s loc_100495
0x10046c  ldstr    aXmlInvalidread_1// "Xml_InvalidReadValueChunk"
0x100471  ldc.i4.1
0x100472  newarr   [mscorlib]System.Object
0x100477  dup
0x100478  ldc.i4.0
0x100479  ldloc.1
0x10047a  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x10047f  ldfld    valuetype System.Xml.XmlNodeType NodeData::type
0x100484  box      System.Xml.XmlNodeType
0x100489  stelem.ref
0x10048a  call     string System.Xml.Res::GetString(string name, object[] args)
0x10048f  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x100494  throw
0x100495  ldarg.0
0x100496  ldfld    char[] <ReadValueChunkAsync>d__490::buffer
0x10049b  brtrue.s loc_1004A8
0x10049d  ldstr    aBuffer// "buffer"
0x1004a2  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1004a7  throw
0x1004a8  ldarg.0
0x1004a9  ldfld    int32 <ReadValueChunkAsync>d__490::count
0x1004ae  ldc.i4.0
0x1004af  bge.s    loc_1004BC
0x1004b1  ldstr    aCount// "count"
0x1004b6  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x1004bb  throw
0x1004bc  ldarg.0
0x1004bd  ldfld    int32 <ReadValueChunkAsync>d__490::index
0x1004c2  ldc.i4.0
0x1004c3  bge.s    loc_1004D0
0x1004c5  ldstr    aIndex// "index"
0x1004ca  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x1004cf  throw
0x1004d0  ldarg.0
0x1004d1  ldfld    char[] <ReadValueChunkAsync>d__490::buffer
0x1004d6  ldlen
0x1004d7  conv.i4
0x1004d8  ldarg.0
0x1004d9  ldfld    int32 <ReadValueChunkAsync>d__490::index
0x1004de  sub
0x1004df  ldarg.0
0x1004e0  ldfld    int32 <ReadValueChunkAsync>d__490::count
0x1004e5  bge.s    loc_1004F2
0x1004e7  ldstr    aCount// "count"
0x1004ec  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x1004f1  throw
0x1004f2  ldloc.1
0x1004f3  ldfld    valuetype ParsingFunction System.Xml.XmlTextReaderImpl::parsingFunction
0x1004f8  ldc.i4.s 0x17
0x1004fa  beq.s    loc_10054F
0x1004fc  ldloc.1
0x1004fd  ldfld    valuetype System.Xml.ReadState System.Xml.XmlTextReaderImpl::readState
0x100502  ldc.i4.1
0x100503  beq.s    loc_10050C
0x100505  ldc.i4.0
0x100506  stloc.2
0x100507  leave    loc_100804
0x10050c  ldloc.1
0x10050d  ldfld    valuetype ParsingFunction System.Xml.XmlTextReaderImpl::parsingFunction
0x100512  ldc.i4.s 0x15
0x100514  bne.un.s loc_100520
0x100516  ldloc.1
0x100517  ldc.i4.s 0xB
0x100519  stfld    valuetype IncrementalReadState System.Xml.XmlTextReaderImpl::incReadState
0x10051e  br.s     loc_100540
0x100520  ldloc.1
0x100521  ldc.i4.s 0xA
0x100523  stfld    valuetype IncrementalReadState System.Xml.XmlTextReaderImpl::incReadState
0x100528  ldloc.1
0x100529  ldloc.1
0x10052a  ldfld    valuetype ParsingFunction System.Xml.XmlTextReaderImpl::nextParsingFunction
0x10052f  stfld    valuetype ParsingFunction System.Xml.XmlTextReaderImpl::nextNextParsingFunction
0x100534  ldloc.1
0x100535  ldloc.1
0x100536  ldfld    valuetype ParsingFunction System.Xml.XmlTextReaderImpl::parsingFunction
0x10053b  stfld    valuetype ParsingFunction System.Xml.XmlTextReaderImpl::nextParsingFunction
0x100540  ldloc.1
0x100541  ldc.i4.s 0x17
0x100543  stfld    valuetype ParsingFunction System.Xml.XmlTextReaderImpl::parsingFunction
0x100548  ldloc.1
0x100549  ldc.i4.0
0x10054a  stfld    int32 System.Xml.XmlTextReaderImpl::readValueOffset
0x10054f  ldarg.0
0x100550  ldfld    int32 <ReadValueChunkAsync>d__490::count
0x100555  brtrue.s loc_10055E
0x100557  ldc.i4.0
0x100558  stloc.2
0x100559  leave    loc_100804
0x10055e  ldarg.0
0x10055f  ldc.i4.0
0x100560  stfld    int32 <ReadValueChunkAsync>d__490::<readCount>5__2
0x100565  ldloc.1
0x100566  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x10056b  ldloc.1
0x10056c  ldfld    int32 System.Xml.XmlTextReaderImpl::readValueOffset
0x100571  ldarg.0
0x100572  ldfld    char[] <ReadValueChunkAsync>d__490::buffer
0x100577  ldarg.0
0x100578  ldfld    int32 <ReadValueChunkAsync>d__490::index
0x10057d  ldarg.0
0x10057e  ldfld    int32 <ReadValueChunkAsync>d__490::<readCount>5__2
0x100583  add
0x100584  ldarg.0
0x100585  ldfld    int32 <ReadValueChunkAsync>d__490::count
0x10058a  ldarg.0
0x10058b  ldfld    int32 <ReadValueChunkAsync>d__490::<readCount>5__2
0x100590  sub
0x100591  callvirt instance int32 NodeData::CopyTo(int32 valueOffset, char[] buffer, int32 offset, int32 length)
0x100596  stloc.3
0x100597  ldarg.0
0x100598  ldarg.0
0x100599  ldfld    int32 <ReadValueChunkAsync>d__490::<readCount>5__2
0x10059e  ldloc.3
0x10059f  add
0x1005a0  stfld    int32 <ReadValueChunkAsync>d__490::<readCount>5__2
0x1005a5  ldloc.1
0x1005a6  ldloc.1
0x1005a7  ldfld    int32 System.Xml.XmlTextReaderImpl::readValueOffset
0x1005ac  ldloc.3
0x1005ad  add
0x1005ae  stfld    int32 System.Xml.XmlTextReaderImpl::readValueOffset
0x1005b3  ldarg.0
0x1005b4  ldfld    int32 <ReadValueChunkAsync>d__490::<readCount>5__2
0x1005b9  ldarg.0
0x1005ba  ldfld    int32 <ReadValueChunkAsync>d__490::count
0x1005bf  bne.un.s loc_100621
0x1005c1  ldarg.0
0x1005c2  ldfld    char[] <ReadValueChunkAsync>d__490::buffer
0x1005c7  ldarg.0
0x1005c8  ldfld    int32 <ReadValueChunkAsync>d__490::index
0x1005cd  ldarg.0
0x1005ce  ldfld    int32 <ReadValueChunkAsync>d__490::count
0x1005d3  add
0x1005d4  ldc.i4.1
0x1005d5  sub
0x1005d6  ldelem.u2
0x1005d7  stloc.s  4
0x1005d9  ldloc.s  4
0x1005db  call     bool System.Xml.XmlCharType::IsHighSurrogate(int32 ch)
0x1005e0  brfalse.s loc_100615
0x1005e2  ldarg.0
0x1005e3  ldfld    int32 <ReadValueChunkAsync>d__490::<readCount>5__2
0x1005e8  stloc.s  5
0x1005ea  ldarg.0
0x1005eb  ldloc.s  5
0x1005ed  ldc.i4.1
0x1005ee  sub
0x1005ef  stfld    int32 <ReadValueChunkAsync>d__490::<readCount>5__2
0x1005f4  ldloc.1
0x1005f5  ldloc.1
0x1005f6  ldfld    int32 System.Xml.XmlTextReaderImpl::readValueOffset
0x1005fb  ldc.i4.1
0x1005fc  sub
0x1005fd  stfld    int32 System.Xml.XmlTextReaderImpl::readValueOffset
0x100602  ldarg.0
0x100603  ldfld    int32 <ReadValueChunkAsync>d__490::<readCount>5__2
0x100608  brtrue.s loc_100615
0x10060a  ldloc.1
0x10060b  ldstr    aXmlNotenoughsp// "Xml_NotEnoughSpaceForSurrogatePair"
0x100610  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res)
0x100615  ldarg.0
0x100616  ldfld    int32 <ReadValueChunkAsync>d__490::<readCount>5__2
0x10061b  stloc.2
0x10061c  leave    loc_100804
0x100621  ldloc.1
0x100622  ldfld    valuetype IncrementalReadState System.Xml.XmlTextReaderImpl::incReadState
0x100627  ldc.i4.s 0xB
0x100629  bne.un   loc_1007E2
0x10062e  ldloc.1
0x10062f  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x100634  ldsfld   string [mscorlib]System.String::Empty
0x100639  callvirt instance void NodeData::SetValue(string value)
0x10063e  ldc.i4.0
0x10063f  stloc.s  6
0x100641  ldc.i4.0
0x100642  stloc.s  7
0x100644  ldc.i4.0
0x100645  stloc.s  8
0x100647  br       loc_10073F
0x10064c  ldc.i4.0
0x10064d  stloc.s  9
0x10064f  ldloc.1
0x100650  ldloc.s  9
0x100652  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Tuple`4<int32, int32, int32, bool>> System.Xml.XmlTextReaderImpl::ParseTextAsync(int32 outOrChars)
0x100657  ldc.i4.0
0x100658  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Tuple`4<int32, int32, int32, bool>>::ConfigureAwait(!!T0)
0x10065d  stloc.s  0xE
0x10065f  ldloca.s 0xE
0x100661  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [mscorlib]System.Tuple`4<int32, int32, int32, bool>>::GetAwaiter()
0x100666  stloc.s  0xD
0x100668  ldloca.s 0xD
0x10066a  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`4<int32, int32, int32, bool>>::get_IsCompleted()
0x10066f  brtrue.s loc_1006B2
0x100671  ldarg.0
0x100672  ldc.i4.0
0x100673  dup
0x100674  stloc.0
0x100675  stfld    int32 <ReadValueChunkAsync>d__490::<>1__state
0x10067a  ldarg.0
0x10067b  ldloc.s  0xD
0x10067d  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`4<int32, int32, int32, bool>> <ReadValueChunkAsync>d__490::<>u__1
0x100682  ldarg.0
0x100683  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <ReadValueChunkAsync>d__490::<>t__builder
0x100688  ldloca.s 0xD
0x10068a  ldarg.0
0x10068b  call     T0x2B0001D5
0x100690  leave    loc_100818
0x100695  ldarg.0
0x100696  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`4<int32, int32, int32, bool>> <ReadValueChunkAsync>d__490::<>u__1
0x10069b  stloc.s  0xD
0x10069d  ldarg.0
0x10069e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`4<int32, int32, int32, bool>> <ReadValueChunkAsync>d__490::<>u__1
0x1006a3  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`4<int32, int32, int32, bool>>
0x1006a9  ldarg.0
0x1006aa  ldc.i4.m1
0x1006ab  dup
0x1006ac  stloc.0
0x1006ad  stfld    int32 <ReadValueChunkAsync>d__490::<>1__state
0x1006b2  ldloca.s 0xD
0x1006b4  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`4<int32, int32, int32, bool>>::GetResult()
0x1006b9  stloc.s  0xC
0x1006bb  ldloc.s  0xC
0x1006bd  stloc.s  0xA
0x1006bf  ldloc.s  0xA
0x1006c1  callvirt instance var<u1> class [mscorlib]System.Tuple`4<int32, int32, int32, bool>::get_Item1()
0x1006c6  stloc.s  7
0x1006c8  ldloc.s  0xA
0x1006ca  callvirt instance var<u1> class [mscorlib]System.Tuple`4<int32, int32, int32, bool>::get_Item2()
0x1006cf  stloc.s  8
0x1006d1  ldloc.s  0xA
0x1006d3  callvirt instance var<u1> class [mscorlib]System.Tuple`4<int32, int32, int32, bool>::get_Item3()
0x1006d8  stloc.s  9
0x1006da  ldloc.s  0xA
0x1006dc  callvirt instance var<u1> class [mscorlib]System.Tuple`4<int32, int32, int32, bool>::get_Item4()
0x1006e1  stloc.s  6
0x1006e3  ldarg.0
0x1006e4  ldfld    int32 <ReadValueChunkAsync>d__490::count
0x1006e9  ldarg.0
0x1006ea  ldfld    int32 <ReadValueChunkAsync>d__490::<readCount>5__2
0x1006ef  sub
0x1006f0  stloc.s  0xB
0x1006f2  ldloc.s  0xB
0x1006f4  ldloc.s  8
0x1006f6  ldloc.s  7
0x1006f8  sub
0x1006f9  ble.s    loc_100702
0x1006fb  ldloc.s  8
0x1006fd  ldloc.s  7
0x1006ff  sub
0x100700  stloc.s  0xB
0x100702  ldloc.1
0x100703  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x100708  ldfld    char[] ParsingState::chars
0x10070d  ldloc.s  7
0x10070f  ldarg.0
0x100710  ldfld    char[] <ReadValueChunkAsync>d__490::buffer
0x100715  ldarg.0
0x100716  ldfld    int32 <ReadValueChunkAsync>d__490::index
0x10071b  ldarg.0
0x10071c  ldfld    int32 <ReadValueChunkAsync>d__490::<readCount>5__2
0x100721  add
0x100722  ldloc.s  0xB
0x100724  call     void System.Xml.XmlTextReaderImpl::BlockCopyChars(char[] src, int32 srcOffset, char[] dst, int32 dstOffset, int32 count)
0x100729  ldarg.0
0x10072a  ldarg.0
0x10072b  ldfld    int32 <ReadValueChunkAsync>d__490::<readCount>5__2
0x100730  ldloc.s  0xB
0x100732  add
0x100733  stfld    int32 <ReadValueChunkAsync>d__490::<readCount>5__2
0x100738  ldloc.s  7
0x10073a  ldloc.s  0xB
0x10073c  add
0x10073d  stloc.s  7
0x10073f  ldarg.0
0x100740  ldfld    int32 <ReadValueChunkAsync>d__490::<readCount>5__2
0x100745  ldarg.0
0x100746  ldfld    int32 <ReadValueChunkAsync>d__490::count
0x10074b  bge.s    loc_100754
0x10074d  ldloc.s  6
0x10074f  brfalse  loc_10064C
0x100754  ldloc.1
0x100755  ldloc.s  6
0x100757  brtrue.s loc_10075D
0x100759  ldc.i4.s 0xB
0x10075b  br.s     loc_10075F
  ... truncated ...
```
