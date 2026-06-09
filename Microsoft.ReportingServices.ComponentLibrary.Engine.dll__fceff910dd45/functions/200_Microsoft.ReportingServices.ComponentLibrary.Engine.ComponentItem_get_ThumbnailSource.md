# Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::get_ThumbnailSource

- ea: `0x200`
- end: `0x225`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::get_ThumbnailSource`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1f0`
- `0x200`

## pseudocode

```c

```

## disassembly

```asm
0x200  ldarg.0
0x201  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::get_Properties()
0x206  ldstr    aThumbnailsourc// "ThumbnailSource"
0x20b  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::ContainsKey(var<u1>)
0x210  brtrue.s loc_214
0x212  ldnull
0x213  ret
0x214  ldarg.0
0x215  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::get_Properties()
0x21a  ldstr    aThumbnailsourc// "ThumbnailSource"
0x21f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Item(void)
0x224  ret
```
