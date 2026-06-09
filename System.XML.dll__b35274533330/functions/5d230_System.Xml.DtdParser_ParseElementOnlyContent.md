# System.Xml.DtdParser::ParseElementOnlyContent

- ea: `0x5d230`
- end: `0x5d39b`
- name: `System.Xml.DtdParser::ParseElementOnlyContent`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x5d0a0`

## callees

- `0x5d230`
- `0x5d3a0`
- `0x5dc90`
- `0x607d0`
- `0x60cd0`
- `0x60dc0`
- `0x60de0`
- `0xb5d30`
- `0xb5d40`
- `0xb5dd0`
- `0xb5e60`
- `0xb5e90`
- `0x119680`

## string_xrefs

- `0x5d299`: `Xml_InvalidContentModel`
- `0x5d2de`: `Xml_InvalidContentModel`
- `0x5d30c`: `Xml_InvalidContentModel`
- `0x5d36c`: `Xml_InvalidContentModel`

## pseudocode

```c

```

## disassembly

```asm
0x5d230  newobj   instance void class [System]System.Collections.Generic.Stack`1<class ParseElementOnlyContent_LocalFrame>::.ctor()
0x5d235  stloc.0
0x5d236  ldarg.2
0x5d237  newobj   instance void ParseElementOnlyContent_LocalFrame::.ctor(int32 startParentEntityIdParam)
0x5d23c  stloc.1
0x5d23d  ldloc.0
0x5d23e  ldloc.1
0x5d23f  callvirt instance void class [System]System.Collections.Generic.Stack`1<class ParseElementOnlyContent_LocalFrame>::Push(var<u1>)
0x5d244  ldarg.0
0x5d245  ldc.i4.0
0x5d246  call     instance valuetype Token System.Xml.DtdParser::GetToken(bool needWhiteSpace)
0x5d24b  stloc.2
0x5d24c  ldloc.2
0x5d24d  ldc.i4.s 0x17
0x5d24f  beq.s    loc_5D260
0x5d251  ldloc.2
0x5d252  ldc.i4.s 0x1B
0x5d254  beq.s    loc_5D277
0x5d256  ldloc.2
0x5d257  ldc.i4.s 0x1D
0x5d259  beq.s    loc_5D292
0x5d25b  br       loc_5D378
0x5d260  ldarg.1
0x5d261  ldarg.0
0x5d262  ldc.i4.1
0x5d263  call     instance class System.Xml.XmlQualifiedName System.Xml.DtdParser::GetNameQualified(bool canHavePrefix)
0x5d268  ldnull
0x5d269  callvirt instance void System.Xml.Schema.ParticleContentValidator::AddName(class System.Xml.XmlQualifiedName name, object particle)
0x5d26e  ldarg.0
0x5d26f  ldarg.1
0x5d270  call     instance void System.Xml.DtdParser::ParseHowMany(class System.Xml.Schema.ParticleContentValidator pcv)
0x5d275  br.s     loc_5D2A8
0x5d277  ldarg.1
0x5d278  callvirt instance void System.Xml.Schema.ParticleContentValidator::OpenGroup()
0x5d27d  ldarg.0
0x5d27e  ldfld    int32 System.Xml.DtdParser::currentEntityId
0x5d283  newobj   instance void ParseElementOnlyContent_LocalFrame::.ctor(int32 startParentEntityIdParam)
0x5d288  stloc.1
0x5d289  ldloc.0
0x5d28a  ldloc.1
0x5d28b  callvirt instance void class [System]System.Collections.Generic.Stack`1<class ParseElementOnlyContent_LocalFrame>::Push(var<u1>)
0x5d290  br.s     loc_5D244
0x5d292  ldarg.0
0x5d293  ldarg.0
0x5d294  ldfld    int32 System.Xml.DtdParser::curPos
0x5d299  ldstr    aXmlInvalidcont// "Xml_InvalidContentModel"
0x5d29e  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x5d2a3  br       loc_5D37E
0x5d2a8  ldarg.0
0x5d2a9  ldc.i4.0
0x5d2aa  call     instance valuetype Token System.Xml.DtdParser::GetToken(bool needWhiteSpace)
0x5d2af  stloc.3
0x5d2b0  ldloc.3
0x5d2b1  ldc.i4.s 0x1C
0x5d2b3  sub
0x5d2b4  switch   loc_5D329, loc_5D365, loc_5D2FB
0x5d2c5  ldloc.3
0x5d2c6  ldc.i4.s 0x2B
0x5d2c8  bne.un   loc_5D378
0x5d2cd  ldloc.1
0x5d2ce  ldfld    valuetype Token ParseElementOnlyContent_LocalFrame::parsingSchema
0x5d2d3  ldc.i4.s 0x1E
0x5d2d5  bne.un.s loc_5D2E8
0x5d2d7  ldarg.0
0x5d2d8  ldarg.0
0x5d2d9  ldfld    int32 System.Xml.DtdParser::curPos
0x5d2de  ldstr    aXmlInvalidcont// "Xml_InvalidContentModel"
0x5d2e3  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x5d2e8  ldarg.1
0x5d2e9  callvirt instance void System.Xml.Schema.ParticleContentValidator::AddSequence()
0x5d2ee  ldloc.1
0x5d2ef  ldc.i4.s 0x2B
0x5d2f1  stfld    valuetype Token ParseElementOnlyContent_LocalFrame::parsingSchema
0x5d2f6  br       loc_5D244
0x5d2fb  ldloc.1
0x5d2fc  ldfld    valuetype Token ParseElementOnlyContent_LocalFrame::parsingSchema
0x5d301  ldc.i4.s 0x2B
0x5d303  bne.un.s loc_5D316
0x5d305  ldarg.0
0x5d306  ldarg.0
0x5d307  ldfld    int32 System.Xml.DtdParser::curPos
0x5d30c  ldstr    aXmlInvalidcont// "Xml_InvalidContentModel"
0x5d311  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x5d316  ldarg.1
0x5d317  callvirt instance void System.Xml.Schema.ParticleContentValidator::AddChoice()
0x5d31c  ldloc.1
0x5d31d  ldc.i4.s 0x1E
0x5d31f  stfld    valuetype Token ParseElementOnlyContent_LocalFrame::parsingSchema
0x5d324  br       loc_5D244
0x5d329  ldarg.1
0x5d32a  callvirt instance void System.Xml.Schema.ParticleContentValidator::CloseGroup()
0x5d32f  ldarg.0
0x5d330  ldfld    bool System.Xml.DtdParser::validate
0x5d335  brfalse.s loc_5D35C
0x5d337  ldarg.0
0x5d338  ldfld    int32 System.Xml.DtdParser::currentEntityId
0x5d33d  ldloc.1
0x5d33e  ldfld    int32 ParseElementOnlyContent_LocalFrame::startParenEntityId
0x5d343  beq.s    loc_5D35C
0x5d345  ldarg.0
0x5d346  ldarg.0
0x5d347  ldfld    int32 System.Xml.DtdParser::curPos
0x5d34c  ldc.i4.0
0x5d34d  ldstr    aSchParentityre// "Sch_ParEntityRefNesting"
0x5d352  ldsfld   string [mscorlib]System.String::Empty
0x5d357  call     instance void System.Xml.DtdParser::SendValidationEvent(int32 pos, valuetype System.Xml.Schema.XmlSeverityType severity, string code, string arg)
0x5d35c  ldarg.0
0x5d35d  ldarg.1
0x5d35e  call     instance void System.Xml.DtdParser::ParseHowMany(class System.Xml.Schema.ParticleContentValidator pcv)
0x5d363  br.s     loc_5D37E
0x5d365  ldarg.0
0x5d366  ldarg.0
0x5d367  ldfld    int32 System.Xml.DtdParser::curPos
0x5d36c  ldstr    aXmlInvalidcont// "Xml_InvalidContentModel"
0x5d371  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x5d376  br.s     loc_5D37E
0x5d378  ldarg.0
0x5d379  call     instance void System.Xml.DtdParser::OnUnexpectedError()
0x5d37e  ldloc.0
0x5d37f  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class ParseElementOnlyContent_LocalFrame>::Pop()
0x5d384  pop
0x5d385  ldloc.0
0x5d386  callvirt instance int32 class [System]System.Collections.Generic.Stack`1<class ParseElementOnlyContent_LocalFrame>::get_Count()
0x5d38b  ldc.i4.0
0x5d38c  ble.s    loc_5D39A
0x5d38e  ldloc.0
0x5d38f  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class ParseElementOnlyContent_LocalFrame>::Peek()
0x5d394  stloc.1
0x5d395  br       loc_5D2A8
0x5d39a  ret
```
