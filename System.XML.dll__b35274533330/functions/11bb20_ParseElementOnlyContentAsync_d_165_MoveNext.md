# <ParseElementOnlyContentAsync>d__165::MoveNext

- ea: `0x11bb20`
- end: `0x11bf0b`
- name: `<ParseElementOnlyContentAsync>d__165::MoveNext`
- size: `1003`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config`

## callees

- `0x607d0`
- `0x60cd0`
- `0x60dc0`
- `0x60de0`
- `0x61430`
- `0x61650`
- `0xb5d30`
- `0xb5d40`
- `0xb5dd0`
- `0xb5e60`
- `0xb5e90`
- `0x119680`
- `0x11bb20`

## string_xrefs

- `0x11bcb3`: `Xml_InvalidContentModel`
- `0x11bd66`: `Xml_InvalidContentModel`
- `0x11bda3`: `Xml_InvalidContentModel`
- `0x11be7e`: `Xml_InvalidContentModel`

## pseudocode

```c

```

## disassembly

```asm
0x11bb20  ldarg.0
0x11bb21  ldfld    int32 <ParseElementOnlyContentAsync>d__165::<>1__state
0x11bb26  stloc.0
0x11bb27  ldarg.0
0x11bb28  ldfld    class System.Xml.DtdParser <ParseElementOnlyContentAsync>d__165::<>4__this
0x11bb2d  stloc.1
0x11bb2e  ldloc.0
0x11bb2f  switch   loc_11BBB6, loc_11BC54, loc_11BD07, loc_11BE51
0x11bb44  ldarg.0
0x11bb45  newobj   instance void class [System]System.Collections.Generic.Stack`1<class ParseElementOnlyContent_LocalFrame>::.ctor()
0x11bb4a  stfld    class [System]System.Collections.Generic.Stack`1<class ParseElementOnlyContent_LocalFrame> <ParseElementOnlyContentAsync>d__165::<localFrames>5__2
0x11bb4f  ldarg.0
0x11bb50  ldarg.0
0x11bb51  ldfld    int32 <ParseElementOnlyContentAsync>d__165::startParenEntityId
0x11bb56  newobj   instance void ParseElementOnlyContent_LocalFrame::.ctor(int32 startParentEntityIdParam)
0x11bb5b  stfld    class ParseElementOnlyContent_LocalFrame <ParseElementOnlyContentAsync>d__165::<currentFrame>5__3
0x11bb60  ldarg.0
0x11bb61  ldfld    class [System]System.Collections.Generic.Stack`1<class ParseElementOnlyContent_LocalFrame> <ParseElementOnlyContentAsync>d__165::<localFrames>5__2
0x11bb66  ldarg.0
0x11bb67  ldfld    class ParseElementOnlyContent_LocalFrame <ParseElementOnlyContentAsync>d__165::<currentFrame>5__3
0x11bb6c  callvirt instance void class [System]System.Collections.Generic.Stack`1<class ParseElementOnlyContent_LocalFrame>::Push(var<u1>)
0x11bb71  ldloc.1
0x11bb72  ldc.i4.0
0x11bb73  call     instance class [mscorlib]System.Threading.Tasks.Task`1<valuetype Token> System.Xml.DtdParser::GetTokenAsync(bool needWhiteSpace)
0x11bb78  ldc.i4.0
0x11bb79  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<valuetype Token>::ConfigureAwait(!!T0)
0x11bb7e  stloc.s  5
0x11bb80  ldloca.s 5
0x11bb82  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<valuetype Token>::GetAwaiter()
0x11bb87  stloc.s  4
0x11bb89  ldloca.s 4
0x11bb8b  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token>::get_IsCompleted()
0x11bb90  brtrue.s loc_11BBD3
0x11bb92  ldarg.0
0x11bb93  ldc.i4.0
0x11bb94  dup
0x11bb95  stloc.0
0x11bb96  stfld    int32 <ParseElementOnlyContentAsync>d__165::<>1__state
0x11bb9b  ldarg.0
0x11bb9c  ldloc.s  4
0x11bb9e  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token> <ParseElementOnlyContentAsync>d__165::<>u__1
0x11bba3  ldarg.0
0x11bba4  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ParseElementOnlyContentAsync>d__165::<>t__builder
0x11bba9  ldloca.s 4
0x11bbab  ldarg.0
0x11bbac  call     T0x2B0002AF
0x11bbb1  leave    loc_11BF0A
0x11bbb6  ldarg.0
0x11bbb7  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token> <ParseElementOnlyContentAsync>d__165::<>u__1
0x11bbbc  stloc.s  4
0x11bbbe  ldarg.0
0x11bbbf  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token> <ParseElementOnlyContentAsync>d__165::<>u__1
0x11bbc4  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token>
0x11bbca  ldarg.0
0x11bbcb  ldc.i4.m1
0x11bbcc  dup
0x11bbcd  stloc.0
0x11bbce  stfld    int32 <ParseElementOnlyContentAsync>d__165::<>1__state
0x11bbd3  ldloca.s 4
0x11bbd5  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token>::GetResult()
0x11bbda  stloc.3
0x11bbdb  ldloc.3
0x11bbdc  stloc.2
0x11bbdd  ldloc.2
0x11bbde  ldc.i4.s 0x17
0x11bbe0  beq.s    loc_11BBF7
0x11bbe2  ldloc.2
0x11bbe3  ldc.i4.s 0x1B
0x11bbe5  beq      loc_11BC7A
0x11bbea  ldloc.2
0x11bbeb  ldc.i4.s 0x1D
0x11bbed  beq      loc_11BCAC
0x11bbf2  br       loc_11BE8A
0x11bbf7  ldarg.0
0x11bbf8  ldfld    class System.Xml.Schema.ParticleContentValidator <ParseElementOnlyContentAsync>d__165::pcv
0x11bbfd  ldloc.1
0x11bbfe  ldc.i4.1
0x11bbff  call     instance class System.Xml.XmlQualifiedName System.Xml.DtdParser::GetNameQualified(bool canHavePrefix)
0x11bc04  ldnull
0x11bc05  callvirt instance void System.Xml.Schema.ParticleContentValidator::AddName(class System.Xml.XmlQualifiedName name, object particle)
0x11bc0a  ldloc.1
0x11bc0b  ldarg.0
0x11bc0c  ldfld    class System.Xml.Schema.ParticleContentValidator <ParseElementOnlyContentAsync>d__165::pcv
0x11bc11  call     instance class [mscorlib]System.Threading.Tasks.Task System.Xml.DtdParser::ParseHowManyAsync(class System.Xml.Schema.ParticleContentValidator pcv)
0x11bc16  ldc.i4.0
0x11bc17  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x11bc1c  stloc.s  7
0x11bc1e  ldloca.s 7
0x11bc20  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x11bc25  stloc.s  6
0x11bc27  ldloca.s 6
0x11bc29  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x11bc2e  brtrue.s loc_11BC71
0x11bc30  ldarg.0
0x11bc31  ldc.i4.1
0x11bc32  dup
0x11bc33  stloc.0
0x11bc34  stfld    int32 <ParseElementOnlyContentAsync>d__165::<>1__state
0x11bc39  ldarg.0
0x11bc3a  ldloc.s  6
0x11bc3c  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ParseElementOnlyContentAsync>d__165::<>u__2
0x11bc41  ldarg.0
0x11bc42  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ParseElementOnlyContentAsync>d__165::<>t__builder
0x11bc47  ldloca.s 6
0x11bc49  ldarg.0
0x11bc4a  call     T0x2B0002B0
0x11bc4f  leave    loc_11BF0A
0x11bc54  ldarg.0
0x11bc55  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ParseElementOnlyContentAsync>d__165::<>u__2
0x11bc5a  stloc.s  6
0x11bc5c  ldarg.0
0x11bc5d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ParseElementOnlyContentAsync>d__165::<>u__2
0x11bc62  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x11bc68  ldarg.0
0x11bc69  ldc.i4.m1
0x11bc6a  dup
0x11bc6b  stloc.0
0x11bc6c  stfld    int32 <ParseElementOnlyContentAsync>d__165::<>1__state
0x11bc71  ldloca.s 6
0x11bc73  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x11bc78  br.s     loc_11BCC2
0x11bc7a  ldarg.0
0x11bc7b  ldfld    class System.Xml.Schema.ParticleContentValidator <ParseElementOnlyContentAsync>d__165::pcv
0x11bc80  callvirt instance void System.Xml.Schema.ParticleContentValidator::OpenGroup()
0x11bc85  ldarg.0
0x11bc86  ldloc.1
0x11bc87  ldfld    int32 System.Xml.DtdParser::currentEntityId
0x11bc8c  newobj   instance void ParseElementOnlyContent_LocalFrame::.ctor(int32 startParentEntityIdParam)
0x11bc91  stfld    class ParseElementOnlyContent_LocalFrame <ParseElementOnlyContentAsync>d__165::<currentFrame>5__3
0x11bc96  ldarg.0
0x11bc97  ldfld    class [System]System.Collections.Generic.Stack`1<class ParseElementOnlyContent_LocalFrame> <ParseElementOnlyContentAsync>d__165::<localFrames>5__2
0x11bc9c  ldarg.0
0x11bc9d  ldfld    class ParseElementOnlyContent_LocalFrame <ParseElementOnlyContentAsync>d__165::<currentFrame>5__3
0x11bca2  callvirt instance void class [System]System.Collections.Generic.Stack`1<class ParseElementOnlyContent_LocalFrame>::Push(var<u1>)
0x11bca7  br       loc_11BB71
0x11bcac  ldloc.1
0x11bcad  ldloc.1
0x11bcae  ldfld    int32 System.Xml.DtdParser::curPos
0x11bcb3  ldstr    aXmlInvalidcont// "Xml_InvalidContentModel"
0x11bcb8  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x11bcbd  br       loc_11BE90
0x11bcc2  ldloc.1
0x11bcc3  ldc.i4.0
0x11bcc4  call     instance class [mscorlib]System.Threading.Tasks.Task`1<valuetype Token> System.Xml.DtdParser::GetTokenAsync(bool needWhiteSpace)
0x11bcc9  ldc.i4.0
0x11bcca  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<valuetype Token>::ConfigureAwait(!!T0)
0x11bccf  stloc.s  5
0x11bcd1  ldloca.s 5
0x11bcd3  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<valuetype Token>::GetAwaiter()
0x11bcd8  stloc.s  0xA
0x11bcda  ldloca.s 0xA
0x11bcdc  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token>::get_IsCompleted()
0x11bce1  brtrue.s loc_11BD24
0x11bce3  ldarg.0
0x11bce4  ldc.i4.2
0x11bce5  dup
0x11bce6  stloc.0
0x11bce7  stfld    int32 <ParseElementOnlyContentAsync>d__165::<>1__state
0x11bcec  ldarg.0
0x11bced  ldloc.s  0xA
0x11bcef  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token> <ParseElementOnlyContentAsync>d__165::<>u__1
0x11bcf4  ldarg.0
0x11bcf5  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ParseElementOnlyContentAsync>d__165::<>t__builder
0x11bcfa  ldloca.s 0xA
0x11bcfc  ldarg.0
0x11bcfd  call     T0x2B0002AF
0x11bd02  leave    loc_11BF0A
0x11bd07  ldarg.0
0x11bd08  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token> <ParseElementOnlyContentAsync>d__165::<>u__1
0x11bd0d  stloc.s  0xA
0x11bd0f  ldarg.0
0x11bd10  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token> <ParseElementOnlyContentAsync>d__165::<>u__1
0x11bd15  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token>
0x11bd1b  ldarg.0
0x11bd1c  ldc.i4.m1
0x11bd1d  dup
0x11bd1e  stloc.0
0x11bd1f  stfld    int32 <ParseElementOnlyContentAsync>d__165::<>1__state
0x11bd24  ldloca.s 0xA
0x11bd26  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token>::GetResult()
0x11bd2b  stloc.s  9
0x11bd2d  ldloc.s  9
0x11bd2f  stloc.s  8
0x11bd31  ldloc.s  8
0x11bd33  ldc.i4.s 0x1C
0x11bd35  sub
0x11bd36  switch   loc_11BDCA, loc_11BE77, loc_11BD8D
0x11bd47  ldloc.s  8
0x11bd49  ldc.i4.s 0x2B
0x11bd4b  bne.un   loc_11BE8A
0x11bd50  ldarg.0
0x11bd51  ldfld    class ParseElementOnlyContent_LocalFrame <ParseElementOnlyContentAsync>d__165::<currentFrame>5__3
0x11bd56  ldfld    valuetype Token ParseElementOnlyContent_LocalFrame::parsingSchema
0x11bd5b  ldc.i4.s 0x1E
0x11bd5d  bne.un.s loc_11BD70
0x11bd5f  ldloc.1
0x11bd60  ldloc.1
0x11bd61  ldfld    int32 System.Xml.DtdParser::curPos
0x11bd66  ldstr    aXmlInvalidcont// "Xml_InvalidContentModel"
0x11bd6b  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x11bd70  ldarg.0
0x11bd71  ldfld    class System.Xml.Schema.ParticleContentValidator <ParseElementOnlyContentAsync>d__165::pcv
0x11bd76  callvirt instance void System.Xml.Schema.ParticleContentValidator::AddSequence()
0x11bd7b  ldarg.0
0x11bd7c  ldfld    class ParseElementOnlyContent_LocalFrame <ParseElementOnlyContentAsync>d__165::<currentFrame>5__3
0x11bd81  ldc.i4.s 0x2B
0x11bd83  stfld    valuetype Token ParseElementOnlyContent_LocalFrame::parsingSchema
0x11bd88  br       loc_11BB71
0x11bd8d  ldarg.0
0x11bd8e  ldfld    class ParseElementOnlyContent_LocalFrame <ParseElementOnlyContentAsync>d__165::<currentFrame>5__3
0x11bd93  ldfld    valuetype Token ParseElementOnlyContent_LocalFrame::parsingSchema
0x11bd98  ldc.i4.s 0x2B
0x11bd9a  bne.un.s loc_11BDAD
0x11bd9c  ldloc.1
0x11bd9d  ldloc.1
0x11bd9e  ldfld    int32 System.Xml.DtdParser::curPos
0x11bda3  ldstr    aXmlInvalidcont// "Xml_InvalidContentModel"
0x11bda8  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x11bdad  ldarg.0
0x11bdae  ldfld    class System.Xml.Schema.ParticleContentValidator <ParseElementOnlyContentAsync>d__165::pcv
0x11bdb3  callvirt instance void System.Xml.Schema.ParticleContentValidator::AddChoice()
0x11bdb8  ldarg.0
0x11bdb9  ldfld    class ParseElementOnlyContent_LocalFrame <ParseElementOnlyContentAsync>d__165::<currentFrame>5__3
0x11bdbe  ldc.i4.s 0x1E
0x11bdc0  stfld    valuetype Token ParseElementOnlyContent_LocalFrame::parsingSchema
0x11bdc5  br       loc_11BB71
0x11bdca  ldarg.0
0x11bdcb  ldfld    class System.Xml.Schema.ParticleContentValidator <ParseElementOnlyContentAsync>d__165::pcv
0x11bdd0  callvirt instance void System.Xml.Schema.ParticleContentValidator::CloseGroup()
0x11bdd5  ldloc.1
0x11bdd6  ldfld    bool System.Xml.DtdParser::validate
0x11bddb  brfalse.s loc_11BE07
0x11bddd  ldloc.1
0x11bdde  ldfld    int32 System.Xml.DtdParser::currentEntityId
0x11bde3  ldarg.0
0x11bde4  ldfld    class ParseElementOnlyContent_LocalFrame <ParseElementOnlyContentAsync>d__165::<currentFrame>5__3
0x11bde9  ldfld    int32 ParseElementOnlyContent_LocalFrame::startParenEntityId
0x11bdee  beq.s    loc_11BE07
0x11bdf0  ldloc.1
0x11bdf1  ldloc.1
0x11bdf2  ldfld    int32 System.Xml.DtdParser::curPos
0x11bdf7  ldc.i4.0
0x11bdf8  ldstr    aSchParentityre// "Sch_ParEntityRefNesting"
0x11bdfd  ldsfld   string [mscorlib]System.String::Empty
0x11be02  call     instance void System.Xml.DtdParser::SendValidationEvent(int32 pos, valuetype System.Xml.Schema.XmlSeverityType severity, string code, string arg)
0x11be07  ldloc.1
0x11be08  ldarg.0
0x11be09  ldfld    class System.Xml.Schema.ParticleContentValidator <ParseElementOnlyContentAsync>d__165::pcv
0x11be0e  call     instance class [mscorlib]System.Threading.Tasks.Task System.Xml.DtdParser::ParseHowManyAsync(class System.Xml.Schema.ParticleContentValidator pcv)
0x11be13  ldc.i4.0
0x11be14  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x11be19  stloc.s  7
0x11be1b  ldloca.s 7
0x11be1d  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x11be22  stloc.s  0xB
0x11be24  ldloca.s 0xB
0x11be26  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x11be2b  brtrue.s loc_11BE6E
0x11be2d  ldarg.0
0x11be2e  ldc.i4.3
0x11be2f  dup
0x11be30  stloc.0
0x11be31  stfld    int32 <ParseElementOnlyContentAsync>d__165::<>1__state
0x11be36  ldarg.0
0x11be37  ldloc.s  0xB
0x11be39  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ParseElementOnlyContentAsync>d__165::<>u__2
0x11be3e  ldarg.0
0x11be3f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ParseElementOnlyContentAsync>d__165::<>t__builder
0x11be44  ldloca.s 0xB
0x11be46  ldarg.0
0x11be47  call     T0x2B0002B0
0x11be4c  leave    loc_11BF0A
0x11be51  ldarg.0
0x11be52  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ParseElementOnlyContentAsync>d__165::<>u__2
0x11be57  stloc.s  0xB
0x11be59  ldarg.0
0x11be5a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <ParseElementOnlyContentAsync>d__165::<>u__2
0x11be5f  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x11be65  ldarg.0
0x11be66  ldc.i4.m1
0x11be67  dup
0x11be68  stloc.0
0x11be69  stfld    int32 <ParseElementOnlyContentAsync>d__165::<>1__state
0x11be6e  ldloca.s 0xB
0x11be70  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x11be75  br.s     loc_11BE90
0x11be77  ldloc.1
0x11be78  ldloc.1
0x11be79  ldfld    int32 System.Xml.DtdParser::curPos
0x11be7e  ldstr    aXmlInvalidcont// "Xml_InvalidContentModel"
0x11be83  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x11be88  br.s     loc_11BE90
0x11be8a  ldloc.1
0x11be8b  call     instance void System.Xml.DtdParser::OnUnexpectedError()
0x11be90  ldarg.0
0x11be91  ldfld    class [System]System.Collections.Generic.Stack`1<class ParseElementOnlyContent_LocalFrame> <ParseElementOnlyContentAsync>d__165::<localFrames>5__2
0x11be96  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class ParseElementOnlyContent_LocalFrame>::Pop()
0x11be9b  pop
0x11be9c  ldarg.0
0x11be9d  ldfld    class [System]System.Collections.Generic.Stack`1<class ParseElementOnlyContent_LocalFrame> <ParseElementOnlyContentAsync>d__165::<localFrames>5__2
  ... truncated ...
```
