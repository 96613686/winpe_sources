# Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::WritePropertyValue

- ea: `0x60f0`
- end: `0x628f`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::WritePropertyValue`
- size: `415`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x5cc0`
- `0x5d90`
- `0x5fe0`

## callees

- `0x60f0`

## pseudocode

```c

```

## disassembly

```asm
0x60f0  ldarg.1
0x60f1  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x60f6  call     valuetype [mscorlib]System.TypeCode [mscorlib]System.Type::GetTypeCode(class [mscorlib]System.Type)
0x60fb  stloc.0
0x60fc  ldloc.0
0x60fd  switch   loc_61ED, loc_627D, loc_61A7, loc_6153, loc_6177, loc_6234, loc_6165, loc_61FE, loc_6258, loc_6210, loc_626A, loc_6222, loc_627D, loc_6246, loc_61DB, loc_61B4, loc_6189, loc_627D, loc_627D
0x614e  br       loc_627D
0x6153  ldarg.0
0x6154  ldfld    class [Microsoft.ReportingServices.OData]Microsoft.ReportingServices.OData.Json.JsonWriter Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::jsonWriter
0x6159  ldarg.1
0x615a  unbox.any [mscorlib]System.Boolean
0x615f  callvirt instance void [Microsoft.ReportingServices.OData]Microsoft.ReportingServices.OData.Json.JsonWriterBase::WriteValue(bool)
0x6164  ret
0x6165  ldarg.0
0x6166  ldfld    class [Microsoft.ReportingServices.OData]Microsoft.ReportingServices.OData.Json.JsonWriter Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::jsonWriter
0x616b  ldarg.1
0x616c  unbox.any [mscorlib]System.Byte
0x6171  callvirt instance void [Microsoft.ReportingServices.OData]Microsoft.ReportingServices.OData.Json.JsonWriterBase::WriteValue(unsigned int8)
0x6176  ret
0x6177  ldarg.0
0x6178  ldfld    class [Microsoft.ReportingServices.OData]Microsoft.ReportingServices.OData.Json.JsonWriter Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::jsonWriter
0x617d  ldarg.1
0x617e  unbox.any [mscorlib]System.Char
0x6183  callvirt instance void [Microsoft.ReportingServices.OData]Microsoft.ReportingServices.OData.Json.JsonWriterBase::WriteValue(int32)
0x6188  ret
0x6189  ldarg.0
0x618a  ldfld    class [Microsoft.ReportingServices.OData]Microsoft.ReportingServices.OData.Json.JsonWriter Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::jsonWriter
0x618f  ldarg.1
0x6190  unbox.any [mscorlib]System.DateTime
0x6195  ldarg.0
0x6196  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::useMsDateFormat
0x619b  brtrue.s loc_61A0
0x619d  ldc.i4.2
0x619e  br.s     loc_61A1
0x61a0  ldc.i4.1
0x61a1  callvirt instance void [Microsoft.ReportingServices.OData]Microsoft.ReportingServices.OData.Json.JsonWriterBase::WriteValue(valuetype [mscorlib]System.DateTime, valuetype [Microsoft.ReportingServices.OData]Microsoft.ReportingServices.OData.ODataVersion)
0x61a6  ret
0x61a7  ldarg.0
0x61a8  ldfld    class [Microsoft.ReportingServices.OData]Microsoft.ReportingServices.OData.Json.JsonWriter Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::jsonWriter
0x61ad  ldnull
0x61ae  callvirt instance void [Microsoft.ReportingServices.OData]Microsoft.ReportingServices.OData.Json.JsonWriterBase::WriteValue(string)
0x61b3  ret
0x61b4  ldarg.0
0x61b5  ldfld    class [Microsoft.ReportingServices.OData]Microsoft.ReportingServices.OData.Json.JsonWriter Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::jsonWriter
0x61ba  ldarg.0
0x61bb  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::treatDecimalAsDouble
0x61c0  brtrue.s loc_61CA
0x61c2  ldarg.1
0x61c3  unbox.any [mscorlib]System.Double
0x61c8  br.s     loc_61D5
0x61ca  ldarg.1
0x61cb  unbox.any [mscorlib]System.Decimal
0x61d0  call     float64 [mscorlib]System.Convert::ToDouble(valuetype [mscorlib]System.Decimal)
0x61d5  callvirt instance void [Microsoft.ReportingServices.OData]Microsoft.ReportingServices.OData.Json.JsonWriterBase::WriteValue(float64)
0x61da  ret
0x61db  ldarg.0
0x61dc  ldfld    class [Microsoft.ReportingServices.OData]Microsoft.ReportingServices.OData.Json.JsonWriter Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::jsonWriter
0x61e1  ldarg.1
0x61e2  unbox.any [mscorlib]System.Double
0x61e7  callvirt instance void [Microsoft.ReportingServices.OData]Microsoft.ReportingServices.OData.Json.JsonWriterBase::WriteValue(float64)
0x61ec  ret
0x61ed  ldarg.0
0x61ee  ldfld    class [Microsoft.ReportingServices.OData]Microsoft.ReportingServices.OData.Json.JsonWriter Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::jsonWriter
0x61f3  ldsfld   string [mscorlib]System.String::Empty
0x61f8  callvirt instance void [Microsoft.ReportingServices.OData]Microsoft.ReportingServices.OData.Json.JsonWriterBase::WriteValue(string)
0x61fd  ret
0x61fe  ldarg.0
0x61ff  ldfld    class [Microsoft.ReportingServices.OData]Microsoft.ReportingServices.OData.Json.JsonWriter Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::jsonWriter
0x6204  ldarg.1
0x6205  unbox.any [mscorlib]System.Int16
0x620a  callvirt instance void [Microsoft.ReportingServices.OData]Microsoft.ReportingServices.OData.Json.JsonWriterBase::WriteValue(int16)
0x620f  ret
0x6210  ldarg.0
0x6211  ldfld    class [Microsoft.ReportingServices.OData]Microsoft.ReportingServices.OData.Json.JsonWriter Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::jsonWriter
0x6216  ldarg.1
0x6217  unbox.any [mscorlib]System.Int32
0x621c  callvirt instance void [Microsoft.ReportingServices.OData]Microsoft.ReportingServices.OData.Json.JsonWriterBase::WriteValue(int32)
0x6221  ret
0x6222  ldarg.0
0x6223  ldfld    class [Microsoft.ReportingServices.OData]Microsoft.ReportingServices.OData.Json.JsonWriter Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::jsonWriter
0x6228  ldarg.1
0x6229  unbox.any [mscorlib]System.Int64
0x622e  callvirt instance void [Microsoft.ReportingServices.OData]Microsoft.ReportingServices.OData.Json.JsonWriterBase::WriteValue(int64)
0x6233  ret
0x6234  ldarg.0
0x6235  ldfld    class [Microsoft.ReportingServices.OData]Microsoft.ReportingServices.OData.Json.JsonWriter Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::jsonWriter
0x623a  ldarg.1
0x623b  unbox.any [mscorlib]System.SByte
0x6240  callvirt instance void [Microsoft.ReportingServices.OData]Microsoft.ReportingServices.OData.Json.JsonWriterBase::WriteValue(int8)
0x6245  ret
0x6246  ldarg.0
0x6247  ldfld    class [Microsoft.ReportingServices.OData]Microsoft.ReportingServices.OData.Json.JsonWriter Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::jsonWriter
0x624c  ldarg.1
0x624d  unbox.any [mscorlib]System.Single
0x6252  callvirt instance void [Microsoft.ReportingServices.OData]Microsoft.ReportingServices.OData.Json.JsonWriterBase::WriteValue(float32)
0x6257  ret
0x6258  ldarg.0
0x6259  ldfld    class [Microsoft.ReportingServices.OData]Microsoft.ReportingServices.OData.Json.JsonWriter Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::jsonWriter
0x625e  ldarg.1
0x625f  unbox.any [mscorlib]System.UInt16
0x6264  callvirt instance void [Microsoft.ReportingServices.OData]Microsoft.ReportingServices.OData.Json.JsonWriterBase::WriteValue(int32)
0x6269  ret
0x626a  ldarg.0
0x626b  ldfld    class [Microsoft.ReportingServices.OData]Microsoft.ReportingServices.OData.Json.JsonWriter Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::jsonWriter
0x6270  ldarg.1
0x6271  unbox.any [mscorlib]System.UInt32
0x6276  conv.u8
0x6277  callvirt instance void [Microsoft.ReportingServices.OData]Microsoft.ReportingServices.OData.Json.JsonWriterBase::WriteValue(int64)
0x627c  ret
0x627d  ldarg.0
0x627e  ldfld    class [Microsoft.ReportingServices.OData]Microsoft.ReportingServices.OData.Json.JsonWriter Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::jsonWriter
0x6283  ldarg.1
0x6284  castclass [mscorlib]System.String
0x6289  callvirt instance void [Microsoft.ReportingServices.OData]Microsoft.ReportingServices.OData.Json.JsonWriterBase::WriteValue(string)
0x628e  ret
```
