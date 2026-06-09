# Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::.cctor

- ea: `0x51e80`
- end: `0x5344d`
- name: `Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::.cctor`
- size: `5581`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, service_task, broker_com_uri`

## string_xrefs

- `0x5210f`: `&copy;`
- `0x52123`: `&COPY;`

## pseudocode

```c

```

## disassembly

```asm
0x51e80  ldsfld   class [mscorlib]System.Collections.Generic.IEqualityComparer`1<string> Microsoft.ReportingServices.OnDemandReportRendering.StringEqualityComparer::Instance
0x51e85  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x51e8a  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x51e8f  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x51e94  ldstr    aQuot// "&quot;"
0x51e99  ldc.i4.s 0x22
0x51e9b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x51ea0  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x51ea5  ldstr    aQuot_0// "&QUOT;"
0x51eaa  ldc.i4.s 0x22
0x51eac  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x51eb1  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x51eb6  ldstr    a34// "&#34;"
0x51ebb  ldc.i4.s 0x22
0x51ebd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x51ec2  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x51ec7  ldstr    aApos// "&apos;"
0x51ecc  ldc.i4.s 0x27
0x51ece  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x51ed3  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x51ed8  ldstr    aApos_0// "&APOS;"
0x51edd  ldc.i4.s 0x27
0x51edf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x51ee4  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x51ee9  ldstr    a39// "&#39;"
0x51eee  ldc.i4.s 0x27
0x51ef0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x51ef5  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x51efa  ldstr    aAmp// "&amp;"
0x51eff  ldc.i4.s 0x26
0x51f01  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x51f06  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x51f0b  ldstr    aAmp_0// "&AMP;"
0x51f10  ldc.i4.s 0x26
0x51f12  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x51f17  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x51f1c  ldstr    a38// "&#38;"
0x51f21  ldc.i4.s 0x26
0x51f23  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x51f28  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x51f2d  ldstr    aLt// "&lt;"
0x51f32  ldc.i4.s 0x3C
0x51f34  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x51f39  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x51f3e  ldstr    aLt_0// "&LT;"
0x51f43  ldc.i4.s 0x3C
0x51f45  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x51f4a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x51f4f  ldstr    a60// "&#60;"
0x51f54  ldc.i4.s 0x3C
0x51f56  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x51f5b  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x51f60  ldstr    aGt// "&gt;"
0x51f65  ldc.i4.s 0x3E
0x51f67  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x51f6c  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x51f71  ldstr    aGt_0// "&GT;"
0x51f76  ldc.i4.s 0x3E
0x51f78  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x51f7d  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x51f82  ldstr    a62// "&#62;"
0x51f87  ldc.i4.s 0x3E
0x51f89  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x51f8e  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x51f93  ldstr    a32// "&#32;"
0x51f98  ldc.i4   0xA0
0x51f9d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x51fa2  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x51fa7  ldstr    aNbsp// "&nbsp;"
0x51fac  ldc.i4   0xA0
0x51fb1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x51fb6  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x51fbb  ldstr    a160// "&#160;"
0x51fc0  ldc.i4   0xA0
0x51fc5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x51fca  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x51fcf  ldstr    aIexcl// "&iexcl;"
0x51fd4  ldc.i4   0xA1
0x51fd9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x51fde  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x51fe3  ldstr    a161// "&#161;"
0x51fe8  ldc.i4   0xA1
0x51fed  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x51ff2  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x51ff7  ldstr    aCent// "&cent;"
0x51ffc  ldc.i4   0xA2
0x52001  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x52006  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x5200b  ldstr    a162// "&#162;"
0x52010  ldc.i4   0xA2
0x52015  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x5201a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x5201f  ldstr    aPound// "&pound;"
0x52024  ldc.i4   0xA3
0x52029  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x5202e  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x52033  ldstr    a163// "&#163;"
0x52038  ldc.i4   0xA3
0x5203d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x52042  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x52047  ldstr    aCurren// "&curren;"
0x5204c  ldc.i4   0xA4
0x52051  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x52056  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x5205b  ldstr    a164// "&#164;"
0x52060  ldc.i4   0xA4
0x52065  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x5206a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x5206f  ldstr    aYen// "&yen;"
0x52074  ldc.i4   0xA5
0x52079  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x5207e  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x52083  ldstr    a165// "&#165;"
0x52088  ldc.i4   0xA5
0x5208d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x52092  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x52097  ldstr    aBrvbar// "&brvbar;"
0x5209c  ldc.i4   0xA6
0x520a1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x520a6  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x520ab  ldstr    a166// "&#166;"
0x520b0  ldc.i4   0xA6
0x520b5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x520ba  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x520bf  ldstr    aSect// "&sect;"
0x520c4  ldc.i4   0xA7
0x520c9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x520ce  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x520d3  ldstr    a167// "&#167;"
0x520d8  ldc.i4   0xA7
0x520dd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x520e2  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x520e7  ldstr    aUml// "&uml;"
0x520ec  ldc.i4   0xA8
0x520f1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x520f6  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x520fb  ldstr    a168// "&#168;"
0x52100  ldc.i4   0xA8
0x52105  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x5210a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x5210f  ldstr    aCopy// "&copy;"
0x52114  ldc.i4   0xA9
0x52119  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x5211e  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x52123  ldstr    aCopy_0// "&COPY;"
0x52128  ldc.i4   0xA9
0x5212d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x52132  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x52137  ldstr    a169// "&#169;"
0x5213c  ldc.i4   0xA9
0x52141  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x52146  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x5214b  ldstr    aOrdf// "&ordf;"
0x52150  ldc.i4   0xAA
0x52155  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x5215a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x5215f  ldstr    a170// "&#170;"
0x52164  ldc.i4   0xAA
0x52169  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x5216e  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x52173  ldstr    aLaquo// "&laquo;"
0x52178  ldc.i4   0xAB
0x5217d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x52182  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x52187  ldstr    a171// "&#171;"
0x5218c  ldc.i4   0xAB
0x52191  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x52196  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x5219b  ldstr    aNot// "&not;"
0x521a0  ldc.i4   0xAC
0x521a5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x521aa  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x521af  ldstr    a172// "&#172;"
0x521b4  ldc.i4   0xAC
0x521b9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x521be  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x521c3  ldstr    aShy// "&shy;"
0x521c8  ldc.i4   0xAD
0x521cd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x521d2  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x521d7  ldstr    a173// "&#173;"
0x521dc  ldc.i4   0xAD
0x521e1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x521e6  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x521eb  ldstr    aReg// "&reg;"
0x521f0  ldc.i4   0xAE
0x521f5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x521fa  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x521ff  ldstr    aReg_0// "&REG;"
0x52204  ldc.i4   0xAE
0x52209  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x5220e  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x52213  ldstr    a174// "&#174;"
0x52218  ldc.i4   0xAE
0x5221d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x52222  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x52227  ldstr    aMacr// "&macr;"
0x5222c  ldc.i4   0xAF
0x52231  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x52236  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x5223b  ldstr    a175// "&#175;"
0x52240  ldc.i4   0xAF
0x52245  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x5224a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x5224f  ldstr    aDeg// "&deg;"
0x52254  ldc.i4   0xB0
0x52259  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x5225e  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x52263  ldstr    a176// "&#176;"
0x52268  ldc.i4   0xB0
0x5226d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x52272  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x52277  ldstr    aPlusmn// "&plusmn;"
0x5227c  ldc.i4   0xB1
0x52281  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x52286  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x5228b  ldstr    a177// "&#177;"
0x52290  ldc.i4   0xB1
0x52295  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x5229a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x5229f  ldstr    aSup2// "&sup2;"
0x522a4  ldc.i4   0xB2
0x522a9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x522ae  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x522b3  ldstr    a178// "&#178;"
0x522b8  ldc.i4   0xB2
0x522bd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x522c2  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x522c7  ldstr    aSup3// "&sup3;"
0x522cc  ldc.i4   0xB3
0x522d1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x522d6  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x522db  ldstr    a179// "&#179;"
0x522e0  ldc.i4   0xB3
0x522e5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x522ea  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x522ef  ldstr    aAcute// "&acute;"
0x522f4  ldc.i4   0xB4
0x522f9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x522fe  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x52303  ldstr    a180// "&#180;"
0x52308  ldc.i4   0xB4
0x5230d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x52312  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x52317  ldstr    aMicro// "&micro;"
0x5231c  ldc.i4   0xB5
0x52321  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x52326  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x5232b  ldstr    a181// "&#181;"
0x52330  ldc.i4   0xB5
0x52335  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x5233a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x5233f  ldstr    aPara// "&para;"
0x52344  ldc.i4   0xB6
0x52349  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x5234e  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x52353  ldstr    a182// "&#182;"
0x52358  ldc.i4   0xB6
0x5235d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x52362  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x52367  ldstr    aMiddot// "&middot;"
0x5236c  ldc.i4   0xB7
0x52371  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x52376  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x5237b  ldstr    a183// "&#183;"
0x52380  ldc.i4   0xB7
0x52385  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x5238a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x5238f  ldstr    aCedil// "&cedil;"
0x52394  ldc.i4   0xB8
0x52399  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x5239e  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x523a3  ldstr    a184// "&#184;"
0x523a8  ldc.i4   0xB8
0x523ad  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x523b2  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x523b7  ldstr    aSup1// "&sup1;"
0x523bc  ldc.i4   0xB9
0x523c1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x523c6  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x523cb  ldstr    a185// "&#185;"
0x523d0  ldc.i4   0xB9
0x523d5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x523da  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x523df  ldstr    aOrdm// "&ordm;"
0x523e4  ldc.i4   0xBA
0x523e9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x523ee  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x523f3  ldstr    a186// "&#186;"
0x523f8  ldc.i4   0xBA
0x523fd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x52402  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x52407  ldstr    aRaquo// "&raquo;"
0x5240c  ldc.i4   0xBB
0x52411  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x52416  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
0x5241b  ldstr    a187// "&#187;"
0x52420  ldc.i4   0xBB
0x52425  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, char>::Add(var<u1>, !!T0)
0x5242a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, char> Microsoft.ReportingServices.OnDemandReportRendering.HtmlEntityResolver::m_entityLookupTable
  ... truncated ...
```
