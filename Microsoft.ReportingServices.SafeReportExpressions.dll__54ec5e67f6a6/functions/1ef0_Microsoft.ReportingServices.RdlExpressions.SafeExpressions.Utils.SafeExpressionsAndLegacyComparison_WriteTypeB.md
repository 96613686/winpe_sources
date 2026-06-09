# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteTypeBasedDetails

- ea: `0x1ef0`
- end: `0x216f`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteTypeBasedDetails`
- size: `639`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1ea0`

## callees

- `0x1ef0`
- `0x26b0`
- `0x26d0`
- `0x26f0`
- `0x27a0`

## pseudocode

```c

```

## disassembly

```asm
0x1ef0  ldarg.3
0x1ef1  call     valuetype [mscorlib]System.TypeCode [mscorlib]System.Type::GetTypeCode(class [mscorlib]System.Type)
0x1ef6  stloc.0
0x1ef7  ldloc.0
0x1ef8  ldc.i4.1
0x1ef9  sub
0x1efa  switch   loc_20FC, loc_216E, loc_1F48, loc_216E, loc_1F60, loc_1F85, loc_1F98, loc_1FBD, loc_1FD0, loc_1FF5, loc_2008, loc_202D, loc_2040, loc_2072, loc_20A4, loc_20D6, loc_216E, loc_20E9
0x1f47  ret
0x1f48  ldarg.1
0x1f49  ldstr    aBooleanresult// "BooleanResult"
0x1f4e  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0x1f53  ldarg.1
0x1f54  ldarg.2
0x1f55  unbox.any [mscorlib]System.Boolean
0x1f5a  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteValue(bool)
0x1f5f  ret
0x1f60  ldarg.0
0x1f61  ldarg.1
0x1f62  ldarg.2
0x1f63  callvirt instance string [mscorlib]System.Object::ToString()
0x1f68  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1f6d  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteObjectLength(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, int32 length)
0x1f72  ldarg.0
0x1f73  ldarg.1
0x1f74  ldarg.2
0x1f75  unbox.any [mscorlib]System.SByte
0x1f7a  call     int32 [mscorlib]System.Math::Sign(int8)
0x1f7f  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteSignForNumericResult(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, int32 sign)
0x1f84  ret
0x1f85  ldarg.0
0x1f86  ldarg.1
0x1f87  ldarg.2
0x1f88  callvirt instance string [mscorlib]System.Object::ToString()
0x1f8d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1f92  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteObjectLength(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, int32 length)
0x1f97  ret
0x1f98  ldarg.0
0x1f99  ldarg.1
0x1f9a  ldarg.2
0x1f9b  callvirt instance string [mscorlib]System.Object::ToString()
0x1fa0  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1fa5  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteObjectLength(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, int32 length)
0x1faa  ldarg.0
0x1fab  ldarg.1
0x1fac  ldarg.2
0x1fad  unbox.any [mscorlib]System.Int16
0x1fb2  call     int32 [mscorlib]System.Math::Sign(int16)
0x1fb7  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteSignForNumericResult(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, int32 sign)
0x1fbc  ret
0x1fbd  ldarg.0
0x1fbe  ldarg.1
0x1fbf  ldarg.2
0x1fc0  callvirt instance string [mscorlib]System.Object::ToString()
0x1fc5  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1fca  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteObjectLength(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, int32 length)
0x1fcf  ret
0x1fd0  ldarg.0
0x1fd1  ldarg.1
0x1fd2  ldarg.2
0x1fd3  callvirt instance string [mscorlib]System.Object::ToString()
0x1fd8  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1fdd  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteObjectLength(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, int32 length)
0x1fe2  ldarg.0
0x1fe3  ldarg.1
0x1fe4  ldarg.2
0x1fe5  unbox.any [mscorlib]System.Int32
0x1fea  call     int32 [mscorlib]System.Math::Sign(int32)
0x1fef  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteSignForNumericResult(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, int32 sign)
0x1ff4  ret
0x1ff5  ldarg.0
0x1ff6  ldarg.1
0x1ff7  ldarg.2
0x1ff8  callvirt instance string [mscorlib]System.Object::ToString()
0x1ffd  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2002  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteObjectLength(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, int32 length)
0x2007  ret
0x2008  ldarg.0
0x2009  ldarg.1
0x200a  ldarg.2
0x200b  callvirt instance string [mscorlib]System.Object::ToString()
0x2010  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2015  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteObjectLength(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, int32 length)
0x201a  ldarg.0
0x201b  ldarg.1
0x201c  ldarg.2
0x201d  unbox.any [mscorlib]System.Int64
0x2022  call     int32 [mscorlib]System.Math::Sign(int64)
0x2027  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteSignForNumericResult(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, int32 sign)
0x202c  ret
0x202d  ldarg.0
0x202e  ldarg.1
0x202f  ldarg.2
0x2030  callvirt instance string [mscorlib]System.Object::ToString()
0x2035  callvirt instance int32 [mscorlib]System.String::get_Length()
0x203a  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteObjectLength(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, int32 length)
0x203f  ret
0x2040  ldarg.0
0x2041  ldarg.1
0x2042  ldarg.2
0x2043  callvirt instance string [mscorlib]System.Object::ToString()
0x2048  callvirt instance int32 [mscorlib]System.String::get_Length()
0x204d  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteObjectLength(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, int32 length)
0x2052  ldarg.0
0x2053  ldarg.1
0x2054  ldarg.2
0x2055  unbox.any [mscorlib]System.Single
0x205a  call     int32 [mscorlib]System.Math::Sign(float32)
0x205f  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteSignForNumericResult(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, int32 sign)
0x2064  ldarg.0
0x2065  ldarg.1
0x2066  ldarg.2
0x2067  callvirt instance string [mscorlib]System.Object::ToString()
0x206c  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteDecimalIndexForNumericResult(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, string strResult)
0x2071  ret
0x2072  ldarg.0
0x2073  ldarg.1
0x2074  ldarg.2
0x2075  callvirt instance string [mscorlib]System.Object::ToString()
0x207a  callvirt instance int32 [mscorlib]System.String::get_Length()
0x207f  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteObjectLength(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, int32 length)
0x2084  ldarg.0
0x2085  ldarg.1
0x2086  ldarg.2
0x2087  unbox.any [mscorlib]System.Double
0x208c  call     int32 [mscorlib]System.Math::Sign(float64)
0x2091  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteSignForNumericResult(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, int32 sign)
0x2096  ldarg.0
0x2097  ldarg.1
0x2098  ldarg.2
0x2099  callvirt instance string [mscorlib]System.Object::ToString()
0x209e  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteDecimalIndexForNumericResult(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, string strResult)
0x20a3  ret
0x20a4  ldarg.0
0x20a5  ldarg.1
0x20a6  ldarg.2
0x20a7  callvirt instance string [mscorlib]System.Object::ToString()
0x20ac  callvirt instance int32 [mscorlib]System.String::get_Length()
0x20b1  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteObjectLength(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, int32 length)
0x20b6  ldarg.0
0x20b7  ldarg.1
0x20b8  ldarg.2
0x20b9  unbox.any [mscorlib]System.Decimal
0x20be  call     int32 [mscorlib]System.Math::Sign(valuetype [mscorlib]System.Decimal)
0x20c3  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteSignForNumericResult(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, int32 sign)
0x20c8  ldarg.0
0x20c9  ldarg.1
0x20ca  ldarg.2
0x20cb  callvirt instance string [mscorlib]System.Object::ToString()
0x20d0  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteDecimalIndexForNumericResult(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, string strResult)
0x20d5  ret
0x20d6  ldarg.0
0x20d7  ldarg.1
0x20d8  ldarg.2
0x20d9  callvirt instance string [mscorlib]System.Object::ToString()
0x20de  callvirt instance int32 [mscorlib]System.String::get_Length()
0x20e3  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteObjectLength(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, int32 length)
0x20e8  ret
0x20e9  ldarg.0
0x20ea  ldarg.1
0x20eb  ldarg.2
0x20ec  callvirt instance string [mscorlib]System.Object::ToString()
0x20f1  callvirt instance int32 [mscorlib]System.String::get_Length()
0x20f6  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteObjectLength(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, int32 length)
0x20fb  ret
0x20fc  ldarg.3
0x20fd  ldtoken  [mscorlib]System.Guid
0x2102  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2107  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x210c  brtrue.s loc_2132
0x210e  ldarg.3
0x210f  ldtoken  [mscorlib]System.DateTimeOffset
0x2114  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2119  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x211e  brtrue.s loc_2132
0x2120  ldarg.3
0x2121  ldtoken  [mscorlib]System.TimeSpan
0x2126  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x212b  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2130  brfalse.s loc_2145
0x2132  ldarg.0
0x2133  ldarg.1
0x2134  ldarg.2
0x2135  callvirt instance string [mscorlib]System.Object::ToString()
0x213a  callvirt instance int32 [mscorlib]System.String::get_Length()
0x213f  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteObjectLength(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, int32 length)
0x2144  ret
0x2145  ldarg.3
0x2146  callvirt instance bool [mscorlib]System.Type::get_IsArray()
0x214b  brfalse.s loc_2156
0x214d  ldarg.0
0x214e  ldarg.1
0x214f  ldarg.2
0x2150  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteArrayLength(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, object result)
0x2155  ret
0x2156  ldarg.3
0x2157  callvirt instance class [mscorlib]System.Reflection.PropertyInfo[] [mscorlib]System.Type::GetProperties()
0x215c  dup
0x215d  brtrue.s loc_2163
0x215f  pop
0x2160  ldc.i4.0
0x2161  br.s     loc_2165
0x2163  ldlen
0x2164  conv.i4
0x2165  stloc.1
0x2166  ldarg.0
0x2167  ldarg.1
0x2168  ldloc.1
0x2169  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteObjectLength(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, int32 length)
0x216e  ret
```
