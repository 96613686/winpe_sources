# Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadAxis

- ea: `0xa2600`
- end: `0xa3538`
- name: `Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadAxis`
- size: `3896`
- prototype: ``
- caller_count: `2`
- callee_count: `87`
- tags: `service_task, broker_com_uri`

## callers

- `0xa1fd0`
- `0xa2060`

## callees

- `0x9f6f0`
- `0xa1d10`
- `0xa22b0`
- `0xa2600`
- `0xa3540`
- `0xa5920`
- `0xa5fd0`
- `0xac750`
- `0xb0fd0`
- `0xb82b0`
- `0xb8b10`
- `0xb8b40`
- `0xb8de0`
- `0xb8e80`
- `0xbb940`
- `0xbcdc0`
- `0xbcde0`
- `0xbce20`
- `0xbe1c0`
- `0xbe2b0`
- `0xbe860`
- `0xbe9a0`
- `0xbf370`
- `0xc17c0`
- `0x1079e0`
- `0x108df0`
- `0x108e10`
- `0x108e20`
- `0x108e40`
- `0x108e60`
- `0x108e80`
- `0x108ea0`
- `0x108ec0`
- `0x108ee0`
- `0x108f00`
- `0x108f20`
- `0x108f40`
- `0x108fb0`
- `0x108fc0`
- `0x108fd0`
- `0x108fe0`
- `0x109000`
- `0x109010`
- `0x109020`
- `0x109040`
- `0x109050`
- `0x109060`
- `0x109080`
- `0x1090a0`
- `0x1090c0`

## pseudocode

```c

```

## disassembly

```asm
0xa2600  ldarg.1
0xa2601  newobj   instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartAxis::.ctor(class Microsoft.ReportingServices.ReportIntermediateFormat.Chart chart)
0xa2606  stloc.0
0xa2607  ldloc.0
0xa2608  ldarg.0
0xa2609  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa260e  ldstr    aName_1// "Name"
0xa2613  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0xa2618  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartAxis::set_AxisName(string value)
0xa261d  ldarg.s  4
0xa261f  ldc.i4.0
0xa2620  ldarg.3
0xa2621  brtrue.s loc_A262A
0xa2623  ldstr    aChartvalueaxis// "ChartValueAxis"
0xa2628  br.s     loc_A262F
0xa262a  ldstr    aChartcategorya_0// "ChartCategoryAxis"
0xa262f  ldc.i4.s 0x10
0xa2631  ldarg.1
0xa2632  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::get_Name()
0xa2637  ldloc.0
0xa2638  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ChartAxis::get_AxisName()
0xa263d  ldarga.s 2
0xa263f  call     instance class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ErrorContext()
0xa2644  callvirt instance bool Microsoft.ReportingServices.ReportPublishing.DynamicImageOrCustomUniqueNameValidator::Validate(valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, string propertyName, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyNameValue, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext)
0xa2649  pop
0xa264a  ldarg.0
0xa264b  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa2650  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xa2655  brtrue   loc_A3536
0xa265a  ldc.i4.0
0xa265b  stloc.1
0xa265c  ldarg.0
0xa265d  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa2662  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xa2667  pop
0xa2668  ldarg.0
0xa2669  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa266e  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xa2673  stloc.2
0xa2674  ldloc.2
0xa2675  ldc.i4.1
0xa2676  beq.s    loc_A2685
0xa2678  ldloc.2
0xa2679  ldc.i4.s 0xF
0xa267b  beq      loc_A3517
0xa2680  br       loc_A3530
0xa2685  ldarg.0
0xa2686  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa268b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa2690  stloc.s  4
0xa2692  ldloc.s  4
0xa2694  brfalse  loc_A3530
0xa2699  ldloc.s  4
0xa269b  call     instance int32 [mscorlib]System.String::get_Length()
0xa26a0  stloc.s  5
0xa26a2  ldloc.s  5
0xa26a4  ldc.i4.5
0xa26a5  sub
0xa26a6  switch   loc_A26FC, loc_A276D, loc_A271D, loc_A2797, loc_A3530, loc_A288C, loc_A290C, loc_A27C1, loc_A2936, loc_A27E2, loc_A28AD, loc_A2CE9, loc_A28EB, loc_A2803, loc_A282D, loc_A2CFF, loc_A286B, loc_A3530, loc_A2D15
0xa26f7  br       loc_A3530
0xa26fc  ldloc.s  4
0xa26fe  ldc.i4.0
0xa26ff  call     instance char [mscorlib]System.String::get_Chars(int32)
0xa2704  stloc.s  6
0xa2706  ldloc.s  6
0xa2708  ldc.i4.s 0x41
0xa270a  beq      loc_A296D
0xa270f  ldloc.s  6
0xa2711  ldc.i4.s 0x53
0xa2713  beq      loc_A2957
0xa2718  br       loc_A3530
0xa271d  ldloc.s  4
0xa271f  ldc.i4.2
0xa2720  call     instance char [mscorlib]System.String::get_Chars(int32)
0xa2725  stloc.s  6
0xa2727  ldloc.s  6
0xa2729  ldc.i4.s 0x6F
0xa272b  bgt.un.s loc_A274D
0xa272d  ldloc.s  6
0xa272f  ldc.i4.s 0x67
0xa2731  beq      loc_A29AF
0xa2736  ldloc.s  6
0xa2738  ldc.i4.s 0x6E
0xa273a  beq      loc_A29DB
0xa273f  ldloc.s  6
0xa2741  ldc.i4.s 0x6F
0xa2743  beq      loc_A29C5
0xa2748  br       loc_A3530
0xa274d  ldloc.s  6
0xa274f  ldc.i4.s 0x73
0xa2751  beq      loc_A2983
0xa2756  ldloc.s  6
0xa2758  ldc.i4.s 0x76
0xa275a  beq      loc_A2999
0xa275f  ldloc.s  6
0xa2761  ldc.i4.s 0x78
0xa2763  beq      loc_A29F1
0xa2768  br       loc_A3530
0xa276d  ldloc.s  4
0xa276f  ldc.i4.0
0xa2770  call     instance char [mscorlib]System.String::get_Chars(int32)
0xa2775  stloc.s  6
0xa2777  ldloc.s  6
0xa2779  ldc.i4.s 0x41
0xa277b  beq      loc_A2A1D
0xa2780  ldloc.s  6
0xa2782  ldc.i4.s 0x4D
0xa2784  beq      loc_A2A07
0xa2789  ldloc.s  6
0xa278b  ldc.i4.s 0x53
0xa278d  beq      loc_A2A33
0xa2792  br       loc_A3530
0xa2797  ldloc.s  4
0xa2799  ldc.i4.2
0xa279a  call     instance char [mscorlib]System.String::get_Chars(int32)
0xa279f  stloc.s  6
0xa27a1  ldloc.s  6
0xa27a3  ldc.i4.s 0x63
0xa27a5  beq      loc_A2A5F
0xa27aa  ldloc.s  6
0xa27ac  ldc.i4.s 0x67
0xa27ae  beq      loc_A2A75
0xa27b3  ldloc.s  6
0xa27b5  ldc.i4.s 0x74
0xa27b7  beq      loc_A2A49
0xa27bc  br       loc_A3530
0xa27c1  ldloc.s  4
0xa27c3  ldc.i4.0
0xa27c4  call     instance char [mscorlib]System.String::get_Chars(int32)
0xa27c9  stloc.s  6
0xa27cb  ldloc.s  6
0xa27cd  ldc.i4.s 0x49
0xa27cf  beq      loc_A2A8B
0xa27d4  ldloc.s  6
0xa27d6  ldc.i4.s 0x4F
0xa27d8  beq      loc_A2AA1
0xa27dd  br       loc_A3530
0xa27e2  ldloc.s  4
0xa27e4  ldc.i4.0
0xa27e5  call     instance char [mscorlib]System.String::get_Chars(int32)
0xa27ea  stloc.s  6
0xa27ec  ldloc.s  6
0xa27ee  ldc.i4.s 0x43
0xa27f0  beq      loc_A2ACD
0xa27f5  ldloc.s  6
0xa27f7  ldc.i4.s 0x49
0xa27f9  beq      loc_A2AB7
0xa27fe  br       loc_A3530
0xa2803  ldloc.s  4
0xa2805  ldc.i4.0
0xa2806  call     instance char [mscorlib]System.String::get_Chars(int32)
0xa280b  stloc.s  6
0xa280d  ldloc.s  6
0xa280f  ldc.i4.s 0x41
0xa2811  beq      loc_A2B0F
0xa2816  ldloc.s  6
0xa2818  ldc.i4.s 0x49
0xa281a  beq      loc_A2AE3
0xa281f  ldloc.s  6
0xa2821  ldc.i4.s 0x50
0xa2823  beq      loc_A2AF9
0xa2828  br       loc_A3530
0xa282d  ldloc.s  4
0xa282f  ldc.i4.6
0xa2830  call     instance char [mscorlib]System.String::get_Chars(int32)
0xa2835  stloc.s  6
0xa2837  ldloc.s  6
0xa2839  ldc.i4.s 0x69
0xa283b  bgt.un.s loc_A2854
0xa283d  ldloc.s  6
0xa283f  ldc.i4.s 0x61
0xa2841  beq      loc_A2B25
0xa2846  ldloc.s  6
0xa2848  ldc.i4.s 0x69
0xa284a  beq      loc_A2B4C
0xa284f  br       loc_A3530
0xa2854  ldloc.s  6
0xa2856  ldc.i4.s 0x6E
0xa2858  beq      loc_A2B89
0xa285d  ldloc.s  6
0xa285f  ldc.i4.s 0x78
0xa2861  beq      loc_A2B73
0xa2866  br       loc_A3530
0xa286b  ldloc.s  4
0xa286d  ldc.i4.0
0xa286e  call     instance char [mscorlib]System.String::get_Chars(int32)
0xa2873  stloc.s  6
0xa2875  ldloc.s  6
0xa2877  ldc.i4.s 0x4C
0xa2879  beq      loc_A2BB5
0xa287e  ldloc.s  6
0xa2880  ldc.i4.s 0x4D
0xa2882  beq      loc_A2B9F
0xa2887  br       loc_A3530
0xa288c  ldloc.s  4
0xa288e  ldc.i4.0
0xa288f  call     instance char [mscorlib]System.String::get_Chars(int32)
0xa2894  stloc.s  6
0xa2896  ldloc.s  6
0xa2898  ldc.i4.s 0x48
0xa289a  beq      loc_A2BE1
0xa289f  ldloc.s  6
0xa28a1  ldc.i4.s 0x49
0xa28a3  beq      loc_A2BCB
0xa28a8  br       loc_A3530
0xa28ad  ldloc.s  4
0xa28af  ldc.i4.7
0xa28b0  call     instance char [mscorlib]System.String::get_Chars(int32)
0xa28b5  stloc.s  6
0xa28b7  ldloc.s  6
0xa28b9  ldc.i4.s 0x57
0xa28bb  bgt.un.s loc_A28D4
0xa28bd  ldloc.s  6
0xa28bf  ldc.i4.s 0x46
0xa28c1  beq      loc_A2C0D
0xa28c6  ldloc.s  6
0xa28c8  ldc.i4.s 0x57
0xa28ca  beq      loc_A2C23
0xa28cf  br       loc_A3530
0xa28d4  ldloc.s  6
0xa28d6  ldc.i4.s 0x63
0xa28d8  beq      loc_A2BF7
0xa28dd  ldloc.s  6
0xa28df  ldc.i4.s 0x72
0xa28e1  beq      loc_A2C39
0xa28e6  br       loc_A3530
0xa28eb  ldloc.s  4
0xa28ed  ldc.i4.0
0xa28ee  call     instance char [mscorlib]System.String::get_Chars(int32)
0xa28f3  stloc.s  6
0xa28f5  ldloc.s  6
0xa28f7  ldc.i4.s 0x4C
0xa28f9  beq      loc_A2C65
0xa28fe  ldloc.s  6
0xa2900  ldc.i4.s 0x50
0xa2902  beq      loc_A2C4F
0xa2907  br       loc_A3530
0xa290c  ldloc.s  4
0xa290e  ldc.i4.1
0xa290f  call     instance char [mscorlib]System.String::get_Chars(int32)
0xa2914  stloc.s  6
0xa2916  ldloc.s  6
0xa2918  ldc.i4.s 0x61
0xa291a  beq      loc_A2CA7
0xa291f  ldloc.s  6
0xa2921  ldc.i4.s 0x69
0xa2923  beq      loc_A2C91
0xa2928  ldloc.s  6
0xa292a  ldc.i4.s 0x6E
0xa292c  beq      loc_A2C7B
0xa2931  br       loc_A3530
0xa2936  ldloc.s  4
0xa2938  ldc.i4.0
0xa2939  call     instance char [mscorlib]System.String::get_Chars(int32)
0xa293e  stloc.s  6
0xa2940  ldloc.s  6
0xa2942  ldc.i4.s 0x48
0xa2944  beq      loc_A2CBD
0xa2949  ldloc.s  6
0xa294b  ldc.i4.s 0x4C
0xa294d  beq      loc_A2CD3
0xa2952  br       loc_A3530
0xa2957  ldloc.s  4
0xa2959  ldstr    aStyle_1// "Style"
0xa295e  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa2963  brtrue   loc_A2D2B
0xa2968  br       loc_A3530
0xa296d  ldloc.s  4
0xa296f  ldstr    aAngle// "Angle"
0xa2974  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa2979  brtrue   loc_A308B
0xa297e  br       loc_A3530
0xa2983  ldloc.s  4
0xa2985  ldstr    aVisible// "Visible"
0xa298a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa298f  brtrue   loc_A2D68
0xa2994  br       loc_A3530
0xa2999  ldloc.s  4
0xa299b  ldstr    aReverse// "Reverse"
0xa29a0  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa29a5  brtrue   loc_A2F3F
0xa29aa  br       loc_A3530
0xa29af  ldloc.s  4
0xa29b1  ldstr    aLogbase// "LogBase"
0xa29b6  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa29bb  brtrue   loc_A304C
0xa29c0  br       loc_A3530
0xa29c5  ldloc.s  4
0xa29c7  ldstr    aCrossat// "CrossAt"
0xa29cc  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa29d1  brtrue   loc_A3365
0xa29d6  br       loc_A3530
0xa29db  ldloc.s  4
0xa29dd  ldstr    aMinimum// "Minimum"
0xa29e2  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa29e7  brtrue   loc_A33B4
0xa29ec  br       loc_A3530
0xa29f1  ldloc.s  4
0xa29f3  ldstr    aMaximum// "Maximum"
0xa29f8  call     bool [mscorlib]System.String::op_Equality(string, string)
  ... truncated ...
```
