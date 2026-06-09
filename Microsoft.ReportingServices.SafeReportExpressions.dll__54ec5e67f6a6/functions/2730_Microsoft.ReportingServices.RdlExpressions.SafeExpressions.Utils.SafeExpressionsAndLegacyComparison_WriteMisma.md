# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteMismatchingIndicesForSimpleObjects

- ea: `0x2730`
- end: `0x27a0`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteMismatchingIndicesForSimpleObjects`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2170`

## callees

- `0x2730`

## pseudocode

```c

```

## disassembly

```asm
0x2730  ldarg.1
0x2731  ldstr    aMismatchingind// "MismatchingIndices"
0x2736  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0x273b  ldarg.1
0x273c  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteStartArray()
0x2741  ldarg.3
0x2742  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2747  brtrue.s loc_2751
0x2749  ldarg.3
0x274a  callvirt instance int32 [mscorlib]System.String::get_Length()
0x274f  br.s     loc_2752
0x2751  ldc.i4.0
0x2752  stloc.0
0x2753  ldarg.2
0x2754  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2759  brtrue.s loc_2763
0x275b  ldarg.2
0x275c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2761  br.s     loc_2764
0x2763  ldc.i4.0
0x2764  stloc.1
0x2765  ldloc.0
0x2766  ldloc.1
0x2767  bgt.s    loc_276C
0x2769  ldloc.1
0x276a  br.s     loc_276D
0x276c  ldloc.0
0x276d  stloc.2
0x276e  ldc.i4.0
0x276f  stloc.3
0x2770  br.s     loc_2795
0x2772  ldloc.3
0x2773  ldloc.1
0x2774  bge.s    loc_278A
0x2776  ldloc.3
0x2777  ldloc.0
0x2778  bge.s    loc_278A
0x277a  ldarg.3
0x277b  ldloc.3
0x277c  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x2781  ldarg.2
0x2782  ldloc.3
0x2783  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x2788  beq.s    loc_2791
0x278a  ldarg.1
0x278b  ldloc.3
0x278c  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteValue(int32)
0x2791  ldloc.3
0x2792  ldc.i4.1
0x2793  add
0x2794  stloc.3
0x2795  ldloc.3
0x2796  ldloc.2
0x2797  blt.s    loc_2772
0x2799  ldarg.1
0x279a  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteEndArray()
0x279f  ret
```
