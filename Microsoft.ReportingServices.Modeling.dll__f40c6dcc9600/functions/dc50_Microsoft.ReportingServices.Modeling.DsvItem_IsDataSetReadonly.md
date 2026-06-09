# Microsoft.ReportingServices.Modeling.DsvItem::IsDataSetReadonly

- ea: `0xdc50`
- end: `0xdc72`
- name: `Microsoft.ReportingServices.Modeling.DsvItem::IsDataSetReadonly`
- size: `34`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2f8c0`
- `0x2fec0`
- `0x30c10`
- `0x31750`
- `0x327c0`

## callees

- `0xdc50`

## string_xrefs

- `0xdc56`: `_ReadOnly`

## pseudocode

```c

```

## disassembly

```asm
0xdc50  ldarg.0
0xdc51  callvirt instance class [System.Data]System.Data.PropertyCollection [System.Data]System.Data.DataSet::get_ExtendedProperties()
0xdc56  ldstr    aReadonly// "_ReadOnly"
0xdc5b  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xdc60  stloc.0
0xdc61  ldloc.0
0xdc62  brfalse.s loc_DC70
0xdc64  ldloc.0
0xdc65  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xdc6a  call     bool [mscorlib]System.Convert::ToBoolean(object, class [mscorlib]System.IFormatProvider)
0xdc6f  ret
0xdc70  ldc.i4.0
0xdc71  ret
```
