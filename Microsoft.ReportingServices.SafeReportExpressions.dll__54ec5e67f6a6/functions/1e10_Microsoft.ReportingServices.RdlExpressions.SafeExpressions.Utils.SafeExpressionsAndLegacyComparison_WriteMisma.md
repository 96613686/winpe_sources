# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteMismatchDetails

- ea: `0x1e10`
- end: `0x1ea0`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteMismatchDetails`
- size: `144`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1710`
- `0x19c0`

## callees

- `0x1de0`
- `0x1e10`
- `0x1ea0`
- `0x2170`

## pseudocode

```c

```

## disassembly

```asm
0x1e10  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor()
0x1e15  stloc.0
0x1e16  ldloc.0
0x1e17  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x1e1c  stloc.1
0x1e1d  ldloc.1
0x1e1e  ldc.i4.0
0x1e1f  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::set_Formatting(valuetype [Newtonsoft.Json]Newtonsoft.Json.Formatting)
0x1e24  ldloc.1
0x1e25  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteStartObject()
0x1e2a  ldloc.1
0x1e2b  ldstr    aSafeexpression// "SafeExpressionsResult"
0x1e30  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0x1e35  ldarg.0
0x1e36  ldloc.1
0x1e37  ldarg.0
0x1e38  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_safeExprResult
0x1e3d  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteObjectProperties(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, object result)
0x1e42  ldloc.1
0x1e43  ldstr    aLegacyresult// "LegacyResult"
0x1e48  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0x1e4d  ldarg.0
0x1e4e  ldloc.1
0x1e4f  ldarg.0
0x1e50  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_legacyResult
0x1e55  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteObjectProperties(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, object result)
0x1e5a  ldarg.0
0x1e5b  ldarg.0
0x1e5c  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_safeExprResult
0x1e61  ldarg.0
0x1e62  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_legacyResult
0x1e67  call     instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::NeitherIsNull(object objA, object objB)
0x1e6c  brfalse.s loc_1E81
0x1e6e  ldarg.0
0x1e6f  ldloc.1
0x1e70  ldarg.0
0x1e71  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_legacyResult
0x1e76  ldarg.0
0x1e77  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_safeExprResult
0x1e7c  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteTypeBasedDifferences(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, object legacyResult, object safeExprResult)
0x1e81  ldloc.1
0x1e82  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteEndObject()
0x1e87  ldarg.0
0x1e88  ldloc.0
0x1e89  callvirt instance string [mscorlib]System.Object::ToString()
0x1e8e  stfld    string Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_mismatchDetail
0x1e93  leave.s  loc_1E9F
0x1e95  ldloc.1
0x1e96  brfalse.s loc_1E9E
0x1e98  ldloc.1
0x1e99  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e9e  endfinally
0x1e9f  ret
```
