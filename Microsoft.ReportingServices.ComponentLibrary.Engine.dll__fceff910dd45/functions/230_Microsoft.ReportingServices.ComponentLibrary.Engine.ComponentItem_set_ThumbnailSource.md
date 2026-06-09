# Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::set_ThumbnailSource

- ea: `0x230`
- end: `0x257`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::set_ThumbnailSource`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1f0`
- `0x230`

## pseudocode

```c

```

## disassembly

```asm
0x230  ldarg.1
0x231  brfalse.s loc_256
0x233  ldarg.1
0x234  callvirt instance string [mscorlib]System.String::Trim()
0x239  ldsfld   string [mscorlib]System.String::Empty
0x23e  call     bool [mscorlib]System.String::Equals(string, string)
0x243  brtrue.s loc_256
0x245  ldarg.0
0x246  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::get_Properties()
0x24b  ldstr    aThumbnailsourc// "ThumbnailSource"
0x250  ldarg.1
0x251  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x256  ret
```
