# Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::set_ThumbnailMimeType

- ea: `0x290`
- end: `0x2b7`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::set_ThumbnailMimeType`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1f0`
- `0x290`

## pseudocode

```c

```

## disassembly

```asm
0x290  ldarg.1
0x291  brfalse.s loc_2B6
0x293  ldarg.1
0x294  callvirt instance string [mscorlib]System.String::Trim()
0x299  ldsfld   string [mscorlib]System.String::Empty
0x29e  call     bool [mscorlib]System.String::Equals(string, string)
0x2a3  brtrue.s loc_2B6
0x2a5  ldarg.0
0x2a6  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::get_Properties()
0x2ab  ldstr    aThumbnailmimet// "ThumbnailMimeType"
0x2b0  ldarg.1
0x2b1  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x2b6  ret
```
