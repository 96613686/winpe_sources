# Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::get_ThumbnailMimeType

- ea: `0x260`
- end: `0x285`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::get_ThumbnailMimeType`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1f0`
- `0x260`

## pseudocode

```c

```

## disassembly

```asm
0x260  ldarg.0
0x261  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::get_Properties()
0x266  ldstr    aThumbnailmimet// "ThumbnailMimeType"
0x26b  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::ContainsKey(var<u1>)
0x270  brtrue.s loc_274
0x272  ldnull
0x273  ret
0x274  ldarg.0
0x275  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::get_Properties()
0x27a  ldstr    aThumbnailmimet// "ThumbnailMimeType"
0x27f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Item(void)
0x284  ret
```
