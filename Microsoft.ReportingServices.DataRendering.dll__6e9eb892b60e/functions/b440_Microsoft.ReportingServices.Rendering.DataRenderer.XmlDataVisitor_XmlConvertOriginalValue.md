# Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataVisitor::XmlConvertOriginalValue

- ea: `0xb440`
- end: `0xb4c5`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataVisitor::XmlConvertOriginalValue`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xb340`
- `0xb380`

## callees

- `0xb440`

## pseudocode

```c

```

## disassembly

```asm
0xb440  ldarg.1
0xb441  isinst   [mscorlib]System.String
0xb446  brfalse.s loc_B44F
0xb448  ldarg.1
0xb449  castclass [mscorlib]System.String
0xb44e  ret
0xb44f  ldarg.1
0xb450  isinst   [mscorlib]System.DateTime
0xb455  brfalse.s loc_B490
0xb457  ldarg.1
0xb458  unbox.any [mscorlib]System.DateTime
0xb45d  stloc.0
0xb45e  ldloca.s 0
0xb460  call     instance valuetype [mscorlib]System.DateTimeKind [mscorlib]System.DateTime::get_Kind()
0xb465  stloc.2
0xb466  ldloc.2
0xb467  switch   loc_B47E, loc_B482, loc_B47A
0xb478  br.s     loc_B486
0xb47a  ldc.i4.0
0xb47b  stloc.1
0xb47c  br.s     loc_B488
0xb47e  ldc.i4.2
0xb47f  stloc.1
0xb480  br.s     loc_B488
0xb482  ldc.i4.1
0xb483  stloc.1
0xb484  br.s     loc_B488
0xb486  ldc.i4.0
0xb487  stloc.1
0xb488  ldloc.0
0xb489  ldloc.1
0xb48a  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.DateTime, valuetype [System.Xml]System.Xml.XmlDateTimeSerializationMode)
0xb48f  ret
0xb490  ldarg.1
0xb491  isinst   [mscorlib]System.TimeSpan
0xb496  brfalse.s loc_B4A4
0xb498  ldarg.1
0xb499  unbox.any [mscorlib]System.TimeSpan
0xb49e  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.TimeSpan)
0xb4a3  ret
0xb4a4  ldarg.1
0xb4a5  isinst   [mscorlib]System.IFormattable
0xb4aa  brfalse.s loc_B4BE
0xb4ac  ldarg.1
0xb4ad  castclass [mscorlib]System.IFormattable
0xb4b2  ldnull
0xb4b3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb4b8  callvirt instance string [mscorlib]System.IFormattable::ToString(string, class [mscorlib]System.IFormatProvider)
0xb4bd  ret
0xb4be  ldarg.1
0xb4bf  callvirt instance string [mscorlib]System.Object::ToString()
0xb4c4  ret
```
