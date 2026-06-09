# <ParseQNameAsync>d__578::MoveNext

- ea: `0x10a0f0`
- end: `0x10a407`
- name: `<ParseQNameAsync>d__578::MoveNext`
- size: `791`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x12920`
- `0x12940`
- `0x296e0`
- `0x29700`
- `0x34f50`
- `0x10a0f0`

## string_xrefs

- `0x10a18a`: `Xml_BadStartNameChar`
- `0x10a295`: `Xml_BadNameChar`
- `0x10a23b`: `Xml_UnexpectedEOF`
- `0x10a392`: `Xml_UnexpectedEOF`

## pseudocode

```c

```

## disassembly

```asm
0x10a0f0  ldarg.0
0x10a0f1  ldfld    int32 <ParseQNameAsync>d__578::<>1__state
0x10a0f6  stloc.0
0x10a0f7  ldarg.0
0x10a0f8  ldfld    class System.Xml.XmlTextReaderImpl <ParseQNameAsync>d__578::<>4__this
0x10a0fd  stloc.1
0x10a0fe  ldloc.0
0x10a0ff  brfalse  loc_10A1F9
0x10a104  ldloc.0
0x10a105  ldc.i4.1
0x10a106  beq      loc_10A33D
0x10a10b  ldarg.0
0x10a10c  ldc.i4.m1
0x10a10d  stfld    int32 <ParseQNameAsync>d__578::<colonOffset>5__2
0x10a112  ldloc.1
0x10a113  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x10a118  ldfld    int32 ParsingState::charPos
0x10a11d  ldarg.0
0x10a11e  ldfld    int32 <ParseQNameAsync>d__578::startOffset
0x10a123  add
0x10a124  stloc.s  4
0x10a126  ldarg.0
0x10a127  ldloc.1
0x10a128  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x10a12d  ldfld    char[] ParsingState::chars
0x10a132  stfld    char[] <ParseQNameAsync>d__578::<chars>5__3
0x10a137  ldc.i4.0
0x10a138  stloc.s  5
0x10a13a  ldloc.1
0x10a13b  ldflda   valuetype System.Xml.XmlCharType System.Xml.XmlTextReaderImpl::xmlCharType
0x10a140  ldfld    unsigned int8* System.Xml.XmlCharType::charProperties
0x10a145  ldarg.0
0x10a146  ldfld    char[] <ParseQNameAsync>d__578::<chars>5__3
0x10a14b  ldloc.s  4
0x10a14d  ldelem.u2
0x10a14e  add
0x10a14f  ldind.u1
0x10a150  ldc.i4.4
0x10a151  and
0x10a152  brfalse.s loc_10A15C
0x10a154  ldloc.s  4
0x10a156  ldc.i4.1
0x10a157  add
0x10a158  stloc.s  4
0x10a15a  br.s     loc_10A1AC
0x10a15c  ldloc.s  4
0x10a15e  ldc.i4.1
0x10a15f  add
0x10a160  ldloc.1
0x10a161  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x10a166  ldfld    int32 ParsingState::charsUsed
0x10a16b  blt.s    loc_10A172
0x10a16d  ldc.i4.1
0x10a16e  stloc.s  5
0x10a170  br.s     loc_10A1AC
0x10a172  ldarg.0
0x10a173  ldfld    char[] <ParseQNameAsync>d__578::<chars>5__3
0x10a178  ldloc.s  4
0x10a17a  ldelem.u2
0x10a17b  ldc.i4.s 0x3A
0x10a17d  bne.un.s loc_10A187
0x10a17f  ldloc.1
0x10a180  ldfld    bool System.Xml.XmlTextReaderImpl::supportNamespaces
0x10a185  brfalse.s loc_10A1AC
0x10a187  ldloc.1
0x10a188  ldloc.s  4
0x10a18a  ldstr    aXmlBadstartnam// "Xml_BadStartNameChar"
0x10a18f  ldarg.0
0x10a190  ldfld    char[] <ParseQNameAsync>d__578::<chars>5__3
0x10a195  ldloc.1
0x10a196  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x10a19b  ldfld    int32 ParsingState::charsUsed
0x10a1a0  ldloc.s  4
0x10a1a2  call     string[] System.Xml.XmlException::BuildCharExceptionArgs(char[] data, int32 length, int32 invCharIndex)
0x10a1a7  call     instance void System.Xml.XmlTextReaderImpl::Throw(int32 pos, string res, string[] args)
0x10a1ac  ldloc.s  5
0x10a1ae  brfalse  loc_10A24A
0x10a1b3  ldloc.1
0x10a1b4  ldloc.s  4
0x10a1b6  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Tuple`2<int32, bool>> System.Xml.XmlTextReaderImpl::ReadDataInNameAsync(int32 pos)
0x10a1bb  ldc.i4.0
0x10a1bc  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Tuple`2<int32, bool>>::ConfigureAwait(!!T0)
0x10a1c1  stloc.s  9
0x10a1c3  ldloca.s 9
0x10a1c5  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [mscorlib]System.Tuple`2<int32, bool>>::GetAwaiter()
0x10a1ca  stloc.s  8
0x10a1cc  ldloca.s 8
0x10a1ce  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<int32, bool>>::get_IsCompleted()
0x10a1d3  brtrue.s loc_10A216
0x10a1d5  ldarg.0
0x10a1d6  ldc.i4.0
0x10a1d7  dup
0x10a1d8  stloc.0
0x10a1d9  stfld    int32 <ParseQNameAsync>d__578::<>1__state
0x10a1de  ldarg.0
0x10a1df  ldloc.s  8
0x10a1e1  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<int32, bool>> <ParseQNameAsync>d__578::<>u__1
0x10a1e6  ldarg.0
0x10a1e7  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Tuple`2<int32, int32>> <ParseQNameAsync>d__578::<>t__builder
0x10a1ec  ldloca.s 8
0x10a1ee  ldarg.0
0x10a1ef  call     T0x2B00021E
0x10a1f4  leave    loc_10A406
0x10a1f9  ldarg.0
0x10a1fa  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<int32, bool>> <ParseQNameAsync>d__578::<>u__1
0x10a1ff  stloc.s  8
0x10a201  ldarg.0
0x10a202  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<int32, bool>> <ParseQNameAsync>d__578::<>u__1
0x10a207  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<int32, bool>>
0x10a20d  ldarg.0
0x10a20e  ldc.i4.m1
0x10a20f  dup
0x10a210  stloc.0
0x10a211  stfld    int32 <ParseQNameAsync>d__578::<>1__state
0x10a216  ldloca.s 8
0x10a218  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<int32, bool>>::GetResult()
0x10a21d  stloc.s  7
0x10a21f  ldloc.s  7
0x10a221  stloc.s  6
0x10a223  ldloc.s  6
0x10a225  callvirt instance var<u1> class [mscorlib]System.Tuple`2<int32, bool>::get_Item1()
0x10a22a  stloc.s  4
0x10a22c  ldloc.s  6
0x10a22e  callvirt instance var<u1> class [mscorlib]System.Tuple`2<int32, bool>::get_Item2()
0x10a233  brtrue   loc_10A126
0x10a238  ldloc.1
0x10a239  ldloc.s  4
0x10a23b  ldstr    aXmlUnexpectede// "Xml_UnexpectedEOF"
0x10a240  ldstr    aName_0// "Name"
0x10a245  call     instance void System.Xml.XmlTextReaderImpl::Throw(int32 pos, string res, string arg)
0x10a24a  ldloc.1
0x10a24b  ldflda   valuetype System.Xml.XmlCharType System.Xml.XmlTextReaderImpl::xmlCharType
0x10a250  ldfld    unsigned int8* System.Xml.XmlCharType::charProperties
0x10a255  ldarg.0
0x10a256  ldfld    char[] <ParseQNameAsync>d__578::<chars>5__3
0x10a25b  ldloc.s  4
0x10a25d  ldelem.u2
0x10a25e  add
0x10a25f  ldind.u1
0x10a260  ldc.i4.8
0x10a261  and
0x10a262  brfalse.s loc_10A26C
0x10a264  ldloc.s  4
0x10a266  ldc.i4.1
0x10a267  add
0x10a268  stloc.s  4
0x10a26a  br.s     loc_10A24A
0x10a26c  ldarg.0
0x10a26d  ldfld    char[] <ParseQNameAsync>d__578::<chars>5__3
0x10a272  ldloc.s  4
0x10a274  ldelem.u2
0x10a275  ldc.i4.s 0x3A
0x10a277  bne.un.s loc_10A2E5
0x10a279  ldloc.1
0x10a27a  ldfld    bool System.Xml.XmlTextReaderImpl::supportNamespaces
0x10a27f  brfalse.s loc_10A2C6
0x10a281  ldarg.0
0x10a282  ldfld    int32 <ParseQNameAsync>d__578::<colonOffset>5__2
0x10a287  ldc.i4.m1
0x10a288  bne.un.s loc_10A292
0x10a28a  ldarg.0
0x10a28b  ldfld    bool <ParseQNameAsync>d__578::isQName
0x10a290  brtrue.s loc_10A2A7
0x10a292  ldloc.1
0x10a293  ldloc.s  4
0x10a295  ldstr    aXmlBadnamechar// "Xml_BadNameChar"
0x10a29a  ldc.i4.s 0x3A
0x10a29c  ldc.i4.0
0x10a29d  call     string[] System.Xml.XmlException::BuildCharExceptionArgs(char invChar, char nextChar)
0x10a2a2  call     instance void System.Xml.XmlTextReaderImpl::Throw(int32 pos, string res, string[] args)
0x10a2a7  ldarg.0
0x10a2a8  ldloc.s  4
0x10a2aa  ldloc.1
0x10a2ab  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x10a2b0  ldfld    int32 ParsingState::charPos
0x10a2b5  sub
0x10a2b6  stfld    int32 <ParseQNameAsync>d__578::<colonOffset>5__2
0x10a2bb  ldloc.s  4
0x10a2bd  ldc.i4.1
0x10a2be  add
0x10a2bf  stloc.s  4
0x10a2c1  br       loc_10A126
0x10a2c6  ldarg.0
0x10a2c7  ldloc.s  4
0x10a2c9  ldloc.1
0x10a2ca  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x10a2cf  ldfld    int32 ParsingState::charPos
0x10a2d4  sub
0x10a2d5  stfld    int32 <ParseQNameAsync>d__578::<colonOffset>5__2
0x10a2da  ldloc.s  4
0x10a2dc  ldc.i4.1
0x10a2dd  add
0x10a2de  stloc.s  4
0x10a2e0  br       loc_10A24A
0x10a2e5  ldloc.s  4
0x10a2e7  ldloc.1
0x10a2e8  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x10a2ed  ldfld    int32 ParsingState::charsUsed
0x10a2f2  bne.un   loc_10A3A1
0x10a2f7  ldloc.1
0x10a2f8  ldloc.s  4
0x10a2fa  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Tuple`2<int32, bool>> System.Xml.XmlTextReaderImpl::ReadDataInNameAsync(int32 pos)
0x10a2ff  ldc.i4.0
0x10a300  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Tuple`2<int32, bool>>::ConfigureAwait(!!T0)
0x10a305  stloc.s  9
0x10a307  ldloca.s 9
0x10a309  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [mscorlib]System.Tuple`2<int32, bool>>::GetAwaiter()
0x10a30e  stloc.s  0xC
0x10a310  ldloca.s 0xC
0x10a312  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<int32, bool>>::get_IsCompleted()
0x10a317  brtrue.s loc_10A35A
0x10a319  ldarg.0
0x10a31a  ldc.i4.1
0x10a31b  dup
0x10a31c  stloc.0
0x10a31d  stfld    int32 <ParseQNameAsync>d__578::<>1__state
0x10a322  ldarg.0
0x10a323  ldloc.s  0xC
0x10a325  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<int32, bool>> <ParseQNameAsync>d__578::<>u__1
0x10a32a  ldarg.0
0x10a32b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Tuple`2<int32, int32>> <ParseQNameAsync>d__578::<>t__builder
0x10a330  ldloca.s 0xC
0x10a332  ldarg.0
0x10a333  call     T0x2B00021E
0x10a338  leave    loc_10A406
0x10a33d  ldarg.0
0x10a33e  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<int32, bool>> <ParseQNameAsync>d__578::<>u__1
0x10a343  stloc.s  0xC
0x10a345  ldarg.0
0x10a346  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<int32, bool>> <ParseQNameAsync>d__578::<>u__1
0x10a34b  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<int32, bool>>
0x10a351  ldarg.0
0x10a352  ldc.i4.m1
0x10a353  dup
0x10a354  stloc.0
0x10a355  stfld    int32 <ParseQNameAsync>d__578::<>1__state
0x10a35a  ldloca.s 0xC
0x10a35c  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<int32, bool>>::GetResult()
0x10a361  stloc.s  0xB
0x10a363  ldloc.s  0xB
0x10a365  stloc.s  0xA
0x10a367  ldloc.s  0xA
0x10a369  callvirt instance var<u1> class [mscorlib]System.Tuple`2<int32, bool>::get_Item1()
0x10a36e  stloc.s  4
0x10a370  ldloc.s  0xA
0x10a372  callvirt instance var<u1> class [mscorlib]System.Tuple`2<int32, bool>::get_Item2()
0x10a377  brfalse.s loc_10A38F
0x10a379  ldarg.0
0x10a37a  ldloc.1
0x10a37b  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x10a380  ldfld    char[] ParsingState::chars
0x10a385  stfld    char[] <ParseQNameAsync>d__578::<chars>5__3
0x10a38a  br       loc_10A24A
0x10a38f  ldloc.1
0x10a390  ldloc.s  4
0x10a392  ldstr    aXmlUnexpectede// "Xml_UnexpectedEOF"
0x10a397  ldstr    aName_0// "Name"
0x10a39c  call     instance void System.Xml.XmlTextReaderImpl::Throw(int32 pos, string res, string arg)
0x10a3a1  ldarg.0
0x10a3a2  ldfld    int32 <ParseQNameAsync>d__578::<colonOffset>5__2
0x10a3a7  ldc.i4.m1
0x10a3a8  beq.s    loc_10A3BE
0x10a3aa  ldloc.1
0x10a3ab  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x10a3b0  ldfld    int32 ParsingState::charPos
0x10a3b5  ldarg.0
0x10a3b6  ldfld    int32 <ParseQNameAsync>d__578::<colonOffset>5__2
0x10a3bb  add
0x10a3bc  br.s     loc_10A3BF
0x10a3be  ldc.i4.m1
0x10a3bf  stloc.3
0x10a3c0  ldloc.3
0x10a3c1  ldloc.s  4
0x10a3c3  newobj   instance void class [mscorlib]System.Tuple`2<int32, int32>::.ctor(var<u1>, !!T0)
0x10a3c8  stloc.2
0x10a3c9  leave.s  loc_10A3EB
0x10a3cb  stloc.s  0xD
0x10a3cd  ldarg.0
0x10a3ce  ldc.i4.s 0xFE
0x10a3d0  stfld    int32 <ParseQNameAsync>d__578::<>1__state
0x10a3d5  ldarg.0
0x10a3d6  ldnull
0x10a3d7  stfld    char[] <ParseQNameAsync>d__578::<chars>5__3
0x10a3dc  ldarg.0
0x10a3dd  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Tuple`2<int32, int32>> <ParseQNameAsync>d__578::<>t__builder
0x10a3e2  ldloc.s  0xD
0x10a3e4  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Tuple`2<int32, int32>>::SetException(class [mscorlib]System.Exception)
0x10a3e9  leave.s  loc_10A406
0x10a3eb  ldarg.0
0x10a3ec  ldc.i4.s 0xFE
0x10a3ee  stfld    int32 <ParseQNameAsync>d__578::<>1__state
0x10a3f3  ldarg.0
0x10a3f4  ldnull
0x10a3f5  stfld    char[] <ParseQNameAsync>d__578::<chars>5__3
0x10a3fa  ldarg.0
0x10a3fb  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Tuple`2<int32, int32>> <ParseQNameAsync>d__578::<>t__builder
0x10a400  ldloc.2
0x10a401  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Tuple`2<int32, int32>>::SetResult(var<u1>)
0x10a406  ret
```
