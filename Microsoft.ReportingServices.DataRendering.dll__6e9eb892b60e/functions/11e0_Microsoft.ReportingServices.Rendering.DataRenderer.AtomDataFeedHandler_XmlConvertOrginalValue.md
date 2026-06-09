# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::XmlConvertOrginalValue

- ea: `0x11e0`
- end: `0x1243`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::XmlConvertOrginalValue`
- size: `99`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1180`
- `0x12e0`
- `0x1530`
- `0x1670`
- `0x19c0`
- `0x3430`

## callees

- `0x11e0`

## pseudocode

```c

```

## disassembly

```asm
0x11e0  ldarg.0
0x11e1  isinst   [mscorlib]System.String
0x11e6  brfalse.s loc_11EF
0x11e8  ldarg.0
0x11e9  castclass [mscorlib]System.String
0x11ee  ret
0x11ef  ldarg.0
0x11f0  isinst   [mscorlib]System.DateTime
0x11f5  brfalse.s loc_1204
0x11f7  ldarg.0
0x11f8  unbox.any [mscorlib]System.DateTime
0x11fd  ldc.i4.3
0x11fe  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.DateTime, valuetype [System.Xml]System.Xml.XmlDateTimeSerializationMode)
0x1203  ret
0x1204  ldarg.0
0x1205  isinst   [mscorlib]System.TimeSpan
0x120a  brfalse.s loc_1218
0x120c  ldarg.0
0x120d  unbox.any [mscorlib]System.TimeSpan
0x1212  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.TimeSpan)
0x1217  ret
0x1218  ldarg.0
0x1219  isinst   [mscorlib]System.IFormattable
0x121e  brfalse.s loc_1232
0x1220  ldarg.0
0x1221  castclass [mscorlib]System.IFormattable
0x1226  ldnull
0x1227  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x122c  callvirt instance string [mscorlib]System.IFormattable::ToString(string, class [mscorlib]System.IFormatProvider)
0x1231  ret
0x1232  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1237  ldstr    a0// "{0}"
0x123c  ldarg.0
0x123d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x1242  ret
```
