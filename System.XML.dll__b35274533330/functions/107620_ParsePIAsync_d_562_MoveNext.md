# <ParsePIAsync>d__562::MoveNext

- ea: `0x107620`
- end: `0x107bda`
- name: `<ParsePIAsync>d__562::MoveNext`
- size: `1466`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config`

## callees

- `0x12920`
- `0x131f0`
- `0x29770`
- `0x297c0`
- `0x33200`
- `0x34b60`
- `0x34dd0`
- `0x34eb0`
- `0xfe500`
- `0xfe510`
- `0xfeab0`
- `0xfeb20`
- `0xfeb70`
- `0xfeb80`
- `0x107620`

## string_xrefs

- `0x1078c4`: `Xml_BadNameChar`
- `0x107730`: `Xml_InvalidPIName`
- `0x107737`: `Xml_XmlDeclNotFirst`

## pseudocode

```c

```

## disassembly

```asm
0x107620  ldarg.0
0x107621  ldfld    int32 <ParsePIAsync>d__562::<>1__state
0x107626  stloc.0
0x107627  ldarg.0
0x107628  ldfld    class System.Xml.XmlTextReaderImpl <ParsePIAsync>d__562::<>4__this
0x10762d  stloc.1
0x10762e  ldloc.0
0x10762f  switch   loc_1076B9, loc_1077EC, loc_107877, loc_107938, loc_107A46, loc_107B11
0x10764c  ldloc.1
0x10764d  ldfld    valuetype ParsingMode System.Xml.XmlTextReaderImpl::parsingMode
0x107652  brtrue.s loc_107675
0x107654  ldloc.1
0x107655  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x10765a  ldloc.1
0x10765b  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x107660  call     instance int32 ParsingState::get_LineNo()
0x107665  ldloc.1
0x107666  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x10766b  call     instance int32 ParsingState::get_LinePos()
0x107670  callvirt instance void NodeData::SetLineInfo(int32 lineNo, int32 linePos)
0x107675  ldloc.1
0x107676  call     instance class [mscorlib]System.Threading.Tasks.Task`1<int32> System.Xml.XmlTextReaderImpl::ParseNameAsync()
0x10767b  ldc.i4.0
0x10767c  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<int32>::ConfigureAwait(!!T0)
0x107681  stloc.s  0xA
0x107683  ldloca.s 0xA
0x107685  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<int32>::GetAwaiter()
0x10768a  stloc.s  9
0x10768c  ldloca.s 9
0x10768e  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>::get_IsCompleted()
0x107693  brtrue.s loc_1076D6
0x107695  ldarg.0
0x107696  ldc.i4.0
0x107697  dup
0x107698  stloc.0
0x107699  stfld    int32 <ParsePIAsync>d__562::<>1__state
0x10769e  ldarg.0
0x10769f  ldloc.s  9
0x1076a1  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <ParsePIAsync>d__562::<>u__1
0x1076a6  ldarg.0
0x1076a7  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <ParsePIAsync>d__562::<>t__builder
0x1076ac  ldloca.s 9
0x1076ae  ldarg.0
0x1076af  call     T0x2B00020D
0x1076b4  leave    loc_107BD9
0x1076b9  ldarg.0
0x1076ba  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <ParsePIAsync>d__562::<>u__1
0x1076bf  stloc.s  9
0x1076c1  ldarg.0
0x1076c2  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <ParsePIAsync>d__562::<>u__1
0x1076c7  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>
0x1076cd  ldarg.0
0x1076ce  ldc.i4.m1
0x1076cf  dup
0x1076d0  stloc.0
0x1076d1  stfld    int32 <ParsePIAsync>d__562::<>1__state
0x1076d6  ldloca.s 9
0x1076d8  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>::GetResult()
0x1076dd  stloc.s  8
0x1076df  ldloc.s  8
0x1076e1  stloc.3
0x1076e2  ldloc.1
0x1076e3  ldfld    class System.Xml.XmlNameTable System.Xml.XmlTextReaderImpl::nameTable
0x1076e8  ldloc.1
0x1076e9  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x1076ee  ldfld    char[] ParsingState::chars
0x1076f3  ldloc.1
0x1076f4  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x1076f9  ldfld    int32 ParsingState::charPos
0x1076fe  ldloc.3
0x1076ff  ldloc.1
0x107700  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x107705  ldfld    int32 ParsingState::charPos
0x10770a  sub
0x10770b  callvirt instance string System.Xml.XmlNameTable::Add(char[] array, int32 offset, int32 length)
0x107710  stloc.s  4
0x107712  ldloc.s  4
0x107714  ldstr    aXml// "xml"
0x107719  ldc.i4.5
0x10771a  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x10771f  brtrue.s loc_107743
0x107721  ldloc.1
0x107722  ldloc.s  4
0x107724  ldstr    aXml// "xml"
0x107729  callvirt instance bool [mscorlib]System.String::Equals(string)
0x10772e  brtrue.s loc_107737
0x107730  ldstr    aXmlInvalidpina// "Xml_InvalidPIName"
0x107735  br.s     loc_10773C
0x107737  ldstr    aXmlXmldeclnotf// "Xml_XmlDeclNotFirst"
0x10773c  ldloc.s  4
0x10773e  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res, string arg)
0x107743  ldloc.1
0x107744  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x107749  ldloc.3
0x10774a  stfld    int32 ParsingState::charPos
0x10774f  ldarg.0
0x107750  ldfld    class [mscorlib]System.Text.StringBuilder <ParsePIAsync>d__562::piInDtdStringBuilder
0x107755  brtrue.s loc_107777
0x107757  ldloc.1
0x107758  ldfld    bool System.Xml.XmlTextReaderImpl::ignorePIs
0x10775d  brtrue.s loc_107785
0x10775f  ldloc.1
0x107760  ldfld    valuetype ParsingMode System.Xml.XmlTextReaderImpl::parsingMode
0x107765  brtrue.s loc_107785
0x107767  ldloc.1
0x107768  ldfld    class NodeData System.Xml.XmlTextReaderImpl::curNode
0x10776d  ldc.i4.7
0x10776e  ldloc.s  4
0x107770  callvirt instance void NodeData::SetNamedNode(valuetype System.Xml.XmlNodeType type, string localName)
0x107775  br.s     loc_107785
0x107777  ldarg.0
0x107778  ldfld    class [mscorlib]System.Text.StringBuilder <ParsePIAsync>d__562::piInDtdStringBuilder
0x10777d  ldloc.s  4
0x10777f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x107784  pop
0x107785  ldarg.0
0x107786  ldloc.1
0x107787  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x10778c  ldfld    char[] ParsingState::chars
0x107791  ldloc.1
0x107792  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x107797  ldfld    int32 ParsingState::charPos
0x10779c  ldelem.u2
0x10779d  stfld    char <ParsePIAsync>d__562::<ch>5__2
0x1077a2  ldloc.1
0x1077a3  ldarg.0
0x1077a4  ldfld    class [mscorlib]System.Text.StringBuilder <ParsePIAsync>d__562::piInDtdStringBuilder
0x1077a9  call     instance class [mscorlib]System.Threading.Tasks.Task`1<int32> System.Xml.XmlTextReaderImpl::EatWhitespacesAsync(class [mscorlib]System.Text.StringBuilder sb)
0x1077ae  ldc.i4.0
0x1077af  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<int32>::ConfigureAwait(!!T0)
0x1077b4  stloc.s  0xA
0x1077b6  ldloca.s 0xA
0x1077b8  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<int32>::GetAwaiter()
0x1077bd  stloc.s  0xC
0x1077bf  ldloca.s 0xC
0x1077c1  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>::get_IsCompleted()
0x1077c6  brtrue.s loc_107809
0x1077c8  ldarg.0
0x1077c9  ldc.i4.1
0x1077ca  dup
0x1077cb  stloc.0
0x1077cc  stfld    int32 <ParsePIAsync>d__562::<>1__state
0x1077d1  ldarg.0
0x1077d2  ldloc.s  0xC
0x1077d4  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <ParsePIAsync>d__562::<>u__1
0x1077d9  ldarg.0
0x1077da  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <ParsePIAsync>d__562::<>t__builder
0x1077df  ldloca.s 0xC
0x1077e1  ldarg.0
0x1077e2  call     T0x2B00020D
0x1077e7  leave    loc_107BD9
0x1077ec  ldarg.0
0x1077ed  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <ParsePIAsync>d__562::<>u__1
0x1077f2  stloc.s  0xC
0x1077f4  ldarg.0
0x1077f5  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <ParsePIAsync>d__562::<>u__1
0x1077fa  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>
0x107800  ldarg.0
0x107801  ldc.i4.m1
0x107802  dup
0x107803  stloc.0
0x107804  stfld    int32 <ParsePIAsync>d__562::<>1__state
0x107809  ldloca.s 0xC
0x10780b  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>::GetResult()
0x107810  stloc.s  0xB
0x107812  ldloc.s  0xB
0x107814  brtrue   loc_1078F4
0x107819  ldloc.1
0x10781a  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x10781f  ldfld    int32 ParsingState::charsUsed
0x107824  ldloc.1
0x107825  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x10782a  ldfld    int32 ParsingState::charPos
0x10782f  sub
0x107830  ldc.i4.2
0x107831  bge.s    loc_10789C
0x107833  ldloc.1
0x107834  call     instance class [mscorlib]System.Threading.Tasks.Task`1<int32> System.Xml.XmlTextReaderImpl::ReadDataAsync()
0x107839  ldc.i4.0
0x10783a  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<int32>::ConfigureAwait(!!T0)
0x10783f  stloc.s  0xA
0x107841  ldloca.s 0xA
0x107843  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<int32>::GetAwaiter()
0x107848  stloc.s  0xD
0x10784a  ldloca.s 0xD
0x10784c  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>::get_IsCompleted()
0x107851  brtrue.s loc_107894
0x107853  ldarg.0
0x107854  ldc.i4.2
0x107855  dup
0x107856  stloc.0
0x107857  stfld    int32 <ParsePIAsync>d__562::<>1__state
0x10785c  ldarg.0
0x10785d  ldloc.s  0xD
0x10785f  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <ParsePIAsync>d__562::<>u__1
0x107864  ldarg.0
0x107865  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <ParsePIAsync>d__562::<>t__builder
0x10786a  ldloca.s 0xD
0x10786c  ldarg.0
0x10786d  call     T0x2B00020D
0x107872  leave    loc_107BD9
0x107877  ldarg.0
0x107878  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <ParsePIAsync>d__562::<>u__1
0x10787d  stloc.s  0xD
0x10787f  ldarg.0
0x107880  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <ParsePIAsync>d__562::<>u__1
0x107885  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>
0x10788b  ldarg.0
0x10788c  ldc.i4.m1
0x10788d  dup
0x10788e  stloc.0
0x10788f  stfld    int32 <ParsePIAsync>d__562::<>1__state
0x107894  ldloca.s 0xD
0x107896  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>::GetResult()
0x10789b  pop
0x10789c  ldarg.0
0x10789d  ldfld    char <ParsePIAsync>d__562::<ch>5__2
0x1078a2  ldc.i4.s 0x3F
0x1078a4  bne.un.s loc_1078C3
0x1078a6  ldloc.1
0x1078a7  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x1078ac  ldfld    char[] ParsingState::chars
0x1078b1  ldloc.1
0x1078b2  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x1078b7  ldfld    int32 ParsingState::charPos
0x1078bc  ldc.i4.1
0x1078bd  add
0x1078be  ldelem.u2
0x1078bf  ldc.i4.s 0x3E
0x1078c1  beq.s    loc_1078F4
0x1078c3  ldloc.1
0x1078c4  ldstr    aXmlBadnamechar// "Xml_BadNameChar"
0x1078c9  ldloc.1
0x1078ca  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x1078cf  ldfld    char[] ParsingState::chars
0x1078d4  ldloc.1
0x1078d5  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x1078da  ldfld    int32 ParsingState::charsUsed
0x1078df  ldloc.1
0x1078e0  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x1078e5  ldfld    int32 ParsingState::charPos
0x1078ea  call     string[] System.Xml.XmlException::BuildCharExceptionArgs(char[] data, int32 length, int32 invCharIndex)
0x1078ef  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res, string[] args)
0x1078f4  ldloc.1
0x1078f5  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Tuple`3<int32, int32, bool>> System.Xml.XmlTextReaderImpl::ParsePIValueAsync()
0x1078fa  ldc.i4.0
0x1078fb  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Tuple`3<int32, int32, bool>>::ConfigureAwait(!!T0)
0x107900  stloc.s  0x10
0x107902  ldloca.s 0x10
0x107904  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [mscorlib]System.Tuple`3<int32, int32, bool>>::GetAwaiter()
0x107909  stloc.s  0xF
0x10790b  ldloca.s 0xF
0x10790d  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`3<int32, int32, bool>>::get_IsCompleted()
0x107912  brtrue.s loc_107955
0x107914  ldarg.0
0x107915  ldc.i4.3
0x107916  dup
0x107917  stloc.0
0x107918  stfld    int32 <ParsePIAsync>d__562::<>1__state
0x10791d  ldarg.0
0x10791e  ldloc.s  0xF
0x107920  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`3<int32, int32, bool>> <ParsePIAsync>d__562::<>u__2
0x107925  ldarg.0
0x107926  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <ParsePIAsync>d__562::<>t__builder
0x10792b  ldloca.s 0xF
0x10792d  ldarg.0
0x10792e  call     T0x2B00020E
0x107933  leave    loc_107BD9
0x107938  ldarg.0
0x107939  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`3<int32, int32, bool>> <ParsePIAsync>d__562::<>u__2
0x10793e  stloc.s  0xF
0x107940  ldarg.0
0x107941  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`3<int32, int32, bool>> <ParsePIAsync>d__562::<>u__2
0x107946  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`3<int32, int32, bool>>
0x10794c  ldarg.0
0x10794d  ldc.i4.m1
0x10794e  dup
0x10794f  stloc.0
0x107950  stfld    int32 <ParsePIAsync>d__562::<>1__state
0x107955  ldloca.s 0xF
0x107957  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`3<int32, int32, bool>>::GetResult()
0x10795c  stloc.s  0xE
0x10795e  ldloc.s  0xE
0x107960  stloc.s  7
0x107962  ldloc.s  7
0x107964  callvirt instance var<u1> class [mscorlib]System.Tuple`3<int32, int32, bool>::get_Item1()
0x107969  stloc.s  5
0x10796b  ldloc.s  7
0x10796d  callvirt instance var<u1> class [mscorlib]System.Tuple`3<int32, int32, bool>::get_Item2()
0x107972  stloc.s  6
0x107974  ldloc.s  7
0x107976  callvirt instance var<u1> class [mscorlib]System.Tuple`3<int32, int32, bool>::get_Item3()
0x10797b  brfalse.s loc_1079E4
0x10797d  ldarg.0
0x10797e  ldfld    class [mscorlib]System.Text.StringBuilder <ParsePIAsync>d__562::piInDtdStringBuilder
0x107983  brtrue.s loc_1079C1
0x107985  ldloc.1
0x107986  ldfld    bool System.Xml.XmlTextReaderImpl::ignorePIs
0x10798b  brfalse.s loc_107994
0x10798d  ldc.i4.0
  ... truncated ...
```
