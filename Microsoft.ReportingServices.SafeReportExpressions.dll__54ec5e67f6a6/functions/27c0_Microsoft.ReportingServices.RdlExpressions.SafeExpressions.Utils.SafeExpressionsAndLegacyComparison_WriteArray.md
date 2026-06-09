# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteArrayMismatchingIndices

- ea: `0x27c0`
- end: `0x2850`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteArrayMismatchingIndices`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2170`

## callees

- `0x27c0`

## pseudocode

```c

```

## disassembly

```asm
0x27c0  ldarg.1
0x27c1  ldstr    aMismatchingind// "MismatchingIndices"
0x27c6  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0x27cb  ldarg.1
0x27cc  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteStartArray()
0x27d1  ldarg.0
0x27d2  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_legacyResult
0x27d7  isinst   [mscorlib]System.Array
0x27dc  stloc.0
0x27dd  ldarg.0
0x27de  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_safeExprResult
0x27e3  isinst   [mscorlib]System.Array
0x27e8  stloc.1
0x27e9  ldloc.1
0x27ea  callvirt instance int32 [mscorlib]System.Array::get_Length()
0x27ef  stloc.2
0x27f0  ldloc.0
0x27f1  callvirt instance int32 [mscorlib]System.Array::get_Length()
0x27f6  stloc.3
0x27f7  ldloc.2
0x27f8  ldloc.3
0x27f9  bgt.s    loc_27FE
0x27fb  ldloc.3
0x27fc  br.s     loc_27FF
0x27fe  ldloc.2
0x27ff  stloc.s  4
0x2801  ldc.i4.0
0x2802  stloc.s  5
0x2804  br.s     loc_2843
0x2806  ldloc.s  5
0x2808  ldloc.3
0x2809  bge.s    loc_2810
0x280b  ldloc.s  5
0x280d  ldloc.2
0x280e  blt.s    loc_281A
0x2810  ldarg.1
0x2811  ldloc.s  5
0x2813  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteValue(int32)
0x2818  br.s     loc_283D
0x281a  ldloc.0
0x281b  ldloc.s  5
0x281d  callvirt instance object [mscorlib]System.Array::GetValue(int32)
0x2822  ldloc.1
0x2823  ldloc.s  5
0x2825  callvirt instance object [mscorlib]System.Array::GetValue(int32)
0x282a  stloc.s  6
0x282c  ldloc.s  6
0x282e  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x2833  brtrue.s loc_283D
0x2835  ldarg.1
0x2836  ldloc.s  5
0x2838  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteValue(int32)
0x283d  ldloc.s  5
0x283f  ldc.i4.1
0x2840  add
0x2841  stloc.s  5
0x2843  ldloc.s  5
0x2845  ldloc.s  4
0x2847  blt.s    loc_2806
0x2849  ldarg.1
0x284a  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteEndArray()
0x284f  ret
```
